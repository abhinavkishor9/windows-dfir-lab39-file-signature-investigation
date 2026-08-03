# windows-dfir-lab39-file-signature-investigation

## Overview

Windows identifies files using their extensions, but every file also contains a unique header known as a file signature or magic number. During Digital Forensics and Incident Response (DFIR), investigators verify these signatures to determine a file's true type, regardless of its filename or extension.

In this hands-on DFIR lab, native Windows tools and PowerShell were used to create sample files, disguise an executable as a PDF, examine file headers, and compare file extensions with actual file signatures. The investigation demonstrates how analysts can identify suspicious or misleading files using built-in Windows utilities.

---

# Executive Summary

This investigation demonstrates how Windows file signatures can be analyzed without relying on third-party forensic software. By comparing filenames with their internal headers, the investigation successfully identified a disguised executable and validated legitimate file contents.

The workflow mirrors a common DFIR process of validating evidence, detecting extension spoofing, correlating file metadata, and documenting forensic findings.

---

# Investigation Objectives

- Understand Windows file signatures.
- Create sample investigation files.
- Simulate extension spoofing.
- Examine file headers.
- Compare file extensions with actual signatures.
- Detect disguised executable files.
- Correlate forensic evidence.
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
- Windows PowerShell
- Format-Hex
- File Explorer

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | File Signatures |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create investigation workspace.
2. Create sample files.
3. Simulate file extension spoofing.
4. Examine file headers.
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
- PowerShell enumeration
- File metadata
- Header comparison
- Cleanup validation

---

# Evidence Correlation

The investigation correlated multiple Windows artifacts to validate file authenticity:

- File extensions were compared with internal file signatures.
- PowerShell revealed executable headers hidden behind misleading filenames.
- File metadata supported evidence validation.
- Header analysis confirmed the true file type despite extension spoofing.

---

# Investigation Findings

The investigation confirmed that file extensions alone cannot be trusted during forensic analysis. Header inspection successfully identified a disguised executable by revealing the "MZ" file signature, demonstrating why investigators rely on file signatures instead of filenames when validating suspicious files.

---

# Key Takeaway

File signatures provide a reliable method for identifying the true nature of files. During DFIR investigations, verifying file headers helps detect extension spoofing, identify disguised malware, and accurately classify suspicious files using native Windows tools.
