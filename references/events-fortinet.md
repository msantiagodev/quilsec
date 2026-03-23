# Fortinet FortiGate Log Types
> Source: Fortinet FortiGate | Events: 40


## Index

- [log_type](#logtype)
- [severity](#severity)


### log_type

**0001** -- traffic - Forward traffic
  Forward traffic log - traffic passing through the firewall between interfaces. Primary traffic visibility source. Ana...

**0002** -- traffic - Local traffic
  Local traffic log - traffic destined to/from the FortiGate itself. Monitor for management plane access attempts, unau...

**0003** -- traffic - Multicast traffic
  Multicast traffic log - multicast routing events. Unusual multicast may indicate network reconnaissance or VXLAN-base...

**0004** -- traffic - Sniffer traffic
  Sniffer traffic log - packet capture mode traffic. Indicates FortiGate in sniffer/one-arm mode. Useful for passive mo...

**0100** -- event - System event
  System event - admin logins, config changes, firmware updates, HA events. Detect unauthorized management plane access...

**0101** -- event - VPN event
  VPN event - IPsec and SSL-VPN tunnel events. Monitor for VPN brute force (repeated failed authentications), unusual s...

**0102** -- event - User event
  User event - user authentication events. Track logon/logoff, RADIUS/LDAP/TACACS+ auth. Monitor for credential stuffin...

**0103** -- event - Router event
  Router event - dynamic routing protocol events (OSPF, BGP, RIP). Route hijacking or unexpected route changes may indi...

**0104** -- event - Wireless event
  Wireless event - WiFi events for FortiAP integration. Monitor for rogue AP detection, WPA attacks, and unauthorized w...

**0105** -- event - WAD event
  WAD event - Web Application Detection proxy events. Application-level visibility through explicit/transparent proxy.

**0106** -- event - Endpoint event
  Endpoint event - FortiClient endpoint events. Endpoint compliance, malware detection, and vulnerability scan results...

**0107** -- event - HA event
  HA event - High Availability cluster events. Monitor for unexpected failovers which may indicate device tampering or...

**0108** -- event - Compliance check event
  Compliance check event - security posture assessment results. Identify non-compliant endpoints and policy violations.

**0109** -- event - FortiExtender event
  FortiExtender event - WAN extender events. Monitor for unauthorized cellular/WAN failover that may bypass network sec...

**0110** -- event - Security rating event
  Security rating event - FortiGate Security Fabric rating assessments. Track security posture changes over time.

**0111** -- event - FortiSDNConnector event
  FortiSDNConnector event - SDN integration events. Monitor for SDN policy changes and cloud connector health.

**0200** -- utm - Virus/malware event
  UTM virus/malware event - antivirus engine detections. Correlate source IP with endpoint inventory for infected host...

**0201** -- utm - Web filter event
  Web filter event - URL/category filtering decisions. Monitor for blocked categories being accessed (malware, phishing...

**0202** -- utm - Application control event
  Application control event - application identification and enforcement. Detect shadow IT, unauthorized remote access...

**0203** -- utm - IPS event
  IPS event - intrusion prevention signatures triggered. High/critical severity requires immediate triage. Correlate CV...

**0204** -- utm - Anomaly event
  Anomaly event - protocol anomaly and rate-based detections. Detect DoS attacks, protocol violations, and traffic patt...

**0205** -- utm - Email filter event
  Email filter event - spam and phishing email detections. Monitor for targeted phishing campaigns and BEC attempts. Co...

**0206** -- utm - DLP event
  DLP event - data loss prevention trigger. Investigate for data exfiltration attempts. Check matched pattern, destinat...

**0207** -- utm - VoIP event
  VoIP event - voice/SIP protocol events. Monitor for toll fraud, VoIP scanning, and SIP-based attacks.

**0208** -- utm - GTP event
  GTP event - GPRS Tunneling Protocol events (mobile network). Relevant for telecom environments, monitor for GTP-based...

**0209** -- utm - DNS event
  DNS event - DNS filtering and inspection results. Detect C2 domains, DGA patterns, DNS tunneling, and malicious domai...

**0210** -- utm - SSH filter event
  SSH filter event - SSH deep inspection events. Monitor for SSH tunneling abuse, brute force, and unauthorized SSH key...

**0211** -- utm - SSL event
  SSL event - SSL/TLS inspection events. Certificate errors may indicate MITM. Monitor for connections using weak ciphe...

**0212** -- utm - CIFS event
  CIFS event - SMB/CIFS protocol events. Monitor for SMB-based lateral movement, ransomware file operations, and unauth...

**0213** -- utm - File filter event
  File filter event - file type-based filtering. Detect executable transfers, script file downloads, and file type masq...

**0214** -- utm - ICAP event
  ICAP event - Internet Content Adaptation Protocol events for external content scanning integration.

**0215** -- utm - Virtual patch event
  Virtual patch event - protection for known vulnerabilities without endpoint patching. Indicates vulnerability exploit...

### severity

**emergency** -- emergency
  Severity 0 - system unusable. Immediate action required. Indicates critical hardware failure, firmware corruption, or...

**alert** -- alert
  Severity 1 - immediate action required. Critical security events requiring SOC response within minutes.

**critical** -- critical
  Severity 2 - critical condition. High-impact events that may affect security posture or service availability.

**error** -- error
  Severity 3 - error condition. Operational errors that may impact security monitoring or enforcement capabilities.

**warning** -- warning
  Severity 4 - warning condition. Conditions that may lead to errors or security gaps if not addressed.

**notification** -- notification
  Severity 5 - normal but significant. Standard operational events that confirm proper functioning.

**information** -- information
  Severity 6 - informational. Routine events useful for baseline and trending analysis.

**debug** -- debug
  Severity 7 - debug messages. Detailed diagnostic information, typically disabled in production.
