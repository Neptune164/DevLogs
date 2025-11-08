## Daily Log
### Time
- 2025-11-08

### Problem shooting
#### 1. VS Code Remote mode on the PowerShell
- If change the Evironment Variables in the Windows system, use the command on the SSH remote terminal.
```bash
    $env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine")
```