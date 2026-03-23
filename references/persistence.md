# Persistence Mechanisms
> Source: PersistenceInfo | Entries: 44 | Platform: windows


## Index

- [persistence](#persistence)


### persistence

#### "Run" and "RunOnce" registry keys
Well known key, used by many apps. Any file path specified in a Registry value will be used to `ShellExecute()` the s...
**Categories:** persistence, persistence_type:registry, code_type:exe; other; fileless, launch_type:same logon required, impact:non-destructive, permissions:user, security_context:user

#### .chm helper DLL
The DLL of your choice will be loaded anytime the old-school .chm file is opened. | Locations: HKCU\Software\Microsof...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:user initiated, impact:non-destructive, permissions:user, security_context:user

#### .NET Startup Hooks
You can set the `DOTNET_STARTUP_HOOKS=path/to/assembly.dll` environment variable and then run a .NET app and the runt...
**Categories:** persistence, persistence_type:other, code_type:dll, launch_type:automatic; user initiated, impact:non-destructive, permissions:admin, security_context:user; system

#### AeDebug
Well known key. Add or edit the `Debugger` value, using a REG_SZ string that specifies the command line for the debug...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:other, impact:non-destructive, permissions:admin, security_context:user; system

#### AMSI Providers
AMSI is designed in particular to combat "fileless malware". Application types that can optimally leverage AMSI techn...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:user; system

#### Authentication Packages
Authentication packages are contained in dynamic-link libraries. The Local Security Authority (LSA) loads authenticat...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Autodial DLL
When Winsock library connects to the internet it 'talks' to various service providers and probes them for connectivit...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Boot Verification Program
If there is a `REG_SZ` or `REG_EXPAND_SZ` value named `ImagePath`, it will be used to launch a process by the Service...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### cmd.exe AutoRun
`cmd.exe /?` says:
when CMD.EXE starts, it looks for the following REG_SZ/REG_EXPAND_SZ registry variables, and [...]...
**Categories:** persistence, persistence_type:registry, code_type:exe; other; fileless, launch_type:user initiated, impact:non-destructive, permissions:user, security_context:user

#### Code Signing DLL
Hijack attacks [...] permit persistent code execution in the context of any application that performs code signing or...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:user initiated, impact:non-destructive, permissions:admin, security_context:user

#### Credential Manager DLL
When user logs on, `winlogon.exe` launches the child `mpnotify.exe` process, which in turns loads Credential Manager...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:any logon required, impact:non-destructive, permissions:admin, security_context:system

#### Desired State Configuration
Desired State Configuration (DSC) is a feature in PowerShell 4.0 and above that helps administrators to automate the...
**Categories:** persistence, persistence_type:other, code_type:files ; other ; fileless, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Disk Cleanup Handler
The disk cleanup manager is part of the operating system. It displays the dialog box [...] The user has the option of...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:user initiated, impact:non-destructive, permissions:admin, security_context:user

#### Explorer tools
Looking at the following location: `HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer` we can quickl...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:user initiated, impact:non-destructive, permissions:admin, security_context:user

#### File Extension Hijacking
Replacing the default application for opening txt files can be used as a persistence mechanism.
The stored payload wi...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:user initiated, impact:destructive, permissions:user, security_context:user

#### Filter Handlers for Windows Search
Microsoft Windows Search uses filters to extract the content of items for inclusion in a full-text index. You can ext...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Group Policy Client Side Extension
Group Policy Client Service (`gpsvc`) loads its extension DLLs. The list is easy to be expanded by own DLL creating a...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### hhctrl.ocx
When hh.exe is started it tries to find the hhctrl.ocx library by checking the following Registry value: `HKCR\CLSID\...
**Categories:** persistence, persistence_type:registry, code_type:other, launch_type:user initiated, impact:destructive, permissions:admin, security_context:user

#### HKCU `Load`
Explorer tries to start an application specified as a value of `Load` within `HKCU\Software\Microsoft\Windows NT\Curr...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:same logon required, impact:non-destructive, permissions:user, security_context:user

#### IFilter
Windows Search may be extended to index new, previously unknown file types. It is done through `IFilter` DLLs. 
If so...
**Categories:** persistence, persistence_type:com, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Image File Execution Options
Well known key. If there is a subkey with a name matching the exe file name, the `Debugger` REG_SZ value is being rea...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:automatic; any logon required; user initiated, impact:destructive, permissions:admin, security_context:user; system

#### Keyboard shortcut
It is possible to replace the function of keyboard shortcuts or individual keys.
Each time the key is pressed, the st...
**Categories:** persistence, persistence_type:other, code_type:exe, launch_type:user initiated, impact:destructive, permissions:user, security_context:user

#### LSA Extension
The `REG_MULTI_SZ` value named `Extensions` contains filenames of DLLs being automatically loaded by `lsass.exe`. Eac...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Monitoring Silent Process Exit
*Monitoring Silent Process Exit* mechanism allows executing an application or script (monitor application), when a pr...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:user initiated, impact:none, permissions:admin, security_context:user; system

#### MPNotify
If you put `mpnotify` `REG_SZ` value into the `HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon` registry k...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:any logon required, impact:non-destructive, permissions:admin, security_context:system

#### Natural Language 6 DLLs
C:\WINDOWS\system32\SearchIndexer.exe process looks for the `DLLOverridePath` entries under the following locations (...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### netsh.exe extensions
Netsh.exe can launch different modules. If you add your own module DLL it will be loaded when netsh.exe starts. `DllM...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:user initiated, impact:non-destructive, permissions:admin, security_context:user

#### Password Filter
When a password change request is made, the Local Security Authority (LSA) calls the password filters registered on t...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:user initiated, impact:non-destructive, permissions:admin, security_context:system

#### PowerShell Profile
PowerShell profile - a script, running automatically each time PowerShell is started.  
To start PowerShell without p...
**Categories:** persistence, persistence_type:files only, code_type:other, launch_type:user initiated, impact:non-destructive, permissions:admin; user, security_context:user

#### Print Monitor
Print monitors are responsible for directing a print data stream from the print spooler to an appropriate port driver...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### RDP WDS Startup Programs
Not very widely known. Launches applications (server side) after connecting RDP session. You can specify multiple val...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:any logon required, impact:non-destructive, permissions:admin, security_context:user

#### Recycle Bin COM Extension Handler
Adding the "open\command" subkey to the Recycle Bin CLSID and adding a new verb for the "shell" key will execute the...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:user initiated, impact:destructive, permissions:admin, security_context:user

#### Screen Saver
Well known key. If you provide a link to your .exe (can be renamed for .scr) in the registry, it will be launched as...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:automatic; any logon required; user initiated, impact:non-destructive, permissions:user, security_context:user; system

#### ServerLevelPluginDll
ServerLevelPluginDll: An absolute pathname of a dynamic link library that the DNS server can use to resolve unknown n...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Startup Folder
Well known folder. Any application, lnk file, script etc. is automatically launched by `explorer.exe` after user logo...
**Categories:** persistence, persistence_type:file, code_type:exe; other, launch_type:same logon required, impact:non-destructive, permissions:user, security_context:user

#### Task Scheduler
Scheduled tasks may be used to run custom tasks in many different scenarios. Generally, end-users can create tasks ex...
**Categories:** persistence, persistence_type:other, code_type:exe; dll; fileless; other, launch_type:automatic; other, impact:non-destructive, permissions:user; admin, security_context:user; system

#### TelemetryController
The Windows Compatibility Telemetry system makes use of the CompatTelRunner.exe binary to run a variety of telemetry...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### TS Initial Program
If the `fInheritInitialProgram` value is set to 1, the exe indicated in the `InitialProgram` value is automatically s...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:user initiated, impact:non-destructive, permissions:admin; user, security_context:user

#### User Init Mpr Logon Script
To test the UserInitMprLogonScript setting:
- Save the script on the drive,
- Under `HKCU\Environment` set `UserInitM...
**Categories:** persistence, persistence_type:registry, code_type:exe; other, launch_type:same logon required, impact:non-destructive, permissions:user, security_context:user

#### WER Debugger
When applications hang, the Windows Error Reporting framework allows us to attach a debugger, if it is set up in the...
**Categories:** persistence, persistence_type:registry, code_type:exe, launch_type:other, impact:non-destructive, permissions:admin, security_context:user; system

#### Windows Platform Binary Table
Hardware-based persistence.  
1. During the OS startup, `smss.exe` calls `NtQuerySystemInformation()` function with a...
**Categories:** persistence, persistence_type:other, code_type:exe, launch_type:automatic, impact:non-destructive, permissions:other, security_context:system

#### Windows Services
Windows Services are one of the best known and widely used persistence mechanisms. EXE-based approach is best known,...
**Categories:** persistence, persistence_type:registry, code_type:exe, dll, other, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system

#### Windows Terminal Profile
1. Modify the `settings.json` located in `%localappdata%` and add a custom profile that contains your payload
1. Chan...
**Categories:** persistence, persistence_type:file, code_type:exe, launch_type:user initiated, impact:non-destructive, permissions:user, security_context:user

#### Winlogon Notification Package
Well documented. May be used to launch arbitrary code on different events, and in both - System, and user context.
Wi...
**Categories:** persistence, persistence_type:registry, code_type:dll, launch_type:automatic, impact:non-destructive, permissions:admin, security_context:system; user
