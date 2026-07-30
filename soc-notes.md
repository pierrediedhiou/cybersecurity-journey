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
## Cybersecurity Career Paths

### Blue Team Roles
| Role | Description | Key Skills |
|------|-------------|------------|
| **Security Analyst (SOC L1/L2/L3)** | Monitors, investigates and responds to security activity on devices and networks | SIEM, log analysis, incident response, threat hunting |
| **Security Engineer** | Builds and maintains security systems and processes. The architect of cybersecurity | Network security, system hardening, security tooling |
| **Detection Engineer** | Creates detection rules and logic for security solutions | SIEM rules, threat intelligence, scripting |
| **Forensic Analyst** | Investigates security incidents by collecting and analyzing digital evidence | DFIR, Volatility, FTK Imager, chain of custody |
| **Incident Responder** | Leads the response to confirmed security incidents | PICERL framework, containment, eradication, recovery |
| **Malware Analyst** | Analyzes malicious software to understand its behavior and capabilities | Reverse engineering, FlareVM, REMnux, CAPA |

---

### Blue vs Red Team Comparison
| | Blue Team | Red Team |
|---|---|---|
| **Focus** | Defense | Offense |
| **Goal** | Detect and respond to attacks | Simulate attacks to test defenses |
| **Roles** | SOC Analyst, Security Engineer, DFIR | Penetration Tester, Red Teamer, Bug Bounty Hunter |
| **Tools** | SIEM, EDR, IDS, Wireshark | Metasploit, Burp Suite, Nmap, Hydra |
| **Mindset** | Defender — protect and detect | Attacker — find and exploit |
## Identity, Authentication, Authorisation and Accountability (IAAA)

### What is IAAA?
IAAA is a framework of four core principles that govern how access
to systems and resources is managed, verified and audited.

---

### The Four IAAA Principles
| Principle | Definition | Examples |
|-----------|------------|---------|
| **Identity** | A unique account representing a person or service | Username, email address, user ID, service account |
| **Authentication** | Proving that identity is genuine | Password, OTP, passkey, biometrics, smart card |
| **Authorisation** | What that identity is allowed to do | File permissions, role-based access, firewall rules |
| **Accountability** | Recording and alerting on who did what, when and where | Logs, audit trails, SIEM alerts |

---

### IAAA Flow
Identity       → Who are you?
Authentication → Prove it
Authorisation  → What can you do?
Accountability → Everything you do is recorded
---

### Authentication Methods
| Method | Type | Strength |
|--------|------|----------|
| Password | Something you know | Low — can be guessed or stolen |
| PIN | Something you know | Low — short and guessable |
| OTP (One-Time Password) | Something you have | Medium — time-limited |
| Passkey | Something you have | High — cryptographic, phishing resistant |
| Biometrics (fingerprint, face) | Something you are | High — hard to replicate |
| Smart card | Something you have | High — physical possession required |
| MFA (combination) | Multiple factors | Very High |

---

### Authorisation Models
| Model | Description | Example |
|-------|-------------|---------|
| **DAC** (Discretionary Access Control) | Owner controls who accesses their resources | File owner sets permissions on their files |
| **MAC** (Mandatory Access Control) | System enforces access based on security labels | Bell-LaPadula model, military clearance levels |
| **RBAC** (Role-Based Access Control) | Access based on user role in the organization | Admin role, user role, read-only role |
| **ABAC** (Attribute-Based Access Control) | Access based on multiple attributes | Department + location + time of day |

---

### Accountability in Practice
| Tool | How it Supports Accountability |
|------|-------------------------------|
| **SIEM** | Centralizes and correlates logs to detect and alert on suspicious activity |
| **Audit Logs** | Record every action taken by every user and system |
| **IDS/IPS** | Detects and alerts on suspicious network behavior |
| **EDR** | Records endpoint activity including process creation and file changes |

---

### Why IAAA Matters for SOC Analysts
✅ Identity helps you know WHICH account was involved
✅ Authentication logs show HOW they logged in
✅ Authorisation tells you WHAT they should and should not access
✅ Accountability (logs) show WHAT they actually did
✅ Together they enable incident investigation and attribution
✅ Missing any one pillar makes forensics and response much harder
## SOC Role in the Blue Team

