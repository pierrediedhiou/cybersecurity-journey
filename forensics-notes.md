# Digital Forensics Notes

## What is Digital Forensics?
Digital forensics is the branch of forensics that investigates
cyber crimes by applying structured methods and procedures to
collect, examine, analyze and report on digital evidence.

---

## The 4 Phases of Digital Forensics

| Phase | Description |
|-------|-------------|
| **1. Collection** | Identify and collect devices (computers, laptops, USBs, cameras). Ensure original data is not tampered with. Document all collected items |
| **2. Examination** | Filter the collected data to extract only what's relevant (specific time range, specific user, etc) |
| **3. Analysis** | Correlate data with other evidence to draw conclusions. Extract relevant activities chronologically |
| **4. Reporting** | Prepare a detailed report with methodology, findings and recommendations for law enforcement and executive management, including an executive summary |

### Phase Workflow
Collection → Examination → Analysis → Reporting

(gather)    (filter)    (correlate)  (document)
---

## Types of Digital Forensics

| Type | Focus Area | Example Evidence |
|------|-----------|-------------------|
| **Computer Forensics** | Personal computers, most common type | Files, logs, browsing history |
| **Mobile Forensics** | Mobile devices | Call records, text messages, GPS locations |
| **Network Forensics** | Entire network, not individual devices | Network traffic logs |
| **Database Forensics** | Dedicated databases | Data modification or exfiltration evidence |
| **Cloud Forensics** | Cloud infrastructure | Limited evidence, more challenging |
| **Email Forensics** | Email communications | Phishing and fraud campaign evidence |

---

## Authorization Requirements
- The forensics team must obtain **proper authorization** from
relevant authorities before collecting any data
- Without authorization, evidence may be inadmissible in legal
proceedings

---

## Disk Image vs Memory Image

| | Disk Image | Memory Image |
|---|---|---|
| **Source** | HDD, SSD (storage device) | RAM |
| **Volatility** | Non-volatile — survives restart | Volatile — lost on restart/shutdown |
| **Contains** | Files, media, documents, browsing history | Open files, running processes, network connections |
| **Priority** | Collect second | **Collect FIRST** — data is lost on restart |

### Critical Rule
Always capture the **memory image before the disk image**.
Any restart or shutdown will permanently delete volatile RAM data
including running processes and active network connections.

---

## Forensics Tools

| Tool | Purpose |
|------|---------|
| **FTK Imager** | Creates disk images of Windows systems with a graphical interface. Used for both acquisition and analysis |

---

## Digital Forensics Best Practices Checklist
✅ Obtain proper authorization before collecting any data

✅ Identify all devices at the scene (computers, phones, USBs)

✅ Capture memory image FIRST (before any restart)

✅ Capture disk image second

✅ Document every collected item in detail

✅ Never alter or tamper with original evidence

✅ Filter and extract only relevant data during examination

✅ Correlate evidence chronologically during analysis

✅ Include an executive summary in the final report

✅ Tailor the report to all audiences (law enforcement and management)
## Malware Analysis Tools

### CAPA — Common Analysis Platform for Artifacts

#### What is CAPA?
CAPA is a free open-source tool developed by the FireEye Mandiant
team that automatically identifies the capabilities present in
executable files without needing to run them (static analysis).

---

#### Supported File Types
| File Type | Description |
|-----------|-------------|
| **PE files** | Windows executables (.exe, .dll, .sys) |
| **ELF binaries** | Linux/Unix executables |
| **.NET modules** | Windows .NET assemblies |
| **Shellcode** | Raw machine code payloads |
| **Sandbox reports** | Behavioral analysis output files |

---

#### What CAPA Identifies
CAPA maps identified capabilities to known frameworks:
- **MITRE ATT&CK** — Tactics and techniques used by the malware
- **Malware Behavior Catalog (MBC)** — Specific malware behaviors
- **Capability namespaces** — Grouped by what the malware can do

#### Example Capabilities CAPA Can Detect
. Create or modify registry keys (persistence)
. Download files from the internet (C2 communication)
. Inject code into other processes (evasion)
. Enumerate running processes (discovery)
. Encrypt or decrypt data (defense evasion)
. Establish a reverse shell (command and control)
---

#### CAPA Basic Usage
```bash
# Run CAPA against an executable
capa malware_sample.exe

# Run CAPA with verbose output
capa -v malware_sample.exe

# Run CAPA and output as JSON
capa -j malware_sample.exe > output.json

# Run CAPA against a directory
capa /path/to/samples/
```

---

#### CAPA vs Manual Analysis
| | CAPA | Manual Analysis |
|---|---|---|
| **Speed** | Fast — seconds to minutes | Slow — hours to days |
| **Depth** | High-level capabilities | Deep code-level understanding |
| **Skill required** | Low | High |
| **Best for** | Quick triage and capability mapping | In-depth reverse engineering |

---

#### Why CAPA Matters
✅ Quickly triage suspicious files without running them
✅ Identify malware capabilities in seconds
✅ Maps to MITRE ATT&CK for threat intelligence context
✅ Works on Windows, Linux and .NET executables
✅ Used in DFIR and malware analysis workflows
✅ Saves hours of manual reverse engineering time
## REMnux — Malware Analysis Distribution

### What is REMnux?
REMnux is a specialized free Linux distribution built for reverse
engineering and malware analysis. It provides a ready-to-use
sandbox-like environment for safely dissecting potentially malicious
software without risking your primary system.

---

### Why Use REMnux?
✅ Pre-installed with all major malware analysis tools
✅ Sandbox-like environment — safe to run suspicious files
✅ No manual tool installation needed
✅ Isolates malware from your primary system
✅ Used by professional DFIR analysts and malware researchers
✅ Free and open source
---

### Pre-Installed Tools in REMnux
| Tool | Purpose |
|------|---------|
| **Volatility** | Memory forensics — analyzes RAM dumps to extract running processes, network connections and loaded modules |
| **YARA** | Malware identification and classification using pattern-matching rules |
| **Wireshark** | Network traffic analysis and packet capture inspection |
| **oledump** | Analyzes OLE files (Word, Excel) for malicious macros and embedded objects |
| **INetSim** | Simulates internet services (HTTP, DNS, SMTP) to capture malware network behavior |
| **CAPA** | Identifies capabilities present in executable files |

---

### REMnux vs Regular Kali Linux
| | REMnux | Kali Linux |
|---|---|---|
| **Primary purpose** | Malware analysis and reverse engineering | Penetration testing |
| **Pre-installed tools** | DFIR and malware analysis tools | Offensive security tools |
| **Best for** | Blue team, DFIR, SOC analysts | Red team, pentesters |
| **Sandbox capability** | Yes — designed for it | No |

---

### REMnux Common Workflow
1. Receive suspicious file (email attachment, downloaded sample)
2. Transfer to REMnux VM (isolated environment)
3. Static analysis — CAPA, YARA, oledump (no execution)
4. Dynamic analysis — run in INetSim environment, capture network
5. Memory analysis — Volatility if memory dump available
6. Wireshark — review captured network traffic
7. Document findings and IOCs
---

### IOCs to Extract During Malware Analysis
. IP addresses and domains contacted
. File hashes (MD5, SHA256)
. Registry keys created or modified
. Files dropped on the system
. Mutex names
. Encoded strings and C2 URLs
