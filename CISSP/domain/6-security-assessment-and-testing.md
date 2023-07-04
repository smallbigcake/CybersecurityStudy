# Security Assessment and Testing

## DESIGN AND VALIDATE ASSESSMENT, TEST, AND AUDIT STRATEGIES

The scope of and targets for audit or assessment should be designed to ensure appropriate systems, processes, and services are evaluated based on their value to the organization, as well as to meet obligations like regulatory or contract requirements.

Various audit and assessment methodology standards exist and may be used as a starting point to guide the organization’s strategy.
Utilizing a standard methodology offers key benefits including repeatable testing and results that will be more comparable over time.
Auditing against the same standard year over year can demonstrate return on investment (ROI) from the organization’s spending on security efforts, as well as the increasing maturity of key security practices or processes.

### Internal

Audits, assessments, and testing can be conducted from two perspectives. Internal evaluations are done inside the organization, with the staff and resources of the organization.
Any use of third-party assessors or auditors constitutes an external perspective, which is discussed in the next section.
When designing an audit strategy, different circumstances will drive the choice of internal, external, or even the use of both audit perspectives.

To conduct an internal audit, the organization must have adequate skills and knowledge on staff, it must have sufficient time and resources to perform the audit, and there must be no requirements for the audit or assessment to be performed by an independent observer who is totally free of conflicts.
Assessments conducted from an internal perspective are appropriate as part of ongoing or continual assessment processes and are often used as part of continuous monitoring with a supplemental external audit performed less frequently.

#### Preparing for External Audits

An audit conducted by internal personnel will never have the same objectivity as an audit conducted by external personnel. Internal audits are still a valuable tool, however, and are often used in preparation for an external audit.
An organization preparing for an external audit may choose to perform an internal readiness audit prior to engaging external auditors.
This offers the advantage of finding and correcting any deficiencies before they appear on an audit report, and conflict of interest is not an issue because the audience is the organization itself and not an external party.

#### Internal Audit Team

Depending on the size of the organization, there may need to be a full-time staff member dedicated to assessment activities, or elements of the assessment may be distributed among multiple staff members.
For example, access control reviews are often conducted once per quarter and may require only a few hours of work, so a single IT staff member can perform them in addition to other work assignments.
In a large multinational organization with complex user access requirements, multiple offices, and hundreds or thousands of systems, access control reviews could be a full-time job.

#### Confict of Interest

There is a general saying that “Whoever wrote the policy shouldn’t be the one to audit it,” and mitigating conflicts of interest is an important element in an audit or assessment strategy.
An internal auditor may be unintentionally blind to faults or may intentionally cover mistakes or deficiencies in the interest of maintaining their position.
In some cases, this conflict of interest may be mitigated by using an internal audit team that does not report directly to any of the department heads being audited.

#### Internal Audit Benefits

While conflict of interest can be an issue for internal audits, greater knowledge of skills, process, and systems in use at the organization is a potential positive.
Internal testers can more accurately perform tests or assessments with the knowledge of an insider, which helps identify issues related to insider threat.
Performing testing on complex systems with complex rules like separation of duties (SoD) can be challenging for an outsider.

#### Types of Testing

These are some types of testing that may be best conducted internally:
* Vulnerability scanning, especially routine scans looking for unpatched software or unknown assets
* Process and procedure audits like change management or training completion
* Phishing simulations

### External

The other perspective for conducing audits, assessments, and testing is external to the organization.
An external auditor should have no conflicts of interest, since they are paid to perform an impartial assessment rather than to deliver a report that makes their department look good.

#### Specialized Skills

External evaluations can also take advantage of specialized skills and knowledge that are valuable but not needed full-time.
Performing penetration testing, often called pen testing, is an important and valuable skill, but due to the specialized skills and high salaries required, employing a full-time pen tester is not cost-effective for most organizations.
Contracting an outside party to perform the test and sharing the costs with other organizations is a more sensible approach.

#### External Audit Benefits

The use of an external firm for assessments, testing, or audits can identify issues the organization is unintentionally unaware of; a fresh pair of eyes can often spot a problem more quickly and offer insight the organization would otherwise miss.
External testing may be advisable or even required in some cases, especially for legal or regulatory reasons, such as maturity assessments against a maturity model.

#### Compliance Purposes

Audits for compliance purposes — for example, PCI-DSS, ISO 27001, and the U.S. government’s Federal Risk and Authorization Management Program (FedRAMP) — all require the use of an independent, authorized third-party auditor or assessor.
The results of these assessments also need to be reliable for any organization doing business with the audited firm, so the use of a third party with no conflict of interest increases the assurance provided by the audit.

### Third-Party

Most organizations rely on a complex series of interconnected organizations, known as a supply chain, to support their operations.
A standard office building with workers performing basic data processing and collaboration relies on hardware manufacturers, utility providers, and probably cloud services, just to name a few.
Vulnerabilities in this supply chain can impact the organization, so an audit strategy is needed to identify risks and associated mitigations in the supply chain.

Supply chain audits are a topic introduced in Chapter 1, “Security and Risk Management,” and are a vital part of any security risk management program.
A sound third party audit strategy must be scoped to include any third-party critical to the organization’s operations, handling any data valuable to the organization, or providing regulated services like payment processing.

The audits may be performed by organizational resources or a third-party auditor retained by the organization to audit their suppliers.
Some suppliers may be able to provide a report performed by a trusted third party, such as a Service Organization Control 2 (SOC 2) Type II report, which provides details about the supplier’s security controls and their effectiveness.
A CISSP must verify if the services their organization is using were in scope of the audit report provided by a supplier.

## CONDUCT SECURITY CONTROL TESTING

Testing controls is essential to ensure they are implemented and operating as intended to mitigate risks.
Over time, processes and systems change, and the risks facing the organization evolve, so a CISSP must design a control testing program to provide reliable and accurate data about the state of controls.
This is a crucial piece of oversight that must support the ability to take action if a control is found to be deficient or no longer effective.

Testing may be done from internal or external perspectives and may target complex control implementations across people, process, and technology.

For example, testing a media disposal control might entail policy and procedure reviews, staff interviews, examination of disposal records, and physical selection of disposed hard drives or other media to test by plugging them into a computer to see if data is recoverable.

### Vulnerability Assessment

Vulnerabilities, which are weaknesses that could be exploited, are a major component of risk management and are discussed in detail in Chapter 1.
Vulnerabilities are typically disclosed more frequently than risk assessments are performed, so ongoing vulnerability assessments are a key element of a continuous monitoring strategy.
Hardware and software assets like servers, routers, operating systems, and applications can be vulnerable to attack, so technical testing is useful to identify vulnerabilities before an attacker does.
Finding vulnerabilities is one step in the process — it is also important to assess the impact of the vulnerability and prioritize remediation, which is where the security practitioner’s skills are valuable.

Assessing identified vulnerabilities includes analysis of their impact to the organization given the organization’s unique configurations or circumstances.
For example, a vulnerability that lets an attacker completely take over and delete data would be highly disruptive for an organization’s financial system but would cause only a minor disruption to an internal company portal that shares news like the daily menu in the office café.
Employees can always walk down to the café and see a printed menu!

The output of vulnerability scanners can also identify the use of insecure protocols like File Transfer Protocol (FTP), which in general should be avoided.
However, compensating controls may be in place that mitigate the risk, like network segmentation or the use of FTP for only publicly accessible, nonsensitive data.

#### Asset Inventory

