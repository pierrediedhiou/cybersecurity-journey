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
## Logs Fundamentals

### What are Logs?
Logs are recorded traces of activity on a system, application or
network. They are essential for security monitoring, incident
investigation, troubleshooting and compliance.

---

## Use Cases of Logs

| Use Case | Description |
|----------|-------------|
| **Security Events Monitoring** | Logs help detect anomalous behavior when real-time monitoring is used |
| **Incident Investigation and Forensics** | Logs are traces of every activity, offering detailed information on what happened during an incident. Used for root cause analysis |
| **Troubleshooting** | Logs record errors in systems or applications, helping diagnose and fix issues |
| **Performance Monitoring** | Logs provide valuable insights into application performance |
| **Auditing and Compliance** | Logs establish a trail of activities, making compliance requirements easier to meet |

---

## Types of Logs

| Log Type | Usage | Example Events |
|----------|-------|----------------|
| **System Logs** | Helpful for troubleshooting OS issues, provides info on operating system activities | System startup/shutdown, driver loading, system errors, hardware events |
| **Security Logs** | Helps detect and investigate incidents, provides security-related activity info | Authentication events, authorization events, security policy changes, user account changes, abnormal activity |
| **Application Logs** | Contains events specific to an application, both interactive and non-interactive activity | User interaction, application changes, application updates, application errors |
| **Audit Logs** | Provides detailed info on system changes and user events, useful for compliance | Data access, system changes, user activity, policy enforcement |
| **Network Logs** | Provides info on outgoing/incoming network traffic, useful for troubleshooting and investigations | Incoming/outgoing traffic, network connections, firewall logs |
| **Access Logs** | Provides detailed info about access to different resources | Webserver access, database access, application access, API access |

---

## Windows Security Event IDs

| Event ID | Description |
|----------|-------------|
| `4624` | A user account successfully logged in |
| `4625` | A user account failed to login |
| `4634` | A user account successfully logged off |
| `4720` | A user account was created |
| `4722` | A user account was enabled |
| `4724` | An attempt was made to reset an account's password |
| `4725` | A user account was disabled |
| `4726` | A user account was deleted |

### Key Event IDs to Monitor During Investigations
✅ 4625 — Repeated failures may indicate brute force attempts

✅ 4720 — Unexpected account creation may indicate persistence

✅ 4724 — Password reset attempts on sensitive accounts

✅ 4726 — Account deletion may indicate covering tracks
---

## Log Analysis Checklist
✅ Identify which log type is relevant to the investigation

✅ Check Security Logs for authentication anomalies (4624, 4625)

✅ Check Audit Logs for unauthorized system or data changes

✅ Check Network Logs to trace incoming/outgoing connections

✅ Check Access Logs to identify who accessed what resource

✅ Correlate logs across multiple sources for full picture

✅ Use logs to build a chronological timeline of the incident

✅ Preserve original logs as evidence — do not modify them
## SIEM (Security Information and Event Management)

### What is a SIEM?
A SIEM is the core security solution used by SOC analysts. It
performs four key functions:
1. Collects logs from various log sources
2. Standardizes their format into a consistent structure
3. Correlates the data across sources
4. Detects malicious activities using detection rules
---

### Log Source Categories

| Category | Description | Generating Devices | Example Logs |
|----------|-------------|---------------------|---------------|
| **Host-Centric** | Events occurring within or related to a host | Windows, Linux, servers | File access, authentication attempts, process execution, registry key changes, PowerShell execution |
| **Network-Centric** | Events from hosts communicating with each other or the internet | Firewalls, IDS/IPS, routers | SSH connections, FTP file access, web traffic | A user accessing the company's resources through VPN. Network file sharing Activity

---

### Host-Centric Log Examples
. A user accessing a file
. A user attempting to authenticate
. A process execution activity
. A process adding/editing/deleting a registry key or value
. PowerShell execution
### Network-Centric Log Examples
. SSH connection
. A file being accessed via FTP
. Web traffic
. A user accessing a company resource over the network
---

### Why SIEM Matters for SOC Analysts
✅ Centralizes logs from across the entire environment

✅ Makes it possible to correlate events across multiple sources

✅ Standardized format allows consistent searching and analysis

✅ Detection rules automatically flag suspicious patterns

✅ Without a SIEM, analysts would need to check each log source

individually — extremely slow and error-prone
## Firewall Fundamentals

### What is a Firewall?
A firewall inspects a network or device's incoming and outgoing
traffic, blocking unauthorized access — similar to a security
guard controlling who enters a building.

---

### Firewall Rule Components
| Component | Description |
|-----------|-------------|
| **Source Address** | The IP address originating the traffic |
| **Destination Address** | The IP address receiving the traffic |
| **Port** | The port number used for the traffic |
| **Protocol** | The protocol used during communication |
| **Action** | What happens when matching traffic is identified |
| **Direction** | Whether the rule applies to incoming or outgoing traffic |

---

### Firewall Actions
| Action | Description |
|--------|-------------|
| **Allow** | The defined traffic is permitted through |
| **Deny** | The defined traffic is blocked |
| **Forward** | Traffic is redirected to a different network segment |

---

### Firewall Rule Types
| Rule Type | Applies To | Example |
|-----------|-----------|---------|
| **Inbound Rules** | Incoming traffic only | Allow incoming HTTP (port 80) on a web server |
| **Outbound Rules** | Outgoing traffic only | Block outgoing SMTP (port 25) from all devices except the mail server |
| **Forward Rules** | Redirects traffic within the network | Forward incoming HTTP (port 80) to the internal web server |

---

### Types of Firewalls
| Firewall Type | Characteristics |
|---------------|-----------------|
| **Stateless Firewalls** | Basic filtering, no track of previous connections, efficient for high-speed networks |
| **Stateful Firewalls** | Recognize traffic by patterns, support complex rules, monitor network connections |
| **Proxy Firewalls** | Inspect data inside packets, provide content filtering, application control, decrypt SSL/TLS |
| **Next-Generation Firewalls (NGFW)** | Advanced threat protection, intrusion prevention system, heuristic anomaly detection, decrypt SSL/TLS |

---

### Firewall Evolution Summary
Stateless → Stateful → Proxy → Next-Generation

(simplest)                      (most advanced)
Each generation adds more inspection depth and security capability,
at the cost of more processing overhead.
Each generation adds more inspection depth and security capability,
at the cost of more processing overhead.
