# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 09:00 | Created investigation workspace | PowerShell |
| 09:05 | Created sample text file | Payroll.txt |
| 09:10 | Copied executable and renamed to Invoice.pdf | PowerShell |
| 09:15 | Verified file extensions | Get-ChildItem |
| 09:20 | Examined executable header | Format-Hex |
| 09:25 | Examined text file header | Format-Hex |
| 09:30 | Compared file signatures | Documentation |
| 09:35 | Correlated evidence | Investigation Notes |
| 09:40 | Removed lab artifacts | Remove-Item |

---

# Investigation Flow

Investigation Started

↓

Created Investigation Workspace

↓

Created Sample Files

↓

Simulated Extension Spoofing

↓

Verified File Extensions

↓

Examined File Headers

↓

Compared Signatures

↓

Correlated Evidence

↓

Documented Findings

↓

Removed Lab Artifacts

↓

Investigation Completed

---

# Summary

The investigation reconstructed Windows file authenticity by examining internal file signatures rather than relying on visible file extensions. Using native PowerShell tools, the lab successfully identified a disguised executable through its "MZ" header, demonstrated the risks of extension spoofing, and reinforced the importance of file signature validation during host-based DFIR investigations.
