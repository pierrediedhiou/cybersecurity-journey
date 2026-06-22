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

