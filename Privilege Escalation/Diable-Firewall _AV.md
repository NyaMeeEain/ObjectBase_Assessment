```
powershell Set-MpPreference -DisableRealtimeMonitoring $true 
```

```
Set-ItemProperty -Path "HKLM:SOFTWARE\Policies\Microsoft\Windows Defender" -Name DisableAntiSpyware -Value 0x00000001 -Force 

```

```
netsh advfirewall set  currentprofile state off 
```