Identifying the organization’s critical assets is an important prerequisite to performing a vulnerability assessment.
It is crucial to understand both the types of systems to be scanned and their criticality to choose appropriate scanning tools and prioritize scanning efforts.
The asset inventory should capture data from other organizational processes like a business impact assessment (BIA), which identifies the criticality of each system, application, or data asset.
Vulnerabilities in highly critical systems should be prioritized first since exploiting a vulnerability in a low criticality system is less likely to disrupt operations.

The asset inventory may also capture important data, like the system classification, needed to scope vulnerability assessments.
Systems handling sensitive or regulated information may have specific requirements related to vulnerability assessments, like how frequently they must be scanned, the use of specific configurations to perform scans, or the baseline used for comparison.
Scoping the scan targets can also be done using the asset inventory; for example, all assets marked as PCI in the inventory may be included in weekly scans using a PCI compliance configuration, while internal nonsensitive assets may be scanned monthly using the organization’s secure baseline configuration.

#### Scanning Tool Functions and Considerations

Many popular scanning tools can identify vulnerabilities in hosts, networks, or applications.
These include open-source tools that are free to use as well as commercial options; the choice to use open-source or commercial may include factors such as the availability of support, ability to scan specific systems or platforms, and the level of skill required to operate the tool.
Proprietary tools may offer more features and support, but with a correspondingly higher price.

Most scanning tools offer a similar set of basic features and operate in a common manner. These automated tools identify targets, which may be a single network endpoint or a range of IP addresses, and then send network traffic and listen for a response to determine if an IP address is in use.
Once an asset is discovered, the scan performs other automated actions to identify vulnerabilities, such as a port scan to identify active services like FTP or system-specific checks like querying the Windows Registry to identify installed software and patch levels.
Some scanners can perform application-specific checks, like identifying a web server’s supported encryption cipher suites.

Once the vulnerability scanner has identified relevant information, it can compare this information against a list of known vulnerabilities.
For example, a Linux webserver running an outdated version of the Linux kernel can be cross-referenced with a list of known vulnerabilities in that version; this list of vulnerabilities is the output of the vulnerability scanner and can be used to identify remedial action needed to address the vulnerability — in this case, applying patches.

Scan output should identify the criticality or severity rating for each finding, often using common standards like Common Vulnerability Scoring System (CVSS) scores or specific Common Vulnerabilities and Exposures (CVE) references.

When choosing and configuring a vulnerability scanner, there are several important considerations to ensure it provides valuable output. A CISSP should understand how these impact the output of the tool and strike a balance to ensure maximum benefit from the tool.

* **Obligations** such as legal, contractual, or regulatory, which may specify the scope, coverage, or frequency of scanning. A free vulnerability scanner might be appropriate for small environments without regulated data, but is likely insufficient for a heavily regulated financial services firm.
* **Depth, scope, or coverage** of the scanner, including the ability to perform advanced scanning by authenticating to targets being scanned with administrative credentials — sometimes known as credentialed scanning.
Vulnerability scanners may generate false positives or provide low-resolution information by only looking at externally accessible information, but many can be configured with credentials like an administrator password or Secure Shell Protocol (SSH) key that allows the scanners to log in and perform additional checks.
* **Platform support** is a major consideration for organizations with mixed IT environments, such as Linux and Windows server operating systems or macOS and Windows workstation operating systems.
Like all IT tools, the requirements for a vulnerability scanner should be defined, such as platform support or the ability to perform credentialed scans.
* **Cloud environments** may pose unique challenges for vulnerability scanning.
Software as a service (SaaS) environments may prevent users from performing vulnerability scans due to the operational overhead it introduces, which can degrade system performance, and not all vulnerability scanners can be run against targets outside a local network.
Some service providers share details of their own vulnerability scanning practices, which can be reviewed as part of a supply chain risk management.

#### Common Vulnerability Assessment Issues

Like many automated security tools, vulnerability scanners can cause issues or encounter problems. Avoiding these requires planning by security practitioners to develop a strategy.

Here are some common examples:
* Excessive traffic and denial of service (DoS)
* Alerts or incidents
* Cross-functional ownership
* Data integrity pollution
* Network segmentation

##### Excessive Traffic and DoS

Vulnerability scanners can generate large volumes of traffic that consume network bandwidth and can lead to DoS conditions on both networks and systems that struggle to process the information.
Proper configuration reduces the likelihood of these issues, such as implementing request throttling to limit the number of requests the scanner generates in a given time period.
Credentialed scans can also help reduce the amount of traffic — a credentialed scan can read configuration information directly from a server’s operating system to see what ports are open, rather than sending traffic to each port individually.

Scan scheduling may also be useful to ensure scans are conducted at times of low user activity. Spreading scans out over a larger time period can also be useful — scanning a few hosts per day reduces the impact of scanning an entire network.

##### Alerts and Incidents

Scanning hosts to identify open ports, well-known vulnerabilities, or other weaknesses is a common tactic used by attackers. When a vulnerability scanner performs the same actions, particularly if the scan triggers a DoS attack or unusual host activity, it will generate security alerts and possibly trigger incident response (IR) processes.
Many security tools are designed to flag activity commonly used by both attackers and vulnerability scanners, like sequential port scans. An attacker might send a request to each port number in sequence to identify open services that could be exploited, which looks similar to a vulnerability scanner identifying open services.
Configuring other security tools to ignore legitimate vulnerability activity is essential, such as marking port scans from the vulnerability scanner’s IP address as nonsuspicious.

##### Cross-Functional Ownership

Cross-functional teams and ownership of scan results can be an issue that requires a CISSP to have not only security skills, but also project and business management skills.
Vulnerability scanners are often owned by a security or IT team, while the applications and network assets where vulnerabilities are identified belong to another team.
Fostering a relationship across those teams is crucial to ensure vulnerabilities are taken seriously and addressed; otherwise, asset owners may simply ignore emails from the security team alerting them to issues discovered by the scanner!

Even if the asset owner is receptive to the findings from a vulnerability assessment, there may be additional issues of communicating the context of any findings.
For example, nonsecurity personnel typically do not understand CVSS scores, so those scores are not useful to prioritize the findings for remediation.
Communicating context to the audience is important and may require formatting results in a way that is best suited to the asset owner.

##### Data Integrity Pollution

Vulnerability scanners can perform automated actions like filling in form fields on a web application to check for issues including Structured Query Language (SQL) injection or cross-site scripting (XSS).
This testing data is obviously not real data that belongs in the system and can cause issues with reports or processes that expect valid data stored in the system.
Some scanners can be configured to ignore certain types of fields, like email address (which could result in unintended messages being sent), or the scanner can be configured to put in a recognized type of test data that can be easily ignored or cleaned up after the scan.
It may be necessary to conduct vulnerability assessments against a different environment altogether, such as a staging environment configured exactly like production but without live production data.

##### Network Segmentation

Segmenting or isolating different parts of a network with access controls like firewalls is a security best practice that may create problems when attempting to perform vulnerability scanning.
The vulnerability scanner itself is a network endpoint, and it requires access to all other endpoints in scope for scanning; if the network is segmented using virtual LANs (VLANs), routers, or firewall rules, the scanner may not be able to reach its targets.
Zero trust network architecture and microsegmentation are particularly challenging in cloud computing environments where these principles are the default and access follows a deny-all, allow-by-exception model.

Distributed scanning is an architecture that places scanning agents inside network segments to allow the endpoints in that segment to be scanned, and then consolidates the results to a central console.

### Penetration Testing

