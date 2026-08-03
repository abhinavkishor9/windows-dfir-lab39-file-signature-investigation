# Investigation Notes

## Lab Summary

In this investigation, we analyzed the file signatures to identify the actual file type behind the file.
We compared the file extension of the file with its actual file signature to validate the authenticity of the file.

---

## Analyst Methodology

1. Create sample investigation workspace.
2. Create sample files in the workspace.
3. Simulate extension spoofing for the files.
4. Verify file extensions.
5. Examine their file headers.
6. Compare legitimate and disguised files by comparing file extension and file signature.
7. Correlate findings.
8. Document evidence.
9. Remove lab artifacts.

---

## Investigation Scenario

A suspicious PDF file was discovered during a forensic investigation.

The investigation aimed to determine:

- Whether the file extension matched the actual file type.
- Whether the file contained a valid PDF signature.
- Whether the file was disguised as PDF.
- Whether the file represented suspicious activity.

---

## Evidence Collected

### Evidence 1 – Investigation Workspace

Collected:

- Investigation directory C:\FileSignatureLab
- Sample files-Invoice.pdf, Payroll.txt

Finding:

We have established an investigation baseline.

---

### Evidence 2 – File Enumeration

Collected:

- Payroll.txt
- Invoice.pdf

Finding:

Verified filenames and extensions which were visible to the analyst.

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

This confirms an executable files-disguised as PDF.

---

### Evidence 4 – Text File Validation

Command Used

```powershell
Format-Hex C:\FileSignatureLab\Payroll.txt
```

Finding:

This displayed normal ASCII text rather than an executable signature.

---

## DFIR Analysis

The investigation showed how Windows file signatures provide a reliable method for checking the authenticity of the file.

The suspicious file appeared to be a PDF, however, its file signature revealed the Windows executable signature "MZ", confirming extension spoofing.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Masquerading | T1036 |
| Discovery | File and Directory Discovery | T1083 |

---

## Analyst Observations

- Never depend on file extensions alone.
- File signatures accurately identify the actual file type.
- PowerShell provides an effective native method for inspecting headers.
- Extension spoofing is a common attacker technique.

---

## Conclusion

The investigation successfully demonstrated how Windows file signatures can be used to identify disguised files. Native PowerShell utilities validated file headers, detected extension spoofing, and provided a structured approach for verifying suspicious files during host-based forensic investigations.
