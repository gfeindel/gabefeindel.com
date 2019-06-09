---
layout: post
title:  "Group Policy As Code"
categories: learning infrastructure as code
comments: true
---
While working on a domain migration project this afternoon, I discovered the PowerShell command `Set-GPRegistryValue`. That sparked the idea for a config management tool for group policy that uses Git, JSON and PowerShell. Eventually I'll throw some proof of concept code up on Github to prove if it is viable or not. Microsoft offers group policy version control in the MDOP suite, but MDOP requires an Enterprise Agreement.

Why a config management tool for group policy? Because it is easy to mess up! Have you ever broken something in group policy? I have...

## The problem with group policy

Out of box, group policy lacks version control and configuration management functionality. Historically, the only way to edit a GPO is through the UI of the Group Policy Management Console or Group Policy Editor. Your comments, if you remember to leave them, are the only record of the change. The typical group policy change process might look like this:

  1. Create a test policy, applied to a test OU that contains only your system.
  2. If the policy works, apply it to the rest of the (poor, unsuspecting) IT team.
  3. If that works, deploy to production.
  4. Hold your breath for 24 hours.

## A better way to manage group policy

The concept of "infrastructure as code" captivates me. The main idea is to apply the same principles, tools and processes to infrastructure management that developers use for their code. Instead of configuring snowflake servers via the UI, you create definition files and scripts, store them in your version control system, and run them through a battery of automated tests, before deploying to production. If you'd like to learn more, check out Kief Morris' book on the topic.

The basic tool chain for this hypothetical "group policy as code" tool includes a VCS, definition files, and Powershell. I use Git for my VCS. YAML, JSON, or any other serialization language would work for the definition file. Since Powershell has native support for JSON, that is what I plan to use. Powershell will read the definition files and convert them to group policies. Eventually, I could imagine a CI pipeline that automatically tests these definitions on a virtual machine to ensure correctness.

### Version Control: Git

I use Git to manage all my scripts and definition files already, so it is natural for me to use it for this too. You can use whatever VCS you want. I like Git because it is open source, easy to use, and very popular.

### Definition files

Here's where it gets interesting. Set-GPRegistryValue manipulates policy settings by referencing the registry directly. It requires at least the guid of the policy, the registry path, the value name, value type, and value data. Here's a minimum viable definition file:

{% highlight json %}
{
	"guid" = "{<guid>}"
	"computersetting" : [
		{
			"key" : "registry_key"
			"valuename" : "value name"
			"value" : "value data"
			"type" : "DWORD|REGSZ|etc"
		}
	]
	"usersetting" : []
}
{% endhighlight %}

### Powershell

Once you have a definition file, the Powershell code to apply it might look something like this:

{% highlight powershell %}
$definition = Get-Content .\definition.json
$policy = $definition | ConvertFrom-Json
foreach($setting in $policy.computersetting) {
	Set-GPRegistryValue -Guid $policy.guid @setting
}
{% endhighlight %}

Now, for it to be truly useful as a config management tool, it must remove settings that do not exist in the definition. That can be accomplished with the use of the Get and Set cmdlets. Sounds like a great application for a DSC resource!

### Continuous Integration

A CI tool like Jenkins, Team City or Visual Studios Team Foundation Server could automate testing of your definition files and the group policies they create. Once you know the policy is correct, then you can apply to production with confidence.

## Summary

Group policy is easy to break. Maybe "group policy as code" is one way to improve the reliability and quality of group policy changes. How do you manage your group policy? Leave your thoughts and comments below!
 