Penetration testing, or pen testing, is similar to vulnerability assessment but goes one step further. A vulnerability assessment merely identifies and reports on vulnerabilities in a system, while in a pen test, the tester will attempt to exploit identified vulnerabilities.
The tester seeks to emulate the same process an attacker uses to identify and exploit vulnerabilities, and these testers are often known as ethical hackers.
Ethical hacking has one key difference — the outcome is a report that the organization can use to fix vulnerabilities, while the outcome of a real attack is usually financial gain, theft, or disruption.

The exploitation of vulnerabilities in a pen test has both benefits and drawbacks. It may be difficult to prove whether results from a vulnerability scanner could actually be exploited, especially if compensating controls are in place.
Pen testers often use vulnerability scanners to identify vulnerabilities and then attempt to exploit them, thereby proving or disproving the severity of the vulnerability.
Potential drawbacks of this approach include the cost and the increased risk of disruption due to the testing activities.
Engaging well-qualified pen testers is more expensive than simply running a vulnerability scanning tool, and the active exploitation of flaws can lead to system outages and downtime; although testers typically avoid causing disruption, accidents or unintended consequences can and will occur.

The amount of information provided to the pen tester varies depending on the organization’s goal for the test. Different levels of information and the testing goals they support include the following:
* **White- or crystal-box** testing is total transparency. The pen testers have complete knowledge of the system or network to be tested, like IP addresses and system version numbers.
This name implies transparency or illumination inside the “box” being tested, since the tester has details and knowledge. This allows more complete test coverage and simulates an insider threat, though controls designed to hide this information from outsiders, such as network address translation (NAT), are not evaluated.
* **Black-box** testing provides zero knowledge to the attacker and instead relies on them to perform reconnaissance to gather details. The name demonstrates how the interior of the system (the “box”) is completely in shadow or dark to the tester.
This can validate controls designed to hide information like internal network configurations, from outsiders, but risks missing assets that the testers are unable to discover.
* **Gray-box** testing combines elements of both white-and black-box methods. Some information is provided to the pen testers, but they are also charged with finding other information like internal network configurations.

    Attackers, unlike pen testers, are not often constrained by time or the need to work billable hours in support of client services. A determined attacker can spend weeks, months, or even years observing an organization’s network and resources, while a pen testing contract rarely lasts more than a few weeks.
    Even highly skilled pen testers can miss something in this limited time, so gray-box testing offers a hybrid benefit.

#### Pen Test Scoping: It’s Not Safe to Ignore Systems!

Many organizations scope pen tests to focus on a narrow set of systems or applications, usually as a cost-saving measure since pen testing an entire network is costly. In other cases, the pen test simply meets a compliance requirement, so only particular systems are in scope.
While understandable, both approaches can create a false sense of security.

Networks are highly interconnected, which means a narrowly scoped pen test will likely miss vulnerabilities in out-of-scope systems that an attacker could exploit.
As one major retailer discovered, a breach at a third-party vendor allowed attackers to access a contract management system. From there, attackers were able to access and compromise a payment card processing environment.
Since the contract system did not process payments, it was outside the scope of many security controls like pen testing, but still proved a valuable pivot point to higher-value targets.

When defining a pen test scope, a CISSP should carefully balance available resources like time and budget to ensure optimum effectiveness of the testing.
If a pen test does discover something on a system that is out of scope, the organization should never ignore the finding just because it is “out of scope.” Attackers would certainly be happy to exploit that vulnerability.

#### Pen Testing Rules

Pen testing is an inherently dangerous activity with the possibility of internal incidents and even legal issues.
If testing causes unintended consequences, many pen test contracts include indemnification for the individuals or organization providing the testing services; this prevents the organization who acquired the test from taking legal action like filing a lawsuit.
Without such contracts in place, a penetration tester could be charged with criminal activity or business interruption if their testing activities cause a disruption.

Pen testing engagements should include defined rules of behavior, which document strict guidelines for what the pen testing team can do.
For example, if a vulnerability is discovered and can be exploited to cause a denial-of-service attack, the pen testers should document it but may be barred from exploiting it. Crafting proper rules of behavior and managing the pen test engagement are key tasks for a CISSP to perform.

The rules of behavior document for a pen test should provide a set of ground rules for testers to follow and provide the organization with adequate information to coordinate necessary resources and plans.
For example, if testing could cause a security incident to be triggered, then appropriate personnel may need to be briefed to ensure they calibrate the response accordingly. Rather than activating a contingency plan, the first step may be to confirm if the incident is the result of testing activity.
In this instance, the organization’s full response capability is not tested, and the penetration tester’s results can be used to identify and address security deficiencies.

Items that are typically defined in a rules of behavior document include the following:
* Which systems, offices, or other targets are in scope for testing?
* Are any systems, offices, or other targets specifically excluded from the scope of testing?
* Are any testing methods forbidden, such as social engineering or password cracking?
* Is physical security in scope? If yes, what facilities or targets are included?
* What level of access will testers be granted? Accounts may be provisioned for the testers in order to evaluate insider threats, or to perform verification activities if they are able to gain unauthorized access.
* What is the expected communication style and cadence? Some organizations may require immediate notice of any potentially critical security issues, while others may be satisfied to wait for a final report.
* Who is performing the test, what equipment and software is allowed, and when is testing to be conducted?
* What procedures are to be used for handling sensitive data like internal network configurations, customer records, etc.?
* How will sensitive data be securely disposed of at the conclusion of testing?
* What level of service is expected. For example, will testers perform re-testing immediately if a fix is implemented or wait for a defined re-test period?
* What are expectations for documentation, specifically details of any issues found, showing work done to verify the test results, and the format of any reports?

#### Pen Testing Phases

Pen testing activity can be broken down into a series of logically connected phases based on the pen tester’s objective. The first goal is to gather information, which is utilized to find vulnerabilities that the testers then attempt to exploit.
The final phase is documenting a report, which is where the pen testing and attack processes diverge — most attackers do not document their findings to help the organization improve cyber defenses!

| Phase                                | Goal                                                                                    |
|--------------------------------------|-----------------------------------------------------------------------------------------|
| Phase 1: Discovery or Reconnaissance | Gather information regarding the target(s)                                              |
| Phase 2: Scanning and Probing        | Utilize gathered information to probe for vulnerabilities and identify entry points     |
| Phase 3: Exploitation                | Utilize approved methods to exploit vulnerabilities and attempt to gain access          |
| Phase 4: Post-exploitation           | Continue the attack by attempting further exploits using the access gained              |
| Phase 5: Reporting                   | Document and present report on actions taken, exploits achieved, suggested remediations |

##### Phase 1: Discovery or Reconnaissance

Discovery or reconnaissance requires the pen tester to gather information regarding the target. This often begins with open-source intelligence (OSINT), since the tester wants to emulate attackers and remain undetected.

OSINT sources include the following:
* **Social media** to identify targets or useful personal details for phishing.
* **Public records** like Domain Name System (DNS) or company websites with information regarding services or locations.
* **Attack surface data** like enumerating the IP addresses associated with the target’s DNS records and potential details about services in use. Publicly available tools Shodan or Have I Been Pwned can also be used.
* **Physical observations** like monitoring employee movements, photographing, driving by, or observing facilities, or dumpster diving to obtain hard copy.

Pen testers generally try to evade detection by the organization and seek information outside of the organization’s monitoring abilities like DNS records, which are publicly accessible and maintained by a domain registrar.
Not all pen testers will perform extensive discovery, especially in a white-or gray-box test where the organization has provided this information.

