# Security Operations

## UNDERSTAND AND COMPLY WITH INVESTIGATIONS

Investigations, evidence collection/handling, and digital forensics requires highly specialized skills.
It is similar to healthcare — you may be qualified to eat a balanced diet and take exercise without guidance from a professional, but if you need major surgery, a professional surgeon is required.
Some security practitioners will specialize in **digital forensics and incident response (DFIR)** and hold credentials in these areas.
For many CISSP credential holders, the process of supporting investigations and forensics will require coordination with appropriate experts to properly handle an investigation, as there are crucial concerns that require specialized skills and training to prevent corruption or destruction of evidence.

### Evidence Collection and Handling

Evidence is any information that indicates a proposition is true or factual; put more simply, it is information that supports a statement.

For example, a door access control record of Alice entering the building at 10 a.m. and CCTV footage of her accessing a restricted vault at 10:10 a.m. support an assertion that Alice entered a vault but does not necessarily support the assertion that Alice stole sensitive assets from the vault.

There are multiple types of evidence that could be collected while investigating a security incident. The most obvious is digital evidence like log files, recordings, computer files, and computer system components such as memory or hard drives.
Hard-copy materials can be important evidence, too, though massive data sets are rarely printed.
Depending on the type of crime, there may be physical evidence like fingerprints, hair, or DNA to be collected, which is not only outside the scope of most CISSP’s knowledge but entirely outside the scope of digital forensics.
Such an investigation is likely to involve a multidisciplinary team of professionals with law enforcement backgrounds, and the CISSP’s role will be to support and comply with any requests from these professionals.

#### Collecting Digital Evidence

Collecting digital evidence can be particularly challenging due to the unique properties of digital information, and preserving the integrity of any evidence collected must be a primary concern when beginning an incident response.
Digital evidence is often short-lived, like log files that are overwritten after only 24 hours or information in volatile RAM that is lost when the system is powered down.
Cloud services have further confused the issue as they store information outside the organization’s control and may not make digital evidence available.
Virtually all digital information is easily changeable as well unless it has been written to specific media designed to prevent it from being altered.

These factors make digital evidence collection a highly specialized endeavor — the investigator must take no actions that interfere with the integrity of the evidence they collect.
Otherwise, the data cannot be relied upon as evidence to make an accusation, since the accused could raise doubt about the veracity of evidence if it was altered during collection or analysis.

##### Digital Evidence Collection Best Practices

Evidence collection may begin during initial incident response, well before a formal investigation is undertaken, so it is crucial to ensure information collected during the response is handled as if it could become evidence in the future.
To achieve this, IR processes must be written to include the following best practices:

* **Record and document everything**, including dates, times, and locations of all actions taken, condition(s) of any evidence collected, and relevant personnel involved.

* **Always make copies** of digital evidence and perform an analysis or investigation of the copies wherever possible.
A bit-level copy is preferred, as it makes an exact duplicate of not only the directories and files on a device but also any deleted files, data remnants, and slack space.
This type of copy takes longer and uses more space than a logical backup that only copies directories and files, but it provides more complete evidence.

* **Prevent unwanted changes** by using copies of data, which can be discarded without losing evidence if an unwanted change is made, and using hardware or software to prevent changes to data.
The simple act of plugging in a removable storage device to a modern computer causes data changes, as operating systems perform functions such as search indexing; the data written during these normal operations can irredeemably damage data that may be needed as evidence.
Hardware devices and software known as write blockers should be used to prevent unwanted changes to media.

* **Verify integrity** to prove unwanted changes were not introduced during collection or analysis.
This will usually involve calculating and comparing hash values to prove the data being used for analysis is the same as the data collected and that data is not changed during analysis leading to adulterated results.

* **Be aware of destructive changes** and avoid them at all costs. When something goes wrong, there is a natural inclination to power down a system or quit applications, but this risks destroying essential data stored in volatile memory like RAM or transient data like application caches.
IR procedures should be written to balance the need to prevent further damage with the need to preserve potential evidence; rather than unplugging a compromised system, it is better to isolate it in a network segment where investigation can occur without evidence being destroyed.

#### Handling Digital Evidence

Once digital evidence has been collected, the highest priority is preserving its integrity as it is handled by the investigators, defined as the chain of custody.
The chain of custody does not prove that information has not changed in any way; rather, it proves that the changes made to the evidence were done in a controlled manner that did not interfere with the information’s integrity and authenticity, and therefore, its reliability as evidence.
The mere act of collecting a mobile device and taking it to a lab for forensic analysis is technically a change, but so long as the evidence is in the custody of trained professionals and no changes were made during transport, any information those devices contain can be relied upon.

There are standards for collecting and handling digital evidence. For security practitioners who do not specialize in DFIR, the recommendations from these sources are likely best implemented in IR processes or procedures.

##### ISO/IEC 27037:2012

In the International Organization for Standardization (ISO) 27000 series, there is ISO/IEC 27037:2012, “Information technology – Security techniques – Guidelines for identification, collection, acquisition and preservation of digital evidence,” which provides guidance for collecting and handling evidence from desktop and laptop computers, mobile phones, personal electronic devices (including mobile navigation devices), and computer networks or equipment implementing Transmission Control Protocol / Internet Protocol (TCP/IP) networking.
Although dated 2012, this ISO standard was reviewed in 2018 and remains current.

##### NIST SP 800-86

National Institute of Standards and Technology (NIST) Special Publication 800-86, “Guide to Integrating Forensic Techniques into Incident Response**,”** also provides guidelines and suggestions for incorporating digital evidence collection into IR practices and covers data sources such as files, network traffic, computer apps, and operating systems.
This document was last updated in 2006, and it provides a strategic level of for creating DFIR programs, which in turn require current skills and abilities relevant to the organization’s IT environment.
The NIST Computer Security Resource Center (CSRC) has a number of resources such as projects and publications addressing current forensics concerns like mobile devices, cloud computing, and analysis of advanced persistent threat (APT) activity, which can be found at csrc.nist.gov.

##### Cloud Computing

Cloud computing represents a specific challenge to the field of digital forensics due to the very nature of its operation.
High availability features like global data replication and hosting can make it difficult to determine exactly where a crime or incident occurred, and if the incident occurred in a different legal jurisdiction, the options for investigating and collecting evidence may be limited.
When choosing a cloud service model and cloud service provider (CSP), a CISSP must understand and provide input to balance business needs such as cost savings, operational functionality, and security capabilities such as digital forensics support.

### Reporting and Documentation

Evidence, just like other data, will have important metadata crucial to its reliability. Details like who collected it, when, and what steps they used must be documented, though the level of metadata required will depend on the type of investigation being conducted.
An internal administrative investigation requires evidence but not highly rigorous handling procedures, while information presented to a court will require thorough documentation and confirmed metadata to support the chain of custody.

Documentation should be created throughout the life of evidence, starting with initial detection of an incident, any investigation steps undertaken, information discovered during investigation, and all actions taken on the evidence.
This documentation should allow for definitive determination of the time and person performing the actions, similar to the principle of accountability in access control.

Any fans of crime investigation TV shows will be familiar — when an interview starts, the detectives state their names and the time on the recording to allow for identification, and any evidence found is bagged and tagged to preserve it and record the conditions of its collection.

Investigation tools like ticketing systems and checklists should be designed to automatically capture this information or ensure the investigator properly documents it.

Reports of investigations and evidence should contain enough information to relate the details of events without the need for subjective interpretation.
The information collected should be presented clearly and accompanied by all relevant metadata as required by the intended audience, such as a chain of custody required by a court.

#### 
Evidence being presented to a court is required to meet the most rigorous standards. Evidence deemed inadmissible that leads investigators to subsequent evidence can cause all the evidence to be useless.
In general, all evidence should adhere to the following principles:

* **Accuracy:** Evidence and documentation must not contain errors, be in conflict with other evidence, or lack integrity. Since evidence is relied upon to prove a case, any inaccuracies weaken that ability.

* **Authenticity:** Authentic information or evidence is of undisputed origin, which is proven by the chain of custody. Inauthentic information runs the risk of, at best, demonstrating incompetence and, at worst, calling the presenter’s credibility into question.
Information that is falsified or adulterated should never be used. Excluding contrary information is also problematic and is not considered a good practice.

* **Comprehensibility:** This is a tricky subject, as digital information often requires specific technical knowledge to understand.
Lawyers and judges in court or business professionals reviewing a case in a non-courtroom proceeding may lack the ability to interpret complex technical topics such as malware forensics or network traffic analysis.
Expert witnesses can be a useful resource for translating or interpreting tech-speak into friendlier language.

* **Convincing:** A user logging in to a restricted workstation is not, by itself, sufficiently convincing evidence that a financial crime was committed.
Presenting the user’s actions along with evidence that they received large, unexpected bank payments is more convincing when telling a story of a particular user committing fraud.

* **Objective:** Evidence must stand on its own in support of an argument or assertion. Audit logs showing user activity are objective, while a security practitioner who “has a hunch” that a user has dubious morals is a subjective statement and does not definitively prove a case.

* **Admissible:** This applies mostly to evidence submitted to a court in civil or criminal trials. Evidence is admissible if it meets requirements set by the court to be introduced in support of a legal argument.
For example, direct evidence like digital forensic examination is typically admissible, while hearsay such as “Sanjay heard a rumor that Lupita shared her password with a member of her team” is not.

Security practitioners are unlikely to be evidentiary experts, so it is crucial to seek advice from legal counsel, law enforcement, or other investigative professionals to ensure evidence you collect, handle, and prepare is adequate.

### Investigative Techniques

The “examine, interview, and test” audit techniques discussed in Chapter 6, “Security Assessment and Testing,” are similar to the techniques used to investigate security incidents and crimes.
The fundamental idea is the same — gather and examine evidence to support a conclusion. In the case of investigations, there are some unique concerns, however, such as legal rights of a suspect when being questioned or investigated.

A CISSP may be called upon to support or handle tasks in an investigation and, as with all evidence handling, should follow the guidance and advice of professionals.

These are the four main investigative techniques a security practitioner should be familiar with:

* **Data capture** includes gathering data such as audit logs or network traffic, as well as specialized techniques such as gathering photographic or video evidence of an incident scene and the associated investigation.
Automated capture is done using traditional monitoring tools and may leverage the organization’s continuous monitoring infrastructure like a security information and event management (SIEM) tool or recorded camera footage.
Manual capture refers to techniques employed by forensic investigators like making copies of data and media and recording the scene of an incident or crime by photos or video.

* **Interviews** are a tool designed to solicit information from individuals, typically witnesses or those with knowledge of an incident.
Interviews follow a question-and-answer format where the investigator is asking questions designed to elicit information and recording the answers, though interviewees may also give a statement.
In general, interviews should be recorded, if permitted by local law and if appropriate permission from the interviewee has been documented.
Multiparty interviews are also encouraged to provide greater reliability of information, whether by having multiple interviewers or an interviewee advocate present who can attest to the accuracy of information gathered.
Interviewees typically have legal rights such as the ability to refuse or terminate an interview, and security practitioners must be careful to abide by all laws — a private citizen (like a CISSP) holding someone against their will without cause is illegal in most places!

* **Interrogations** carry more stringent requirements than interviews and are generally carried out by law enforcement professionals. An interrogation is conducted against an individual suspected of a crime and often takes place after that individual has been arrested.
There are specific legal rights assigned to suspects that, if not observed, can render information gathered in the interrogation inadmissible.

* **External requests** can be made by investigators to gather information from third parties such as an internet service provider (ISP), government agency, or formal request for information from a specific party.
These often require legal approvals and processes like warrants and subpoenas, so security practitioners may only be tangentially involved with originating them in an investigation.
However, a CISSP may be subject to these processes if called upon to provide evidence. In these cases, guidance from appropriate legal counsel is key, either from a personal attorney or from corporate counsel.

### Digital Forensics Tools, Tactics, and Procedures

Properly trained professionals are required to perform forensics tasks and must, of course, be given access to appropriate tools and resources.
Organizations must decide if the analysts and investigators will be internal employees or contractors or will be external vendors that are called upon only when needed.
The cost of retaining the needed talent and resources in-house must be weighed against the benefit of quicker response times and more customized procedures and should consider the frequency of incidents that require formal investigation.

An investigation and forensic team should include people with diverse skills and experience across computer networking protocols, security tools and platforms, system administrators, and the practices of threat and vulnerability management.
Any investigation requiring forensic expertise is likely to be a critical priority for the organization, so forensic team members should be granted the ability to approach any member of the organization and expect cooperation, even if it interrupts the member’s routine tasks.
In some cases, organization members may be temporarily reassigned to support the investigation, similar to incident response teams.

#### Tools

There are physical forensic tools used by digital forensics experts, even though they are mainly interested in and deal with digital or electronic information.
Forensics work requires tracking and case management software and equipment, workstations, and workspaces that are isolated and dedicated to forensics to prevent contamination of evidence under investigation.

Additional tools include the following:

