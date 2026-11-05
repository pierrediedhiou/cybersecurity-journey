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
## Malware Classification

### What is Malware?
Malware refers to software or code created to damage systems,
steal information or allow unauthorized access. It appears in
many forms, each with different tactics and goals.

### Impact of Malware on Organizations
• Financial loss (ransom payments, downtime costs)
• Stolen data (intellectual property, customer records)
• Disrupted services (availability loss)
• Reputational damage (loss of customer trust)

---

### Malware Types Reference Table
| Type | Goal | Real-World Indicator | Example Scenario |
|------|------|----------------------|-------------------|
| **Adware** | Generate revenue via ads | Frequent pop-ups, suspicious background process | Browser shows ads even with no sites open |
| **Spyware** | Covert surveillance | Unauthorized access to personal data | Employee's emails accessed by someone else |
| **Ransomware** | Extort payment | Ransom note, encrypted files | Files encrypted after malicious email attachment |
| **Wiper** | Destroy data | Crashed servers, overwritten files | Servers crash, files overwritten with random data |
| **C2 Malware** | Remote control | Connections to unfamiliar domains at odd hours | Endpoint reaching out to unknown C2 domains |
| **Data Stealer** | Exfiltrate data | Sensitive documents leaked online | Files from user directories sent externally |
| **Keylogger** | Steal credentials | Unauthorized financial transfers | Keystrokes recorded on accountant's PC |
| **Cryptominer** | Hijack resources | Slow desktops, high CPU, fans running | High CPU usage linked to mining activity |

---

### Malware Classification by Goal
| Goal Category | Malware Types |
|---------------|---------------|
| **Financial gain** | Ransomware, Cryptominer, Keylogger |
| **Espionage/Surveillance** | Spyware, Keylogger, C2 malware |
| **Data theft** | Data stealer, Spyware, Keylogger |
| **Destruction** | Wiper |
| **Remote access/control** | C2 malware |
| **Advertising/Revenue** | Adware |

---

### Binary vs Script-Based Malware
| | Binary Malware | Script-Based Malware |
|---|---|---|
| **Format** | Compiled executable (.exe, ELF) | Interpreted script (PowerShell, Python, Bash, JS) |
| **Detection** | Signature-based AV, hash matching | Behavioral analysis, content inspection |
| **Analysis tools** | CAPA, IDA Pro, Ghidra, PEStudio | Text editors, CyberChef, sandbox execution |
| **Obfuscation** | Packing, encryption | Base64 encoding, string concatenation |
| **Persistence** | Registry, services, scheduled tasks | Often fileless — lives in memory or scripts |
| **Examples** | Ransomware binaries, trojans | Malicious PowerShell scripts, macro malware |

---

### Malware Classification Workflow
1. Observe the symptom/alert
(pop-ups, encrypted files, high CPU, unusual network traffic)
↓
2. Identify the behavior pattern
(what is it doing — displaying ads, encrypting, mining, stealing)
↓
3. Match behavior to malware type
(use the reference table above)
↓
4. Determine binary vs script-based format
↓
5. Select appropriate analysis tools
(static/dynamic analysis, CAPA, sandbox)
↓
6. Document classification and IOCs
↓
7. Report findings with MITRE ATT&CK mapping

---

### Key Detection Signals by Malware Type
| Malware Type | SOC Detection Signal |
|--------------|----------------------|
| **Adware** | Unusual background processes, browser extension changes |
| **Spyware** | Unexpected outbound connections, keystroke capture APIs |
| **Ransomware** | Mass file renaming/encryption, shadow copy deletion |
| **Wiper** | Mass file deletion/overwrite, MBR modification |
| **C2 Malware** | Beaconing to unknown domains, DNS anomalies (Sysmon 22) |
| **Data Stealer** | Large outbound transfers, access to sensitive directories |
| **Keylogger** | Hooking into keyboard input APIs, hidden processes |
| **Cryptominer** | Sustained high CPU/GPU usage, connections to mining pools |

---

### Malware Classification Checklist
✅ Identify the observable symptom (what changed on the system)
✅ Correlate with network, process and file system artifacts
✅ Classify by primary goal (financial, espionage, destruction, etc)
✅ Determine binary or script-based format
✅ Check for C2 communication (DNS, network connections)
✅ Map behavior to MITRE ATT&CK techniques
✅ Use appropriate analysis tools (static vs dynamic)
✅ Document classification with evidence and IOCs
## Intro to Malware Analysis

