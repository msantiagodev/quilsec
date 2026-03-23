---
name: cyber-prism
description: >
  Unified cybersecurity threat intelligence lookup across 33 Living-off-the-Land (LOTL)
  and offensive security reference databases plus 512 purpose-built hack tools
  (5,893+ entries total) plus 2,791 security event codes
  across 15 vendor-specific reference files. Use this
  skill whenever analyzing suspicious binaries, system behaviors, Windows APIs, DLL loading,
  Active Directory commands, C2 channels, RMM tool abuse, persistence mechanisms, driver
  vulnerabilities, file extensions, obfuscation techniques, event code/ID lookups, red/blue/
  purple team tool identification, offensive security tool detection, or any security-related
  behavior examination. Triggers on: threat hunting, incident response, malware analysis,
  LOLBin lookup, GTFOBin lookup, binary analysis, suspicious process, detection engineering,
  MITRE ATT&CK technique lookup, indicator enrichment, false positive triage, security
  assessment, event ID lookup, syslog message ID, SIEM event type, EDR alert type, log
  analysis, hack tool identification, C2 framework detection, credential dumping tool
  detection, EDR evasion tool detection, red team tool lookup, blue team tool lookup.
  Even if the user doesn't explicitly say "security" -- if they're asking about a binary,
  API, service, event code, log type, or system behavior in a way that implies threat
  analysis, use this skill.
allowed-tools: Read, Grep, Glob
context: default
model: inherit
user-invocable: true
disable-model-invocation: false
---

# Cyber-Prism

Unified offensive/defensive cybersecurity reference covering 33 Living-off-the-Land projects
with 5,381+ entries PLUS 512 purpose-built offensive/defensive security tools (HackTools).
Total: 5,893+ entries. This skill lets you instantly look up any binary, API, service, driver,
DLL, technique, hack tool, C2 framework, credential dumper, EDR evasion tool, or behavior
across the entire LOTL + HackTools ecosystem.

## When This Skill Is Invoked

When this skill is loaded (either via `/cyber-prism` or auto-triggered), immediately perform
a full threat intelligence lookup using the user's query. Do not just describe what you could
do -- actually do it. Follow the Lookup Procedure below end-to-end:

1. Parse the user's query for the binary, API, service, technique, or behavior in question
2. Route to the correct reference file(s) using the routing table
3. Read the reference file and locate the entry
4. Grep the source JSON in `data/` for the full entry (ALWAYS do this step)
5. Cross-reference adjacent domains (e.g., check false-positives, check C2 channels)
6. Present the complete threat intelligence using the Response Format at the bottom

If the user provides no specific query, present the skill's capabilities and the full
taxonomy of available data sources so they know what they can ask about.

## How This Skill Works

The reference data is organized into domain-specific reference files in the `references/`
directory. Each file covers a specific security domain. Your job is to **route the query to
the right reference file(s)**, read the relevant section, and provide the intelligence.

For most lookups, reading the reference file is sufficient. For deep detail (full indicator
lists, all command examples, raw metadata), grep the bundled JSON files in `data/`.

## Routing Table

Use this table to determine which reference file(s) to read based on the query:

