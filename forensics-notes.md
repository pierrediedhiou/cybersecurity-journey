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
## FlareVM — Windows Malware Analysis Environment

### What is FlareVM?
**FLARE** stands for **Forensics, Logic Analysis and Reverse
Engineering**. FlareVM is a free Windows-based virtual machine
developed by FireEye Mandiant, containing a comprehensive and
curated collection of tools specifically designed for:
- Reverse engineers
- Malware analysts
- Incident responders
- Forensic investigators
- Penetration testers

---

### FlareVM vs REMnux
| | FlareVM | REMnux |
|---|---|---|
| **OS** | Windows | Linux |
| **Primary focus** | Reverse engineering and malware analysis | Malware analysis and network simulation |
| **Best for** | Analyzing Windows malware (.exe, .dll) | Analyzing Linux malware, network behavior |
| **Developed by** | FireEye Mandiant | SANS Institute |
| **Sandbox** | Yes | Yes |
| **Used by** | Malware analysts, DFIR, pentesters | DFIR, SOC analysts, malware researchers |

---

### FlareVM Tool Categories
| Category | Description | Example Tools |
|----------|-------------|---------------|
| **Disassemblers and Decompilers** | Convert compiled binaries back to readable code | IDA Pro, Ghidra, Binary Ninja |
| **Debuggers** | Step through code execution line by line | x64dbg, WinDbg, OllyDbg |
| **Static Analysis** | Analyze files without executing them | PEStudio, CFF Explorer, strings |
| **Dynamic Analysis** | Analyze files during execution | Process Monitor, Process Hacker |
| **Forensics and Incident Response** | Collect and analyze forensic evidence | Volatility, Autopsy, FTK |
| **Network Analysis** | Capture and inspect network traffic | Wireshark, Fakenet-NG |
| **File Analysis** | Inspect file structure and contents | HxD (hex editor), 7-Zip |
| **Scripting and Automation** | Automate repetitive analysis tasks | Python, PowerShell, YARA |
| **Sysinternals Suite** | Advanced Windows monitoring and diagnostics | Process Explorer, Autoruns, TCPView |

---

### Static vs Dynamic Analysis Comparison
| | Static Analysis | Dynamic Analysis |
|---|---|---|
| **Executes the file** | No | Yes |
| **Safety** | Safe — malware never runs | Requires isolated environment |
| **What it reveals** | Code structure, strings, imports, file type | Real behavior, network connections, file changes |
| **Speed** | Fast | Slower |
| **Tools** | CAPA, PEStudio, strings, oledump | Process Monitor, Wireshark, Fakenet-NG |
| **Best for** | First-pass triage | Behavioral analysis |

---

### Reverse Engineering Process
1. Static triage — file type, hashes, strings, imports (CAPA, PEStudio)
2. Disassemble — convert binary to assembly (Ghidra, IDA Pro)
3. Decompile — recover high-level code where possible
4. Dynamic analysis — run in sandbox, observe behavior
5. Debug — step through suspicious code sections (x64dbg)
6. Document — record capabilities, IOCs and MITRE ATT&CK mappings
---

### Key Sysinternals Tools
| Tool | Purpose |
|------|---------|
| **Process Explorer** | Advanced task manager showing process trees and parent-child relationships |
| **Process Monitor** | Real-time monitoring of file system, registry and process activity |
| **Autoruns** | Shows all programs configured to run at startup |
| **TCPView** | Real-time view of all TCP and UDP connections |
| **Strings** | Extracts readable text strings from binary files |

---

### FlareVM Workflow for Malware Analysis
1. Transfer suspicious file to FlareVM (isolated VM snapshot)
2. Static analysis — PEStudio, CAPA, strings (no execution)
3. Check file hash against VirusTotal
4. Disassemble with Ghidra or IDA Pro
5. Dynamic analysis — run with Process Monitor and Wireshark active
6. Network capture — review with Wireshark or Fakenet-NG
7. Debug suspicious code sections with x64dbg
8. Extract IOCs (IPs, domains, file paths, registry keys)
9. Map findings to MITRE ATT&CK
10. Write analysis report
