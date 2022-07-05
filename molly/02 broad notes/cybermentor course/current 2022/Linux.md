**Files**
user configs > /etc/passwd
passwds > /etc/shadow (good for cracking)

**Networking**
ping
ifconfig / iwconfig (old)
**ip**
- ip a
	- ifaces and ips
- ip n
	- arp table
- ip r
	- routing tables

**nc -nvlp 7777**
netcat listen on port

**arp -a**
ip addresses and macs associated

**netstat -ano**
active connections on a machine

**route**
routing table, where your traffic's exiting

first probe (ping or else)
ip list into file, then nmap (or similar) on the list

**Upgrade**
apt update && apt upgrade