### What is a SOC?
A Security Operations Center (SOC) is a team of IT security
professionals tasked with five core responsibilities:
1. Monitoring   — Continuously watch networks and systems for threats
2. Preventing   — Proactively block known threats before they occur
3. Detecting    — Identify malicious activity and anomalies
4. Investigating — Analyze alerts to determine scope and impact
5. Responding   — Contain, eradicate and recover from incidents
---

### SOC Team Models
| Model | Description | Best For |
|-------|-------------|---------|
| **Internal SOC** | Dedicated in-house security team | Large organizations with budget |
| **Virtual SOC** | Remote security team, no physical location | Medium organizations |
| **MSSP** | Outsourced SOC provided by a third party | Small/medium organizations without resources |
| **Hybrid SOC** | Combination of internal team and MSSP | Organizations wanting internal control with external support |

---

### SOC vs CIRT
| | SOC | CIRT |
|---|---|---|
| **Focus** | Ongoing monitoring and detection | Active incident response |
| **When active** | 24/7 continuous | Activated when incident confirmed |
| **Goal** | Detect threats early | Contain and eradicate confirmed incidents |
| **Relationship** | SOC detects and escalates | CIRT responds to SOC escalations |

---

### Key SOC Metrics (KPIs)
| Metric | Description |
|--------|-------------|
| **MTTD** | Mean Time to Detect — how long to identify a threat |
| **MTTR** | Mean Time to Respond — how long to contain and resolve |
| **False Positive Rate** | Percentage of alerts that are not real threats |
| **Alert Volume** | Total number of alerts processed per day/week |
| **Incident Escalation Rate** | Percentage of alerts escalated from L1 to L2/L3 |

---

### SOC Tools Stack
| Category | Common Tools |
|----------|-------------|
| **SIEM** | Splunk, Microsoft Sentinel, QRadar, Elastic SIEM |
| **EDR** | CrowdStrike, SentinelOne, Microsoft Defender |
| **IDS/IPS** | Snort, Suricata, Zeek |
| **Threat Intelligence** | MISP, VirusTotal, Shodan |
| **SOAR** | Splunk SOAR, Palo Alto XSOAR |
| **Ticketing** | ServiceNow, Jira |
| **Network Analysis** | Wireshark, tcpdump, Zeek |

---

### SOC Daily Workflow
Start of shift
↓
Review overnight alerts and incidents
↓
Triage new alerts (L1) — false positive or true positive?
↓
Escalate confirmed incidents to L2/L3
↓
Investigate and correlate data across sources
↓
Contain and respond to confirmed incidents (CIRT)
↓
Update tickets and document findings
↓
Handover to next shift
---

### Blue Team Responsibilities Summary
✅ Monitor networks and systems 24/7
✅ Analyze and triage security alerts
✅ Hunt for threats proactively (threat hunting)
✅ Maintain and tune detection rules
✅ Respond to and contain confirmed incidents
✅ Conduct forensic investigations
✅ Report security posture to management and CISO
✅ Continuously improve detection and response capabilities
## Humans as Attack Vectors

### Why Humans are the Weakest Link
While technical defenses protect networks, humans are often the
easiest target. Social engineering bypasses firewalls, IDS and
encryption by simply manipulating people into helping the attacker.

**The fortress analogy:**
- Technical attack = breach the walls and gates
- Social engineering = convince the gatekeeper to open the door

---

### What is Social Engineering?
Social engineering exploits human psychology rather than technical
flaws. For it to succeed, attacks are designed to be:

| Characteristic | Description | Example |
|----------------|-------------|---------|
| **Trustworthy** | Attacker appears legitimate so victim trusts them | Spoofed email from IT department |
| **Emotional** | Triggers urgency, fear or curiosity | "Your account will be deleted in 24 hours" |

---

