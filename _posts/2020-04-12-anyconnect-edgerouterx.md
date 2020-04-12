---
title: "Ubiquiti EdgeRouter X and Cisco AnyConnect VPN"
categories: troubleshooting anyconnect vpn ubiquity edgerouter erx
comments: false
layout: post
---

## TL;DR

If you have a Ubiquiti EdgeRouter X and Cisco AnyConnect, and you experience periodic disruptions of 10-20 seconds, make sure you enabled hardware offload on ERX:

```
configure
set system offload hwnat enable
commit
save
```

## Explanation
I don't know why this occurs, only that several forum posts strongly recommend enabling hardware offload and tuning the conntrack table parameters. I haven't changed conntrack yet. The EdgeRouter is not "plug-and-play." 

I experience a similar problem with Teams audio regardless of VPN connection. In that case, community recommends disabling SIP ALG. Don't yet know if that helped.

## Symptoms

 - Every 3-5 minutes, AnyConnect appears to stop passing traffic, but split-tunnelled traffic works fine.
 - AnyConnect says it's connected.

## Solution

Enable hardware offload. Consider disabling helper modules. 

## Reference

 - https://help.ubnt.com/hc/en-us/articles/115006567467-EdgeRouter-Hardware-Offloading
 - https://community.ui.com/questions/SSL-VPN-Connections-Dropping/583d51e6-7556-411b-8f95-e73deec6bbbf


