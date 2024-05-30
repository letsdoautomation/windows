# Windows: Creating Windows 11 installation USB and downloading ISO

<b>Downloads:</b>

* [Media Creation Tool and Windows ISO](https://www.microsoft.com/software-download/windows11)

<b>Documentation:</b>

* [Specify VMware Tools Components in Silent Installation](https://docs.vmware.com/en/VMware-Tools/12.4.0/com.vmware.vsphere.vmwaretools.doc/GUID-E45C572D-6448-410F-BFA2-F729F2CDA8AC.html)

<b>Objectives:</b>

* Create Windows 11 installation USB
    * Add autounattend.xml to USB to automate steps in pre-installation enviroment.
    * Create provisioning package
        * Skip OOBE
        * Install VMware tools
        * Execute oobe-setup.ps1
            * Create local admin user
            * Skip privacy experience
            * Configure power settings
* Download Windows 11 ISO

<b>Execute oobe-setup.ps1</b>

```powershell
powershell.exe -ExecutionPolicy Bypass -File oobe-setup.ps1
```

<b>Execute silent VMware tools installtion:</b>

```powershell
cmd /c copy setup64.exe %TEMP% && cmd /c %TEMP%\setup64.exe /S /v "/qn REBOOT=R"
```

<b>ReturnCodeSuccess:</b>3010

### Related videos:

<b>Windows Configuration Designer</b>

* [Windows Configuration Designer: Downloading and installing](https://youtu.be/cSa12YaNMbU)