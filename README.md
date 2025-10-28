## Install PowerToys (Windows Store)
- Make a workspace
- Use `keymapper` to map keys to run `work.bat`
## Save as Work.bat
```bat
@ECHO OFF
REM === Configruation  ===
SET WorkSpaceID=XXXXX

REM === Force close YOUR programs immediately ===
TASKKILL /IM PROGRAM.exe /F >NUL 2>&1

REM === Run PowerToys Workspace ===
ECHO Starting workspace...
START "" "C:\Users\%USERPROFILE%\AppData\Local\PowerToys\PowerToys.WorkspacesLauncher.exe" {%WorkSpaceID%} 1
```
