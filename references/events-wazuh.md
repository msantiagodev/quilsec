# Wazuh Rule IDs
> Source: Wazuh Rules | Events: 145


**1** -- Generic template for all syslog rules.
  Generic template for all syslog rules.

**2** -- Generic template for all firewall rules.
  Generic template for all firewall rules.

**3** -- Generic template for all ids rules.
  Generic template for all ids rules.

**4** -- Generic template for all web rules.
  Generic template for all web rules.

**5** -- Generic template for all web proxy rules.
  Generic template for all web proxy rules.

**6** -- Generic template for all windows rules.
  Generic template for all windows rules.

**7** -- Generic template for all ossec rules.
  Generic template for all ossec rules.

**500** -- Grouping of ossec rules.
  Grouping of ossec rules.

**501** -- New ossec agent connected.
  New Wazuh agent connected - agent enrollment event. Monitor for unauthorized agents joining the cluster. Verify new a...

**502** -- Ossec server started.
  Wazuh server started. Service lifecycle event. Unexpected restarts may indicate stability issues or tampering.

**503** -- Ossec agent started.
  Wazuh agent started. Agent service lifecycle. Correlate with endpoint maintenance windows.

**504** -- Ossec agent disconnected.
  Wazuh agent disconnected - agent went offline. Investigate for agent tampering, endpoint compromise, or network issue...

**505** -- Ossec agent removed.
  Wazuh agent removed from manager. Verify through change management. Unauthorized removal may indicate attacker disabl...

**509** -- Rootcheck event.
  Rootcheck event - host-based rootkit detection scan results. Baseline event for rootcheck analysis.

**510** -- Host-based anomaly detection event (rootcheck).
  Host-based anomaly detection (rootcheck) - level 7. Active rootkit or system anomaly found. Investigate immediately f...

**511** -- Ignored common NTFS ADS entries.
  Ignored common NTFS ADS entries.

**512** -- Windows Audit event.
  Windows Audit event.

**513** -- Windows malware detected.
  Windows malware detected (rootcheck) - level 9. High-confidence malware detection via system integrity analysis. Requ...

**514** -- Windows application monitor event.
  Windows application monitor event.

**515** -- Ignoring scan messages.
  Ignoring scan messages.

**516** -- System Audit event.
  System Audit event.

**517** -- Syscheck Audit: $(extra_data)
  Syscheck Audit: $(extra_data)

**518** -- Windows Adware/Spyware application found.
  Windows Adware/Spyware detected (rootcheck) - level 9. Potentially unwanted software found. May indicate drive-by dow...

**519** -- System Audit: Vulnerable web application found.
  Vulnerable web application found (audit) - level 7. Known vulnerable web application identified. Assess exploitation...

**520** -- Trying to add an agent with duplicated IP.
  Trying to add an agent with duplicated IP.

**530** -- OSSEC process monitoring rules.
  OSSEC process monitoring rules.

**531** -- Partition usage reached 100% (disk space monitor).
  Partition usage reached 100% - disk space exhaustion. May indicate log flooding attack, crypto mining, or data stagin...

**532** -- Ignoring external medias.
  Ignoring external medias.

**533** -- Listened ports status (netstat) changed (new port opened or closed).
  Listened ports changed (netstat) - new port opened or closed. New listening ports indicate new services, backdoors, o...

**534** -- List of logged in users. It will not be alerted by default.
  List of logged in users. It will not be alerted by default.

**535** -- List of the last logged in users.
  List of the last logged in users.

**536** -- Ignore snap disks because they are always at 100% of capacity
  Ignore snap disks because they are always at 100% of capacity

**550** -- Integrity checksum changed.
  File integrity checksum changed (syscheck) - level 7. Critical file was modified. Check if change matches authorized...

**553** -- File deleted.
  File deleted (syscheck) - monitored file removed. Deletion of security tools, logs, or system files may indicate anti...

**554** -- File added to the system.
  File added to system (syscheck) - new file in monitored directory. New executables, scripts, or config files outside...

**555** -- Integrity checksum for agentless device changed.
  Integrity checksum for agentless device changed.

**560** -- FIM real-time queue is full. Some real-time events may be lost.
  FIM real-time queue is full. Some real-time events may be lost.

**580** -- Host information changed.
  Host information changed - level 8. System hostname, IP, or OS information changed. Unexpected changes may indicate s...

**581** -- Host information added.
  Host information added.

**591** -- Log file rotated.
  Log file rotated. Normal maintenance event. Verify rotation schedule matches configuration.

**592** -- Log file size reduced.
  Log file size reduced - level 8. Log truncation is anti-forensics indicator. Investigate for tampered audit trails. T...

**593** -- Microsoft Event log cleared.
  Microsoft Event log cleared - level 9. Windows event log clearing is strong anti-forensics indicator. Same significan...

**594** -- Registry Key Integrity Checksum Changed
  Registry key integrity checksum changed (syscheck). Windows registry modification detected. Check if key is persisten...

