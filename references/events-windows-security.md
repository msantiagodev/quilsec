# Windows Security Event IDs
> Source: Windows Security Events | Events: 140


## Index

- [security-event-log](#security-event-log)


### security-event-log

**1102** -- Audit log cleared (Security log)
  Audit log cleared - anti-forensics indicator. Clearing Security log requires SeSecurityPrivilege. Always investigate...

**4608** -- Windows starting up (lsass.exe started)
  Windows starting up (lsass.exe started). Baseline event for system boot timeline. Unexpected restarts may indicate cr...

**4610** -- Authentication package loaded by LSA
  Authentication package loaded by LSA. Monitor for non-standard packages (e.g., mimilib.dll loaded as SSP for credenti...

**4611** -- Trusted logon process registered with LSA
  Trusted logon process registered with LSA. Unusual processes registering with LSA may indicate credential interceptio...

**4614** -- Security Account Manager notification package loaded
  Security Account Manager notification package loaded. SAM notification packages see plaintext passwords during change...

**4616** -- System time changed
  System time changed. Time manipulation can disrupt log correlation and evade time-based detections. Monitor for chang...

**4622** -- Security package loaded by LSA
  Security package loaded by LSA. New security packages loaded at boot. Non-default packages may indicate credential in...

**4624** -- Successful logon
  Successful logon - check LogonType (2=interactive, 3=network, 4=batch, 5=service, 7=unlock, 8=network cleartext, 9=ne...

**4625** -- Failed logon attempt
  Failed logon attempt - high volume from single source indicates brute force. Status codes: 0xC000006D=bad username/pa...

**4626** -- User/device claims information
  User/device claims information. Provides claim-based authorization context. Useful for tracking dynamic access contro...

**4627** -- Group membership information
  Group membership information. Logged with 4624, shows all groups for the authenticated user. Useful for identifying o...

**4634** -- Logoff (account logged off)
  Logoff (account logged off). Pair with 4624 using Logon ID to calculate session duration. Short sessions from service...

**4647** -- User initiated logoff
  User initiated logoff. Unlike 4634, indicates deliberate user action. Useful for tracking user session patterns and i...

**4648** -- Logon using explicit credentials (runas / pass-the-hash indicator)
  Logon using explicit credentials (runas) - indicates credential use outside normal context. Common in pass-the-hash,...

**4649** -- Replay attack detected
  Replay attack detected. Kerberos detected a replay attempt. May indicate credential theft and replay-based attacks. A...

**4656** -- Handle to object requested
  Handle to object requested. High volume event when object access auditing enabled. Filter by ObjectType and AccessMas...

**4657** -- Registry value modified
  Registry value modified. Tracks registry changes when SACL is set. Monitor Run/RunOnce keys, Services, Image File Exe...

**4658** -- Handle to object closed
  Handle to object closed. Pair with 4656 for complete object access timeline. Useful for session correlation but high...

**4660** -- Object deleted
  Object deleted. Tracks deletion of audited objects. Monitor for mass deletion patterns (ransomware) or deletion of se...

**4661** -- Handle to object requested (SAM)
  Handle to object requested (SAM). Access to Security Account Manager objects. Monitor for enumeration of domain users...

**4662** -- Operation performed on object (AD DS)
  Operation performed on AD DS object. Tracks Active Directory changes. Monitor for DCSync (Replicating Directory Chang...

**4663** -- Attempt to access object (file/folder/registry)
  Attempt to access object (file/folder/registry). Requires SACL on object. Monitor for access to sensitive files (SAM,...

**4670** -- Permissions on object changed
  Permissions on object changed. DACL modifications on files, registry, or AD objects. Attackers weaken permissions for...

**4672** -- Special privileges assigned to new logon (admin logon)
  Special privileges assigned to new logon - SeDebugPrivilege, SeTcbPrivilege, SeBackupPrivilege, SeRestorePrivilege, S...

**4673** -- Privileged service called
  Privileged service called. Tracks use of sensitive privileges like SeSystemEnvironmentPrivilege (UEFI vars) and SeLoa...

**4674** -- Operation attempted on privileged object
  Operation attempted on privileged object. Tracks privileged operations on secured objects. Useful for detecting unaut...

**4688** -- New process created (with command line if enabled)
  New process created - requires command line logging (GPO: Include command line in process creation events). Critical...

**4689** -- Process exited
  Process exited. Pair with 4688 for process lifetime analysis. Very short-lived processes may indicate reconnaissance...

**4690** -- Attempt to duplicate handle
  Attempt to duplicate handle. Handle duplication between processes. Used in some injection techniques and privilege es...

**4692** -- Backup of DPAPI master key attempted
  Backup of DPAPI master key attempted. DPAPI keys protect user secrets (browser passwords, credential manager). Backup...

**4693** -- Recovery of DPAPI master key attempted
  Recovery of DPAPI master key attempted. Recovering DPAPI keys allows decryption of all user secrets. Monitor for reco...

**4694** -- Protection of auditable protected data attempted
  Protection of auditable protected data attempted. Encryption of data using DPAPI. Unusual patterns may indicate ranso...

**4695** -- Unprotection of auditable protected data attempted
  Unprotection of auditable protected data attempted. Decryption of DPAPI-protected data. Bulk unprotection may indicat...

**4696** -- Primary token assigned to process
  Primary token assigned to process. Token manipulation can enable privilege escalation. Monitor for token assignment t...

**4697** -- Service installed on system
  Service installed on system - persistence mechanism. Check for services with unusual binary paths (temp dirs, encoded...

**4698** -- Scheduled task created
  Scheduled task created - persistence/execution mechanism. Check task actions for encoded commands, unusual binaries,...

**4699** -- Scheduled task deleted
  Scheduled task deleted. Deletion after execution is a cleanup technique. Monitor for create-execute-delete patterns i...

**4700** -- Scheduled task enabled
  Scheduled task enabled. Re-enabling previously disabled tasks may indicate reactivated persistence. Correlate with ta...

**4701** -- Scheduled task disabled
  Scheduled task disabled. Disabling security-related tasks (AV scans, log collection) indicates defense evasion.

**4702** -- Scheduled task updated
  Scheduled task updated. Modification of existing tasks can hijack legitimate scheduled operations. Monitor for change...

**4703** -- Token right adjusted
  Token right adjusted. Tracks privilege enable/disable on tokens. Enabling SeDebugPrivilege at runtime is a strong ind...

**4704** -- User right assigned
  User right assigned. New privilege granted to user/group. Monitor for SeTcbPrivilege, SeDebugPrivilege, SeImpersonate...

**4705** -- User right removed
  User right removed. Privilege removal may indicate cleanup after privilege escalation or legitimate hardening.

**4706** -- Trust to domain created
  Trust to domain created. New domain trust creation is a high-impact AD change. Unauthorized trusts enable cross-domai...

**4707** -- Trust to domain removed
  Trust to domain removed. Trust removal is major infrastructure change. May indicate response to breach or unauthorize...

**4713** -- Kerberos policy changed
  Kerberos policy changed. Changes to Kerberos ticket lifetime, renewal, or encryption settings. Weakening encryption t...

**4716** -- Trusted domain information modified
  Trusted domain information modified. Changes to existing trust relationships. Monitor for trust direction changes or...

**4717** -- System security access granted
  System security access granted. Account granted system-level logon rights. Monitor for SeInteractiveLogonRight, SeRem...

**4718** -- System security access removed
  System security access removed. Logon rights removed. May indicate hardening or attacker covering tracks after using...

**4719** -- System audit policy changed
  System audit policy changed. Audit policy modification is a defense evasion technique. Disabling auditing for specifi...

**4720** -- User account created
  User account created - check for accounts created outside IAM process, especially during off-hours, from unusual sour...

**4722** -- User account enabled
  User account enabled. Re-enabling disabled accounts provides access without creating new detectable accounts. Monitor...

**4723** -- Password change attempted
  Password change attempted. Users change their own password. High failure rate may indicate password policy testing by...

**4724** -- Password reset attempted
  Password reset attempted. Admin-initiated password reset. Monitor for resets of high-privilege accounts, especially f...

**4725** -- User account disabled
  User account disabled. Disabling accounts may be defensive (compromise response) or offensive (denial of service to l...

**4726** -- User account deleted
  User account deleted. Account deletion destroys audit trail for that identity. Attackers may delete accounts created...

**4727** -- Security-enabled global group created
  Security-enabled global group created. New AD security groups may be created for unauthorized access delegation. Moni...

**4728** -- Member added to security-enabled global group
  Member added to security-enabled global group. Adding users to privileged groups (Domain Admins, Enterprise Admins, S...

**4729** -- Member removed from security-enabled global group
  Member removed from security-enabled global group. Removal may indicate cleanup after escalation or defensive respons...

**4730** -- Security-enabled global group deleted
  Security-enabled global group deleted. Group deletion removes access controls and audit trail. Monitor for deletion o...

**4731** -- Security-enabled local group created
  Security-enabled local group created. Local security groups on servers/workstations. Monitor for creation on high-val...

**4732** -- Member added to security-enabled local group
  Member added to security-enabled local group - adding user to local Administrators group is a common privilege escala...

**4733** -- Member removed from security-enabled local group
  Member removed from security-enabled local group. Removal from privileged local groups may indicate defensive respons...

**4734** -- Security-enabled local group deleted
  Security-enabled local group deleted. Deletion of local security groups on endpoints. May indicate post-exploitation...

**4735** -- Security-enabled local group changed
  Security-enabled local group changed. Group attribute changes may weaken security settings or change group scope/type.

**4737** -- Security-enabled global group changed
  Security-enabled global group changed. Changes to AD group attributes. Monitor for scope changes that expand access.

**4738** -- User account changed
  User account changed. Tracks modifications to user attributes. Monitor for UAC flag changes (dont-require-preauth ena...

**4739** -- Domain policy changed
  Domain policy changed. Changes to domain-level policies (password policy, lockout policy, Kerberos policy). Weakening...

**4740** -- User account locked out
  User account locked out. Lockout indicates brute force against the account. Check source workstation (CallerComputerN...

**4741** -- Computer account created
  Computer account created. New computer accounts in AD. Unauthorized computer objects may be used for resource-based c...

**4742** -- Computer account changed
  Computer account changed. Monitor for changes to msDS-AllowedToActOnBehalfOfOtherIdentity (RBCD attacks) and ServiceP...

**4743** -- Computer account deleted
  Computer account deleted. Deletion may disrupt services or indicate cleanup of attack infrastructure in AD.

**4744** -- Security-disabled local group created
  Security-disabled local group created. Distribution groups don't control access but converting them to security group...

**4754** -- Security-enabled universal group created
  Security-enabled universal group created. Universal groups replicate to all DCs in the forest. Monitor for unauthoriz...

**4755** -- Security-enabled universal group changed
  Security-enabled universal group changed. Changes to forest-wide security groups have broad impact.

**4756** -- Member added to security-enabled universal group
  Member added to security-enabled universal group. Universal group membership changes affect entire forest. Monitor fo...

**4757** -- Member removed from security-enabled universal group
  Member removed from security-enabled universal group. Monitor for unauthorized removals that may weaken security cont...

**4764** -- Group type changed
  Group type changed. Converting between security and distribution groups, or changing scope. May enable or circumvent...

**4765** -- SID History added to account
  SID History added to account. SID History injection enables access to resources of another account. Used in domain es...

**4766** -- SID History add attempt failed
  SID History add attempt failed. Failed SID History injection. Still indicates attack attempt even though it failed.

**4767** -- User account unlocked
  User account unlocked. Manual unlock after lockout. Verify through helpdesk ticket. Unlock without corresponding requ...

**4768** -- Kerberos TGT requested (AS-REQ)
  Kerberos TGT requested (AS-REQ) - abnormal encryption types (0x17=RC4) may indicate AS-REP roasting when account has...

**4769** -- Kerberos service ticket requested (TGS-REQ)
  Kerberos service ticket requested (TGS-REQ) - encryption type 0x17 (RC4) may indicate Kerberoasting. Monitor for high...

**4770** -- Kerberos service ticket renewed
  Kerberos service ticket renewed. Frequent renewals or renewals for unusual services may indicate ticket manipulation.

**4771** -- Kerberos pre-authentication failed
  Kerberos pre-authentication failed - Status 0x18=wrong password (brute force), 0x12=account disabled/expired, 0x17=pa...

**4773** -- Kerberos ticket request failed
  Kerberos ticket request failed. Failed TGS requests may indicate invalid or forged tickets being used. Monitor for pa...

**4774** -- Account mapped for logon
  Account mapped for logon. Certificate-based authentication mapping. Monitor for unexpected certificate-to-account map...

**4776** -- NTLM authentication attempted (domain controller)
  NTLM authentication attempted (domain controller) - legacy protocol, monitor for pass-the-hash. Should be rare in Ker...

**4778** -- Session reconnected (RDP reconnect)
  Session reconnected (RDP reconnect). RDP session reconnection from different client may indicate session hijacking or...

**4779** -- Session disconnected (RDP disconnect)
  Session disconnected (RDP disconnect). Disconnection without logoff leaves session active. Attackers may disconnect t...

**4780** -- ACL set on admin group member accounts
  ACL set on admin group member accounts. Automatic ACL reset on admin accounts. Failures may indicate tampered admin a...

**4781** -- Account name changed
  Account name changed. Renaming accounts can disguise compromised or malicious accounts. Monitor for renaming to/from...

**4782** -- Password hash accessed
  Password hash accessed. Direct access to password hashes, indicates credential harvesting. Always investigate - may i...

**4793** -- Password Policy Checking API called
  Password Policy Checking API called. Reconnaissance of password policy. Attackers check policy to optimize brute forc...

**4794** -- DSRM admin password set attempt
  DSRM admin password set attempt. Directory Services Restore Mode password allows offline AD access. Unauthorized chan...

**4798** -- User local group membership enumerated
  User local group membership enumerated. Reconnaissance activity - enumerating who belongs to local groups. Common in...

**4799** -- Security-enabled local group membership enumerated
  Security-enabled local group membership enumerated. Reconnaissance of local admin group membership. Part of standard...

**4800** -- Workstation locked
  Workstation locked. User activity tracking. Unexpected lock events may indicate screensaver policy but generally low...

**4801** -- Workstation unlocked
  Workstation unlocked. Tracks when users return to workstations. Useful for timeline reconstruction during investigati...

**4802** -- Screensaver invoked
  Screensaver invoked. User activity tracking for timeline purposes.

**4803** -- Screensaver dismissed
  Screensaver dismissed. User activity tracking for timeline purposes.

**4825** -- RDP access denied (NLA)
  RDP access denied (NLA). Network Level Authentication rejection. Indicates RDP access attempt that failed before full...

**4826** -- Boot Configuration Data loaded
  Boot Configuration Data loaded. Tracks BCD settings at startup. Changes may indicate bootkits or secure boot tampering.

**4946** -- Windows Firewall exception list rule added
  Windows Firewall exception list rule added. New firewall rules may open unauthorized access. Monitor for rules allowi...

**4947** -- Windows Firewall exception list rule modified
  Windows Firewall exception list rule modified. Rule modifications may weaken existing firewall protection. Monitor fo...

**4948** -- Windows Firewall exception list rule deleted
  Windows Firewall exception list rule deleted. Rule deletion may remove protection. Less concerning than additions unl...

**4950** -- Windows Firewall setting changed
  Windows Firewall setting changed. Profile or global firewall settings modified. Disabling firewall is common defense...

**4964** -- Special groups assigned to new logon
  Special groups assigned to new logon. Custom special group monitoring. Alerts when members of designated groups authe...

**5024** -- Windows Firewall Service started
  Windows Firewall Service started. Normal at boot. Mid-session starts may indicate firewall was previously stopped.

**5025** -- Windows Firewall Service stopped
  Windows Firewall Service stopped. Firewall service stop is defense evasion. Should only occur during planned maintena...

**5031** -- Windows Firewall blocked application
  Windows Firewall blocked application. Application tried to accept connections but was blocked. May indicate malware f...

**5038** -- Code integrity determined image hash is not valid
  Code integrity determined image hash is not valid. Unsigned or tampered binary detected. May indicate malware or modi...

**5058** -- Key file operation
  Key file operation. Cryptographic key operations. Monitor for unauthorized access to encryption keys used for data pr...

**5059** -- Key migration operation
  Key migration operation. Cryptographic key export/migration. May indicate key theft for later decryption of protected...

**5136** -- Directory service object modified
  Directory service object modified. AD object attribute changes. Critical for detecting AdminSDHolder poisoning, GPO m...

**5137** -- Directory service object created
  Directory service object created. New AD objects. Monitor for computer objects (RBCD), GPOs, and organizational units...

**5138** -- Directory service object undeleted
  Directory service object undeleted. Restoring deleted AD objects. May indicate attacker recovering previously cleaned...

**5139** -- Directory service object moved
  Directory service object moved. Moving AD objects between OUs may change inherited permissions and group policies app...

**5140** -- Network share accessed
  Network share accessed - monitor for access to ADMIN$, C$, IPC$ from unusual sources indicating lateral movement. Acc...

**5141** -- Directory service object deleted
  Directory service object deleted. AD object deletion. Monitor for deletion of security groups, GPOs, and organization...

**5142** -- Network share created
  Network share created. New shares on systems. Attackers create shares for data staging or to facilitate lateral movem...

**5143** -- Network share modified
  Network share modified. Share permission changes may weaken access controls on sensitive data.

**5144** -- Network share deleted
  Network share deleted. Share deletion may indicate cleanup of data staging shares used during exfiltration.

**5145** -- Network share object access checked (detailed file share auditing)
  Network share object access checked (detailed file share auditing) - granular share access with access mask. Useful f...

**5152** -- Windows Filtering Platform blocked packet
  Windows Filtering Platform blocked packet. WFP packet block events. High volume from single source may indicate port...

**5154** -- WFP permitted application to listen on port
  WFP permitted application to listen on port. New listening ports opened. Monitor for unusual applications binding to...

**5156** -- WFP permitted connection
  WFP permitted connection. Allowed network connections. Useful for network traffic analysis when full packet capture u...

**5157** -- WFP blocked connection
  WFP blocked connection. Blocked outbound or inbound connections. Failed C2 communication or blocked lateral movement...

**5158** -- WFP permitted bind to local port
  WFP permitted bind to local port. Application allowed to bind a port. Monitor for unusual binaries or unexpected port...

**5159** -- WFP blocked bind to local port
  WFP blocked bind to local port. Application blocked from binding port. May indicate malware prevented from opening li...

**5376** -- Credential Manager credentials backed up
  Credential Manager credentials backed up. Backup of stored credentials may indicate credential harvesting for offline...

**5377** -- Credential Manager credentials restored from backup
  Credential Manager credentials restored from backup. Restoring credentials from backup. May indicate credential injec...

**5378** -- Requested credentials delegation disallowed by policy
  Requested credentials delegation disallowed by policy. CredSSP delegation blocked. May indicate attack attempt using...

**5379** -- Credential Manager credentials read
  Credential Manager credentials read. Reading stored credentials. Tools like mimikatz read credential manager for save...

**5380** -- Vault Find Credential
  Vault Find Credential. Vault enumeration of stored credentials. Part of credential harvesting workflow.

**5381** -- Vault credentials read
  Vault credentials read. Direct read of Windows Vault credentials. Credential theft indicator when performed by non-st...

**5382** -- Vault credentials read
  Vault credentials read. Additional vault credential read event. Same detection context as 5381.

**6416** -- New external device recognized
  New external device recognized. USB/external device connection. Monitor for unauthorized removable media in sensitive...

**7045** -- New service installed (System log, not Security)
  New service installed (System log) - persistence mechanism. Correlate with 4697 for full service installation picture...

**8004** -- NTLM authentication to domain controller (Sysmon-like, AppLocker in some configs)
  NTLM authentication to domain controller. NTLM pass-through authentication. Should be minimal in modern Kerberos envi...