##### Phase 2: Scanning and Probing

Once basic information is gathered in Phase 1, the testers identify potential targets and gather more detailed information.
For example, an IP address that leads to a marketing website with nonsensitive data may categorized a low-priority target, while URLs that clearly host high-value targets like remote.* or webmail.* are prioritized higher.

Scanning and probing require some traffic to be sent to the organization or target systems, which introduces the risk of detection by the organization’s security processes.

These are tools and resources that pen testers might use during this phase:
* **Network footprinting:** Testers define the footprint of a network, or what endpoints exist and services running on them. Tools like Nmap, nslookup, ping sweeps, and port scanning are used to perform queries that determine active network hosts and services running on a network.
* **Banner grabs:** Testers analyze information returned by endpoints, which often contains useful information including software names and versions.
* **Vulnerability scanning:** While an obvious approach, the use of a vulnerability scanner increases the pen tester’s efficiency. These tools automate tasks like footprinting and parsing information from banners.
* **Exploitation toolkits:** Tools like Metasploit combine reconnaissance, footprinting, vulnerability scanning, and partially or fully automated exploitation into a single software interface. Since these tools combine multiple functions, they are utilized across multiple phases.

##### Phase 3: Exploitation

This third phase is self-explanatory — the testers exploit the identified vulnerabilities and attempt to gain access. They may use a variety of methods as defined by the rules of engagement, which are discussed in detail in a later section.
The goal of exploitation is gaining access to systems or data that should not be accessible.

These are some automated and manual exploitation tools:
* Exploitation toolkits like Metasploit, which can automate many aspects of pen testing
* Password crackers like John the Ripper, Hashcat, or Hydra, which are useful if the tester gathers hashed passwords and needs to identify a valid password
* Monitoring tools and proxies like Wireshark and Burp Suite, which allow the tester to capture, analyze, and modify network traffic
* Application security tools like Nikto or fuzzing tools, which can identify and attempt to exploit application vulnerabilities like buffer overflows or SQL injection

###### Limitations of Pen Testing

Although pen testers try to emulate attackers, they may have some limitations. Attackers usually do not work on timeframes or within budgets, which gives them more resources to use for hunting and exploiting vulnerabilities.
Pen testers may be limited to a standard set of tools, while attackers may have more freedom to try new tools and processes.

###### Monitoring Pen Testing Activity

Due to the risk of pen testing activities causing real operational and security incidents, it is important for the security practitioner to monitor the process closely.
Although pen testers typically avoid causing major disruptions, they might discover a vulnerability that causes an application to crash or corrupt data.
Unintended consequences like an operational outage should be disclosed to the testers quickly so the testing activity can be stopped, and internal communication may also be necessary to alert personnel to the testing activity and avoid drastic measures being taken, such as activating an expensive disaster recovery plan.

##### Phase 4: Post-exploitation

Once the testers have gained initial access, they will attempt to pivot or use that access to gain further access. For example, compromising a system in the demilitarized zone (DMZ) is not highly valuable since sensitive data is typically not stored here.
However, DMZ assets may be authorized to connect to endpoints on an internal network segment, which could grant the tester unauthorized access to something more valuable.

The compromised DMZ could even be used to iterate Phase 2 activities and perform network footprinting of internal resources that are not reachable from outside the network. Endpoints or assets discovered will be categorized, and attention will be paid to high-value targets.
Once network endpoints have been enumerated, various techniques are used to fingerprint them — the goal is to discover useful details like operating system and application software versions.
Exploits will be tried against these until the tester is discovered, runs out of time, or exhausts all identified possibilities.

##### Phase 5: Reporting

Throughout the testing process, documentation should be created to capture all activities performed, vulnerabilities found, and any access the testers achieve.
These findings are compiled into a report, and it is typical for the testers to include recommendations for the organization to remediate any identified vulnerabilities.
This report is usually presented in a formal meeting, which marks the end of the pen test engagement.

Different reports, or different parts of the report, may be designed for different audiences.
An executive summary with the scope, high-level synopsis of tests performed, and number of findings is often prepared to share with management or users outside the organization, while more technically detailed parts of the report are in a separate document or appendix designed for internal IT staff.

#### Physical Penetration Testing

Physical security is a critical aspect of securing systems and data, so some organizations may need to conduct physical penetration testing.
Testers attempt to gain unauthorized access to facilities like offices or data centers, with the goal of identifying potential weaknesses in physical security controls.
Social engineering tactics like carrying a bulky item and asking someone to hold the door or showing up dressed as an official are often utilized.

Gaining unauthorized physical access to certain facilities is illegal in some circumstances, so physical pen testers should be given a get out of jail free card that details the purpose of their activity and a point of contact within the organization who can verify their story.
In the event the tester is captured or detained, the test is concluded, since they failed to gain access and evade detection, and the card can be presented to help them avoid potential legal trouble like being arrested and charged with trespassing.

In high-security organizations, especially those with armed guards, it is important to properly coordinate penetration testing with stakeholders like the guard staff to ensure they are prepared to respond appropriately if a tester is discovered.

### Log Reviews

The fundamentals of logging and monitoring are covered in Chapter 7, “Security Operations,” but a CISSP should remember that logs play an essential role as detective controls in a security program.
They can be generated by most systems, endpoints, devices, and applications, and the capability to generate logs should be turned on and configured to capture meaningful information.
This information is made useful by reviewing it — if an attacker has gained access and the logs capturing the malicious activity are ignored, the attacker may evade detection.

Assessments and audits often rely on log entries as artifacts to directly prove that the organization’s technical controls are in place and operating as intended.
For example, if the organization’s access control policy states that access to a critical system is available only during normal business hours, then auditors may look for both positive and negative enforcement of this control: system configurations that enforce this restriction, and logs that show users denied access when attempting access outside the defined hours.

The practice of log management is itself subject to auditing and assessment. Policies, procedures, and technical configurations for log generation, management, and review should be in place, and auditors may examine these to identify compliance with standards such as ISO 27001 control A.12.4, PCI-DSS Requirement 10.6, or the Audit and Accountability (AU) family of controls in NIST SP 800-53.

### Synthetic Transactions

Synthetic transactions are automated activities run against a monitored target to measure its performance.
For a web application, this might involve logging in with a test user account to verify if the application responds to the login request or returns data in response to queries.

#### Transaction

The term transactions does not necessarily mean financial transactions, but can be any system activity like querying for data or making a request for services.
Monitored objects can be any system or application, such as a DNS or Dynamic Host Configuration Protocol (DHCP) server, and the synthetic transaction is a request for a DNS resolution or assignment of an IP address.

Synthetic transactions can be employed as a test mechanism for a variety of purposes:
* SLA monitoring: Hosted or cloud-based services may guarantee certain levels of service, such as a SaaS application that guarantees 99.9 percent uptime. Synthetic transactions can be used to log into the application every hour to verify if the service meets the agreed level.
* Data integrity monitoring: Systems with complex business logic may have dynamic rules for handling data. Synthetic transactions can be used to monitor these rules and alert administrators if processing a set of test data does not result in the expected outcome, which indicates issues with the business logic rules.
* System or service monitoring: Even in the absence of an Service Level Agreement (SLA), systems can be monitored to ensure they are online and responding as expected. This is often known as heartbeat monitoring and is a detective control that identifies services that are offline or unresponsive.

#### Real User Monitoring (RUM)

