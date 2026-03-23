# Linux Auditd Event Types
> Source: Linux Auditd Events | Events: 238


**1000** -- AUDIT_GET
  Get status

**1001** -- AUDIT_SET
  Set status (enable/disable/auditd)

**1002** -- AUDIT_LIST
  List syscall rules -- deprecated

**1003** -- AUDIT_ADD
  Add syscall rule -- deprecated

**1004** -- AUDIT_DEL
  Delete syscall rule -- deprecated

**1005** -- AUDIT_USER
  Message from userspace -- deprecated

**1006** -- AUDIT_LOGIN
  Define the login id and information

**1007** -- AUDIT_WATCH_INS
  Insert file/dir watch entry

**1008** -- AUDIT_WATCH_REM
  Remove file/dir watch entry

**1009** -- AUDIT_WATCH_LIST
  List all file/dir watches

**1010** -- AUDIT_SIGNAL_INFO
  Get info about sender of signal to auditd

**1011** -- AUDIT_ADD_RULE
  Add syscall filtering rule

**1012** -- AUDIT_DEL_RULE
  Delete syscall filtering rule

**1013** -- AUDIT_LIST_RULES
  List syscall filtering rules

**1014** -- AUDIT_TRIM
  Trim junk from watched tree

**1015** -- AUDIT_MAKE_EQUIV
  Append to watched tree

**1016** -- AUDIT_TTY_GET
  Get TTY auditing status

**1017** -- AUDIT_TTY_SET
  Set TTY auditing status

**1018** -- AUDIT_SET_FEATURE
  Turn an audit feature on or off

**1019** -- AUDIT_GET_FEATURE
  Get which features are enabled

**1100** -- AUDIT_FIRST_USER_MSG
  Userspace messages mostly uninteresting to kernel

**1107** -- AUDIT_USER_AVC
  We filter this differently

**1124** -- AUDIT_USER_TTY
  Non-ICANON TTY input meaning

**1199** -- AUDIT_LAST_USER_MSG

**2100** -- AUDIT_FIRST_USER_MSG2
  More user space messages

**2999** -- AUDIT_LAST_USER_MSG2

**1200** -- AUDIT_DAEMON_START
  Daemon startup record

**1201** -- AUDIT_DAEMON_END
  Daemon normal stop record

**1202** -- AUDIT_DAEMON_ABORT
  Daemon error stop record

**1203** -- AUDIT_DAEMON_CONFIG
  Daemon config change

**1300** -- AUDIT_SYSCALL
  Syscall event - records syscall number, arguments, success/fail, uid, gid, pid. Foundation of auditd monitoring. Conf...

**1302** -- AUDIT_PATH
  Filename path information - file path context for syscall events. Essential for understanding which files were access...

**1303** -- AUDIT_IPC
  IPC record

**1304** -- AUDIT_SOCKETCALL
  sys_socketcall arguments - socket operation details. Detect unauthorized network connections, port binding, and raw s...

**1305** -- AUDIT_CONFIG_CHANGE
  Audit system configuration change - changes to audit rules themselves. Attackers modify audit config to hide activity...

**1306** -- AUDIT_SOCKADDR
  Socket address details (SOCKADDR) - captures remote IP:port for network connections. Essential for correlating proces...

**1307** -- AUDIT_CWD
  Current working directory for syscall events. Provides path context. Processes executing from /tmp, /dev/shm, or /var...

**1309** -- AUDIT_EXECVE
  EXECVE - captures full command line of executed programs. Essential for detecting malicious commands, encoded payload...

**1311** -- AUDIT_IPC_SET_PERM
  IPC new permissions record type

**1312** -- AUDIT_MQ_OPEN
  POSIX MQ open record type

**1313** -- AUDIT_MQ_SENDRECV
  POSIX MQ send/receive record type

**1314** -- AUDIT_MQ_NOTIFY
  POSIX MQ notify record type

