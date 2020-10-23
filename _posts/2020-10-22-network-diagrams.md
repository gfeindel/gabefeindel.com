---
date: 2020-10-22
layout: post
title: How to draw effective network diagrams
---

Informative network diagrams are an essential skill for every sysadmin. Here are some principles and practices I've encountered over the years.

A well executed network diagram is beautiful and informative. If one must choose between beauty and utility, though, the latter wins. An informative network diagram accelerates troubleshooting, supports engineering and bolsters security.

Every network diagram consists of nodes, edges and containers. Every element should be labeled. The meaning of these diagram elements depends on the type of network diagram. Mixing network diagram types often leads to confusion. 

There are three types of network diagrams: physical diagrams, logical diagrams, and flow diagrams.  

## Physical Diagrams

Physical diagrams, also called wiring diagrams or layer 1 diagrams, represent the physical connections in a network. They are useful for troubleshooting basic connectivity issue, identifying single points of failure, and planning changes.

Nodes represent network devices. Edges represent physical connections between network device ports. Areas typically represent either logical network segments or physical location.

### Best practices

 - Label nodes with their hostname and IP. 
 - Label edges with the ports at the near and far end. If you use one label, place it near one end and use a consistent format to indicate the near and far port. 
 - Use rounded edges to indicate direction. Use "gaps" for line intersections.
 - Use a star or tree topology depending on the complexity of the network.

## Logical Diagrams

Logical diagrams, also called layer 3 diagrams, represent the IP topology of a network. They are useful for troubleshooting routing issues, identifying potential security risks, or planning network changes.

Nodes represent network devices and networks. Edges represent the connections of devices to networks. Containers represent logical network segments or physical areas.

### Best practices

 - Label nodes with their hostname and IP.
 - Label edges with the host's address on that subnet. Include just the host bits for brevity. For example, host 192.168.1.2 can be labeled as ".2."
 - Use containers to indicate logical segments of the network, such as Edge, LAN, WAN, and secured areas.

## Flow Diagrams

Flow diagrams represent the flow of information and the interfaces between network elements. These are often used to describe service architecture.

Nodes represent service elements, such as clients and servers. Edges represent flows, typically labeled with TCP ports. Areas typically represent networks.

### Best practices

 - Use directed arrows to indicate flow of information.
 - Use colors to indicate related flows.
 - Label edges with the TCP or UDP port numbers.
 - Label nodes with their hostname, function or IP address.
 - Use containers to indicate network boundaries.

## References

The following references have greatly helped me develop my own network diagrams and have informed many of my own practices above.

 - [Network Documentation Series: Logical Diagrams](https://packetpushers.net/network-documentation-series-logical-diagram/) (John Kerns)
 - [How to Draw Clear L3 Logical Network Diagrams](https://packetpushers.net/how-to-draw-clear-l3-logical-network-diagrams/) (Jaakko Rautanen)