### Common Human-Targeted Attack Types
| Attack Type | Description | Example |
|-------------|-------------|---------|
| **Phishing** | Fraudulent emails designed to steal credentials or deliver malware | Fake Microsoft login page link |
| **Spear Phishing** | Targeted phishing using personal details about the victim | Email appearing to come from victim's manager |
| **Vishing** | Voice phishing — phone calls pretending to be support or authority | Fake IT helpdesk call requesting password |
| **Smishing** | SMS phishing — malicious links sent via text message | Fake bank alert text |
| **Malware Downloads** | Victim tricked into downloading and running malicious files | Fake invoice PDF with embedded macro |
| **Deepfakes** | AI-generated video or audio impersonating trusted people | Fake video call of CEO approving a wire transfer |
| **Impersonation** | Attacker pretends to be IT, management or a vendor | Attacker calling as "IT support" to reset a password |
| **Baiting** | Leaving infected USB drives in accessible locations | USB labeled "Salary 2024" left in company car park |
| **Pretexting** | Creating a fabricated scenario to manipulate the victim | Fake vendor claiming they need system access |
| **Tailgating** | Following an authorized person through a secured entry | Walking behind an employee through a badge-locked door |

---

### Phishing Attack Anatomy
1. Attacker researches the target (OSINT, LinkedIn, company website)
2. Crafts a convincing email with a spoofed sender address
3. Adds urgency or emotional trigger (account suspended, invoice due)
4. Includes malicious link or attachment
5. Victim clicks and either:
a. Enters credentials on a fake login page (credential harvesting)
b. Downloads malware disguised as a legitimate file
6. Attacker uses stolen credentials or malware for further access
---

### Defending Against Human-Targeted Attacks

#### Mitigation — Prevent Attacks
| Control | Description |
|---------|-------------|
| **Security Awareness Training** | Educate employees to recognize phishing and social engineering |
| **Phishing Simulations** | Send fake phishing emails to test and train employees |
| **Email Filtering** | Block known malicious senders, domains and attachments |
| **MFA** | Even if credentials are stolen, MFA blocks unauthorized access |
| **Least Privilege** | Limit damage from compromised accounts by restricting access |
| **Clear IT Policies** | Define what IT will and will never ask employees to do |

#### Detection — Identify Attacks
| Control | Description |
|---------|-------------|
| **SIEM Alerting** | Detect unusual login attempts, locations and behaviors |
| **Email Header Analysis** | Identify spoofed sender addresses and suspicious routing |
| **User Reporting** | Encourage employees to report suspicious emails immediately |
| **EDR Monitoring** | Detect malware execution from downloaded files |
| **Anomaly Detection** | Flag unusual data transfers or access patterns |

---

### Red Flags Employees Should Recognize
🚩 Urgent requests demanding immediate action
🚩 Requests to bypass normal procedures
🚩 Unexpected emails with attachments or links
🚩 Requests for passwords or sensitive information
🚩 Sender email address doesn't match the organization
🚩 Poor grammar or unusual formatting
🚩 Threats of account suspension or legal action
🚩 Too-good-to-be-true offers or rewards
---

### Social Engineering vs Technical Attacks
| | Social Engineering | Technical Attack |
|---|---|---|
| **Target** | Human psychology | System vulnerabilities |
| **Skill required** | Low to medium | High |
| **Success rate** | Very high | Lower |
| **Detection difficulty** | Hard — no malicious code | Easier — security tools detect |
| **Defense** | Training and awareness | Patches and security tools |
| **Example** | Phishing email | SQL injection |
## SOC L1 Alert Triage

### Events vs Alerts
| Concept | Description | Example |
|---------|-------------|---------|
| **Event** | Any observable occurrence in a system or network | User login, file download, DNS query |
| **Alert** | An event that matches a detection rule and triggers a notification | Failed login 10 times in 60 seconds triggers brute force alert |

Not every event becomes an alert — only events matching
detection rules generate alerts for analysts to review.

---

### SOC Team Roles in Alert Triage
| Role | Responsibility |
|------|---------------|
| **L1 Analyst** | Reviews alerts, distinguishes real threats from false positives, escalates confirmed incidents to L2 |
| **L2 Analyst** | Receives escalated alerts from L1, performs deeper analysis and remediation |
| **SOC Engineer** | Ensures alerts contain enough information for efficient triage, tunes detection rules |
| **SOC Manager** | Tracks speed and quality of alert triage, ensures real attacks are not missed |