* **Write blockers** and drive imagers designed to allow examination or imaging of a storage device, typically a hard drive, without writing any data to the storage device, which would violate the integrity of the evidence.
 
* **Faraday containers** like bags or boxes, which are shielded to prevent radio communications to or from a physical device.
These are especially useful when digital evidence exists on portable devices like smartphones, tablets, or even laptops, since these devices can send and receive commands using wireless protocols like Bluetooth, WiFi, or cellular connections.
This can unintentionally alter data, such as an app update being installed that overwrites critical evidence, or the device can be tampered with to destroy evidence by remotely locking or wiping it.

* **Video and audio recording** tools can be used to document evidence of a crime or incident and can also serve to document the investigation team’s activities to support the integrity of any evidence.
Rather than taking extra time to document the steps taken when performing forensic analysis, the analyst can simply record a video or audio log of their work.

Once all physical evidence has been collected, it must be analyzed, and there are a variety of software tools available to the forensic investigator.
These can be categorized based on their intended use or area of specialization:

* **Network traffic analysis** tools like Wireshark can be used for both network packet capture (pcap) and network traffic analysis, by reconstructing the communication sessions.
With the rise of software-defined networks (SDNs) and virtualized cloud infrastructure, these software tools may replace physical network forensic tools like using a SPAN port to capture traffic; some of this capture and analysis may be performed proactively by tools like security orchestration, automation, and response (SOAR) or security information and event management (SIEM), as part of the organization’s continuous monitoring strategy.

* **Log analysis tools** like SIEM tools are often useful to investigators as a way to reconstruct the series of events that led up to an incident.
Less mature organizations may not have SIEM tools in place, in which case, logs can be manually collected and imported into a SIEM tool for analysis.

* **Data recovery tools** assist investigators in recovering files and information that have been deleted or overwritten.
Most operating systems do not delete the actual data when a user deletes a file, but merely update an allocation table that tracks where files are stored on a disk and where free space exists.
Deleted file contents still exist, but there is nothing preventing a new file from being written there if requested; if no new file has been written, it is easy to recover the information by reading the information on each sector of the drive.
Depending on the type of media, it may even be possible to use highly specialized physical equipment to reconstruct data after a disk has been overwritten.

* **Virtual machines (VMs)** are not specifically a forensics tool, but they are useful for investigative purposes. Suspected malware can be copied to and run on a VM that is isolated from all other systems, which allows it to be observed and investigated without threat of infecting other systems.
Such virtual lab or testing environments can be set up and torn down much easier than their physical counterparts.

* **Code analysis tools** include decompilers designed to reverse-engineer software, as well as binary analysis tools designed to observe the functioning of a program at the source-code level.

* **Hashing** tools are essential to investigators, not because they provide any insight into the data being analyzed, but due to their essential role in proving the continued integrity of data that is collected and analyzed.
Hash values and message digests are useful to prove that data like an app or email has not been changed in transit, and hashing can also be used to prove the data was not altered by the investigator.
This proves the data can be relied upon in support of any assertions or accusations made.

* **Toolkits** are suites of software that provide common tools for a specific purpose like forensic investigation, and there are many forensics toolkits that are made by commercial vendors, open-source projects, or even composed of tools chosen by a particular forensic expert to support their work.
These toolkits combine multiple resources that are useful to forensic investigators, including system-specific analysis software like Windows Registry analyzers, data recovery and reconstruction apps, and tools discussed earlier like network traffic analyzers and software write blockers.

#### Techniques and Procedures

It is important to be prepared with training on forensics techniques and easily followed procedures, even with trained professionals conducting forensics and investigating an incident.
The situation during an incident is frequently stressful and time sensitive in nature, so preparation and job aids will prove useful.

The first step is to define the process and procedure to be used during an incident, which is the realm of the IR plan.
Many investigations begin as a response to an incident; details gathered during the response may require forensic analysis later if the cause of the incident is found to be a crime or other serious matter.

##### Standards and Resources

Documented standards for the collection, handling, and investigation of digital evidence include ISO 27041, 27042, 27043, and 27050.

SANS also provides a number of useful resources to aid investigators and responders, including cheat sheets, quick-start guides, and posters for common tasks like malware analysis using Linux or malicious document analysis.
These can be found at digital-forensics.sans.org/community/cheat-sheets.

NIST also provides resources for forensic investigators, focused on ensuring the quality of software forensic tools and on developing skills and training programs for investigators.
These resources can be found at the NIST Computer Forensics Tool Testing Program (CFTT) site: nist.gov/itl/ssd/software-quality-group/computer-forensics-tool-testing-program-cftt.

##### Forensic Analysis Procedure Steps

A generic set of procedural steps for conducting a forensic analysis is presented here. These may be initiated proactively to investigate a suspected incident or be invoked by escalating an incident response for further investigation when the evidence points to a serious security issue.

* **Define priorities:**
There are three possible priorities an organization might pursue when responding to an incident — return as quickly as possible to normal operations, minimize damage, or preserve the greatest amount of detail regarding the incident.
Returning to normal operations by wiping and reimaging machines gets things running again quickly, but vital data is lost. Taking a system offline completely to conduct an investigation can cause business operations to cease completely or require expensive duplicate equipment purchases.
The organization must ascertain the requirements of each situation and choose an appropriate set of actions.

* **Identify data sources:**
All incidents require the discovery of relevant information, and certain actions will need to be taken in a timely manner based on the sources identified.
Some log data, for example, is short-lived and must be captured before it is written over, and some memory may be frequently overwritten or volatile, meaning data stored there is available to be collected for only a short time.
Some data may already be captured and stored long-term as part of continuous monitoring, making it easier to access. All data sources must be quickly identified and prioritized for collection.

* **Plan to collect data and execute:**
Once data sources have been identified, a plan must be made and acted upon to collect the needed information.
This plan should prioritize ephemeral data like temp files that are designed to be overwritten, as well as volatile memory storage like RAM that disappears when the machine is powered down.
Executing data collection involves the use of investigative techniques discussed earlier and may require formal processes such as getting search warrants or subpoenas issued.
Tools used in this step will vary based on the information source, such as specific programs needed for data recovery on different operating systems and physical collection and storage tools for different types of media.

* **Document and preserve integrity:**
Data collection is the first link in the chain of custody, so documentation of the work done is essential. Details including the time a piece of evidence was collected and any handling it was subject to must be documented.
In some cases, the evidence itself will already contain needed metadata, such as read-only log files in a SIEM tool that should contain date and timestamp information.
In other cases, the integrity metadata must be calculated as part of the process, such as calculating hash values for files as they are collected to prove the evidence analyzed has not been changed since it was collected.

* **Look for hidden or erased data:**
Vital information needed for the investigation may have been deleted, overwritten, or exist in hidden directories.
In some cases, an attacker or malicious software will deliberately delete or obfuscate data to confuse the investigation, and in others, the data may have been deleted or overwritten during routine system operations or innocent user behavior.
Unless extraordinary means like overwriting or cryptoshredding are employed, deleted data may be recoverable with hardware or software tools.

* **Perform analysis:**
Once collected, forensic investigation of the data is performed. This may entail simple tasks such as reviewing documents, files, and communications for suspicious user activity, or more complex tasks such as network traffic analysis to determine how a piece of malware spread throughout a network.
It may even require highly advanced tasks such as reverse-engineering malware to investigate the incident. Determining a timeline or sequence of events is also critical.

### Artifacts

Locard’s exchange principle is a guiding idea in forensics and is named for a forensic scientist and criminologist who observed that a criminal will both introduce traces of their presence at a crime scene and remove something and that both can be used as forensic evidence.
In the investigation of physical crimes, this is known as trace evidence like hair, fibers, and DNA. In computer crime, digital forensics often focus on artifacts, which are digital traces left behind when a user or program interacts with a device.
Searching for these is one of the main goals of digital forensics, as these traces of activity tell the story of an incident and are vital in supporting any accusation or case made.

Given the specialized nature of digital forensics, there are advanced requirements for training and certification in the field.
Many government organizations with law enforcement missions and dedicated DFIR providers have internal training and skills development programs that cover what artifacts to look for and how to recover them.

#### Computer

In almost all circumstances, using a computer will leave traces of the activities performed, and actions like installing programs or executing specific commands will leave evidence useful to an investigator.
Log files will be created as system events like logins occur, system configuration files like the Windows Registry or Unix .plist files will be updated, and files will be written, altered, and deleted.
Some information regarding an incident may be compiled by existing tools like endpoint detection and response (EDR) or host-based intrusion detection system (HIDS) agents, while other information will require manual investigation.

The following list highlights a few common sources of artifacts across three major computing platforms. It is not exhaustive, and just like system administrators, it is often the case that forensic investigators will specialize in one of these platforms.

* **Windows:**
Windows systems maintain a log that can be accessed using the Event Viewer, and they contain entries for vital system, application, and security events.
Deleted files may be in the Recycle Bin if a user or malicious program has not taken extra steps, and hidden metadata or deleted-but-recoverable files may also be found.
The Windows Registry is also a useful source of information, as it contains records of configuration changes and software installed.

* **macOS:**
The Mac equivalents of the Windows Event Viewer and Recycle Bin are called the Console and Trash, respectively, and their investigation follows many of the same procedures.
Some macOS-specific technologies can also prove useful investigation points such as the automatically generated Time Machine backup system, Spotlight indexing and systemwide search function, and configuration files known as property list (PLIST) files.

* **Linux:**
Unlike desktop versions of Windows and macOS, many Linux systems are designed to be run solely using a command-line interface (CLI).
Native graphical tools for accessing artifacts may not exist, so third-party toolkits are required, or the investigator must be familiar with the standard filesystem to find relevant data.
Examples include the /usr folder where user files are stored, /tmp for temporary files (a vital source of volatile data, as most Linux systems will delete the data in this directory upon reboot), and /var where frequently changed files are stored including caches, log files, and information about currently running processes.

* **Browsers:**
A user’s browsing history contains enough data that it’s now a common joke for an individual to be charged with the duty of deleting a person’s browsing history upon their passing.
However, if the root cause of a malware infection is the user visiting a particular website, records of activity like sites visited, cookies placed, and any data stored locally by websites could be informative.

* **Local storage:**
Physical investigations often involve a look through physical storage like file cabinets, and digital forensics should perform the digital equivalent by browsing local filesystems or removable media.
Perhaps a criminal maintained some log of their activity that supports the investigation, or metadata exists that can prove certain actions like deletion of key files.

* **Cloud storage:**
Because of the lack of physical control over cloud systems, artifacts may require the investigator to follow legal procedures like getting warrants issued.
The wide variety of cloud services means forensic investigation may be against a VM that is similar to investigating a physical computer or may target entirely novel tools like microservices where standard forensic artifacts aren’t even available.

#### Network

Data in transit is an ephemeral state; that is to say, data moves across communication networks but does not get stored there.
However, metadata about these communications is essential to investigating incidents, and in many cases, stored data or actors in an incident can be identified or tracked using the communication metadata.

The following are some sources for network artifacts:

* **NetFlow** analysis provides a picture of the Internet Protocol (IP) traffic flow and volume across a network device, typically a switch.
It can be used to identify details of the communication such as ports, protocols, and addresses being used for communication.

* **Packet analysis** (often known as pcap) is useful as it captures both details about communications and the data itself.
Packet sniffer tools can capture packets in transit across a network and reconstruct data being sent or received, which can be further analyzed.

* **Known bad traffic** can be used to identify suspicious or unwanted activity, such as a server sending data to known spam domains or communicating with known malware servers like command and control (C2) or botnets.

* **Network device log files** can contain a wealth of useful information if they have been configured to store it.
Devices like switches and routers contain details of traffic passing the network, and security-focused tools like proxies or Virtual Private Network (VPN) concentrators are a useful source of artifacts relevant to a security incident.

#### Mobile Devices

##### Encryption

Forensic investigation of smartphones running Apple’s iOS and Google’s Android have been in the news frequently after major criminal cases due to encryption making forensics difficult or impossible.
Strong encryption is often implemented by default on these devices due to their highly portable nature and wealth of sensitive private information.
This makes it difficult or impossible to conduct forensics if investigators do not have the information needed to unlock the device and decrypt its data.

##### Data Sources

The fact that software designed for these devices often assumes internet connectivity is also a potential issue — smartphone apps may not store data locally, instead accessing data from the cloud.
In this case, forensics will require identifying all the sources of data and executing appropriate search techniques like gathering physical device evidence and issuing warrants for cloud-hosted data.

##### Mobile Device Artifacts

Gathering artifacts from mobile devices will follow many of the same procedures previous discussed. iOS is a variant of the macOS, and Android is a Linux-based system, so the process of gathering artifacts may be similar but utilize special tools.
The largely consumer-focused nature of these devices may also prove a boon to investigators, as poorly coded apps or those with limited functionality may prevent users from thoroughly removing data.
The always-on connectivity in these devices usually includes cellular, WiFi, Bluetooth, and near-field communication (NFC) standards, so network forensics will be similar to other devices, just with more network interfaces and tools for the specific protocols.