**597** -- Registry Key Entry Deleted.
  Registry Key Entry Deleted.

**598** -- Registry Key Entry Added to the System
  Registry Key Entry Added to the System

**600** -- Active Response Messages Grouped
  Active Response Messages Grouped

**601** -- Host Blocked by firewall-drop.sh Active Response
  Host blocked by firewall-drop active response. Wazuh automated threat response activated. Verify the triggering alert...

**602** -- Host Unblocked by firewall-drop.sh Active Response
  Host Unblocked by firewall-drop.sh Active Response

**603** -- Host Blocked by host-deny.sh Active Response
  Host Blocked by host-deny.sh Active Response

**604** -- Host Unblocked by host-deny.sh Active Response
  Host Unblocked by host-deny.sh Active Response

**605** -- Host Blocked by $(script) Active Response
  Host Blocked by $(script) Active Response

**606** -- Host Unblocked by $(script) Active Response
  Host Unblocked by $(script) Active Response

**607** -- Active response: $(script) - $(type)
  Active response: $(script) - $(type)

**700** -- Logcollector Messages Grouped
  Logcollector Messages Grouped

**701** -- Ignore informational messages (usually at startup)
  Ignore informational messages (usually at startup)

**750** -- Registry Value Integrity Checksum Changed
  Registry Value Integrity Checksum Changed

**751** -- Registry Value Entry Deleted.
  Registry Value Entry Deleted.

**752** -- Registry Value Entry Added to the System
  Registry Value Entry Added to the System

**200** -- Grouping of wazuh rules.
  Grouping of wazuh rules.

**201** -- Agent event queue rule
  Agent event queue rule

**202** -- Agent event queue is $(level) full.
  Agent event queue is $(level) full.

**203** -- Agent event queue is full. Events may be lost.
  Agent event queue is full. Events may be lost.

**204** -- Agent event queue is flooded. Check the agent configuration.
  Agent event queue is flooded. Check the agent configuration.

**205** -- Agent event queue is back to normal load.
  Agent event queue is back to normal load.

**210** -- Remote upgrade alert
  Remote upgrade alert

**211** -- Remote installation alert
  Remote installation alert

**212** -- Remote upgrade started.
  Remote upgrade started.

**213** -- Remote upgrade could not be launched. Error: $(error).
  Remote upgrade could not be launched. Error: $(error).

**214** -- Remote upgrade finished successfully.
  Remote upgrade finished successfully.

**215** -- Remote upgrade failed. Agent restored to previous version.
  Remote upgrade failed. Agent restored to previous version.

**216** -- Remote upgrade failed. Agent disconnected.
  Remote upgrade failed. Agent disconnected.

**217** -- Custom installation started.
  Custom installation started.

**218** -- Custom installation could not be launched. Error: $(error).
  Custom installation could not be launched. Error: $(error).

**220** -- The agent could not restart due to a $(module) failure in the remote configuration
  The agent could not restart due to a $(module) failure in the remote configuration

**221** -- Syscollector event.
  Syscollector event.

**222** -- The agent could not restart due to a error while unmerging files.
  The agent could not restart due to a error while unmerging files.

**230** -- FIM DB rule
  FIM DB rule

**231** -- The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and all files that come after the limit will not be monitored. Change this setting in centralized configuration or locally on the agent.
  The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and all files that c...

**232** -- The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and all files that come after the limit will not be monitored. Change this setting in centralized configuration or locally on the agent.
  The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and all files that c...

**233** -- The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and no more files will be monitored. Change this setting in centralized configuration or locally on the agent.
  The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored and no more files wi...

**234** -- The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored.
  The file limit set for this agent is $(file_limit). Now, $(file_count) files are being monitored.

**20100** -- First time this IDS alert is generated.
  First time this IDS alert is generated.

**20101** -- IDS event.
  IDS event.

**20102** -- Ignored snort ids.
  Ignored snort ids.

**20103** -- Ignored snort ids.
  Ignored snort ids.

**20152** -- Multiple IDS alerts for same id.
  Multiple IDS alerts for same id.

**20151** -- Multiple IDS events from same source ip.
  Multiple IDS events from same source ip.

**20161** -- Multiple IDS events from same source ip
  Multiple IDS events from same source ip

**20162** -- Multiple IDS alerts for same id
  Multiple IDS alerts for same id

**80200** -- AWS alert.
  AWS alert.

**80202** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName).
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName).

**80203** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName). Error: $(aws.errorCode).
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName). Error: $(aws.errorCode).

**80250** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName). Error: $(aws.errorCode).
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName). Error: $(aws.errorCode).

**80251** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName).
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName).

**80252** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - high number of deleted object.
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - high number of deleted object.

**80253** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - User Login Success.
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - User Login Success.

**80254** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - User Login failed.
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - User Login failed.

**80255** -- AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - Possible breaking attempt (high number of login attempts).
  AWS Cloudtrail: $(aws.eventSource) - $(aws.eventName) - Possible breaking attempt (high number of login attempts).