Real user monitoring (RUM) is often discussed along with synthetic transactions. RUM monitors users in real time as they interact with an application or service and can be useful for detecting issues like slow or unresponsive pages.
Unfortunately, RUM tools also introduce privacy concerns as they often record every user interaction with an application or web page. This includes users entering sensitive data that may be captured by the RUM agent.
Even if the application safeguards the data entered by users, the RUM tool may not; several RUM tools have caused data breaches by recording and storing sensitive or regulated information like financial data and user passwords.

### Code Review and Testing

Code comprises software and is the foundation of information systems, so reviewing and testing this code to identify and remediate flaws is an essential security control.
Bugs or vulnerabilities in the code can impact the security of the overall system and any data it stores or processes.
Additional topics related to code reviews, testing, and software security are covered in Chapter 8, including common frameworks for assessing or describing software vulnerabilities like the Common Weakness Enumeration (CWE), CVSS, and the Open Web Application Security Project (OWASP) Top 10 security vulnerabilities.

Although a CISSP may not be directly responsible for writing or maintaining code in a system, which is the responsibility of a software developer, it is vital to understand the importance of adequate code review and testing measures.
Code testing should be designed and implemented to detect and correct software vulnerabilities and ideally to detect flaws close to the time the code is written. It is generally easier to make changes while the code is still under development, and two main approaches may be used to support this goal:
* Black-box testing: The tester does not have access to the source code or internal workings of the application, modeling the perspective of an external attacker or user.
* White-box testing: The tester has access to the source code or knowledge of internal elements of the application like Application Programming Interface (API), which an outsider would not have.

Code testing may be done using automated tools or manual processes like code peer reviews, where developers manually review and edit the work of a peer to spot mistakes.
Automated tools such as static code analysis use software to model the execution of code and identify potential vulnerabilities like buffer overflow or inconsistent data conditions that could result during program execution.
Dynamic analysis tests the actual running program to observe the behavior of the system or application.

A CISSP should ensure that code review and testing controls meet the objectives of both security and business needs.
For example, the testing should provide adequate coverage across the application code to detect flaws without introducing unacceptable delays into the software development process.

Development practices in DevSecOps rely heavily on automated, repeatable testing in the continuous integration/continuous delivery (CI/CD) pipeline to balance delivery speed and security, and emerging security concepts like security orchestration, automation, and response (SOAR) apply a similar focus on automating security incident response; both topics are covered in detail in Chapter 8.
These tests should be supplemented by manual testing like a penetration test or formal code testing on a less frequent basis to ensure deeper analysis is performed.

### Misuse Case Testing

Misuse case or negative testing is designed to assess how a system or application responds to unexpected inputs or situations, and identifies vulnerabilities which might be exploitable under these unexpected circumstances.
In the context of software development, a use case describes the expected interaction between an actor, typically a user or process, and a system.

For example, a use case for system login would describe the steps the user takes to reach a login prompt, enter their credentials, and then be either granted or denied access as appropriate.
A misuse case describes the opposite: what happens when the system is not used as expected?

Vulnerabilities have been found in several applications when users supply incomplete or unexpected information at a login prompt.
The use case expects a user to enter a username and password; instead, a user enters a username but leaves the password blank.
This might cause the applications to crash, or worse — Apple’s macOS contained a bug where secure configuration settings could be accessed by supplying a username of “root” and leaving the password field blank, as documented in CVE-2017-13872.

Common elements of misuse case testing should be incorporated in system test plans and activities and often focus on system behavior when unexpected values are entered in application fields, such as incorrect data formats or data that is significantly different than what is expected.

For example, how does the application behave when a string of text is entered into a field where a numerical value is expected, or the text of an entire book is pasted into a field designed to contain only a few words?
Null or blank values should also be considered, as demonstrated in the previously described authentication bug where a username and blank password incorrectly granted access.

Misuse cases can test for application behavior in unintentional circumstances, such as a user accidentally entering their phone number in a field designed to hold their name.
Abuse case testing models how a system or feature might be misused in a way that was not expected and specifically describes how an attacker might exploit this weakness.
Modeling these cases can be useful to identify threats to a system or its data and assists in designing controls to mitigate the risk.

#### Abuse Cases

Unlike a misuse case, an abuse case is a specification of a deliberate, harmful interaction between a user and a system. They are often used to identify security requirements by specifying the ways a system could be abused by a malicious actor and are an integral part of threat modeling.

### Test Coverage Analysis

Test coverage refers to the number of functions in a system or application that are tested and can be expressed as a percentage of the total system that has been tested or a specific number of things tested, such as functions or modules.
Testing involves costs, so a key concern for the security practitioner is ensuring that adequate test coverage is achieved for critical system functions even if all functions cannot be tested due to cost.
Since code testing may be the responsibility of other teams within the organization, a CISSP may be a stakeholder responsible for communicating requirements and validating test plan designs to ensure the chosen tools and test strategy achieve the desired level of coverage.

Test coverage analysis measures four main criteria to identify sub-elements of a program or system being tested:
* **Branch coverage** ensures that each branch in a control statement has been executed.
* **Condition coverage** requires each Boolean expression in the code to be validated for both true and false conditions.
* **Function coverage** makes sure that every function in the program is called.
* **Statement coverage** validates the execution of every statement in the program.

Additional coverage measurement includes more advanced criteria like decision coverage, which validates combinations of function and branch coverage to test various input and output scenarios, as well as parameter coverage to test the behavior of functions that accept parameter inputs.
This can identify vulnerabilities related to unexpected or malformed inputs and is especially useful for applications that accept user-supplied data.

In an ideal scenario, test coverage would be 100 percent across the system or application, but costs and complexity associated with this level of testing may be prohibitive.
A CISSP should identify criteria like the sensitivity of data handled by the system, impacts to human life or safety, and the organizational criticality of the system when developing requirements for acceptable test coverage, and should ensure test coverage is adequate.
The definition of adequate will vary between systems and organizations, but in general, sensitive functions like user management, system administration, and sensitive data handling should be most thoroughly tested.
Compensating controls may also be considered to mitigate untested system elements, such as an air-gapped system or additional continuous monitoring targets.

### Interface Testing

An interface is an interaction point with a system. Examples include the user interface (UI), which provides a way for a human user to interact with a system, and APIs, which are used for system-to-system interaction.
UIs often take the form of a graphical user interface (GUI) with windows and menus or text-based interaction using a command-line interface (CLI).
APIs may be implemented using a variety of methods like Representational State Transfer (REST) APIs for web applications, inter-process communication (IPCs), and remote procedure calls (RPCs).

Evaluating interface functionality and security is a critical part of system testing. Security controls should be implemented in interfaces to support security goals of confidentiality, via access controls, or nonrepudiation, via logging of actions executed using the interface.
Interface testing may be part of standard software development testing conducted by developers and is also a key element in security testing activities overseen by security practitioners, such as vulnerability assessments, penetration tests, and security testing like breach simulations.

Like many system testing functions, interface testing should identify if the interface behaves as expected under both typical use and abnormal circumstances like dealing with unexpected or malformed input.
Interfaces, like all elements of a system, should have clearly documented requirements, test cases, and acceptance criteria to determine if they adequately implement the required levels of data protection.

Organizations with large and complex systems, or those with distributed components, may find server interface testing to be an appropriate area of focus.
Interfaces between application servers, web servers, and databases are critical points of security control implementation and should be targeted to test the effectiveness of multilayered security controls.
For example, if a web application accepts user-supplied input, then the application’s input validation controls must be tested to ensure they reject incorrect data.
In case this control fails, the interface to an application server may also incorporate logic to verify that incoming data conforms to expected parameters, providing a defense-in-depth input validation control.