**1315** -- AUDIT_MQ_GETSETATTR
  POSIX MQ get/set attribute record type

**1316** -- AUDIT_KERNEL_OTHER
  For use by 3rd party kernel modules. Custom audit messages from loaded kernel modules. May indicate rootkit activity...

**1317** -- AUDIT_FD_PAIR
  audit record for pipe/socketpair

**1318** -- AUDIT_OBJ_PID
  ptrace target (OBJ_PID) - identifies the target process of ptrace operations. Ptrace is used for debugging but also f...

**1319** -- AUDIT_TTY
  Input on an administrative TTY - captures keystrokes on admin terminals. Essential for detecting unauthorized interac...

**1320** -- AUDIT_EOE
  End of multi-record event

**1321** -- AUDIT_BPRM_FCAPS
  Information about fcaps increasing perms

**1322** -- AUDIT_CAPSET
  CAPSET - records capability changes via sys_capset. Granting CAP_SYS_ADMIN, CAP_NET_RAW, CAP_SYS_PTRACE to unexpected...

**1323** -- AUDIT_MMAP
  MMAP record - memory mapping operations. Detect executable memory mappings from anonymous pages (potential shellcode)...

**1324** -- AUDIT_NETFILTER_PKT
  Packets traversing netfilter chains

**1325** -- AUDIT_NETFILTER_CFG
  Netfilter chain modifications - firewall rule changes. Attackers modify iptables/nftables rules to open access or red...

**1326** -- AUDIT_SECCOMP
  SECCOMP event - seccomp-bpf filter violations. Processes violating their sandbox indicate exploitation attempts or mi...

**1327** -- AUDIT_PROCTITLE
  PROCTITLE - full process command line in hex-encoded format. Complements EXECVE for complete execution visibility. Su...

**1328** -- AUDIT_FEATURE_CHANGE
  audit log listing feature changes

**1329** -- AUDIT_REPLACE
  Replace auditd if this packet unanswerd

