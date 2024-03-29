# CybersecurityStudy
Study materials for cybersecurity.

## Web Security
OWASP Top Ten: https://owasp.org/www-project-top-ten/


## CTF
XCTF: https://www.xctf.org.cn/  
XCTF AdWorld: https://adworld.xctf.org.cn/  
CTMtime: https://ctftime.org/

## Penetration Test
Vulhub: https://vulhub.org/

## Try Hack Me

https://tryhackme.com/


## Vulnerability Websites

Often in hacking you'll come across software that might be open to exploitation. For example, Content Management Systems (such as Wordpress, FuelCMS, Ghost, etc) are frequently used to make setting up a website easier, and many of these are vulnerable to various attacks. So where would we look if we wanted to exploit specific software?

The answer to that question lies in websites such as:

* [ExploitDB](https://www.exploit-db.com/)
* [NVD](https://nvd.nist.gov/vuln/search)
* [CVE Mitre](https://cve.mitre.org/)

NVD keeps track of CVEs (Common Vulnerabilities and Exposures) -- whether or not there is an exploit publicly available -- so it's a really good place to look if you're researching vulnerabilities in a specific piece of software. CVEs take the form: CVE-YEAR-IDNUMBER
(Hint Hint: It's going to be really useful in the questions!)

ExploitDB tends to be very useful for hackers, as it often actually contains exploits that can be downloaded and used straight out of the box. It tends to be one of the first stops when you encounter software in a CTF or pentest.

If you're inclined towards the CLI on Linux, Kali comes pre-installed with a tool called "searchsploit" which allows you to search ExploitDB from your own machine. This is offline, and works using a downloaded version of the database, meaning that you already have all of the exploits already on your Kali Linux!

## Cryptography
[Cryptography](cryptography.md)

## CISSP
[CISSP](CISSP/README.md)

## FIDO

 
## MITRE ATT&CK


## NISP
[NIST SP 800-150](https://doi.org/10.6028/NIST.SP.800-150) Guide to Cyber Threat Information Sharing


## OASIS Cyber Threat Intelligence (CTI) TC

The [OASIS Cyber Threat Intelligence (CTI) TC](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=cti) supports automated information sharing for cybersecurity situational awareness, real-time network defense, and sophisticated threat analysis.  


[Documentation](https://oasis-open.github.io/cti-documentation/)




### STIX - A structured language for cyber threat intelligence

Structured Threat Information Expression (STIX™) is a language and serialization format used to exchange cyber threat intelligence (CTI).

STIX enables organizations to share CTI with one another in a consistent and machine readable manner, allowing security communities to better understand what computer-based attacks they are most likely to see and to anticipate and/or respond to those attacks faster and more effectively.

STIX is designed to improve many different capabilities, such as collaborative threat analysis, automated threat exchange, automated detection and response, and more.

[Read More](https://oasis-open.github.io/cti-documentation/stix/intro)


### TAXII - A transport mechanism for sharing cyber threat intelligence

Trusted Automated Exchange of Intelligence Information (TAXII™) is an application layer protocol for the communication of cyber threat information in a simple and scalable manner.

TAXII is a protocol used to exchange cyber threat intelligence (CTI) over HTTPS. TAXII enables organizations to share CTI by defining an API that aligns with common sharing models.

TAXII is specifically designed to support the exchange of CTI represented in STIX.

[Read More](https://oasis-open.github.io/cti-documentation/taxii/intro)



### Common source of TAXII data include:

[Anomali](https://www.anomali.com/resources/limo)  
[AlienVault](https://cybersecurity.att.com/blogs/security-essentials/otx-is-now-a-free-stix-taxii-server)  
[PickupSTIX](https://www.celerium.com/pickupstix)  
[MITRE ATT&CK](https://github.com/mitre/cti)
  
