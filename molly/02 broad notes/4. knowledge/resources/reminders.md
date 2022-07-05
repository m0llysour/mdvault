"A debugged program is one for which you have not yet found the conditions that make it fail." - Jerry Ogdin

---
"spray and pray"

---
use google fu to discover resources (domains, sensitive files)

---
think of point of attack as an attacker
commonly found ports with exploits, historically (low hanging fruit, juiciest)
hygiene of the target (good/bad)
information disclosure (versions, hostnames, non-existent dirs/files)

---
remember to check html source code (comments, keys, info disclosure)

---
post-exploit
- find out my ip
- see if we have 2(more) NICs, and pivot
- see to whom the machine is talking to
- cat psw and shadow files / hashdump
- crack passwords
- enumerate files
- see user folders for more juicy stuff