# DFIR & Blue Team
> Source: HackTools | Entries: 30 | Platform: cross_platform


## Index

- [AD Reporting](#ad-reporting)
- [Blue Team](#blue-team)
- [DFIR](#dfir)
- [macos_security](#macossecurity)
- [network_monitoring](#networkmonitoring)


### AD Reporting

#### PlumHound
Reporting engine that operates on BloodHound Neo4j data to generate actionable reports, dashboards, and prioritized f...
**Categories:** AD Reporting, BloodHound Analytics, Security Assessment, Graph Analysis, Blue Team
```
python3 PlumHound.py --easy -p neo4j_password
```

### Blue Team

#### Cortex
Observable analysis and active response engine that provides automated enrichment of indicators of compromise through...
**Categories:** Blue Team, SOC, Threat Intelligence, SOAR
```
docker-compose up -d cortex
```

#### Elastic SIEM
Security information and event management solution built on the Elastic Stack (Elasticsearch, Kibana, Beats, Logstash...
**Categories:** Blue Team, SIEM, SOC, Detection, Threat Hunting
```
filebeat setup -e --modules system,auditd
```

#### MISP
Malware Information Sharing Platform - open-source threat intelligence platform for collecting, storing, distributing...
**Categories:** Blue Team, Threat Intelligence, Information Sharing, SOC
```
curl -XPOST https://misp/events/add -H 'Authorization: API_KEY' -H 'Content-Type: application/json' -d '{"Event":{"info":"Incident","distribution":0}}'
```

#### OpenCTI
Open Cyber Threat Intelligence platform that provides structured storage, visualization, and analysis of threat intel...
**Categories:** Blue Team, Threat Intelligence, SOC, CTI
```
docker-compose up -d (deploy full OpenCTI stack)
```

#### OSQuery
Operating system instrumentation framework that exposes OS internals as a relational database queryable with SQL, ena...
**Categories:** Blue Team, Endpoint Detection, Monitoring, Threat Hunting
```
osqueryi "SELECT pid, name, cmdline, uid FROM processes WHERE name = 'sshd';"
```

#### RITA
Real Intelligence Threat Analytics - network traffic analysis framework that identifies command-and-control (C2) beac...
**Categories:** Blue Team, Network Security, Threat Hunting, Detection
```
rita import /opt/zeek/logs/2024-01-15/ --database case001
```

#### Security Onion
All-in-one network security monitoring and log management platform that integrates Suricata, Zeek, Elasticsearch, Kib...
**Categories:** Blue Team, SOC, Network Security, SIEM, NSM
```
sudo so-setup (initial setup wizard)
```

#### Sigma
Generic signature format for log-based detection rules that provides a vendor-agnostic way to describe suspicious act...
**Categories:** Blue Team, Detection, SIEM, Threat Hunting
```
sigma convert -t splunk -p splunk_windows rules/windows/process_creation/
```

#### Snort
Open-source network intrusion detection and prevention system (IDS/IPS) that performs real-time traffic analysis, pac...
**Categories:** Blue Team, Network Security, IDS/IPS, Detection
```
snort -c /etc/snort/snort.conf -i eth0 -A console
```

#### Splunk
Enterprise SIEM and data analytics platform that indexes machine-generated data from any source, providing search (SP...
**Categories:** Blue Team, SIEM, SOC, Log Analysis, Threat Hunting
```
splunk start (start Splunk daemon)
```

#### Suricata
High-performance network intrusion detection, prevention, and security monitoring engine that provides multi-threaded...
**Categories:** Blue Team, Network Security, IDS/IPS, Detection, NSM
```
suricata -c /etc/suricata/suricata.yaml -i eth0
```

#### Sysmon
Windows system monitoring service that logs detailed information about process creation, network connections, file ch...
**Categories:** Blue Team, Endpoint Detection, Telemetry, Monitoring
```
sysmon.exe -i sysmonconfig.xml -accepteula
```

#### TheHive
Security incident response platform providing case management, alert intake, task assignment, observable enrichment,...
**Categories:** Blue Team, SOC, Incident Response, Case Management
```
docker-compose -f docker-compose.yml up -d (deploy TheHive stack)
```

#### Wazuh
Open-source security monitoring platform providing endpoint detection, log analysis, file integrity monitoring, vulne...
**Categories:** Blue Team, SIEM, Endpoint Detection, Compliance, XDR
```
/var/ossec/bin/wazuh-control start
```

#### YARA
Pattern matching engine for malware identification and classification that uses rule-based descriptions to scan files...
**Categories:** Blue Team, Malware Analysis, Detection, Threat Hunting
```
yara rules.yar suspicious_file.exe
```

#### Zeek (Bro)
Network security monitoring framework that passively analyzes network traffic to produce detailed protocol logs, conn...
**Categories:** Blue Team, Network Security, NSM, Forensics
```
zeek -i eth0 local
```

### DFIR

#### Autopsy
Open-source digital forensics platform providing GUI-based disk image analysis, file recovery, timeline analysis, key...
**Categories:** DFIR, Forensics, Disk Forensics, Evidence Analysis
```
autopsy (launches GUI on port 9999 for Autopsy 2.x web interface)
```

#### Chainsaw
Rapid Windows forensic artifact search and threat hunting tool that applies Sigma rules and custom detection logic ag...
**Categories:** DFIR, Blue Team, Forensics, Threat Hunting, Log Analysis
```
chainsaw hunt evtx_logs/ -s sigma/rules/ --mapping mappings/sigma-event-logs-all.yml -o results.csv
```

#### DeepBlueCLI
PowerShell-based threat hunting tool that analyzes Windows Event Logs for indicators of compromise including credenti...
**Categories:** DFIR, Blue Team, Log Analysis, Threat Hunting, Detection
```
.\DeepBlue.ps1 .\evtx\security.evtx
```

#### GRR Rapid Response
Google's incident response framework for remote live forensics that enables large-scale artifact collection, file acq...
**Categories:** DFIR, Forensics, Incident Response, Endpoint Detection
```
grr_server --component admin_ui
```

#### Hayabusa
Windows event log fast forensics timeline generator and threat hunting tool written in Rust that applies Sigma-based...
**Categories:** DFIR, Blue Team, Log Analysis, Threat Hunting, Detection
```
hayabusa.exe csv-timeline -d C:\Windows\System32\winevt\Logs -o timeline.csv
```

#### KAPE
Kroll Artifact Parser and Extractor - triage collection and processing tool that rapidly acquires forensic artifacts...
**Categories:** DFIR, Forensics, Artifact Collection, Triage
```
kape.exe --tsource C: --tdest C:\ForensicOutput\target --target KapeTriage --vhdx YOURCASE
```

#### Plaso (log2timeline)
Super timeline creation engine that extracts timestamps from a wide variety of file formats, log files, and forensic...
**Categories:** DFIR, Forensics, Timeline Analysis, Log Analysis
```
log2timeline.py --storage-file timeline.plaso /path/to/image.E01
```

#### Velociraptor
Endpoint visibility and digital forensics platform that enables rapid artifact collection, threat hunting, and monito...
**Categories:** DFIR, Blue Team, Forensics, Endpoint Detection, Threat Hunting
```
velociraptor gui --datastore /opt/velociraptor/data
```

#### Volatility
Advanced memory forensics framework that extracts digital artifacts from volatile memory (RAM) dumps, enabling analys...
**Categories:** DFIR, Forensics, Memory Forensics, Malware Analysis
```
vol.py -f memory.dmp windows.pslist
```

### macos_security

#### KnockKnock
macOS persistence detection tool by Objective-See that enumerates all known persistence mechanisms on macOS to identi...
**Categories:** macos_security, persistence_detection, endpoint_security, forensics, threat_hunting
```
KnockKnock.app/Contents/MacOS/KnockKnock
```

#### OSXCollector
macOS forensic evidence collection and analysis tool that gathers system artifacts, browser data, startup items, and...
**Categories:** macos_security, forensics, incident_response, artifact_collection, threat_hunting
```
sudo python osxcollector.py
```

### network_monitoring

#### tcpdump
Command-line packet analyzer for capturing and displaying network traffic. Detectable through promiscuous mode activa...
**Categories:** network_monitoring, packet_capture, forensics
```
tcpdump -i eth0 -w capture.pcap -c 10000
```

#### Wireshark
Network protocol analyzer and packet capture tool providing deep inspection of hundreds of protocols. Detectable thro...
**Categories:** network_monitoring, packet_analysis, forensics
```
wireshark -i eth0 -k -w capture.pcapng
```
