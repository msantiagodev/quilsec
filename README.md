# QUILL Sec

Offline cybersecurity threat intelligence skill for [Claude Code](https://claude.ai/claude-code). Look up any binary, API, driver, DLL, technique, hack tool, C2 framework, event code, or behavior across 49 security research databases -- instantly, without network calls.

**8,600+ entries. 2,700+ event codes. 42 reference files. Zero API calls.**

## What's inside

| Domain | Sources | Entries |
|--------|---------|---------|
| Windows binaries | LOLBAS | 235 |
| Linux binaries | GTFOBins | 478 |
| macOS binaries | LOOBins | 59 |
| Misc binaries | WTFBins, LOFL | 437 |
| Drivers | LOLDrivers, Bootloaders | 1,029 |
| DLL hijacking | HijackLibs | 578 |
| Windows APIs | MalAPI, LOLAPI | 420 |
| Active Directory | LOLAD, WADComs | 237 |
| C2 channels | LOLC2, LOTS, LOT Webhooks, LOTTunnels | 278 |
| RMM tools | LOLRMM | 294 |
| Persistence | PersistenceInfo | 44 |
| Infrastructure | LOLESXi, LOTH, lolcerts, LOLApps, LOTP, Project-Lost, LOLBins-CTI | 130 |
| False positives | LoFP | 671 |
| File extensions | FileSec | 121 |
| Payloads | PayloadsAllTheThings | 281 |
| Obfuscation | Invoke-Obfuscation, Invoke-DOSfuscation, Bashfuscator, PowerShell-Obfuscation-Bible | 89 |
| Hack tools | HackTools (C2, creds, AD, privesc, evasion, recon, network, phishing, DFIR, RE) | 512 |
| Event codes | Windows Security, Sysmon, Cisco ASA, Palo Alto, Fortinet, Linux Auditd, Wazuh, Suricata, Azure Entra, SentinelOne, Trend Micro, MITRE ATT&CK, HTTP Status | 2,791 |

## Install

```bash
# Clone into your Claude Code skills directory
git clone https://github.com/msantiagodev/quilsec.git ~/.claude/skills/quilsec
```

Or manually copy the contents to `~/.claude/skills/quilsec/`.

## Usage

The skill auto-triggers when you ask Claude Code about security topics. You can also invoke it directly:

```
/quilsec certutil.exe
/quilsec what is Windows event 4624?
/quilsec Cobalt Strike beacon detection
/quilsec sideloading via signed Adobe exe
```

## How it works

1. Your query is routed to the correct reference file(s) via a domain routing table
2. The compact markdown index identifies the entry
3. Full details are enriched from bundled JSON data files
4. Adjacent domains are cross-referenced (e.g., a binary lookup also checks false positives)

All lookups are local file reads -- no network, no API keys, no latency.

## Data sources

All data is sourced from open-source security research projects. This skill aggregates and indexes their work -- all credit belongs to the original maintainers and contributors. See `references/_stats.md` for the full attribution list.

Powered by [QUILL](https://quilsec.com) (Query-driven Unified Index for Living Landscapes).

## License

The aggregated data comes from various open-source projects, each with their own licenses. This skill is provided as a convenience index. Refer to each source project for their specific licensing terms.