---

### Alert Properties
. Every alert typically contains:
. Alert name/title — What triggered the detection rule
. Severity — Critical / High / Medium / Low
. Timestamp — When the event occurred
. Source IP — Where the activity came from
. Destination IP — Where the activity was directed
. Affected user/host — Which account or machine was involved
. Raw log data — The underlying evidence
. MITRE ATT&CK mapping — Which tactic/technique was detected
---

### Alert Prioritisation — The 3-Step Approach

#### Step 1 — Filter the Alerts
✅ Only take NEW, unseen and unresolved alerts
✅ Do NOT take alerts already being reviewed by teammates
✅ Check the alert queue before starting to avoid duplicate work
#### Step 2 — Sort by Severity
| Priority | Severity | Why |
|----------|----------|-----|
| 1st | **Critical** | Most likely to be a real major threat with highest impact |
| 2nd | **High** | Serious threat, likely real and impactful |
| 3rd | **Medium** | Moderate threat, investigate after critical and high |
| 4th | **Low** | Least likely to be real, lowest impact |

Detection engineers design rules so that **critical alerts are
far more likely to be genuine major threats** than medium or low.

#### Step 3 — Sort by Time
Start with the OLDEST alerts first, end with the NEWEST

Why: If two breaches are happening simultaneously:

. The older breach attacker is likely already dumping data
. The newer breach attacker has just started reconnaissance

Responding to the older breach first limits the most damage
---

### Alert Triage Decision Flow
New alert received
↓
Is it already being investigated? → YES → Skip, take next alert
↓ NO
What is the severity?
↓
Critical/High → Investigate immediately
Medium/Low → Queue for later
↓
Analyze the alert
↓
False Positive? → Document and close
↓
True Positive? → Escalate to L2, open incident ticket
---

### L1 Triage Checklist
✅ Check alert has not already been claimed by another analyst
✅ Review alert severity and timestamp
✅ Identify affected user, host and IP addresses
✅ Review raw log data and supporting evidence
✅ Check MITRE ATT&CK technique if available
✅ Search for related alerts on the same host or user
✅ Search threat intelligence for known IOCs
✅ Determine: False Positive or True Positive?
✅ If True Positive: escalate to L2 with full notes
✅ If False Positive: document reason and close
✅ Update ticket with all findings
---

### Common Alert Triage Mistakes to Avoid
❌ Taking alerts already claimed by a teammate
❌ Starting with low severity alerts before critical ones
❌ Closing alerts as false positive without investigating
❌ Escalating to L2 without documenting your findings
❌ Ignoring older alerts in favor of newer ones
❌ Not checking for related alerts on the same host/user
❌ Forgetting to update the ticket with your analysis
---

### SIEM and EDR Automation in Triage
Most SOC teams automate prioritization by configuring:
- **Alert severity scoring** — Critical rules trigger first
- **Alert sorting logic** — Automatic queue ordering by severity
- **Deduplication** — Merging duplicate alerts for same event
- **Auto-enrichment** — Automatically adding threat intel context
- **Playbook triggers** — Automatic response actions for known
alert types (ex: auto-block IP on phishing detection)
## EDR (Endpoint Detection and Response)

### What is EDR?
An EDR is a security solution deployed on individual endpoints
(laptops, servers, workstations) that continuously collects
telemetry data to enable security teams to detect, investigate
and respond to threats in real time.

---

### The Three Pillars of EDR
| Pillar | Description |
|--------|-------------|
| **Visibility** | Continuous monitoring of all endpoint activity through telemetry collection |
| **Detection** | Identifies malicious behavior using rules, behavioral analysis and threat intelligence |
| **Response** | Enables containment actions like isolating the endpoint, killing processes or blocking files |

---

### EDR Telemetry — The Endpoint Black Box
Telemetry is everything an EDR collects from an endpoint to
enable detection and investigation:

| Telemetry Type | What it Captures | Why it Matters |
|----------------|-----------------|----------------|
| **Process Executions and Terminations** | All running and terminated processes, parent-child relationships | Identifies suspicious child processes, malware payloads, unusual executables |
| **Network Connections** | All inbound and outbound connections from the endpoint | Detects C2 communication, unusual ports, data exfiltration, lateral movement |
| **Command Line Activity** | All commands executed in CMD, PowerShell, bash | Identifies malicious commands and obfuscated PowerShell scripts missed by AV |
| **File and Folder Modifications** | File creation, modification, deletion and movement | Detects data staging, ransomware file encryption, malicious file dropping |
| **Registry Modifications** | Changes to Windows registry keys and values | Identifies persistence mechanisms, configuration changes during malware execution |

---

### EDR vs Traditional Antivirus
| | Traditional AV | EDR |
|---|---|---|
| **Detection method** | Signature-based only | Behavioral + signature + threat intel |
| **Visibility** | Limited — only scans files | Full endpoint telemetry |
| **Response capability** | Quarantine files only | Isolate host, kill processes, rollback changes |
| **Obfuscated attacks** | Often misses them | Detects via behavioral analysis |
| **PowerShell attacks** | Largely blind | Captures all command line activity |
| **Forensic data** | Minimal | Full timeline of all endpoint activity |
| **Real-time monitoring** | No | Yes — continuous |

---

### What EDR Can Detect That AV Misses
✅ Obfuscated PowerShell script execution
✅ Living off the land attacks (LOLBins) — using legitimate tools
✅ Process injection into legitimate processes
✅ Suspicious parent-child process relationships
✅ C2 beaconing and unusual outbound connections
✅ Fileless malware running only in memory
✅ Registry-based persistence mechanisms
✅ Lateral movement using stolen credentials
✅ Data exfiltration to external IP addresses
---

### Common EDR Solutions
| Tool | Vendor |
|------|--------|
| **CrowdStrike Falcon** | CrowdStrike |
| **SentinelOne** | SentinelOne |
| **Microsoft Defender for Endpoint** | Microsoft |
| **Carbon Black** | VMware |
| **Cortex XDR** | Palo Alto Networks |
| **Elastic EDR** | Elastic |

---

### EDR Alert Investigation Workflow
EDR alert triggered
↓
Review telemetry — process tree, network connections, command line
↓
Identify parent-child process relationship
↓
Check command line arguments for suspicious activity
↓
Review network connections — external IPs, unusual ports
↓
Check file and registry modifications
↓
Search threat intelligence for IOCs
↓
False Positive → Document and close
True Positive → Isolate endpoint, escalate to L2
---

### Key Suspicious Indicators in EDR Telemetry
| Indicator | Why Suspicious |
|-----------|---------------|
| `cmd.exe` or `powershell.exe` spawned by `word.exe` | Office macro executing shell |
| Encoded PowerShell commands (`-EncodedCommand`) | Obfuscation technique |
| `svchost.exe` with unusual parent process | Process injection |
| Outbound connection to non-standard port | C2 communication |
| Mass file renaming with new extensions | Ransomware encryption |
| New registry run key created | Persistence mechanism |
| `whoami`, `net user`, `ipconfig` executed in sequence | Discovery phase |
| Large outbound data transfer at unusual hours | Data exfiltration |
## Splunk — SIEM Fundamentals

### What is Splunk?
Splunk is one of the leading SIEM solutions in the market. It
allows security teams to collect, analyze and correlate network
and machine logs in real time for threat detection, investigation
and incident response.

---

### Splunk Architecture — Three Core Components
| Component | Role | Description |
|-----------|------|-------------|
| **Splunk Forwarder** | Data collection | Lightweight agent installed on endpoints that collects and sends data to Splunk |
| **Splunk Indexer** | Data processing | Receives data from forwarders, parses and normalizes it into field-value pairs, stores as searchable events |
| **Splunk Search Head** | Data analysis | Where analysts search, analyze and visualize indexed log data using SPL |

### Data Flow
Endpoint/Log Source
↓
Splunk Forwarder (collect and send)
↓
Splunk Indexer (parse, normalize, store as events)
↓
Splunk Search Head (search, analyze, visualize)
↓
SOC Analyst (investigate and respond)
---

### SPL — Search Processing Language

