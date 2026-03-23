# Sysmon Event IDs
> Source: Sysmon Events | Events: 30


## Index

- [sysmon](#sysmon)


### sysmon

**1** -- Process Create
  Process Create - full command line, parent process, hashes, current directory, user. Key detections: encoded PowerShe...

**2** -- File creation time changed
  File creation time changed (timestomping) - attackers backdate malware to blend with legitimate files. Compare Creati...

**3** -- Network connection
  Network connection - process-level network visibility with source/destination IP and port. Detect C2 beacons (periodi...

**4** -- Sysmon service state changed
  Sysmon service state changed - service started or stopped. Sysmon being stopped is a defense evasion indicator. Monit...

**5** -- Process terminated
  Process terminated - process end events. Useful for correlating process lifetime with network activity. Very short-li...

**6** -- Driver loaded
  Driver loaded - kernel driver load events with signature status. Detect unsigned drivers (vulnerable driver exploitat...

**7** -- Image loaded
  Image loaded (DLL) - detect DLL sideloading (unsigned DLL loaded by signed process from non-standard path), DLL searc...

**8** -- CreateRemoteThread
  CreateRemoteThread - classic code injection indicator. Source process creating thread in target process. High confide...

**9** -- RawAccessRead
  RawAccessRead - direct disk read bypassing filesystem. Used to read locked files (SAM, NTDS.dit), access raw MBR/VBR,...

**10** -- ProcessAccess
  ProcessAccess - LSASS credential dumping indicator. GrantedAccess 0x1010 or 0x1FFFFF targeting lsass.exe is high-conf...

**11** -- FileCreate
  FileCreate - monitor for executables written to unusual locations (C:\Windows\Temp, AppData\Local\Temp, Recycle Bin),...

**12** -- RegistryEvent (Object create/delete)
  RegistryEvent (Object create/delete) - registry key or value creation/deletion. Monitor HKLM\SYSTEM\CurrentControlSet...

**13** -- RegistryEvent (Value Set)
  RegistryEvent (Value Set) - persistence via Run/RunOnce keys, Services, COM objects, IFEO debugger injection. Monitor...

**14** -- RegistryEvent (Key and Value Rename)
  RegistryEvent (Key and Value Rename) - renaming registry keys/values may be used to obfuscate persistence mechanisms...

**15** -- FileCreateStreamHash
  FileCreateStreamHash - Alternate Data Stream (ADS) creation with hash. ADS hides data within existing files. Detect M...

**16** -- ServiceConfigurationChange
  ServiceConfigurationChange - Sysmon config modified. Config changes may weaken monitoring by excluding malicious acti...

**17** -- PipeEvent (Pipe Created)
  PipeEvent (Pipe Created) - named pipe creation. Detect known C2 pipes (Cobalt Strike default pipes: \MSSE-*, \msagent...

**18** -- PipeEvent (Pipe Connected)
  PipeEvent (Pipe Connected) - named pipe connection. Detect processes connecting to known malicious pipes. Pair with E...

**19** -- WmiEvent (WmiEventFilter activity detected)
  WmiEvent (WmiEventFilter) - WMI event filter registered. WMI persistence mechanism (part 1 of 3). Monitor for event f...

**20** -- WmiEvent (WmiEventConsumer activity detected)
  WmiEvent (WmiEventConsumer) - WMI event consumer registered. WMI persistence mechanism (part 2 of 3). CommandLineEven...

**21** -- WmiEvent (WmiEventConsumerToFilter activity detected)
  WmiEvent (WmiEventConsumerToFilter) - WMI consumer-to-filter binding. WMI persistence mechanism (part 3 of 3). Bindin...

**22** -- DNSEvent (DNS query)
  DNSEvent (DNS query) - process-level DNS resolution. Invaluable for detecting C2 domains, DGA patterns (high entropy...

**23** -- FileDelete (File Delete archived)
  FileDelete (archived) - deleted file captured and archived by Sysmon. Enables recovery of deleted malware, tools, and...

**24** -- ClipboardChange
  ClipboardChange - clipboard content monitoring. Detect clipboard hijacking (cryptocurrency address replacement), data...

**25** -- ProcessTampering
  ProcessTampering - process hollowing and herpaderping detection. Image file name changed after process creation. High...

**26** -- FileDeleteDetected
  FileDeleteDetected - file delete logged but not archived. Lower cost than Event 23 (no disk space for archived files)...

**27** -- FileBlockExecutable
  FileBlockExecutable - executable file write blocked by Sysmon rule. Indicates attempted delivery of executable to mon...

**28** -- FileBlockShredding
  FileBlockShredding - file shredding blocked. Anti-forensics prevention. Attackers use secure deletion tools to preven...

**29** -- FileExecutableDetected
  FileExecutableDetected - executable file creation detected. New executables on disk from any source. Monitor for PE f...

**255** -- Error
  Error - Sysmon internal error. May indicate resource exhaustion, driver conflicts, or tampering. Persistent errors ma...
