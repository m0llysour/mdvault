**vaccine**
https://dfir.science/2014/07/how-to-cracking-zip-and-rar-protected.html
zip2john backup.zip > backup.hashes (same with rar)
then john backup.hashes
always always look for pwds in files!

**responder**
`nmap --min-rate 5000` is very fast
steal ntlm hashes (responder) and then crack them (john)
evil-winrm to connect to win remote management

**unified**
log4j exploit on unify app https://github.com/puzzlepeaches/Log4jUnifi
using tcpdump to validate attack via LDAP
sudo tcpdump -i tun0 'tcp port 389'
interact.sh to capture out of band interactions (vuln detection with callback)

**RouterSpace**
interesting to use `anbox` to virtualize android and run apks
rode on someone else's uploading of a private id_rsa key and then ssh'n with that
trying CVE-2021-4034 levearing on something on polkit's poor implementation of guid
it was finally CVE-2021-3156 sudo vulnerability (dubbed Baron Samedit by Qualys)

**Timelapse**
next: scan ports ✓
next: connect to smb and get files ✓
next: try pwd cracking on zip files (fail)
next: get more files from smb and see what they are
also do a small free course on AD (https://www.youtube.com/playlist?list=PLt7zzBn5CwKp8NHj8bVsLCWzHDqguthiK)
