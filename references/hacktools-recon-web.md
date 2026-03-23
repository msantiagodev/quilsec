# Recon, Web App Testing & OSINT
> Source: HackTools | Entries: 61 | Platform: cross_platform


## Index

- [AD Enumeration](#ad-enumeration)
- [cloud_security](#cloudsecurity)
- [dns_enumeration](#dnsenumeration)
- [OSINT](#osint)
- [Reconnaissance](#reconnaissance)
- [web_application_testing](#webapplicationtesting)


### AD Enumeration

#### ADSearch
C# tool for performing custom LDAP searches against Active Directory with support for JSON output. Provides a lightwe...
**Categories:** AD Enumeration, LDAP Queries, Reconnaissance, Kerberos Reconnaissance, Delegation Discovery
```
ADSearch.exe --search "(&(objectClass=user)(servicePrincipalName=*))" --attributes cn,servicePrincipalName
```

#### LDAPDomainDump
Python tool that dumps Active Directory information via LDAP and generates human-readable HTML, JSON, and grep-friend...
**Categories:** AD Enumeration, LDAP Dumping, Reporting, Reconnaissance, Cross-Platform
```
ldapdomaindump -u 'corp\user' -p 'P@ss' dc01.corp.local -o /tmp/ldap_dump
```

### cloud_security

#### AzureADRecon
Azure Active Directory reconnaissance tool that extracts and reports on directory configuration and security posture....
**Categories:** cloud_security, azure_ad, reconnaissance
```
Import-Module AzureADRecon.psm1; Invoke-AzureADRecon
```

#### cloud_enum
Multi-cloud enumeration tool for discovering exposed cloud resources across AWS, Azure, and GCP. Detectable through m...
**Categories:** cloud_security, resource_discovery, reconnaissance
```
python cloud_enum.py -k targetcompany
```

#### S3Scanner
AWS S3 bucket discovery and permission enumeration tool. Detectable through mass S3 bucket name brute-forcing, permis...
**Categories:** cloud_security, s3_security, reconnaissance
```
python s3scanner.py --list buckets.txt
```

### dns_enumeration

#### dnsenum
Multithreaded Perl-based DNS enumeration tool that discovers hostnames, subdomains, IP ranges, and network blocks ass...
**Categories:** dns_enumeration, reconnaissance, information_gathering, subdomain_discovery
```
dnsenum example.com
```

#### fierce
DNS reconnaissance tool that performs non-contiguous IP space discovery and DNS enumeration to map an organization's...
**Categories:** dns_enumeration, reconnaissance, information_gathering, subdomain_discovery
```
fierce --domain example.com
```

### OSINT

#### breach-parse
Bash-based tool for parsing and searching large breach compilation datasets by domain or keyword. Designed to efficie...
**Categories:** OSINT, Breach Analysis, Credential Hunting, Data Processing, Password Security
```
breach-parse target.com breach-results/
```

#### creepy
Geolocation OSINT tool that aggregates location data from social media platforms and image hosting services. Extracts...
**Categories:** OSINT, Geolocation, Social Media Intelligence, Location Tracking, Visualization
```
python CreepyMain.py
```

#### dehashed
Commercial breach data search engine with a CLI tool for querying compromised credentials by email, username, IP, nam...
**Categories:** OSINT, Breach Detection, Credential Hunting, Threat Intelligence, Password Security
```
dehashed-cli -q 'email:target@email.com' -k API_KEY
```

#### exiftool
Comprehensive metadata reader/writer supporting 400+ file formats including images, documents, audio, and video. Extr...
**Categories:** OSINT, Metadata Analysis, Digital Forensics, Image Analysis, Geolocation
```
exiftool image.jpg
```

#### FOCA
Metadata extraction and analysis tool that finds and downloads documents from target websites, then extracts hidden m...
**Categories:** OSINT, Metadata Analysis, Document Analysis, Information Leakage, Reconnaissance
```
foca.exe
```

#### GHunt
Google account OSINT tool that extracts information from Google services using email addresses or Google IDs. Discove...
**Categories:** OSINT, Google Intelligence, Account Investigation, Social Media Intelligence, Reconnaissance
```
ghunt email target@gmail.com
```

#### h8mail
Email OSINT and password breach hunting tool that queries multiple breach databases and paste sites to find leaked cr...
**Categories:** OSINT, Breach Detection, Credential Hunting, Email Intelligence, Password Security
```
h8mail -t target@email.com
```

#### holehe
Email OSINT tool that checks whether an email address is registered on 120+ websites by exploiting password reset and...
**Categories:** OSINT, Email Intelligence, Account Enumeration, Reconnaissance, Digital Footprint
```
holehe target@email.com
```

#### maigret
Advanced username OSINT tool that searches 2500+ sites for accounts, significantly expanding on Sherlock's coverage....
**Categories:** OSINT, Username Enumeration, Social Media Intelligence, Profiling, Reconnaissance
```
maigret targetuser
```

#### Maltego
Visual link analysis and data mining platform for OSINT investigations. Performs automated entity discovery and relat...
**Categories:** OSINT, Link Analysis, Threat Intelligence, Reconnaissance, Investigation
```
maltego
```

#### Metagoofil
Document metadata harvester that uses Google dorks to find and download public documents from target domains, then ex...
**Categories:** OSINT, Metadata Analysis, Document Analysis, Information Leakage, Reconnaissance
```
metagoofil -d target.com -t pdf,doc,xls -l 100 -n 50 -o output/ -f results.html
```

#### Osintgram
Instagram OSINT tool that provides interactive analysis of Instagram accounts. Extracts followers, following, posts,...
**Categories:** OSINT, Social Media Intelligence, Instagram Analysis, Reconnaissance, Media Extraction
```
python3 main.py targetuser
```

#### Photon
High-speed web crawler designed for OSINT that extracts URLs, email addresses, social media accounts, files, secret k...
**Categories:** OSINT, Web Crawling, Reconnaissance, Information Gathering, URL Discovery
```
photon -u https://target.com -o output_dir
```

#### Recon-ng
Full-featured web reconnaissance framework modeled after Metasploit with modular architecture. Provides workspace-bas...
**Categories:** OSINT, Reconnaissance, Information Gathering, Framework, Automated Scanning
```
recon-ng -w workspace_name
```

#### Sherlock
Username enumeration tool that searches across 400+ social media platforms and websites to find accounts associated w...
**Categories:** OSINT, Username Enumeration, Social Media Intelligence, Reconnaissance, Digital Footprint
```
sherlock targetusername
```

#### social-analyzer
API, CLI, and web app for analyzing and profiling social media accounts by username, email, or phone number. Searches...
**Categories:** OSINT, Social Media Intelligence, Profiling, Account Correlation, Reconnaissance
```
social-analyzer --username targetuser --metadata --top 500
```

#### SpiderFoot
Automated OSINT collection and reconnaissance framework with 200+ modules querying public data sources. Correlates di...
**Categories:** OSINT, Reconnaissance, Threat Intelligence, Information Gathering, Automated Scanning
```
spiderfoot -l 127.0.0.1:5001
```

#### theHarvester
OSINT gathering tool for email addresses, subdomains, hosts, employee names, open ports, and banners from public sour...
**Categories:** OSINT, Reconnaissance, Email Harvesting, Subdomain Enumeration, Information Gathering
```
theHarvester -d target.com -b google,bing,linkedin -l 500
```

#### Twint
Advanced Twitter/X scraping tool that collects tweets, followers, following lists, and profile data without using the...
**Categories:** OSINT, Social Media Intelligence, Twitter Scraping, Reconnaissance, Data Collection
```
twint -u targetuser --since 2024-01-01
```

#### WhatsMyName
Username enumeration tool with a community-maintained JSON database of website checking rules. Tests username existen...
**Categories:** OSINT, Username Enumeration, Social Media Intelligence, Reconnaissance, Identity Research
```
python3 web_accounts_list_checker.py -u targetuser
```

### Reconnaissance

#### Amass
In-depth attack surface mapping and asset discovery tool performing extensive DNS enumeration, subdomain brute-forcin...
**Categories:** Reconnaissance
```
amass enum -d target.com -active -brute -w wordlist.txt -o results.txt
```

#### Aquatone
Visual inspection tool for large numbers of web hosts capturing screenshots and clustering similar pages. Uses headle...
**Categories:** Reconnaissance
```
cat hosts.txt | aquatone -ports 80,443,8080 -out results/ -threads 5
```

#### Censys
Internet-wide search and monitoring platform CLI that queries indexed scan data for hosts, certificates, and services...
**Categories:** Reconnaissance
```
censys search 'services.http.response.headers.server: Apache' --index-type hosts
```

#### CloudEnum
Cloud infrastructure enumeration tool discovering exposed cloud resources (S3 buckets, Azure blobs, GCP storage) by b...
**Categories:** Reconnaissance
```
cloud_enum -k target -k targetcorp -l results.txt
```

#### Dirsearch
Web path discovery tool brute-forcing directories and files on web servers. Generates sequential HTTP requests with e...
**Categories:** Reconnaissance
```
dirsearch -u https://target.com -e php,asp,html -t 50 --deep-recursive
```

#### EyeWitness
Web application screenshot and header analysis tool capturing visual snapshots of web interfaces. Launches headless b...
**Categories:** Reconnaissance
```
eyewitness --web -f urls.txt --timeout 30 -d output_dir
```

#### Feroxbuster
Recursive content discovery tool written in Rust performing forced browsing with automatic recursion into discovered...
**Categories:** Reconnaissance
```
feroxbuster -u https://target.com -w wordlist.txt --depth 4 --threads 50
```

#### ffuf
Fast web fuzzer for directory, file, parameter, and virtual host discovery using wordlists. Generates high-volume HTT...
**Categories:** Reconnaissance
```
ffuf -u https://target.com/FUZZ -w /usr/share/wordlists/dirb/common.txt -mc 200,301 -o results.json
```

#### Gobuster
Brute-force tool for URI directories/files, DNS subdomains, virtual hosts, S3 buckets, and TFTP servers. Generates sy...
**Categories:** Reconnaissance
```
gobuster dir -u https://target.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 50
```

#### GoWitness
Web screenshot utility written in Go using headless Chrome for visual reconnaissance. Captures screenshots with serve...
**Categories:** Reconnaissance
```
gowitness scan single -u https://target.com -s /tmp/screenshots/
```

#### httpx
Fast HTTP toolkit probing web servers for status codes, titles, technologies, and response metadata. Generates HTTP/H...
**Categories:** Reconnaissance
```
httpx -l hosts.txt -status-code -title -tech-detect -o live_hosts.txt
```

#### Masscan
Asynchronous TCP port scanner capable of scanning the entire Internet in under 6 minutes. Generates massive packet vo...
**Categories:** Reconnaissance
```
masscan -p0-65535 192.168.0.0/16 --rate=10000 -oJ results.json
```

#### Nikto
Web server vulnerability scanner checking for dangerous files, outdated software, and misconfigurations. Sends thousa...
**Categories:** Reconnaissance
```
nikto -h https://target.com -output results.html -Format htm
```

#### Nmap
Network mapper performing host discovery, port scanning, service/version detection, and OS fingerprinting. Generates...
**Categories:** Reconnaissance
```
nmap -sS -sV -O -p- --script=default,vuln -oA scan_results 192.168.1.0/24
```

#### Nuclei
Template-based vulnerability scanner sending targeted HTTP, DNS, TCP, and other protocol probes defined in YAML templ...
**Categories:** Reconnaissance
```
nuclei -u https://target.com -t nuclei-templates/ -severity critical,high -o results.txt
```

#### Pacu
AWS exploitation framework performing enumeration, privilege escalation, and data exfiltration via AWS API calls. Mak...
**Categories:** Reconnaissance
```
pacu --new-session pentest
```

#### Prowler
Cloud security assessment tool performing checks against CIS benchmarks, GDPR, HIPAA, and other compliance frameworks...
**Categories:** Reconnaissance
```
prowler aws --compliance cis_2.0_aws
```

#### Recon-ng
Modular web reconnaissance framework with database-backed workflows. Queries dozens of OSINT sources and APIs through...
**Categories:** Reconnaissance
```
recon-ng -w workspace_name -m recon/domains-hosts/hackertarget -o SOURCE=target.com -x
```

#### RustScan
Fast port scanner written in Rust that pipes results into Nmap for detailed service enumeration. Creates initial burs...
**Categories:** Reconnaissance
```
rustscan -a 192.168.1.1 --ulimit 5000 -- -sV -sC
```

#### ScoutSuite
Multi-cloud security auditing tool assessing AWS, Azure, GCP, Alibaba Cloud, and Oracle Cloud configurations. Makes a...
**Categories:** Reconnaissance
```
scout aws --profile production --report-dir ./results
```

#### Shodan CLI
Command-line interface for the Shodan search engine that queries pre-indexed Internet scan data. Queries Shodan API e...
**Categories:** Reconnaissance
```
shodan search 'apache port:443 country:US' --fields ip_str,port,org
```

#### SpiderFoot
Automated OSINT collection tool querying 200+ data sources for intelligence on IPs, domains, emails, and names. Gener...
**Categories:** Reconnaissance
```
spiderfoot -s target.com -t INTERNET_NAME,IP_ADDRESS -m sfp_dnsresolve,sfp_shodan -o results.csv
```

#### Subfinder
Passive subdomain discovery tool querying multiple online sources without direct target interaction. Generates API tr...
**Categories:** Reconnaissance
```
subfinder -d target.com -all -o subdomains.txt
```

#### theHarvester
OSINT tool for gathering emails, subdomains, IPs, and URLs from multiple public data sources. Generates queries to se...
**Categories:** Reconnaissance
```
theHarvester -d target.com -b all -l 500 -f results.html
```

#### wafw00f
Web Application Firewall detection tool identifying WAF products by analyzing HTTP response variations to normal and...
**Categories:** Reconnaissance
```
wafw00f https://target.com -a -v
```

#### Wappalyzer
Technology profiling tool identifying web frameworks, CMS platforms, analytics tools, and JavaScript libraries from p...
**Categories:** Reconnaissance
```
wappalyzer https://target.com
```

#### Wfuzz
Web application fuzzer replacing any HTTP request component with wordlist payloads. Generates high-volume requests wi...
**Categories:** Reconnaissance
```
wfuzz -c -z file,wordlist.txt --hc 404 https://target.com/FUZZ
```

#### WhatWeb
Web technology fingerprinting tool identifying CMS platforms, frameworks, JavaScript libraries, and server software f...
**Categories:** Reconnaissance
```
whatweb https://target.com -v -a 3
```

### web_application_testing

#### Arjun
HTTP parameter discovery tool that finds hidden or undocumented query and body parameters. Detectable through mass pa...
**Categories:** web_application_testing, parameter_discovery, reconnaissance
```
arjun -u http://target.com/api/endpoint -m GET -t 10
```

#### Burp Suite
Integrated web application security testing platform used for intercepting, modifying, and replaying HTTP/HTTPS traff...
**Categories:** web_application_testing, proxy, vulnerability_scanner
```
java -jar burpsuite_pro.jar --project-file=target.burp
```

#### ParamSpider
Parameter mining tool that extracts URLs with parameters from web archives and crawl data. Detectable through high-vo...
**Categories:** web_application_testing, parameter_discovery, osint
```
python paramspider.py -d target.com --exclude woff,css,js,png,svg
```

#### sqlmap
Automated SQL injection detection and exploitation tool that supports multiple database backends. Detectable through...
**Categories:** web_application_testing, sql_injection, database_exploitation
```
sqlmap -u 'http://target.com/page?id=1' --batch --dbs
```

#### XSStrike
Advanced XSS detection suite with fuzzing engine, context analysis, and WAF fingerprinting. Detectable through its di...
**Categories:** web_application_testing, xss_detection, fuzzing
```
python xsstrike.py -u 'http://target.com/search?q=test' --crawl
```

#### ZAP
OWASP Zed Attack Proxy is an open-source web application security scanner that acts as a man-in-the-middle proxy. Det...
**Categories:** web_application_testing, proxy, vulnerability_scanner
```
zap.sh -daemon -port 8080 -config api.key=changeme
```