#### Basic SPL Syntax
index=* sourcetype=* keyword | command | command
#### Most Useful SPL Commands
| Command | Purpose | Example |
|---------|---------|---------|
| `search` | Filter events by keyword | `search failed login` |
| `index=` | Specify which index to search | `index=windows` |
| `sourcetype=` | Filter by log source type | `sourcetype=WinEventLog` |
| `\|table` | Display specific fields as a table | `\| table _time, src_ip, user` |
| `\|stats` | Calculate statistics | `\| stats count by src_ip` |
| `\|sort` | Sort results | `\| sort -count` |
| `\|head` | Show first N results | `\| head 10` |
| `\|tail` | Show last N results | `\| tail 10` |
| `\|dedup` | Remove duplicate results | `\| dedup src_ip` |
| `\|rename` | Rename a field | `\| rename src_ip as Source` |
| `\|eval` | Create calculated fields | `\| eval status=if(code=200,"OK","Error")` |
| `\|where` | Filter results with conditions | `\| where count > 100` |
| `\|rex` | Extract fields using regex | `\| rex field=_raw "user=(?P<user>\w+)"` |
| `\|timechart` | Create time-based charts | `\| timechart count by EventCode` |
| `\|lookup` | Enrich data with external tables | `\| lookup threat_intel ip as src_ip` |

---

### Common SOC Splunk Searches

**Brute force detection:**
```spl
index=windows sourcetype=WinEventLog EventCode=4625
| stats count by src_ip, user
| where count > 10
| sort -count
```

**Failed logins followed by success:**
```spl
index=windows sourcetype=WinEventLog EventCode=4625 OR EventCode=4624
| stats count by user, EventCode
| sort user
```

**PowerShell execution:**
```spl
index=windows sourcetype=WinEventLog EventCode=4104
| table _time, ComputerName, ScriptBlockText
```

**Unusual outbound connections:**
```spl
index=network sourcetype=firewall action=allowed
| stats count by dest_ip, dest_port
| where count < 5
| sort count
```

**New user created:**
```spl
index=windows sourcetype=WinEventLog EventCode=4720
| table _time, ComputerName, TargetUserName, SubjectUserName
```

---

### Common Windows Event IDs to Know
| Event ID | Description |
|----------|-------------|
| `4624` | Successful login |
| `4625` | Failed login |
| `4634` | Account logoff |
| `4720` | New user account created |
| `4722` | User account enabled |
| `4725` | User account disabled |
| `4728` | User added to security group |
| `4732` | User added to local group |
| `4768` | Kerberos ticket requested |
| `4769` | Kerberos service ticket requested |
| `4776` | NTLM authentication attempted |
| `4104` | PowerShell script block logged |
| `7045` | New service installed |

---

### Splunk Investigation Workflow for SOC Analysts
1. Receive alert from Splunk
2. Open the alert in Search Head
3. Review the triggering event and raw log data
4. Expand the time window to get context around the event
5. Search for related events on the same host/user/IP
6. Use stats and table commands to identify patterns
7. Check threat intelligence for known IOCs
8. Determine: False Positive or True Positive?
9. Document findings in the ticket
10. Escalate to L2 if True Positive
---

### Splunk vs Other SIEM Solutions
| | Splunk | Microsoft Sentinel | QRadar | Elastic SIEM |
|---|---|---|---|---|
| **Type** | Commercial | Cloud-native | Commercial | Open source option |
| **Query language** | SPL | KQL | AQL | EQL/Lucene |
| **Ease of use** | High | High | Medium | Medium |
| **Cost** | High | Pay per use | High | Low/Free |
| **Best for** | Enterprise SOC | Azure environments | IBM environments | Cost-conscious teams |
## SOAR (Security Orchestration, Automation and Response)

### What is SOAR?
SOAR is a platform that unifies all security tools used in a SOC
into a single interface, allowing analysts to operate SIEM, EDR,
firewall, threat intelligence and ticketing systems without
switching between tools. It also automates repetitive tasks
through playbooks.

---

