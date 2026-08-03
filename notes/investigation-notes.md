# Investigation Notes

## Lab Summary

This investigation focused on analyzing Windows file signatures using native PowerShell tools to determine the true file type behind a filename.

The investigation reconstructed file authenticity by comparing file extensions with internal file signatures (magic numbers) and identifying extension spoofing.

---

## Analyst Methodology

1. Create investigation workspace.
2. Create sample files.
3. Simulate extension spoofing.
4. Verify file extensions.
5. Examine file headers.
6. Compare legitimate and disguised files.
7. Correlate findings.
8. Document evidence.
9. Remove lab artifacts.

---

## Investigation Scenario

A suspicious PDF file was discovered during a forensic investigation.

The investigation aimed to determine:

- Whether the file extension matched the actual file type.
- Whether the file contained a valid PDF signature.
- Whether the file was disguised.
- How PowerShell could validate the file header.
- Whether the file represented suspicious activity.

---

## Evidence Collected

### Evidence 1 – Investigation Workspace

Collected:

- Investigation directory
- Sample files

Finding:

Established investigation baseline.

---

### Evidence 2 – File Enumeration

Collected:

- Payroll.txt
- Invoice.pdf

Finding:

Verified visible filenames and extensions.

---

### Evidence 3 – File Header Analysis

Command Used

```powershell
Format-Hex C:\FileSignatureLab\Invoice.pdf
```

Finding:

Header contained:

```text
4D 5A
```

confirming an executable file.

---

### Evidence 4 – Text File Validation

Command Used

```powershell
Format-Hex C:\FileSignatureLab\Payroll.txt
```

Finding:

Displayed normal ASCII text rather than an executable signature.

---

## DFIR Analysis

The investigation demonstrated how Windows file signatures provide a reliable method for validating file authenticity.

Although the suspicious file appeared to be a PDF, its internal header revealed the Windows executable signature "MZ", confirming extension spoofing.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Masquerading | T1036 |
| Discovery | File and Directory Discovery | T1083 |

---

## Analyst Observations

- File extensions alone should never be trusted.
- File signatures accurately identify the real file type.
- PowerShell provides an effective native method for inspecting headers.
- Extension spoofing is a common attacker technique.
- Correlating filenames with file signatures improves investigation confidence.

---

## Conclusion

The investigation successfully demonstrated how Windows file signatures can be used to identify disguised files. Native PowerShell utilities validated file headers, detected extension spoofing, and provided a structured approach for verifying suspicious files during host-based forensic investigations.