##### Remote Locking and Wiping

One unique situation posed by mobile devices’ constant connectivity is the ability for data to be lost or destroyed.
Services like Apple’s Find My and Google’s Find My Device allow a lost or stolen phone to be remotely locked or wiped, which destroys vital evidence.
Mobile device management (MDM) can be useful if the organization can prevent these actions from being carried out on a device that might contain evidence.
In these cases, special handling is required for the physical devices, including placing them inside a Faraday bag and analyzing them in a properly shielded room, to prevent cellular, WiFi, etc., signals from reaching the devices.


## CONDUCT LOGGING AND MONITORING ACTIVITIES

Logging and monitoring can be somewhat confusing because logging involves proactive safeguarding measures as well as reactive countermeasures. Defining a logging strategy is proactive, including what events to capture, where to store the data, and mandatory review or monitoring activities.
The occurrence of events and their recording in a log is, obviously, a reactive activity, and performing analysis or review of logs to determine what happened is inherently an after-the-fact activity.
Defining a log strategy, choosing effective tools to implement it, and performing active monitoring or reviews based on the data logged are essential elements of security risk management.

### Intrusion Detection and Prevention

Intrusion detection systems (IDSs) and intrusion prevention systems (IPSs) are narrowly defined categories of security tools, though in practice, they often have overlapping capabilities.
Both are designed to detect signs of intrusion, but IDS stops at the point of detection and generating an alert, while IPS goes a step further to mitigate the intrusion activity.
Once an intrusion is detected, IPS can take a variety of actions like implementing a firewall rule to block malicious traffic, restoring files to a pre-compromised state, or even shutting down an application, service, or server to prevent further intrusion.

IDS and IPS can be deployed in either network-based (NIDS and NIPS) or host-based (HIDS and HIPS) variants.

#### Network-Based IDS and IPS

Network-based systems are often dedicated appliances that scan all network traffic to look for signs of attack.
They should be placed at crucial chokepoints of a network to monitor vital traffic flows, such as the connection between the demilitarized zone (DMZ) and internal networks or between a VPN terminator and an internal network.
NIDS and NIPS can be integrated with other security devices such as firewalls and proxies, which are also deployed at the same network points, and IPS especially benefits from this integration because it allows the monitoring and response action to be integrated into a single device; for example, a proxy that can terminate a NIPS-identified malicious connection.

#### Host-Based IDS and IPS

Host-based systems are designed to be deployed on a specific network endpoint like a server or a workstation, typically in the form of a software agent.
HIDS and HIPS monitor host-specific network traffic, leverage signals from other tools such as anti-malware to detect attacks, or hash critical system or application files to detect unexpected changes.
The emerging field of EDR combines functions like anti-malware, configuration management, and HIDS/HIPS into a single software agent.

### Security Information and Event Management

The volume of log data in even a small IT environment may quickly become overwhelming — a single user workstation can generate hundreds or thousands of log entries per day.
SIEM is a composite of several tools and capabilities like log centralization, log data integrity protection, and analysis to generate actionable intelligence from the data stored in logs.

SIEM is a loosely defined term for a broad category of tools that different vendors may implement differently.
However, most SIEM tools provide a specific set of services related to centralizing and managing log data, as well as extracting useful information from log entries to identify potential incidents.
These include the following:

* **Centralization:**
Individual systems generate their own log files, and without pulling them together into a central repository, the task of searching logs would be immense.
Performing analysis across such a large environment is prohibitive, so centralizing log files is crucial. SIEM tools can use standard abilities on endpoints, often referred to as forwarding, to send a copy of their log file data to a central location.
Endpoints that do not support log forwarding can be equipped with software agents to harvest and forward the logs. Data should be captured from devices including servers, user workstations, network equipment, cloud services, applications, and security tools like firewalls.

  Centralizing can also enforce a key access control for log data: users with credentials to monitored systems may be able to delete or change logs on those systems, but can be easily denied permission to the SIEM tool.

* **Normalization:**
Log files generated by a Windows system will have data that is similar to but not exactly the same as files generated by a Linux system.
Examples include numeric user IDs versus usernames, or timestamps in different formats like YYYY-MM-DD versus DD-MM-YY, and these differences can make it difficult to search and correlate traffic across systems.
Normalization happens when logs are forwarded to the SIEM — data is converted into a standardized format or standard labels are applied for consistency.

* **Correlation and detection:**
Once centralized and normalized, data can be processed to correlate activity across systems and detect potentially suspicious actions.
A user may log in to their workstation and interact with company applications around the same time each day, generating log events on a workstation, a directory server, and applications.
The same user logging in remotely, at a different time of day, and downloading large volumes of data from applications can easily be detected as an anomaly.

  * _Correlation_ refers to discovering relationships between data; in the previous example, the logins from a unique location at a different time deviate from the norm.
    This deviation is a correlation of the users’ normal or expected behavior and allows for detection of potentially suspicious events, like a user’s account being compromised and used to exfiltrate data.

  * More advanced SIEM tools offer integrations to perform fine-grained detection.
    For example, an integration with a travel system could be used to determine if the employee has a documented work trip scheduled, which lowers the probability that the logins during odd hours or from a new location are malicious.
    Other sources of external information can also be correlated, such as data from external threat intelligence feeds or status information from a CSP to associate application downtime with known cloud service outages.
    Adding context to data via such external sources is known as _enrichment_.

* Alerting: Once data has been centralized, normalized, and analyzed, the SIEM’s final value comes in the form of alerts being generated.
The speed and continuous monitoring ability of a SIEM tool frees human resources, such as security operations center (SOC) analysts, from the tedious tasks of combing through data.
Instead, tickets or other tasks can be generated by the SIEM for analysts to investigate, which is a better use of critical thinking and analysis skills.
The tickets or work tracking should capture details of these investigations including assigned analyst, steps taken, and any artifacts that lead to the ticket or were captured during investigation.

### Continuous Monitoring

Security control assessments were heavily focused on formal, point-in-time processes like audits or certification and accreditation well into the early 2000s.
Popular frameworks like ISO 27001 and the U.S. government’s Federal Information Security Management Act (FISMA) were on three-year audit cycles; as a result, many security programs performed monitoring activities only once every three years as the organization prepared for or underwent audit.

The rapidly evolving threat landscape drove the need for more frequent assurance, and thus the practice of continuous monitoring was created.

Continuous monitoring, as the name implies, requires a more frequent set of checks to determine if security controls are in place and operating effectively to mitigate risk.
The goal is more timely information should a control fail or be rendered ineffective by changing technology or threats, which allows the organization to respond more quickly.
Continuous monitoring requires the use of automation and focuses heavily on metrics to provide data about controls and indicate needed changes.

When designing a continuous monitoring strategy, it is important to address several key concerns.
This begins with policy and executive support and should enable the organization to document a strategy for designing and operating the continuous monitoring program.

Aspects to consider in this strategy include the following:

* **Defined reference point:**
Effective monitoring requires a baseline set of measures for ongoing comparison. This may be a compliance framework like PCI-DSS, ISO 27001, or NIST SP 800-53.
System baselines may also be useful for the purpose of monitoring information system components like servers and applications and may be organization-specific baselines or public references like the CIS Benchmarks.
Many frameworks and baselines will also contain prioritization information to guide the implementation of continuous monitoring.
Higher-priority controls are selected first for implementation and targeted with more frequent or intense monitoring.
Lower-priority controls may be assessed less frequently.

* **Automation:**
Auditing an information system of even moderate complexity is a significant undertaking, and performing even a subset of those activities on a regular basis is no small task.
Automated checks are critical and begin with identifying data sources necessary to enable this automation.
Log files or system information that can be read and analyzed programmatically is a common starting point, and information in a SIEM tool is also useful to enable near real-time analysis of events to detect unexpected behavior.
Tools designed to support automated security monitoring are becoming prevalent, such as EDR and user entity behavior analytics (UEBA) agents, both of which automatically scan a network endpoint for suspicious activity that violates policy or threats that have evaded detection mechanisms.

* **Frequency:**
Continuous monitoring should ideally move from static audits to more frequent checking, but that does not mean controls will be assessed all the time.
Determining a control evaluation cadence should be driven by the priority of the control as well as the cost of evaluating, both in terms of financial costs associated with the monitoring solution and any operational impacts like reduced system capacity.

* **Appropriate metrics:**
There are any number of interesting numbers to monitor in an IT environment, but the metrics defined for a continuous monitoring program should provide actionable intelligence about the effectiveness of the controls.
In addition, interpreting metrics must be done carefully. The number of bugs found per year in a given system can be useful to track, but it is to be expected that software will contain bugs, and that number does not provide meaningful insight into the effectiveness of vulnerability management.
Tracking the patch deployment window is a more meaningful measure of how effectively the organization is handling risk presented by software flaws.
Metrics should support clear decision-making when variances are detected.

* **Defined action plans:**
Metrics are useless without context and action plans. A car’s dashboard shows important information like fuel level, which a driver (hopefully) understands — a full tank means keep driving, and a tank nearing empty means it’s time to stop and refuel.
Metrics from the continuous monitoring program should provide similar calls to action, so it is critical to define acceptable ranges and action plans to address variances.
If a configuration management tool indicates a patch deployment level below 75 percent two weeks after a patch is available, forced restarts to patch may be an appropriate next step.

* **Balance cost and value:**
Monitoring control effectiveness can actually increase the value of the controls — if a risk mitigation becomes ineffective but the organization keeps paying for it, that money is wasted.
If the change is detected and remedial action taken, the control continues to deliver value.
Balancing the cost of the continuous monitoring program with the value received is less a technical activity than a business activity, but it is important for security practitioners to understand and communicate this value effectively.

Guidance for continuous monitoring systems can be found in NIST SP 800-37, with a special emphasis on implementing the practices within the NIST Risk Management Framework (RMF) and utilizing the SP 800-53 control framework and SP 800-53A assessment methods (csrc.nist.gov/publications/detail/sp/800-137/final).

Another U.S. government initiative that is freely available is the U.S. Cybersecurity & Infrastructure Agency (CISA) Continuous Diagnostics and Mitigation (CDM) program (us-cert.cisa.gov/cdm/home).

ISO 27004, “Security techniques – Information security management – Monitoring, measurement, analysis and evaluation,” also provides a framework for designing and executing oversight and monitoring of security control effectiveness.

### Egress Monitoring

When attackers gain access to a network, it is often with the goal of stealing sensitive information stored or processed on that network.
This is known as exfiltration, and it relies on sending information using standard ports, protocols, and services like email, FTP, or HTTP.
In many cases, this is done without an attempt at hiding the activity, but instead disguising it inside a high-volume data source like HTTP traffic.
Because of the amount of web and other traffic using port 80, it may be difficult for organizations to monitor the traffic closely.

An exit point is known as an egress; in network terms, these can be web, FTP, or email servers, while in physical form, an egress point could be a door, loading dock, or garbage container where hardware like laptops, removable media, or even hard-copy material can be removed.
Egress monitoring, therefore, comprises monitoring and restricting what data and storage devices can leave controlled environments.

#### Data Loss Prevention (DLP)

Data loss or data leakage prevention (DLP) is one tool for managing electronic data leaving a network, and these tools can recognize information using common patterns or signatures like four groups of four numbers — 1111 1111 1111 1111 — which is commonly a Visa or Mastercard credit card number.
DLP tools can be trained to recognize sensitive information specific to an organization.
If your organization uses account numbers or other unique identifiers, the DLP tool can be configured to scan for and identify those in data sets using regular expressions, which are structured search parameters such as CUSTIDnnnnaaa.
In this example, CUSTID is always present, while the n represents a number and a represents letters. Any string of data matching this configuration can be recognized by the DLP.

DLP solutions can perform a number of important functions once they have identified data. Discovery is the process of scanning a network to identify data based on pattern matching, signatures, or data labels, and DLP can be used to find unknown stores of sensitive data stored on a network.
It can also be used to identify sensitive data moving around a network, like when files are copied from a fileshare to a workstation or attached to an email.
Depending on the DLP’s configuration, these actions may simply generate an alert, temporarily block the action and ask the user to confirm they intended to send the file, or block the action altogether.
The choice of DLP action will depend on the sensitivity of the data in question.

#### Ingress Monitoring

In addition to monitoring data leaving the organization’s control, some organizations may implement ingress monitoring to identify what data is entering the network.
Data that should not be handled or stored may be rejected; for example, an email with a spreadsheet containing credit card information may be rejected by an email server.
This prevents the organization from being forced to carry out cleanup and remediation tasks to contain a data breach.

#### Physical Ingress and Egress Monitoring

Physical ingress and egress monitoring may also be appropriate, such as screening physical media entering or exiting the facility to ensure data is not being transmitted on removable media or the like in contravention of organization policies.

### Log Management

Logs are a vital source of information for a number of security operations activities, chiefly continuous monitoring and IR.
Multiple frameworks including ISO 27001 and NIST SP 800-53 define key elements to consider when creating a logging strategy.
In addition, NIST SP 800-92 provides a set of critical requirements for securely managing log data, as well as processes for standardizing and analyzing the information collected (csrc.nist.gov/publications/detail/sp/800-92/final).

