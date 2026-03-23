# Cisco ASA Syslog Message IDs
> Source: Cisco ASA Syslog | Events: 488


## Index

- [Access Control/ACL](#access-control-acl)
- [Application Bypass](#application-bypass)
- [Application Inspection (FTP)](#application-inspection-ftp)
- [Application Inspection (SIP)](#application-inspection-sip)
- [Application Inspection (Skinny)](#application-inspection-skinny)
- [Application Inspection (URL/Web)](#application-inspection-url-web)
- [ARP/Layer2](#arp-layer2)
- [ASDM Management](#asdm-management)
- [Authentication](#authentication)
- [Certificate/PKI](#certificate-pki)
- [Cluster/VPN Redistribution](#cluster-vpn-redistribution)
- [Connection Build/Teardown](#connection-build-teardown)
- [Connection Limits](#connection-limits)
- [Content Filtering](#content-filtering)
- [DHCP](#dhcp)
- [DNS Inspection](#dns-inspection)
- [Failover Configuration](#failover-configuration)
- [Failover/HA](#failover-ha)
- [Flow Offload](#flow-offload)
- [Hardware Monitoring](#hardware-monitoring)
- [ICMP](#icmp)
- [IDS/IPS Signatures](#ids-ips-signatures)
- [IKE/IPsec VPN Negotiation](#ike-ipsec-vpn-negotiation)
- [IKEv2](#ikev2)
- [Interface Status](#interface-status)
- [IP Fragmentation](#ip-fragmentation)
- [IPsec/Crypto](#ipsec-crypto)
- [Layer2/Bridging](#layer2-bridging)
- [Link-State Propagation](#link-state-propagation)
- [Logging](#logging)
- [Management Access](#management-access)
- [NAT/Connection Limits](#nat-connection-limits)
- [NAT/Translation](#nat-translation)
- [Network State](#network-state)
- [NTP](#ntp)
- [Object-Group Search](#object-group-search)
- [Policy-Based Routing](#policy-based-routing)
- [Protocol Inspection](#protocol-inspection)
- [Protocol Inspection (RTSP)](#protocol-inspection-rtsp)
- [Protocol Inspection (SSH)](#protocol-inspection-ssh)
- [Routing (OSPF)](#routing-ospf)
- [Routing (RIP)](#routing-rip)
- [Security Context](#security-context)
- [Shunning](#shunning)
- [SSL VPN/SVC](#ssl-vpn-svc)
- [SSL/TLS](#ssl-tls)
- [Stateful Failover](#stateful-failover)
- [Stateful Failover Replication](#stateful-failover-replication)
- [System](#system)
- [System Resources](#system-resources)
- [System Resources (Hardware)](#system-resources-hardware)
- [System Resources (PPTP/L2TP)](#system-resources-pptp-l2tp)
- [System Resources (SNMP)](#system-resources-snmp)
- [Threat Detection](#threat-detection)
- [TrustSec/SGT](#trustsec-sgt)
- [Tunneling (PPTP/L2TP/PPPoE)](#tunneling-pptp-l2tp-pppoe)
- [User Management](#user-management)
- [VPN Tunnels](#vpn-tunnels)
- [VPN/IPsec](#vpn-ipsec)
- [VXLAN](#vxlan)
- [WebVPN/AnyConnect](#webvpn-anyconnect)


### Access Control/ACL

**106001** -- ASA-2-106001
  Inbound TCP connection denied

**106002** -- ASA-2-106002
  Connection denied by outbound list

**106006** -- ASA-2-106006
  Deny inbound UDP packet

**106007** -- ASA-2-106007
  Deny inbound UDP DNS query or response

**106010** -- ASA-3-106010
  Deny inbound connection by security policy

**106011** -- ASA-3-106011
  Deny inbound with no translation entry

**106012** -- ASA-6-106012
  IP packet with options discarded

**106013** -- ASA-2-106013
  Dropping ICMP Echo to PAT address

**106014** -- ASA-3-106014
  Deny inbound ICMP packet

**106015** -- ASA-6-106015
  Deny TCP with no connection state

**106016** -- ASA-2-106016
  Deny IP spoof attempt

**106017** -- ASA-2-106017
  Deny IP Land Attack

**106018** -- ASA-2-106018
  ICMP denied by outbound list

**106020** -- ASA-2-106020
  Deny IP teardrop fragment attack

**106021** -- ASA-1-106021
  Deny reverse path check failure

**106022** -- ASA-1-106022
  Deny connection spoof attempt

**106023** -- ASA-4-106023
  Deny by access-list for source

**106024** -- ASA-2-106024
  Access rules memory exhausted

**106025** -- ASA-6-106025
  Failed to determine security context

**106026** -- ASA-6-106026
  Failed to determine security context

**106027** -- ASA-4-106027
  Deny non-IP packet by access-group

**106100** -- ASA-6-106100
  Access-list permits or denies traffic

**106101** -- ASA-1-106101
  Cached deny-flows for ACL log limit reached

**106102** -- ASA-1-106102
  VPN filter access-list permit or deny

**106103** -- ASA-4-106103
  VPN filter access-list denies traffic

### Application Bypass

**850001** -- ASA-3-850001
  Auto-Application-Bypass triggered due to packet delay

**850002** -- ASA-3-850002
  Auto-Application-Bypass triggered, SNORT not responding

### Application Inspection (FTP)

**303002** -- ASA-6-303002
  FTP file upload or download completed

**303004** -- ASA-5-303004
  Unsupported FTP command failed strict inspection

**303005** -- ASA-5-303005
  Strict FTP inspection matched configured policy action

### Application Inspection (SIP)

**607001** -- ASA-6-607001
  SIP secondary channel preallocated

**607002** -- ASA-4-607002
  SIP classification criteria satisfied

**607003** -- ASA-6-607003
  SIP classification standalone log action

### Application Inspection (Skinny)

**608001** -- ASA-6-608001
  Skinny secondary channel preallocated

**608002** -- ASA-4-608002
  Skinny message dropped, SCCP prefix too small

**608003** -- ASA-4-608003
  Skinny message dropped, SCCP prefix too large

**608004** -- ASA-4-608004
  Skinny message dropped, message ID not allowed

**608005** -- ASA-4-608005
  Skinny message dropped, endpoint registration incomplete

### Application Inspection (URL/Web)

**304001** -- ASA-5-304001
  Host accessed specified URL

**304002** -- ASA-5-304002
  Access to URL or FTP site was denied

**304003** -- ASA-3-304003
  URL server timed out

**304004** -- ASA-6-304004
  Websense server request failed

**304005** -- ASA-7-304005
  Websense server request pending

**304006** -- ASA-3-304006
  Websense server unavailable for access

**304007** -- ASA-2-304007
  URL server not responding, entering allow mode

**304008** -- ASA-2-304008
  Exiting allow mode, URL server is up

**304009** -- ASA-7-304009
  URL pending buffer block space exhausted

### ARP/Layer2

**405001** -- ASA-4-405001
  ARP packet with MAC different from cache entry

**405002** -- ASA-4-405002
  Packet with mismatched MAC for authenticated host

**405003** -- ASA-4-405003
  IP address collision between host and interface

### ASDM Management

**606001** -- ASA-6-606001
  ASDM administrator session authenticated

**606002** -- ASA-6-606002
  ASDM session ended

**606003** -- ASA-6-606003
  ASDM logging connection started

**606004** -- ASA-6-606004
  ASDM logging connection terminated

### Authentication

**308001** -- ASA-6-308001
  Console enable password incorrect after multiple tries

**308002** -- ASA-4-308002
  Static command IP addresses overlap

**308003** -- ASA-4-308003
  Enable password is not configured warning

**308004** -- ASA-4-308004
  Enable password configured by user

**605004** -- ASA-6-605004
  Login denied due to incorrect credentials

**605005** -- ASA-6-605005
  User successfully authenticated and session started

**611101** -- ASA-6-611101
  User authentication succeeded for firewall

**611102** -- ASA-6-611102
  User authentication failed for firewall

**611103** -- ASA-5-611103
  User logged out from firewall

**611104** -- ASA-5-611104
  Serial console idle timeout exceeded

### Certificate/PKI

**717001** -- ASA-3-717001
  Querying keypair failed during enrollment

**717002** -- ASA-3-717002
  Certificate enrollment failed for trustpoint

**717003** -- ASA-6-717003
  Certificate received from CA for trustpoint

**717006** -- ASA-6-717006
  PKCS 12 import failed for trustpoint

### Cluster/VPN Redistribution

**8300001** -- ASA-6-8300001
  VPN session redistribution operation started/completed

**8300002** -- ASA-6-8300002
  Active sessions moved to cluster member

**8300003** -- ASA-3-8300003
  Failed to send session redistribution message

### Connection Build/Teardown

**302003** -- ASA-6-302003
  Built H245 connection for Intel Internet Phone

**302004** -- ASA-6-302004
  Pre-allocated H323 UDP back connection

**302010** -- ASA-6-302010
  Provides connection usage statistics

**302012** -- ASA-6-302012
  Pre-allocated H225 Call Signalling Connection

**302013** -- ASA-6-302013
  Built TCP connection between two hosts

**302014** -- ASA-6-302014
  TCP connection terminated between hosts

**302015** -- ASA-6-302015
  Built UDP connection between two hosts

**302016** -- ASA-6-302016
  UDP connection deleted between hosts

**302017** -- ASA-6-302017
  Built GRE connection between two hosts

**302018** -- ASA-6-302018
  GRE connection deleted between hosts

**302019** -- ASA-3-302019
  H.323 ASN Library initialization failed

**302020** -- ASA-6-302020
  Built ICMP connection in fast-path

**302021** -- ASA-6-302021
  ICMP session removed in fast-path

**302022** -- ASA-6-302022
  Built TCP director/backup/forwarder flow

**302023** -- ASA-6-302023
  TCP director/backup/forwarder flow torn down

**302024** -- ASA-6-302024
  Built UDP director/backup/forwarder flow

**302025** -- ASA-6-302025
  UDP director/backup/forwarder flow torn down

**302026** -- ASA-6-302026
  Built ICMP director/backup/forwarder flow

**302027** -- ASA-6-302027
  ICMP director/backup/forwarder flow torn down

**302033** -- ASA-6-302033
  Pre-allocated H323 GUP connection

**302034** -- ASA-4-302034
  Failed to allocate H323 GUP connection

**302035** -- ASA-6-302035
  Built SCTP connection between hosts

**302036** -- ASA-6-302036
  SCTP connection deleted between hosts

**302037** -- ASA-6-302037
  Built IPINIP connection between hosts

**302038** -- ASA-6-302038
  IPINIP connection torn down between hosts

**302302** -- ASA-3-302302
  IPsec proxy mismatch with deny ACL policy

**302303** -- ASA-6-302303
  Built TCP state-bypass connection bypassing checks

**302304** -- ASA-6-302304
  TCP state-bypass connection terminated

**302305** -- ASA-6-302305
  Built SCTP state-bypass connection with bypass enabled

**302306** -- ASA-6-302306
  SCTP state-bypass connection deleted

**302310** -- ASA-4-302310
  SCTP packet contains unsupported Hostname Parameter

**302311** -- ASA-4-302311
  Failed to create connection due to app-cache memory failure

### Connection Limits

**201002** -- ASA-3-201002
  Too many TCP connections on static/xlate global address

**201003** -- ASA-2-201003
  Embryonic connection limit exceeded for static global address

**201004** -- ASA-3-201004
  Too many UDP connections on static/xlate global address

**201005** -- ASA-3-201005
  FTP data connection failed due to insufficient memory

**201006** -- ASA-3-201006
  RCMD backconnection failed due to insufficient memory

**201008** -- ASA-3-201008
  New connections disallowed when syslog server unreachable

**201009** -- ASA-3-201009
  TCP connection limit for host exceeded on interface

**201010** -- ASA-6-201010
  Embryonic connection limit exceeded for traffic class

**201011** -- ASA-3-201011
  Connection limit exceeded for packet on interface

**201012** -- ASA-6-201012
  Per-client embryonic connection limit exceeded

**201013** -- ASA-3-201013
  Per-client connection limit exceeded

### Content Filtering

**500001** -- ASA-5-500001
  ActiveX content modified by filtering

**500002** -- ASA-5-500002
  Java content modified by filtering

**500003** -- ASA-5-500003
  TCP header length validation error

**500004** -- ASA-4-500004
  Invalid transport field with zero port number

**500005** -- ASA-3-500005
  Incompatible inspection and filter combination

**500006** -- ASA-4-500006
  Staleness in pinhole flows due to timeout

### DHCP

**604101** -- ASA-6-604101
  DHCP client obtained IP from server

**604102** -- ASA-6-604102
  DHCP client released IP address

**604103** -- ASA-6-604103
  DHCP server granted IP to external client

**604104** -- ASA-6-604104
  External client released IP to DHCP server

### DNS Inspection

**410001** -- ASA-4-410001
  Dropped UDP DNS request, label length exceeds limit

**410002** -- ASA-2-410002
  Excess DNS responses with mismatched identifier

**410003** -- ASA-4-410003
  DNS classification performed and action taken

**410004** -- ASA-6-410004
  DNS classification criteria satisfied

### Failover Configuration

**109001** -- ASA-1-109001
  Failover feature not enabled

**109002** -- ASA-1-109002
  Received failover command

**109003** -- ASA-1-109003
  Received failover reset command

**109005** -- ASA-1-109005
  Failover LAN failover interface specified

**109006** -- ASA-1-109006
  Primary unit acquired

**109007** -- ASA-1-109007
  Secondary unit acquired

**109008** -- ASA-1-109008
  Failover LAN interface changed

**109010** -- ASA-1-109010
  Failover command interface specified

**109011** -- ASA-1-109011
  Primary firewall unit acquired

**109012** -- ASA-1-109012
  Secondary firewall unit acquired

**109013** -- ASA-1-109013
  Failover command interface changed

**109014** -- ASA-1-109014
  Failover unit acquired by nameif

**109016** -- ASA-1-109016
  Hello interval set

**109017** -- ASA-1-109017
  Holdover interval set

**109018** -- ASA-1-109018
  Failover threshold set

**109019** -- ASA-1-109019
  Failover polling interval changed

**109020** -- ASA-1-109020
  Failover hold-time changed

**109021** -- ASA-1-109021
  Failed to setup failover interface

**109022** -- ASA-1-109022
  Failed to change failover configuration

**109023** -- ASA-1-109023
  Failover cable not connected

**109024** -- ASA-1-109024
  Failover configuration changed

**109025** -- ASA-1-109025
  Failover LAN interface specified as failover

**109026** -- ASA-1-109026
  Failover statistics reset

**109027** -- ASA-1-109027
  Failover statistics display

**109028** -- ASA-1-109028
  Failover role changed

**109029** -- ASA-1-109029
  Failover unit state changed

**109030** -- ASA-1-109030
  Active unit status reported

**109031** -- ASA-1-109031
  Standby unit status reported

**109032** -- ASA-1-109032
  Failover pair synchronized

**109033** -- ASA-1-109033
  Failover unit entered OK state

**109034** -- ASA-1-109034
  Failover unit entered failed state

**109035** -- ASA-1-109035
  Failover unit status unknown

**109036** -- ASA-1-109036
  Primary firewall specified as active

### Failover/HA

**101001** -- ASA-1-101001
  Failover cable present and functioning correctly

**101002** -- ASA-1-101002
  Failover cable present but not functioning correctly

**101003** -- ASA-1-101003
  Failover cable not connected to primary unit

**101004** -- ASA-1-101004
  Failover cable not connected to secondary unit

**101005** -- ASA-1-101005
  Error reading failover cable status

**103001** -- ASA-1-103001
  No response from other firewall with reason code

**103002** -- ASA-1-103002
  Other firewall network interface OK

**103003** -- ASA-1-103003
  Other firewall network interface failed

**103004** -- ASA-1-103004
  Other firewall reports this firewall failed

**103005** -- ASA-1-103005
  Other firewall reporting SSM card failure

**103006** -- ASA-1-103006
  Mate version not compatible with ours

**103007** -- ASA-1-103007
  Mate version not identical but compatible

**103008** -- ASA-1-103008
  Mate hwdib index not identical

**104001** -- ASA-1-104001
  Switching to ACTIVE state

**104002** -- ASA-1-104002
  Switching to STANDBY state

**104003** -- ASA-1-104003
  Primary unit has failed

**104004** -- ASA-1-104004
  Previously failed unit now operating

**104500** -- ASA-1-104500
  Switching to ACTIVE for Cloud HA pair

**104501** -- ASA-1-104501
  Switching to BACKUP for Cloud HA pair

**104502** -- ASA-1-104502
  Becoming Backup unit failed for Cloud HA

**105001** -- ASA-1-105001
  Failover has been automatically disabled

**105002** -- ASA-1-105002
  Failover has been enabled

**105003** -- ASA-1-105003
  Testing specified network interface

**105004** -- ASA-1-105004
  Network interface test successful

**105005** -- ASA-1-105005
  Lost failover communications with peer

**105006** -- ASA-1-105006
  Link status UP on interface

**105007** -- ASA-1-105007
  Link status DOWN on interface

**105008** -- ASA-1-105008
  Testing specified network interface

**105009** -- ASA-1-105009
  Interface test passed or failed

**105010** -- ASA-3-105010
  Failover message block allocation failed

**105011** -- ASA-1-105011
  Failover cable communication failure

**105020** -- ASA-1-105020
  Incomplete or slow config replication detected

**105021** -- ASA-1-105021
  Standby unit failed to sync due to locked config

**105022** -- ASA-1-105022
  Config replication failed with specified reason

**105031** -- ASA-1-105031
  LAN failover interface link is up

**105032** -- ASA-1-105032
  LAN failover interface link is down

**105033** -- ASA-1-105033
  LAN failover interface down and up again

**105034** -- ASA-1-105034
  Received LAN_FAILOVER_UP message from peer

**105035** -- ASA-1-105035
  Received LAN failover interface down from peer

**105036** -- ASA-1-105036
  Dropped unacknowledged LAN failover message

**105037** -- ASA-1-105037
  Units switching back and forth as active

**105038** -- ASA-1-105038
  Interface count mismatch detected

**105039** -- ASA-1-105039
  Unable to verify interface count with mate

**105040** -- ASA-1-105040
  Mate failover version not compatible

**105041** -- ASA-1-105041
  Command replication failed during sync

**105042** -- ASA-1-105042
  Failover interface restored to OK status

**105043** -- ASA-1-105043
  Failover interface failed

**105044** -- ASA-1-105044
  Mate operational mode not compatible

**105045** -- ASA-1-105045
  Mate license not compatible

**105046** -- ASA-1-105046
  Mate has different chassis type

**105047** -- ASA-1-105047
  Mate has different card in slot

**105048** -- ASA-1-105048
  Mate service module different from ours

**105050** -- ASA-3-105050
  Standby unit has fewer Ethernet interfaces

**105052** -- ASA-3-105052
  Weaker cipher in use when stronger available

**105500** -- ASA-5-105500
  Cloud HA enabled on this ASA Virtual

**105501** -- ASA-5-105501
  Cloud HA disabled on this ASA Virtual

**105502** -- ASA-1-105502
  Restarting Cloud HA for specified reason

**105503** -- ASA-5-105503
  Internal HA state changed

**105504** -- ASA-5-105504
  Connected to HA peer

**105505** -- ASA-4-105505
  Failed to connect to HA peer

### Flow Offload

**805001** -- ASA-6-805001
  Flow offloaded to super-fast path

**805002** -- ASA-6-805002
  Flow no longer offloaded from super-fast path

### Hardware Monitoring

**806001** -- ASA-6-806001
  CPU temperature high alarm threshold reached

### ICMP

**313001** -- ASA-3-313001
  ICMP packet denied by access list

**313004** -- ASA-4-313004
  ICMP denied, no matching session found

**313005** -- ASA-4-313005
  ICMP error message not related to established session

**313008** -- ASA-3-313008
  IPv6-ICMP packet denied by access list

**313009** -- ASA-4-313009
  ICMP echo with invalid code denied

### IDS/IPS Signatures

**400000** -- ASA-4-400000
  IP options-Bad Option List

**400001** -- ASA-4-400001
  IP options-Record Packet Route

**400002** -- ASA-4-400002
  IP options-Timestamp

**400003** -- ASA-4-400003
  IP options-Security

**400004** -- ASA-4-400004
  IP options-Loose Source Route

**400005** -- ASA-4-400005
  IP options-SATNET ID

**400006** -- ASA-4-400006
  IP options-Strict Source Route

**400007** -- ASA-4-400007
  IP Fragment Attack detected

**400008** -- ASA-4-400008
  IP Impossible Packet detected

**400009** -- ASA-4-400009
  IP Fragments Overlap detected

**400010** -- ASA-4-400010
  ICMP Echo Reply

**400011** -- ASA-4-400011
  ICMP Host Unreachable

**400012** -- ASA-4-400012
  ICMP Source Quench

**400013** -- ASA-4-400013
  ICMP Redirect

**400014** -- ASA-4-400014
  ICMP Echo Request

**400015** -- ASA-4-400015
  ICMP Time Exceeded

**400016** -- ASA-4-400016
  ICMP Parameter Problem

**400017** -- ASA-4-400017
  ICMP Timestamp Request

**400018** -- ASA-4-400018
  ICMP Timestamp Reply

**400019** -- ASA-4-400019
  ICMP Information Request

**400020** -- ASA-4-400020
  ICMP Information Reply

**400021** -- ASA-4-400021
  ICMP Address Mask Request

**400022** -- ASA-4-400022
  ICMP Address Mask Reply

**400023** -- ASA-4-400023
  Fragmented ICMP Traffic attack detected

**400024** -- ASA-4-400024
  Large ICMP Traffic attack detected

**400025** -- ASA-4-400025
  Ping of Death Attack detected

**400026** -- ASA-4-400026
  TCP NULL flags attack detected

**400027** -- ASA-4-400027
  TCP SYN+FIN flags attack detected

**400028** -- ASA-4-400028
  TCP FIN only flags attack detected

**400029** -- ASA-4-400029
  FTP Improper Address Specified attack

**400030** -- ASA-4-400030
  FTP Improper Port Specified attack

**400031** -- ASA-4-400031
  UDP Bomb attack detected

**400032** -- ASA-4-400032
  UDP Snork attack detected

**400033** -- ASA-4-400033
  UDP Chargen DoS attack detected

**400034** -- ASA-4-400034
  DNS HINFO Request

**400035** -- ASA-4-400035
  DNS Zone Transfer

**400036** -- ASA-4-400036
  DNS Zone Transfer from High Port

**400037** -- ASA-4-400037
  DNS Request for All Records

**400038** -- ASA-4-400038
  RPC Port Registration

**400039** -- ASA-4-400039
  RPC Port Unregistration

**400040** -- ASA-4-400040
  RPC Dump

**400041** -- ASA-4-400041
  Proxied RPC Request attack detected

**400042** -- ASA-4-400042
  ypserv Portmap Request

**400043** -- ASA-4-400043
  ypbind Portmap Request

**400044** -- ASA-4-400044
  yppasswdd Portmap Request

**400045** -- ASA-4-400045
  ypupdated Portmap Request

**400046** -- ASA-4-400046
  ypxfrd Portmap Request

**400047** -- ASA-4-400047
  mountd Portmap Request

**400048** -- ASA-4-400048
  rexd Portmap Request

**400049** -- ASA-4-400049
  rexd Attempt

**400050** -- ASA-4-400050
  statd Buffer Overflow attack detected

### IKE/IPsec VPN Negotiation

**713049** -- ASA-5-713049
  IPsec tunnel security negotiation completed

**713050** -- ASA-5-713050
  IPsec tunnel terminated

**713119** -- ASA-5-713119
  IKE Phase 1 completed successfully

**713120** -- ASA-5-713120
  IKE Phase 2 completed successfully

**713128** -- ASA-6-713128
  Connection redirected to VCA peer via load balancing

### IKEv2

**840001** -- ASA-3-840001
  Failed to create backup for IKEv2 session

### Interface Status

**411001** -- ASA-4-411001
  Line protocol on interface changed to up

**411002** -- ASA-4-411002
  Line protocol on interface changed to down

**411003** -- ASA-4-411003
  Interface changed to administratively up

**411004** -- ASA-4-411004
  Interface changed to administratively down

**411005** -- ASA-4-411005
  Interface experienced hardware transmit hang

### IP Fragmentation

**209003** -- ASA-4-209003
  Fragment database limit exceeded for reassembly

**209004** -- ASA-4-209004
  Invalid IP fragment exceeds maximum reassembly size

**209005** -- ASA-4-209005
  IP packet fragmented into more than allowed elements

**209006** -- ASA-4-209006
  Fragment queue threshold exceeded, dropped packets

### IPsec/Crypto

**402114** -- ASA-4-402114
  IPsec packet received with invalid SPI

**402115** -- ASA-4-402115
  IPsec packet missing expected ESP header

**402116** -- ASA-4-402116
  Decapsulated IPsec packet does not match negotiated identity

**402117** -- ASA-4-402117
  Non-IPsec packet matched crypto map ACL

**402118** -- ASA-4-402118
  Decapsulated IPsec packet contained illegal IP fragment

**402119** -- ASA-4-402119
  IPsec packet failed anti-replay checking

**402120** -- ASA-4-402120
  IPsec packet failed authentication check

**402121** -- ASA-4-402121
  IPsec packet dropped by IPsec subsystem

**402122** -- ASA-4-402122
  Cleartext packet to be encapsulated was dropped

**402123** -- ASA-4-402123
  Hardware accelerator error during crypto command

**402124** -- ASA-4-402124
  Crypto hardware chip reported fatal error

**402125** -- ASA-4-402125
  Crypto driver detected descriptor ring timeout

**402126** -- ASA-4-402126
  Crypto archive file created due to hardware issue

**402127** -- ASA-4-402127
  Crypto archive file not written, max files limit

**402128** -- ASA-5-402128
  SSL connection exceeds allowed memory allocation

**402129** -- ASA-6-402129
  Internal error releasing DMA memory block

**402130** -- ASA-6-402130
  IPsec packet detected with incorrect padding

**402131** -- ASA-4-402131
  Hardware accelerator configuration bias changed

**402140** -- ASA-3-402140
  RSA key generation error

**402141** -- ASA-3-402141
  Key zeroization error

**402142** -- ASA-3-402142
  Symmetric key operation error

**402143** -- ASA-3-402143
  Asymmetric key operation error

**402144** -- ASA-3-402144
  Digital signature generation error

**402145** -- ASA-3-402145
  Hash generation error

**402146** -- ASA-3-402146
  Keyed hash generation error

**402147** -- ASA-3-402147
  HMAC generation error

**402148** -- ASA-3-402148
  Random Number Generator error

**402149** -- ASA-3-402149
  Weak encryption algorithm not FIPS 140-2 compliant

**402150** -- ASA-3-402150
  Deprecated hash algorithm used for RSA operation

### Layer2/Bridging

**412001** -- ASA-4-412001
  MAC address moved from one interface to another

**412002** -- ASA-4-412002
  Bridge table full while inserting MAC address

### Link-State Propagation

**812005** -- ASA-4-812005
  Link-State-Propagation activated on inline-pair

### Logging

**414001** -- ASA-3-414001
  Failed to save logging buffer to FTP server

**414002** -- ASA-3-414002
  Failed to save logging buffer to flash

**414003** -- ASA-3-414003
  TCP syslog server not responding

**414004** -- ASA-6-414004
  TCP syslog server connection restored

**414005** -- ASA-3-414005
  TCP syslog server connected

**414006** -- ASA-3-414006
  TCP syslog server configured and logging queue full

### Management Access

**710001** -- ASA-7-710001
  TCP access requested to management interface

**710002** -- ASA-7-710002
  TCP/UDP access permitted to management interface

**710003** -- ASA-3-710003
  TCP/UDP access denied by ACL to management

**710005** -- ASA-7-710005
  TCP/UDP/SCTP request discarded by device

**710006** -- ASA-7-710006
  IP protocol request discarded, no matching server

**710007** -- ASA-7-710007
  NAT-T keepalive message received

### NAT/Connection Limits

**202001** -- ASA-3-202001
  Out of address translation slots available

**202005** -- ASA-3-202005
  Non-embryonic connection in embryonic list

**202010** -- ASA-3-202010
  NAT/PAT pool exhausted, unable to create connection

**202016** -- ASA-3-202016
  Unable to pre-allocate SIP secondary channel for PAT

### NAT/Translation

**305005** -- ASA-3-305005
  No translation group found for packet

**305006** -- ASA-3-305006
  Translation creation failed for protocol

**305007** -- ASA-6-305007
  Attempted to translate address not in global pool

**305008** -- ASA-3-305008
  Inconsistency when freeing unallocated global IP

**305009** -- ASA-6-305009
  Built dynamic or static address translation slot

**305010** -- ASA-6-305010
  Address translation slot deleted

**305011** -- ASA-6-305011
  Built TCP/UDP/ICMP address translation slot

**305012** -- ASA-6-305012
  Address translation slot deleted

**305013** -- ASA-5-305013
  Asymmetric NAT rules caused reverse path failure

**305014** -- ASA-6-305014
  Allocated port blocks for CGNAT translation

**305015** -- ASA-6-305015
  Released port blocks for CGNAT translation

**305016** -- ASA-3-305016
  Unable to create connection due to PAT port exhaustion

**305017** -- ASA-3-305017
  Active port block interim logging for CGNAT

**305018** -- ASA-6-305018
  MAP translation applied to connection

**305019** -- ASA-3-305019
  MAP node address has inconsistent Port Set ID

**305020** -- ASA-3-305020
  MAP node address not allowed to use port

**305021** -- ASA-4-305021
  Ports exhausted in sticky IP, allocating new pool

**305022** -- ASA-4-305022
  Cluster unit allocated unequal port blocks

**305023** -- ASA-3-305023
  Unable to create connection due to PAT pool exhaustion

### Network State

**609001** -- ASA-7-609001
  Network state container reserved for host

**609002** -- ASA-7-609002
  Network state container for host removed

### NTP

**610001** -- ASA-3-610001
  NTP packet denied from unconfigured source

**610002** -- ASA-3-610002
  NTP packet failed authentication check

### Object-Group Search

**815002** -- ASA-2-815002
  Object-group search hard limit exceeded, packet denied

### Policy-Based Routing

**880001** -- ASA-6-880001
  PBR selected different interface based on metrics

### Protocol Inspection

**107001** -- ASA-1-107001
  RIP authentication failed

**107002** -- ASA-1-107002
  RIP packet failed validation

**108002** -- ASA-2-108002
  SMTP replaced invalid character in address

**108003** -- ASA-2-108003
  ESMTP connection terminated for malicious pattern

**108004** -- ASA-4-108004
  ESMTP classification action taken

### Protocol Inspection (RTSP)

**314001** -- ASA-6-314001
  Pre-allocated RTSP UDP media channel

**314002** -- ASA-6-314002
  RTSP failed to allocate UDP media connection

**314003** -- ASA-6-314003
  RTSP traffic dropped due to security policy violation

### Protocol Inspection (SSH)

**315004** -- ASA-3-315004
  SSH session failed, RSA host key retrieval failed

**315011** -- ASA-6-315011
  SSH session terminated normally or disconnected

**315012** -- ASA-3-315012
  Weak SSH cipher/MAC not FIPS 140-2 compliant

**315013** -- ASA-6-315013
  SSH session rekeyed successfully

### Routing (OSPF)

**503001** -- ASA-5-503001
  OSPFv2 neighbor state changed

### Routing (RIP)

**312001** -- ASA-6-312001
  RIP header failed validation

### Security Context

**504001** -- ASA-5-504001
  Security context successfully added

**504002** -- ASA-5-504002
  Security context successfully removed

### Shunning

**401001** -- ASA-4-401001
  Shuns cleared from memory

**401002** -- ASA-4-401002
  Shun added to database for IP address

**401003** -- ASA-4-401003
  Single shunned host removed from database

**401004** -- ASA-4-401004
  Packet dropped, source host in shun database

**401005** -- ASA-4-401005
  Shun add failed due to insufficient memory

### SSL VPN/SVC

**722001** -- ASA-4-722001
  Invalid SVC connection request

**722020** -- ASA-3-722020
  No IP addresses available for SVC connection

**722022** -- ASA-6-722022
  SVC connection established

**722023** -- ASA-6-722023
  SVC connection terminated

**722032** -- ASA-5-722032
  New SVC connection replacing existing one

**722037** -- ASA-5-722037
  SVC connection closed

**722038** -- ASA-5-722038
  SVC session terminated

**722047** -- ASA-4-722047
  SVC disabled globally or image invalid

**722055** -- ASA-6-722055
  User attempting connection with user-agent

### SSL/TLS

**725001** -- ASA-6-725001
  SSL handshake initiated

**725002** -- ASA-6-725002
  SSL handshake completed successfully

**725006** -- ASA-6-725006
  SSL handshake with remote device failed

**725007** -- ASA-6-725007
  SSL session terminated

### Stateful Failover

**210001** -- ASA-3-210001
  Stateful Failover error occurred

**210002** -- ASA-3-210002
  Stateful Failover memory allocation failed

**210003** -- ASA-3-210003
  Stateful Failover received unsupported Logical Update object

**210005** -- ASA-3-210005
  Stateful Failover cannot allocate connection on standby

**210006** -- ASA-3-210006
  Stateful Failover unable to locate NAT group

**210007** -- ASA-3-210007
  Stateful Failover failed to allocate translation slot

**210008** -- ASA-3-210008
  Stateful Failover cannot find translation slot record

**210010** -- ASA-3-210010
  Stateful Failover unable to allocate UDP connection

**210020** -- ASA-3-210020
  Stateful Failover unable to reserve PAT port

**210021** -- ASA-3-210021
  Stateful Failover unable to create static translation

**210022** -- ASA-6-210022
  Stateful Failover missed updates in sequence

### Stateful Failover Replication

**311001** -- ASA-6-311001
  Stateful Failover update sent to standby

**311002** -- ASA-6-311002
  Stateful Failover update stopped to standby

**311003** -- ASA-6-311003
  Update acknowledgment received from standby

**311004** -- ASA-6-311004
  Stateful Failover update transmitted to standby

### System

**208005** -- ASA-3-208005
  Clear command returned non-zero error code

### System Resources

**211001** -- ASA-3-211001
  Memory allocation error occurred

**211003** -- ASA-3-211003
  CPU usage percentage computed greater than 100

**211004** -- ASA-1-211004
  Minimum memory requirement not met for device

**214001** -- ASA-2-214001
  Manager session terminated due to excessive encrypted data

**215001** -- ASA-2-215001
  Bad route_compress() call internal error

**217001** -- ASA-2-217001
  Memory allocation failure for operation

**219002** -- ASA-3-219002
  I2C serial bus API call failed

### System Resources (Hardware)

**218001** -- ASA-2-218001
  Module failed genuine Cisco product identification

**218002** -- ASA-2-218002
  Prototype module detected not certified for production

**218003** -- ASA-2-218003
  Module version obsolete, must be returned via RMA

**218004** -- ASA-2-218004
  Hardware identification test failed

**218005** -- ASA-2-218005
  System information inconsistency in non-volatile memory

### System Resources (PPTP/L2TP)

**213001** -- ASA-3-213001
  PPTP control daemon socket I/O error

**213002** -- ASA-3-213002
  PPTP tunnel hashtable insert failed

**213003** -- ASA-3-213003
  PPP virtual interface failed to open

**213004** -- ASA-3-213004
  PPP virtual interface client IP allocation failed

**213005** -- ASA-3-213005
  L2TP Dynamic-Access-Policy action aborts connection

**213006** -- ASA-3-213006
  L2TP Dynamic-Access-Policy retrieval failed

**213007** -- ASA-4-213007
  L2TP failed to install redirect URL or ACL

### System Resources (SNMP)

**212001** -- ASA-3-212001
  Unable to open SNMP channel on interface

**212002** -- ASA-3-212002
  Unable to open SNMP trap channel on interface

**212003** -- ASA-3-212003
  Unable to receive SNMP request on interface

**212004** -- ASA-3-212004
  Unable to send SNMP response to host

**212005** -- ASA-3-212005
  Incoming SNMP request exceeds data buffer size

**212006** -- ASA-3-212006
  SNMP request dropped due to authentication/encryption failure

**212009** -- ASA-5-212009
  SNMP group configuration request failed

**212010** -- ASA-3-212010
  SNMP user configuration change failed for host

**212011** -- ASA-3-212011
  SNMP engineBoots set to maximum value

**212012** -- ASA-3-212012
  Unable to write SNMP engine data to storage

### Threat Detection

**733100** -- ASA-4-733100
  Drop rate threshold exceeded

**733101** -- ASA-4-733101
  Host/subnet scanning or attack activity detected

**733102** -- ASA-5-733102
  Connection rate-limit threshold exceeded

**733103** -- ASA-5-733103
  TCP connection-limit threshold exceeded

**733104** -- ASA-5-733104
  UDP connection-limit exceeded

**733105** -- ASA-5-733105
  IP fragmentation rate threshold exceeded

**734001** -- ASA-6-734001
  Threat detection basic-threat enabled

**734002** -- ASA-6-734002
  Threat detection basic-threat disabled

### TrustSec/SGT

**776201** -- ASA-4-776201
  CTS PAC nearing expiration

**776202** -- ASA-3-776202
  CTS PAC has expired

**776251** -- ASA-6-776251
  SGT binding added to binding manager

**776252** -- ASA-5-776252
  SGT binding deleted from binding manager

### Tunneling (PPTP/L2TP/PPPoE)

**603101** -- ASA-6-603101
  PPTP packet received out of sequence

**603104** -- ASA-6-603104
  PPTP tunnel created with tunnel ID

**603105** -- ASA-6-603105
  PPTP tunnel deleted

**603106** -- ASA-6-603106
  L2TP tunnel created with tunnel ID

**603107** -- ASA-6-603107
  L2TP tunnel deleted

**603108** -- ASA-6-603108
  PPPoE tunnel created successfully

**603109** -- ASA-6-603109
  PPPoE tunnel deleted

### User Management

**501101** -- ASA-5-501101
  User privilege level transitioned

**502101** -- ASA-5-502101
  New user added to local database

**502102** -- ASA-5-502102
  User deleted from local database

**502103** -- ASA-5-502103
  User privilege level changed

**502111** -- ASA-5-502111
  New group policy added to system

**502112** -- ASA-5-502112
  Group policy removed from system

### VPN Tunnels

**316001** -- ASA-3-316001
  New tunnel denied, VPN peer limit exceeded

### VPN/IPsec

**602101** -- ASA-6-602101
  PMTU-D packet exceeded MTU, ICMP unreachable sent

**602103** -- ASA-6-602103
  IPsec SA MTU updated based on ICMP PMTU message

**602303** -- ASA-6-602303
  New IPsec SA created between endpoints

**602304** -- ASA-6-602304
  IPsec SA deleted between endpoints

**602305** -- ASA-3-602305
  Error creating IPsec security association

### VXLAN

**778001** -- ASA-6-778001
  VXLAN packet discarded, invalid segment-id

### WebVPN/AnyConnect

**716001** -- ASA-6-716001
  WebVPN session started for user

**716002** -- ASA-6-716002
  WebVPN session terminated

**716003** -- ASA-6-716003
  WebVPN user access granted to URL

**716004** -- ASA-6-716004
  WebVPN user access denied to URL

**716038** -- ASA-6-716038
  Authentication successful for WebVPN session

**716039** -- ASA-6-716039
  Authentication rejected for session type

**716057** -- ASA-3-716057
  Session terminated, license type unavailable

**716058** -- ASA-6-716058
  AnyConnect session lost connection, waiting to resume

**716059** -- ASA-6-716059
  AnyConnect session resumed from new IP
