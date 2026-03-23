# OSSEM Sysmon Field Detail
> Source: OSSEM Sysmon | Events: 24


## Index

- [Sysmon](#sysmon)


### Sysmon

**1** -- 
  The **process creation** event provides extended information about a newly created process. The full command line pro...

**2** -- 
  The change **file creation time** event is registered when a file creation time is explicitly modified by a process....

**3** -- 
  The **network connection** event logs TCP/UDP connections on the machine. It is disabled by default. Each connection...

**4** -- 
  The **service state change** event reports the state of the Sysmon service (started or stopped).

**5** -- 
  The **process terminate** event reports when a process terminates. It provides the UtcTime, ProcessGuid and ProcessId...

**6** -- 
  The **driver loaded** events provides information about a driver being loaded on the system. The configured hashes ar...

**7** -- 
  The **image loaded** event logs when a module is loaded in a specific process. This event is disabled by default and...

**8** -- 
  The **CreateRemoteThread** event detects when a process creates a thread in another process. This technique is used b...

**9** -- 
  The **RawAccessRead** event detects when a process conducts reading operations from the drive using the .\ denotation...

**10** -- 
  The **process accessed** event reports when a process opens another process, an operation that's often followed by in...

**11** -- 
  **File create** operations are logged when a file is created or overwritten. This event is useful for monitoring auto...

**12** -- 
  **Registry key and value create and delete** operations map to this event type, which can be useful for monitoring fo...

**13** -- 
  This Registry event type identifies **Registry value modifications**. The event records the value written for Registr...

**14** -- 
  **Registry key and value rename** operations map to this event type, recording the new name of the key or value that...

**15** -- 
  This event logs when a **named file stream is created**, and it generates events that log the hash of the contents of...

**16** -- 
  This event logs when the local **sysmon configuration is updated**.

**17** -- 
  This event generates when a **named pipe is created**. Malware often uses named pipes for interprocess communication.

**18** -- 
  This event logs when a **named pipe connection** is made between a client and a server.

**19** -- 
  When a **WMI event filter is registered**, which is a method used by malware to execute, this event logs the WMI name...

**20** -- 
  This event logs the **registration of WMI consumers**, recording the consumer name, log, and destination.

**21** -- 
  When a consumer **binds to a filter**, this event logs the consumer name and filter path.

**22** -- 
  This event generates when a process executes a **DNS query**, whether the result is successful or fails, cached or not.

**23** -- 
  This event logs when a **file is deleted** by a process.

**26** -- 
  A file was deleted.
