This content could be, for example, pages or portals intended for staff usage, older versions of the website, backup files, configuration files, administration panels, etc.

 three main ways of discovering content: Manually, Automated and OSINT (Open-Source Intelligence).

**manual**
- robots.txt
- favicon left from framework: https://wiki.owasp.org/index.php/OWASP_favicon_database
- sitemap.xml
- http headers
- Framework Stack: Once you've established the framework of a website, either from the above favicon example or by looking for clues in the page source such as comments, copyright notices or credits, you can then locate the framework's website. From there, we can learn more about the software and other information, possibly leading to more content we can discover.

**osint**
- google dorking
- wappalyzer and similar
- The Wayback Machine ([https://archive.org/web/](https://archive.org/web/)) 
- GitHub's search feature to look for company names or website names to try and locate repositories belonging to your target. Once discovered, you may have access to source code, passwords or other content that you hadn't yet found.
- public s3 buckets: The format of the S3 buckets is http(s)://**{name}.**[**s3.amazonaws.com**](http://s3.amazonaws.com/) where {name} is decided by the owner, such as [tryhackme-assets.s3.amazonaws.com](http://tryhackme-assets.s3.amazonaws.com/). S3 buckets can be discovered in many ways, such as finding the URLs in the website's page source, GitHub repositories, or even automating the process. One common automation method is by using the company name followed by common terms such as **{name}**-assets, **{name}**-www, **{name}**-public, **{name}**-private, etc.

**automated**
- wordlists
- tools: ffuf, dirb and gobuster
- 