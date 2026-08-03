# windows-dfir-lab39-file-signature-investigation
## Overview

In Windows, files are identified through their extensions. However, every file also contains a unique header which we call as File Signature or Magic Number. In this Digital Signature and Digital Forensics Lab, we identify the file using their file signature to identify a disguised executable. 

---

# Executive Summary

This investigation demonstrates how file signatures are analyzed without using third-party tools. In this investigation, we used native PowerShell tools to create sample files, disguise a PDF, and compare the file extensions with actual file signatures.

---

# Investigation Objectives

- Understand Windows file signatures.
- Create sample files.
- Simulate extension spoofing.
- Examine sample file headers.
- Compare the file extensions with actual signatures of the files.
- Detect disguised executable files by identifying their actual signatures.
- Correlate forensic evidence from this.
- Document investigation findings.

---

# Skills Demonstrated

- Windows File Signature Analysis
- Windows DFIR Methodology
- Host-Based Forensic Investigation
- PowerShell File Analysis
- Magic Number Identification
- Extension Spoofing Detection
- Evidence Correlation
- Investigation Documentation
- Incident Reporting

---

# Tools Used

- Windows 10
- PowerShell
- Format-Hex in PowerShell
- File Explorer

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 x64|
| VM | VMWare Workstation 25 Player |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | File Signatures |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create a workspace for investigation.
2. Create sample files.
3. Simulate file extension spoofing for these files.
4. Examine  their file headers.
5. Compare extensions and signatures.
6. Validate suspicious files.
7. Correlate evidence.
8. Remove lab artifacts.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1036 | Masquerading |
| T1083 | File and Directory Discovery |
| T1005 | Data from Local System |

---

# Evidence Collected

- Sample text file
- Disguised executable
- Format-Hex output
- File metadata
- Header comparison
- Cleanup validation

---

# Evidence Correlation

This DFIR investigation correlated multiple Windows artifacts to check the authenticity of the files:

- File extensions were compared with internal file signatures.
- PowerShell revealed executable headers hidden behind misleading filenames. What looked like txt or pdf contained executable headers.
- File metadata supported evidence validation.
- Header analysis confirmed the actual file type.

---

# Investigation Findings

The investigation confirmed that you cannot trust only file extensions during DFIR analysis. Header inspection successfully identified a disguised executable by revealing the "MZ" file signature for it. This shows that in DFIR analysis, we depend on file signatures instead of file extensions, as file extensions can bs spoofed by attackers to mislead analysts.

---

