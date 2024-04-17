# Windows: Prevent OneDrive from installing for new users

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