**80300** -- AWS GuardDuty alert.
  AWS GuardDuty alert.

**80301** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)

**80302** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)

**80303** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title)

**80305** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDetails.remoteIpDetails.ipAddressV4)] [Port: $(aws.service.action.portProbeAction.portProbeDetails.localPortDetails.port)]
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDet...

**80306** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDetails.remoteIpDetails.ipAddressV4)] [Port: $(aws.service.action.portProbeAction.portProbeDetails.localPortDetails.port)]
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDet...

**80307** -- AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDetails.remoteIpDetails.ipAddressV4)] [Port: $(aws.service.action.portProbeAction.portProbeDetails.localPortDetails.port)]
  AWS GuardDuty: $(aws.service.action.actionType) - $(aws.title) [IP: $(aws.service.action.portProbeAction.portProbeDet...

**80325** -- AWS ALB alert.
  AWS ALB alert.

**80330** -- AWS CLB alert.
  AWS CLB alert.

**80335** -- AWS NLB alert.
  AWS NLB alert.

**80350** -- AWS Macie alert.
  AWS Macie alert.

**80351** -- AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)
  AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)

**80352** -- AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)
  AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)

**80353** -- AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)
  AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)

**80354** -- AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)
  AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)

**80355** -- AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)
  AWS Macie $(aws.severity): $(aws.name) - $(aws.summary.description)

**80400** -- AWS VPC Flow alert.
  AWS VPC Flow alert.

**80401** -- AWS VPC Flow: [$(aws.action)] - Interface: $(aws.interface_id) - Protocol: $(aws.protocol)
  AWS VPC Flow: [$(aws.action)] - Interface: $(aws.interface_id) - Protocol: $(aws.protocol)

**80402** -- AWS VPC Flow: [$(aws.action)] - Interface: $(aws.interface_id) - Protocol: $(aws.protocol)
  AWS VPC Flow: [$(aws.action)] - Interface: $(aws.interface_id) - Protocol: $(aws.protocol)

**80440** -- AWS WAF alert.
  AWS WAF alert.

**80441** -- AWS WAF - Allowed request.
  AWS WAF - Allowed request.

**80442** -- AWS WAF - Blocked request.
  AWS WAF - Blocked request.

**80443** -- AWS WAF - Multiple Blocked request.
  AWS WAF - Multiple Blocked request.

**80450** -- AWS Config alert.
  AWS Config alert.

**80451** -- AWS Config - History
  AWS Config - History

**80452** -- AWS Config - Snapshot
  AWS Config - Snapshot

**80453** -- AWS Config - History [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  AWS Config - History [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configura...

**80454** -- The resource was newly discovered. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  The resource was newly discovered. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)...

**80455** -- The resource was discovered but its configuration was not recorded since the recorder excludes the recording of resources of this type. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  The resource was discovered but its configuration was not recorded since the recorder excludes the recording of resou...

**80456** -- The resource was deleted. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  The resource was deleted. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws....

**80457** -- The resource was deleted but its configuration was not recorded since the recorder excludes the recording of resources of this type. AWS Config - History:  [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  The resource was deleted but its configuration was not recorded since the recorder excludes the recording of resource...

**80475** -- AWS Config - Snapshot [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configurationItemStatus))
  AWS Config - Snapshot [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)]: $(aws.resourceId) ($(aws.configur...

**80476** -- AWS Config - Snapshot Compliance [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)] [$(aws.configuration.configRuleList.configRuleName)]: $(aws.resourceId) ($(aws.configurationItemStatus)) $(aws.configuration.complianceType)
  AWS Config - Snapshot Compliance [$(aws.awsAccountId) $(aws.awsRegion)] [$(aws.resourceType)] [$(aws.configuration.co...

**80480** -- AWS Trusted Advisor alert.
  AWS Trusted Advisor alert.

**80481** -- AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)
  AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)

**80482** -- AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)
  AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)

**80483** -- AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)
  AWS Trusted Advisor - [$(aws.uuid)] [$(aws.check-name)]: $(aws.status)

**80490** -- AWS KMS alert.
  AWS KMS alert.

**80491** -- AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type)
  AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type)

**80492** -- AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type) - $(aws.userIdentity.userName) - $(aws.sourceIPAddress)
  AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type) - $(aws.userIdentity.userName) - $(aws.sourceIPAddress)

**80493** -- AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type)
  AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type)

**80494** -- AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type) - $(aws.userIdentity.userName) - $(aws.sourceIPAddress)
  AWS KMS: [$(aws.eventName)] $(aws.userIdentity.type) - $(aws.userIdentity.userName) - $(aws.sourceIPAddress)

**80495** -- AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
  AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]

**80496** -- AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
  AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]

**80497** -- AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
  AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]

**80498** -- AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
  AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]

**80499** -- AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
  AWS Inspector - Network assessment [$(aws.createdAt)]: $(aws.title) [$(aws.severity)]