Web application interfaces are particularly complex due to the possible inclusion of systems outside the organization’s control. A web application with external users may require unique access management controls like session management to identify, authenticate, and track user interactions.
If cookies are used to store information like session tokens or other identifying information, then the interface between outside user systems and the web application should be considered when defining interface testing requirements.

### Breach Attack Simulations

Breach attack simulations or breach and attack simulations (BAS) are an emerging method of automated testing designed to simulate a realistic attacker attempting to gain unauthorized access. BAS combines elements of vulnerability scanning and automated penetration testing.
BAS tools utilize a continuously refreshed database of attack methods and newly discovered vulnerabilities to test the ability for the organization to withstand newly evolved threats.
Implementing a BAS solution allows this testing to be done more frequently to identify potential vulnerabilities sooner than legacy approaches like a quarterly vulnerability scan or yearly penetration test.

BAS tools perform automated attacks modeled after real attack vectors utilized when attempting to breach a network or system. If the simulated attacks are blocked, then the security controls functioned as intended.
However, if an attack is successful, it could indicate a deficient control or a new risk that is not addressed by existing controls.

The categories of attacks carried out by a BAS are often categorized by the target or vector and can include the following:
* **Endpoint:** The BAS performs action on or against a network endpoint, such as creating files or processes that match known malware signatures to test endpoint detection and response (EDR) capabilities.
This may be accomplished remotely from a BAS appliance or console or may utilize a software agent running on the endpoint.
* **Network:** The BAS sends network traffic that should be blocked and generates an alert if known bad or malicious traffic is not blocked by controls like firewalls or routers.
* **Email:** Spam filters, email spoofing controls, and content filters can be tested by test messages generated and sent by the BAS. If messages reach inboxes or are opened, it indicates a deficiency in email security controls.
* **Behavior-based:** Advanced BAS functions can test behavior-based security controls like security tools monitoring for malicious network scans or complex interaction with applications that should be blocked by a web application firewall (WAF).

### Compliance Checks

Compliance frameworks generally combine a set of risks specific to an industry or region, and the required security controls are designed to mitigate them. Compliance should be treated not as a security objective but as a starting point to help an organization’s risk management program.

Compliance checks are a part of oversight designed to verify the status of controls in place to meet compliance objectives. Audits are a common method of checking this status; further details on conducting or facilitating audits are presented later in this chapter.
Formal audits or assessments are conducted on a defined schedule, such as annual audits for PCI-DSS and SOC 2, or ISO 27001 audits once every three years.

#### Continuous Monitoring

Most compliance frameworks recognize that an audit at a single point in time is not an effective way to monitor security risk.
The purpose of the scheduled audit is to evaluate the security program at a specific point in time, and the compliance frameworks typically include requirements for more frequent assessment of key controls or areas.
Some compliance audits, like SOC 2 Type II and ISO 27001, require the evaluation of security over a period of performance, so the auditors will review data and artifacts from a specific time period (typically the last year) to determine if the organization’s security program was functioning as intended during that time.

#### Examples of Compliance Frameworks

Some examples of security and compliance frameworks that require compliance audits are identified here:
* ISO 27001 audits are performed every three years by an external auditor to achieve certification, while the organization must perform continuous monitoring and oversight, including internal auditing and surveillance audits on an annual basis.
* PCI-DSS requires organizations to undergo an annual audit by a third-party auditor and perform routine internal activities such as quarterly vulnerability scans.
* FedRAMP requires an ongoing annual assessment after the initial full security assessment and also requires a continuous monitoring strategy for key risks in order to maintain Authority to Operate (ATO) status.

#### Goals of Compliance Checks

Compliance checks and continuous monitoring, which are discussed in Chapter 7, share a common goal: identify weaknesses as soon as possible and take corrective action before an attacker finds the weakness.
Compliance checks can uncover controls that are deficient or ineffective due to changed risk circumstances, or controls that are no longer being properly executed.
A CISSP should seek to balance the costs and operational overhead of performing these compliance checks against the threat landscape facing the organization, including the risk of noncompliance.


## COLLECT SECURITY PROCESS DATA

#### Importance of Continuous Monitoring

Once an organization has identified risks and implemented appropriate controls to mitigate them, it is important to monitor the status of those controls and their effectiveness at achieving the desired risk mitigation.
A CISSP must ensure that adequate data is collected and analyzed to support monitoring and oversight of how effective the organization’s security controls are at mitigating risk.
The strategy for and practice of continuous monitoring is discussed in Chapter 7, and the sources of data that should be monitored are discussed in the following sections.

#### Status of Continuous Monitoring

Continuous monitoring is a complex task that requires an organization to have mature cybersecurity capabilities.
Like any complex process, it is best to approach the implementation in stages, beginning with fundamentals like performing a thorough risk assessment and designing a security control program to mitigate the identified risks.
Once these controls are in place, a logging and monitoring strategy can be developed, starting with basics like enabling logging on all systems, centralizing log files, and automating monitoring with tools like a security information and event management (SIEM) platform.

#### Measurement and Metrics

The volume of data generated by monitoring security processes and control implementations can make the task of monitoring overwhelming. Rather than looking at raw data, measurements or metrics can be useful to identify trends or useful information.
Data trends can be analyzed using automated means to generate trending data such as key performance indicators (KPIs), and the emerging field of artificial intelligence and machine learning (AI/ML) offers some solutions to automate data analysis tasks.

A CISSP should be able to identify relevant information to monitor when looking at all possible sources of security process data. Reviewing every change request ticket individually is not an efficient use of time, but monitoring the number of changes that require a rollback can be a useful way to identify deficient change review processes.
This metric supports obvious next steps — the change review process and changes that required rollbacks should be examined, and any findings can inform process changes.

Designing a security metrics program requires two key elements. First, an understanding of the security program objectives is essential, as this is the reference point for the metrics. Second, the security controls must provide a method of measurement or quantification.
For example, if multifactor authentication is required for all logins, access control logs can be queried to determine if this requirement is enforced 100 percent of the time.

### Technical Controls and Processes

Technical or logical controls are implemented with or by electronic systems, like username and password prompts to access an information system or the configuration of a firewall to reject traffic from a known malicious source.
Collecting data from technical controls can be straightforward since electronic systems usually support logging natively.
Technical process data may include information captured as part of the organization’s logging and monitoring strategy, or it may be generated via analysis of that log data.
Examples include application user access logs and logs from network devices like routers or firewalls.

Designing a technical metrics program should be done to measure the organization’s effectiveness at implementing multilayered security. To do so, it is useful to capture metrics across categories like these:
* **Prevent:** Preventative technical processes include encryption of data and securing access to decryption keys, network access controls like virtual private networks (VPNs), and endpoint controls like host-based firewalls.
* **Detect:** These technical processes include any controls that detect incidents or deviations, such as EDR and SIEM. Detective security data may come from controls that overlap with operations, such as monitoring the status of hardware or software to detect unexpected outages.
* **Respond:** When something goes wrong, response controls are designed to correct the issue, and include EDR as well as network- and host-based intrusion prevention systems (IPSs).

### Administrative Controls

Administrative controls are implemented in policies and procedures, like acceptable use policies, access review procedures, and personnel security controls such as job rotation.
Unlike technical security processes, administrative processes do not automatically generate data like audit logs that can be easily monitored.
Data regarding administrative processes may instead come from evaluation of process artifacts, which are objects created or used during process execution.

