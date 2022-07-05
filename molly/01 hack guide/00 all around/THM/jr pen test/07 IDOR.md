IDOR stands for Insecure Direct Object Reference and is a type of access control vulnerability.  
This type of vulnerability can occur when a web server receives user-supplied input to retrieve objects (files, data, documents), too much trust has been placed on the input data, and it is not validated on the server-side to confirm the requested object belongs to the user requesting it.

changing a reference, for example ?user=1 to user=100 and being able to read it
sometimes ids or value data is encoded, so you can try decode/tamper/encode
also with hashed values, again using crackstation.net or similar

if ids are not identifiable, to verify the vuln, you can create 2 accounts and try to see the id of one from within the other