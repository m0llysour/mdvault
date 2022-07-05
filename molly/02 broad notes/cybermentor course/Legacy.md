Legacy

**\[5 stages of hacking\]**

1.  reconnaissance: information gathering, passive (not client services, linkedin, google, no scans on the host) and active>scanning
    
2.  !scanning and enumeration: nmap, nessus, nikto, etc
    
3.  gaining access: exploits, social eng, etc
    
4.  maintaining access: on the network, not get detected/disconnected
    
5.  covering tracks: psexec, not leave malware / information / logs
    

1.  passive recon (OSINT):
    a. physical / social
    location info:
    satellite images, drone recon, building layout (badge readers, break areas, security, fencing)
    location offices, gate, guard, distance to creep, contact info
    job info:
    employees (topology / who they are? name, job title, phone number, manager, etc)
    search for standing out names, not common
    pictures (social networks: badge photos, desk photos, computer photos, etc)
    b. web / host
    target validation: verify host/ipspace ownership (WHOIS, nslookup, dnsrecon)
    finding subdomains: environments dev/admin (google fu, nmap, sublist3r, bluto, crt.sh, etc)
    fingerprinting (~active): type of software (nmap, wappalyzer, whatweb, builtwith, netcat)
    data breaches: haveibeenpwned and similar lists
    access || valid usernames || passwd patterns (if possible compare >1 sources)
    

**\[resources\]**
hunter.io (find emails)
site:x.com -www filetype:pdf (google)
theharvester -d x.com -l 500 -b google (general data)
bluto (OLD pwned, scan/brute/active recon)
netcraft
crt.sh (domain certificate search > subdomains)
wappalyzer/builtwith (tech used on websites)
whatweb (what is website ~active)

2.  scanning and enumeration

- scan on TCP && UDP
    → TCP: conn oriented, has a handshake > http, ftp, telnet
    ⇒ 3 way handshake: \[SYN\] \[SYN ACK\] \[ACK\]
    ⇒ SYN ACK: acknowledge, you can connect
    → UDP: connless, fast conn > DNS, DHCP, SNMP
- nmap: stealth does \[SYN\] \[SYN ACK\] \[RST\] (just kidding)
    → look for varied scanning techniques
    → pingsweep: nmap -sn 192.168.1.0/24 (ICMP packets)