**1330** -- AUDIT_KERN_MODULE
  Kernel module events - loading/unloading kernel modules. Detect rootkit installation (insmod/modprobe of unknown modu...

**1331** -- AUDIT_FANOTIFY
  Fanotify access decision

**1332** -- AUDIT_TIME_INJOFFSET
  Timekeeping offset injected

**1333** -- AUDIT_TIME_ADJNTPVAL
  NTP value adjustment

**1334** -- AUDIT_BPF
  BPF subsystem events - eBPF program loading. Malicious eBPF programs can intercept network traffic, hide processes, a...

**1335** -- AUDIT_EVENT_LISTENER
  Task joined multicast read socket

**1336** -- AUDIT_URINGOP
  io_uring operation

**1337** -- AUDIT_OPENAT2
  Record showing openat2 how args

**1338** -- AUDIT_DM_CTRL
  Device Mapper target control

**1339** -- AUDIT_DM_EVENT
  Device Mapper events

**1400** -- AUDIT_AVC
  SELinux AVC denial or grant - mandatory access control decisions. Denials may indicate exploitation attempts hitting...

**1401** -- AUDIT_SELINUX_ERR
  Internal SE Linux Errors

**1402** -- AUDIT_AVC_PATH
  dentry, vfsmount pair from avc

**1403** -- AUDIT_MAC_POLICY_LOAD
  MAC policy file load - SELinux/AppArmor policy changes. Policy reloads may weaken enforcement. Monitor for policy cha...

**1404** -- AUDIT_MAC_STATUS
  MAC status changed - SELinux mode changes between enforcing, permissive, and disabled. Switching to permissive or dis...

**1405** -- AUDIT_MAC_CONFIG_CHANGE
  Changes to booleans

**1406** -- AUDIT_MAC_UNLBL_ALLOW
  NetLabel: allow unlabeled traffic

**1407** -- AUDIT_MAC_CIPSOV4_ADD
  NetLabel: add CIPSOv4 DOI entry

**1408** -- AUDIT_MAC_CIPSOV4_DEL
  NetLabel: del CIPSOv4 DOI entry

**1409** -- AUDIT_MAC_MAP_ADD
  NetLabel: add LSM domain mapping

**1410** -- AUDIT_MAC_MAP_DEL
  NetLabel: del LSM domain mapping

**1411** -- AUDIT_MAC_IPSEC_ADDSA
  Not used

**1412** -- AUDIT_MAC_IPSEC_DELSA
  Not used

**1413** -- AUDIT_MAC_IPSEC_ADDSPD
  Not used

**1414** -- AUDIT_MAC_IPSEC_DELSPD
  Not used

**1415** -- AUDIT_MAC_IPSEC_EVENT
  Audit an IPSec event

**1416** -- AUDIT_MAC_UNLBL_STCADD
  NetLabel: add a static label

**1417** -- AUDIT_MAC_UNLBL_STCDEL
  NetLabel: del a static label

**1418** -- AUDIT_MAC_CALIPSO_ADD
  NetLabel: add CALIPSO DOI entry

**1419** -- AUDIT_MAC_CALIPSO_DEL
  NetLabel: del CALIPSO DOI entry

**1420** -- AUDIT_IPE_ACCESS
  IPE denial or grant

**1421** -- AUDIT_IPE_CONFIG_CHANGE
  IPE config change

**1422** -- AUDIT_IPE_POLICY_LOAD
  IPE policy load

**1423** -- AUDIT_LANDLOCK_ACCESS
  Landlock denial

**1424** -- AUDIT_LANDLOCK_DOMAIN
  Landlock domain status

**1425** -- AUDIT_MAC_TASK_CONTEXTS
  Multiple LSM task contexts

**1426** -- AUDIT_MAC_OBJ_CONTEXTS
  Multiple LSM objext contexts

**1700** -- AUDIT_FIRST_KERN_ANOM_MSG
  ANOM_PROMISCUOUS - network interface entered promiscuous mode. Potential packet sniffing or network reconnaissance. L...

**1799** -- AUDIT_LAST_KERN_ANOM_MSG

**1700** -- AUDIT_ANOM_PROMISCUOUS
  ANOM_PROMISCUOUS - network interface entered promiscuous mode. Potential packet sniffing or network reconnaissance. L...

**1701** -- AUDIT_ANOM_ABEND
  ANOM_ABEND - process ended abnormally (crash). Repeated crashes may indicate exploitation attempts (buffer overflow,...

**1702** -- AUDIT_ANOM_LINK
  ANOM_LINK - suspicious use of file links. Symlink/hardlink attacks for privilege escalation (e.g., linking to /etc/sh...

**1703** -- AUDIT_ANOM_CREAT
  ANOM_CREAT - suspicious file creation in monitored directories. Files created in /tmp, /dev/shm with executable permi...

**1800** -- AUDIT_INTEGRITY_DATA
  INTEGRITY_DATA - data integrity verification (IMA). File content integrity check results. Failures indicate tampered...

**1801** -- AUDIT_INTEGRITY_METADATA
  Metadata integrity verification

**1802** -- AUDIT_INTEGRITY_STATUS
  Integrity enable status

**1803** -- AUDIT_INTEGRITY_HASH
  Integrity HASH type

**1804** -- AUDIT_INTEGRITY_PCR
  PCR invalidation msgs

**1805** -- AUDIT_INTEGRITY_RULE
  policy rule

**1806** -- AUDIT_INTEGRITY_EVM_XATTR
  New EVM-covered xattr

**1807** -- AUDIT_INTEGRITY_POLICY_RULE
  IMA policy rules

**1808** -- AUDIT_INTEGRITY_USERSPACE
  Userspace enforced data integrity

**2000** -- AUDIT_KERNEL
  Asynchronous audit record. NOT A REQUEST.

**0** -- AUDIT_FILTER_USER
  Apply rule to user-generated messages

**0** -- AUDIT_FILTER_TASK
  Apply rule at task creation (not syscall)

**0** -- AUDIT_FILTER_ENTRY
  Apply rule at syscall entry

**0** -- AUDIT_FILTER_WATCH
  Apply rule to file system watches

**0** -- AUDIT_FILTER_EXIT
  Apply rule at syscall exit

**0** -- AUDIT_FILTER_EXCLUDE
  Apply rule before record creation

**0** -- AUDIT_FILTER_FS
  Apply rule at __audit_inode_child

**0** -- AUDIT_FILTER_URING_EXIT
  Apply rule at io_uring op exit

**8** -- AUDIT_NR_FILTERS

**0** -- AUDIT_FILTER_PREPEND
  Prepend to front of list

**0** -- AUDIT_NEVER
  Do not build context if rule matches

**1** -- AUDIT_POSSIBLE
  Build context if rule matches

**2** -- AUDIT_ALWAYS
  Generate audit record if rule matches

**64** -- AUDIT_MAX_FIELDS

**256** -- AUDIT_MAX_KEY_LEN

**64** -- AUDIT_BITMASK_SIZE

**16** -- AUDIT_SYSCALL_CLASSES

**0** -- AUDIT_CLASS_DIR_WRITE

**1** -- AUDIT_CLASS_DIR_WRITE_32

**2** -- AUDIT_CLASS_CHATTR

**3** -- AUDIT_CLASS_CHATTR_32

**4** -- AUDIT_CLASS_READ

**5** -- AUDIT_CLASS_READ_32

**6** -- AUDIT_CLASS_WRITE

**7** -- AUDIT_CLASS_WRITE_32

**8** -- AUDIT_CLASS_SIGNAL

**9** -- AUDIT_CLASS_SIGNAL_32

**0** -- AUDIT_UNUSED_BITS

**1** -- AUDIT_COMPARE_UID_TO_OBJ_UID

**2** -- AUDIT_COMPARE_GID_TO_OBJ_GID

**3** -- AUDIT_COMPARE_EUID_TO_OBJ_UID

**4** -- AUDIT_COMPARE_EGID_TO_OBJ_GID

**5** -- AUDIT_COMPARE_AUID_TO_OBJ_UID

**6** -- AUDIT_COMPARE_SUID_TO_OBJ_UID

**7** -- AUDIT_COMPARE_SGID_TO_OBJ_GID

**8** -- AUDIT_COMPARE_FSUID_TO_OBJ_UID

**9** -- AUDIT_COMPARE_FSGID_TO_OBJ_GID

**10** -- AUDIT_COMPARE_UID_TO_AUID

**11** -- AUDIT_COMPARE_UID_TO_EUID

**12** -- AUDIT_COMPARE_UID_TO_FSUID

**13** -- AUDIT_COMPARE_UID_TO_SUID

**14** -- AUDIT_COMPARE_AUID_TO_FSUID

**15** -- AUDIT_COMPARE_AUID_TO_SUID

**16** -- AUDIT_COMPARE_AUID_TO_EUID

**17** -- AUDIT_COMPARE_EUID_TO_SUID

**18** -- AUDIT_COMPARE_EUID_TO_FSUID

**19** -- AUDIT_COMPARE_SUID_TO_FSUID

**20** -- AUDIT_COMPARE_GID_TO_EGID

**21** -- AUDIT_COMPARE_GID_TO_FSGID

**22** -- AUDIT_COMPARE_GID_TO_SGID

**23** -- AUDIT_COMPARE_EGID_TO_FSGID

**24** -- AUDIT_COMPARE_EGID_TO_SGID

**25** -- AUDIT_COMPARE_SGID_TO_FSGID

**0** -- AUDIT_PID

**1** -- AUDIT_UID

**2** -- AUDIT_EUID

**3** -- AUDIT_SUID

**4** -- AUDIT_FSUID

**5** -- AUDIT_GID

**6** -- AUDIT_EGID

**7** -- AUDIT_SGID

**8** -- AUDIT_FSGID

**9** -- AUDIT_LOGINUID

**10** -- AUDIT_PERS

**11** -- AUDIT_ARCH

**12** -- AUDIT_MSGTYPE

**13** -- AUDIT_SUBJ_USER
  security label user

**14** -- AUDIT_SUBJ_ROLE
  security label role

**15** -- AUDIT_SUBJ_TYPE
  security label type

**16** -- AUDIT_SUBJ_SEN
  security label sensitivity label

**17** -- AUDIT_SUBJ_CLR
  security label clearance label

**18** -- AUDIT_PPID

**19** -- AUDIT_OBJ_USER

**20** -- AUDIT_OBJ_ROLE

**21** -- AUDIT_OBJ_TYPE

**22** -- AUDIT_OBJ_LEV_LOW

**23** -- AUDIT_OBJ_LEV_HIGH

**24** -- AUDIT_LOGINUID_SET

**25** -- AUDIT_SESSIONID
  Session ID

**26** -- AUDIT_FSTYPE
  FileSystem Type

**100** -- AUDIT_DEVMAJOR

**101** -- AUDIT_DEVMINOR

**102** -- AUDIT_INODE

**103** -- AUDIT_EXIT

**104** -- AUDIT_SUCCESS
  exit >= 0; value ignored

**105** -- AUDIT_WATCH

**106** -- AUDIT_PERM

**107** -- AUDIT_DIR

**108** -- AUDIT_FILETYPE

**109** -- AUDIT_OBJ_UID

**110** -- AUDIT_OBJ_GID

**111** -- AUDIT_FIELD_COMPARE

**112** -- AUDIT_EXE

**113** -- AUDIT_SADDR_FAM

**200** -- AUDIT_ARG0

**210** -- AUDIT_FILTERKEY

**0** -- AUDIT_NEGATE

**0** -- AUDIT_BIT_MASK

**0** -- AUDIT_LESS_THAN

**0** -- AUDIT_GREATER_THAN

**0** -- AUDIT_NOT_EQUAL

**0** -- AUDIT_EQUAL

**0** -- AUDIT_STATUS_ENABLED

**0** -- AUDIT_STATUS_FAILURE

**0** -- AUDIT_STATUS_PID

**0** -- AUDIT_STATUS_RATE_LIMIT

**0** -- AUDIT_STATUS_BACKLOG_LIMIT

**0** -- AUDIT_STATUS_BACKLOG_WAIT_TIME

**0** -- AUDIT_STATUS_LOST

**0** -- AUDIT_STATUS_BACKLOG_WAIT_TIME_ACTUAL

**0** -- AUDIT_FEATURE_BITMAP_BACKLOG_LIMIT

**0** -- AUDIT_FEATURE_BITMAP_BACKLOG_WAIT_TIME

**0** -- AUDIT_FEATURE_BITMAP_EXECUTABLE_PATH

**0** -- AUDIT_FEATURE_BITMAP_EXCLUDE_EXTEND

**0** -- AUDIT_FEATURE_BITMAP_SESSIONID_FILTER

**0** -- AUDIT_FEATURE_BITMAP_LOST_RESET

**0** -- AUDIT_FEATURE_BITMAP_FILTER_FS

**0** -- AUDIT_FAIL_SILENT

**1** -- AUDIT_FAIL_PRINTK

**2** -- AUDIT_FAIL_PANIC

**1** -- AUDIT_PERM_EXEC

**2** -- AUDIT_PERM_WRITE

**4** -- AUDIT_PERM_READ

**8** -- AUDIT_PERM_ATTR

**8560** -- AUDIT_MESSAGE_TEXT_MAX

**1** -- AUDIT_FEATURE_VERSION

**0** -- AUDIT_FEATURE_ONLY_UNSET_LOGINUID

**1** -- AUDIT_FEATURE_LOGINUID_IMMUTABLE
