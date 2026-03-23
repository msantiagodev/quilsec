# Palo Alto PAN-OS Threat IDs
> Source: Palo Alto PAN-OS | Events: 24


## Index

- [log_type](#logtype)
- [threat_type_id](#threattypeid)


### log_type

**TRAFFIC** -- TRAFFIC
  Traffic log - connection start/end/deny with source/dest IP, port, zone, rule, bytes, session duration. Essential for...

**THREAT** -- THREAT
  Threat log - virus, spyware, vulnerability, URL filtering, file blocking, data filtering events. Primary security eve...

**SYSTEM** -- SYSTEM
  System log - PAN-OS system events including admin logins, config changes, firmware updates, HA failover. Detect unaut...

**CONFIG** -- CONFIG
  Configuration log - all configuration changes with before/after values. Essential for change management audit trail....

**HIPMATCH** -- HIPMATCH
  HIP Match log - GlobalProtect Host Information Profile results. Endpoint compliance check outcomes. Identify non-comp...

**GLOBALPROTECT** -- GLOBALPROTECT
  GlobalProtect log - VPN portal and gateway events. Monitor for VPN brute force, unusual connection sources, and concu...

**AUTHENTICATION** -- AUTHENTICATION
  Authentication log - all authentication events. Monitor for brute force patterns, authentication from unusual locatio...

**USERID** -- USERID
  User-ID log - user-to-IP mapping events. Essential for identity-based policy enforcement. Stale mappings may cause po...

**TUNNEL** -- TUNNEL
  Tunnel Inspection log - GRE and non-encrypted tunnel events. Detect unauthorized tunneling that may bypass security c...

**SCTP** -- SCTP
  SCTP log - SCTP association events. Monitor for unauthorized SCTP usage which may indicate telecom-specific attacks o...

**DECRYPTION** -- DECRYPTION
  Decryption log - SSL/TLS decryption events. Monitor for decryption failures (certificate pinning bypass failures) and...

**CORRELATION** -- CORRELATION
  Correlation log - events correlated by PAN-OS analytics engine. Pre-built detection logic combining multiple log sour...

### threat_type_id

**8000-8099** -- Application detection signatures
  Application detection signatures - identifies applications traversing the firewall regardless of port. Detect shadow...

**8500-8599** -- File blocking signatures
  File blocking signatures - blocks file transfers matching configured types. Detect executable downloads, script file...

**9000-9999** -- Custom vulnerability signatures
  Custom vulnerability signatures - user-defined IPS rules. Organization-specific protections for internal applications...

**10000-19999** -- Phone home detection signatures
  Phone home detection signatures - detects outbound C2 communication patterns. Matches known C2 protocols, beaconing p...

**20000-29999** -- Spyware phone home signatures
  Spyware phone home signatures - detects spyware/adware calling home. Lower severity than C2 but indicates compromised...

**30000-44999** -- Vulnerability protection signatures
  Vulnerability protection signatures - IPS signatures matching CVE exploits. High severity hits require immediate inve...

**52000-52999** -- File type identification signatures
  File type identification signatures - identifies file types regardless of extension. Detects extension masquerading a...

**60000-69999** -- Data filtering signatures
  Data filtering signatures - DLP pattern matching. Detects credit card numbers, SSNs, and custom data patterns leaving...

**100000-2999999** -- Virus (WildFire) signatures
  WildFire malware signatures - cloud-analyzed file verdicts. Indicates known malware matched by sandbox analysis. File...

**3000000-3999999** -- WildFire inline ML signatures
  WildFire inline ML signatures - machine learning-based detection applied inline. Catches zero-day malware without clo...

**4000000-4999999** -- DNS Security signatures
  DNS Security signatures - malicious domain detection. Blocks C2, DGA domains, DNS tunneling, newly registered domains...

**6000001-6999999** -- Advanced Threat Prevention inline cloud-analyzed signatures
  Advanced Threat Prevention inline cloud-analyzed signatures - real-time cloud analysis for advanced threats. Combines...
