# Console Commands

## Powershell

- Run android emulator

```ps2

emulator -avd pixel4

Start-Job -ScriptBlock { emulator -avd pixel4 > $null 2>&1 }

Get-Job

Stop-Job <id-of-the-job>
```
