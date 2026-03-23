# Windows Event Codes (Full)
> Source: Windows Event Codes | Events: 574


**?** -- 
  We have observed this event being logged upon restarting Windows after a dirty shutdown.

**?** -- 
  Event 1102 is logged whenever the Security log is cleared, REGARDLESS of the status of the Audit System Events audit...

**?** -- 
  No more events will be logged until the log is expanded, cleared or configured to overwrite events.

This event indi...

**?** -- 
  This event is only logged when "When maximum log size is reached:" is set to "Archive the log when full, do not overw...

**?** -- 
  I have observed this event on actual systems but have not been able to determine the cause. Start a discussion below...

**?** -- 
  4608 is an important security event: Any operating system is essentially defenseless when the operating system is down.

**?** -- 
  Despite the documentation, as of Release candidate1 this event is not found. Perhaps this is because the event loggin...

**?** -- 
  Event4610 is logged once at startup for each authentication package on the system. 

An authentication package is a...

**?** -- 
  An occurrence of event 4611 is logged at startup and occasionally afterwards for each logon process on the system....

**?** -- 
  This event has not been observed but would indicate that an extremely high period of activity prevented Windows from...

**?** -- 
  An occurrence of Event4614 is logged for each notification package on the system. 

Notification packages are DLLs t...

**?** -- 
  LPC is used for communication between threads or processes or for communication between kernel mode and user mode com...

**?** -- 
  This event indicates the old and new system time as well as who did it as specified in the Subject: section. Process...

**?** -- 

**?** -- 
  In testing I configured the log to crash on audit failure and then filled up the security log which indeed brought th...

**?** -- 
  Security packages are yet another type of plug-in that extends security functionality in Windows. MSDN defines a secu...

**?** -- 
  This is a highly valuable event since it documents each and everysuccessful attemptto logon to the local computer reg...

**?** -- 
  This is a useful event because it documents each and every failed attempt to logon to the local computer regardless o...

**?** -- 
  nan

**?** -- 
  This is the only event of it's new Group Membership subcategory.  One or more of these events are logged whenever a u...

**?** -- 
  Also see event ID 4647which Windows logs instead of this eventin the case of interactive logonswhen the user logs out...

**?** -- 

**?** -- 
  Also see 4634. This event signals the end of a logon session and can be correlated back to the logon event 4624 using...

**?** -- 
  This is a useful event for tracking several different situations:

**?** -- 

**?** -- 
  An IPsec Main Mode security association was established. Extended Mode was not enabled. Certificate authentication wa...

**?** -- 
  An IPsec Main Mode security association was established. Extended Mode was not enabled. A certificate was used for au...

**?** -- 
  nan

**?** -- 
  nan

**?** -- 
  An IPsec Quick Mode negotiation failed

**?** -- 
  nan

**?** -- 
  This event is logged by multiple subcategories as indicated above.

