Subdomain enumeration is the process of finding valid subdomains for a domain, but why do we do this? We do this to expand our attack surface to try and discover more potential points of vulnerability.

different subdomain enumeration methods: Brute Force, OSINT (Open-Source Intelligence) and Virtual Host.

---
**SSL/TLS Certificates**
When an SSL/TLS (Secure Sockets Layer/Transport Layer Security) certificate is created for a domain by a CA (Certificate Authority), CA's take part in what's called "Certificate Transparency (CT) logs". These are publicly accessible logs of every SSL/TLS certificate created for a domain name. The purpose of Certificate Transparency logs is to stop malicious and accidentally made certificates from being used. We can use this service to our advantage to discover subdomains belonging to a domain, sites like [https://crt.sh](http://crt.sh/) and [https://transparencyreport.google.com/https/certificates](https://transparencyreport.google.com/https/certificates) offer a searchable database of certificates that shows current and historical results.

**search engines**
-site:www.tryhackme.com  site:*.tryhackme.com

**dns bruteforce**
https://www.kali.org/tools/dnsrecon/

**enumeration tools**
https://github.com/aboul3la/Sublist3r

**virtual hosts**
try to discover virtual hosts on the server by changing the Host header on the request with a fuzzer

ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://MACHINE_IP -fs {size}

replacing {size} with the most occurring size value from the previous result