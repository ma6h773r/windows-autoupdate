# Windows AutoUpdate

A PowerShell script that updates everything on a Windows machine in one run: app via Winget, the Windows itself via Windows Update.

## How it works

1. **App updates** - Finds 'winget.exe' and runs 'winget upgrade -all -include-unknown', silently accepting package and source agreements.
2. **Windows Updates** - Uses the PSWindowsUpdate module to scan and install all Windows/Microsoft updates without forcing a reboot.
3. **Reboot check** - If a reboot pending afterward, it prints a warning and pops up a reminder that stays on screen until dismissed by the user.
4. **Logging** - Everything is recorded to 'C:\Scripts\last-update-log.txt' via transcript.

## Requirements
- Run as **Administrator**
- PSWindowsUpdate module: 'Install-Module PSWindowsUpdate -Force'
- Winget (ships with Windows 10/11 via the App Installer)

## Usage
'''powershell
.\AutoUpdate.ps1