#### Define Auditable Events and Thresholds

Defining auditable events and thresholds for logging is a proactive security decision. Determining which events are written into log files and which are not is done before activities occur, and there is a careful balance required.
Log too much and the data can become overwhelming, both in terms of storage space and review effort required. Log too little and the organization won’t be able to effectively reconstruct details of what happened should an incident occur.

Most platforms offer the ability to set auditable event thresholds based on some event information, while custom-built applications should have documented requirements to support logging.
For example, standard informational events like a system status check with no issues noted can be ignored, while changes to vital system configuration files should definitely be logged.
Threat intelligence and risks facing the organization should be used to define auditable events — if the organization is facing increased phishing attempts, then increased logging of unusual account activity is justified.

Other auditable events to consider include the following:

* Successful and unsuccessful access attempts like system logins, file or data access, and application access
* Changes to user permissions, especially escalation like using sudo or other admin privileges
* Changes to or disabling of security tools like DLP
* Copy or export of sensitive files
* Sensitive data transactions performed in applications

Logs must contain sufficient detail to reconstruct the actions that occurred on an information system, including who, what, and when.
This entails capturing sufficient details about the subjects (users or processes), objects (files, applications, etc.), and action (read, write, execute, delete, etc.).

Data points that should be captured to support these requirements typically include the following:

* User or process IDs
* Timestamps, ideally in a standardized format like UTC or in a standardize time zone used by the whole organization
* Device identifier, hostname, IP address, or similar
* Name of object(s) accessed, like filename or function
* Policy identifier that triggered the log event, such as a failed login, admin privilege use, or file deletion

#### Protect Log Data

NIST SP 800-92 lays out requirements for securely managing and protecting log data, with particular emphasis on preserving the confidentiality and integrity of the data.
It includes references to various compliance frameworks that mandate protection of log data, including Payment Card Industry Data Security Standard (PCI DSS), and highlights the critical role of integrity for log data.

Information that is logged could become evidence in a future security incident, so the log collection and protection strategy must be designed to provide a defensible basis for authentic data and an unbroken chain of custody.
Data contained in the logs may be highly sensitive due to internal confidential information (in the case of system information like IP addresses), or even possible protected information like Personally Identifiable Information (PII) in application logs.

##### Integrity

Logs that need to be relied upon in forensics must have an intact chain of custody, so log files are often written to high integrity storage media like write once, read many (WORM) disks, which physically prevent log data from being changed after being written.
Storing log files on segregated systems with different access permissions also supports integrity, and SIEM tools can implement this separation of duties.
System administrators can tamper with log files on the systems they administer, but if the logs are forwarded to a SIEM tool where they have no access, tampering becomes much more difficult.
As log files are written, copied, or forwarded, integrity checks should be performed by hashing the original and storing the hash for later comparison.

##### Confidentiality

Sensitive information may be captured in logs by design, such as system event information, or incidentally, as is often the case with application logs.
An application error may contain unexpected data, such as a user’s form input that caused the error.
An internal data breach is possible if unauthorized users are able to see that information, so protecting logs often requires restricting access to only authorized security personnel.
Once again, SIEM or other tools used by SOC personnel can be provisioned separately from systems where logs are generated, thereby avoiding unauthorized access to the data.

##### Availability

Although integrity and confidentiality are crucial for log data, availability is also of concern.
Log data increases over time as more events are recorded, so adequate capacity planning is required. This includes ensuring the storage space is sufficient and may also involve determining the length of time audit logs are held before they are overwritten.
For local storage on servers, a short period like two weeks may be implemented to conserve space, while on a SIEM tool, the log data may be retained for months, years, or indefinitely.
Log data may be archived using offline, cheaper storage methods, which offer slower access at a reduced cost.

### Threat Intelligence

Risk-based security requires a holistic understanding of risk, comprising vulnerabilities that can be exploited by threats. Security practices like patch management focus on identifying and addressing vulnerabilities reactively.
Threat intelligence is a proactive activity that allows security practitioners to identify threats and threat actors targeting their organization.

For example, threat intelligence may aid in identifying a system compromised by latent malware, which threat actors have access to but have not yet used.
In this case, a larger, potentially more serious breach can be prevented by isolating the infected endpoint and removing the malware.

#### Threat Feeds

Sources of information that can be used for threat intelligence vary based on your organization’s industry, region, and level of technical sophistication.
Organizations with high technical skills and a large staff of security practitioners may have the skills and resources to do their own threat hunting and generate relevant information.

However, there are threat intel vendors that create data feeds of relevant information by performing threat hunting and research and that provide the data in an easily consumable feed.
These feeds range from routine emails or other alerts to a data feed accessible via an application programming interface (API), which can be integrated with SIEM and SOAR tools.
A SIEM integration may generate alerts, while a SOAR can proactively respond with actions such as deploying patches, instituting new firewall rules, or even isolating affected systems.

In addition to threat intel vendors, there are freely available sources. In many countries, government agencies tasked with cybersecurity roles will send notifications, such as CISA in the United States and the Canadian Centre for Cyber Security.
Industry-specific groups known as information sharing and analysis centers (ISACs) also offer threat information to their members.
Due to their focus on a particular industry, ISACs can offer more targeted information, and membership typically requires an organization to be either directly in or in some way related to the particular industry.
ISACs exist for a variety of industries including retail and hospitality, financial services, municipal governments, and healthcare.

### Threat Hunting

Threat hunters, as the name implies, are the human analysts or software agents looking for threat data. This data, when combined with useful information on how to counter the threat, comprise threat intel that can be used to take specific action.

Threat hunters can look for threats at a variety of levels in the organization:

* **Strategic** threats to an organization are high-level issues like the need for a chief information security officer (CISO) to guide an organization’s security program, or a requirement for better phishing training in an industry that is particularly hard hit by such attacks.

* **Tactical** details generated by threat hunters are commonly known as indicators of compromise (IoCs), which are gathered during forensic analysis of a security incident.
These details can be used for detecting the particular threat targeting other systems, much the same way malware signatures are used to update anti-malware tools to spot known virus files.

* **Operational** threat hunting seeks to understand the tools, techniques, and procedures (TTPs) of attackers, which in some cases can be quite technical and in other cases may be as simple as “financial services firms are facing increased denial-of-service attacks from a particular country.”

Threat hunting is often done as part of security research outside of any particular organization, and the community of researchers generally share their work and findings in the spirit of making everyone more secure.
As a result, threat details are often shared in social forums like blogs, in conference talks, and on Twitter, while relevant information like IoCs is integrated with security tools including SOAR, SIEM, and penetration testing toolkits.
Industry-specific feeds of threat intelligence generated by threat hunting activities can be found in respective industry-specific ISACs.

#### Deep Web and Dark Web

Some work done by threat hunters relies on searching the deep web or dark web, both of which require a specific set of technical knowledge and skill to access.

The deep web comprises content that is accessible over the internet but not publicly exposed, such as online banking information, private social media feeds, and even content behind paywalls like news sites.

The dark web, by contrast, exists on nonpublically accessible networks that require the use of special access methods like the Tor network.
The skills and complexity of access are what make threat intel feeds a valuable tool, as the cost to acquire talent with this knowledge is prohibitive for many organizations.

### User and Entity Behavior Analytics

Although it has a complicated name, UEBA is a relatively straightforward security function. Entities are nonhuman actors on a network including hardware like routers and servers and software processes, threads, or daemons.
Users are human users who log into and interact with information systems. UEBA combines machine learning and statistical analysis models to analyze and define a baseline of normal or expected behavior by users and entities interacting with information systems.
Any activity that deviates from this anticipated baseline is flagged as suspicious and can be used as an input to other security tools.

Consider Alice, who logs into her workstation each day around 10 a.m. and typically downloads between 10–100 MB of data each day from the internal finance system.
Next Monday, Alice’s workstation begins downloading hundreds of gigabytes of data from highly sensitive systems that belong to the legal department and the research and development department, and it sends gigabytes of data to an external IP address.
This is obviously a suspicious situation, but one that traditional security tools might miss due to a lack of targeted monitoring focused on Alice and her workstation.

UEBA allows for targeted and individualized security baselines to be developed based on individual users or entities.
Alice’s previous activity indicates that uploading large amounts of data to external sources is unusual — this could indicate her job function has changed, that her workstation has been infected with malware, or that she has begun selling company information to a competitor.
If Bob works in the manufacturing department, he may routinely exchange large design files with manufacturing partners outside the company, so a security tool that blocks all large data transfers will be obviously problematic.
UEBA provides more granular enforcement and the ability to adapt to unique user and organization requirements.

The output of UEBA monitoring can be a useful input to other security tools like a SOAR or IPS.
An alert of suspicious activity on a server could trigger a network quarantine of the affected machine by placing it on an isolated virtual LAN (VLAN), or a user’s access credentials could be temporarily suspended if suspicious activity is detected on their workstation.
Alert of suspicious activity can trigger a manual investigation; if the trigger activity was unexpected but legitimate, the blocks can be removed.
If the alert is related to malicious activity, the response limits the damage caused.

This targeted approach allows security tools to achieve a better cost-benefit trade-off by providing adaptability for unique circumstances in each organization.
Some users need to download large amounts of data to their workstations in one organization, while a different organization doing similar work may implement all virtualized desktops with no local storage.
UEBA provides the flexibility to identify a unique organizational baseline and generate alerts for behavior that deviates from that baseline.


## PERFORM CONFIGURATION MANAGEMENT

Configuration management is a formal process of identifying key assets whose state — also known as _configuration_ — should be controlled, and implementing practices designed to achieve that.
It is desirable to keep information systems in a known good or secure state to ensure security controls like security agents, operating system configurations like full disk encryption (FDE), or placing systems in access-controlled networks continue to function.
Making changes to these configurations can alter the security posture of the system, so assets under configuration management must go through formal change approval processes to control unwanted configuration changes.

CM requires several foundational elements. _Configuration items (CIs)_ are the items under configuration management and can include entire systems, individual endpoints, and source code.
The secure configuration of a CI is known as a baseline, and any changes from the baseline require the use of a formal change request and approval process known as change management.
All systems over time will naturally undergo changes like patching, upgrades, and expansion of capabilities.

The organization’s guidance for implementing configuration management for hardware and software assets, including roles, responsibilities, and resources needed, should be documented in the configuration management plan.
The CMB is often the organizational body responsible for implementing and maintaining change management practices, though the processes require participation across the organization.
IT personnel responsible for systems maintenance will play a part in maintaining system configuration, while some nonobvious roles in change management include functions like purchasing and physical security and maintain controls like purchase order management and delivery verification controls that can prevent unwanted changes.

### Provisioning

Provisioning is synonymous with setting up and deploying a system or application, and the connection to the practice of CM is obvious — if a standard exists for a system’s configuration, it makes sense to follow the standard when provisioning.
Deploying an information system can be as simple as installing an application on an existing operating system, or it may involve designing the entire system and developing custom application code or components.

#### Requirements and Baselines

Traditional provisioning requirements for CM might include purchasing only approved hardware/software and then installing and configuring it in accordance with defined baselines (which are described in the “Baselining” section).
This can require a great deal of manual work, so tools like scripts and preconfigured system installation images exist to speed up and reduce the chances for error in the process.
The advent of virtualization made this task simpler, as VMs can be automatically created from images with all necessary configurations applied.

#### Benefits of Virtualization

Provisioning, built on the benefits of virtualization, has evolved in the world of cloud computing into extensively automated system and resource deployment.
Virtualized cloud services allow provisioning at scale across globally distributed data centers, which relies on definition files for system deployment and configuration.
Infrastructure as code (IaC) is the use of text-based definition files to specify virtual system parameters, such as amount of memory and processing capacity, and configurations like which system services should be enabled or disabled.
Because the definition file is relatively small and easy to read, it is simple to perform thorough reviews and ensure the system configuration conforms to the expected baseline.
The automated nature of deploying in an IaC environment also means there is less chance for human error.

### Asset Inventory

At the time of provisioning, entering an asset into the asset inventory is an essential element of a CM process. The organization cannot maintain configuration over assets it doesn’t know about, so recording new hardware, software, cloud services, and other information system assets is essential.
Due to its foundational role, the asset inventory may be worth implementing with a defense-in-depth strategy of both proactive and reactive inventory controls.

#### Proactive Inventory Controls

Proactive asset inventory controls include integration with purchase ordering and finance systems for hardware, software, and services purchases.
When the organization acquires a new asset, it is entered into the inventory along with details such as manufacturer, hostname, version/model/serial number, etc.
Deployment of new hardware/software can also be integrated with inventory update services, and automated deployment makes the process much easier by allowing for automated update of inventory data whenever new services are deployed using IaC.
When systems are decommissioned, the inventory can also be proactively updated by removing or marking these assets as decommissioned, using the same manual or automated methods.

#### Reactive Inventory Controls

