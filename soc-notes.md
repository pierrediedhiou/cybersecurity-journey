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
## Incident Response Fundamentals

### Alert Classification
| Type | Description | Example |
|------|-------------|---------|
| **False Positive** | Alert appears dangerous but is actually benign | High data transfer flagged, turns out to be a scheduled backup |
| **True Positive** | Alert is confirmed genuinely harmful | Phishing email confirmed to be malicious, sent to compromise a user |

True positive alerts are referred to as **incidents** and are
assigned a severity level for prioritization.

---

### Incident Severity Levels
Critical > High > Medium > Low
Critical severity incidents always receive the highest priority
response, followed by high, medium and low.

---

### Common Incident Types
| Type | Description |
|------|-------------|
| **Malware Infections** | Caused by malicious files (text, documents, executables). Most common incident type |
| **Security Breaches** | Unauthorized access to confidential data |
| **Data Leaks** | Confidential info exposed to unauthorized entities — can be intentional or accidental |
| **Insider Attacks** | Incidents originating from within the organization, often more dangerous due to greater access |
| **DoS Attacks** | Floods a system/network with false requests, exhausting resources and causing unavailability |

---

### Key Security Solutions
| Solution | Purpose |
|----------|---------|
| **SIEM** | Centralizes and correlates logs to identify incidents |
| **AV** | Detects known malicious programs through regular scans |
| **EDR** | Deployed on endpoints, protects against advanced threats, can contain and eradicate |

---

### Incident Response Playbook Example — Phishing Email
1. Notify all stakeholders of the phishing email incident
2. Conduct header and body analysis to determine if malicious
3. Look for attachments and analyze them
4. Determine if anyone opened the attachments
5. Isolate infected systems from the network
6. Block the email sender
---

## SANS Incident Response Framework — PICERL

The SANS framework has 6 phases, remembered with the acronym **PICERL**.

| Phase | Explanation | Example |
|-------|-------------|---------|
| **Preparation** | Building resources to handle an incident: IR teams, response plans, security solutions | Conducting phishing awareness training for employees |
| **Identification** | Looking for abnormal behavior indicating an incident | Security team notices unusual data transfer, traces it to a phishing-delivered malicious file |
| **Containment** | Minimizing the impact by isolating the victim machine or disabling compromised accounts | Isolating the host from the network to prevent lateral movement |
| **Eradication** | Removing the threat completely from the environment | Running a deep malware scan to remove malicious software |
| **Recovery** | Recovering affected systems from backup or rebuilding them, then testing | Reconfiguring the compromised host and restoring exfiltrated data from backup |
| **Lessons Learned** | Identifying and documenting gaps in detection and analysis to improve future response | Post-incident review meeting to analyze root cause and improve security |

### PICERL Workflow
Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned
---

## SANS vs NIST Framework Comparison

| SANS | NIST |
|------|------|
| Preparation | Preparation |
| Identification | Detection and Analysis |
| Containment | Containment, Eradication, and Recovery |
| Eradication | Containment, Eradication, and Recovery |
| Recovery | Containment, Eradication, and Recovery |
| Lessons Learned | Post Incident Activity |

**Key difference:** SANS splits Containment, Eradication and
Recovery into three separate phases, while NIST groups them
together as one combined phase. SANS also separates Identification
clearly while NIST combines Detection and Analysis.

---

## Incident Response Best Practices Checklist
✅ Classify every alert as false positive or true positive

✅ Assign severity level immediately to confirmed incidents

✅ Always prioritize Critical severity incidents first

✅ Follow PICERL or NIST framework consistently

✅ Capture memory data before containment if forensics needed

✅ Use playbooks for known incident types (phishing, malware, etc)

✅ Document every action taken during the response

✅ Always conduct a Lessons Learned / Post Incident review
