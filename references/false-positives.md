# False Positive Triage
> Source: LoFP | Entries: 671 | Platform: network, windows


## Index

- [false_positive](#falsepositive)


### false_positive

#### A New Trust Was Created To A Domain
Addition of domains is seldom and should be verified for legitimacy. (Level: medium, Status: stable)
**Categories:** false_positive, T1098, sigma

#### Access LSASS Memory for Dump Creation
The following analytic detects attempts to dump the LSASS process memory, a common technique in credential dumping at...
**Categories:** false_positive, T1003.001, splunk

#### Access To ADMIN$ Network Share
Detects access to ADMIN$ network share (Level: low, Status: test)
**Categories:** false_positive, T1021.002, sigma

#### Access To Crypto Currency Wallets By Uncommon Applications
Detects file access requests to crypto currency files by uncommon processes.
Could indicate potential attempt of cryp...
**Categories:** false_positive, T1003, sigma

#### Account Tampering - Suspicious Failed Logon Reasons
This method uses uncommon error codes on failed logons to determine suspicious activity and tampering with accounts t...
**Categories:** false_positive, T1078, sigma

#### Active Directory Lateral Movement Identified
The following analytic identifies potential lateral movement activities within an organization's Active Directory (AD...
**Categories:** false_positive, T1210, splunk

#### Active Directory Privilege Escalation Identified
The following analytic identifies potential privilege escalation activities within an organization's Active Directory...
**Categories:** false_positive, T1484, splunk

#### Active Setup Registry Autostart
The following analytic detects suspicious modifications to the Active Setup registry for persistence and privilege es...
**Categories:** false_positive, T1547.014, splunk

#### AD Privileged Users or Groups Reconnaissance
Detect priv users or groups recon based on 4661 eventid and known privileged users or groups SIDs (Level: high, Statu...
**Categories:** false_positive, T1087.002, sigma

#### ADCS Certificate Template Configuration Vulnerability
Detects certificate creation with template allowing risk permission subject (Level: low, Status: test)
**Categories:** false_positive, sigma

#### ADCS Certificate Template Configuration Vulnerability with Risky EKU
Detects certificate creation with template allowing risk permission subject and risky EKU (Level: high, Status: test)
**Categories:** false_positive, sigma

#### Add or Set Windows Defender Exclusion
The following analytic detects the use of commands to add or set exclusions
in Windows Defender. It leverages data fr...
**Categories:** false_positive, T1562.001, splunk

#### Addition of SID History to Active Directory Object
An attacker can use the SID history attribute to gain additional privileges. (Level: medium, Status: stable)
**Categories:** false_positive, T1134.005, sigma

#### Admin User Remote Logon
Detect remote login by Administrator user (depending on internal pattern). (Level: low, Status: test)
**Categories:** false_positive, T1078.001, T1078.002, T1078.003, sigma

#### ADS Zone.Identifier Deleted By Uncommon Application
Detects the deletion of the "Zone.Identifier" ADS by an uncommon process. Attackers can leverage this in order to byp...
**Categories:** false_positive, T1070.004, sigma

#### ADSI-Cache File Creation By Uncommon Tool
Detects the creation of an "Active Directory Schema Cache File" (.sch) file by an uncommon tool. (Level: medium, Stat...
**Categories:** false_positive, T1001.003, sigma

#### AdsiSearcher Account Discovery
The following analytic detects the use of the `[Adsisearcher]` type accelerator in PowerShell to query Active Directo...
**Categories:** false_positive, T1087.002, splunk

#### Advanced IP or Port Scanner Execution
The following analytic detects the execution of network scanning utilities such as Advanced IP Scanner or Advanced Po...
**Categories:** false_positive, T1046, T1135, splunk

#### Advanced IP Scanner - File Event
Detects the use of Advanced IP Scanner. Seems to be a popular tool for ransomware groups. (Level: medium, Status: test)
**Categories:** false_positive, T1046, sigma

#### Allow File And Printing Sharing In Firewall
The following analytic detects the modification of firewall settings to allow file and printer sharing. It leverages...
**Categories:** false_positive, T1562.007, splunk

#### Allow Inbound Traffic By Firewall Rule Registry
The following analytic detects suspicious modifications to firewall rule registry settings that allow inbound traffic...
**Categories:** false_positive, T1021.001, splunk

#### Allow Inbound Traffic In Firewall Rule
The following analytic detects a suspicious PowerShell command that allows inbound traffic to a specific local port w...
**Categories:** false_positive, T1021.001, splunk

#### Allow Network Discovery In Firewall
The following analytic detects a suspicious modification to the firewall to allow network discovery on a machine. It...
**Categories:** false_positive, T1562.007, splunk

#### Anomalous usage of 7zip
The following analytic detects the execution of 7z.exe, a 7-Zip utility, spawned from rundll32.exe or dllhost.exe. Th...
**Categories:** false_positive, T1560.001, splunk

#### Anydesk Remote Access Software Service Installation
Detects the installation of the anydesk software service. Which could be an indication of anydesk abuse if you the so...
**Categories:** false_positive, sigma

#### Anydesk Temporary Artefact
An adversary may use legitimate desktop support and remote access software, such as Team Viewer, Go2Assist, LogMein,...
**Categories:** false_positive, T1219.002, sigma

#### AppLocker Prevented Application or Script from Running
Detects when AppLocker prevents the execution of an Application, DLL, Script, MSI, or Packaged-App from running. (Lev...
**Categories:** false_positive, T1204.002, T1059.001, T1059.003, T1059.005, T1059.006, T1059.007, sigma

#### AppX Package Deployment Failed Due to Signing Requirements
Detects an appx package deployment / installation with the error code "0x80073cff" which indicates that the package d...
**Categories:** false_positive, sigma

#### Assembly DLL Creation Via AspNetCompiler
Detects the creation of new DLL assembly files by "aspnet_compiler.exe", which could be a sign of "aspnet_compiler" a...
**Categories:** false_positive, sigma

#### Atera Agent Installation
Detects successful installation of Atera Remote Monitoring & Management (RMM) agent as recently found to be used by C...
**Categories:** false_positive, T1219.002, sigma

#### Attacker Tools On Endpoint
The following analytic detects the execution of tools commonly exploited by cybercriminals, such as those used for un...
**Categories:** false_positive, T1003, T1036.005, T1595, splunk

#### Attempt To Add Certificate To Untrusted Store
The following analytic detects attempts to add a certificate to the untrusted
certificate store using the 'certutil -...
**Categories:** false_positive, T1553.004, splunk

#### Backup Files Deleted
Detects deletion of files with extensions often used for backup files. Adversaries may delete or remove built-in oper...
**Categories:** false_positive, T1490, sigma

#### Batch File Write to System32
The following analytic detects the creation of a batch file (.bat) within the Windows system directory tree, specific...
**Categories:** false_positive, T1204.002, splunk

#### BCDEdit Failure Recovery Modification
The following analytic detects modifications to the Windows error recovery boot configurations using bcdedit.exe with...
**Categories:** false_positive, T1490, splunk

#### BITS Job Persistence
The following analytic detects the use of `bitsadmin.exe` to schedule a BITS job for persistence on an endpoint. It l...
**Categories:** false_positive, T1197, splunk

#### BITS Transfer Job Downloading File Potential Suspicious Extension
Detects new BITS transfer job saving local files with potential suspicious extensions (Level: medium, Status: test)
**Categories:** false_positive, T1197, sigma

#### BITS Transfer Job With Uncommon Or Suspicious Remote TLD
Detects a suspicious download using the BITS client from a FQDN that is unusual. Adversaries may abuse BITS jobs to p...
**Categories:** false_positive, T1197, sigma

#### BITSAdmin Download File
The following analytic detects the use of `bitsadmin.exe` with the `transfer` parameter to download a remote object....
**Categories:** false_positive, T1197, T1105, splunk

#### BloodHound Collection Files
Detects default file names outputted by the BloodHound collection tool SharpHound (Level: high, Status: test)
**Categories:** false_positive, T1087.001, T1087.002, T1482, T1069.001, T1069.002, T1059.001, sigma

#### Certificate Exported From Local Certificate Store
Detects when an application exports a certificate (and potentially the private key as well) from the local Windows ce...
**Categories:** false_positive, T1649, sigma

#### Certificate Private Key Acquired
Detects when an application acquires a certificate private key (Level: medium, Status: test)
**Categories:** false_positive, T1649, sigma

#### Certificate Use With No Strong Mapping
Detects a user certificate that was valid but could not be mapped to a user in a strong way (such as via explicit map...
**Categories:** false_positive, sigma

#### Certutil exe certificate extraction
The following analytic identifies the use of certutil.exe with arguments indicating the manipulation or extraction of...
**Categories:** false_positive, splunk

#### CertUtil With Decode Argument
The following analytic detects the use of CertUtil.exe with the 'decode' argument, which may indicate an attempt to d...
**Categories:** false_positive, T1140, splunk

#### CHCP Command Execution
The following analytic detects the execution of the chcp.com utility, which is used to change the active code page of...
**Categories:** false_positive, T1059, splunk

#### Check Elevated CMD using whoami
The following analytic identifies the execution of the "whoami" command with the "/group" flag, where the results are...
**Categories:** false_positive, T1033, splunk

#### Child Processes of Spoolsv exe
The following analytic identifies child processes spawned by spoolsv.exe, the Print Spooler service in Windows, which...
**Categories:** false_positive, T1068, splunk

#### Cisco Isovalent - Access To Cloud Metadata Service
The following analytic detects workloads accessing the cloud instance metadata service at 169.254.169.254. This IP is...
**Categories:** false_positive, T1552.005, splunk

#### Cisco Isovalent - Cron Job Creation
The following analytic detects the creation of a cron job within the Cisco Isovalent environment. It identifies this...
**Categories:** false_positive, T1053.003, T1053.007, splunk

#### Cisco Isovalent - Curl Execution With Insecure Flags
The following analytic detects the execution of curl commands with insecure flags within the Cisco Isovalent environm...
**Categories:** false_positive, T1105, splunk

#### Cisco Isovalent - Kprobe Spike
This analytic detects excessive kernel probe (kprobe) events in a Kubernetes cluster over a short period of time.
Kpr...
**Categories:** false_positive, T1068, splunk

#### Cisco Isovalent - Late Process Execution
Detects process executions that occur well after a container has initialized, which can indicate
suspicious activity...
**Categories:** false_positive, T1543, splunk

#### Cisco Isovalent - Non Allowlisted Image Use
The following analytic detects use of container images that fall outside an approved
allowlist, leveraging Cisco Isov...
**Categories:** false_positive, T1204.003, splunk

#### Cisco Isovalent - Nsenter Usage in Kubernetes Pod
This analytic detects the execution of the nsenter utility from within a container, a technique often used for exploi...
**Categories:** false_positive, T1543, splunk

#### Cisco Isovalent - Pods Running Offensive Tools
The following analytic detects execution of known offensive tooling from within Kubernetes pods, including network sc...
**Categories:** false_positive, T1204.003, splunk

#### Cisco Isovalent - Potential Escape to Host
This analytic detects potential container escape or reconnaissance attempts by monitoring for the rapid execution of...
**Categories:** false_positive, T1611, splunk

#### Cisco Isovalent - Shell Execution
The following analytic detects the execution of a shell inside a container namespace within the Cisco Isovalent envir...
**Categories:** false_positive, T1543, splunk

#### Cisco NVM - Curl Execution With Insecure Flags
This analytic detects the use of `curl.exe` with insecure flags such as `-k`, `--insecure`, `--proxy-insecure`, or `-...
**Categories:** false_positive, T1197, splunk

#### Cisco NVM - Installation of Typosquatted Python Package
This analytic detects suspicious python package installations where the package name resembles popular Python librari...
**Categories:** false_positive, T1059, splunk

#### Cisco NVM - MSHTML or MSHTA Network Execution Without URL in CLI
This analytic detects suspicious use of 'mshta.exe' or 'rundll32.exe' invoking 'mshtml.dll'
or the 'RunHTMLApplicatio...
**Categories:** false_positive, T1218.005, T1059.005, splunk

#### Cisco NVM - Non-Network Binary Making Network Connection
This analytic detects network connections initiated by binaries that are not typically associated with network commun...
**Categories:** false_positive, T1055, T1036, splunk

#### Cisco NVM - Outbound Connection to Suspicious Port
The following analytic detects any outbound network connection from an endpoint process to a known suspicious or non-...
**Categories:** false_positive, T1571, splunk

#### Cisco NVM - Rclone Execution With Network Activity
This detection identifies execution of the file synchronization utility "rclone".
It leverages Cisco Network Visibili...
**Categories:** false_positive, T1567.002, splunk

#### Cisco NVM - Rundll32 Abuse of MSHTML.DLL for Payload Download
This analytic detects suspicious use of `rundll32.exe` in combination with `mshtml.dll` and the export `RunHTMLApplic...
**Categories:** false_positive, T1218.005, splunk

#### Cisco NVM - Susp Script From Archive Triggering Network Activity
This analytic detects script execution (`wscript.exe` or `cscript.exe`) triggered from compressed files opened direct...
**Categories:** false_positive, T1059.005, T1204.002, splunk

#### Cisco NVM - Suspicious Download From File Sharing Website
This analytic detects suspicious downloads from common file sharing and content delivery platforms using known living...
**Categories:** false_positive, T1197, splunk

#### Cisco NVM - Suspicious File Download via Headless Browser
This analytic identifies the use of Chromium-based browsers (like Microsoft Edge) running in headless mode with the `...
**Categories:** false_positive, T1105, T1059, splunk

#### Cisco NVM - Suspicious Network Connection From Process With No Args
This analytic detects system binaries that are commonly abused in process injection techniques but are observed witho...
**Categories:** false_positive, T1055, T1218, splunk

#### Cisco NVM - Suspicious Network Connection Initiated via MsXsl
This analytic identifies the use of `msxsl.exe` initiating a network connection to a non-private IP address.
Although...
**Categories:** false_positive, T1220, splunk

#### Cisco NVM - Suspicious Network Connection to IP Lookup Service API
This analytic identifies non-browser processes reaching out to public IP lookup or geolocation services,
such as `ipi...
**Categories:** false_positive, T1590.005, T1016, splunk

#### Cisco NVM - Webserver Download From File Sharing Website
This analytic detects unexpected outbound network connections initiated by known webserver processes such as `httpd.e...
**Categories:** false_positive, T1105, T1190, splunk

#### Clear Unallocated Sector Using Cipher App
The following analytic detects the execution of `cipher.exe` with the `/w` flag to clear unallocated sectors on a dis...
**Categories:** false_positive, T1070.004, splunk

#### Clop Common Exec Parameter
The following analytic identifies the execution of CLOP ransomware variants using specific arguments ("runrun" or "te...
**Categories:** false_positive, T1204, splunk

#### Cloudflared Tunnels Related DNS Requests
Detects DNS requests to Cloudflared tunnels domains.
Attackers can abuse that feature to establish a reverse shell or...
**Categories:** false_positive, T1071.001, T1572, sigma

#### CMD Carry Out String Command Parameter
The following analytic detects the use of `cmd.exe /c` to execute commands, a technique often employed by adversaries...
**Categories:** false_positive, T1059.003, splunk

#### CMLUA Or CMSTPLUA UAC Bypass
The following analytic detects the use of COM objects like CMLUA or CMSTPLUA to bypass User Account Control (UAC). It...
**Categories:** false_positive, T1218.003, splunk

#### CodeIntegrity - Unmet Signing Level Requirements By File Under Validation
Detects attempted file load events that did not meet the signing level requirements. It often means the file's signat...
**Categories:** false_positive, sigma

#### Common Ransomware Extensions
The following analytic detects modifications to files with extensions commonly associated with ransomware. It leverag...
**Categories:** false_positive, T1485, splunk

#### Common Ransomware Notes
The following analytic detects the creation of files with names commonly associated with ransomware notes.
It leverag...
**Categories:** false_positive, T1485, splunk

#### ConnectWise ScreenConnect Path Traversal Windows SACL
The following analytic detects attempts to exploit the ConnectWise ScreenConnect CVE-2024-1708 vulnerability using Wi...
**Categories:** false_positive, T1190, splunk

#### Conti Common Exec parameter
The following analytic detects the execution of suspicious command-line arguments commonly associated with Conti rans...
**Categories:** false_positive, T1204, splunk

#### Control Loading from World Writable Directory
The following analytic identifies instances of control.exe loading a .cpl or .inf file from a writable directory, whi...
**Categories:** false_positive, T1218.002, splunk

#### Create or delete windows shares using net exe
The following analytic detects the creation or deletion of Windows shares using the net.exe command. It leverages End...
**Categories:** false_positive, T1070.005, splunk

#### Create Remote Thread into LSASS
The following analytic detects the creation of a remote thread in the Local Security Authority Subsystem Service (LSA...
**Categories:** false_positive, T1003.001, splunk

#### Creation Of a Suspicious ADS File Outside a Browser Download
Detects the creation of a suspicious ADS (Alternate Data Stream) file by software other than browsers (Level: medium,...
**Categories:** false_positive, sigma

#### Creation of lsass Dump with Taskmgr
The following analytic detects the creation of an lsass.exe process dump using Windows Task Manager. It leverages Sys...
**Categories:** false_positive, T1003.001, splunk

#### Creation of Shadow Copy
The following analytic detects the creation of shadow copies using Vssadmin or Wmic. It leverages data from Endpoint...
**Categories:** false_positive, T1003.003, splunk

#### Creation of Shadow Copy with wmic and powershell
The following analytic detects the creation of shadow copies using "wmic" or "Powershell" commands. It leverages the...
**Categories:** false_positive, T1003.003, splunk

#### Cred Dump Tools Dropped Files
Files with well-known filenames (parts of credential dump software or files produced by them) creation (Level: high,...
**Categories:** false_positive, T1003.001, T1003.002, T1003.003, T1003.004, T1003.005, sigma

#### Credential Dumping Tools Service Execution - Security
Detects well-known credential dumping tools execution via service execution events (Level: high, Status: test)
**Categories:** false_positive, T1003.001, T1003.002, T1003.004, T1003.005, T1003.006, T1569.002, sigma

#### Credential Dumping Tools Service Execution - System
Detects well-known credential dumping tools execution via service execution events (Level: high, Status: test)
**Categories:** false_positive, T1003.001, T1003.002, T1003.004, T1003.005, T1003.006, T1569.002, sigma

#### Credential Manager Access By Uncommon Applications
Detects suspicious processes based on name and location that access the windows credential manager and vault.
Which c...
**Categories:** false_positive, T1003, sigma

#### CrowdStrike Falcon Stream Alerts
The following analytic is to leverage alerts from CrowdStrike Falcon Event Stream. This query aggregates and summariz...
**Categories:** false_positive, splunk

#### CSC Net On The Fly Compilation
The following analytic detects the use of the .NET compiler csc.exe for on-the-fly compilation of potentially malicio...
**Categories:** false_positive, T1027.004, splunk

#### DCERPC SMB Spoolss Named Pipe
Detects the use of the spoolss named pipe over SMB. This can be used to trigger the authentication via NTLM of any ma...
**Categories:** false_positive, T1021.002, sigma

#### Deleting Shadow Copies
The following analytic detects the deletion of shadow copies using the vssadmin.exe or wmic.exe utilities. It leverag...
**Categories:** false_positive, T1490, splunk

#### Denied Access To Remote Desktop
This event is generated when an authenticated user who is not allowed to log on remotely attempts to connect to this...
**Categories:** false_positive, T1021.001, sigma

#### Deployment AppX Package Was Blocked By AppLocker
Detects an appx package deployment that was blocked by AppLocker policy. (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Deployment Of The AppX Package Was Blocked By The Policy
Detects an appx package deployment that was blocked by the local computer policy.
The following events indicate that...
**Categories:** false_positive, sigma

#### Desktop.INI Created by Uncommon Process
Detects unusual processes accessing desktop.ini, which can be leveraged to alter how Explorer displays a folder's con...
**Categories:** false_positive, T1547.009, sigma

#### Detect AzureHound File Modifications
The following analytic detects the creation of specific AzureHound-related files, such as `*-azurecollection.zip` and...
**Categories:** false_positive, T1069.001, T1069.002, T1087.001, T1087.002, T1482, splunk

#### Detect Baron Samedit CVE-2021-3156 Segfault
The following analytic identifies a heap-based buffer overflow in sudoedit by detecting Linux logs containing both "s...
**Categories:** false_positive, T1068, splunk

#### Detect Copy of ShadowCopy with Script Block Logging
The following analytic detects the use of PowerShell commands to copy the SAM, SYSTEM, or SECURITY hives, which are c...
**Categories:** false_positive, T1003.002, splunk

#### Detect Credential Dumping through LSASS access
The following analytic detects attempts to read LSASS memory, indicative of credential dumping. It leverages Sysmon E...
**Categories:** false_positive, T1003.001, splunk

#### Detect Empire with PowerShell Script Block Logging
The following analytic detects suspicious PowerShell execution indicative of PowerShell-Empire activity. It leverages...
**Categories:** false_positive, T1059.001, splunk

#### Detect Excessive Account Lockouts From Endpoint
The following analytic detects endpoints causing a high number of account lockouts within a short period. It leverage...
**Categories:** false_positive, T1078.002, splunk

#### Detect Excessive User Account Lockouts
The following analytic identifies user accounts experiencing an excessive number of lockouts within a short timeframe...
**Categories:** false_positive, T1078.003, splunk

#### Detect Exchange Web Shell
The following analytic identifies the creation of suspicious .aspx files in known drop locations for Exchange exploit...
**Categories:** false_positive, T1133, T1190, T1505.003, splunk

#### Detect HTML Help Renamed
The following analytic detects instances where hh.exe (HTML Help) has been renamed and is executing a Compiled HTML H...
**Categories:** false_positive, T1218.001, splunk

#### Detect HTML Help URL in Command Line
The following analytic detects the execution of hh.exe (HTML Help) loading a Compiled HTML Help (CHM) file from a rem...
**Categories:** false_positive, T1218.001, splunk

#### Detect HTML Help Using InfoTech Storage Handlers
The following analytic detects the execution of hh.exe (HTML Help) using InfoTech Storage Handlers to load Windows sc...
**Categories:** false_positive, T1218.001, splunk

#### Detect Mimikatz With PowerShell Script Block Logging
The following analytic detects the execution of Mimikatz commands via PowerShell by leveraging PowerShell Script Bloc...
**Categories:** false_positive, T1003, T1059.001, splunk

#### Detect mshta inline hta execution
The following analytic detects the execution of "mshta.exe" with inline protocol handlers such as "JavaScript", "VBSc...
**Categories:** false_positive, T1218.005, splunk

#### Detect mshta renamed
The following analytic identifies instances where mshta.exe has been renamed and executed. It leverages Endpoint Dete...
**Categories:** false_positive, T1218.005, splunk

#### Detect MSHTA Url in Command Line
The following analytic detects the use of Microsoft HTML Application Host (mshta.exe) to make remote HTTP or HTTPS co...
**Categories:** false_positive, T1218.005, splunk

#### Detect New Local Admin account
The following analytic detects the creation of new accounts elevated to local administrators. It uses Windows event l...
**Categories:** false_positive, T1136.001, splunk

#### Detect Outlook exe writing a zip file
The following analytic identifies the execution of `outlook.exe` writing a `.zip` file to the disk.
It leverages data...
**Categories:** false_positive, T1566.001, splunk

#### Detect Password Spray Attack Behavior From Source
The following analytic identifies one source failing to authenticate with 10 or more unique users. This behavior coul...
**Categories:** false_positive, T1110.003, splunk

#### Detect Password Spray Attack Behavior On User
The following analytic identifies any user failing to authenticate from 10 or more unique sources. This behavior coul...
**Categories:** false_positive, T1110.003, splunk

#### Detect Prohibited Applications Spawning cmd exe
The following analytic detects executions of cmd.exe spawned by processes that are commonly abused by attackers and d...
**Categories:** false_positive, T1059.003, splunk

#### Detect PsExec With accepteula Flag
The following analytic identifies the execution of `PsExec.exe` with the `accepteula` flag in the command line. It le...
**Categories:** false_positive, T1021.002, splunk

#### Detect Rare Executables
The following analytic detects the execution of rare processes that appear only once across the network within a spec...
**Categories:** false_positive, T1204, splunk

#### Detect RClone Command-Line Usage
The following analytic detects the usage of `rclone.exe` with specific command-line arguments indicative of file tran...
**Categories:** false_positive, T1020, splunk

#### Detect Regasm Spawning a Process
The following analytic detects regasm.exe spawning a child process. This behavior is identified using data from Endpo...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regasm with Network Connection
The following analytic detects the execution of regasm.exe establishing a network connection to a public IP address,...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regasm with no Command Line Arguments
The following analytic detects instances of regasm.exe running without command line arguments. This behavior typicall...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regsvcs Spawning a Process
The following analytic identifies regsvcs.exe spawning a child process. This behavior is detected using Endpoint Dete...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regsvcs with Network Connection
The following analytic identifies instances of Regsvcs.exe establishing a network connection to a public IP address,...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regsvcs with No Command Line Arguments
The following analytic detects instances of regsvcs.exe running without command line arguments. This behavior typical...
**Categories:** false_positive, T1218.009, splunk

#### Detect Regsvr32 Application Control Bypass
The following analytic identifies the abuse of Regsvr32.exe to proxy execution of malicious code, specifically detect...
**Categories:** false_positive, T1218.010, splunk

#### Detect Remote Access Software Usage File
The following analytic detects the writing of files from known remote access software to disk within the environment....
**Categories:** false_positive, T1219, splunk

#### Detect Remote Access Software Usage FileInfo
The following analytic detects the execution of processes with file or code signing attributes from known remote acce...
**Categories:** false_positive, T1219, splunk

#### Detect Remote Access Software Usage Process
The following analytic detects the execution of known remote access software within the environment. It leverages dat...
**Categories:** false_positive, T1219, splunk

#### Detect Remote Access Software Usage Registry
The following analytic detects when a known remote access software is added to common persistence locations on a devi...
**Categories:** false_positive, T1219, splunk

#### Detect Renamed 7-Zip
The following analytic detects the usage of a renamed 7-Zip executable using Sysmon data. It leverages the OriginalFi...
**Categories:** false_positive, T1560.001, splunk

#### Detect Renamed PSExec
The following analytic identifies instances where `PsExec.exe` has been renamed and executed on an endpoint. It lever...
**Categories:** false_positive, T1569.002, splunk

#### Detect Renamed RClone
The following analytic detects the execution of a renamed `rclone.exe` process, which is commonly used for data exfil...
**Categories:** false_positive, T1020, splunk

#### Detect RTLO In File Name
The following analytic identifies the use of the right-to-left override
(RTLO) character in file names. It leverages...
**Categories:** false_positive, T1036.002, splunk

#### Detect RTLO In Process
The following analytic identifies the abuse of the right-to-left override (RTLO) character (U+202E) in process names....
**Categories:** false_positive, T1036.002, splunk

#### Detect Rundll32 Inline HTA Execution
The following analytic detects the execution of "rundll32.exe" with inline protocol handlers such as "JavaScript", "V...
**Categories:** false_positive, T1218.005, splunk

#### Detect SharpHound Command-Line Arguments
The following analytic detects the execution of SharpHound command-line arguments, specifically `-collectionMethod` a...
**Categories:** false_positive, T1069.001, T1069.002, T1087.001, T1087.002, T1482, splunk

#### Detect SharpHound File Modifications
The following analytic detects the creation of files typically associated with SharpHound, a reconnaissance tool used...
**Categories:** false_positive, T1069.001, T1069.002, T1087.001, T1087.002, T1482, splunk

#### Detect SharpHound Usage
The following analytic detects the usage of the SharpHound binary by identifying its original filename, `SharpHound.e...
**Categories:** false_positive, T1069.001, T1069.002, T1087.001, T1087.002, T1482, splunk

#### Detect Use of cmd exe to Launch Script Interpreters
The following analytic detects the execution of cscript.exe or wscript.exe processes initiated by cmd.exe. It leverag...
**Categories:** false_positive, T1059.003, splunk

#### Detect WMI Event Subscription Persistence
The following analytic identifies the creation of WMI Event Subscriptions, which can be used to establish persistence...
**Categories:** false_positive, T1546.003, splunk

#### Detection of tools built by NirSoft
The following analytic identifies the execution of tools built by NirSoft by detecting specific command-line argument...
**Categories:** false_positive, T1072, splunk

#### Disable AMSI Through Registry
The following analytic detects modifications to the Windows registry that disable the Antimalware Scan Interface (AMS...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender AntiVirus Registry
The following analytic detects the modification of Windows Defender registry settings to disable antivirus and antisp...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender BlockAtFirstSeen Feature
The following analytic detects the modification of the Windows registry to disable the Windows Defender BlockAtFirstS...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender Enhanced Notification
The following analytic detects the modification of the registry to disable Windows Defender's Enhanced Notification f...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender MpEngine Registry
The following analytic detects the modification of the Windows Defender MpEngine registry value, specifically setting...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender Spynet Reporting
The following analytic detects the modification of the registry to disable Windows Defender SpyNet reporting. It leve...
**Categories:** false_positive, T1562.001, splunk

#### Disable Defender Submit Samples Consent Feature
The following analytic detects the modification of the Windows registry to disable the Windows Defender Submit Sample...
**Categories:** false_positive, T1562.001, splunk

#### Disable ETW Through Registry
The following analytic detects modifications to the registry that disable the Event Tracing for Windows (ETW) feature...
**Categories:** false_positive, T1562.001, splunk

#### Disable Logs Using WevtUtil
The following analytic detects the execution of "wevtutil.exe" with parameters to disable event logs. It leverages da...
**Categories:** false_positive, T1070.001, splunk

#### Disable Registry Tool
The following analytic detects modifications to the Windows registry aimed at disabling the Registry Editor (regedit)...
**Categories:** false_positive, T1112, T1562.001, splunk

#### Disable Schedule Task
The following analytic detects the execution of a command to disable an existing scheduled task using 'schtasks.exe'...
**Categories:** false_positive, T1562.001, splunk

#### Disable UAC Remote Restriction
The following analytic detects the modification of the registry to disable UAC remote restriction by setting the "Loc...
**Categories:** false_positive, T1548.002, splunk

#### Disable Windows Behavior Monitoring
The following analytic identifies modifications in the registry to disable Windows Defender's real-time behavior moni...
**Categories:** false_positive, T1562.001, splunk

#### Disable Windows SmartScreen Protection
The following analytic detects modifications to the Windows registry that disable SmartScreen protection. It leverage...
**Categories:** false_positive, T1562.001, splunk

#### Disabled Kerberos Pre-Authentication Discovery With Get-ADUser
The following analytic detects the execution of the `Get-ADUser` PowerShell cmdlet with parameters indicating a searc...
**Categories:** false_positive, T1558.004, splunk

#### Disabled Kerberos Pre-Authentication Discovery With PowerView
The following analytic detects the execution of the `Get-DomainUser` commandlet with the `-PreauthNotRequired` parame...
**Categories:** false_positive, T1558.004, splunk

#### Disabling CMD Application
The following analytic detects modifications to the registry that disable the CMD prompt application. It leverages da...
**Categories:** false_positive, T1112, T1562.001, splunk

#### Disabling ControlPanel
The following analytic detects registry modifications that disable the Control Panel on Windows systems. It leverages...
**Categories:** false_positive, T1112, T1562.001, splunk

#### Disabling Defender Services
The following analytic detects the disabling of Windows Defender services by monitoring registry modifications. It le...
**Categories:** false_positive, T1562.001, splunk

#### Disabling Firewall with Netsh
The following analytic identifies the disabling of the firewall using the netsh application. It leverages data from E...
**Categories:** false_positive, T1562.001, splunk

#### Disabling FolderOptions Windows Feature
The following analytic detects the modification of the Windows registry to disable the Folder Options feature, which...
**Categories:** false_positive, T1562.001, splunk

#### Disabling NoRun Windows App
The following analytic detects the modification of the Windows registry to disable the Run application in the Start m...
**Categories:** false_positive, T1112, T1562.001, splunk

#### Disabling Remote User Account Control
The following analytic identifies modifications to the registry key that controls the enforcement of Windows User Acc...
**Categories:** false_positive, T1548.002, splunk

#### Disabling SystemRestore In Registry
The following analytic detects the modification of registry keys to disable System Restore on a machine. It leverages...
**Categories:** false_positive, T1490, splunk

#### Disabling Task Manager
The following analytic identifies modifications to the Windows registry that disable Task Manager. It leverages data...
**Categories:** false_positive, T1562.001, splunk

#### Disabling Windows Local Security Authority Defences via Registry
The following analytic identifies the deletion of registry keys that disable Local Security Authority (LSA) protectio...
**Categories:** false_positive, T1556, splunk

#### DLLHost with no Command Line Arguments with Network
The following analytic detects instances of DLLHost.exe running without
command line arguments while establishing a n...
**Categories:** false_positive, T1055, splunk

#### DNS Exfiltration Using Nslookup App
The following analytic identifies potential DNS exfiltration using the nslookup application. It detects specific comm...
**Categories:** false_positive, T1048, splunk

#### DNS HybridConnectionManager Service Bus
Detects Azure Hybrid Connection Manager services querying the Azure service bus service (Level: high, Status: test)
**Categories:** false_positive, T1554, sigma

#### DNS Query for Anonfiles.com Domain - DNS Client
Detects DNS queries for anonfiles.com, which is an anonymous file upload platform often used for malicious purposes (...
**Categories:** false_positive, T1567.002, sigma

#### DNS Query for Anonfiles.com Domain - Sysmon
Detects DNS queries for "anonfiles.com", which is an anonymous file upload platform often used for malicious purposes...
**Categories:** false_positive, T1567.002, sigma

#### DNS Query Request By QuickAssist.EXE
Detects DNS queries initiated by "QuickAssist.exe" to Microsoft Quick Assist primary endpoint that is used to establi...
**Categories:** false_positive, T1071.001, T1210, sigma

#### DNS Query To AzureWebsites.NET By Non-Browser Process
Detects a DNS query by a non browser process on the system to "azurewebsites.net". The latter was often used by threa...
**Categories:** false_positive, T1219.002, sigma

#### DNS Query To Common Malware Hosting and Shortener Services
Detects DNS queries to domains commonly used by threat actors to host malware payloads or redirect through URL shorte...
**Categories:** false_positive, T1071.004, sigma

#### DNS Query To Devtunnels Domain
Detects DNS query requests to Devtunnels domains. Attackers can abuse that feature to establish a reverse shell or pe...
**Categories:** false_positive, T1071.001, T1572, sigma

#### DNS Query To MEGA Hosting Website
Detects DNS queries for subdomains related to MEGA sharing website (Level: medium, Status: test)
**Categories:** false_positive, T1567.002, sigma

#### DNS Query To MEGA Hosting Website - DNS Client
Detects DNS queries for subdomains related to MEGA sharing website (Level: medium, Status: test)
**Categories:** false_positive, T1567.002, sigma

#### DNS Query To Put.io - DNS Client
Detects DNS queries for subdomains related to "Put.io" sharing website. (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### DNS Query To Remote Access Software Domain From Non-Browser App
An adversary may use legitimate desktop support and remote access software, such as Team Viewer, Go2Assist, LogMein,...
**Categories:** false_positive, T1219.002, sigma

#### DNS Query To Ufile.io
Detects DNS queries to "ufile.io", which was seen abused by malware and threat actors as a method for data exfiltrati...
**Categories:** false_positive, T1567.002, sigma

#### DNS Query To Ufile.io - DNS Client
Detects DNS queries to "ufile.io", which was seen abused by malware and threat actors as a method for data exfiltrati...
**Categories:** false_positive, T1567.002, sigma

#### DNS Query To Visual Studio Code Tunnels Domain
Detects DNS query requests to Visual Studio Code tunnel domains. Attackers can abuse that feature to establish a reve...
**Categories:** false_positive, T1071.001, sigma

#### DNS Server Discovery Via LDAP Query
Detects DNS server discovery via LDAP query requests from uncommon applications (Level: low, Status: test)
**Categories:** false_positive, T1482, sigma

#### Domain Account Discovery with Dsquery
The following analytic identifies the execution of `dsquery.exe` with command-line arguments used to discover domain...
**Categories:** false_positive, T1087.002, splunk

#### Domain Account Discovery with Wmic
The following analytic detects the execution of `wmic.exe` with command-line arguments used to query for domain users...
**Categories:** false_positive, T1087.002, splunk

#### Domain Controller Discovery with Nltest
The following analytic detects the execution of `nltest.exe` with command-line arguments `/dclist:` or `/dsgetdc:` to...
**Categories:** false_positive, T1018, splunk

#### Domain Controller Discovery with Wmic
The following analytic identifies the execution of `wmic.exe` with command-line arguments used to discover domain con...
**Categories:** false_positive, T1018, splunk

#### Domain Group Discovery with Adsisearcher
The following analytic detects the use of the `[Adsisearcher]` type accelerator in PowerShell to query Active Directo...
**Categories:** false_positive, T1069.002, splunk

#### Domain Group Discovery With Dsquery
The following analytic identifies the execution of `dsquery.exe` with command-line arguments used to query for domain...
**Categories:** false_positive, T1069.002, splunk

#### Domain Group Discovery With Wmic
The following analytic identifies the execution of `wmic.exe` with command-line arguments used to query for domain gr...
**Categories:** false_positive, T1069.002, splunk

#### Download Files Using Telegram
The following analytic detects suspicious file downloads by the Telegram application on a Windows system. It leverage...
**Categories:** false_positive, T1105, splunk

#### DPAPI Domain Master Key Backup Attempt
Detects anyone attempting a backup for the DPAPI Master Key. This events gets generated at the source and not the Dom...
**Categories:** false_positive, T1003.004, sigma

#### Driver Load From A Temporary Directory
Detects a driver load from a temporary directory (Level: high, Status: test)
**Categories:** false_positive, T1543.003, sigma

#### DSQuery Domain Discovery
The following analytic detects the execution of "dsquery.exe" with arguments targeting `TrustedDomain` queries direct...
**Categories:** false_positive, T1482, splunk

#### Dump Ntds.dit To Suspicious Location
Detects potential abuse of ntdsutil to dump ntds.dit database to a suspicious location (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Elevated Group Discovery with PowerView
The following analytic detects the execution of the `Get-DomainGroupMember` cmdlet from PowerView, identified through...
**Categories:** false_positive, T1069.002, splunk

#### Elevated Group Discovery With Wmic
The following analytic detects the execution of `wmic.exe` with command-line arguments querying specific elevated dom...
**Categories:** false_positive, T1069.002, splunk

#### Esentutl SAM Copy
The following analytic detects the use of `esentutl.exe` to access credentials stored in the ntds.dit or SAM file. Th...
**Categories:** false_positive, T1003.002, splunk

#### ETW Logging/Processing Option Disabled On IIS Server
Detects changes to of the IIS server configuration in order to disable/remove the ETW logging/processing option. (Lev...
**Categories:** false_positive, T1562.002, T1505.004, sigma

#### Eventlog Cleared
One of the Windows Eventlogs has been cleared. e.g. caused by "wevtutil cl" command execution (Level: medium, Status:...
**Categories:** false_positive, T1070.001, sigma

#### Eventvwr UAC Bypass
The following analytic detects an Eventvwr UAC bypass by identifying suspicious registry modifications in the path th...
**Categories:** false_positive, T1548.002, splunk

#### EVTX Created In Uncommon Location
Detects the creation of new files with the ".evtx" extension in non-common or non-standard location.
This could indic...
**Categories:** false_positive, T1562.002, sigma

#### Excessive distinct processes from Windows Temp
The following analytic identifies an excessive number of distinct processes executing from the Windows\Temp directory...
**Categories:** false_positive, T1059, splunk

#### Excessive File Deletion In WinDefender Folder
The following analytic detects excessive file deletion events in the Windows Defender folder. It leverages Sysmon Eve...
**Categories:** false_positive, T1485, splunk

#### Excessive number of service control start as disabled
The following analytic detects an excessive number of `sc.exe` processes launched with the command line argument `sta...
**Categories:** false_positive, T1562.001, splunk

#### Excessive number of taskhost processes
The following analytic identifies an excessive number of taskhost.exe and taskhostex.exe processes running within a s...
**Categories:** false_positive, T1059, splunk

#### Excessive Usage Of Cacls App
The following analytic identifies excessive usage of `cacls.exe`, `xcacls.exe`,
or `icacls.exe` to change file or fol...
**Categories:** false_positive, T1222, splunk

#### Excessive Usage Of SC Service Utility
The following analytic detects excessive usage of the `sc.exe` service utility on a host machine. It leverages Sysmon...
**Categories:** false_positive, T1569.002, splunk

#### Exchange PowerShell Abuse via SSRF
The following analytic detects suspicious behavior indicative of ProxyShell exploitation against on-premise Microsoft...
**Categories:** false_positive, T1190, T1133, splunk

#### Exchange PowerShell Cmdlet History Deleted
Detects the deletion of the Exchange PowerShell cmdlet History logs which may indicate an attempt to destroy forensic...
**Categories:** false_positive, T1070, sigma

#### Exchange PowerShell Module Usage
The following analytic detects the usage of specific Exchange PowerShell modules, such as New-MailboxExportRequest, N...
**Categories:** false_positive, T1059.001, splunk

#### Executable File Written in Administrative SMB Share
The following analytic detects executable files (.exe or .dll) being written to Windows administrative SMB shares (Ad...
**Categories:** false_positive, T1021.002, splunk

#### Executables Or Script Creation In Suspicious Path
The following analytic identifies the creation of executables or scripts in suspicious file paths on Windows systems....
**Categories:** false_positive, T1036, splunk

#### Executables Or Script Creation In Temp Path
The following analytic identifies the creation of executables or scripts in temporary file paths on Windows systems....
**Categories:** false_positive, T1036, splunk

#### External Disk Drive Or USB Storage Device Was Recognized By The System
Detects external disk drives or plugged-in USB devices. (Level: low, Status: test)
**Categories:** false_positive, T1091, T1200, sigma

#### External Remote RDP Logon from Public IP
Detects successful logon from public IP address via RDP. This can indicate a publicly-exposed RDP port. (Level: mediu...
**Categories:** false_positive, T1133, T1078, T1110, sigma

#### External Remote SMB Logon from Public IP
Detects successful logon from public IP address via SMB. This can indicate a publicly-exposed SMB port. (Level: high,...
**Categories:** false_positive, T1133, T1078, T1110, sigma

#### Failed Code Integrity Checks
Detects code integrity failures such as missing page hashes or corrupted drivers due unauthorized modification. This...
**Categories:** false_positive, T1027.001, sigma

#### Failed Logon From Public IP
Detects a failed logon attempt from a public IP. A login from a public IP can indicate a misconfigured firewall or ne...
**Categories:** false_positive, T1078, T1190, T1133, sigma

#### Failed MSExchange Transport Agent Installation
Detects a failed installation of a Exchange Transport Agent (Level: high, Status: test)
**Categories:** false_positive, T1505.002, sigma

#### File Access Of Signal Desktop Sensitive Data
Detects access to Signal Desktop's sensitive data files: db.sqlite and config.json.
The db.sqlite file in Signal Desk...
**Categories:** false_positive, T1003, sigma

#### File Deleted Via Sysinternals SDelete
Detects the deletion of files by the Sysinternals SDelete utility. It looks for the common name pattern used to renam...
**Categories:** false_positive, T1070.004, sigma

#### File Download or Read to Pipe Execution
The following analytic detects the use of download or file reading utilities from Windows, Linux or MacOS to download...
**Categories:** false_positive, T1105, splunk

#### File with Samsam Extension
The following analytic detects file writes with extensions indicative of a SamSam ransomware attack.
It leverages fil...
**Categories:** false_positive, splunk

#### Files With System DLL Name In Unsuspected Locations
Detects the creation of a file with the ".dll" extension that has the name of a System DLL in uncommon or unsuspected...
**Categories:** false_positive, T1036.005, sigma

#### Files With System Process Name In Unsuspected Locations
Detects the creation of an executable with a system process name in folders other than the system ones (System32, Sys...
**Categories:** false_positive, T1036.005, sigma

#### Firewall Allowed Program Enable
The following analytic detects the modification of a firewall rule to allow the execution of a specific application....
**Categories:** false_positive, T1562.004, splunk

#### First Time Seen Child Process of Zoom
The following analytic identifies the first-time execution of child processes spawned by Zoom (zoom.exe or zoom.us)....
**Categories:** false_positive, T1068, splunk

#### First Time Seen Remote Named Pipe
This detection excludes known namped pipes accessible remotely and notify on newly observed ones, may help to detect...
**Categories:** false_positive, T1021.002, sigma

#### First Time Seen Running Windows Service
The following analytic detects the first occurrence of a Windows service running in your environment. It leverages Wi...
**Categories:** false_positive, T1569.002, splunk

#### FodHelper UAC Bypass
The following analytic detects the execution of fodhelper.exe, which is known to exploit a User Account Control (UAC)...
**Categories:** false_positive, T1112, T1548.002, splunk

#### Get ADDefaultDomainPasswordPolicy with Powershell
The following analytic detects the execution of `powershell.exe` running the `Get-ADDefaultDomainPasswordPolicy` cmdl...
**Categories:** false_positive, T1201, splunk

#### Get ADDefaultDomainPasswordPolicy with Powershell Script Block
The following analytic detects the execution of the `Get-ADDefaultDomainPasswordPolicy` PowerShell cmdlet, which is u...
**Categories:** false_positive, T1201, splunk

#### Get ADUser with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments used to enumerate domain...
**Categories:** false_positive, T1087.002, splunk

#### Get ADUser with PowerShell Script Block
The following analytic detects the execution of the `Get-AdUser` PowerShell cmdlet, which is used to enumerate all do...
**Categories:** false_positive, T1087.002, splunk

#### Get ADUserResultantPasswordPolicy with Powershell
The following analytic detects the execution of `powershell.exe` running the `Get-ADUserResultantPasswordPolicy` cmdl...
**Categories:** false_positive, T1201, splunk

#### Get ADUserResultantPasswordPolicy with Powershell Script Block
The following analytic detects the execution of the `Get-ADUserResultantPasswordPolicy` PowerShell cmdlet, which is u...
**Categories:** false_positive, T1201, splunk

#### Get DomainPolicy with Powershell
The following analytic detects the execution of `powershell.exe` running the `Get-DomainPolicy` cmdlet, which is used...
**Categories:** false_positive, T1201, splunk

#### Get DomainPolicy with Powershell Script Block
The following analytic detects the execution of the `Get-DomainPolicy` cmdlet using PowerShell Script Block Logging (...
**Categories:** false_positive, T1201, splunk

#### Get DomainUser with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments used to enumerate domain...
**Categories:** false_positive, T1087.002, splunk

#### Get DomainUser with PowerShell Script Block
The following analytic detects the execution of the `Get-DomainUser` cmdlet using PowerShell Script Block Logging (Ev...
**Categories:** false_positive, T1087.002, splunk

#### Get WMIObject Group Discovery
The following analytic detects the use of the `Get-WMIObject Win32_Group` command executed via PowerShell to enumerat...
**Categories:** false_positive, T1069.001, splunk

#### Get WMIObject Group Discovery with Script Block Logging
The following analytic detects the execution of the `Get-WMIObject Win32_Group` command using PowerShell Script Block...
**Categories:** false_positive, T1069.001, splunk

#### Get-DomainTrust with PowerShell
The following analytic identifies the execution of the Get-DomainTrust command from PowerView using PowerShell, which...
**Categories:** false_positive, T1482, splunk

#### Get-DomainTrust with PowerShell Script Block
The following analytic detects the execution of the Get-DomainTrust command from PowerView using PowerShell Script Bl...
**Categories:** false_positive, T1482, splunk

#### Get-ForestTrust with PowerShell
The following analytic detects the execution of the Get-ForestTrust command via PowerShell, commonly used by adversar...
**Categories:** false_positive, T1482, splunk

#### Get-ForestTrust with PowerShell Script Block
The following analytic detects the execution of the Get-ForestTrust command from PowerSploit using PowerShell Script...
**Categories:** false_positive, T1482, T1059.001, splunk

#### GetAdComputer with PowerShell
The following analytic detects the execution of `powershell.exe` with the `Get-AdComputer` commandlet, which is used...
**Categories:** false_positive, T1018, splunk

#### GetAdComputer with PowerShell Script Block
The following analytic detects the execution of the `Get-AdComputer` PowerShell commandlet using PowerShell Script Bl...
**Categories:** false_positive, T1018, splunk

#### GetAdGroup with PowerShell
The following analytic detects the execution of `powershell.exe` with the `Get-AdGroup` commandlet, which is used to...
**Categories:** false_positive, T1069.002, splunk

#### GetAdGroup with PowerShell Script Block
The following analytic detects the execution of the `Get-AdGroup` PowerShell cmdlet using PowerShell Script Block Log...
**Categories:** false_positive, T1069.002, splunk

#### GetCurrent User with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments invoking the `GetCurrent...
**Categories:** false_positive, T1033, splunk

#### GetCurrent User with PowerShell Script Block
The following analytic detects the execution of the `GetCurrent` method from the WindowsIdentity .NET class using Pow...
**Categories:** false_positive, T1033, splunk

#### GetDomainComputer with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments that utilize `Get-Domain...
**Categories:** false_positive, T1018, splunk

#### GetDomainComputer with PowerShell Script Block
The following analytic detects the execution of the `Get-DomainComputer` commandlet using PowerShell Script Block Log...
**Categories:** false_positive, T1018, splunk

#### GetDomainController with PowerShell
The following analytic detects the execution of `powershell.exe` with the `Get-DomainController` command, which is us...
**Categories:** false_positive, T1018, splunk

#### GetDomainController with PowerShell Script Block
The following analytic detects the execution of the `Get-DomainController` commandlet using PowerShell Script Block L...
**Categories:** false_positive, T1018, splunk

#### GetDomainGroup with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments that query for domain gr...
**Categories:** false_positive, T1069.002, splunk

#### GetDomainGroup with PowerShell Script Block
The following analytic detects the execution of the `Get-DomainGroup` cmdlet using PowerShell Script Block Logging (E...
**Categories:** false_positive, T1069.002, splunk

#### GetLocalUser with PowerShell
The following analytic detects the execution of `powershell.exe` with the `Get-LocalUser` commandlet, which is used t...
**Categories:** false_positive, T1087.001, splunk

#### GetLocalUser with PowerShell Script Block
The following analytic detects the execution of the `Get-LocalUser` PowerShell commandlet using PowerShell Script Blo...
**Categories:** false_positive, T1059.001, T1087.001, splunk

#### GetNetTcpconnection with PowerShell
The following analytic identifies the execution of `powershell.exe` with the `Get-NetTcpConnection` command, which li...
**Categories:** false_positive, T1049, splunk

#### GetNetTcpconnection with PowerShell Script Block
The following analytic detects the execution of the `Get-NetTcpconnection` PowerShell cmdlet using PowerShell Script...
**Categories:** false_positive, T1049, splunk

#### GetWmiObject Ds Computer with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments that utilize the `Get-Wm...
**Categories:** false_positive, T1018, splunk

#### GetWmiObject Ds Computer with PowerShell Script Block
The following analytic detects the execution of the `Get-WmiObject` cmdlet with the `DS_Computer` class parameter via...
**Categories:** false_positive, T1018, splunk

#### GetWmiObject Ds Group with PowerShell
The following analytic identifies the execution of `powershell.exe` with command-line arguments used to query domain...
**Categories:** false_positive, T1069.002, splunk

#### GetWmiObject Ds Group with PowerShell Script Block
The following analytic detects the execution of the `Get-WmiObject` commandlet with the `DS_Group` parameter via Powe...
**Categories:** false_positive, T1069.002, splunk

#### GetWmiObject DS User with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments used to query domain use...
**Categories:** false_positive, T1087.002, splunk

#### GetWmiObject DS User with PowerShell Script Block
The following analytic detects the execution of the `Get-WmiObject` cmdlet with the `DS_User` class parameter via Pow...
**Categories:** false_positive, T1087.002, splunk

#### GetWmiObject User Account with PowerShell
The following analytic detects the execution of `powershell.exe` with command-line arguments that utilize the `Get-Wm...
**Categories:** false_positive, T1087.001, splunk

#### GetWmiObject User Account with PowerShell Script Block
The following analytic detects the execution of the `Get-WmiObject` commandlet with the `Win32_UserAccount` parameter...
**Categories:** false_positive, T1059.001, T1087.001, splunk

#### GitHub Workflow File Creation or Modification
The following analytic hunts for any creations or modifications to GitHub Actions workflow YAML files across the orga...
**Categories:** false_positive, T1574.006, T1554, T1195, splunk

#### GoToAssist Temporary Installation Artefact
An adversary may use legitimate desktop support and remote access software, such as Team Viewer, Go2Assist, LogMein,...
**Categories:** false_positive, T1219.002, sigma

#### GPUpdate with no Command Line Arguments with Network
The following analytic detects the execution of gpupdate.exe without command line arguments and with an active networ...
**Categories:** false_positive, T1055, splunk

#### Group Policy Abuse for Privilege Addition
Detects the first occurrence of a modification to Group Policy Object Attributes to add privileges to user accounts o...
**Categories:** false_positive, T1484.001, sigma

#### HackTool - Dumpert Process Dumper Default File
Detects the creation of the default dump file used by Outflank Dumpert tool. A process dumper, which dumps the lsass...
**Categories:** false_positive, T1003.001, sigma

#### HackTool - Powerup Write Hijack DLL
Powerup tool's Write Hijack DLL exploits DLL hijacking for privilege escalation.
In it's default mode, it builds a se...
**Categories:** false_positive, T1574.001, sigma

#### HackTool - SafetyKatz Dump Indicator
Detects default lsass dump filename generated by SafetyKatz. (Level: high, Status: test)
**Categories:** false_positive, T1003.001, sigma

#### HackTool - Typical HiveNightmare SAM File Export
Detects files written by the different tools that exploit HiveNightmare (Level: high, Status: test)
**Categories:** false_positive, T1552.001, sigma

#### Hacktool Ruler
This events that are generated when using the hacktool Ruler by Sensepost (Level: high, Status: test)
**Categories:** false_positive, T1087, T1114, T1059, T1550.002, sigma

#### Headless Browser Usage
The following analytic detects the usage of headless browsers within an organization. It identifies processes contain...
**Categories:** false_positive, T1497, T1564.003, splunk

#### Hidden Executable In NTFS Alternate Data Stream
Detects the creation of an ADS (Alternate Data Stream) that contains an executable by looking at a non-empty Imphash...
**Categories:** false_positive, T1564.004, sigma

#### Hiding Files And Directories With Attrib exe
The following analytic detects the use of the Windows binary attrib.exe to hide files or directories by marking them...
**Categories:** false_positive, T1222.001, splunk

#### High Frequency Copy Of Files In Network Share
The following analytic detects a high frequency of file copying or moving within network shares, which may indicate p...
**Categories:** false_positive, T1537, splunk

#### High Process Termination Frequency
The following analytic identifies a high frequency of process termination events on a computer within a short period....
**Categories:** false_positive, T1486, splunk

#### Hunting 3CXDesktopApp Software
The following analytic detects the presence of any version of the 3CXDesktopApp, also known as the 3CX Desktop App, o...
**Categories:** false_positive, T1195.002, splunk

#### HybridConnectionManager Service Installation
Rule to detect the Hybrid Connection Manager service installation. (Level: high, Status: test)
**Categories:** false_positive, T1554, sigma

#### HybridConnectionManager Service Running
Rule to detect the Hybrid Connection Manager service running on an endpoint. (Level: high, Status: test)
**Categories:** false_positive, T1554, sigma

#### IIS WebServer Access Logs Deleted
Detects the deletion of IIS WebServer access logs which may indicate an attempt to destroy forensic evidence (Level:...
**Categories:** false_positive, T1070, sigma

#### Impacket Lateral Movement Commandline Parameters
The following analytic identifies the use of suspicious command-line parameters associated with Impacket tools, such...
**Categories:** false_positive, T1021.002, T1021.003, T1047, T1543.003, splunk

#### Impacket Lateral Movement smbexec CommandLine Parameters
The following analytic identifies suspicious command-line parameters associated with the use of Impacket's smbexec.py...
**Categories:** false_positive, T1021.002, T1021.003, T1047, T1543.003, splunk

#### Impacket Lateral Movement WMIExec Commandline Parameters
The following analytic detects the use of Impacket's `wmiexec.py` tool for lateral movement by identifying specific c...
**Categories:** false_positive, T1021.002, T1021.003, T1047, T1543.003, splunk

#### Important Windows Eventlog Cleared
Detects the clearing of one of the Windows Core Eventlogs. e.g. caused by "wevtutil cl" command execution (Level: hig...
**Categories:** false_positive, T1070.001, sigma

#### Important Windows Service Terminated Unexpectedly
Detects important or interesting Windows services that got terminated unexpectedly. (Level: high, Status: test)
**Categories:** false_positive, sigma

#### Important Windows Service Terminated With Error
Detects important or interesting Windows services that got terminated for whatever reason (Level: high, Status: test)
**Categories:** false_positive, sigma

#### Interactive Session on Remote Endpoint with PowerShell
The following analytic detects the use of the `Enter-PSSession` cmdlet to establish an interactive session on a remot...
**Categories:** false_positive, T1021.006, splunk

#### ISATAP Router Address Was Set
Detects the configuration of a new ISATAP router on a Windows host. While ISATAP is a legitimate Microsoft technology...
**Categories:** false_positive, T1557, T1565.002, sigma

#### ISO File Created Within Temp Folders
Detects the creation of a ISO file in the Outlook temp folder or in the Appdata temp folder. Typical of Qakbot TTP fr...
**Categories:** false_positive, T1566.001, sigma

#### ISO Image Mounted
Detects the mount of an ISO image on an endpoint (Level: medium, Status: test)
**Categories:** false_positive, T1566.001, sigma

#### ISO or Image Mount Indicator in Recent Files
Detects the creation of recent element file that points to an .ISO, .IMG, .VHD or .VHDX file as often used in phishin...
**Categories:** false_positive, T1566.001, sigma

#### Java Writing JSP File
The following analytic detects the Java process writing a .jsp file to disk, which may indicate a web shell being dep...
**Categories:** false_positive, T1190, T1133, splunk

#### Kerberoasting Activity - Initial Query
This rule will collect the data needed to start looking into possible kerberoasting activity.
Further analysis or com...
**Categories:** false_positive, T1558.003, sigma

#### Kerberoasting spn request with RC4 encryption
The following analytic detects potential Kerberoasting attacks by identifying Kerberos service ticket requests with R...
**Categories:** false_positive, T1558.003, splunk

#### Kerberos Manipulation
Detects failed Kerberos TGT issue operation. This can be a sign of manipulations of TGT messages by an attacker. (Lev...
**Categories:** false_positive, T1212, sigma

#### Kerberos Pre-Authentication Flag Disabled with PowerShell
The following analytic detects the use of the `Set-ADAccountControl` PowerShell cmdlet with parameters that disable K...
**Categories:** false_positive, T1558.004, splunk

#### Kerberos Service Ticket Request Using RC4 Encryption
The following analytic detects Kerberos service ticket requests using RC4 encryption, leveraging Kerberos Event 4769....
**Categories:** false_positive, T1558.001, splunk

#### Kerberos TGT Request Using RC4 Encryption
The following analytic detects a Kerberos Ticket Granting Ticket (TGT) request using RC4-HMAC encryption (type 0x17)...
**Categories:** false_positive, T1550, splunk

#### Kerberos User Enumeration
The following analytic detects an unusual number of Kerberos Ticket Granting Ticket (TGT) requests for non-existing u...
**Categories:** false_positive, T1589.002, splunk

#### Linux Account Manipulation Of SSH Config and Keys
The following analytic detects the deletion of SSH keys on a Linux machine. It leverages filesystem event logs to ide...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Add Files In Known Crontab Directories
The following analytic detects unauthorized file creation in known crontab directories on Unix-based systems. It leve...
**Categories:** false_positive, T1053.003, splunk

#### Linux Add User Account
The following analytic detects the creation of new user accounts on Linux systems using commands like "useradd" or "a...
**Categories:** false_positive, T1136.001, splunk

#### Linux Adding Crontab Using List Parameter
The following analytic detects suspicious modifications to cron jobs on Linux systems using the crontab command with...
**Categories:** false_positive, T1053.003, splunk

#### Linux APT Privilege Escalation
The following analytic detects the use of the Advanced Package Tool (APT) or apt-get with elevated privileges via sud...
**Categories:** false_positive, T1548.003, splunk

#### Linux At Allow Config File Creation
The following analytic detects the creation of the /etc/at.allow or /etc/at.deny configuration files in Linux. It lev...
**Categories:** false_positive, T1053.003, splunk

#### Linux At Application Execution
The following analytic detects the execution of the "At" application in Linux, which can be used by attackers to crea...
**Categories:** false_positive, T1053.002, splunk

#### Linux Auditd Add User Account
The following analytic detects the creation of new user accounts on Linux systems using commands like "useradd" or "a...
**Categories:** false_positive, T1136.001, splunk

#### Linux Auditd Add User Account Type
The following analytic detects the suspicious add user account type. This behavior is critical for a SOC to monitor b...
**Categories:** false_positive, T1136.001, splunk

#### Linux Auditd AI CLI Permission Override Activated
This detection identifies when an AI command-line tool is launched in an unsafe mode that bypasses normal safety chec...
**Categories:** false_positive, T1480, splunk

#### Linux Auditd At Application Execution
The following analytic detects the execution of the "At" application in Linux, which can be used by attackers to crea...
**Categories:** false_positive, T1053.002, splunk

#### Linux Auditd Auditd Daemon Abort
The following analytic detects the abnormal termination of the Linux audit daemon (auditd) by identifying DAEMON_ABOR...
**Categories:** false_positive, T1562.012, splunk

#### Linux Auditd Auditd Daemon Shutdown
The following analytic detects the unexpected termination of the Linux Audit daemon (auditd) by monitoring for log en...
**Categories:** false_positive, T1562.012, splunk

#### Linux Auditd Auditd Daemon Start
The following analytic detects the (re)initialization of the Linux audit daemon (auditd) by identifying log entries o...
**Categories:** false_positive, T1562.012, splunk

#### Linux Auditd Auditd Service Stop
The following analytic detects the suspicious auditd service stop. This behavior is critical for a SOC to monitor bec...
**Categories:** false_positive, T1489, splunk

#### Linux Auditd Base64 Decode Files
The following analytic detects suspicious Base64 decode operations that may indicate malicious activity, such as data...
**Categories:** false_positive, T1140, splunk

#### Linux Auditd Change File Owner To Root
The following analytic detects the use of the 'chown' command to change a file owner to 'root' on a Linux system. It...
**Categories:** false_positive, T1222.002, splunk

#### Linux Auditd Clipboard Data Copy
The following analytic detects the use of the Linux 'xclip' command to copy data from the clipboard. It leverages Lin...
**Categories:** false_positive, T1115, splunk

#### Linux Auditd Data Transfer Size Limits Via Split
The following analytic detects suspicious data transfer activities that involve the use of the `split` syscall, poten...
**Categories:** false_positive, T1030, splunk

#### Linux Auditd Data Transfer Size Limits Via Split Syscall
The following analytic detects suspicious data transfer activities that involve the use of the `split` syscall, poten...
**Categories:** false_positive, T1030, splunk

#### Linux Auditd Database File And Directory Discovery
The following analytic detects suspicious database file and directory discovery activities, which may signal an attac...
**Categories:** false_positive, T1083, splunk

#### Linux Auditd Dd File Overwrite
The following analytic detects the use of the 'dd' command to overwrite files on a Linux system. It leverages data fr...
**Categories:** false_positive, T1485, splunk

#### Linux Auditd Disable Or Modify System Firewall
The following analytic detects the suspicious disable or modify system firewall. This behavior is critical for a SOC...
**Categories:** false_positive, T1562.004, splunk

#### Linux Auditd Doas Conf File Creation
The following analytic detects the creation of the doas.conf file on a Linux host.
This file is used by the doas util...
**Categories:** false_positive, T1548.003, splunk

#### Linux Auditd Doas Tool Execution
The following analytic detects the execution of the 'doas' tool on a Linux host. This tool allows standard users to p...
**Categories:** false_positive, T1548.003, splunk

#### Linux Auditd Edit Cron Table Parameter
The following analytic detects the suspicious editing of cron jobs in Linux using the crontab command-line parameter...
**Categories:** false_positive, T1053.003, splunk

#### Linux Auditd File And Directory Discovery
The following analytic detects suspicious file and directory discovery activities, which may indicate an attacker's e...
**Categories:** false_positive, T1083, splunk

#### Linux Auditd File Permission Modification Via Chmod
The following analytic detects suspicious file permission modifications using the `chmod` command, which may indicate...
**Categories:** false_positive, T1222.002, splunk

#### Linux Auditd File Permissions Modification Via Chattr
The following analytic detects suspicious file permissions modifications using the chattr command, which may indicate...
**Categories:** false_positive, T1222.002, splunk

#### Linux Auditd Find Credentials From Password Managers
The following analytic detects suspicious attempts to find credentials stored in password managers, which may indicat...
**Categories:** false_positive, T1555.005, splunk

#### Linux Auditd Find Credentials From Password Stores
The following analytic detects suspicious attempts to find credentials stored in password stores, indicating a potent...
**Categories:** false_positive, T1555.005, splunk

#### Linux Auditd Find Ssh Private Keys
The following analytic detects suspicious attempts to find SSH private keys, which may indicate an attacker's effort...
**Categories:** false_positive, T1552.004, splunk

#### Linux Auditd Hardware Addition Swapoff
The following analytic detects the execution of the "swapoff" command, which disables the swapping of paging devices...
**Categories:** false_positive, T1200, splunk

#### Linux Auditd Hidden Files And Directories Creation
The following analytic detects suspicious creation of hidden files and directories, which may indicate an attacker's...
**Categories:** false_positive, T1083, splunk

#### Linux Auditd Insert Kernel Module Using Insmod Utility
The following analytic detects the insertion of a Linux kernel module using the insmod utility. It leverages data fro...
**Categories:** false_positive, T1547.006, splunk

#### Linux Auditd Install Kernel Module Using Modprobe Utility
The following analytic detects the installation of a Linux kernel module using the modprobe utility. It leverages dat...
**Categories:** false_positive, T1547.006, splunk

#### Linux Auditd Kernel Module Enumeration
The following analytic identifies the use of the 'kmod' process to list kernel modules on a Linux system. This detect...
**Categories:** false_positive, T1082, T1014, splunk

#### Linux Auditd Kernel Module Using Rmmod Utility
The following analytic detects suspicious use of the `rmmod` utility for kernel module removal, which may indicate an...
**Categories:** false_positive, T1547.006, splunk

#### Linux Auditd Nopasswd Entry In Sudoers File
The following analytic detects the addition of NOPASSWD entries to the /etc/sudoers file on Linux systems. It leverag...
**Categories:** false_positive, T1548.003, splunk

#### Linux Auditd Osquery Service Stop
The following analytic detects suspicious stopping of the `osquery` service, which may indicate an attempt to disable...
**Categories:** false_positive, T1489, splunk

#### Linux Auditd Possible Access Or Modification Of Sshd Config File
The following analytic detects access, deletion or modification of the ssh_config file on Linux systems.
It leverages...
**Categories:** false_positive, T1098.004, splunk

#### Linux Auditd Possible Access To Credential Files
The following analytic detects attempts to access or dump the contents of /etc/passwd and /etc/shadow files on Linux...
**Categories:** false_positive, T1003.008, splunk

#### Linux Auditd Possible Access To Sudoers File
The following analytic detects potential access or modification of the /etc/sudoers file on a Linux system.
It levera...
**Categories:** false_positive, T1548.003, splunk

#### Linux Auditd Possible Append Cronjob Entry On Existing Cronjob File
The following analytic detects potential tampering with cronjob files on a Linux system.
It leverages logs from Linux...
**Categories:** false_positive, T1053.003, splunk

#### Linux Auditd Preload Hijack Library Calls
The following analytic detects the use of the LD_PRELOAD environment variable to hijack or hook library functions on...
**Categories:** false_positive, T1574.006, splunk

#### Linux Auditd Preload Hijack Via Preload File
The following analytic detects suspicious preload hijacking via the `preload` file, which may indicate an attacker's...
**Categories:** false_positive, T1574.006, splunk

#### Linux Auditd Private Keys and Certificate Enumeration
The following analytic detects suspicious attempts to find private keys, which may indicate an attacker's effort to a...
**Categories:** false_positive, T1552.004, splunk

#### Linux Auditd Service Restarted
The following analytic detects the restarting or re-enabling of services on Linux systems using the `systemctl` or `s...
**Categories:** false_positive, T1053.006, splunk

#### Linux Auditd Service Started
The following analytic detects the suspicious service started. This behavior is critical for a SOC to monitor because...
**Categories:** false_positive, T1569.002, splunk

#### Linux Auditd Setuid Using Chmod Utility
The following analytic detects the execution of the chmod utility to set the SUID or SGID bit on files, which can all...
**Categories:** false_positive, T1548.001, splunk

#### Linux Auditd Setuid Using Setcap Utility
The following analytic detects the execution of the 'setcap' utility to enable the SUID bit on Linux systems. It leve...
**Categories:** false_positive, T1548.001, splunk

#### Linux Auditd Shred Overwrite Command
The following analytic detects the execution of the 'shred' command on a Linux machine, which is used to overwrite fi...
**Categories:** false_positive, T1485, splunk

#### Linux Auditd Stop Services
The following analytic detects attempts to stop a service on Linux systems. It leverages data from Linux Auditd. This...
**Categories:** false_positive, T1489, splunk

#### Linux Auditd Sudo Or Su Execution
The following analytic detects the execution of the "sudo" or "su" command on a Linux operating system. It leverages...
**Categories:** false_positive, T1548.003, splunk

#### Linux Auditd Sysmon Service Stop
The following analytic detects the suspicious sysmon service stop. This behavior is critical for a SOC to monitor bec...
**Categories:** false_positive, T1489, splunk

#### Linux Auditd System Network Configuration Discovery
The following analytic detects suspicious system network configuration discovery activities, which may indicate an ad...
**Categories:** false_positive, T1016, splunk

#### Linux Auditd Unix Shell Configuration Modification
The following analytic detects suspicious access or modifications to Unix shell configuration files, which may indica...
**Categories:** false_positive, T1546.004, splunk

#### Linux Auditd Unload Module Via Modprobe
The following analytic detects suspicious use of the `modprobe` command to unload kernel modules, which may indicate...
**Categories:** false_positive, T1547.006, splunk

#### Linux Auditd Virtual Disk File And Directory Discovery
The following analytic detects suspicious discovery of virtual disk files and directories, which may indicate an atta...
**Categories:** false_positive, T1083, splunk

#### Linux Auditd Whoami User Discovery
The following analytic detects the suspicious use of the whoami command, which may indicate an attacker trying to gat...
**Categories:** false_positive, T1033, splunk

#### Linux AWK Privilege Escalation
The following analytic detects the use of the AWK command with elevated privileges to execute system commands. It lev...
**Categories:** false_positive, T1548.003, splunk

#### Linux Busybox Privilege Escalation
The following analytic detects the execution of BusyBox with sudo privileges, which can lead to privilege escalation...
**Categories:** false_positive, T1548.003, splunk

#### Linux c89 Privilege Escalation
The following analytic detects the execution of the 'c89' command with elevated privileges, which can be used to comp...
**Categories:** false_positive, T1548.003, splunk

#### Linux c99 Privilege Escalation
The following analytic detects the execution of the c99 utility with sudo privileges, which can lead to privilege esc...
**Categories:** false_positive, T1548.003, splunk

#### Linux Change File Owner To Root
The following analytic detects the use of the 'chown' command to change a file owner to 'root' on a Linux system. It...
**Categories:** false_positive, T1222.002, splunk

#### Linux Clipboard Data Copy
The following analytic detects the use of the Linux 'xclip' command to copy data from the clipboard. It leverages End...
**Categories:** false_positive, T1115, splunk

#### Linux Common Process For Elevation Control
The following analytic identifies the execution of common Linux processes used for elevation control, such as `chmod`...
**Categories:** false_positive, T1548.001, splunk

#### Linux Composer Privilege Escalation
The following analytic detects the execution of the Composer tool with elevated privileges on a Linux system. It iden...
**Categories:** false_positive, T1548.003, splunk

#### Linux Cpulimit Privilege Escalation
The following analytic detects the use of the 'cpulimit' command with specific flags ('-l', '-f') executed with 'sudo...
**Categories:** false_positive, T1548.003, splunk

#### Linux Csvtool Privilege Escalation
The following analytic detects the execution of the 'csvtool' command with 'sudo' privileges, which can allow a user...
**Categories:** false_positive, T1548.003, splunk

#### Linux Curl Upload File
The following analytic detects the use of the curl command with specific switches (-F, --form, --upload-file, -T, -d,...
**Categories:** false_positive, T1105, splunk

#### Linux DD File Overwrite
The following analytic detects the use of the 'dd' command to overwrite files on a Linux system. It leverages data fr...
**Categories:** false_positive, T1485, splunk

#### Linux Decode Base64 to Shell
The following analytic detects the behavior of decoding base64-encoded data and passing it to a Linux shell. Addition...
**Categories:** false_positive, T1027, T1059.004, splunk

#### Linux Deleting Critical Directory Using RM Command
The following analytic detects the deletion of critical directories on a Linux machine using the `rm` command with ar...
**Categories:** false_positive, T1485, splunk

#### Linux Deletion Of Cron Jobs
The following analytic detects the deletion of cron jobs on a Linux machine. It leverages filesystem event logs to id...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Deletion Of Init Daemon Script
The following analytic detects the deletion of init daemon scripts on a Linux machine. It leverages filesystem event...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Deletion Of Services
The following analytic detects the deletion of services on a Linux machine. It leverages filesystem event logs to ide...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Deletion of SSL Certificate
The following analytic detects the deletion of SSL certificates on a Linux machine. It leverages filesystem event log...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Disable Services
The following analytic detects attempts to disable a service on a Linux system. It leverages data from Endpoint Detec...
**Categories:** false_positive, T1489, splunk

#### Linux Doas Conf File Creation
The following analytic detects the creation of the doas.conf file on a Linux host. This file is used by the doas util...
**Categories:** false_positive, T1548.003, splunk

#### Linux Doas Tool Execution
The following analytic detects the execution of the 'doas' tool on a Linux host. This tool allows standard users to p...
**Categories:** false_positive, T1548.003, splunk

#### Linux Docker Root Directory Mount
This detection identifies Docker containers that mount the host's root directory into the container filesystem.
Mount...
**Categories:** false_positive, T1611, splunk

#### Linux Docker Shell Execution
This detection identifies shell execution activity associated with Docker containers on Linux systems.
Specifically,...
**Categories:** false_positive, T1059.013, splunk

#### Linux Edit Cron Table Parameter
The following analytic detects the suspicious editing of cron jobs in Linux using the crontab command-line parameter...
**Categories:** false_positive, T1053.003, splunk

#### Linux Emacs Privilege Escalation
The following analytic detects the execution of Emacs with elevated privileges using the `sudo` command and the `--ev...
**Categories:** false_positive, T1548.003, splunk

#### Linux File Created In Kernel Driver Directory
The following analytic detects the creation of files in the Linux kernel/driver directory. It leverages filesystem da...
**Categories:** false_positive, T1547.006, splunk

#### Linux File Creation In Init Boot Directory
The following analytic detects the creation of files in Linux init boot directories, which are used for automatic exe...
**Categories:** false_positive, T1037.004, splunk

#### Linux File Creation In Profile Directory
The following analytic detects the creation of files in the /etc/profile.d directory on Linux systems. It leverages f...
**Categories:** false_positive, T1546.004, splunk

#### Linux Find Privilege Escalation
The following analytic detects the use of the 'find' command with 'sudo' and '-exec' options, which can indicate an a...
**Categories:** false_positive, T1548.003, splunk

#### Linux GDB Privilege Escalation
The following analytic detects the execution of the GNU Debugger (GDB) with specific flags that indicate an attempt t...
**Categories:** false_positive, T1548.003, splunk

#### Linux Gdrive Binary Activity
The following analytic detects the execution of the 'gdrive' tool on a Linux host. This tool allows standard users to...
**Categories:** false_positive, T1567, splunk

#### Linux Gem Privilege Escalation
The following analytic detects the execution of the RubyGems utility with elevated privileges, specifically when it i...
**Categories:** false_positive, T1548.003, splunk

#### Linux GNU Awk Privilege Escalation
The following analytic detects the execution of the 'gawk' command with elevated privileges on a Linux system. It lev...
**Categories:** false_positive, T1548.003, splunk

#### Linux Hardware Addition SwapOff
The following analytic detects the execution of the "swapoff" command, which disables the swapping of paging devices...
**Categories:** false_positive, T1200, splunk

#### Linux High Frequency Of File Deletion In Boot Folder
The following analytic detects a high frequency of file deletions in the /boot/ folder on Linux systems. It leverages...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux High Frequency Of File Deletion In Etc Folder
The following analytic detects a high frequency of file deletions in the /etc/ folder on Linux systems. It leverages...
**Categories:** false_positive, T1070.004, T1485, splunk

#### Linux Impair Defenses Process Kill
The following analytic identifies the execution of the 'pkill' command, which is used to terminate processes on a Lin...
**Categories:** false_positive, T1562.001, splunk

#### Linux Indicator Removal Service File Deletion
The following analytic detects the deletion of Linux service unit configuration files by suspicious processes. It lev...
**Categories:** false_positive, T1070.004, splunk

#### Linux Ingress Tool Transfer Hunting
The following analytic detects the use of 'curl' and 'wget' commands within a Linux environment. It leverages data fr...
**Categories:** false_positive, T1105, splunk

#### Linux Ingress Tool Transfer with Curl
The following analytic detects the use of the curl command with specific switches (-O, -sO, -ksO, --output) commonly...
**Categories:** false_positive, T1105, splunk

#### Linux Insert Kernel Module Using Insmod Utility
The following analytic detects the insertion of a Linux kernel module using the insmod utility. It leverages data fro...
**Categories:** false_positive, T1547.006, splunk

#### Linux Install Kernel Module Using Modprobe Utility
The following analytic detects the installation of a Linux kernel module using the modprobe utility. It leverages dat...
**Categories:** false_positive, T1547.006, splunk

#### Linux Iptables Firewall Modification
The following analytic detects suspicious command-line activity that modifies the iptables firewall settings on a Lin...
**Categories:** false_positive, T1562.004, splunk

#### Linux Kernel Module Enumeration
The following analytic identifies the use of the 'kmod' process to list kernel modules on a Linux system. This detect...
**Categories:** false_positive, T1082, T1014, splunk

#### Linux Magic SysRq Key Abuse
Detects potential abuse of the Linux Magic SysRq (System Request) key by adversaries with root or sufficient privileg...
**Categories:** false_positive, T1059.004, T1529, T1489, T1499, splunk

#### Linux Make Privilege Escalation
The following analytic detects the use of the 'make' command with elevated privileges to execute system commands as r...
**Categories:** false_positive, T1548.003, splunk

#### Linux Medusa Rootkit
This detection identifies file creation events associated with the installation of the Medusa rootkit, a userland LD_...
**Categories:** false_positive, T1014, T1589.001, splunk

#### Linux MySQL Privilege Escalation
The following analytic detects the execution of MySQL commands with elevated privileges using sudo, which can lead to...
**Categories:** false_positive, T1548.003, splunk

#### Linux Ngrok Reverse Proxy Usage
The following analytic detects the use of Ngrok on a Linux operating system. It leverages data from Endpoint Detectio...
**Categories:** false_positive, T1572, T1090, T1102, splunk

#### Linux Node Privilege Escalation
The following analytic identifies the execution of Node.js with elevated privileges using sudo, specifically when spa...
**Categories:** false_positive, T1548.003, splunk

#### Linux NOPASSWD Entry In Sudoers File
The following analytic detects the addition of NOPASSWD entries to the /etc/sudoers file on Linux systems. It leverag...
**Categories:** false_positive, T1548.003, splunk

#### Linux Obfuscated Files or Information Base64 Decode
The following analytic detects the use of the base64 decode command on Linux systems, which is often used to deobfusc...
**Categories:** false_positive, T1027, splunk

#### Linux Octave Privilege Escalation
The following analytic detects the execution of GNU Octave with elevated privileges, specifically when it runs system...
**Categories:** false_positive, T1548.003, splunk

#### Linux OpenVPN Privilege Escalation
The following analytic detects the execution of OpenVPN with elevated privileges, specifically when combined with the...
**Categories:** false_positive, T1548.003, splunk

#### Linux Persistence and Privilege Escalation Risk Behavior
The following analytic identifies potential Linux persistence and privilege escalation activities. It leverages risk...
**Categories:** false_positive, T1548, splunk

#### Linux PHP Privilege Escalation
The following analytic detects the execution of PHP commands with elevated privileges on a Linux system. It identifie...
**Categories:** false_positive, T1548.003, splunk

#### Linux pkexec Privilege Escalation
The following analytic detects the execution of `pkexec` without any command-line arguments. This behavior leverages...
**Categories:** false_positive, T1068, splunk

#### Linux Possible Access Or Modification Of sshd Config File
The following analytic detects suspicious access or modification of the sshd_config file on Linux systems. It leverag...
**Categories:** false_positive, T1098.004, splunk

#### Linux Possible Access To Credential Files
The following analytic detects attempts to access or dump the contents of /etc/passwd and /etc/shadow files on Linux...
**Categories:** false_positive, T1003.008, splunk

#### Linux Possible Access To Sudoers File
The following analytic detects potential access or modification of the /etc/sudoers file on a Linux system. It levera...
**Categories:** false_positive, T1548.003, splunk

#### Linux Possible Append Command To At Allow Config File
The following analytic detects suspicious command lines that append user entries to /etc/at.allow or /etc/at.deny fil...
**Categories:** false_positive, T1053.002, splunk

#### Linux Possible Append Command To Profile Config File
The following analytic detects suspicious command-lines that modify user profile files to automatically execute scrip...
**Categories:** false_positive, T1546.004, splunk

#### Linux Possible Append Cronjob Entry on Existing Cronjob File
The following analytic detects potential tampering with cronjob files on a Linux system by identifying 'echo' command...
**Categories:** false_positive, T1053.003, splunk

#### Linux Possible Cronjob Modification With Editor
The following analytic detects potential unauthorized modifications to Linux cronjobs using text editors like "nano,"...
**Categories:** false_positive, T1053.003, splunk

#### Linux Possible Ssh Key File Creation
The following analytic detects the creation of SSH key files in the ~/.ssh/ directory. It leverages filesystem data t...
**Categories:** false_positive, T1098.004, splunk

#### Linux Preload Hijack Library Calls
The following analytic detects the use of the LD_PRELOAD environment variable to hijack or hook library functions on...
**Categories:** false_positive, T1574.006, splunk

#### Linux Proxy Socks Curl
The following analytic detects the use of the `curl` command with proxy-related arguments such as `-x`, `socks`, `--p...
**Categories:** false_positive, T1090, T1095, splunk

#### Linux Puppet Privilege Escalation
The following analytic detects the execution of Puppet commands with elevated privileges, specifically when Puppet is...
**Categories:** false_positive, T1548.003, splunk

#### Linux RPM Privilege Escalation
The following analytic detects the execution of the RPM Package Manager with elevated privileges, specifically when i...
**Categories:** false_positive, T1548.003, splunk

#### Linux Ruby Privilege Escalation
The following analytic detects the execution of Ruby commands with elevated privileges on a Linux system. It identifi...
**Categories:** false_positive, T1548.003, splunk

#### Linux Service File Created In Systemd Directory
The following analytic detects the creation of suspicious service files within the systemd directories on Linux platf...
**Categories:** false_positive, T1053.006, splunk

#### Linux Service Restarted
The following analytic detects the restarting or re-enabling of services on Linux systems using the `systemctl` or `s...
**Categories:** false_positive, T1053.006, splunk

#### Linux Service Started Or Enabled
The following analytic detects the creation or enabling of services on Linux platforms using the systemctl or service...
**Categories:** false_positive, T1053.006, splunk

#### Linux Setuid Using Chmod Utility
The following analytic detects the execution of the chmod utility to set the SUID or SGID bit on files, which can all...
**Categories:** false_positive, T1548.001, splunk

#### Linux Setuid Using Setcap Utility
The following analytic detects the execution of the 'setcap' utility to enable the SUID bit on Linux systems. It leve...
**Categories:** false_positive, T1548.001, splunk

#### Linux Shred Overwrite Command
The following analytic detects the execution of the 'shred' command on a Linux machine, which is used to overwrite fi...
**Categories:** false_positive, T1485, splunk

#### Linux Sqlite3 Privilege Escalation
The following analytic detects the execution of the sqlite3 command with elevated privileges, which can be exploited...
**Categories:** false_positive, T1548.003, splunk

#### Linux SSH Authorized Keys Modification
The following analytic detects the modification of SSH Authorized Keys on Linux systems. It leverages process executi...
**Categories:** false_positive, T1098.004, splunk

#### Linux SSH Remote Services Script Execute
The following analytic detects the use of SSH to move laterally and execute a script or file on a remote host. It lev...
**Categories:** false_positive, T1021.004, splunk

#### Linux Stop Services
The following analytic detects attempts to stop or clear a service on Linux systems. It leverages data from Endpoint...
**Categories:** false_positive, T1489, splunk

#### Linux Sudo OR Su Execution
The following analytic detects the execution of the "sudo" or "su" command on a Linux operating system. It leverages...
**Categories:** false_positive, T1548.003, splunk

#### Linux Sudoers Tmp File Creation
The following analytic detects the creation of the "sudoers.tmp" file, which occurs when editing the /etc/sudoers fil...
**Categories:** false_positive, T1548.003, splunk

#### Linux Suspicious React or Next.js Child Process
This analytic detects Linux processes such as sh, bash, and common Linux LOLBINs being spawned by React or Next.js ap...
**Categories:** false_positive, T1190, T1059.004, splunk

#### Linux System Network Discovery
The following analytic identifies potential enumeration of local network configuration on Linux systems. It detects t...
**Categories:** false_positive, T1016, splunk

#### Linux Telnet Authentication Bypass
Detects an authentication bypass in telnet tracked as CVE-2026-24061. An attacker can supply a specifically crafted U...
**Categories:** false_positive, T1548, splunk

#### Linux Visudo Utility Execution
The following analytic detects the execution of the 'visudo' utility to modify the /etc/sudoers file on a Linux syste...
**Categories:** false_positive, T1548.003, splunk

#### LLM Model File Creation
Detects the creation of Large Language Model (LLM) files on Windows endpoints by monitoring file creation events for...
**Categories:** false_positive, T1543, splunk

#### Loading Diagcab Package From Remote Path
Detects loading of diagcab packages from a remote path, as seen in DogWalk vulnerability (Level: high, Status: test)
**Categories:** false_positive, sigma

#### Loading Of Dynwrapx Module
The following analytic detects the loading of the dynwrapx.dll module, which is associated with the DynamicWrapperX A...
**Categories:** false_positive, T1055.001, splunk

#### Local Account Discovery With Wmic
The following analytic detects the execution of `wmic.exe` with command-line arguments used to query local user accou...
**Categories:** false_positive, T1087.001, splunk

#### Local LLM Framework DNS Query
Detects DNS queries related to local LLM models on endpoints by monitoring Sysmon DNS query events (Event ID 22) for...
**Categories:** false_positive, T1590, splunk

#### Local User Creation
Detects local user creation on Windows servers, which shouldn't happen in an Active Directory environment. Apply this...
**Categories:** false_positive, T1136.001, sigma

#### Locked Workstation
Detects locked workstation session events that occur automatically after a standard period of inactivity. (Level: inf...
**Categories:** false_positive, sigma

#### LOLBAS With Network Traffic
The following analytic identifies the use of Living Off the Land Binaries and Scripts (LOLBAS) with network traffic....
**Categories:** false_positive, T1105, T1567, T1218, splunk

#### LSASS Access Detected via Attack Surface Reduction
Detects Access to LSASS Process (Level: high, Status: test)
**Categories:** false_positive, T1003.001, sigma

#### LSASS Process Crashed - Application
Detects Windows error reporting events where the process that crashed is LSASS (Local Security Authority Subsystem Se...
**Categories:** false_positive, T1003.001, sigma

#### LSASS Process Dump Artefact In CrashDumps Folder
Detects the presence of an LSASS dump file in the "CrashDumps" folder. This could be a sign of LSASS credential dumpi...
**Categories:** false_positive, T1003.001, sigma

#### MacOS plutil
The following analytic detects the usage of the `plutil` command to modify plist files on macOS systems. It leverages...
**Categories:** false_positive, T1647, splunk

#### Malicious Driver Load By Name
Detects loading of known malicious drivers via the file name of the drivers. (Level: medium, Status: test)
**Categories:** false_positive, T1543.003, T1068, sigma

#### Malicious InProcServer32 Modification
The following analytic detects a process modifying the registry with a known malicious CLSID under InProcServer32. It...
**Categories:** false_positive, T1218.010, T1112, splunk

#### Malicious Powershell Executed As A Service
The following analytic identifies the execution of malicious PowerShell commands or payloads via the Windows SC.exe u...
**Categories:** false_positive, T1569.002, splunk

#### Malicious PowerShell Process - Encoded Command
The following analytic detects the use of the EncodedCommand parameter in PowerShell processes. It leverages Endpoint...
**Categories:** false_positive, T1027, splunk

#### Malicious PowerShell Process - Execution Policy Bypass
The following analytic detects PowerShell processes initiated with parameters that bypass the local execution policy...
**Categories:** false_positive, T1059.001, splunk

#### Malicious PowerShell Process With Obfuscation Techniques
The following analytic detects PowerShell processes launched with command-line arguments indicative of obfuscation te...
**Categories:** false_positive, T1059.001, splunk

#### Mesh Agent Service Installation
Detects a Mesh Agent service installation. Mesh Agent is used to remotely manage computers (Level: medium, Status: test)
**Categories:** false_positive, T1219.002, sigma

#### Metasploit Or Impacket Service Installation Via SMB PsExec
Detects usage of Metasploit SMB PsExec (exploit/windows/smb/psexec) and Impacket psexec.py by triggering on specific...
**Categories:** false_positive, T1021.002, T1570, T1569.002, sigma

#### Metasploit SMB Authentication
Alerts on Metasploit host's authentications on the domain. (Level: high, Status: test)
**Categories:** false_positive, T1021.002, sigma

#### Microsoft Defender ATP Alerts
The following analytic is to leverage alerts from Microsoft Defender ATP Alerts. This query aggregates and summarizes...
**Categories:** false_positive, splunk

#### Microsoft Defender Incident Alerts
The following analytic is to leverage alerts from Microsoft Defender O365 Incidents. This query aggregates and summar...
**Categories:** false_positive, splunk

#### Microsoft Defender Tamper Protection Trigger
Detects blocked attempts to change any of Defender's settings such as "Real Time Monitoring" and "Behavior Monitoring...
**Categories:** false_positive, T1562.001, sigma

#### Microsoft Malware Protection Engine Crash
This rule detects a suspicious crash of the Microsoft Malware Protection Engine (Level: high, Status: test)
**Categories:** false_positive, T1211, T1562.001, sigma

#### Microsoft Malware Protection Engine Crash - WER
This rule detects a suspicious crash of the Microsoft Malware Protection Engine (Level: high, Status: test)
**Categories:** false_positive, T1211, T1562.001, sigma

#### Mimikatz DC Sync
Detects Mimikatz DC sync security events (Level: high, Status: test)
**Categories:** false_positive, T1003.006, sigma

#### Mimikatz PassTheTicket CommandLine Parameters
The following analytic detects the use of Mimikatz command line parameters associated with pass-the-ticket attacks. I...
**Categories:** false_positive, T1550.003, splunk

#### Mimikatz Use
This method detects mimikatz keywords in different Eventlogs (some of them only appear in older Mimikatz version that...
**Categories:** false_positive, T1003.002, T1003.004, T1003.001, T1003.006, sigma

#### Mmc LOLBAS Execution Process Spawn
The following analytic identifies `mmc.exe` spawning a LOLBAS execution process. It leverages data from Endpoint Dete...
**Categories:** false_positive, T1021.003, T1218.014, splunk

#### Modification Of Wallpaper
The following analytic detects the modification of registry keys related to the desktop wallpaper settings. It levera...
**Categories:** false_positive, T1491, splunk

#### Modify ACL permission To Files Or Folder
The following analytic detects the modification of ACL permissions to files or folders, making them accessible to eve...
**Categories:** false_positive, T1222, splunk

#### Monitor Registry Keys for Print Monitors
The following analytic detects modifications to the registry key `HKLM\SYSTEM\CurrentControlSet\Control\Print\Monitor...
**Categories:** false_positive, T1547.010, splunk

#### MOVEit Certificate Store Access Failure
This detection identifies potential exploitation attempts of the CVE-2024-5806 vulnerability in Progress MOVEit Trans...
**Categories:** false_positive, T1190, splunk

#### MOVEit Empty Key Fingerprint Authentication Attempt
This detection identifies attempts to authenticate with an empty public key fingerprint in Progress MOVEit Transfer,...
**Categories:** false_positive, T1190, splunk

#### MS Exchange Mailbox Replication service writing Active Server Pages
The following analytic identifies the creation of suspicious .aspx files in specific directories associated with Exch...
**Categories:** false_positive, T1133, T1190, T1505.003, splunk

#### MS Scripting Process Loading Ldap Module
The following analytic detects the execution of MS scripting processes (wscript.exe or cscript.exe) loading LDAP-rela...
**Categories:** false_positive, T1059.007, splunk

#### MS Scripting Process Loading WMI Module
The following analytic detects the loading of WMI modules by Microsoft scripting processes like wscript.exe or cscrip...
**Categories:** false_positive, T1059.007, splunk

#### MSBuild Suspicious Spawned By Script Process
The following analytic detects the suspicious spawning of MSBuild.exe by Windows Script Host processes (cscript.exe o...
**Categories:** false_positive, T1127.001, splunk

#### MSExchange Transport Agent Installation - Builtin
Detects the Installation of a Exchange Transport Agent (Level: medium, Status: test)
**Categories:** false_positive, T1505.002, sigma

#### Mshta spawning Rundll32 OR Regsvr32 Process
The following analytic detects a suspicious mshta.exe process spawning rundll32 or regsvr32 child processes. It lever...
**Categories:** false_positive, T1218.005, splunk

#### MSI Installation From Suspicious Locations
Detects MSI package installation from suspicious locations (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### MSI Module Loaded by Non-System Binary
The following analytic detects the loading of `msi.dll` by a binary not located in `system32`, `syswow64`, `winsxs`,...
**Categories:** false_positive, T1574.001, splunk

#### Msmpeng Application DLL Side Loading
The following analytic detects the suspicious creation of msmpeng.exe or mpsvc.dll in non-default Windows Defender fo...
**Categories:** false_positive, T1574.001, splunk

#### MSSQL Add Account To Sysadmin Role
Detects when an attacker tries to backdoor the MSSQL server by adding a backdoor account to the sysadmin fixed server...
**Categories:** false_positive, sigma

#### MSSQL Destructive Query
Detects the invocation of MS SQL transactions that are destructive towards table or database data, such as "DROP TABL...
**Categories:** false_positive, T1485, sigma

#### MSSQL Disable Audit Settings
Detects when an attacker calls the "ALTER SERVER AUDIT" or "DROP SERVER AUDIT" transaction in order to delete or disa...
**Categories:** false_positive, sigma

#### MSSQL Server Failed Logon
Detects failed logon attempts from clients to MSSQL server. (Level: low, Status: test)
**Categories:** false_positive, T1110, sigma

#### MSSQL SPProcoption Set
Detects when the a stored procedure is set or cleared for automatic execution in MSSQL. A stored procedure that is se...
**Categories:** false_positive, sigma

#### MSSQL XPCmdshell Option Change
Detects when the MSSQL "xp_cmdshell" stored procedure setting is changed. (Level: high, Status: test)
**Categories:** false_positive, sigma

#### NET Profiler UAC bypass
The following analytic detects modifications to the registry aimed at bypassing the User Account Control (UAC) featur...
**Categories:** false_positive, T1548.002, splunk

#### NetSupport Manager Service Install
Detects NetSupport Manager service installation on the target system. (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Network Connection Discovery With Arp
The following analytic detects the execution of `arp.exe` with the `-a` flag, which is used to list network connectio...
**Categories:** false_positive, T1049, splunk

#### Network Connection Discovery With Netstat
The following analytic detects the execution of `netstat.exe` with command-line arguments to list network connections...
**Categories:** false_positive, T1049, splunk

#### Network Discovery Using Route Windows App
The following analytic detects the execution of the `route.exe` Windows application, commonly used for network discov...
**Categories:** false_positive, T1016.001, splunk

#### Network Share Discovery Via Dir Command
The following analytic detects access to Windows administrative SMB shares (Admin$, IPC$, C$) using the 'dir' command...
**Categories:** false_positive, T1135, splunk

#### Network Traffic to Active Directory Web Services Protocol
The following analytic identifies network traffic directed to the Active Directory Web Services Protocol (ADWS) on po...
**Categories:** false_positive, T1069.001, T1069.002, T1087.001, T1087.002, T1482, splunk

#### New BITS Job Created Via Bitsadmin
Detects the creation of a new bits job by Bitsadmin (Level: low, Status: test)
**Categories:** false_positive, T1197, sigma

#### New BITS Job Created Via PowerShell
Detects the creation of a new bits job by PowerShell (Level: low, Status: test)
**Categories:** false_positive, T1197, sigma

#### New Custom Shim Database Created
Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by applicati...
**Categories:** false_positive, T1547.009, sigma

#### New Firewall Rule Added In Windows Firewall Exception List Via WmiPrvSE.EXE
Detects the addition of a new "Allow" firewall rule by the WMI process (WmiPrvSE.EXE).
This can occur if an attacker...
**Categories:** false_positive, T1562.004, sigma

#### New Module Module Added To IIS Server
Detects the addition of a new module to an IIS server. (Level: medium, Status: test)
**Categories:** false_positive, T1562.002, T1505.004, sigma

#### New Outlook Macro Created
Detects the creation of a macro file for Outlook. (Level: medium, Status: test)
**Categories:** false_positive, T1137, T1008, T1546, sigma

#### New PDQDeploy Service - Client Side
Detects PDQDeploy service installation on the target system.
When a package is deployed via PDQDeploy it installs a r...
**Categories:** false_positive, T1543.003, sigma

#### New PDQDeploy Service - Server Side
Detects a PDQDeploy service installation which indicates that PDQDeploy was installed on the machines.
PDQDeploy can...
**Categories:** false_positive, T1543.003, sigma

#### Nishang PowershellTCPOneLine
The following analytic detects the use of the Nishang Invoke-PowerShellTCPOneLine utility, which initiates a callback...
**Categories:** false_positive, T1059.001, splunk

#### NLTest Domain Trust Discovery
The following analytic identifies the execution of `nltest.exe` with command-line arguments `/domain_trusts` or `/all...
**Categories:** false_positive, T1482, splunk

#### Non Chrome Process Accessing Chrome Default Dir
The following analytic detects a non-Chrome process accessing files in the Chrome user default folder. It leverages W...
**Categories:** false_positive, T1555.003, splunk

#### Non Firefox Process Access Firefox Profile Dir
The following analytic detects non-Firefox processes accessing the Firefox profile directory, which contains sensitiv...
**Categories:** false_positive, T1555.003, splunk

#### Notepad with no Command Line Arguments
The following analytic identifies instances where Notepad.exe is launched without any command line arguments, a behav...
**Categories:** false_positive, T1055, splunk

#### Notepad++ Updater DNS Query to Uncommon Domains
Detects when the Notepad++ updater (gup.exe) makes DNS queries to domains that are not part of the known legitimate u...
**Categories:** false_positive, T1195.002, T1557, sigma

#### Ntdsutil Abuse
Detects potential abuse of ntdsutil to dump ntds.dit database (Level: medium, Status: test)
**Categories:** false_positive, T1003.003, sigma

#### Ntdsutil Export NTDS
The following analytic detects the use of Ntdsutil to export the Active Directory database (NTDS.dit). It leverages d...
**Categories:** false_positive, T1003.003, splunk

#### NTLM Brute Force
Detects common NTLM brute force device names (Level: medium, Status: test)
**Categories:** false_positive, T1110, sigma

#### NTLM Logon
Detects logons using NTLM, which could be caused by a legacy source or attackers (Level: low, Status: test)
**Categories:** false_positive, T1550.002, sigma

#### NTLMv1 Logon Between Client and Server
Detects the reporting of NTLMv1 being used between a client and server. NTLMv1 is insecure as the underlying encrypti...
**Categories:** false_positive, T1550.002, sigma

#### Office Macro File Creation
Detects the creation of a new office macro files on the systems (Level: low, Status: test)
**Categories:** false_positive, T1566.001, sigma

#### Office Macro File Download
Detects the creation of a new office macro files on the system via an application (browser, mail client).
This can he...
**Categories:** false_positive, T1566.001, sigma

#### OneNote Attachment File Dropped In Suspicious Location
Detects creation of files with the ".one"/".onepkg" extension in suspicious or uncommon locations. This could be a si...
**Categories:** false_positive, sigma

#### OpenSSH Server Listening On Socket
Detects scenarios where an attacker enables the OpenSSH server and server starts to listening on SSH socket. (Level:...
**Categories:** false_positive, T1021.004, sigma

#### Outbound Network Connection from Java Using Default Ports
The following analytic detects outbound network connections from Java processes to default ports used by LDAP and RMI...
**Categories:** false_positive, T1190, T1133, splunk

#### Outgoing Logon with New Credentials
Detects logon events that specify new credentials (Level: low, Status: test)
**Categories:** false_positive, T1550, sigma

#### Overwriting Accessibility Binaries
The following analytic detects modifications to Windows accessibility binaries such as sethc.exe, utilman.exe, osk.ex...
**Categories:** false_positive, T1546.008, splunk

#### PaperCut NG Suspicious Behavior Debug Log
The following analytic identifies potential exploitation attempts on a PaperCut NG server by analyzing its debug log...
**Categories:** false_positive, T1190, T1133, splunk

#### Pass the Hash Activity 2
Detects the attack technique pass the hash which is used to move laterally inside the network (Level: medium, Status:...
**Categories:** false_positive, T1550.002, sigma

#### Password Change on Directory Service Restore Mode (DSRM) Account
Detects potential attempts made to set the Directory Services Restore Mode administrator password.
The Directory Serv...
**Categories:** false_positive, T1098, sigma

#### Password Dumper Remote Thread in LSASS
Detects password dumper activity by monitoring remote thread creation EventID 8 in combination with the lsass.exe pro...
**Categories:** false_positive, T1003.001, sigma

#### Password Protected ZIP File Opened
Detects the extraction of password protected ZIP archives. See the filename variable for more details on which file h...
**Categories:** false_positive, T1027, sigma

#### Password Protected ZIP File Opened (Email Attachment)
Detects the extraction of password protected ZIP archives. See the filename variable for more details on which file h...
**Categories:** false_positive, T1027, T1566.001, sigma

#### Password Protected ZIP File Opened (Suspicious Filenames)
Detects the extraction of password protected ZIP archives with suspicious file names. See the filename variable for m...
**Categories:** false_positive, T1027, T1105, T1036, sigma

#### Permission Modification using Takeown App
The following analytic detects the modification of file or directory permissions using the takeown.exe Windows applic...
**Categories:** false_positive, T1222, splunk

#### Persistence and Execution at Scale via GPO Scheduled Task
Detect lateral movement using GPO scheduled task, usually used to deploy ransomware at scale (Level: high, Status: test)
**Categories:** false_positive, T1053.005, sigma

#### PetitPotam Network Share Access Request
The following analytic detects network share access requests indicative of the PetitPotam attack (CVE-2021-36942). It...
**Categories:** false_positive, T1187, splunk

#### PetitPotam Suspicious Kerberos TGT Request
Detect suspicious Kerberos TGT requests.
Once an attacer obtains a computer certificate by abusing Active Directory C...
**Categories:** false_positive, T1187, sigma

#### Ping Sleep Batch Command
The following analytic identifies the execution of ping sleep batch commands.
It leverages data from Endpoint Detecti...
**Categories:** false_positive, T1497.003, splunk

#### Possible Browser Pass View Parameter
The following analytic identifies processes with command-line parameters associated with web browser credential dumpi...
**Categories:** false_positive, T1555.003, splunk

#### Possible DC Shadow Attack
Detects DCShadow via create new SPN (Level: medium, Status: test)
**Categories:** false_positive, T1207, sigma

#### Possible Lateral Movement PowerShell Spawn
The following analytic detects the spawning of a PowerShell process as a child or grandchild of commonly abused proce...
**Categories:** false_positive, T1021.003, T1021.006, T1047, T1053.005, T1059.001, T1218.014, T1543.003, splunk

#### Possible PetitPotam Coerce Authentication Attempt
Detect PetitPotam coerced authentication activity. (Level: high, Status: test)
**Categories:** false_positive, T1187, sigma

#### Possible Shadow Credentials Added
Detects possible addition of shadow credentials to an active directory object. (Level: high, Status: test)
**Categories:** false_positive, T1556, sigma

#### Potential Access Token Abuse
Detects potential token impersonation and theft. Example, when using "DuplicateToken(Ex)" and "ImpersonateLoggedOnUse...
**Categories:** false_positive, T1134.001, sigma

#### Potential AD User Enumeration From Non-Machine Account
Detects read access to a domain user from a non-machine account (Level: medium, Status: test)
**Categories:** false_positive, T1087.002, sigma

#### Potential AS-REP Roasting via Kerberos TGT Requests
Detects suspicious Kerberos TGT requests with pre-authentication disabled (Pre-Authentication Type = 0) and Ticket En...
**Categories:** false_positive, sigma

#### Potential Binary Or Script Dropper Via PowerShell
Detects PowerShell creating a binary executable or a script file. (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Potential Malicious AppX Package Installation Attempts
Detects potential installation or installation attempts of known malicious appx packages (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Potential password in username
The following analytic identifies instances where users may have mistakenly entered their passwords in the username f...
**Categories:** false_positive, T1078.003, T1552.001, splunk

#### Potential Persistence Via Microsoft Office Add-In
Detects potential persistence activity via startup add-ins that load when Microsoft Office starts (.wll/.xll are simp...
**Categories:** false_positive, T1137.006, sigma

#### Potential Persistence Via Microsoft Office Startup Folder
Detects creation of Microsoft Office files inside of one of the default startup folders in order to achieve persisten...
**Categories:** false_positive, T1137, sigma

#### Potential Persistence Via Notepad++ Plugins
Detects creation of new ".dll" files inside the plugins directory of a notepad++ installation by a process other than...
**Categories:** false_positive, sigma

#### Potential Persistence Via Outlook Form
Detects the creation of a new Outlook form which can contain malicious code (Level: high, Status: test)
**Categories:** false_positive, T1137.003, sigma

#### Potential Privileged System Service Operation - SeLoadDriverPrivilege
Detects the usage of the 'SeLoadDriverPrivilege' privilege. This privilege is required to load or unload a device dri...
**Categories:** false_positive, T1562.001, sigma

#### Potential Remote Desktop Connection to Non-Domain Host
Detects logons using NTLM to hosts that are potentially not part of the domain. (Level: medium, Status: test)
**Categories:** false_positive, T1219.002, sigma

#### Potential SAM Database Dump
Detects the creation of files that look like exports of the local SAM (Security Account Manager) (Level: high, Status...
**Categories:** false_positive, T1003.002, sigma

#### Potential Secure Deletion with SDelete
Detects files that have extensions commonly seen while SDelete is used to wipe files. (Level: medium, Status: test)
**Categories:** false_positive, T1070.004, T1027.005, T1485, T1553.002, sigma

#### Potential Startup Shortcut Persistence Via PowerShell.EXE
Detects PowerShell writing startup shortcuts.
This procedure was highlighted in Red Canary Intel Insights Oct. 2021,...
**Categories:** false_positive, T1547.001, sigma

#### Potential Suspicious PowerShell Module File Created
Detects the creation of a new PowerShell module in the first folder of the module directory structure "\WindowsPowerS...
**Categories:** false_positive, sigma

#### Potential System Network Configuration Discovery Activity
The following analytic identifies the rapid execution of processes used for system network configuration discovery on...
**Categories:** false_positive, T1016, splunk

#### Potential Telegram API Request Via CommandLine
The following analytic detects the presence of "api.telegram.org" in the CommandLine of a process. It leverages data...
**Categories:** false_positive, T1102.002, T1041, splunk

#### Potentially Suspicious AccessMask Requested From LSASS
Detects process handle on LSASS process with certain access mask (Level: medium, Status: test)
**Categories:** false_positive, T1003.001, sigma

#### Potentially Suspicious DMP/HDMP File Creation
Detects the creation of a file with the ".dmp"/".hdmp" extension by a shell or scripting application such as "cmd", "...
**Categories:** false_positive, sigma

#### Potentially Suspicious File Creation by OpenEDR's ITSMService
Detects the creation of potentially suspicious files by OpenEDR's ITSMService process.
The ITSMService is responsible...
**Categories:** false_positive, T1105, T1570, T1219, sigma

#### Potentially Suspicious File Download From ZIP TLD
Detects the download of a file with a potentially suspicious extension from a .zip top level domain. (Level: high, St...
**Categories:** false_positive, sigma

#### PowerShell - Connect To Internet With Hidden Window
The following analytic detects PowerShell commands using the WindowStyle parameter to hide the window while connectin...
**Categories:** false_positive, T1059.001, splunk

#### PowerShell 4104 Hunting
The following analytic identifies suspicious PowerShell execution using Script Block Logging (EventCode 4104). It lev...
**Categories:** false_positive, T1059.001, splunk

#### Powershell COM Hijacking InprocServer32 Modification
The following analytic detects attempts to modify or add a Component Object Model (COM) entry to the InProcServer32 p...
**Categories:** false_positive, T1059.001, T1546.015, splunk

#### Powershell Creating Thread Mutex
The following analytic detects the execution of PowerShell scripts using the `mutex` function via EventCode 4104. Thi...
**Categories:** false_positive, T1027.005, T1059.001, splunk

#### Powershell Disable Security Monitoring
The following analytic identifies attempts to disable Windows Defender
real-time behavior monitoring via PowerShell c...
**Categories:** false_positive, T1562.001, splunk

#### PowerShell Domain Enumeration
The following analytic detects the execution of PowerShell commands used for domain enumeration, such as `get-netdoma...
**Categories:** false_positive, T1059.001, splunk

#### PowerShell Enable PowerShell Remoting
The following analytic detects the use of the Enable-PSRemoting cmdlet, which allows PowerShell remoting on a local o...
**Categories:** false_positive, T1059.001, splunk

#### Powershell Enable SMB1Protocol Feature
The following analytic detects the enabling of the SMB1 protocol via `powershell.exe`. It leverages PowerShell script...
**Categories:** false_positive, T1027.005, splunk

#### Powershell Execute COM Object
The following analytic detects the execution of a COM CLSID through PowerShell. It leverages EventCode 4104 and searc...
**Categories:** false_positive, T1059.001, T1546.015, splunk

#### PowerShell Module File Created
Detects the creation of a new PowerShell module ".psm1", ".psd1", ".dll", ".ps1", etc. (Level: low, Status: test)
**Categories:** false_positive, sigma

#### PowerShell Script Dropped Via PowerShell.EXE
Detects PowerShell creating a PowerShell file (.ps1). While often times this behavior is benign, sometimes it can be...
**Categories:** false_positive, sigma

#### Powerview Add-DomainObjectAcl DCSync AD Extend Right
Backdooring domain object to grant the rights associated with DCSync to a regular user or machine account using Power...
**Categories:** false_positive, T1098, sigma

#### Previously Installed IIS Module Was Removed
Detects the removal of a previously installed IIS module. (Level: low, Status: test)
**Categories:** false_positive, T1562.002, T1505.004, sigma

#### Process Deletion of Its Own Executable
Detects the deletion of a process's executable by itself. This is usually not possible without workarounds and may be...
**Categories:** false_positive, sigma

#### PUA - Process Hacker Driver Load
Detects driver load of the Process Hacker tool (Level: high, Status: test)
**Categories:** false_positive, T1543, sigma

#### PUA - System Informer Driver Load
Detects driver load of the System Informer tool (Level: medium, Status: test)
**Categories:** false_positive, T1543, sigma

#### Publisher Attachment File Dropped In Suspicious Location
Detects creation of files with the ".pub" extension in suspicious or uncommon locations. This could be a sign of atta...
**Categories:** false_positive, sigma

#### Rare Remote Thread Creation By Uncommon Source Image
Detects uncommon processes creating remote threads. (Level: high, Status: test)
**Categories:** false_positive, T1055, sigma

#### Rclone Config File Creation
Detects Rclone config files being created (Level: medium, Status: test)
**Categories:** false_positive, T1567.002, sigma

#### RDP over Reverse SSH Tunnel WFP
Detects svchost hosting RDP termsvcs communicating with the loopback address (Level: high, Status: test)
**Categories:** false_positive, T1090.001, T1090.002, T1021.001, sigma

#### Reconnaissance Activity
Detects activity as "net user administrator /domain" and "net group domain admins /domain" (Level: high, Status: test)
**Categories:** false_positive, T1087.002, T1069.002, sigma

#### Relevant Anti-Virus Signature Keywords In Application Log
Detects potentially highly relevant antivirus events in the application log based on known virus signature names and...
**Categories:** false_positive, T1588, sigma

#### Remote Access Tool - ScreenConnect Command Execution
Detects command execution via ScreenConnect RMM (Level: low, Status: test)
**Categories:** false_positive, T1059.003, sigma

#### Remote Access Tool - ScreenConnect File Transfer
Detects file being transferred via ScreenConnect RMM (Level: low, Status: test)
**Categories:** false_positive, T1059.003, sigma

#### Remote Access Tool - ScreenConnect Temporary File
Detects the creation of files in a specific location by ScreenConnect RMM.
ScreenConnect has feature to remotely exec...
**Categories:** false_positive, T1059.003, sigma

#### Remote Access Tool Services Have Been Installed - Security
Detects service installation of different remote access tools software. These software are often abused by threat act...
**Categories:** false_positive, T1543.003, T1569.002, sigma

#### Remote AppX Package Downloaded from File Sharing or CDN Domain
Detects an appx package that was added to the pipeline of the "to be processed" packages which was downloaded from a...
**Categories:** false_positive, sigma

#### Remote PowerShell Sessions Network Connections (WinRM)
Detects basic PowerShell Remoting (WinRM) by monitoring for network inbound connections to ports 5985 OR 5986 (Level:...
**Categories:** false_positive, T1059.001, sigma

#### Remote Thread Creation By Uncommon Source Image
Detects uncommon processes creating remote threads. (Level: medium, Status: test)
**Categories:** false_positive, T1055, sigma

#### Remote Utilities Host Service Install
Detects Remote Utilities Host service installation on the target system. (Level: medium, Status: test)
**Categories:** false_positive, sigma

#### Scheduled Task Executed Uncommon LOLBIN
Detects the execution of Scheduled Tasks where the program being run is located in a suspicious location or where it...
**Categories:** false_positive, T1053.005, sigma

#### SCR File Write Event
Detects the creation of screensaver files (.scr) outside of system folders. Attackers may execute an application as a...
**Categories:** false_positive, T1218.011, sigma

#### ScreenConnect Temporary Installation Artefact
An adversary may use legitimate desktop support and remote access software, such as Team Viewer, Go2Assist, LogMein,...
**Categories:** false_positive, T1219.002, sigma

#### Security Eventlog Cleared
One of the Windows Eventlogs has been cleared. e.g. caused by "wevtutil cl" command execution (Level: high, Status: t...
**Categories:** false_positive, T1070.001, sigma

#### Service Registry Key Read Access Request
Detects "read access" requests on the services registry key.
Adversaries may execute their own malicious payloads by...
**Categories:** false_positive, T1574.011, sigma

#### Standard User In High Privileged Group
Detect standard users login that are part of high privileged groups such as the Administrator group (Level: medium, S...
**Categories:** false_positive, sigma

#### Startup Folder File Write
A General detection for files being created in the Windows startup directory. This could be an indicator of persisten...
**Categories:** false_positive, T1547.001, sigma

#### Startup/Logon Script Added to Group Policy Object
Detects the modification of Group Policy Objects (GPO) to add a startup/logon script to users or computer objects. (L...
**Categories:** false_positive, T1484.001, T1547, sigma

#### Successful Account Login Via WMI
Detects successful logon attempts performed with WMI (Level: low, Status: stable)
**Categories:** false_positive, T1047, sigma

#### Successful Overpass the Hash Attempt
Detects successful logon with logon type 9 (NewCredentials) which matches the Overpass the Hash behavior of e.g Mimik...
**Categories:** false_positive, T1550.002, sigma

#### Suspicious Access to Sensitive File Extensions
Detects known sensitive file extensions accessed on a network share (Level: medium, Status: test)
**Categories:** false_positive, T1039, sigma

#### Suspicious Application Installed
Detects suspicious application installed by looking at the added shortcut to the app resolver cache (Level: medium, S...
**Categories:** false_positive, sigma

#### Suspicious Deno File Written from Remote Source
Detects Deno writing a file from a direct HTTP(s) call and writing to the appdata folder or bringing it's own malicio...
**Categories:** false_positive, T1204, T1059.007, T1105, sigma

#### Suspicious Desktopimgdownldr Target File
Detects a suspicious Microsoft desktopimgdownldr file creation that stores a file to a suspicious location or contain...
**Categories:** false_positive, T1105, sigma

#### Suspicious DNS Query for IP Lookup Service APIs
Detects DNS queries for IP lookup services such as "api.ipify.org" originating from a non browser process. (Level: me...
**Categories:** false_positive, T1590, sigma

#### Suspicious DotNET CLR Usage Log Artifact
Detects the creation of Usage Log files by the CLR (clr.dll). These files are named after the executing process once...
**Categories:** false_positive, T1218, sigma

#### Suspicious File Access to Browser Credential Storage
Detects file access to browser credential storage paths by non-browser processes, which may indicate credential acces...
**Categories:** false_positive, T1555.003, T1217, sigma

#### Suspicious File Created in Outlook Temporary Directory
Detects the creation of files with suspicious file extensions in the temporary directory that Outlook uses when openi...
**Categories:** false_positive, T1566.001, sigma

#### Suspicious File Created Via OneNote Application
Detects suspicious files created via the OneNote application. This could indicate a potential malicious ".one"/".onep...
**Categories:** false_positive, sigma

#### Suspicious File Download From File Sharing Websites -  File Stream
Detects the download of suspicious file type from a well-known file and paste sharing domain (Level: high, Status: test)
**Categories:** false_positive, T1564.004, sigma

#### Suspicious Kerberos RC4 Ticket Encryption
Detects service ticket requests using RC4 encryption type (Level: medium, Status: test)
**Categories:** false_positive, T1558.003, sigma

#### Suspicious LDAP-Attributes Used
Detects the usage of particular AttributeLDAPDisplayNames, which are known for data exchange via LDAP by the tool LDA...
**Categories:** false_positive, T1001.003, sigma

#### Suspicious Rejected SMB Guest Logon From IP
Detect Attempt PrintNightmare (CVE-2021-1675) Remote code execution in Windows Spooler Service (Level: medium, Status...
**Categories:** false_positive, T1110.001, sigma

#### Suspicious Remote Logon with Explicit Credentials
Detects suspicious processes logging on with explicit credentials (Level: medium, Status: test)
**Categories:** false_positive, T1078, sigma

#### Sysinternals Tools AppX Versions Execution
Detects execution of Sysinternals tools via an AppX package.
Attackers could install the Sysinternals Suite to get ac...
**Categories:** false_positive, sigma

#### TacticalRMM Service Installation
Detects a TacticalRMM service installation. Tactical RMM is a remote monitoring & management tool. (Level: medium, St...
**Categories:** false_positive, T1219.002, sigma

#### Tap Driver Installation
Well-known TAP software installation. Possible preparation for data exfiltration using tunnelling techniques (Level:...
**Categories:** false_positive, T1048, sigma

#### Tap Driver Installation - Security
Detects the installation of a well-known TAP driver service. This could be a sign of potential preparation for data e...
**Categories:** false_positive, T1048, sigma

#### TeamViewer Domain Query By Non-TeamViewer Application
Detects DNS queries to a TeamViewer domain only resolved by a TeamViewer client by an image that isn't named TeamView...
**Categories:** false_positive, T1219.002, sigma

#### Tomcat WebServer Logs Deleted
Detects the deletion of tomcat WebServer logs which may indicate an attempt to destroy forensic evidence (Level: medi...
**Categories:** false_positive, T1070, sigma

#### Transferring Files with Credential Data via Network Shares
Transferring files with well-known filenames (sensitive files with credential data) using network shares (Level: medi...
**Categories:** false_positive, T1003.002, T1003.001, T1003.003, sigma

#### Unauthorized System Time Modification
Detect scenarios where a potentially unauthorized application or user is modifying the system time. (Level: low, Stat...
**Categories:** false_positive, T1070.006, sigma

#### Uncommon File Created by Notepad++ Updater Gup.EXE
Detects when the Notepad++ updater (gup.exe) creates files in suspicious or uncommon locations.
This could indicate p...
**Categories:** false_positive, T1195.002, T1557, sigma

#### Uncommon File Created In Office Startup Folder
Detects the creation of a file with an uncommon extension in an Office application startup folder (Level: high, Statu...
**Categories:** false_positive, T1587.001, sigma

#### Uncommon Outbound Kerberos Connection - Security
Detects uncommon outbound network activity via Kerberos default port indicating possible lateral movement or first st...
**Categories:** false_positive, T1558.003, sigma

#### Unsigned or Unencrypted SMB Connection to Share Established
Detects SMB server connections to shares without signing or encryption enabled.
This could indicate potential lateral...
**Categories:** false_positive, T1021.002, sigma

#### USB Device Plugged
Detects plugged/unplugged USB devices (Level: low, Status: test)
**Categories:** false_positive, T1200, sigma

#### User Added to Local Administrator Group
Detects the addition of a new member to the local administrator group, which could be legitimate activity or a sign o...
**Categories:** false_positive, T1078, T1098, sigma

#### Volume Shadow Copy Mount
Detects volume shadow copy mount via Windows event log (Level: low, Status: test)
**Categories:** false_positive, T1003.002, sigma

#### VSSAudit Security Event Source Registration
Detects the registration of the security event source VSSAudit. It would usually trigger when volume shadow copy oper...
**Categories:** false_positive, T1003.002, sigma

#### Vulnerable Driver Load By Name
Detects the load of known vulnerable drivers via the file name of the drivers. (Level: low, Status: test)
**Categories:** false_positive, T1543.003, T1068, sigma

#### Win Defender Restored Quarantine File
Detects the restoration of files from the defender quarantine (Level: high, Status: test)
**Categories:** false_positive, T1562.001, sigma

#### WinDivert Driver Load
Detects the load of the Windiver driver, a powerful user-mode capture/sniffing/modification/blocking/re-injection pac...
**Categories:** false_positive, T1599.001, T1557.001, sigma

#### Windows AppX Deployment Full Trust Package Installation
Detects the installation of MSIX/AppX packages with full trust privileges which run with elevated privileges outside...
**Categories:** false_positive, T1204.002, T1553.005, sigma

#### Windows AppX Deployment Unsigned Package Installation
Detects attempts to install unsigned MSIX/AppX packages using the -AllowUnsigned parameter via AppXDeployment-Server...
**Categories:** false_positive, T1204.002, T1553.005, sigma

#### Windows Default Domain GPO Modification
Detects modifications to Default Domain or Default Domain Controllers Group Policy Objects (GPOs).
Adversaries may mo...
**Categories:** false_positive, T1484.001, sigma

#### Windows Defender Configuration Changes
Detects suspicious changes to the Windows Defender configuration (Level: high, Status: stable)
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Exclusion List Modified
Detects modifications to the Windows Defender exclusion registry key. This could indicate a potentially suspicious or...
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Exclusions Added
Detects the Setting of Windows Defender Exclusions (Level: medium, Status: stable)
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Malware Detection History Deletion
Windows Defender logs when the history of detected infections is deleted. (Level: informational, Status: test)
**Categories:** false_positive, sigma

#### Windows Defender Real-time Protection Disabled
Detects disabling of Windows Defender Real-time Protection. As this event doesn't contain a lot of information on who...
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Real-Time Protection Failure/Restart
Detects issues with Windows Defender Real-Time Protection features (Level: medium, Status: stable)
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Submit Sample Feature Disabled
Detects disabling of the "Automatic Sample Submission" feature of Windows Defender. (Level: low, Status: stable)
**Categories:** false_positive, T1562.001, sigma

#### Windows Defender Threat Detection Service Disabled
Detects when the "Windows Defender Threat Protection" service is disabled. (Level: medium, Status: stable)
**Categories:** false_positive, T1562.001, sigma

#### Windows Network Access Suspicious desktop.ini Action
Detects unusual processes accessing desktop.ini remotely over network share, which can be leveraged to alter how Expl...
**Categories:** false_positive, T1547.009, sigma

#### Windows Service Terminated With Error
Detects Windows services that got terminated for whatever reason (Level: low, Status: test)
**Categories:** false_positive, sigma

#### WMI Persistence
Detects suspicious WMI event filter and command line event consumer based on WMI and Security Logs. (Level: medium, S...
**Categories:** false_positive, T1546.003, sigma

#### WMI Persistence - Security
Detects suspicious WMI event filter and command line event consumer based on WMI and Security Logs. (Level: medium, S...
**Categories:** false_positive, T1546.003, sigma