When you enable auditing on an object(e.g. file...

**?** -- 
  This event documents creation, modification and deletion of registry VALUES. This event is logged between the open (4...

**?** -- 
  This event is logged by multiple subcategories as indicated above.

**?** -- 
  This event should be logged whenever your install a patch that requires replacement of a file that is already opened...

**?** -- 
  This event is logged by multiple subcategories as indicated above.

This event is logged when an object is deleted w...

**?** -- 
  This event is logged by multiple subcategories as indicated above.

Most objects, when opened (handle request), gene...

**?** -- 
  Active Directory logs this event when a user accesses an AD object. 

Of course the object's audit policy must be en...

**?** -- 
  This event is logged by multiple subcategories as indicated above.

This event documents actual operations performed...

**?** -- 
  An attempt was made to create a hard link.

**?** -- 

**?** -- 
  nan

**?** -- 
  This event is logged in connection with Authorization Manager access checks. See Establishing a Client Context with A...

**?** -- 
  I haven't been able to produce this event. Have you? If so, please start a discussion (see above) and post a sample a...

**?** -- 
  Windows logs this event when someonechanges the access control list on an object. The event identifies the object, wh...

**?** -- 
  TBS is a part of Trusted Platform Module

**?** -- 
  This event lets you know whenever an account assigned any "administrator equivalent" user rights logs on. For instanc...

**?** -- 
  Event 4673 indicates that the specified user exercised the user right specified in the Privileges field. 

Note: "Us...

**?** -- 
  Event 4674 indicates that the specified user exercised the user right specified in the Privileges field. 

Note: "Us...

**?** -- 
  SIDs were filtered

**?** -- 
  Event 4688 documents each program that is executed, who the program ran as and the process that started this process....

**?** -- 
  Event 4689 documents when a process ends. 

When you start a program you are creating a "process" that stays open un...

**?** -- 
  When a program opens an object like a file, it gets a "handle" to that file which it references in subsequent operati...

**?** -- 
  Indirect access to an object was requested.

**?** -- 
  Microsoft documentation indicates this is a routine event that can be filtered out of events to review. At this time...

**?** -- 

**?** -- 

**?** -- 
  This event has to do with the Data Protection API. 

Per Microsoft: "The Data Protection API (DPAPI) helps to protec...

**?** -- 
  This often happens when a service starts or a scheduled task starts under the authority of a different user. You will...

**?** -- 
  A new service was installed by the userindicated in the subject. Subject often identifies the local system (SYSTEM) f...

**?** -- 
  The user indicated in Subject: just created a new scheduled task (Start menu\Accessories\System Tools\Task Scheduler)...

**?** -- 
  The user indicated in Subject: just deletedthe scheduled task (Start menu\Accessories\System Tools\Task Scheduler) id...

**?** -- 
  The user indicated in Subject: just enabled the scheduled task (Start menu\Accessories\System Tools\Task Scheduler) i...

**?** -- 
  The user indicated in Subject: just disabled the scheduled task (Start menu\Accessories\System Tools\Task Scheduler)...

**?** -- 
  The user indicated in Subject: just updated the scheduled task (Start menu\Accessories\System Tools\Task Scheduler) i...

**?** -- 
  We have not yet observed this event

**?** -- 
  This event documents a change to user right assignments on this computer including the right anduser or group that re...

**?** -- 
  This event documents a change to user right assignments on this computer including the right anduser or group that lo...

**?** -- 
  This event is logged for all new trust relationships connecting to this domain. While the description says "Trusted"...

**?** -- 
  This event is logged for all deleted trust relationships that connected to this domain. While the description says "T...

**?** -- 
  This event is not produced in the default configuration (using Windows Firewall)however event 5478 is produced..

**?** -- 
  In the default configuration this event is not produced when the IPsec Policy agent service is disabled or fails to s...

**?** -- 

**?** -- 
  In theory this reports when the service cannot perform its required tasks, such as properly processing filters, or ca...

**?** -- 
  Windows logs 4713 when it detects a change to the the domain's Kerberos policy. Kerberos policy is defined in GPOs li...

**?** -- 
  This computer's Security Settings\Public Key Policies\Encrypting File System data recovery agent policy was modified...

**?** -- 
  The description is poorly worded but this event is logged whenever you set the security descriptor used to delegate a...

**?** -- 
  This event is logged for modifications to trust relationships connecting to this domain. While the description says "...

**?** -- 
  This event documents the grant of logon rights such as "Access this computer from the network" or "Logon as a service...

**?** -- 
  This event documents the revokation of logon rights such as "Access this computer from the network" or "Logon as a se...

**?** -- 
  This computer'ssystem level audit policywas modified - either via Local Security Policy, Group Policy in Active Direc...

**?** -- 
  The user identified by Subject: created the user identified by New Account:. 

Attributes show some of the propertie...

**?** -- 
  The user identified by Subject: enabed the user identified by Target Account:. 

This event is logged both for local...

**?** -- 
  The user attempted to change his/her own password. Subject and Target should always match. Don't confuse this event w...

**?** -- 
  The Subject attempted to reset the password of the Target:

Don't confuse this event with 4723.

This event is logg...

**?** -- 
  The user identified by Subject: disabled the user identified by Target Account:. 

This event is logged both for loc...

**?** -- 
  The user identified by Subject: deleted the user identified by Target Account:. 

This event is logged both for loca...

**?** -- 
  The user in Subject: just created a Security Global group identified in New Group.

In Active Directory Users and Co...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Security Global group in Group:.

In Active Dir...

**?** -- 
  The user in Subject: removed the user/group/computer in Member: from the Security Global group in Group:.

In Active...

**?** -- 
  The user in Subject:deleted theSecurity Global group identified in Deleted Group.

In Active Directory Users and Com...

**?** -- 
  The user in Subject: created a Security Local group identified in New Group.

This event is logged on domain control...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Security Local group in Group:.

This event is...

**?** -- 
  The user in Subject: removed the user/group/computer in Member: to the Security Local group in Group:.

This event i...

**?** -- 
  The user in Subject:deleted theSecurity Local group identified in Deleted Group.

This event is logged on domain con...

**?** -- 
  The user in Subject: changed the Security Local group identified in Group:.

This event is logged on domain controll...

**?** -- 
  The user in Subject: changed the Security Global group identified in Group:.

In Active Directory Users and Computer...

**?** -- 
  The user identified by Subject: changed the user identified by Target Account:. 

Attributes show some of the proper...

**?** -- 
  This computer's Security Settings\Account Policyor Account Lockout Policypolicy was modified - either via Local Secur...

**?** -- 
  The indicated user account was locked out after repeated logon failures due to a bad password. 

See event ID 4767 f...

**?** -- 
  The user identified by Subject: created the computer identified by New Computer Account:. 

Note: computer accounts...

**?** -- 
  The user identified by Subject: changed the computer identified by Computer Account That Was Changed:. 

Note: compu...

**?** -- 
  The user identified by Subject: changed the computer identified by Target Computer:. 

Note: computer accounts alway...

**?** -- 
  The user in Subject: created a Local Distribution group identified in New Group.

This event is only logged on domai...

**?** -- 
  The user in Subject: changed the Local Distribution group identified in Group:.

This event is only logged on domain...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Local Distribution group in Group:.

This event...

**?** -- 
  The user in Subject: removed the user/group/computer in Member: to the Local Distribution group in Group:.

This eve...

**?** -- 
  The user in Subject:deleted theLocal Distribution group identified in Deleted Group.

This event is only logged on d...

**?** -- 
  The user in Subject: created a Global Distribution group identified in New Group.

This event is only logged on doma...

**?** -- 
  The user in Subject: changed the Global Distribution group identified in Group:.

This event is only logged on domai...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Global Distribution group in Group:.

This even...

**?** -- 
  The user in Subject: removed the user/group/computer in Member:from the Global Distribution group in Group:.

This e...

**?** -- 
  The user in Subject:deleted theGlobal Distribution group identified in Deleted Group.

This event is only logged on...

**?** -- 
  The user in Subject: created a Universal Security group identified in New Group.

In Active Directory Users and Comp...

**?** -- 
  The user in Subject: changed the Universal Security group identified in Group:.

In Active Directory Users and Compu...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Universal Security group in Group:.

In Active...

**?** -- 
  The user in Subject: removed the user/group/computer in Member: from the Universal Security group in Group:.

This e...

**?** -- 
  The user in Subject:deleted theUniversal Security group identified in Deleted Group.

In Active Directory Users and...

**?** -- 
  The user in Subject: created a Universal Distribution group identified in New Group.

This event is only logged on d...

**?** -- 
  The user in Subject: changed the Universal Distribution group identified in Group:.

This event is only logged on do...

**?** -- 
  The user in Subject: added the user/group/computer in Member: to the Universal Distribution group in Group:.

This e...

**?** -- 
  The user in Subject: removed the user/group/computer in Member:from the Universal Distribution group in Group:.

Thi...

**?** -- 
  The user in Subject:deleted theUniversal Distribution group identified in Deleted Group.

This event is only logged...

**?** -- 
  A group's type or scope was changed by Subject:.

AD has 2 types of groups: Security and Distribution. Distribution...

**?** -- 
  A group's type or scope was changed by Subject:.

AD has 2 types of groups: Security and Distribution. Distribution...

**?** -- 

**?** -- 

**?** -- 
  The user identified by Subject: unlocked the user identified by Target Account:. 

Note: this event is logged whenev...

**?** -- 
  This event is logged on domain controllers only and both success and failure instances of this event are logged. 

A...

**?** -- 
  Windows uses this event ID for both successful and failed service ticket requests. If it is a failure event see Failu...

**?** -- 
  Kerberos limits how long a ticket is valid. If a ticket expires when the user is still logged on, Windows automatical...

**?** -- 
  This event is logged on domain controllers only and only failure instances of this event are logged. 

At the beginn...

**?** -- 

**?** -- 
  Windows does not log this event. Instead it logs event ID 4769 with keyword Failure Audit.

**?** -- 
  I have not actually seen this event logged by Windows but suspect that if it is logged at all it would be in conjunct...

**?** -- 
  I have not actually seen this event logged by Windows but suspect that it if it is logged at all it would be in conju...

**?** -- 
  Despite what this event says, the computer is not necessarily a domain controller; member servers and workstations al...

**?** -- 
  This event does not seem to exist. I have never observed it. Furthermore, 4776 is logged for both success and failure.

**?** -- 
  Windows logs this event when a user reconnects to a disconnected terminal server (aka Remote Desktop) session as oppo...

**?** -- 
  Windows logs this event when a user disconnects from a terminal server (aka remote desktop) session as opposed to an...

**?** -- 
  This event, 4780, is logged whenever Windows modifies the ACL of a member of Domain Admins or Administrators to match...

**?** -- 
  The user identified by Subject: changed either the normal logon name or the pre-Win2k logonnameof the user identified...

**?** -- 
  This typically happens when something like the Active Directory Migration Tool (ADMT) is moving password data.

**?** -- 
  The user in Subject: created an application group identified in Group:.

Application groups are part of Windows's ro...

**?** -- 
  The user in Subject: changed the application group identified in Group:.

Application groups are part of Windows's r...

**?** -- 
  The user in Subject: added Member: to the application group identified in Group:.

Application groups are part of Wi...

**?** -- 
  The user in Subject: removed Member: from the application group identified in Group:.

Application groups are part o...

**?** -- 
  Apparently this event is supposed to be logged when you add an exclusion to a basic application group but instead Win...

**?** -- 
  Apparently this event is supposed to be logged when you remove an exclusionfrom a basic application group but instead...

**?** -- 
  The user in Subject: deleted the application group identified in Group:.

Application groups are part of Windows's r...

**?** -- 
  This event also applies to Business Rule Application Groups.

The user in Subject: created an LDAP Query group or Bu...

**?** -- 
  The user in Subject: changed the LDAP Query group or Business Rule Application Group(BRAP) identified in Group:.

Th...

**?** -- 
  This event also applies to Business Rule Application Groups.

The user in Subject: deleted theLDAP Query group or Bu...

**?** -- 
  Microsoft says this is "typical behavior" and can be ignored. I concur. You may frequently see it on SQL Servers.

**?** -- 
  This event is logged whenever you successfully set the DSRM administrator password such as with ntdsutil.

This pass...

**?** -- 
  There is a lot of confusion about this event and no good explanation.  If you see this event for many different targe...

**?** -- 
  Windows logs this event when a process enumerates the local groups to which a the specified user belongs on that comp...

**?** -- 
  Windows logs this event when a process enumerates the members of the specified local group on that computer.

**?** -- 
  When either a user manually lockshis workstation or the workstation automatically locks its console after a period of...

**?** -- 
  When a user unlockshis workstation you will see this event.

To find out when the workstation was previously lockedl...

**?** -- 
  When the workstation activates the screen saver in response toa period of inactivity this event is logged.

To find...

**?** -- 
  When a user unlockshis workstation you will see this event.

To find out when the screen saver previously kicked in...

**?** -- 

**?** -- 
  Auditing settings on object were changed.

**?** -- 
  nan

**?** -- 
  nan

**?** -- 
  This event is new to Server 2012 R2. It does not appear in earlier versions.

**?** -- 
  This event is new to Server 2012 R2. It does not appear in earlier versions.

**?** -- 
  This event is new to Server 2012 R2. It does not appear in earlier versions.

**?** -- 
  This event is new to Server 2012 R2. It does not appear in earlier versions.

**?** -- 
  This event is new to Server 2012 R2. It does not appear in earlier versions.

**?** -- 
  nan

**?** -- 
  Windows logs this event at startup to document the current Boot Configuration Data settings with particular security...

**?** -- 
  We have not yet seen this event

**?** -- 

**?** -- 
  This event is logged cross-forest trust relationships are created or modified. You will get several of these events p...

**?** -- 
  This event is logged cross-forest trust relationships are deleted or modified. You will get several of these events p...

**?** -- 
  This event is logged cross-forest trust relationships are modified. You will get several of these events per trust....

**?** -- 
  Certification Authorities and Certificate Templates can be configured to require approval by an administrator or cert...

**?** -- 
  This event gets logged more than the description would indicate. It seems to be logged whenever

**?** -- 
  When an administrator revokes a certificate the certificate is moved to the Revoked Certificates folder and this even...

**?** -- 
  See event 4872.

**?** -- 
  Certification Authorities as a normal course of operation periodically publish an updated CRL and this event is logge...

**?** -- 

**?** -- 

**?** -- 
  Having tested for this event by shutting down Certificate Services I conclude this event does not seem to get logged...

**?** -- 
  Logged each time the Certification Authorities backup starts. Event indicates type of backup below. Next, event 4877...

**?** -- 
  Certificate Services backup completed. To find out when the backup started and what type of backup it was look earlie...

**?** -- 
  self explanatory

To find out when the restore ended look later in the log for 4879.

This event event is only logg...

**?** -- 
  self explanatory

To find out when the restore started look earlier in the log for 4878.

**?** -- 
  This event is logged each time the Active Directory Certificate Services service starts.

This event event is only l...

**?** -- 
  This event is logged each time the Active Directory Certificate Services service is stopped.

This event event is on...

**?** -- 
  This event documents a change to the access control list of the Certification Authority itself. The ACL governs who c...

**?** -- 

**?** -- 

**?** -- 
  Windows logs this event whenever you modify the Auditing tab of the Properties dialog of the CA in the Certification...

**?** -- 
  When the Certification Authority receives a certificate reqeuest it logs this event. 

Then it evaluates the request...

**?** -- 
  This event is logged when a certificate is issued as a result of either:

**?** -- 
  This event event is only logged if "Issue and manage certificate requests" is enabled on the Audit tab of the CA's pr...

**?** -- 
  Certification Authorities and Certificate Templates can be configured to require approval by an administrator or cert...

**?** -- 
  This event is logged when you modify the settings in the Certificate Managers tab of the CA properties dialog in Cert...

**?** -- 
  Windows logs this event to document changes to Certificate Services registry entries many of which correspond to prop...

**?** -- 
  A property of Certificate Services changed.

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  Certificate Services published the CA certificate to Active Directory Domain Services.

**?** -- 
  This event is logged whenever CS starts and whenever role separation is actually changed.

Role separation is a form...

**?** -- 
  Windows logs this event when CS loads a certificate template in order to evaluate a new certificate request

**?** -- 
  Having tested for this event by making changes to certificate templates I conclude Windows fails to log this event.

**?** -- 
  Windows logs this event when you modify the ACL on a certificate template.

**?** -- 
  This is a routine event logged at system startup and can be regarded as noise.

**?** -- 
  Windows allows applications to report their own security events to the security log by registering with Authorization...

**?** -- 
  Windows allows applications to report their own security events to the security log by registering through Authorizat...

**?** -- 
  This event is logged when you change the value of the security option "Audit: Shut down system immediately if unable...

**?** -- 
  When you change the audit SACL of an object, such as a file or folder, Windows logs this event. In the example below,...

**?** -- 
  This event is produced when a SID (Security Identifier) is added to SpecialGroups for auditing purposes.

**?** -- 
  This event, 4909, is apparently logged when you make a change to the TPM configuration in the local policy objectof t...

**?** -- 
  This event, 4910, is apparently logged when you make a change to the TPM configuration through a group policy object...

**?** -- 
  nan

**?** -- 
  When you use auditpol to set per user selective auditing Windows logs this event documenting the user for whom you se...

**?** -- 
  nan

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  Directory Service replication has little to no security relevance. I recommend disabling these 2 subcategories:

**?** -- 
  This event is logged once each time Windows Firewall start which is usually at boot up. This event documents the high...

**?** -- 
  This event is logged aproximately 1.7 bazillion times everytime Windows Firewall starts which results in a full recor...

**?** -- 
  Exceptions define traffic that bypasses other Windows Firewall rules.

**?** -- 
  Exceptions define traffic that bypasses other Windows Firewall rules.

Profile Changed: Domain, Private, Public, All

**?** -- 
  A change was made via the Windows Firewall with Advanced Services MMC console.

**?** -- 
  self explanatory

**?** -- 
  A change was made via the Windows Firewall with Advanced Services MMC console.

**?** -- 

**?** -- 

**?** -- 
  I haven't been able to produce this event. Have you? If so, please start a discussion (see above) and post a sample a...

**?** -- 
  This event is logged whenever group policy is refreshed and a change in the RSOP (resultant set of policy) of Windows...

**?** -- 
  This event is logged whenever Windows Firewall switches between Domain and Public profiles.

You will usually see th...

**?** -- 
  I routinely see this event logged throughout the day for Teredo and ICMP related rules. 

These rules are defined in...

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  For this event to be produced, auditing for SpecialGroups must first be set up. See Event 4908 for setup.

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  The state of a transaction has changed.

**?** -- 
  Self explanatory.

**?** -- 
  This event is produced when the Windows Firewall Service (MpsSvc)is stopped via the Services MMC.

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  It's strange that this event refers to "Windows Firewall Service" when it is supposed to be a Filtering Platform Conn...

**?** -- 
  This event seems to be logged as a normal course of operation if you have Windows Firewall configured not to provide...

**?** -- 
  The Windows Firewall driver is the the "callout" component of Windows Firewall that works with the Windows Filtering...

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  This is a normal event generated by Windows Firewall rule processing. Microsoft says "This is a normal condition. No...

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  nan

**?** -- 

**?** -- 
  Key file operation

**?** -- 
  Key migration operation

**?** -- 

**?** -- 
  Cryptographic operation.

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  This event is new to Server 2012. It does not appear in earlier versions.

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  This event documents modifications to AD objects, identifying the object, user, attribute modified, thenew value of t...

**?** -- 
  This event documents creations ofAD objects, identifying the object created anduser who created it. 

Of course this...

**?** -- 
  This event has not been observed.

**?** -- 
  This event documents the move ofan AD objects from one OU to another, identifying the object moved anduser whomoved i...

**?** -- 
  Windows logs this event the first time you access a given network share during a given logon session. Be aware that W...

**?** -- 
  This event documents deletion ofAD objects, identifying the object deleted anduser whodeleted it. 

Of course this e...

**?** -- 
  nan

**?** -- 
  A network share object was modified.

**?** -- 
  A network share object was deleted.

**?** -- 
  A network share object was checked to see whether client can be granted desired access

**?** -- 
  This event is new to Server 2012. It does not appear in earlier versions.

**?** -- 
  This event is new to Server 2012. It does not appear in earlier versions.

**?** -- 
  The Windows Filtering Platform has detected a DoS attack and entered a defensive mode; packets associated with this a...

**?** -- 
  The DoS attack has subsided and normal processing is being resumed.

**?** -- 
  The Windows Filtering Platform has blocked a packet.

**?** -- 
  A more restrictive Windows Filtering Platform filter has blocked a packet.

**?** -- 
  This event logs all the particulars about a blocked packet including the filter that caused the block.

Application...

**?** -- 

**?** -- 
  This event documents each time WFP allows a program to begin listening on a TCP or UDP port for incoming connections...

**?** -- 

**?** -- 
  This event documents each time WFP allows a program to connect to another process (on the same or a remote computer)...

**?** -- 
  This event documents each time WFP allows a program to connect to another process (on the same or a remote computer)...

**?** -- 
  This event is logged every time a client or server application binds to a port. Binding is the first step in TCP/UDP...

**?** -- 
  This event is logged every timeWFP prevents aclient or server application binds to a port. Binding is the first step...

**?** -- 
  Spn check for SMB/SMB2 fails.

**?** -- 
  nan

**?** -- 
  We have not yet seen this event

**?** -- 
  Credential Manager is the stored passwords feature in Windows that allows Windows to remember passwords for websites,...

**?** -- 
  Credential Manager is the stored passwords feature in Windows that allows Windows to remember passwords for websites,...

**?** -- 
  This event is probably connected with the "Account is trusted for delegation" account option needed for the applicati...

**?** -- 
  This is event is new in Windows Server 2019.This event occurs when a user performs a read operation on stored credent...

**?** -- 
  This event is new in Windows Server 2019.This event occurs when a user finds stored vault credentials.

**?** -- 
  This event is new in Server 2019.This event occurs when a user enumerates stored vault credentials.

**?** -- 
  This event is new in Server 2019. It is very similar to 5381.This event occurs when a user reads a stored vault crede...

**?** -- 
  I haven't been able to produce this event. Have you? If so, please start a discussion (see above) and post a sample a...

**?** -- 
  This event is logged for each filter of each WFP provider at startup. For more information on WFP and providers see 5...

**?** -- 
  This event is logged for each Windows Filtering Platform Provider present when the base engine starts as part of Wind...

**?** -- 

**?** -- 
  This event is logged for sub-layer of each WFP provider at startup. For more information on WFP and providers see 544...

**?** -- 
  A WFP callout is aet of functions in a driver used for specialized filtering. Callouts can block, permit, modify and...

**?** -- 
  nan

**?** -- 
  This event is logged when a WFP provider is added or there is a change to an existing provider. 

For more informati...

**?** -- 
  A provider context is a blob used by a WFP provider to store its state information. For more information on WFP and p...

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  This event is produced when the IPsec Policy Agent service starts.

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  An object added to the Com+ Catalog

**?** -- 
  This is a useful event.  This event does not just get logged each time Group Policy refreshes.  It only gets logged (...

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 

**?** -- 
  Code Integrity determined that the page hashes of an image file are not valid. The file could be improperly signed wi...

**?** -- 
  BranchCache: Received an incorrectly formatted response while discovering availability of content.

**?** -- 
  BranchCache: Received invalid data from a peer. Data discarded.

**?** -- 
  BranchCache: The message to the hosted cache offering it data is incorrectly formatted.

**?** -- 
  BranchCache: The hosted cache sent an incorrectly formatted response to the client&apos;s message to offer it data.

**?** -- 
  BranchCache: Hosted cache could not be authenticated using the provisioned SSL certificate.

**?** -- 
  BranchCache: %2 instance(s) of event id %1 occurred.

**?** -- 
  %1 registered to Windows Firewall to control filtering for the following: %2.

**?** -- 
  %1

**?** -- 
  Registered product %1 failed and Windows Firewall is now controlling the filtering for %2.

**?** -- 
  This event is new to Server 2012. It does not appear in earlier versions.

**?** -- 
  nan

**?** -- 
  Windows logs at least 1 of these events (observed 6 in the case of a USB flash drive) when you connect a new external...

**?** -- 
  nan

**?** -- 
  Not yet observed

**?** -- 
  This event is generated if a user attempts to disable a device on the system. This event does not mean that a device...

**?** -- 
  This event is generated when a user successfully disables a device.

**?** -- 
  This event is generated if a user attempts to enable a device on the system. This event does not mean that a device w...

**?** -- 
  This event is generated when a user successfully enables a device.

**?** -- 
  Logged as a result of \Computer Configuration\Administrative Templates\System\Device Installation\Device Installation...

**?** -- 
  Microsoft says "This event occurs rarely, and in some situations may be difficult to reproduce."

**?** -- 
  nan

**?** -- 
  Despite the documentation's wording, "Windows NT is shutting down",neither Windows 2000 nor Windows NT logs event 513...

**?** -- 
  Event 514 is logged once at startup for each authentication package on the system. 

An authentication package is a...

**?** -- 
  An occurrence of event 515 is logged at startup and occasionally afterwards for each logon process on the system....

**?** -- 
  Event 516 indicates that an extremely high period of activity prevented Windows from logging %1 number of security ev...

**?** -- 
  Event 517 is logged whenever the Security log is cleared, REGARDLESS of the status of the Audit System Events audit p...

**?** -- 
  An occurrence of Event 518 is logged for each notification package on the system.

**?** -- 
  Event 519 appears in Microsoft documenation but hasn't been confirmed through testing.

**?** -- 
  Process name, explained below, indicates how the time waschanged.

**?** -- 
  This event is logged if Windows was unable to write events to the Security event log.

**?** -- 
  Event 528 is logged whenever an account logs on to the local computer, except for in the event of network logons (see...

**?** -- 
  Event 529 is logged on the workstation or server where the user failed to log on.

**?** -- 
  The logon failed because the user attempted to log on outside the account's hour or day of week restrictions. To dete...

**?** -- 
  Event 531 is logged on the workstation or server where the user failed to log on. To determine if the user was presen...

**?** -- 
  Do not confuse event 532 with password expiration. 

Event 532 is logged on the workstation or server where the user...

**?** -- 
  Event 533 is logged on the workstation or server where the user failed to logon. To determine if the user was present...

**?** -- 
  Event 534 is logged on the workstation or server where the user failed to logon. To determine if the user was present...

**?** -- 
  Event 535 is logged on the workstation or server where the user failed to logon. To determine if the user was present...

**?** -- 
  Event 536 has not been observed.

**?** -- 
  Thanks toIsaac at Prism Microsystems (EventTracker) for this explanation:

**?** -- 
  Ostensibly, event 538 is logged whenever a user logs off, whether from a network connection, interactive logon, or ot...

**?** -- 
  Do not confuse this with event 644. 

This event is logged on the workstation or server where the user failed to log...

**?** -- 
  Event 540 gets logged when a user elsewhere on the network connects to a resource (e.g. shared folder) provided by th...

**?** -- 
  A user that had logged on interactively (type 2) or by terminal services hasstarted the logoff process. Event ID 538...

**?** -- 
  Event 552 is logged when a process logs on as a different account such as when the Scheduled Tasks service starts a t...

**?** -- 
  Events of this category allow you to track failed and successful attempts to access files and other Windows objects....

**?** -- 
  nan

**?** -- 
  After successfully opening an object, a program eventually closes it which is documented by this event. Event 562 hel...

**?** -- 
  Event 563 does not get logged on normal file deletes. MS documentation says "An attempt was made to open an object wi...

**?** -- 
  When an object for which successful delete access has been enabled for auditing, Event 564 is logged upon actual dele...

**?** -- 
  This event varies depending on the OS. 

Win2000 

Event 565 allows you to track changes to Active Directory object...

**?** -- 
  Whereas event 565 logs the permissions requested by user/program, event 566 logs the permissions actually exercised b...

**?** -- 
  Event 567 logs the actual permissions exercised by the user/program on the object after opening it. While event 560 l...

**?** -- 
  Some user rights (aka privileges) are exercised so frequently that the system and security log would quickly become o...

**?** -- 
  Event 577 indicates that the specified user exercised the user right specified in the Privileges field. To understand...

**?** -- 
  This event indicates that the specified user exercised the user right specified in the Privileges field. To understan...

**?** -- 
  This event allows you to monitor each program as it is executed. Image File Name identify) the executable. Prior to w...

**?** -- 
  The program identified in Image File Name was closed or terminated. To find out when the program started, look for th...

**?** -- 
  This simply means that the program obtained another handle to an object (e.g. file) that it already had open under a...

**?** -- 
  Unconfirmed. 

Microsoft's Comments: 

Expected activity.

**?** -- 
  nan

**?** -- 
  This often happens when a service starts or a scheduled task starts under the authority of a different user. You will...

**?** -- 
  A new service was installed by the indicated user and domain. 

Service Name: the internal system name of the new se...

**?** -- 
  This event actually gets logged for both scheduled task creations as well as changes to exisiting tasks. This event d...

**?** -- 
  This event documents a change to user right assignments on this computer. Rights, like most other security settings,...

**?** -- 
  A user right was revoked from the Removed From user or group. See event 608 for a full explanation. 

Note: This eve...

**?** -- 
  This event varies depending on the OS. 

Win2000 

This event gets logged twice (duplicate) by the domain controlle...

**?** -- 
  This event varies depending on the OS. 

Win2000 

This event gets logged twice (duplicate) by the domain controlle...

**?** -- 
  This indicates the system's audit policy was modified. Pluses indicate auditingis enabled, minuses indicate itis disa...

**?** -- 
  This event has not been observed.

**?** -- 
  This event has not been observed.

**?** -- 
  This event varies depending on the OS.

**?** -- 
  See event 615 for W2k

**?** -- 
  W2k logs this event each time the DC applies group policy. W3 corrects this problem and only logs the event when it d...

**?** -- 
  This event gets logged when EFS data recovery agent information is changed. User name will usually correspond to the...

**?** -- 
  This event has not been observed.

**?** -- 
  This event varies depending on the OS. 

Win2000 

It appears this event only gets logged upon trust additions, not...

**?** -- 
  This event documents the grant of logon rights such as "Access this computer from the network" or "Logon as a service...

**?** -- 
  A logon right was revoked from the Removed From user or group. See event 621 for a full explanation. 

Note: This ev...

**?** -- 
  623 does not exist. 806 however does.Windows Server 2003 is supposed to include per user selective auditing but no do...

**?** -- 
  "Caller user" created "new account". This event will be accompanied by at least 2 subsequent event ID 642s and one 627.

**?** -- 
  Despite MS documentation, this event does not get logged by W2k. However W2k does log event 642 and identifies the ty...

**?** -- 
  Despite MS documentation, this event does not get logged by W2k but W3 does log this event correctly. However W2k doe...

**?** -- 
  On Windows 2000, this event gets logged for both succesful and failed attempts for both password changes (user changi...

**?** -- 
  On Windows 2000, this event does not get logged by w2k despite MS documentation. 

This event DOES get logged on Win...

**?** -- 
  Windows logs this event for both user accounts and computer accounts. Computer account names are recognizable by the...

**?** -- 
  Logged when one user (caller user) deletes another user account (target account).

**?** -- 
  Global security group created.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security di...

**?** -- 
  Member added to security global group."Caller user"added "member name"to the "target" group. Member may be a user, co...

**?** -- 
  Member removed from security global group."Caller user" removed "member name" from the "target" group. Member may be...

**?** -- 
  Security global group deletedType: 

AD has 2 types of groups: Security and Distribution. Distribution (security dis...

**?** -- 
  Local security group created.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security dis...

**?** -- 
  Member added to security local group. "Caller user"added "member name"to the "target" group. Member may be a user, co...

**?** -- 
  Member removed from security local group. "Caller user" removed "member name" from the "target" group. Member may be...

**?** -- 
  Security local group deletedType: 

AD has 2 types of groups: Security and Distribution. Distribution (security disa...

**?** -- 
  Security local group changed.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security dis...

**?** -- 
  This event is not confirmed

**?** -- 
  Security global group changed.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security di...

**?** -- 
  "Target" user account was changed by "Caller" user. 

On Windows 2000 and XP, for some types of changes, the event w...

**?** -- 
  This event varies depending on the OS 

Win2000 

W2k logs frequent occurrences of this event even if you haven't c...

**?** -- 
  "Target" user account was locked out because of consecutive failed logon attempts exceeded lockout policy of domain -...

**?** -- 
  "Caller" user created a new computer account. Note that internally Windows appends a $ to all computer account names...

**?** -- 
  "Target"computer account was changed by "Caller" user. For some types of changes the event will include a description...

**?** -- 
  "Caller" user deleted "target" computer account. 

Note, this event also gets logged when a trust relationship is de...

**?** -- 
  Distribution local group created.

**?** -- 
  Distribution local group changed. Type: AD has 2 types of groups: Security and Distribution. Distribution (security d...

**?** -- 
  Member added to distribution local group. "Caller user" removed "member name" from the "target" group. Member may be...

**?** -- 
  Member removed from distribution local group. "Caller user" removed "member name" from the "target" group. Member may...

**?** -- 
  Distribution local group deleted

**?** -- 
  Global distribution group created

**?** -- 
  Distribution global group changed.

**?** -- 
  Member added to distribution global group. "Caller user" removed "member name" from the "target" group. Member may be...

**?** -- 
  Member removed from distribution global group. "Caller user" removed "member name" from the "target" group. Member ma...

**?** -- 
  Distribution global group deleted.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (securit...

**?** -- 
  Security universal group created.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security...

**?** -- 
  Security universal group changed.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (security...

**?** -- 
  Member added to security universal group. "Caller user" removed "member name" from the "target" group. Member may be...

**?** -- 
  Member removed from security universal group. "Caller user" removed "member name" from the "target" group. Member may...

**?** -- 
  Security universal group deleted

**?** -- 
  Distribution universal group created.

**?** -- 
  Distribution universal group changed.Type: 

AD has 2 types of groups: Security and Distribution. Distribution (secu...

**?** -- 
  Member added to distribution universal group. "Caller user" removed "member name" from the "target" group. Member may...

**?** -- 
  Member removed from distribution universal group. "Caller user" removed "member name" from the "target" group. Member...

**?** -- 
  Distribution universal group deleted

Type: 

AD has 2 types of groups: Security and Distribution. Distribution (se...

**?** -- 
  This event gets logged when scope or type of the "target" group is changed by the "caller" user. 

Type: 

AD has 2...

**?** -- 
  This event is not confirmed.

**?** -- 
  This event is not confirmed.

**?** -- 
  This event gets logged twice (duplicated)

**?** -- 
  This event varies depending on the OS. 

Win2000 

This event gets logged on domain controllers only. 

At the beg...

**?** -- 
  This event varies depending on the OS. 

Win2000 

Whereas event ID 672 lets you track initial logons through the g...

**?** -- 
  This event varies depending on the OS. 

Win2000 

Kerberos limits how long a ticket is valid. If a ticket expires...

**?** -- 
  When a user attempts to log on at a workstation and uses a valid domain account name but enters a bad password, the D...

**?** -- 
  This event varies depending on the OS.

Win2000

W2k logs this event when the user's initial logon fails for other...

**?** -- 
  This event varies depending on the OS.

Win2000

Sometimes an attempt to acquire a service ticket fails even though...

**?** -- 
  This event is not confirmed to exist outside MS documentation.

**?** -- 
  This event is not confirmed. Without seeing examples we can't document the meaning of %2 and %1. If you have an examp...

**?** -- 
  This event varies depending on the OS. 

Win2000 

When DC successfully authenticates a user via NTLM (instead of K...

**?** -- 
  This event varies depending on the OS. 

Win2000 

If an NTLM authentication request fails for any reason, W2k logs...

**?** -- 
  Windows logs this event when a user reconnects to a disconnected terminal server session as opposed to a fresh logon...

**?** -- 
  Windows logs this event when a user disconnects from a terminal server (aka remote desktop) session as opposed to an...

**?** -- 
  According to MS documentation: "Every 60 minutes on a domain controller a background thread searches all members of a...

**?** -- 
  When an account name ischanged, the SID remains the same. However the Target ID in this event indicates the new name....

**?** -- 
  This event is not confirmed

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed.These events evidently relate to application groups which are created by application d...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  These events are not confirmed. 

These events evidently relate to application groups which are created by applicati...

**?** -- 
  Microsoft says this is "typical behavior" and can be ignored. I concur. You may frequently see it on SQL Servers.

**?** -- 
  Windows Server 2003 is supposed to include per user selective auditing but no documentation exists from MS. You will...

**?** -- 
  Not confirmed. See event 806 for more information on per user selective auditing. 

See Roger Grimes article at www....

**?** -- 
  A process identified by Process Id registered itself as being able to report events to the Windows security log. See...

**?** -- 
  A process degistered itself as source for reporting events to the security log. See event ID 808

**?** -- 
  This event is logged once each time Windows Firewall start which is usually at boot up. This event documents the high...

**?** -- 
  This isn't really an event per se. It's just logged for each Windows Firewall applicationexception when the firewall...

**?** -- 
  This isn't really an event per se. It's just logged for each Windows Firewall exception when the firewall starts in o...

**?** -- 
  Windows logs this event when an administrator changes the local policy  of the Windows Firewall or a group policy ref...

**?** -- 
  Windows logs this event when an administrator changes the local policy of the Windows Firewall or a group policy refr...

**?** -- 
  Windows logs this event when an administrator changes the local policy  of the Windows Firewall or a group policy ref...

**?** -- 
  Windows logs this event when an administrator changes the local policy   of the Windows Firewall or a group policy re...

**?** -- 
  Windows logs this event when an administrator changes the local policy    of the Windows Firewall or a group policy r...

**?** -- 
  Windows logs this event when an administrator changes the local policy     of the Windows Firewall or a group policy...

**?** -- 
  Windows logs this event when an administrator changes the local  policy  of the Windows Firewall or a group policy re...

**?** -- 
  This event is logged whenever group policy is refreshed and a change in  the RSOP (resultant set of policy) of Window...

**?** -- 
  This event is logged whenever group policy is refreshed and as a result the Windows Firewall policy settings are remo...

**?** -- 
  This event occurs, if the Windows Firewall profile changes from standard to domain and vica versa.

**?** -- 
  This event documents applications that request to open UDP or TCP ports in listening mode and whether the request was...

**?** -- 
  This is a normal event logged at time of shutdown
