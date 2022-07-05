* use google fu to discover resources (domains, sensitive files)
* think of point of attack as an attacker
* commonly found ports with exploits, historically (low hanging fruit, juiciest)
* hygiene of the target (good/bad)
* information disclosure (versions, hostnames, non-existent dirs/files)
* remember to check html source code (comments, keys, info disclosure)

---

**metasploit port 80** from https://medium.com/hacker-toolbelt/metasploitable-2-iv-port-80-5b90a0a22cb6

`db_nmap -sV 192.168.231.109 -p 80`
saves results to db, just use nmap for not saving

`use auxiliary/scanner/http/http_version`
version get

`use auxiliary/scanner/http/dir_listing`
determine if directory listing is enabled on the remote server

`use auxiliary/scanner/http/dir_scanner`
dir fuzzer within metasploit

`use auxiliary/scanner/http/files_dir`
file fuzzer for what we found on previous step

modules recommended by the writeup
`use auxiliary/scanner/http/verb_auth_bypass`
‘options’, ‘robots_txt’ and ‘verb_auth_bypass’:

`$ searchsploit apache | grep 5.4.2`
check for an attack vector on an exploit (goes into exploit area, oh well)

`use exploit/multi/http/php_cgi_arg_injection`
in the example, it's exploitable