### The Problem SOAR Solves — Manual Tool Switching
**Example: VPN Brute Force Investigation (without SOAR)**
Alert triggered in SIEM
↓
Switch to SIEM → Check if user normally uses that IP
↓
Switch to Threat Intelligence → Check IP reputation
↓
Switch to IAM Tool → Disable user if successful login found
↓
Switch to Ticketing System → Open and track the incident
Each switch wastes time, introduces human error and slows
response. With SOAR, all of this happens in one interface
— or automatically via a playbook.

---

### SOAR Core Capabilities
| Capability | Description |
|------------|-------------|
| **Orchestration** | Connects and integrates all security tools into one unified interface |
| **Automation** | Automates repetitive manual tasks through playbooks |
| **Response** | Executes response actions (block IP, disable user, isolate host) automatically or with one click |
| **Case Management** | Tracks incidents and analyst actions in one place |
| **Reporting** | Generates reports on incident metrics and analyst performance |

---

### SOAR vs SIEM
| | SIEM | SOAR |
|---|---|---|
| **Primary function** | Collect, correlate and alert on logs | Automate and orchestrate the response |
| **Human interaction** | High — analysts manually investigate | Lower — automates repetitive tasks |
| **Tool integration** | Collects logs from tools | Controls and operates tools |
| **Response capability** | None — detection only | Yes — automated response actions |
| **Works with** | Log sources | SIEM, EDR, TI, IAM, firewall, ticketing |

---

### SOAR Playbooks
A playbook is a predefined automated workflow triggered by a
specific alert type. It replaces the manual multi-tool process
with automated actions.

**Example Playbook — VPN Brute Force:**
Trigger: SIEM alert — 10+ failed VPN logins from same IP

Automated Steps:

1. Query SIEM → Check if IP is known for this user
2. Query Threat Intelligence → Check IP reputation score
3. If IP is malicious → Auto-block IP in firewall
4. If successful login detected → Auto-disable user in IAM
5. Create ticket in ticketing system with all findings
6. Notify L2 analyst via email or Slack
7. Request analyst approval for further response actions
**Example Playbook — Phishing Email:**
Trigger: User reports phishing email

Automated Steps:

1. Extract sender, links and attachments from email
2. Query Threat Intelligence for sender domain and links
3. Scan attachments with antivirus
4. If malicious → Delete email from all mailboxes
5. Block sender domain in email gateway
6. Check if any user clicked the link (SIEM query)
7. If clicked → Isolate endpoint via EDR
8. Create incident ticket with full timeline
9. Notify affected users
---

### Tools SOAR Integrates With
| Category | Examples |
|----------|---------|
| **SIEM** | Splunk, Microsoft Sentinel, QRadar |
| **EDR** | CrowdStrike, SentinelOne, Defender |
| **Threat Intelligence** | VirusTotal, MISP, Shodan |
| **Firewall** | Palo Alto, Fortinet, Cisco |
| **IAM** | Active Directory, Okta, Azure AD |
| **Ticketing** | ServiceNow, Jira |
| **Email** | Microsoft 365, Google Workspace |
| **Communication** | Slack, Microsoft Teams |

---

### Popular SOAR Platforms
| Platform | Vendor |
|----------|--------|
| **Splunk SOAR** | Splunk |
| **Palo Alto XSOAR** | Palo Alto Networks |
| **Microsoft Sentinel** | Microsoft (built-in SOAR) |
| **IBM QRadar SOAR** | IBM |
| **Shuffle** | Open source |

---

### Benefits of SOAR for SOC Analysts
✅ No more switching between 5+ tools during investigation
✅ Repetitive tasks automated — analysts focus on complex work
✅ Faster response time (MTTR significantly reduced)
✅ Consistent process — playbooks ensure no steps are missed
✅ Full audit trail of all automated and manual actions
✅ Reduces analyst burnout from alert fatigue
✅ Scales with alert volume without adding headcount
---

### SOAR Investigation Workflow
Alert triggered in SIEM
↓
SOAR automatically enriches alert with context
(threat intel, user info, IP reputation)
↓
Playbook executes automated response steps
↓
Analyst reviews enriched alert in SOAR interface
↓
Analyst approves or modifies automated actions
↓
Final response — contain, eradicate, recover
↓
Case closed and documented in ticketing system
