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

`whatweb`
gather info, versions to lookup vulnerabilities & exploits

`burp suite`
web proxy for intercepting traffic from/to a website

`nmap -p 80 -T4 $ip`
`nmap -T4 -p- -A`
-sn: Ping scan
-Pn: treat all hosts as online
-sU: UDP scan (connection-less > 65k ports, very slow to scan)
--min-rate 5000: very fast
-sT or sF: different connect/detection methos
-sV : Attempts to determine the version of the service running on a port 
-sC : Scan with default NSE scripts

`nikto -h https://host`
web vulnerability scanner

`dirbuster`
directory busting, alternatives: `dirb`, `gobuster`

`ffuf -w list.txt:FUZZ -u http://host/FUZZ`
webapp directory fuzzer

`nessus`
vulnerability scanner, extra layer of assesment

`dnsrecon -r 127.0.0.0/24 -n 192.168.129.135`\
reverse search an ip on a given dns server
a webserver might be listening for a specific domain (set on local /etc/hosts					)

`builtwith.com`
tech/platforms used on/from websites

`wappalyzer`
tech/platforms used on/from websites, ffox extension

`tcpdump`
listen in on traffic out of ifaces

`interact.sh`
capture out of band interactions (vuln detection with callback)