Artifacts are often indirect sources, like a guard recording that they performed a walkthrough of a facility at a particular time, or an incident report filed by the guard for an unlocked workstation discovered on the walkthrough.
The record of the walkthrough indicates a process was executed, while the incident report provides details of a user who violated a clear screen policy.
Direct sources often include documentation, which may prove confusing since documents are often managed in digital form using information systems. Even though the data comes from an information system, it still supports measuring an administrative control.

Take, for example, an organizational policy barring personal social media use on organization-issued equipment.
This policy will have administrative components like an acceptable use policy and employee training and awareness, and it may comprise technical controls like web content filters or blocklists.

Metrics about the implementation of this control could measure the following:
* **Policy reach:** How many users have read and acknowledged their understanding of the policy by signing it?
* **Education effectiveness:** How many users attempt to access restricted content?
* **Technology effectiveness:** Based on web traffic, how many users are able to reach restricted content, and how effective are technology controls at enforcing the policy?

### Account Management

An account is a set of credentials used to access a resource. Usernames and passwords are a common example for user access, and there are other types of credentials like encryption keys, which can be used both to protect data and identify the user, system, or process accessing it.
Identity and access management, including identification, authentication, authorization, and the account management lifecycle used to provision, review, and deprovision these access control elements are covered in Chapter 5, “Identity and Access Management.”

Account management data is a critical area to focus on when collecting security process data, because access control is fundamental to information system security.
Access controls are also a crucial example of blended control types — policies are implemented using process and procedure, implemented using technology systems, and may require physical controls like managing facility access or safeguarding account tokens like smart cards.

Take, for example, an information system’s account management requirements. To restrict and monitor access, the following controls may be put in place. The data generated by these controls should be collected and analyzed to evaluate effectiveness.

* Administrative process for requesting user access, including formal request and approval before access is granted. This may require an access request ticket or hard-copy access request form.
All user accounts must have corresponding request and approval documents, which must contain all required information like user role, justification for access, and necessary approvals.
Audit and other assurance activities over these processes and artifacts are also a part of the administrative controls.
* Technical implementation might include the system for submitting the request, performing reviews and approvals, and the actual identity and access management tool where the user account is created like Active Directory, Okta, or a local computer operating system.
A highly sensitive system may also utilize network access controls such as a segregated VLAN or restrictive firewall rules. If a system supports unique API login credentials, a secure method of distributing API keys, such as a secure API site, might also be needed to provision access.
* Physical controls will also be used to enforce the access control, such as placing information system components in access-restricted spaces.
The implementation of user access controls may also utilize physical devices like tokens, smartcards, or trusted devices, which require policy, procedure, and training to ensure restricted physical access is maintained.

Key process data to collect from account management processes includes the following:
* Timely account management such as removal of access within specified timeframes after a user changes roles or leaves employment
* Timely notifications received for account provisioning or deprovisioning, like notification within 24 hours of a user joining or leaving the organization
* Proper account reviews performed according to the organization’s defined schedule
* Proper process execution such as out-of-bound distribution of passwords, proper verification before password resets, or properly configured network access controls

### Management Review and Approval

Management is responsible for defining and executing the mission of an organization, including supporting functions like security and privacy.
In some organizations, a security practitioner like a CISSP will be in an executive role to manage mission objectives, while in others, a security practitioner will be tasked with providing data related to security and privacy processes to management.
Management support and sponsorship of security initiatives is crucial, as it provides direction and support.

Each of the techniques and procedures discussed in this chapter play a role in management oversight of the security program.
Assessments, audits, and ongoing monitoring of security process metrics provide timely data to management, and it is essential for decision-making like identifying organizational risks and the proper course of mitigating action.
Examples include short-term decisions like a disaster necessitating activation of the business continuity plan (BCP), or long-term decisions like changing architecture from on-premises hosting to cloud-based systems due to the cost benefit of self-hosting compared to outsourcing.

Management review and approval of security process data should be performed to ensure that controls are functioning as intended; that is to say that they are reducing risks to an acceptable level and that previously accepted risks are still within acceptable parameters.
Changes to the organization’s operating environment can render controls ineffective, even if they were previously adequate to reduce risks.
Examples including launching new lines of business, the addition of new systems or processes, new compliance or regulatory obligations, and organizational changes like mergers, acquisitions, and divestitures.

To perform adequate review and oversight of a security program, the organization’s management will monitor a variety of sources. The continuous monitoring program should generate metrics and performance indicators, which are reliant upon security process data.

### Management Reviews for Compliance

There are several frameworks that formally define management review and approval processes related to security. This oversight task is a key element of governance and risk management, which is covered in Chapter 1.

Specific security and compliance frameworks, and their requirements for management review, include the following:
* **ISO 27001** control 9.3 specifies that management must periodically review the information security program for “continuing suitability, adequacy and effectiveness.”
* **NIST and FedRAMP** define management roles for assessment and authorization and continuous monitoring.
Management must review the plans for assessing information systems and the results of assessments and then make a formal decision to authorize the system for use by issuing an authorization to operate (ATO).
Management uses continuous monitoring data to ensure risk remediations remain effective.
* **Certification and accreditation** are similar to assessment and authorization. Certification is a formal process for evaluating a system or process against a set of criteria, and accreditation is a formal decision about the system’s fitness to perform the specified function.
Any organization can use this to develop management processes for formally evaluating and approving systems based on security capabilities and requirements.
* **SOC 2** requires management to establish “performance measures,” as well as generate and use “relevant, quality information to support the functioning of internal control.”
* **Control Objectives for Information Technologies (COBIT)** is a management framework for IT and cybersecurity, and it is geared toward high-level management tasks like planning adequate resources, capacity, and oversight tasks like reviews of the organization’s control program.

Senior and executive managers are not the only stakeholders with responsibilities for reviewing and approving security control effectiveness.
Information system owners, data owners, and custodians will also have responsibility for ensuring adequate controls are in place when handling data, as well as reporting any issues or deficiencies they encounter.

### Key Performance and Risk Indicators

As a CISSP, it is important to measure not only existing performance, but also to maintain awareness of how situations may change in the future.
Security metrics communicate the effectiveness of existing security controls at mitigating risk and monitor the state of risks that could impact the organization in the future.

Key performance indicators (KPIs) are the monitoring tool for existing risk mitigations, while key risk indicators (KRIs) allow the organization to maintain awareness of potential future risks.
Both are essential to a governance, risk, and compliance (GRC) program and provide proactive and reactive input to the GRC strategy.

Every organization will find different metrics useful and must take into account a variety of factors when determining which indicators are meaningful and worthy of monitoring.
To use a nonsecurity example, a driver with cheap gasoline but poorly maintained roads is likely to monitor the health of a car’s tires.
A driver with the same car in a location with expensive gasoline but well-maintained roads might instead be concerned with the car’s performance in miles per gallon or kilometers per liter.

Both are useful indicators that provide usable information, but the circumstances dictate which is more applicable in a given situation.
A CISSP must understand the business context of their security program and ensure that both KPIs and KRIs are chosen to provide this useful information.
This requires coordinating with stakeholders including the user community, management, and possibly outside parties like regulators or business partners.

#### Key Performance Indicators

