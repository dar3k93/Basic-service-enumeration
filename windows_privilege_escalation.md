#### Information Gathering
- systeminfo ***OS info***
- hostname ***host info***
- net users ***users info***
- net user <user_name>
- ipconfig /all ***network interfaces and routing table.***
- route print
- arp -A
- netstat -ano ***network connections and the firewall rules***
- netsh firewall show state
- netsh firewall show state
- netsh firewall show config
- schtasks /query /fo LIST /v ***scheduled tasks, running processes, started services and installed drivers.***
- tasklist /SVC
- net start

#### Search for password
- findstr /si password *.txt
- findstr /si password *.xml
- findstr /si password *.ini
- dir /s *pass* == *cred* == *vnc* == *.config*
- findstr /spin "password" *.*
***password in files***
- c:\sysprep.inf
- c:\sysprep\sysprep.xml
- c:\unattend.xml
- %WINDIR%\Panther\Unattend\Unattended.xml
- %WINDIR%\Panther\Unattended.xml
- dir c:\*vnc.ini /s /b
- dir c:\*ultravnc.ini /s /b 
- dir c:\ /s /b | findstr /si *vnc.ini
***Find all those strings in confing files***
dir /s *pass* == *cred* == *vnc* == *.config*
***In Registry***
- ***Putty*** : reg query "HKCU\Software\SimonTatham\PuTTY\Sessions"
- ***SNMP Paramters*** : reg query "HKLM\SYSTEM\Current\ControlSet\Services\SNMP"
- ***Windows autologin*** : reg query "HKLM\SOFTWARE\Microsoft\Windows NT\Currentversion\Winlogon"
- ***VNC*** : reg query "HKCU\Software\ORL\WinVNC3\Password"
- ***Search for password in registry*** : reg query HKLM /f password /t REG_SZ /s ***OR*** reg query HKCU /f password /t REG_SZ /s

#### Service available form inside
netstat -ano




#### Usefull scrips

- ***Windows Exploit Suggester*** https://github.com/AonCyberLabs/Windows-Exploit-Suggester
- ***JustAnotherWindowsScript(Enum)*** https://github.com/411Hall/JAWS
-
