# Troubleshooting Notes

## Issue 1

`Format-Hex -Count` returned an error.

### Cause

Windows PowerShell 5.1 does not support the `-Count` parameter.

### Resolution

Run:

```powershell
Format-Hex C:\FileSignatureLab\Invoice.pdf
```

---

## Issue 2

Unable to copy Notepad executable.

### Cause

Incorrect source path.

### Resolution

Verify the executable exists:

```powershell
Test-Path C:\Windows\System32\notepad.exe
```

---

## Issue 3

File header did not display.

### Cause

Incorrect file path supplied.

### Resolution

Verify the file exists:

```powershell
Get-ChildItem C:\FileSignatureLab
```

---

## Issue 4

Unexpected file signature displayed.

### Cause

Wrong file selected for analysis.

### Resolution

Confirm the filename before running:

```powershell
Format-Hex <filename>
```

---

## Issue 5

Invoice.pdf appeared as a normal PDF.

### Cause

Windows hides executable details behind renamed extensions.

### Resolution

Inspect the file header instead of trusting the extension.

---

## Issue 6

Unable to remove investigation folder.

### Cause

File remained open.

### Resolution

Close all open applications before running:

```powershell
Remove-Item C:\FileSignatureLab -Recurse -Force
```