The terms KPIs and metrics are often used interchangeably, but there is a difference. Metrics are simply measurements, like the number of patches applied to a computing environment.
A performance indicator uses metrics and provides context (an indication). For example, the number of patched endpoints divided by the total number of endpoints in the environment is an indicator of the effectiveness of a patch management program.
If the organization expects 100 percent patch coverage after seven days, then this KPI can be used to gauge the performance of that program against the expectation.
If the number is below the expectation, it indicates remedial action needed, such as manual application of patches or isolation of unpatched endpoints from the network until they have been properly remediated.

##### Information Needed and Baselines

When designing KPIs for the organization’s security program, it is helpful to understand the information needed by the organization and essential to ensure the KPIs provide clear information to support decision making.
KPIs should exist to identify how effectively controls are operating to mitigate risks, and provide notice if a control is ineffective, which indicates a risk that may be more likely to occur.
A performance baseline must be established, well as thresholds for upper and lower bounds on the process being monitored.
Processes may have strict or loose requirements for performance, and the thresholds will reflect that — any deviation from the baseline is cause for concern in a strict process, with greater variation allowed for a loose process.

Patch deployment timeframes are a good example of a KPI. If the organization has set the baseline at seven days after the patch is released, then any patch deployed after the seven-day window is a negative indicator in a strict situation.
In a loose example, patches deployed 8–10 days after release may be acceptable but do not require additional action. The KPI can even be used to measure the success of improvement efforts — if patches are consistently deployed in less than seven days, then the improvement worked.

##### Frameworks

Developing high-quality KPIs can be a challenge. Frameworks exist, including ISO 27004, “Security techniques — Information security management — Monitoring, measurement, analysis and evaluation,” and NIST SP 800-55, “Performance Measurement Guide for Information Security.”
The Software Engineering Institute (SEI) at Carnegie Mellon University has also developed a framework called the Goal-Question-Indicator-Metric (GQIM) Method, which is designed to assist organizations in defining measurement strategies that provide meaningful information.

##### Determining Targets and Frequency

Determining targets and frequency of monitoring should be done by identifying organizational goals, critical systems, and the controls in place to mitigate risks to those goals or systems. As always, balancing the cost of measuring with the benefits is critical, as sampling a process or system every day can be costly.

Examples of important metrics to track and define KPIs for include the following:
* **Mean time to detect (MTTD):** This measures the mean time required to detect a security incident or threat.
* **Mean time to resolve (MTTR):** This measures the time required to resolve incidents.
* **Security scores:** Many vendors provide security scorecards or grades, which can be an indicator of the maturity of an organization’s security efforts.
Note that these externally provided scores may not capture all the necessary details, so receiving an A or 100 percent, similar to passing a compliance audit, should not be interpreted as being entirely secure.
* **ROI:** This is a challenging area for many CISSPs, since business concerns like finances are often outside the scope of a technology or security practitioner.
However, the risk-reducing effect of controls must always be balanced against their cost.
Management may require an indicator showing how effective a particular security control or program is at reducing costs — for example, if phishing costs the organization 100 lost hours of productivity each month, then anti-phishing training must cost less than 100 hours and result in a reduction of lost productivity due to successful phishing attacks.

#### Key Risk Indicators

KRIs can provide the organization with a window into future risks and should be designed to capture how the changing risk landscape might impact the organization.
The indications from KRIs can drive proactive mitigating action — for example, a rise in the volume of malicious traffic being blocked by a firewall can be an indicator to upgrade the firewall before it is overwhelmed.
KRIs often support long-term management decision-making, like a firewall upgrade project requiring lead time for IT budget and resource allocation to avoid the risk of system disruption by malicious outsiders.

##### Sources of KRIs

Sources of KRIs include common security practices like vulnerability scanning, auditing and assessments, security incident response, malware infection and containment rates, and other security process data.
The indicators should measure the adequacy of existing security controls to deal with changing risks.

##### Examples of KRIs

Continuing the example of patch deployments from earlier, a KRI might be set for the latest patches to be present on a specific percentage of endpoints.
If patch deployments are delayed and the number of unpatched endpoints rises above the threshold, then the organization is at risk of any the unpatched vulnerabilities being exploited.
Corrective action like initiating a security incident response and manually deploying patches could be an appropriate response.

Examples of other valuable KRIs include the following:
* **Number of security incidents:** An increase in the number of security incidents could indicate that the threat environment has changed, and more robust security tools or additional staff are needed.
* **Number of findings:** An increase in findings from audits and assessments could indicate security program deficiencies that require additional attention or resources.
* **Number of phishing attempts detected or reported:** An increase in phishing attempts is often the precursor to an attack, as attackers seek to gain valid credentials to access the organization’s resources.
Additional system monitoring, multifactor authentication (MFA), and user training could all be deployed in response to this threat.

### Backup Verification Data

Data and system backups are an essential control for integrity and availability, so ensuring they are usable in the event of data loss or corruption is critical.
The first step is identifying critical data or systems that the organization needs to continue operations and designing a backup strategy appropriate for the recovery needs, which is covered in more detail in Chapter 7.

Once procedures and systems are in place to perform backups, it is important to verify the integrity of both the backup process and the backup data. Both can be evaluated by performing a test restore from backup media to ensure that all required data is present and readable.
If data is missing, it could indicate backup configuration issues like directories or systems that are excluded from the backup, or corruption of the backup media.
Some backup systems include integrity checking as part of standard operations and can be configured to automatically verify backup integrity, generate alerts if integrity loss is detected, and automatically retry the backup process.

### Training and Awareness

Establishing and maintaining a program to deliver security awareness, education, and training is vital, because users can be both a critical line of defense against attacks as well as a high-value target of attacks.
Designing this program is a topic covered in more detail in Chapter 1.

To test and evaluate the effectiveness of security training and awareness programs, the following metrics can be useful:
* **Training completion rates:** Users who do not complete training may be more liable to miss indications like a phishing email or unexpected system behavior.
* **Long-term information retention and habit building:** If users take a training, complete a quiz, and immediately forget the information, the program is ineffective.
* **Coverage:** Threats and risks are constantly evolving; training programs must be updated to address these.
* **Audience needs:** Some security practices are too technical or might be unimportant for all users, so it is important to deliver an appropriate level of knowledge and training material to the audience.

### Disaster Recovery and Business Continuity

Business continuity and disaster recover (BCDR) topics, including strategies for gathering requirements, designing a plan to address them, and testing the plan, are discussed in Chapter 1 and Chapter 7.
The output of the requirements gathering and testing processes are important sources to monitor and measure for effectiveness, as the BCDR activities support the goal of maintaining availability.

The information gathered when auditing, assessing, and monitoring BCDR activities should provide answers to the following questions.
Insufficient or negative answers indicate weaknesses that might be addressed by updating the plan documents or iterating processes like business impact analysis (BIA) or plan exercises.

* Do appropriate plan documents exist, and are they updated? Examples include a BCDR plan, continuity of operations plan (COOP), or individual BC and DR plans.
* Are key personnel aware of their roles and responsibilities under the plan?
* Are new staff trained on key BCDR roles as part of onboarding? This can be a shared metric between security training and BCDR data collection.
* Is the current version of the plan readily accessible and securely stored?
* Are the organization’s current critical functions captured in the plans?
* Have significant organizational changes occurred that are not reflected in the plan? Examples include major IT architecture changes and business activity like mergers, acquisitions, divestitures, or restructuring.
* Is the plan tested regularly, and have any deficiencies noted during testing been addressed?
* Does the organization rely on critical third parties or services? If so, have those dependencies been tested?
* Do other processes like change management integrate with the BCDR plans to ensure organizational changes are properly reflected in planning documents?

