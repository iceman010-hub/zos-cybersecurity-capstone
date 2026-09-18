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

## The package

The complete proposal is one 119 page document:
**[`ZOS_Cybersecurity_Proposal.pdf`](ZOS_Cybersecurity_Proposal.pdf)**

| Pages | Section |
|-------|---------|
| 11–12 | Executive summary and introduction |
| 12–17 | Unified network system design, physical and wireless topology |
| 18–19 | Physical security and the AZTOF framework |
| 20–28 | Risk assessment, CSET before/after comparison, top five findings, three priority threats |
| 29–42 | CSET assessment narrative (baseline February 20, 2026 and redesign February 23, 2026) |
| 43–48 | Finance and pricing, professional services, five year total cost of ownership |
| 49–55 | Management plan, business continuity and incident response summaries |
| 57–80 | The four policies in full |
| 81–92 | Incident Response Plan |
| 93–101 | Cybersecurity Management Plan |
| 102–114 | IT Department Business Continuity Plan |
| 115–119 | Appendices A–E, network diagrams and floor plan |

### Individual documents

The same package, split so any one document can be read on its own. Each is
lifted straight from the pages above, so nothing here diverges from the master.

```
design/
  network-design.pdf                              Unified network system design and topology
policies/
  password-protection-policy.pdf                  Length, screening, rotation, MFA, lockout
  server-vulnerability-management-policy.pdf      Scanning cadence, remediation SLAs, pen testing
  network-device-management-policy.pdf            Inventory, secure mgmt access, firmware lifecycle
  cloud-service-provider-management-policy.pdf    CSP onboarding, data tiering, offboarding
plans/
  incident-response-plan.pdf                      IRT structure, P1–P5 severity model
  cybersecurity-management-plan.pdf               AZTOF framework and its six domains
  business-continuity-plan.pdf                    Recovery team, phases, Austin failover
budget/
  cybersecurity-budget.pdf                        Line item pricing and five year TCO
diagrams/
  network-diagrams.pdf                            Appendices A–E, before/after and floor plan
```

## Using this

See [LICENSE](LICENSE). Read it, share it, reference it with attribution, don't
submit it as your own coursework. The policies adapt SANS and CRF templates,
which carry their own terms.

## About me

I'm an IT System Administrator currently and finished my AAS in Cybersecurity at Dallas College. Find me on [LinkedIn](https://www.linkedin.com/in/noevalencia).
