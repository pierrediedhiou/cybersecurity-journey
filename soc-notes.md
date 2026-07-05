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
## IDS Fundamentals

### What is an IDS?
An Intrusion Detection System (IDS) monitors network or host
activity for signs of malicious behavior and raises alerts when
suspicious activity is detected.

---

### IDS Deployment Types
| Type | Scope | Description |
|------|-------|-------------|
| **HIDS** (Host IDS) | Single host | Installed individually on hosts, detects threats specific to that host only |
| **NIDS** (Network IDS) | Entire network | Monitors network-wide traffic for malicious activity, regardless of specific hosts |

---

### IDS Detection Modes
| Mode | How it Works | Strength | Weakness |
|------|-------------|----------|----------|
| **Signature-Based** | Matches traffic against known attack patterns (signatures) | Very accurate for known threats | Cannot detect new/unknown attacks |
| **Anomaly-Based** | Learns normal baseline behavior, alerts on deviation | Can detect unknown/zero-day attacks | Higher false positive rate |
| **Hybrid** | Combines signature-based and anomaly-based detection | Leverages strengths of both methods | More complex to tune and maintain |

---

### IDS Tools
| Tool | Description |
|------|-------------|
| **Snort** | Open-source IDS developed in 1998. Uses signature-based and anomaly-based detection. One of the most widely used IDS solutions |

---

### IDS Detection Mode Comparison Summary
Signature-Based  → Known threats     → Fast, accurate, but blind to new attacks

Anomaly-Based    → Unknown threats   → Detects novel attacks, more false positives

Hybrid           → Best of both      → Combines strengths, more complex setup
---

### Key IDS Concepts to Remember
✅ HIDS = single host, NIDS = whole network

✅ Signature-based = known attacks only

✅ Anomaly-based = detects deviations from baseline

✅ Hybrid = combines both approaches

✅ IDS detects and alerts — it does NOT block (that's IPS)
## CyberChef

### What is CyberChef?
CyberChef is a free, simple and intuitive web-based application
for performing various cyber operation tasks directly in your
browser — no installation required.

Available at: **gchq.github.io/CyberChef**

---

### CyberChef Interface — Four Areas
| Area | Description |
|------|-------------|
| **1. Operations** | The full list of available operations you can use (encoding, decoding, encryption, hashing, compression, etc) |
| **2. Recipe** | Where you build your workflow by adding and chaining operations together in sequence |
| **3. Input** | Where you paste or type the data you want to process |
| **4. Output** | Where the result of your recipe appears after processing the input |

---

### CyberChef Workflow
Input data → Apply Operations (Recipe) → Output result
---

### Common CyberChef Use Cases
| Use Case | Operations Used |
|----------|----------------|
| Decode Base64 encoded data | From Base64 |
| Encode text to Base64 | To Base64 |
| Decrypt XOR encoded strings | XOR |
| Identify hash type | Analyze Hash |
| Convert hex to text | From Hex |
| Decompress data | Gunzip / Unzip |
| Decode URL encoded strings | URL Decode |
| Identify file type from bytes | Detect File Type |
| Parse timestamps | From UNIX Timestamp |
| Decode malware strings | Multiple chained operations |

---

### Why CyberChef Matters for SOC Analysts
---

### Common CyberChef Use Cases
| Use Case | Operations Used |
|----------|----------------|
| Decode Base64 encoded data | From Base64 |
| Encode text to Base64 | To Base64 |
| Decrypt XOR encoded strings | XOR |
| Identify hash type | Analyze Hash |
| Convert hex to text | From Hex |
| Decompress data | Gunzip / Unzip |
| Decode URL encoded strings | URL Decode |
| Identify file type from bytes | Detect File Type |
| Parse timestamps | From UNIX Timestamp |
| Decode malware strings | Multiple chained operations |

---

### Why CyberChef Matters for SOC Analysts
✅ Quickly decode suspicious Base64 strings found in logs
✅ Decode encoded malware payloads for analysis
✅ Convert and analyze data without writing code
✅ Chain multiple operations into a single recipe
✅ Used daily in SOC, DFIR and malware analysis workflows
✅ No installation needed — runs entirely in the browser
## Security Principles

### The CIA Triad
| Pillar | Goal | Attacked By |
|--------|------|-------------|
| **Confidentiality** | Only authorized persons can access data | Disclosure |
| **Integrity** | Data cannot be altered without detection | Alteration |
| **Availability** — Systems and services available when needed | Destruction/Denial |

---

### The DAD Triad — Attacks on CIA
| Attack | Targets | Example |
|--------|---------|---------|
| **Disclosure** | Confidentiality | Leaking confidential employee data |
| **Alteration** | Integrity | Modifying a bank cheque or financial record |
| **Destruction/Denial** | Availability | DDoS attack taking down a web service |

---

### Additional Security Properties
| Property | Description |
|----------|-------------|
| **Authenticity** | Ensures data, systems or identities are genuine and not forged |
| **Nonrepudiation** | Ensures a party cannot deny having performed an action |

---

### Security Models

#### Bell-LaPadula Model — Confidentiality Focused
| Rule | Name | Description |
|------|------|-------------|
| Simple Security Property | No Read Up | Lower security subjects cannot read higher security objects |
| Star Security Property | No Write Down | Higher security subjects cannot write to lower security objects |
| Discretionary Security Property | Access Matrix | Uses an access matrix to allow read and write operations |

**Key principle:** Protects sensitive data from being read or leaked
downward to lower clearance levels.

---

#### Biba Model — Integrity Focused
| Rule | Name | Description |
|------|------|-------------|
| Simple Integrity Property | No Read Down | Higher integrity subjects should not read lower integrity objects |
| Star Integrity Property | No Write Up | Lower integrity subjects should not write to higher integrity objects |

**Key principle:** Prevents lower integrity data from corrupting
higher integrity data.

---

#### Clark-Wilson Model — Integrity Focused
| Component | Description |
|-----------|-------------|
| **CDI** (Constrained Data Item) | Data whose integrity must be preserved |
| **UDI** (Unconstrained Data Item) | All other data — user and system input |
| **TP** (Transformation Procedure) | Programmed operations (read, write) that maintain CDI integrity |
| **IVP** (Integrity Verification Procedure) | Procedures that check and ensure the validity of CDIs |

---

### Security Models Comparison
| Model | Goal | Key Concept |
|-------|------|-------------|
| **Bell-LaPadula** | Confidentiality | No read up, no write down |
| **Biba** | Integrity | No read down, no write up |
| **Clark-Wilson** | Integrity | CDI, UDI, TP, IVP |

---

### Vulnerability, Threat and Risk
| Concept | Definition | Example |
|---------|------------|---------|
| **Vulnerability** | A weakness susceptible to attack | Unpatched software |
| **Threat** | A potential danger associated with a vulnerability | Attacker targeting the unpatched software |
| **Risk** | Likelihood of threat exploiting vulnerability and its business impact | High likelihood + critical system = high risk |

**Formula:** Vulnerability × Threat = Risk

---

### Defence-in-Depth
A security strategy that creates multiple layers of security
controls. If one layer fails, others remain to protect the system.
Also called **Multi-Level Security**.
Layer 1: Perimeter security (firewall)
Layer 2: Network segmentation
Layer 3: Host-based security (EDR, AV)
Layer 4: Application security
Layer 5: Data encryption
Layer 6: User awareness and training
