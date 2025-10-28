## Install PowerToys (Windows Store)
### Make a workspace
- Open `PowerToys -> Workspaces` Tick `Create desktop shortcut` and `Move existing windows`
- Find the `Workspace shortcut` on your desktop open with properties & save id as `WorkSpaceID` in `work.bat`
### Create key mapping
- Open `PowerToys -> Keyboard Manager` and map keys to run `work.bat`
## Save as Work.bat
```bat
@ECHO OFF
REM === Configuration ===
SET "WorkSpaceID=xxxxx"
SET "Programs=program1.exe program2.exe"

REM === Hide All Programs ===
POWERSHELL -command "(New-Object -ComObject shell.application).ToggleDesktop()"

REM === Run PowerToys Workspace ===
START "" "%USERPROFILE%\AppData\Local\PowerToys\PowerToys.WorkspacesLauncher.exe" {%WorkSpaceID%} 1

REM === Force kill programs ===
for %%p in (%Programs%) do (
    TASKKILL /im "%%p" /f >NUL 2>&1
)
```
