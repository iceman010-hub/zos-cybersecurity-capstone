# ZOS Cybersecurity Infrastructure Proposal

My capstone project. It's a complete cybersecurity infrastructure program for Zenith Orbital Systems (ZOS), a fictional aerospace and satellite communications company running Low Earth Orbit data relay and autonomous flight telemetry for commercial and defense clients.

ZOS is fictional, but I built the whole thing like a real engagement. I started with a formal CISA CSET assessment against NIST CSF 2.0, found the gaps, redesigned the network to close every one of them, wrote the policies, documented the response and continuity plans, and costed it out with a five year budget. The full 119 page proposal package is in this repo.

> Everything here is fictional. The company, the people, the addresses, and the network are all made up. It's an academic project built to show GRC and security architecture work end to end. No real organization or data is involved.

## The scenario

ZOS runs satellite command and control out of a primary ground station in Dallas with a secondary relay hub in Austin. About 200 staff across engineering, mission operations, IT security, and admin. The thing that drives the whole design is the stakes. At a ground station, a security failure isn't just a data breach. A compromised station means a satellite you can't command, so the security posture had to match that.

## What I did

**Assessed first, then designed.** I ran a CSET assessment against NIST CSF 2.0 on the original network on February 20, 2026. It came back at a Security Assurance Level of LOW. Then I redesigned the network and ran a second assessment on the rebuilt design on February 23, 2026 to measure the improvement. Every part of the proposal traces back to a specific finding from that first assessment.

**Built a governance framework.** I put together a framework I called AZTOF (Adaptive Security and Zero Trust Operations Framework) by combining NIST CSF 2.0, NIST SP 800-207 Zero Trust Architecture, CISA Zero Trust Maturity Model 2.0, and MITRE ATT&CK Enterprise. It's organized into six domains so every security area has clear ownership and measurable outcomes.

**Redesigned the network.** Full hardware refresh with enterprise gear. Palo Alto NGFW in an HA pair, Cisco Catalyst core and access switching, Meraki Wi-Fi 6E, segmented VLANs, a proper DMZ, and Zscaler Zero Trust Network Access replacing traditional VPN to kill the lateral movement risk.

**Wrote the policy suite.** Five policies following SANS template methodology: Server Vulnerability Management, Password Protection, Network Device Management, Application/CSP Management, and an overarching Cybersecurity Management Plan.

**Documented the plans.** A full Incident Response Plan with an IRT structure and a P1 to P5 severity model, plus a Business Continuity Plan built around ground to space link redundancy and failover to the Austin hub.

**Costed it out.** A complete budget with real market pricing, roughly $1.86M in year one, and a five year total cost of ownership analysis.

## Before and after

The redesign moved the network from a CSET Security Level of LOW to MODERATE/HIGH. A few of the bigger changes:

| Area | Before | After |
|------|--------|-------|
| Firewall | Basic ISP gateway | Palo Alto PA-5220 NGFW, HA pair |
| Network monitoring | None | Splunk SIEM, 250GB/day ingest |
| Endpoint protection | Basic antivirus | Huntress Managed EDR, 24/7 SOC |
| Remote access | None | Zscaler Zero Trust Exchange |
| Wireless | Unmanaged APs, open SSIDs | Meraki Wi-Fi 6E, 802.1X, isolated public VLAN |
| Identity | Basic AD, no MFA | Okta MFA plus CyberArk PAM |
| Incident response | None | Full IRT, P1 to P5 severity model |
| Awareness training | None | KnowBe4 quarterly plus phishing simulations |

## Frameworks and tools

CISA CSET, NIST CSF 2.0, NIST SP 800-207, CISA Zero Trust Maturity Model 2.0, MITRE ATT&CK, and SANS policy templates. The risk work uses Defense in Depth Index and Business Risk Profile scoring across infrastructure, applications, operations, and people.

## What's in the repo

The full proposal package is one PDF: [`ZOS_Cybersecurity_Proposal.pdf`](ZOS_Cybersecurity_Proposal.pdf). It covers the network design, physical security, the AZTOF framework, the CSET assessment narrative, risk analysis, all five policies, the IRP, the BCP, and the full budget.

## About me

I'm an IT System Administrator currently and finished my AAS in Cybersecurity at Dallas College in May 2026. Find me on [LinkedIn](https://www.linkedin.com/in/noevalencia).
