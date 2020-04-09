---
title: "Windows firewall mis-classifies AnyConnect VPN"
categories: windows wfas troubleshooting anyconnect vpn
comments: false
layout: post
---

## TL;DR

If you use Windows Firewall and AnyConnect VPN, set `HKLM\System\CurrentControlSet\Services\Netlogon\Parameters\NegativeCachePeriod=0x0`. If that doesn't work, set `HKLM\...\DnsCache\Parameters\NegativeCacheTtl=0x0`, too.

## Explanation
On a domain-joined system, the Netlogon service tries to discover a domain controller when it receives a network connection change event. It does this by calling DsGetDc, which attempts to resolve `_ldap._tcp.<domain>`. NLA uses the success or failure of this attempt to classify the network as DomainAuthenticated or not. If Netlogon calls DsGetDc before your VPN has added the appropriate routes, the query fails, and WFAS thinks your VPN is a private or public network.

Microsoft explains this [here](https://support.microsoft.com/en-us/help/4550028/firewall-profile-does-not-switch-to-domain-when-using-third-party-vpn). Cisco TAC confirmed the issue. Ironically, Microsoft considers it a VPN client bug, and Cisco considers it a Microsoft bug.

## Symptoms

 - Remote access tools mysteriously stop working on your VPN-connected clients.
 - VOIP apps get one-way or audio or no audio at all.

## Diagnosis

Check the WFAS profile for your AnyConnect VPN connection.

```powershell
Get-NetAdapter -InterfaceDescription "Cisco AnyConnect*" |% {Get-NetConnectionProfile -InterfaceAlias $_.Name}
```

Check your DNS cache for negative cache entries for the _LDAP SRV record.

```powershell
ipconfig /displaydns | find "_ldap._tcp"
```

Check if DsGetDc returns a list of DCs or an error.

```
nltest /dsgetdc:<domain>
```

## Solution

Set  `HKLM\System\CurrentControlSet\Services\Netlogon\Parameters\NegativeCachePeriod = 0` and `HKLM\System\CurrentControlSet\Services\Dnscache\Parameters\NegativeCacheTtl = 0`. Group policy preferences are the easiest way to deploy this to your clients.

## Reference

 - https://support.microsoft.com/en-us/help/4550028/firewall-profile-does-not-switch-to-domain-when-using-third-party-vpn

