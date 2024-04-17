# Windows: Prevent OneDrive from installing for new users

## Manual method

<b>Loading default user registry:</b>

```powershell
reg load HKLM\image C:\Users\Default\NTUSER.DAT
```

<b>OneDrive installation registry:</b>

* Path: HKEY_LOCAL_MACHINE\image\Software\Microsoft\Windows\CurrentVersion\Run
* Value name: OneDriveSetup

<b>Unloading default user registry:</b>

```powershell
reg unload HKLM\image
```

## Automatic method

<b>Remove RunOnce entry with ActiveSetup:</b>

```powershell
ni "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\DisableOneDrive" | New-ItemProperty -Name "StubPath" -Value 'REG DELETE "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v OneDriveSetup /f'
```

## Related videos

<b>Windows Registry</b>

[Windows Registry: Run and RunOnce](https://youtu.be/zgFzCq5uEPw) <br />
[Windows Registry: Active Setup](https://youtu.be/HrVJ7wdvfmo)

<b>Other powershell videos</b>

[PowerShell playlist](https://www.youtube.com/playlist?list=PLVncjTDMNQ4RDyVzbV0_kpXCScTMgUw_A)