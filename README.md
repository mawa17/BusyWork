## Install PowerToys (Windows Store)
### Make a workspace
- Open `PowerToys -> Workspaces` Tick `Create desktop shortcut` and `Move existing windows`
- Find the `Workspace shortcut` on your desktop open with properties & save id as `WorkSpaceID`
### Create key mapping
- Open `PowerToys -> Keyboard Manager` and map keys to run `work.bat`
## Save as Work.bat
```bat
@ECHO OFF
REM === Configruation  ===
SET WorkSpaceID=XXXXX

REM === Hide All Programs  ===
powershell -command "(New-Object -ComObject shell.application).ToggleDesktop()"

REM === Run PowerToys Workspace ===
ECHO Starting workspace...
START "" "%USERPROFILE%\AppData\Local\PowerToys\PowerToys.WorkspacesLauncher.exe" {%WorkSpaceID%} 1

REM === Force close YOUR programs immediately ===
TASKKILL /IM PROGRAM.exe /F >NUL 2>&1
```
