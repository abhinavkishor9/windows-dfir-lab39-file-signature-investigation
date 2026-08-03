# Troubleshooting Notes

## Issue 1

`Format-Hex -Count` returned an error.

### Cause

Windows PowerShell in  VM does not support the `-Count` parameter.

### Resolution

Run:

```powershell
Format-Hex C:\FileSignatureLab\Invoice.pdf
```

---

## Issue 2

 We are Unable to copy Notepad executable.

### Cause

Due to incorrect source path.

### Resolution

First check that the executable exists or not:

```powershell
Test-Path C:\Windows\System32\notepad.exe
```

---

## Issue 3

File header did not display at all.

### Cause

Incorrect file path.

### Resolution

First check the file exists:

```powershell
Get-ChildItem C:\FileSignatureLab
```

---

## Issue 4

Unexpected file signature displayed.

### Cause

You have chosen the wrong file for analysis.

### Resolution

Confirm the filename before running:

```powershell
Format-Hex <filename>
```

---

## Issue 5

Invoice.pdf appeared as a normal PDF.

### Cause

The executable details are hidden behind the renamed extension.

### Resolution

Inspect the file header instead of extension. Extension can be spoofed by the attacker.

---

## Issue 6

Unable to remove investigation folder.

### Cause

File was open.

### Resolution

Close open applications before running:

```powershell
Remove-Item C:\FileSignatureLab -Recurse -Force
```
