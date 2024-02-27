# Despoofed
> A deep dive into packet spoofing

## ROUGH DRAFT

## Introduction
Packet spoofing is a deceptive technique in computer networks where the source address of a data packet is manipulated to appear as if it's coming from a trusted source, rather than its true origin. This alteration can be used to hide the actual source of the traffic, often for malicious purposes. By impersonating a trusted source, attackers can bypass network security measures, launch powerful reflection attacks like DDoS, gain unauthorized system access, or trick users into trusting and interacting with the manipulated data.

## The current state of packet spoofing
Packet spoofing, while once more straightforward, has become increasingly challenging to execute today due to the widespread adoption of network security best practices and filtering mechanisms. One of the primary defenses against spoofing is "ingress filtering" or "source address validation." Based on a best practice recommended by documents such as [BCP 38](https://www.ietf.org/rfc/bcp/bcp38.html), ingress filtering involves checking the source address of incoming packets at the edge of a network. If the source address isn't valid or doesn't belong to the range of IP addresses managed by that network, the packet is discarded.

Internet Service Providers and large network operators have been encouraged to implement these filters to ensure that traffic leaving their networks has a legitimate source address that belongs to their IP address space. By doing so, even if an attacker within their network tries to spoof an IP address, the malicious packets would be dropped before they reach the intended target.

In summary, the combination of industry best practices like ingress filtering, advancements in networking technology, and the proactive measures taken by ISPs and network operators have made it significantly more challenging for attackers to successfully execute spoofing attacks in the modern internet landscape.

## Mothers Against Spoofed Packets
[Mutually Agreed Norms for Routing Security](https://manrs.org) *(MANRS)* is a global initiative designed to bolster the security and resilience of the internet's routing infrastructure. By fostering collaboration among network operators and internet exchange points, MANRS aims to counter common routing threats.

One of its primary focuses is on filtering and [anti-spoofing](https://www.manrs.org/netops/guide/antispoofing/), ensuring that traffic is from legitimate sources and thus directly combating IP spoofing. With the broad adoption of MANRS recommendations, many of the world's filters preventing spoofing have been implemented. Additionally, MANRS emphasizes efficient coordination among operators and global validation of routing information to further enhance network security.

###### Participants
- [cdn/cloud providers](https://www.manrs.org/cdn-cloud-providers/participants/) *([csv](data/cdn.csv), [json](data/cdn.json))*
- [ixps](https://www.manrs.org/ixps/participants/) *([csv](data/ixp.csv), [json](data/ixp.json))*
- [network operators](https://www.manrs.org/netops/participants/) *([csv](data/netops.csv), [json](data/netops.json))*

###### Statical Coverage Report
- **Total ASNs:** 1,403
- **Total IPv4 Ranges:** 65,723
- **Total IPv4 Addresses:** 774,313,984

This accounts for roughly **25%** of the **routeable** address space.

## CAIDA
The [CAIDA Spoofer Project](https://www.caida.org/projects/spoofer/) is an initiative undertaken by the [Center for Applied Internet Data Analysis](https://www.caida.org/) *(CAIDA)* to measure and analyze the susceptibility of the internet to source address validation *(SAV)* failures, which are often exploited in various cyberattacks, such as Distributed Denial of Service *(DDoS)* attacks using IP address spoofing. The project provides free software to the public, enabling individuals and organizations to test their networks for vulnerabilities related to IP spoofing. The gathered data is then used by researchers to create a global view of the current state of SAV enforcement and to devise strategies to improve internet security.

The significance of the Spoofer Project lies in its potential to highlight areas of the internet that are vulnerable to spoofing attacks, thereby encouraging network operators to adopt best practices in network filtering. By offering a clear picture of the state of IP spoofing vulnerabilities worldwide, the project aims to drive change and reduce the potential for malicious actors to misuse the internet's infrastructure. The collaborative nature of the project, with participants from around the world, underscores the importance of collective efforts in ensuring a safer online environment.

###### Reports
- https://spoofer.caida.org/summary.php
- https://spoofer.caida.org/country_stats.php
- https://spoofer.caida.org/as_stats.php

You can lookup a specific ASN to get a report on it, for example here is the report for [OVH](https://spoofer.caida.org/as.php?asn=16276).

## References
- [RFC 3704 - Ingress Filtering for Multihomed Networks](https://datatracker.ietf.org/doc/html/rfc3704)
- [SAVing the Internet - Measuring the adoption of Source Address Validation (SAV) by network providers](https://pure.tudelft.nl/ws/portalfiles/portal/115359139/Final_Submission.pdf)
- [MANRS API](https://manrs.stoplight.io/docs/manrs-public-api/38c368e1d6b43-manrs-public-api)
- [DDoS Aspire Final Report](https://www.caida.org/funding/ddos-aspire/ddos-aspire_finalreport.pdf)
- [Mind Your MANRS - Measuring the MANRS Ecosystem](https://www.caida.org/catalog/papers/2022_mind_your_manrs/mind_your_manrs.pdf)

## Todo
- Compile list of blocked ASN's world-wide to discover ASN's that can allow spoofing
- Shit on people like [this](https://spoofer.network/)
- Show CAIDA spoofer software result samples
- Include code to automate finding ASN's that will allow spoofing
- CAIDA API documentation

___

###### Mirrors for this repository: [acid.vegas](https://git.acid.vegas/despoofed) • [SuperNETs](https://git.supernets.org/acidvegas/despoofed) • [GitHub](https://github.com/acidvegas/despoofed) • [GitLab](https://gitlab.com/acidvegas/despoofed) • [Codeberg](https://codeberg.org/acidvegas/despoofed)