Reactive inventory controls primarily consist of discovering assets that were previously unknown and going through the process of adding them to the inventory.
Many CM tools, network vulnerability scanners, and cloud management consoles offer the ability to enumerate or discover assets, and this list can be compared against the existing inventory to identify discrepancies.
This type of detective control is less secure as previously unknown assets may be unwanted or misconfigured, but with increased automation, a nearly continuous asset detection scan can be an acceptable method of updating the inventory.

### Baselining

A baseline is a set of agreed attributes for a system — in the context of CM and security, it is the set of configurations that are known to implement the desired security state.
A baseline provides a reference point for determining the amount of risk mitigation the organization has achieved, as well as a way to identify if the organization’s controls are not operating as intended.
Maintaining the baseline’s known good state is the ultimate goal of configuration management, while the closely related practice of change management is concerned with moving from one known good state to another in a controlled manner.

Each organization can develop its own security baseline to meet unique needs, though there are standard baselines available that can be used by any organization as written or as a starting point. These include the following:

* **DISA STIGs:**
Since they are designed for the U.S. Department of Defense, which has strict security standards, these baselines are unlikely to be broadly useful as many common functionalities must be disabled to comply with a STIG.
However, organizations may use these as a high-security starting point and then scope and tailor to enable needed functionality. STIGs exist for a wide variety of platforms.

* **CIS Benchmarks:**
CIS publishes free security benchmark documents covering a wide variety of desktop and mobile devices from Apple, Google, Microsoft, and versions of Linux, networking devices including firewalls and routers, as well as cloud and server operating systems from Amazon, Microsoft, Apache, and Oracle just to name a few.
These are based on global best practices and are usually less restrictive than DISA STIGs.

* **Vendor-provided guidance:**
Large technology vendors including Microsoft, Amazon, and Apple publish security best practices and suggestions for their products, which include hardening and baseline configurations.
These include documentation about how to enable specific features that enhance security like turning on encryption for data at rest.
They also include documentation about configurations or features that may provide useful functionality but with increased security risk, such as basic username/password authentication support for older applications that do not support multifactor authentication (MFA).

Configuration management and compliance tools often incorporate the benchmarks mentioned earlier as part of automated capabilities for configuration management auditing.
Baselines provide a consistent reference point, so these tools perform scans to identify any systems not configured according to the expected baseline, and the freely available nature of STIGs and CIS Benchmarks make them popular choices.
A configuration management audit typically involves the comparison of a set of systems against the expected baseline to identify configuration drift, or systems that have been modified in such a way that they are no longer configured according to the expected, secure baseline.

### Automation

Security misconfigurations are still one of the biggest causes of security incidents, and configuration management auditing is a key method to check for these misconfigurations.
Even a moderately complex IT environment can be challenging to audit frequently.
Continuous monitoring strategies require more frequent data collection; combined with increased expectations for frequent application and system delivery, supported by the move to DevOps and Agile methodologies, automated solutions for configuration management are required.

A proactive configuration management strategy enabled by DevOps and the use of dynamic cloud services involves the use of _immutable infrastructure_, which is infrastructure that is not designed to be changed.
Immutable infrastructure is torn down each time a system is deployed and then rebuilt using IaC definition files. Changes to the infrastructure require this teardown and rebuild process, which is automated and less error-prone and labor-intensive than legacy system-by-system upgrades.
Virtualized cloud environments make this process easy, and tools exist specifically for this purpose. These include vendor-agnostic tools and tools from the major CSPs like Amazon Web Services (AWS) CloudFormation and Microsoft Azure Resource Manager.

Automation supports not only the deployment of resources but can also be used to implement continuous audits. Dedicated configuration management tools exist to verify system and application configurations by querying system configuration files like the Windows Registry.
This function is also available in other tools like vulnerability scanners and automated compliance checking tools, and file integrity monitoring (FIM) is a technique that uses hashes of key files, such as system and application source code or configuration files, to detect unwanted changes.
Standalone FIM tools exist, and this capability is built into many HIDS and EDR solutions as well.


## APPLY FOUNDATIONAL SECURITY OPERATIONS CONCEPTS

There are several concepts underpinning good security practices in SecOps, including need-to-know, job rotation, and Service Level Agreements (SLAs).
These controls include both foundational elements of security programs and overarching concepts that may be implemented across multiple controls or parts of the organization.
For example, restricting access based on least privilege requires a combination of personnel security as well as physical and logical access controls.
These concepts should be implemented not just as individual controls, but also strategies used to guide the selection, implementation, and operation of other controls across the organization’s people, process, and technology.

### Need-to-Know/Least Privilege

Need-to-know and least privilege are often used interchangeably, but there is a subtle difference between them. Need-to-know is a concept describing a user’s organization-defined requirement to access specific information, such as a project or data contained in a system.
Users with a role in the finance department do not have a requirement to access sensitive data in a technical research project if it is not finance-related, and members of the research project likely do not have a need to access the company’s general ledger.

#### Need-to-Know

Need-to-know is often used in designing access control systems where compartmentalization is desired, where even users performing the same job or function but working on different projects across the organization are isolated from accessing data belonging to other projects.
Isolating information in this manner is often known as _compartmentalization_.

#### Least Privilege

Least privilege describes access controls designed to give users the absolute least amount of access needed to perform their job function, sometimes also known as minimum necessary access.
This access should be sufficient to perform assigned job functions and not in excess of that requirement; for example, a data entry specialist likely does not need administrative privileges to achieve their job function.

#### Applying Need-to-Know and Least Privilege

From the perspective of the entire organization, these concepts may be applied when structuring business operations and architecting information systems, which is why they are SecOps concerns.

If users with different need-to-know requirements will use the same system, that system must implement the ability to restrict access on a granular level.
If not, multiple instances of the system may be required to properly isolate data; with the advent of virtualization and cloud services, this has become significantly easier.

#### Just-in-Time

These concepts can also be applied when looking at individual user access required at different times. For example, system administrators do not need elevated permission at all times to perform their jobs.
When making a system configuration change, the elevated administrative privilege is obviously required, but checking email or writing a report can be done with normal user permission.
An architecture of separate user and admin accounts, or providing a method of escalating privileges like sudo, implements access controls in line with these principles.

An emerging concept in access management is just-in-time access, where users are granted access to privileged credentials when needed, and the privileges are revoked once the task requiring the credentials is complete.

### Separation of Duties and Responsibilities

Separating duties or responsibilities can achieve multiple benefits. It can frustrate insider threats by making fraudulent activities much more difficult to pull off, and it also supports integrity of data and processes by requiring multiple parties to participate.
This raises the chance of detecting errors and can protect the authenticity of data by preventing a single user from corrupting it.

#### Separation of Duties

Separation of duties (SoD) limits the potential for misuse of resources or malicious activities by separating process steps among multiple personnel.
Typical examples include expense report submissions, where an employee submits an expense report that must be approved by a finance admin before being paid out, or retail stores where a cashier and manager are both required to count and validate cash at the close of each day.
In both cases, the process is made less efficient, but the intention is to make it harder for any one individual to commit fraud, make a mistake, or commit an act alone which carries serious consequences.
To do these things, two individuals must either act in collusion or be forced to commit fraud, which is more difficult than one individual acting alone or being coerced.

#### Two-Person Integrity

The cashier and manager close scenario cited is an example of dual control, which is a process requiring two or more individuals to perform the same action to achieve an objective.
Two-person integrity is another related concept, whereby no single person can access an asset like a file or piece of equipment without another authorized individual present.
Other systems where this is implemented include encryption key escrow recovery, where multiple users must sign in to the escrow system to recover a key.

### Privileged Account Management

Privileges, often called permissions, are the abilities a user is granted on a system.
Privileged accounts are those with elevated levels of access, oftentimes administrators or superusers; this increased level of access also means the risks associated with these accounts are higher — since an administrator can perform more functions, there is inherently more risk if they make a mistake, act maliciously, or have their credentials stolen.

Managing privileged accounts adds additional requirements to the user management lifecycle. Before privileged users are even provisioned, it is desirable to identify the positions and privileged functions required for the functioning of information systems and organizational processes.
These roles, such as database administrators (DBAs) and access control administrators, should be designed with principles like least privilege and SoD in mind, and system architectural choices may be driven by these requirements.

For example, DBAs may not require access to the actual data in databases they administer, so an application-level encryption choice is appropriate to allow DBAs access to the database but block access to plaintext data.

Furthermore, privileged accounts may be dedicated to administrative functions, and users should be issued other nonadmin credentials for routine tasks like web browsing or checking email.

Privileged accounts typically require additional levels of rigor during the access management lifecycle, such as more frequent reviews. Additional controls at different phases include the following:

* **Provisioning:**
Users who request or need privileged access should be subject to additional request and review procedures. This may require more documentation and multiple levels of review or approval prior to granting access.
These reviews may utilize other security processes such as personnel screening, with privileged users subject to a more thorough background investigation.

* **Use:**
If possible, credentials for elevated access should be time-bound and automatically expire. Just-in-time privileged access management allows users to gain temporary access to privileged credentials for a limited time and by following auditable procedures.
Unix and Linux systems can implement this via sudo, which is usable for a set period of time before reauthentication is required.
Dedicated privileged access management systems also exist and can be used to implement what is known as a “break the glass” process, where administrative credentials can be accessed for a limited period of time in the event of an emergency.
After the time period passes, the credentials are automatically reset. The use of administrative privileges should be logged, and wherever possible, separate accounts for privileged and nonprivileged activities should be used.
Where privileged accounts are necessary, additional authentication mechanisms are also appropriate, such as mandatory MFA.

* **Review:**
Monitoring strategies should include a focus on privileged account usage, and monitoring tasks like automated or manual log reviews should be performed more frequently for privileged accounts.
Reviews should identify either accidental or malicious credential usage. Accidental misuse might be a user forgetting to sign out from a privileged account before performing nonprivileged work, while malicious use might be a privileged account being used remotely from a different country.

* **Deprovisioning:**
Compliance frameworks or obligations may require that privileged account activity be retained for a longer period of time, especially if the privileged access is to sensitive data like healthcare or financial information.
Archiving logs associated with privileged users or unique deprovisioning actions like suspending accounts rather than deleting them are common practices for privileged accounts, as they support investigation of the elevated actions taken by these users.

### Job Rotation

Rotating jobs among employees has two primary benefits.

#### Cross-Training Opportunities

It provides cross-training opportunities, which offer employees the opportunity to enhance skills, and it provides more resilience to the organization.
If one person is on vacation or unavailable, others can fill in for those job duties. This availability aspect is one reason a CISSP should consider implementing job rotation within an organization, as it supports business continuity (BC), disaster recovery (DR), and resilience capabilities.

#### Mitigating Insider Threats

The second function of job rotation is to mitigate insider threats like fraud. A single employee performing the same function repeatedly has the opportunity to commit fraud and cover their tracks, but if the job is done by another employee next month, the possibility of discovery increases.
This is used in complement with separation of roles or duties, which forces collusion among multiple employees if fraud is to be committed.
When an unknown employee will rotate into a job in the future, collusion becomes more difficult.

#### Spotting Errors

A new user taking over a process during job rotation also has the opportunity to spot and correct errors that are not malicious, which supports integrity.

#### Forced Vacations

Forced vacations or leave, where employees are required to step away from their job, can also be effective at spotting either fraudulent or innocent errors, and provide cross-training opportunities that support availability.

#### Disrupting Malicious Outsiders

Job rotation can be also used as a long-term strategy to disrupt potentially malicious outsiders from attacking employees.
Open-source intelligence (OSINT) is often used to gather information like job function, department, or role, which is useful when crafting spear phishing or other social engineering scenarios.
If employees do not stay in the same role for extended periods, this intelligence becomes much less valuable.

### Service-Level Agreements

Organizations are increasingly acquiring technology in the form of services provided by outside parties. CSPs and managed security services providers (MSSPs) are two common examples.
Due to the costs associated with building cloud IT infrastructure or security functions like a SOC, it might make sense for a business to instead pay a specialized provider for these services.
In this case, the organization becomes an acquirer of services, and the CSP or MSSP is a provider.

Managing service providers can be a challenge since the provider is outside the direct control of the acquirer.
If an organization wants IT systems that provide high availability and 99.9 percent uptime, they can specify those as requirements for internal system developers and operations personnel to meet.

#### Service-Level Requirements and Agreements

When a provider is used, those same requirements become service-level requirements (SLRs), which must be documented and agreed upon between the parties. SLRs should be recurring or continual needs that must be met, rather than infrequent events like meeting a disaster recovery time objective.
A mutual agreement of SLRs is an SLA, which codifies the shared understanding of SLRs.

#### SLA Objectives

SLA objectives should be discrete and measurable, such as an application uptime of 99 percent over the course of a year. This can be measured by calculating 365 * 0.99 = 361.35.
To meet the SLA, the application must be reachable and perform the desired function for at least 361 days out of the year. Put another way, the application should not be down for more than four days.
These agreed-upon metrics must be documented and carefully reviewed to ensure mutual agreement. If the service provider excludes maintenance windows from uptime and the acquirer does not, then the parties may have different calculations of uptime, leading to disagreement about whether the service met requirements.