### The Two Core Malware Analysis Techniques

| | Static Analysis | Dynamic Analysis |
|---|---|---|
| **Executes the malware?** | No | Yes |
| **Safety** | Safe — malware never runs | Requires isolated sandbox |
| **What it reveals** | Code structure, strings, imports, metadata | Real behavior, network traffic, file changes |
| **Speed** | Fast | Slower — must observe execution |
| **Risk** | Low | Higher — must be fully contained |
| **Tools** | CAPA, PEStudio, strings, oledump, IDA Pro, Ghidra | Process Monitor, Wireshark, Fakenet-NG, sandbox |
| **Best for** | Initial triage, quick classification | Understanding true behavior and capabilities |

---

### The Malware Analyst's Dilemma
Malware faces a fundamental dilemma that analysts exploit:
Malware MUST execute to fulfill its purpose
↓
Execution reveals its true behavior
↓
This is exactly what Dynamic Analysis captures
No matter how well obfuscated or packed malware is statically,
it cannot hide its behavior once it actually runs. This is why
dynamic analysis is so powerful — but also why it requires a
fully isolated and controlled environment (sandbox, REMnux, FlareVM).

---

### Static Analysis Workflow
1. Identify file type and format (PE, ELF, script, document)
2. Calculate file hashes (MD5, SHA256) — check against VirusTotal
3. Extract strings — look for URLs, IPs, file paths, commands
4. Examine PE headers and sections (PEStudio, CFF Explorer)
5. Check imports/exports — what Windows APIs does it call
6. Run CAPA — identify capabilities automatically
7. Check for packing/obfuscation (entropy analysis)
8. Document findings — no execution required

### Dynamic Analysis Workflow
1. Set up isolated sandbox (FlareVM, REMnux, isolated VM snapshot)
2. Start monitoring tools BEFORE execution:
     • Process Monitor (file/registry activity)
     • Wireshark (network traffic)
     • Process Explorer (process tree)
4. Execute the malware sample
5. Observe behavior in real time:
     • What files are created/modified?
     • What registry keys are changed?
     • What network connections are made?
     • What processes are spawned?
5. Capture network traffic with Fakenet-NG (simulate internet)
6. Stop execution and analyze captured data
7. Revert sandbox snapshot (never reuse an infected VM)

---

### PE (Portable Executable) File Structure
PE is the standard executable file format on Windows (.exe, .dll,
.sys, .sys, .ocx). Understanding its structure is essential for
static analysis.

| PE Section | Contains |
|------------|---------|
| **DOS Header** | Legacy MS-DOS compatibility header |
| **PE Header** | File metadata, target architecture |
| **Section Table** | List of sections (.text, .data, .rsrc) |
| **.text** | Executable code |
| **.data** | Initialized global/static variables |
| **.rdata** | Read-only data, often strings |
| **.rsrc** | Resources (icons, dialogs, version info) |
| **Import Table** | External functions the PE depends on (DLLs) |
| **Export Table** | Functions the PE makes available to others |

**Why PE structure matters for analysis:**
✅ Imports reveal capabilities (ex: WinINet.dll = network activity)
✅ Section entropy reveals packing/encryption
✅ Resources section can hide embedded payloads
✅ Compile timestamp can reveal when malware was built
✅ Digital signature (or lack of) indicates legitimacy

---

### Static vs Dynamic — When to Use Which
Use STATIC analysis first when:
✅ You need a quick initial triage
✅ You want to avoid any execution risk
✅ You’re checking against known malware families
✅ You need to extract IOCs quickly (strings, hashes)

Use DYNAMIC analysis when:
✅ Static analysis is inconclusive (heavily obfuscated/packed)
✅ You need to see real network behavior (C2 domains, IPs)
✅ You need to understand the full attack chain
✅ You want to capture dropped files and registry changes

---

### Malware Analysis Safety Rules
✅ Always use an isolated, air-gapped or controlled network
✅ Never analyze malware on your host machine
✅ Always take a VM snapshot before execution
✅ Always revert to snapshot after analysis — never reuse
✅ Use Fakenet-NG or INetSim to simulate internet safely
✅ Disable shared folders and clipboard between host and VM
✅ Never connect analysis VM directly to the internet
