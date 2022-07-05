**From # Changing Our Mindset From Technical To Psychological Defenses Andrew Kalat** https://www.youtube.com/watch?v=lwHW_W1KbK4
trigger reward systems on victims: if they get paid to sell, pose as client; if they are help desk, pose as someone having tech issues, etc
what do people care about? what are they looking (desperately) for? phish them with that bait

![[Screen Shot 2022-04-16 at 13.28.44.png]]
---

**Open Source Intelligence Gathering: Techniques, Automation ~~, and Visualization~~ from https://posts.specterops.io/gathering-open-source-intelligence-bee58de48e05**

this article will focus on network targets (e.g. IP addresses, domains, and systems) while lightly touching on collecting personnel information (e.g. email addresses, names, job titles)

**target**
A target is necessary to begin the discovery process. a name and a domain is a good place to start.

**people**
Full Contact marketing database and API is a fine place to begin.
Collect and use on linkedin.

**domains**
WhoXY is a solid service for this and offers a reverse WHOIS API endpoint that accepts company names and keywords to perform searches against WHOIS records. pause and consider these new domains.
Pick through the results and select a few domains that look interesting to carry forward and then continue on to the next step, subdomain discovery.

**subdomains**
Aquatone and Sublist3r. Brute forcing can reveal subdomains that may never have been found otherwise, but you have to contend with wildcard DNS and it is not necessary in these early stages. [DNS Dumpster](https://dnsdumpster.com/) and [Netcraft](https://www.netcraft.com/) are likely to have a good number of catalogued subdomains for the target domain(s). 
TLS certificates, pulled from crt.sh or censys.io
https://transparencyreport.google.com/https/certificates

DNS records are all useful in different ways. The A records provide IP addresses and the other records provide some situationally interesting information.
manual checks, [dnsstuff.com](https://www.dnsstuff.com/)

**DNS Records: MX and TXT**
The DMARC and SPF records, or lack thereof, will help determine if email spoofing is in the cards for any social engineering campaigns.

**DNS Records: CNAMES**
This is also the time to look for Content Delivery Networks (CDNs) and cloud services mentioned in the DNS records. These records will reveal if a domain is pointed at an asset like an S3 bucket for web hosting. Also, some of the subdomains may be usable for domain fronting or vulnerable to a takeover of that subdomain (e.g. a dangling DNS record for a deleted S3 bucket).
http://flaws.cloud/

**Additional Network Information**
Finally, [RDAP](https://www.arin.net/resources/rdap.html) and [Shodan](https://shodan.io/) can fill-in some of the gaps in the information collected for all of these IP addresses and domain names.

**contacts**
hunt for email addresses associated with each of the domains the organization uses for their business. Email Hunter’s API

Email addresses open up opportunities for phishing and password spraying, but can be taken a step further. By **checking the email addresses against a service like Troy Hunt’s HaveIBeenPwned**, or a private database of security breaches and dumped passwords, employees can be matched-up with services they have used in the past.

Like most of the data collected so far, on its own this data is not terribly interesting. However, it can indicate how long each employee has been with the company (assuming they have not left by this point) and **might even hint at what they do there and the sorts of services the organization uses internally. Of course, it also means their old passwords might be available and, possibly, reused for a business account.**

**Additionally, hunting through paste sites (e.g. pastebin, ghostbin, slexy)** looking for the email addresses can yield some especially juicy information.
reporting a password came from such a breach is problematic. Use good judgement before blindly treating all pastes as equals in a client-facing deliverable.

**Social Media Profiles**
It is generally a good plan to take it easy with social media at this point in the intelligence gathering process. Wrangling what might be dozens or hundreds of social media profiles is a bit much for early reconnaissance.

basic Google searches like `site:linkedin.com COMPANY`
 harvest some names and information to get you started. Also, Email Hunter will return LinkedIn profiles links, supposedly pre-verified, if it knows of any.

the Twitter API can help verify the profiles. Just like LinkedIn profiles and email addresses, these handles will come back for searches against twitter.com.

A CEO may have a highly curated persona on Twitter and LinkedIn, which makes it difficult to learn much about the person behind the title and profiles. Manual analysis may lead to the CEO’s personal assistant who could have a more “honest” public presence on Twitter or Facebook.
Sometimes one or two steps removed is better than the higher value target. They are more likely to be accessible, less likely to be carefully monitored, and may offer more convenient access to the high value target.

**cloud**
 Basic Google searches, like `site:company.com filetype:pdf`
 Bucket hunting is hot right now, but do not neglect [Digital Ocean’s “Spaces.](https://www.digitalocean.com/products/spaces/)
 Hunting for these becomes just a matter of using a wordlist to create new web requests.
 Since the goal is to target a specific organization, the wordlist should be related to the company. At a minimum, try to include the company’s name, any acronyms or abbreviations they use, alternate names they might have, subsidiaries, and their NASDAQ listing (if they have one).

**automate**
Recon-ng and Discover Scripts. I took a shot at automating everything laid out above in a tool I named ODIN:

