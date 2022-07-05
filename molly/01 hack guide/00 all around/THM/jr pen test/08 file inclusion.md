main issue of these vulnerabilities is the input validation, in which the user inputs are not sanitized or validated, and the user controls them. When the input is not validated, the user can pass any input to the function, causing the vulnerability.
it won't be effective if file inclusion vulnerability is found with no access to sensitive data and no writing ability to the server.

**path/directory traversal vuln**
We can test out the URL parameter by adding payloads to see how the web application behaves. Path traversal attacks, also known as the dot-dot-slash attack, take advantage of moving the directory one step up using the double dots ../

**Local File Inclusion (LFI) attacks**

Using null bytes is an injection technique where URL-encoded representation such as %00 or 0x00 in hex with user-supplied data to terminate strings. You could think of it as trying to trick the web app into disregarding whatever comes after the Null Byte.

play with extra dots to test if there's regex filtering

**Remote File Inclusion (RFI) attacks**

The risk of RFI is higher than LFI since RFI vulnerabilities allow an attacker to gain Remote Command Execution (RCE) on the server. Other consequences of a successful RFI attack include:

-   Sensitive Information Disclosure
-   Cross-site Scripting (XSS)
-   Denial of Service (DoS)  

An external server must communicate with the application server for a successful RFI attack where the attacker hosts malicious files on their server. Then the malicious file is injected into the include function via HTTP requests, and the content of the malicious file executes on the vulnerable application server.

**remediation**
 To prevent the file inclusion vulnerabilities, some common suggestions include:

1.  Keep system and services, including web application frameworks, updated with the latest version.  
2.  Turn off PHP errors to avoid leaking the path of the application and other potentially revealing information.
3.  A Web Application Firewall (WAF) is a good option to help mitigate web application attacks.
4.  Disable some PHP features that cause file inclusion vulnerabilities if your web app doesn't need them, such as allow_url_fopen on and allow_url_include.  
5.  Carefully analyze the web application and allow only protocols and PHP wrappers that are in need.
6.  Never trust user input, and make sure to implement proper input validation against file inclusion.  
7.  Implement whitelisting for file names and locations as well as blacklisting.