| Query About | Reference File | Source Projects | Entries |
|---|---|---|---|
| Windows binary/exe/script abuse | `references/binaries-windows.md` | LOLBAS | 235 |
| Linux binary exploitation | `references/binaries-linux.md` | GTFOBins | 478 |
| macOS binary abuse | `references/binaries-macos.md` | LOOBins | 59 |
| Cross-platform/unusual binaries | `references/binaries-misc.md` | WTFBins, LOFL | 437 |
| Vulnerable/malicious drivers | `references/drivers.md` | LOLDrivers, Bootloaders | 1,029 |
| DLL hijacking/sideloading | `references/dll-hijacking.md` | HijackLibs | 578 |
| Windows API abuse (malware) | `references/windows-apis.md` | MalAPI, LOLAPI | 420 |
| Active Directory attacks | `references/active-directory.md` | LOLAD, WADComs | 237 |
| C2 channels/trusted service abuse | `references/c2-channels.md` | LOLC2, LOTS, LOT Webhooks, LOTTunnels | 278 |
| Remote management tool abuse | `references/rmm-tools.md` | LOLRMM | 294 |
| Persistence mechanisms | `references/persistence.md` | PersistenceInfo | 44 |
| ESXi/hardware/certs/misc infra | `references/infrastructure.md` | LOLESXi, LOTH, lolcerts, LOLApps, LOTP, Project-Lost, LOLBins-CTI | 130 |
| False positive triage | `references/false-positives.md` | LoFP | 671 |
| Suspicious file extensions | `references/file-extensions.md` | FileSec | 121 |
| Attack payloads/techniques | `references/payloads.md` | PayloadsAllTheThings | 281 |
| PowerShell/command obfuscation | `references/obfuscation.md` | Invoke-Obfuscation, Invoke-DOSfuscation, Bashfuscator, PowerShell-Obfuscation-Bible | 89 |
| C2 frameworks, RATs, implants | `references/hacktools-c2.md` | HackTools | 26 |
| Credential dumping/access/cracking | `references/hacktools-credential-access.md` | HackTools | 33 |
| AD attacks, lateral movement | `references/hacktools-ad-lateral.md` | HackTools | 43 |
| Privilege escalation, post-exploitation | `references/hacktools-privesc-postex.md` | HackTools | 84 |
| EDR evasion, payload gen, steganography | `references/hacktools-evasion.md` | HackTools | 76 |
| Recon, web app testing, OSINT | `references/hacktools-recon-web.md` | HackTools | 61 |
| Network, wireless, cloud, containers, tunneling | `references/hacktools-network-cloud.md` | HackTools | 30 |
| Phishing, social eng, exploitation | `references/hacktools-phishing-exploit.md` | HackTools | 58 |
| DFIR, blue team, forensics | `references/hacktools-dfir-blue.md` | HackTools | 30 |
| Reverse engineering, misc tools | `references/hacktools-re-misc.md` | HackTools | 38 |
| Windows Security Event ID (4624, 4625, etc.) | `references/events-windows-security.md` | Windows Security Events | 140 |
| Windows Event Code (full list) | `references/events-windows-full.md` | Windows Event Codes | 574 |
| Sysmon Event ID (1-29) | `references/events-sysmon.md` | Sysmon Events | 30 |
| Sysmon field-level detail | `references/events-ossem-sysmon.md` | OSSEM Sysmon | 24 |
| Cisco ASA syslog message ID | `references/events-cisco-asa.md` | Cisco ASA Syslog | 488 |
| Palo Alto threat ID / log type | `references/events-paloalto.md` | Palo Alto PAN-OS | 24 |
| Fortinet FortiGate log type ID | `references/events-fortinet.md` | Fortinet FortiGate | 40 |
| Linux auditd event type (AUDIT_*) | `references/events-linux-auditd.md` | Linux Auditd Events | 238 |
| Wazuh rule ID | `references/events-wazuh.md` | Wazuh Rules | 145 |
| Suricata classification / priority | `references/events-suricata.md` | Suricata Classifications | 43 |
| Azure Entra ID audit event | `references/events-azure-entra.md` | Azure Entra Audit | 104 |
| SentinelOne activity type ID | `references/events-sentinelone.md` | SentinelOne Events | 40 |
| Trend Micro EventId/EventSubId | `references/events-trendmicro.md` | Trend Micro Vision One | 36 |
| MITRE ATT&CK technique ID (Txxxx) | `references/events-mitre-attack.md` | MITRE ATT&CK | 835 |
| HTTP status code (security context) | `references/events-http-status.md` | HTTP Status Codes | 30 |

## Lookup Procedure

The reference files are compact indexes -- they give you enough to identify and route, but the
full intelligence (all indicators, every command variant, detection strategies, raw metadata)
lives in the JSON files under `data/`. A good lookup always goes to the source.

1. **Route** -- identify the domain from the query using the routing table, read the reference file
2. **Locate** -- find the tool/technique in the reference file to confirm it exists and get context
3. **Enrich** -- ALWAYS grep the source JSON for the full entry. The reference is a summary; the
   JSON has the complete picture. Use `Grep` with the tool_name against the relevant JSON file
   in `data/`. This is where the real value is -- full indicator lists, all command examples,
   detection strategies, related references, and source-specific raw_data fields.
4. **Cross-reference** -- check adjacent domains. If you found a binary, also check false-positives.
   If you found a C2 channel, also check if there are related RMM tools or tunneling entries.
   Thorough analysis means looking through multiple lenses.