#### SLA Monitoring

SLA monitoring is a form of third-party risk management and should be a critical part of continuous monitoring.
Different strategies exist for different types of SLAs; for monitoring uptime, there are tools like synthetic transactions, which verify transaction results in the expected outcome, or heartbeat technologies, which check to see if a web page loads.
SLA reports can also be calculated for services like response times, where a provider must respond to support tickets within a certain timeframe.

#### SLA Compensation

An SLA is a signed and legally binding document between the service provider and acquirer and may include payment discriminators when services do not meet the objectives.
If the SLA is not met, then the provider must offer a discount or credit proportional to the duration the service was unavailable or degraded.
These terms and conditions may not be the direct responsibility of a security practitioner, but it is important to ensure that alternative controls exist if needed to compensate for a service failure.


## APPLY RESOURCE PROTECTION

Almost the entire contents of this book deals with protecting resources, including processes, procedures, and tools to preserve confidentiality, integrity, and availability of an organization’s valuable assets.

Media is any material that can hold data, so techniques are warranted to ensure the data is adequately protected from unauthorized disclosure, tampering, or destruction.

Many organizations publish their media, information, and records handling policies as a transparency measure, so customers or users are informed of how data they submit will be handled and stored.
There are a number of resources that can be used to craft media handling policies including the A.8.3 “Media Handling” requirements in ISO 27001, or the Media Protection (MP) family of controls in NIST Special Publication 800-53.
For specific guidance on secure media destruction procedures, NIST SP 800-88 revision 1, “Guidelines for Media Sanitization,” is a freely available resource that covers specific methods and tools to securely destroy media and data.

While ISO and NIST documents provide a high-level standard for securing media, many organizations will also be required to follow specific guidance based on the industry regulations.
A CISSP should be aware of these requirements and ensure any resource protection policies and procedures account for them.

For example, securely shredding removable USB drives is a valid protection against data exposure, but some industry regulations ban the use of such devices altogether.
In this case, policies and technical controls must be in place to prevent data from being written to USB drives, rather than focusing on their secure destruction.

### Media Management

Media can be anything from paper records to traditional hard disk or solid state drives (HDD or SSD) and increasingly include storage in cloud environments.
Data should be classified in accordance with the organization’s classification policy, and the identified classification level should be used to select appropriate controls.

#### Labeling and Marking

All media should be labeled in some way to indicate the classification of the data it contains, and wherever feasible, data should also include an identifier of its classification level.
In traditional hard copy, this might be a watermark or document header/footer with the classification level, while digital documents can have watermarks, header/footers, or even metadata like file tags, filenames, or other embedded attributes indicating the classification level.

Marking digital media can be more difficult for a variety of reasons. If an information system contains multiple files or datasets, what is the correct classification level?
In that case, the policy should provide an answer — typically the media is classified to the highest level of data it contains.
Similarly, if an information system contains multiple storage devices, the policy and media procedures should dictate if each storage device must be individually labelled.
The ever-shrinking size of storage devices can make labeling data difficult, as there is not enough room for all vital information, while other technologies like VMs present additional challenges.
In the case of the VM, the cluster or data center it is created in may be the method of “marking” it at a certain classification level, and restrictions must be in place to prevent the VM from moving to a cluster of a lower classification level.

#### Handling

The purpose of a label should be to communicate the classification level of the data, which in turn drives user behavior when it comes to handling the media and data.
Users must be trained on classification levels and media handling procedures.

For example, if data is on a drive marked “Internal Use Only,” then users might be trained to never remove that drive or its data from an organization-controlled facility.
Handling procedures also include destruction or disposal requirements, which may be indicated on the label and are discussed in the following section.

### Media Protection Techniques

Protecting media involves applying the security controls indicated by the data’s
classification. Processes and procedures to apply the necessary controls must be documented, users must be trained, and of course, the users must actually implement the required controls.

Organizations should restrict access to media using principles of least privilege and also provide physical security measures to be implemented by authorized staff.
These may include locked bags or cases, security cables, or other physical security means, as well as training on the proper use of such tools.
Media should also be subject to inventory and inspection from time to time to ensure it is accounted for and being handled properly.

#### Transporting Media

Although data-in-transit controls are typically discussed in the context of protecting network communications, data can also be transported on physical media.

Controls for securing media in transit include the following:

* **Encrypt** data prior to storage on the media or use self-encrypting media that requires a user to enter credentials to access the data.
* **Hash** data written to the removable media and compare the data’s current hash to the original to ensure data was not altered during transit.
* **Physically secure** the media with locked cases, nonobvious labeling, and strict procedures for the courier or other individual transporting the media to maintain awareness of the media’s location and safeguard it from damage or theft.

#### Sanitization and Disposal

Media may be sanitized if the data contained is no longer needed, after which the media may be reused, sold, or disposed of. Various methods of sanitization and disposal exist, and are discussed in Chapter 2, “Asset Security,” as part of the data lifecycle.
Choosing a destruction method must take into account several factors, including the speed of destruction and any desired reuse of the media.
Obviously, media that is physically destroyed cannot be reused, but the time needed to sanitize media by overwriting may be so excessive that simply buying new media is a more cost-effective action.

In the case of FDE, it is possible to utilize an existing security control for data sanitization or destruction.
The confidentiality of data on a disk with FDE can be preserved if the key needed for decryption is destroyed.
Sanitizing the disk simply requires secure destruction of the key, which is a process known as cryptoshredding or cryptographic erasure.

For SSDs where overwriting or degaussing is not an option, this may be a viable alternative to physical destruction, and in cloud storage solutions where the organization has no physical control over storage media, it is often the only way of ensuring secure data disposal.

Media destruction can often involve expensive equipment and require the use of an authorized destruction provider. In this case, proper management of the destruction vendor will be a key contract and SLA activity.
The organization and provider should agree to specific physical security standards for the destruction task, and contracts should include language requiring insurance against any data breaches as a result of recovery from destroyed media.


## CONDUCT INCIDENT MANAGEMENT

There is a subtle but important difference between events and incidents; both are important for continuous monitoring and the practice of incident management.

* **Events** are any observable item like routine user or system actions, such as a user successfully logging into a system or a file being accessed.
Many routine events will be logged but do not require additional action.

* **Incidents** are events that are both unplanned and have an adverse impact on the organization. They typically require investigation and remediation by some combination of IT, operations, and security personnel.

Examples of incidents include unexpected restart of a system, ransomware preventing users from accessing a system, or a planned system outage that goes beyond the allotted time.

All incidents should be investigated and remediated to restore the organization’s normal operations as quickly as possible and to minimize impacts like lost productivity or revenue.
Resuming normal service is the primary goal of incident management. While legacy incident management processes focused on manual detection, investigation, and response to incidents, SOAR platforms are designed to reduce the time required to manage incidents.
They do so by gathering and analyzing data to detect incidents and then automating response actions needed to defend and protect systems.

Not all incidents will require participation by the security team. For example, increased system utilization due to a new product launch is expected and simply requires operations resources to add additional capacity.
A coordinated DoS attack by a foreign nation state, however, would require participation by both IT and security personnel to successfully remediate.

### Incident Management Plan

Many security frameworks refer to incident handing as incident response, while operational frameworks such as ITIL use incident management.
The goal of both is largely the same — dealing with the incident and restoring the organization to normal operations.

The foundation of this IR capability is a documented IR plan, which is a proactive control designed to help the organization respond more effectively when an incident occurs.

The IR plan should document the tools, resources, and processes needed to identify, categorize, and remediate the impact of incidents. The IR plan typically contains the following:

* **Definitions of incident types**, such as internal operational incidents, security incidents, or emergency situations that require first responders.

* The **incident response team (IR team) personnel**. The team members and skills needed will depend on the type of incident, but an incident response coordinator should always be appointed to assess the situation and identify the skills and actions needed.

* **Roles and responsibilities for the IR team personnel in each incident type**. This includes roles internal to the organization, as well as responsibilities of external stakeholders like law enforcement or business partners.

* **Resources required**, such as operations or security management tools to facilitate detection and response like the SIEM or IDS. Checklists and procedure documentation is useful during an emergency to ensure team members perform the correct functions during a stressful event.

* **Incident management processes** must be laid out according to the lifecycle phases presented in this section, including processes for personnel to follow when an incident is first detected, under triage, and once a remediation plan is determined.
Incidents must be detected to begin the process, and then the IRT will execute appropriate steps to investigate, respond, and remediate.

All incident response frameworks emphasize the importance of planning ahead for incidents by identifying likely scenarios and developing appropriate response strategies for each before they occur.
Incidents can be a high-stress situation, and ad hoc responses are less preferable than preplanned, rehearsed responses.

A variety of standards exist to support organizations developing an incident response capability, as highlighted by the following list:

* ITIL framework incident management processes
* NIST Special Publication 800-61, “Computer Security Incident Handling Guide”
* ISO 27035, “Security incident management”
* European Network and Information Security Agency (ENISA), “CSIRT Setting Up Guide”
* ISACA, “Incident Management and Response”

Another important aspect of the organization’s incident management capability is the proper categorization and prioritization of incidents based on their impact and criticality.
This is similar to risk assessments where risks are analyzed according to their potential impact and likelihood.

Incidents have already occurred, so they are often measured by:

* **Criticality/impact:** The effect the incident has on operations
* **Urgency:** The timeframe in which the incident must be resolved to avoid unacceptable impacts

Many organizations utilize a priority score from zero to five (P0–P5) to categorize incidents. P0 is the most critical, and P5 is the least critical, and members of the IRT use this score to prioritize the work they must perform.
In many organizations, an incident at or above a certain priority rating may also be a trigger for other organizational capabilities, such as invoking BC or DR plans.

#### Incident Response Testing and Exercise

IR planning is a proactive control, so the IR plan must be documented before an incident occurs. Conducting tests and exercises of the IR plan serves two vital functions.

* First, testing the plan in a nonemergency situation can help to identify gaps, oversights, or issues that could prevent the successful execution of the plan during a real incident.
* Second, the exercise can be used to train members of the IR team on their duties, which reduces confusion or wasted effort during a real incident because team members are able to respond from memory.

IR testing can be conducted to exercise a particular scenario, with the goal of identifying how effective the plan is in dealing with that type of incident.
For example, widespread outbreak of ransomware could be used as a scenario to gauge how effectively backup procedures or systems are at taking over operations.

IR exercises can be integrated with the testing or exercise of other plans like BC and DR, as security incidents often create situations that necessitate the activation of these other processes.

#### Third-Party Considerations

Most organizations will have some dependencies on external entities including suppliers or vendors, especially for services like utilities and cloud computing.
Activities like IR and business continuity and disaster recovery (BCDR) may need to include these vendors to ensure proper coordination with external service providers to allow the organization to continue functioning.

The IR plan should identify any key external service providers or third parties like digital forensics and incident response (DFIR) providers, cyber insurance carriers, legal or communications experts, and data breach specialists who might need to be involved with an incident response.
The IR plan should also contain contact information for these third parties to ensure the organization can engage any services needed during an incident.

Third parties whose services need to be utilized in emergencies should be included in the IR plan. Each provider’s contact information should be documented for easy reference, as well as the circumstances that require the provider to be involved.
Roles and responsibilities of the third party should also be documented, so it is clear to the team which tasks must be performed internally and which tasks will be handled by the third party. 

### Detection

#### Detection Sources

An incident must be detected before the organization can take appropriate response measures. The tools and processes that are monitoring operations and risks detect the incident and then generate alerts or signals to security analysts.
Automated platforms like SIEM tools, security tools like anti-malware, and even humans can be the detectives who notice something and report it, whether by generating an automated alert or by raising an incident report.

#### Automated Detection

The organization’s logging and monitoring strategy should be centered on identifying and alerting on potential incidents as quickly as possible.
When an incident is detected, documentation should be automatically created to begin tracking work and decisions related to the incident — tools like SIEM tools will create a work ticket where the subsequent steps can be recorded.
The process may initially generate false positive results, but with a process of continuous improvement and tuning of the detection capabilities, automated tools and alerts should become more accurate over time.

The detection of an incident can automatically trigger the incident response process by generating an incident report and initiating resources like a service ticket or checklist to begin investigation.
Alternatively, the detection may go through a review process during which an analyst reviews the incident and conducts some basic research to determine if the incident is legitimate or a false positive.
If the analyst deems the incident valid, response procedures are initiated.

### Response

Triage is an early-stage response process for confirmed incidents and is designed to identify the criticality and categorization of the incident type. For technical incidents, a SOAR tool automates some or all of the response.
If the incident is completely contained by the SOAR, no additional triage is needed. If the incident cannot be fully contained by the SOAR, identifying impacts of the incident such as data breached and users or systems impacted is essential.

These factors guide the creation of an IR team with appropriate resources to handle the specific incident at hand.
For example, a ransomware incident affecting Windows-based systems is unlikely to require Linux administrator skills, while a data breach on a Linux system will definitely require Linux administrators as well as breach response personnel such as legal counsel.

