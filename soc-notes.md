# SOC (Security Operations Center) Notes

## What is a SOC?
A Security Operations Center (SOC) is a team responsible for
detecting and responding to cybersecurity incidents within an
organization.

---

## The Three Pillars of a SOC
| Pillar | Description |
|--------|-------------|
| **People** | The SOC team — analysts, engineers and managers |
| **Process** | The structured procedures the SOC team follows |
| **Technology** | The security tools and solutions used by the SOC |

A mature SOC requires all three pillars working together to
efficiently detect and respond to incidents.

---

## Core SOC Responsibilities

### Detection
The SOC focuses on detecting four main categories of issues:

| Category | Description | Example |
|----------|-------------|---------|
| **Vulnerabilities** | Weaknesses in software that attackers could exploit | Unpatched Windows machines |
| **Unauthorized Activity** | Access using stolen or unauthorized credentials | Login from unusual geographic location |
| **Policy Violations** | Breaches of company security policy | Downloading pirated media, insecure file sharing |
| **Intrusions** | Unauthorized access to systems and networks | Exploited web app, malware infection |

### Response
Once an incident is detected, the SOC supports incident response by:
- Minimizing the impact of the incident
- Performing root cause analysis
- Supporting the incident response team through containment,
eradication and recovery

---

## SOC Team Roles and Responsibilities

| Role | Responsibilities |
|------|-------------------|
| **SOC Analyst (Level 1)** | First responder to detections. Performs basic alert triage to determine if a detection is harmful. Reports through proper channels |
| **SOC Analyst (Level 2)** | Performs deeper investigation. Correlates data from multiple sources for thorough analysis |
| **SOC Analyst (Level 3)** | Experienced professional. Proactively hunts for threat indicators. Supports incident response including containment, eradication and recovery |
| **Security Engineer** | Deploys and configures security solutions used by the SOC team |
| **Detection Engineer** | Creates the security rules and logic used by detection solutions. Sometimes performed by Level 2/3 Analysts |
| **SOC Manager** | Manages SOC processes and team support. Reports security posture to the CISO |

---

## SOC Analyst Escalation Path
Detection Triggered

↓

Level 1 Analyst — Basic triage, determine if harmful

↓ (if needs deeper investigation)

Level 2 Analyst — Correlate data, deeper analysis

↓ (if critical security incident)

Level 3 Analyst — Threat hunting, full incident response

↓

SOC Manager — Reports posture to CISO
---

## Key Relationships
- **SOC Manager** reports to the **CISO** (Chief Information
Security Officer) on the organization's security posture
- **Detection Engineers** work closely with **Level 2/3 Analysts**
to build effective detection rules
- **Security Engineers** ensure the tools that **Analysts** rely
on are properly deployed and maintained
---

## Key Relationships
- **SOC Manager** reports to the **CISO** (Chief Information
Security Officer) on the organization's security posture
- **Detection Engineers** work closely with **Level 2/3 Analysts**
to build effective detection rules
- **Security Engineers** ensure the tools that **Analysts** rely
on are properly deployed and maintained
