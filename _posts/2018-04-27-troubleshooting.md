---
layout: post
title:  "How to troubleshoot effectively"
date:   2018-04-27 08:33 -0400
comments: true 
categories: skills troubleshooting 
---
Troubleshooting is an essential skill for every sysadmin. Software breaks. Hardware fails. Most of the time, people break stuff. When that happens, your customers rely on you to fix it. Watching an experienced sysadmin troubleshoot is almost magical. Given a few slivers of information, he makes a snap judgement about the root cause--and is often right. This might lead you to believe that troubleshooting is an innate--even mystical--ability, not a teachable skill. Wrong!

You can learn to troubleshoot any system. Given an effective method, sufficient information, and appropriate tools, you can diagnose any problem. If you are an experienced sysadmin, I hope this post helps you deconstruct your intuitive ability and share it with others. If you're new to the game, I hope this post helps you to develop the same mystical ability, what [Daniel Kahneman][1] calls "expert intuition," that earns you guru status with your customers and coworkers.

## What is troubleshooting?

[Steve Litt][2] defines troubleshooting as a ten-step, universal process. For the IT sysadmin, a simpler, five-step process will do. Are you ready? Take a deep breath. Here it is:
  1. Define the problem.
  2. Appy a workaround.
  3. Diagnose the problem.
  4. Fix the problem.
  5. Test the solution.
  
That's it? Yep. Not terribly insightful, original or erudite. But it works. You might be surprised at how uncommon common sense is. Now, let's get down to business and consider each step in turn.

## Step 1. Define the problem.

You cannot troubleshoot without some trouble to shoot. Without a good problem definition, you will waste valuable time and energy. A good problem definition is MAD--measurable, accurate, and detailed.

  1. A _measurable_ problem definition is quantifiable and verifiable. In other words, it is possible to determine objectively and unequivocably whether the problem is fixed.
  2. An _accurate_ problem definition describes the _right_ problem. This might make you chuckle, but how often has a misunderstanding of the problem sent you troubleshooting your way down a rabbit trail? 
  3. A _detailed_ problem definition includes all relevant information to understand the problem. It describes environmental details, such as software versions, network addresses and user information. It includes error messages, steps to reproduce the problem, and anything else that might aid with troubleshooting.

The effective sysadmin owns the problem definition. Users often report problems in experiential terms like, "The internet isn't working," or, "I can't log in." Such problem statements are often misleading, vague, and unverifiable. The customer does not have the knowledge, training or expertise to develop an effective problem definition. Unfairly expect this of the customer, and it will frustrate both of you.

> Customer Service Tip: Repeat the problem definition back to the user to confirm its accuracy. This affords two important benefits. First, it reassures the user that you understand the problem. Second, it provokes necessary clarification.

## Step 2. Apply a workaround if appropriate.

Every sysadmin is in the business of customer service. Your first priority is to get your customer back to work as quickly as possible. If you can apply a workaround that enables the customer to work, do it now.

> Customer Service Tip: Empathize with your user's frustration. Practice active listening. A frustrated user's caustic remarks can sting. Remind yourself (and your user) that you have a common goal--to get her back to work.

## Step 3. Diagnose the root cause.

Begin your root cause analysis by developing a model of the system. An effective model identifies the system components and how they interface with each other and with users. The client-server model and the Open Systems Interconnection (OSI) Model are two common representations of distributed systems. Distributed systems consist of computers that communicate with each other over a network. In the client-server model, a _client_ receives data over a _network_ from a _server_. The OSI Model, developed in the 1970s, divides the system into seven logical layers.  Experienced sysadmins use mental models to quickly explore the problem space, but visual models are also effective.

> Tip: Check the basics first! Save time and effort by first testing for common causes such as a disconnected cable, missing DNS record, and other forehead-slappers.

If none of the common causes is to blame, use the scientific method to iteratively reduce the problem space until you identify the root cause. The scientific method consists of four steps: Guess, Test, Observe, Refine.

  1. Guess which component that contains the fault. This is not a blind guess. It is based on the problem definition and your understanding of the system.
  2. Test the selected component to determine whether it is functioning correctly.
  3. Observe the test results. It's a good idea to keep notes.
  4. Refine your guess about the location of the fault. If the selected component is faulty, expand the model for that component and repeat. If not, choose another component to test.

The Guess and Refine steps follow either a linear search or a binary search. A linear search begins at one end of the model and proceeds to the other. In a client-server model, it begins with the client and moves towards the server, or vice versa. In the OSI model, it begins at the Application Layer and moves towards the Physical Layer. Linear search is the better approach for systems that you do not thoroughly understand.

The binary search method, also called "divide-and-conquer," isolates the problem more quickly by using diagnostic tests that eliminate large portions of the problem space. This is the most efficient method, but it requires a thorough understanding of the system in order to design diagnostic tests and draw accurate conclusions from those results.

The Test and Observe steps use tools, diagnostic information and critical thinking to measure the health of the chosen component. The component dictates the appropriate tools. Every sysadmin should be familiar with common network tools such as _ping_, _nslookup_, _traceroute_, Nmap, Wireshark and _telnet_. Windows sysadmins should know how to use Event Viewer, Performance Monitor, Task Manager, and Sysinternals tools. Linux sysadmins should know how to use _ps_, _top_, _lsof_, _lsmod_, and others. For more information about these and other tools, see the links at the end of the post.

Log files contain valuable diagnostic information about the activities of the system. Log entries are usually timestamped, which provides context and correlation with other components and systems. Windows has Event Viewer. Linux has Syslog. Many applications create their own log files. Always check the logs. The information found there can significantly reduce the problem space by identifying the faulty component, or ruling out other components.

Now that you have a scientific method, diagnostic information, and appropriate tools, you have everything you need to troubleshoot any IT system! Of course, finding the problem is not the goal. Fixing it is.

## Step 4. Fix the problem.

Whether it's user error, a bad network cable, or a complex logic error, you will eventually identify the root cause. Fixing the problem is a cooperative effort between the user, the sysadmin, and, if necessary, the vendor of the IT system. There are two kinds of fixes: workarounds and permanent solutions. A _workaround_ enables the customer to work while you troubleshoot. A _permanent solution_ fixes the problem in such a way that it should never occur again. Consider a leaky web application that hangs the server, for example. Rebooting the server is a workaround. Fixing the memory mananagement bug in the application code is a permanent solution.

## Step 5. Test the solution.

This should go without saying, but in the chaotic world of the IT sysadmin, it's easy to apply a fix, assume it worked, close the ticket, and move on. I've done it. You've done it. Don't do it. This is sloppy and leads to re-work and bad customer reviews. When you apply a fix, confirm with the user that the system works. This is where that problem definition proves invaluable. The issue is fixed if the behavior described in the problem definition no longer occurs.

## Conclusion

That's it! If this all sounded like common sense to you, good! You are well on your way to effective troubleshooting. Leave your comments and suggestions below! Thanks for reading.

Until next time, stay curious!

[1]: http://en.wikipedia.org/wiki/Daniel_Kahneman
[2]: http://www.troubleshooters.com