The most obvious aspect of the IR phase is to begin responding to the incident at hand, which includes both gathering evidence and making decisions about how to restore normal operations.
The IR plan should contain scenario-based guidance for likely incidents to guide the team’s actions, such as responding to a widespread malware outbreak or breach of sensitive data.
Following documented procedures and utilizing checklists is essential to ensure a coordinated response, though it is unlikely all possible circumstances will be accounted for in the IR plan.
In uncertain circumstances, the IR coordinator or IR team lead must make executive decisions with the information available and coordinate the team’s response accordingly.

The IR team must begin to collect and preserve evidence as soon as the incident is declared. As mentioned earlier about evidence collection and handling, it is not always possible to determine at the outset whether an incident will require law enforcement or the presentation of evidence in a court of law.
Evidence gathered must preserve the chain of custody if the incident necessitates these actions, so the IR team’s activities should follow strict standards to ensure any information gathered can be used later.

During response, the initial elements of reporting will also be performed. The primary goal of reporting is to accurately document what happens before, during, and after the incident, so the IR team should be generating documentation including the following:

* A summary of the incident detection
* Detailed steps taken to investigate and respond to the incident, including the team member name, time, and purpose of any activities conducted by the IR team
* Any information system events, IoC, and evidence related to the incident collected during investigation
* Origins of the attack and any evidence of the TTPs gathered during the investigation if applicable
* Evidence of interviews or other information gathering activities

#### Data Frameworks

The process of investigating and responding to an incident generates a large volume of data, and without structure, the data can be difficult or impossible to use.
The communications and security company Verizon has produced a framework for categorizing, capturing, and managing data related to incident response called the VERIS framework.
This provides a structured way of capturing and managing IR data, which is useful for directing activities of the IR team. Details of the project can be found here: veriscommunity.net.

### Mitigation

Mitigation is the phase where the organization begins to implement actions necessary to fix the incident. This requires an understanding of the incident cause, as well as both people and technology resources to address it.
Mitigation focuses on containing the incident quickly and stopping the impact from spreading, and may involve short-term fixes to address immediate problems but long-term fixes for root causes.

Isolating or containing an incident often involves isolating, quarantining, or otherwise disabling problematic systems or components like user accounts, servers, or workstations.
These steps will be highly dependent on the type of incident — for example, a malware infection may involve logical isolation of affected servers or physically disconnecting network connections to prevent the malware from spreading, while a widespread phishing attack might necessitate a reset of all user passwords in the organization and disabling email to prevent additional users from being affected.
Given the wide variety of potential incident circumstances, mitigation should follow playbooks, checklists, or other prepared reaction guides that reduce the amount of decision-making required — people in a crisis situation do not always make the best decisions, so planning ahead is crucial.

During mitigation, details of the response effort will need to be reported, as the actions taken can be used to estimate the impact of the incident and drive continued decision-making.
For example, if a system infected by malware can be easily isolated and restored from a backup, the impact to the organization is minimal.
However, if the same malware infection has spread widely among the network, isolation and recovery may not be an effective mitigation.

Reporting these results will help executive decision-making about activating other plans like BCDR.
The potential for rapidly evolving intelligence about the incident may necessitate the use of routine check in meetings, such as an hourly status briefing to ensure all stakeholders are apprised of the situation and can act accordingly.

### Reporting

Although reporting is a single IR phase, the reality is that reporting is done continuously throughout the IR process. Various stakeholders will require information updates throughout the process, both for situational awareness and to provide resources needed for the IR team to carry out its duties.
However, there will be formal reporting required at various points and to various stakeholders, and a single IR coordinator should be appointed to handle formal communications to stakeholders like executive management or the public.

#### Internal Reporting

Incident reports will be required by different internal stakeholders for a variety of purposes.
Members of the IR team will require status reports to keep team activities aligned to the goal of restoring normal operations, and they will need details like systems or data impacted, investigation steps performed, and any findings.
These reports may be informal and be generated as part of the investigation process, such as completion of checklists or logging of incident investigation and mitigation activities by IR team members.

More formal reporting to management and decision-makers will also be required. Depending on the incident and steps needed, the reporting may be informal, such as a metric on a dashboard showing the number of successfully resolved incidents, or a highly formal report for particularly serious incidents.
In the latter case, this report may be presented to senior executives to drive strategic decision-making needed for long-term responses, like making a shift from on-premises to cloud hosting for vital services to decrease downtime.
Formal reports or notifications to key decision-makers are also usually required to activate other organizational plans like BCDR.

#### External Reporting

Members of the IR team may need to prepare reports for external stakeholders in some circumstances.
The contents of the report, format of the data, and timelines required for reporting will vary based on the external stakeholder’s requirement, so the IR team will often need to coordinate with a communications or legal expert to ensure compliance.
Note that none of this section deals with reporting a data breach incident, which is detailed in a later section.

Non-breach-related external reporting may be required in a variety of circumstances, including the following:

* **Government organizations** (including private-sector entities like government contractors and critical infrastructure providers) may be required to report certain cybersecurity incidents like intrusions or data breaches to governmental agencies like a Computer Emergency Readiness Team (CERT).
These bodies typically require specific methods and timeframes for reporting or submitting information.

* **Industry regulators** like the Payment Card Industry (PCI) may require that security incidents be reported if they meet certain thresholds such as number of affected users or number of records breached.
In some cases, the industry regulator will have its own IR team and abilities that can be activated to assist with the investigation.

* **Law enforcement** agencies will require reporting and sharing of details in the event an incident is caused by criminal activity.

* **Business partners, vendors, and service providers** may require reporting of any incidents that could affect their business or data they share with the impacted organization.
Requirements for these reports will be in contracts and should be accounted for when planning IR team capabilities related to communications.
These external stakeholders may also need to be notified in the event that they were the cause of an incident or breach that impacted the investigating organization.

* **Users, customers, and the general public** may need to be informed of a security incident that impacts the usability or availability of services.
Organizations that provide services to external parties may need to notify those parties of a potential suspension or degradation of the services during the incident. Note that this excludes data breaches, which are covered next.

#### Breach Reporting

The definition of a data breach varies subtly across different laws, regulations, and security frameworks, but it is essentially any unauthorized access to data.
This definition can include both internal and external users, but different regulations carry different requirements for reporting.
As a security practitioner, it is important to know what type of data your organization handles, to understand what regulations or jurisdictions you operate in, and to get proper legal guidance on your organization’s requirements for reporting breaches.

In most privacy legislation, there is a requirement to report breaches affecting private information to a regulator within a certain period of time.
This time period is typically a certain number of hours after an organization discovers a breach, which allows time for basic incident triage and response to occur — but it is worth noting that the initial report usually must be made before the full IR process is complete.
Investigation and triage may be ongoing when the initial breach report is submitted, and it is likely the regulator will require updates as IR progresses.
Privacy laws with breach reporting include various state-level laws in the United States, federal and provincial laws in Canada, federal laws in many South American and Asian countries, as well as the EU General Data Protection Regulation (GDPR) and data protection laws for each member nation in the EU.

Many of these laws also require direct notification to any impacted individuals and may require additional post-breach obligations as well.
These can include ongoing monitoring for potential identity theft, and the costs of such obligations should be a key consideration in the organization’s governance and compliance strategies.

### Recovery

The primary goal of recovery is to restore normal operations. Not all incidents will involve a recovery, such as a violation of a security policy that only results in an employee being disciplined.
That mitigation step is the end of the IR process, since normal operations were not disrupted; if the employee had utilized a software vulnerability to steal sensitive data, then recovery activities including system patching and breach response would be appropriate.

Recovery may begin as soon as detection occurs and continue until the incident is completely over. Action like changing a password after a user responded to a phishing email can be a recovery step, and the recovery phase ends when the organization returns to normal levels of service operations.
If a BCDR event is declared due to the incident, the recovery phase may last until that declaration is also resolved.

### Remediation

Remediation is a long-term strategic activity designed to eradicate any root causes identified for the incident.
Underlying vulnerabilities identified as the root cause of an incident must be addressed during remediation, such as insufficient monitoring of patch deployment that allowed a software vulnerability to be exploited.
If a user clicked a phishing link and entered their credentials, remediation might include more robust user anti-phishing training for all staff, blocking known malicious email senders or the domains used in the phishing attack, and implementing email security tools designed to block phishing.

Damages resulting from incidents are also addressed during remediation. This can include payment of monetary fees/settlements to stakeholders such as regulators, customers, or users impacted by the incident.
Long-term organizational steps to address root causes, such as increasing security staff or resources, can also be remediation steps if the organization deems these additional resources necessary given the threats faced.

### Lessons Learned

After an incident is remediated, it is important to document any lessons learned during the IR process.
This serves two goals: first to identify any IR process improvements to be made, and second to address any underlying or root causes with the goal of preventing the incident from recurring.
Metrics from the incident response process should be gathered and analyzed to support this decision-making, and the intent is to highlight both the positive and negative aspects of the incident response to facilitate improvement.

Lesson learned should be gathered in a formal process, documented, and assigned as action items with accountability for completion.
These lessons should identify what went well and what could be improved for future incidents, and the process is often called a postmortem or after-action report.
The process should be facilitated by a neutral party who can help participants separate relevant facts from personal feelings related to the incident.
Incidents can be stressful and challenging, so the facilitator’s role is crucial to ensure facts and metrics are properly documented to support improvement efforts.


## OPERATE AND MAINTAIN DETECTIVE AND PREVENTATIVE MEASURES

Security controls can mitigate risks by preventing them from occurring and reducing the likelihood, or they can detect a risk that has occurred to trigger corrective actions designed to reduce the impact.
A CISSP should design a security program using the defense-in-depth paradigm where controls are layered to serve both preventative and detective functions.
This arrangement provides both proactive and reactive risk mitigation, and the types and number of controls implemented must be balanced against the value of the asset and associated costs to implement.

#### People and Process

To be truly effective, security controls like those discussed next, including firewalls, intrusion detection, and next-generation tools incorporating machine learning and artificial intelligence, must not be treated as purely technology solutions.
People and process must be considered to make these tools truly valuable and achieve the goal of mitigating risk.
Security incidents that could have been stopped sooner or entirely prevented have occurred due to security tools that were improperly tuned or, even worse, ignored.
Processes for investigating and responding to alerts and properly configuring platforms like SIEM are more important than having the latest technology, since the technology ultimately must support the human analysts who are tasked with addressing complex risks.

#### Involvement of Multiple Phases 

Security practitioners will be involved at multiple phases in the selection, implementation, ongoing management, and monitoring of these controls.
For instance, the security team may be a key stakeholder in choosing network security tools like firewalls and should be consulted when gathering requirements.
IT or network operations personnel will likely be in charge of installing and maintaining the firewall, but log data generated by the firewall about potential network attacks is a key input to continuous monitoring processes owned by the security team.

#### Effective Communication and Partnership

Operating and maintaining these tools requires security practitioners to collaborate with other departments or teams in the organization, so effective communication and partnership skills need to be a priority for a CISSP.
Ensuring that IT and operations teams understand the requirements for and importance of the security measures they maintain is crucial, and being an effective partner requires offering reciprocal support when those teams encounter problems.
Simply telling a network administrator “no” when they request to open a port on the firewall does not support the CISSP’s mission of aligning security with the organization’s mission, especially if the requested port is required for a legitimate business purpose.

### Firewalls

Firewalls access control devices designed to isolate and control the flow of information between different segments of a network. They do this by analyzing traffic and applying rules to determine if the traffic is forwarded (allowed) or dropped (denied).
Depending on the type of firewall, they can be used to prevent outside access to resources in a network segment, prevent malicious requests from reaching an application, or even control the flow of information into and out of a specific host.

There are several types of firewalls, and it is important for security practitioners to understand the specific uses cases where each can be deployed most effectively. They include the following:
* **Static packet inspection (stateless):**
These are the original firewall type, designed to inspect network packets and compare them against a ruleset.
For example, the firewall might see TCP destination port 23 (Telnet) in a packet header and drop the packet since Telnet is an insecure protocol.
Static firewalls operate very quickly but struggle with complex situations like videoconferencing where the ports used are less easily determined, which makes defining rules difficult.

* **Stateful:**
These are an evolution of static firewalls and offer the ability for the firewall to understand context regarding communication (known as a state).
A stateful firewall might normally block traffic on high-number ports but allow it for a specific endpoint if that endpoint has previously established a connection using port 20/21 (FTP).
Since FTP clients often negotiate a custom port for transferring a file, allowing the higher port makes sense in the context of previous traffic.
Stateful firewalls have more intelligence and flexibility, but come with higher processing overhead and cost.

* **Web application firewall (WAF) and API gateway:**
These are a highly specialized form of network access control devices designed to handle specific types of traffic, unlike a generic firewall that handles all network traffic.
WAFs and API gateways analyze traffic destined specifically for a web application or an application’s API and can be useful for mitigating complex attacks such as SQL injection.
These devices apply a set of rules to HTTP conversations and look for anomalous interactions with the application and can identify attacks that would not be immediately apparent in raw network traffic.