The JSON files map to reference files as follows:
| Reference File | JSON Source(s) in `data/` |
|---|---|
| binaries-windows.md | lolbas.json |
| binaries-linux.md | gtfobins.json |
| binaries-macos.md | loobins.json |
| binaries-misc.md | wtfbins.json, lofl.json |
| drivers.md | loldrivers.json, bootloaders.json |
| dll-hijacking.md | hijacklibs.json |
| windows-apis.md | malapi.json, lolapi.json |
| active-directory.md | lolad.json, wadcoms.json |
| c2-channels.md | lolc2.json, lots.json, lot_webhooks.json, lottunnels.json |
| rmm-tools.md | lolrmm.json |
| persistence.md | persistenceinfo.json |
| infrastructure.md | lolesxi.json, loth.json, lolcerts.json, lolapps.json, lotp.json, project-lost.json, lolbins-cti.json |
| false-positives.md | lofp.json |
| file-extensions.md | filesec.json |
| payloads.md | payloads_all_the_things.json |
| obfuscation.md | invoke_obfuscation.json, dosfuscation.json, bashfuscator.json, ps_obfuscation_bible.json |
| hacktools-c2.md | hacktools.json |
| hacktools-credential-access.md | hacktools.json |
| hacktools-ad-lateral.md | hacktools.json |
| hacktools-privesc-postex.md | hacktools.json |
| hacktools-evasion.md | hacktools.json |
| hacktools-recon-web.md | hacktools.json |
| hacktools-network-cloud.md | hacktools.json |
| hacktools-phishing-exploit.md | hacktools.json |
| hacktools-dfir-blue.md | hacktools.json |
| hacktools-re-misc.md | hacktools.json |
| events-windows-security.md | event_codes/windows_security_events.json |
| events-windows-full.md | event_codes/windows_event_codes_csv.json |
| events-sysmon.md | event_codes/sysmon_event_ids.json |
| events-ossem-sysmon.md | event_codes/ossem_dd_sysmon.json |
| events-cisco-asa.md | event_codes/cisco_asa_syslog.json |
| events-paloalto.md | event_codes/paloalto_panos.json |
| events-fortinet.md | event_codes/fortinet_fortigate.json |
| events-linux-auditd.md | event_codes/linux_auditd_event_types.json |
| events-wazuh.md | event_codes/wazuh_rules.json |
| events-suricata.md | event_codes/suricata_classifications.json |
| events-azure-entra.md | event_codes/azure_entra_audit.json |
| events-sentinelone.md | event_codes/sentinelone.json |
| events-trendmicro.md | event_codes/trendmicro_vision_one.json |
| events-mitre-attack.md | event_codes/mitre_attack.json |
| events-http-status.md | event_codes/http_status_codes.json |

## Multi-Domain Query Examples

Some queries span multiple reference files. Route to all relevant ones:

- "Is certutil suspicious?" -> `binaries-windows.md` (LOLBAS entry) + `false-positives.md` (FP context)
- "telegram being used as C2" -> `c2-channels.md` (LOLC2 entry with detection strategies)
- "VirtualAllocEx in malware" -> `windows-apis.md` (MalAPI entry on injection APIs)
- "persistence via registry" -> `persistence.md` (PersistenceInfo registry techniques)
- "sideloading via signed Adobe exe" -> `dll-hijacking.md` (HijackLibs Adobe entries)
- ".iso file in phishing email" -> `file-extensions.md` (FileSec entry)
- "BloodHound AD enumeration" -> `active-directory.md` (WADComs entry)
- "AnyDesk on compromised host" -> `rmm-tools.md` (LOLRMM entry with IOCs)
- "obfuscated PowerShell command" -> `obfuscation.md` (Invoke-Obfuscation techniques)
- "what is Windows event 4624?" -> `events-windows-security.md` (logon types, lateral movement indicators)
- "Palo Alto threat ID 52000" -> `events-paloalto.md` (file type identification signatures)
- "Cisco ASA syslog 302014" -> `events-cisco-asa.md` (TCP connection teardown)
- "Cobalt Strike beacon detected" -> `hacktools-c2.md` (C2 framework with named pipes, malleable C2 indicators)
- "mimikatz on endpoint" -> `hacktools-credential-access.md` (credential dumping tool with LSASS access patterns)
- "BloodHound SharpHound collection" -> `hacktools-ad-lateral.md` (AD enumeration with LDAP query patterns)
- "PrintSpoofer privilege escalation" -> `hacktools-privesc-postex.md` (token impersonation via print spooler)
- "ScareCrow payload evasion" -> `hacktools-evasion.md` (EDR bypass with code signing and loader techniques)
- "nuclei scanning detected" -> `hacktools-recon-web.md` (vulnerability scanner with template-based detection)
- "chisel tunnel on network" -> `hacktools-network-cloud.md` (HTTP tunneling/pivoting tool)
- "Evilginx2 phishing proxy" -> `hacktools-phishing-exploit.md` (reverse proxy credential harvesting)
- "Velociraptor artifact collection" -> `hacktools-dfir-blue.md` (DFIR endpoint visibility platform)
- "Frida hooking on mobile app" -> `hacktools-re-misc.md` (dynamic instrumentation for mobile security)
- "Sysmon event 10" -> `events-sysmon.md` (ProcessAccess / LSASS credential dumping)
- "what does Suricata classification trojan-activity mean?" -> `events-suricata.md`
- "Wazuh rule 5710" -> `events-wazuh.md`
- "FortiGate logid 0203" -> `events-fortinet.md` (IPS event)
- "Linux audit type 1700" -> `events-linux-auditd.md` (ANOM_PROMISCUOUS)
- "MITRE T1078" -> `events-mitre-attack.md` (Valid Accounts)