* **Host-based firewalls:**
These are installed on a specific endpoint and use a ruleset specific to that endpoint. They can be a useful defense-in-depth measure that offers protection if a network-based firewall fails, but also introduce processing overhead on the endpoint.
They can be particularly useful in virtualized environments and enable microsegmentation, whereby individual endpoints exist in their own network segment with customized access rules.

* **Next-generation firewalls (NGFW):**
These are more of a marketing term than a unique type of firewall, but NGFWs combine multiple security functions into a single device.
This may include a stateful firewall and API gateway, and many include advanced analytics based on artificial intelligence or external threat data.
NGFWs combine other network security protections like intrusion detection or VPN services as well. Centralizing these functions can offer lower overhead in configuring network security devices, with the downside of a potential single point of failure.

* **Security groups:**
These exist in SDNs and cloud environments and serve many of the same functions as a firewall. A globally load-balanced application may exist in several data centers all over the world, and it would be difficult to place firewalls to control highly dynamic virtualized resources.
Security groups (also called network security groups [NSGs]) are an abstraction layer that define protections required, and the virtualized infrastructure is created and deployed according to definition files in a process similar to IaC.
This dynamic creation allows for consistent yet flexible deployments and supports microsegmentation.

Firewalls, security groups, and microsegmentation are useful access control devices in a zero-trust network architecture, where no part of the network is implicitly trusted.
Individual endpoints and subnetworks that are within the organization’s control are still viewed as potentially malicious and therefore require strict access controls.
This assumes that an attack might be carried out by a trusted insider or an attacker who has gained an insider’s credentials.

### Intrusion Detection Systems and Intrusion Prevention Systems

#### IDS

IDS can detect system intrusion attempts, while IPS can both detect and react to system intrusion attempts.
An IDS is a passive device that analyzes traffic or activity and generates an alert when activity is detected that matches a known malicious pattern, deviates from normal or expected system operations, or both.
For example, a large volume of halfcompleted TCP handshakes — where a synchronize (SYN) packet is received but never acknowledged — is unusual and is a known signature of a TCP SYN flood attack.
A more complex IDS might monitor key system files and system usage patterns and generate an alert when the activity on the system deviates from the established baseline.

#### IPS

An IPS goes one step further. Rather than just generating an alert and requiring a human to take action, the IPS can automatically take preventative action in response.
In the TCP SYN flood example, the IPS might implement a new firewall rule to block traffic from the IP addresses creating the half-open connections.
While there are obvious benefits such as faster response, which reduces the impact of an intrusion, there is also the potential for an IPS to take unwanted action.
In the case of suspicious system behavior, the system in question could be shut down, which renders it useless. If the unexpected behavior is legitimate, the IPS has inadvertently caused a loss of availability.

#### Network- and Host-based IDS/IPS

Both IDS and IPS can be deployed in two ways, and the deployment model as well as location are critical to ensure the devices can see all traffic they require to be effective.

Network-based IDS/IPS (NIDS/NIPS) sit on a network and should be placed to observe all traffic, such as at a network’s perimeter, for optimum visibility.
Similar to firewalls, however, NIDS/NIPS may struggle with a virtualized environment where network traffic between VMs never crosses a switch.

Host-based IDS/IPS (HIDS/HIPS) are deployed on a specific host to monitor traffic, which helps overcome traffic visibility issues but introduces additional costs for licenses, processing overhead, and issues of compatibility with endpoints.

### Whitelisting/Blacklisting

The terms whitelisting and blacklisting are being replaced with other terms like allow list and deny list; regardless of the terminology, these refer to a list of explicitly allowed or explicitly denied entities such as applications, IP addresses, network endpoints, or even network traffic originating from specific countries.

Explicitly allowing or denying entities will have different implementation methods depending on the type of entity.

Allowing network traffic from only known, organization-controlled IP addresses to a cloud service is a common tactic for preventing unwanted access by outsiders and forces legitimate users to connect through organization-controlled networks where monitoring is enforced.
Blocking all traffic from countries that are known to host criminal activity and that your organization does not interact with can reduce the likelihood of attacks.
Both of these could be implemented using network technologies like firewalls or VPNs.

Allow lists or deny lists can also be used within other tools such as operating systems, app stores, and email clients.
A list of explicitly approved and denied apps can be created and enforced through app store purchasing policies, configuration management tools, or even internal training material like “For accessing corporate email, only the approved smartphone email app is to be used.”
Many email security tools offer the ability to filter traffic from known-malicious domains or email servers, which effectively denies potentially malicious messages from ever reaching users’ inboxes and is a form of deny listing.

### Third-Party-Provided Security Services

One crucial decision a CISSP must make is whether to build security processes and services inside the organization or to acquire these services from external sources.
Most organizations have core competencies in a field other than security, and limited resources must be shared across the organization for a variety of security and operational goals.

Acquiring security services from a third party offers access to two primary benefits: less expensive security capabilities, and specialized knowledge.
These benefits must be balanced against loss of control inherent in using a third party, the potential for the third party to be a target of attack, and the additional overhead of managing the third party.

#### Benefits

Pooling and sharing resources is a fundamental business concept and in fact is a main driver for the use of cloud computing services.
MSSPs perform common security functions like SOC or DFIR, where building the function, hiring the right staff, and running the service internally is typically a costly endeavor.
MSSPs frequently have advanced tools, resources, and knowledge and can share these resources among all customers. Customers of the MSSP gain a more robust security capability at a lower cost, which supports the CISSP’s objective to align security with organizational goals.

#### Drawbacks

MSSPs also present drawbacks, so the organization must make an informed decision about the use of these external security services.
As with any third party, the management of the resources is more complicated due to the indirect relationship, so strong contract language and SLA management will be required.
The MSSP typically has access to sensitive data about the organization, so data security concerns must be addressed — the risk of sharing data like the organization’s network architecture must not exceed the benefit of enhanced security capabilities offered by the MSSP.

#### Supply Chain Risk

Finally, it is not uncommon for MSSPs to be a target of attackers looking to compromise multiple organizations via the supply chain.
Many security tools, like vulnerability scanners, require privileged access to perform security functions, and MSSPs may be authorized to perform administrative functions on infrastructure they monitor.
Compromising an MSSP with 1,000 clients is a good way to gain privileged access to 1,000 organizations, so choosing an MSSP with a robust internal security program is an important consideration.

Security services that are commonly acquired from third parties include the following:

* **SOC:**
Both full or partial SOC outsourcing can be useful to deal with the cost and complexity of building and running a 24x7 SOC operation. The organization’s own SOC may be supplemented by a third party during nonbusiness hours, or entirely outsourced.

* **DFIR:**
As a natural extension of continuous monitoring, investigating incidents and collecting evidence may be included in an MSSP’s service offerings.
It may also be included as part of another tool like managed detection and response (MDR), which enhances traditional anti-malware software with analysis and remediation services.
Digital forensics requires a high degree of specialized knowledge that is not needed every day, and a third-party DFIR firm provides access only when needed.

* **Threat intelligence:**
Threat intelligence services provide useful information about threats that could target the organization and are often industry- or technology-specific.
These may be integrated into procedures like continuous monitoring and risk assessments, as well as technology like SOAR that can automate responses to known threats.

### Sandboxing

Sandboxing may be a somewhat confusing term, as it applies to a broad concept as well as specific technologies. At the most basic level, a sandbox is an isolated environment with a restricted ability to connect to resources outside the sandbox.
Examples of the term include a VM with no connectivity to other systems where researchers can execute malware without fear of infecting other systems (sometimes known as detonation).

A proof-of-concept software environment can also be a sandbox, where users may experiment without violating data integrity in a live system.

#### Software-Enforced Sandboxes

In addition to conceptual sandboxes, there are software-enforced sandboxes, which implement a restrictive set of rules to govern the behavior of an application during execution.
One example is Apple’s iOS, which sandboxes apps to restrict the data and functions they can access. Some rules are absolute, while others are configurable — apps cannot run persistently in the background, while apps can access data in other apps only with explicit user permission.

#### MDM

MDM can be added as an additional layer of security on smartphones, which extends the concept of sandboxing to containers — not to be confused with the concept of application containerization, which is covered in Chapter 8, “Software Development Security.”
MDM containers install a specific set of apps on user smartphones to allow access to organization data but restrict data access from anything outside the secure container.
These restrictions may be implemented as rules preventing file-level access to data, as well as user restrictions like preventing copy and paste or screenshot functions inside the sandboxed apps.

### Honeypots/Honeynets

A honeypot or honeynet can be useful if deployed appropriately, to detect or gather information about unauthorized attempts to gain access to data and information systems.
A honeypot appears to outsiders as a valuable resource such as a database or server but, in reality, does not contain valuable data.
However, attackers attempting to access them may be distracted or deflected from high-value targets and, by accessing the honeypot, also give up information about themselves like their IP address.

#### Legel Issues
In most jurisdictions, there are significant legal issues concerning the use of honeypots or honeynets, particularly regarding the concept of entrapment.
Entrapment describes an agent inducing a person to commit a crime, which gives the perpetrator a legal defense against responsibility for the crime.
Honeypots or honeynets should never be set up with an explicit purpose of being attractive targets or be designed to “catch the bad guys,” but instead should be passive observation tools.

Third-party honeypot services exist and provide a simple way to deploy and monitor honeypot devices. These services handle the legal challenge of dealing with honeypots and avoiding entrapment, and alerts they generate can be integrated into SIEM or SOAR tools.

### Anti-malware

Anti-malware was one of the first widespread information or cybersecurity concerns, with antivirus (A/V) software dating back to the rise of the internet and personal computing.
A/V was gradually replaced by the term anti-malware as the threat evolved from simple computer viruses to include more complex threats like Trojan horses, adware, and hoaxes or scams that combine malicious software with social engineering.

#### Defense-in-Depth

A/M software should be deployed using the defense-in-depth model to ensure traffic and activity can be scanned thoroughly to detect malicious activity.
This software can be deployed on critical resources like email servers or file shares, as well as in network monitoring tools designed to look for specific attack patterns in network traffic, such as sudden increased traffic to UDP port 1434 associated with the SQL Slammer worm.

#### EDR

The most recent evolution of A/M is driven by the recognition that any endpoint that is a device connected to a network can be targeted by malware.
This includes user workstations, routers, servers, mobile devices like tablets, and even Internet of Things (IoT) devices like home appliances.
EDR solutions are the next generation and combine A/M features with other tools like host-based firewalls, file integrity monitoring, and UEBA.
Some providers also offer services for responding to alerts or incidents detected by EDR, which is commonly sold as MDR and combines detective capabilities and third-party security service to address endpoint security risks.

#### Methods of Detection

Anti-malware, A/V, and EDR utilize a variety of methods to identify and respond to malicious software and activity on computer systems. Signature-based tools look for signatures associated with known malware, such as specific files or patterns of activity.
More complex detection may rely on statistical analysis of activity patterns, known as heuristics, to detect potentially malicious actions.
Once detected, the tool can perform actions like quarantining an affected file or system and generating an alert to the user or a centralized dashboard.
These alerts can be integrated with tools like SIEM for centralized monitoring and response, or even SOAR for the automation of incident responses.

### Machine Learning and Artificial Intelligence Based Tools

Machine learning (ML) and artificial intelligence (AI) are emerging areas of data science.
ML is concerned with improving computer algorithms by experience; for example, asking a computer to identify photos of dogs and then having a human verify which photos actually contain dogs and which contain other animals.
The algorithm learns and refines future identification; these algorithms can be used across a wide variety of applications, such as filtering out unwanted emails by observing which messages users mark as junk, and are widely implemented in security tools designed to learn and adapt to an organization’s unique environment.

AI is a field of computer science that seeks to design computer systems capable of displaying intelligent thought or problem solving, though the term is often used to describe systems that simply mimic human tasks like playing strategy-based board games or operating autonomous vehicles.
Both AI and ML require large sets of data to learn, and there are myriad security as well as privacy concerns inherent in providing your organization’s data to an outside party for the purpose of training an AI or ML model.

#### Benefits

The benefits of AI and ML in security tools include faster detection of and response to incidents, as these tools work 24x7 without needing time to sleep or take vacations.
They can also, if configured correctly, remove the element of human error from decision-making — though it is arguable whether it is even possible to configure such systems for highly complex and poorly understood security issues like handling zero-day flaws.
Applications like EDR and IDS are common implementation points for AI to enhance speed of detection and decision-making when dealing with novel threats like emerging malware.

#### Drawbacks

Another potential drawback of AI and ML is their black-box nature of decision-making, which can make spotting errors or understanding their output difficult.
The situation is similar to a complex math problem being solved without showing work — it’s impossible to identify potential errors in the solution or learn how the solution was reached.
Due to proprietary ML and AI algorithms, it may not be possible to access underlying data to analyze decisions from these tools, so taking action based on an alert may be difficult. As with any new technology, caution is warranted.