## Source Data -- Always Enrich From JSON

The reference markdown files are summaries. The real intelligence is in the JSON. After
locating an entry in a reference file, ALWAYS use Grep to pull the full entry from the
corresponding JSON in `data/`. This is not optional -- truncated indicators or missing
command variants can mean the difference between catching and missing a threat.

Example enrichment flow:
```
1. User asks about "mshta.exe"
2. Read references/binaries-windows.md -> find mshta entry, see categories
3. Grep data/lolbas.json for "mshta" -> get ALL command examples, ALL indicators, ALL references
4. Check data/lofp.json for "mshta" -> get false positive context
5. Synthesize complete answer from full data
```

Each JSON file is an array of objects with this schema:
```json
{
  "source_project": "LOLBAS",
  "tool_name": "certutil.exe",
  "platform": "windows",
  "description": "...",
  "native_purpose": "...",
  "known_behaviors": ["..."],
  "command_examples": ["..."],
  "indicators": ["..."],
  "categories": ["Download", "Execute", "T1105"],
  "references": ["https://..."]
}
```

## Source Project Taxonomy

Understanding what each source project covers helps route ambiguous queries:

**Platform Binaries (LOLBins)**
- **LOLBAS** -- Windows binaries, scripts, and libraries that can be abused (certutil, mshta, rundll32...)
- **GTFOBins** -- Linux binaries exploitable for privilege escalation, file read/write, shells
- **LOOBins** -- macOS-specific binary abuse
- **WTFBins** -- Unusual/unexpected binary behaviors
- **LOFL** -- Living off Foreign Land -- non-native binaries (Python, Node, etc.)

**Drivers & Boot**
- **LOLDrivers** -- Vulnerable and malicious Windows drivers (BYOVD attacks)
- **Bootloaders** -- Revoked/vulnerable bootloaders (Secure Boot bypass)

**DLL & Library Abuse**
- **HijackLibs** -- DLL search order hijacking and sideloading targets

**Windows Internals**
- **MalAPI** -- Windows APIs commonly used by malware (injection, evasion, enumeration)
- **LOLAPI** -- Legitimate Windows APIs abused for offensive operations

**Active Directory**
- **LOLAD** -- AD enumeration and exploitation using native tools
- **WADComs** -- Windows/AD attack tool commands (BloodHound, Rubeus, Mimikatz...)

**C2 & Network Abuse**
- **LOLC2** -- Legitimate services abused as C2 channels (Telegram, Discord, Slack...)
- **LOTS** -- Legitimate sites abused for phishing, C2, and payload delivery
- **LOT Webhooks** -- Webhook services abused for data exfiltration
- **LOTTunnels** -- Tunneling tools for covert communications

**Infrastructure**
- **LOLRMM** -- Remote monitoring/management tools abused by attackers
- **LOLESXi** -- VMware ESXi exploitation techniques
- **LOTH** -- Hardware-level attack techniques
- **LOLApps** -- Application-level abuse
- **LOTP** -- Platform-specific techniques
- **lolcerts** -- Certificate abuse
- **Project-Lost** -- Supply chain and lost/abandoned project risks
- **LOLBins-CTI** -- Threat intelligence on LOLBin usage in the wild

**Offensive/Defensive Security Tools (HackTools)**
- **HackTools** -- 512 purpose-built red/blue/purple team tools

**Detection & Triage**
- **LoFP** -- Known false positive patterns indexed by MITRE technique
- **FileSec** -- File extension security intelligence

**Offensive Techniques**
- **PayloadsAllTheThings** -- Attack payloads (XSS, SQLi, SSTI, CRLF, etc.)
- **Invoke-Obfuscation** -- PowerShell obfuscation techniques with detection patterns
- **Invoke-DOSfuscation** -- cmd.exe/DOSfuscation techniques
- **Bashfuscator** -- Bash obfuscation techniques
- **PowerShell-Obfuscation-Bible** -- PowerShell obfuscation reference


## Response Format

When providing threat intelligence from this skill, structure responses as:

**Tool/Technique:** name
**Source:** which LOL project(s)
**Platform:** windows/linux/macos/cross-platform
**Risk:** what it can be abused for
**Detection:** key indicators or detection strategies
**Commands:** example abuse commands (if available)
**References:** links for further reading

For false positive triage, include the MITRE technique ID and the FP context.
