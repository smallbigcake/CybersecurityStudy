# Asset Security

## IDENTIFY AND CLASSIFY INFORMATION AND ASSETS

The following are some of the common regulations and guidelines that formalize the classification and categorization of information assets:
* Canada: Security of Information Act
* China: Guarding State Secrets
* European Union (EU): General Data Protection Regulation (GDPR)
* United Kingdom: Official Secrets Acts (OSA)
* United States: NIST Federal Information Processing Standard 199, “Standards for Security Categorization of Federal Information and Information Systems”
* United States: NIST Special Publication (SP) 800-60, “Guide for Mapping Types of Information and Information Systems to Security Categories” (this is considered the “how-to” manual for FIPS 199)
* United States: Committee on National Security Systems (CNSS) Instruction No. 1253, “Security Categorization and Control Selection for National Security Systems”

### Data Classification and Data Categorization

#### Data Classification

Data classification is the process of organizing data into groups or categories that describe the data’s sensitivity, criticality, or value.
Data classification helps to determine the security controls necessary to manage and safeguard the confidentiality, integrity, and availability of the data, and is a cornerstone of data security and risk management.
In addition, data classification is often necessary to remain compliant with legal and regulatory requirements.

There are three primary types of data classification:
* **Context-based:**
Derived from metadata like ownership, location, or other values that can indirectly indicate sensitivity or criticality.

* **Content-based:**
Derived by inspecting the contents of files and directly identifying sensitive data, rather than inferring it from metadata.
Compliance authorities, such as the Health Insurance Portability and Accountability Act of 1996 (HIPAA), Payment Card Industry (PCI), or contract-related terms (e.g., nondisclosure agreements) involve content-based classifications, as the type of information itself drives classification.

* **User-based:**
Involves manual assignment of data classification and is based on users’ understanding of the data and your organization’s classification scheme.


##### Government Data Classifications

* **Top Secret**
The top secret label is “applied to information, the unauthorized disclosure of which reasonably could be expected to cause exceptionally grave damage to the national security that the original classification authority is able to identify or describe.”

* **Secret**
The secret label is “applied to information, the unauthorized disclosure of which reasonably could be expected to cause serious damage to the national security that the original classification authority is able to identify or describe.”

* **Confidential**
The confidential label is “applied to information, the unauthorized disclosure of which reasonably could be expected to cause damage to the national security that the original classification authority is able to identify or describe.”

* **Unclassified**
Unclassified refers to any data that doesn’t meet one of the descriptions for top secret, secret, or confidential data.
Within the United States, unclassified data is available to anyone, though it often requires individuals to request the information using procedures identified in the Freedom of Information Act (FOIA).

* There are additional subclassifications of unclassified, such as for official use only (FOUO) and sensitive but unclassified (SBU). Documents with these designations have strict controls limiting their distribution.
As an example, the U.S. Internal Revenue Service (IRS) uses SBU for individual tax records, restricting access to these records.

##### Nongovernmental Organizations

* **Confidential or Proprietary**
The confidential or proprietary label typically refers to the highest level of classified data.
In this context, a data breach would cause exceptionally grave damage to the mission of the organization.
As an example, attackers have repeatedly attacked Sony, stealing more than 100 terabytes of data, including full-length versions of unreleased movies.
These quickly showed up on file-sharing sites, and security experts estimate that people downloaded these movies up to a million times.
With pirated versions of the movies available, many people skipped seeing them when Sony ultimately released them. This directly affected Sony’s bottom line.
The movies were proprietary, and the organization might have considered it exceptionally grave damage.
In retrospect, they may choose to label movies as confidential or proprietary and use the strongest access controls to protect them.

* **Private**
The private label refers to data that should stay private within the organization but that doesn’t meet the definition of confidential or proprietary data.
In this context, a data breach would cause serious damage to the mission of the organization.
Many organizations label PII and PHI data as private. It’s also common to label internal employee data and some financial data as private.
As an example, the payroll department of a company would have access to payroll data, but this data is not available to regular employees.

* **Sensitive**
Sensitive data is similar to confidential data. In this context, a data breach would cause damage to the mission of the organization.
As an example, IT personnel within an organization might have extensive data about the internal network, including the layout, devices, operating systems, software, Internet Protocol (IP) addresses, and more.
If attackers have easy access to this data, it makes it much easier for them to launch attacks.
Management may decide they don’t want this information available to the public, so they might label it as sensitive.

* **Public**
Public data is similar to unclassified data. It includes information posted in websites, brochures, or any other public source.
Although an organization doesn’t protect the confidentiality of public data, it does take steps to protect its integrity.
For example, anyone can view public data posted on a website. However, an organization doesn’t want attackers to modify this data, so it takes steps to protect it.

#### Data Categorization

Often confused with data classification, data categorization is a closely related, but different technique.
Data categorization is the process of grouping types of data with comparable “sensitivity labels” (classifications).
According to NIST SP 800-60, “Information is categorized according to its information type. An information type is a specific category of information (e.g., privacy, medical, proprietary, financial, investigative, contractor sensitive, security management) defined by an organization or, in some instances, by a specific law, Executive Order, directive, policy, or regulation.”
By categorizing data into buckets of similarly classified sensitivity, your organization is better equipped to apply similar security controls to assets with similar sensitivities.

#### Asset Classification

Whereas data classification is focused on the identification of the sensitivity, criticality, and value of data, asset classification is more broadly related to identifying the sensitivity, criticality, and value of the information systems and assets that store, process, and transmit that data, as well as the data itself.

Asset classification begins with conducting an inventory of assets and determining the responsible people, or owners, for the assets.

#### Benefits of Classification

Because it provides valuable insight into an environment, classification is a critical first step to better and more secure asset and data management.

#### Asset Classification Levels

Assets should be identified and controlled based on their level of sensitivity. This allows similar assets to be grouped according to the value the organization places on the assets.


## ESTABLISH INFORMATION AND ASSET HANDLING REQUIREMENTS

### Marking and Labeling

Electronic assets can include markings and labels in document headers or footers, for example, while hard assets can include a physical tag affixed to the asset.

With a label in plain view, it is much easier to identify the importance of individual assets and manage the assets to assure confidentiality, integrity, and availability based on their classification levels.

### Handling

Your organization should have established policies and procedures in place that govern the handling of each category and classification of asset.
These policies and procedures provide rules for accessing, transmitting, transporting, and using sensitive data and other critical assets.

### Storage

Similar to information handling guidelines, information storage guidelines are critical to your organization’s overall asset security management.

When sensitive information was all paper-based, information storage security was as simple as keeping assets locked up and behind adequate physical barriers.
With digital information stored in data centers, on removable hard drives, on mobile phones, and in the cloud, asset storage can be a bit complicated.
In the digital age, there are too many easy ways for stored data to be stolen, leaked inadvertently because of mismanagement, or accessed by unauthorized individuals through identification credential theft.

A primary consideration for secure asset storage of digital information is encryption.

An additional consideration for secure storage is limiting the volume of data retained.

A final consideration related to data storage is backups.

### Declassification

Declassification is the process of modifying the assigned classification of an asset to a lower level of sensitivity.
As data moves throughout the data lifecycle, there may come a time when it no longer holds the same value or maintains the same sensitivity as when it was originally classified; your organization must have a process to declassify data to account for such evolution.
When data sensitivity changes from confidential to public, for example, marking, handling, and storage requirements have to be adjusted accordingly.

The declassification of assets is a process that requires thorough documentation and often multiple levels of approval.
The data owner plays a central role in this process, as they determine the classification level of the data and when it can change.

Methods to declassify assets include altering data to remove or obfuscate identifying or sensitive elements of the data.


#### De-identification

Data de-identification is the process of removing information that can be used to identify an individual (i.e., personally identifiable information (PII)).

#### Tokenization

Tokenization is the process of substituting a sensitive data element with a nonsensitive set of characters or numbers, called a token. Usually, the token has the same field length as the data that was replaced but is otherwise not meaningful in relation to the original data.


## PROVISION RESOURCES SECURELY

### Information and Asset Ownership

Within an organization, the chief executive officer or authorized delegates have formal ownership responsibility, as defined and directed by the organization’s formal governance documents, and within compliance limits of law and regulation.
This responsibility includes the authority to represent the organization for the protection and security of the information asset.

Additional responsibilities of asset owners may include the following:
* Keeping the information asset inventory up-to-date
* Identifying the classification level of the information asset
* Defining and implementing appropriate safeguards to ensure the confidentiality, integrity, and availability of the information asset
* Assessing and monitoring safeguards to ensure compliance and reporting situations of noncompliance
* Authorizing access for those who have a business need for the information
* Ensuring that access is removed from those who no longer have a business need for the information
* Continually evaluating the environment and the legal/compliance landscape to determine if changes to the above are necessary

### Asset Inventory

Any organization needs, as a foundation to its security and compliance programs, effective tools and processes to track its asset inventory.
The asset inventory includes all physical and virtual assets, including hardware, software, and data.

#### Inventory Tool/System of Record

The tool should also collect and track individual asset details necessary for reporting, audits, risk management, and incident management.
These details need to cover technical specifications, such as the following:
* Hardware
  * Manufacturer
  * Model number
  * Serial number
  * Physical location
  * Number and type of processors
  * Memory size
  * Network interfaces and their MACs and IPs
  * Hostname
  * Hypervisor, operating systems, containers, virtual images running on this device
  * Purchase date, warranty information
  * Last update dates (firmware, hypervisor, etc.)
  * Asset usage metrics
* Software
  * Publisher
  * Version number, service pack/hotfix number
  * License information
  * Purchase date
  * Install date

There are, of course, many tools available that do these tasks or portions of these tasks. Most organizations already own many such tools. Consider the following:
* An Active Directory (AD) and Lightweight Directory Access Protocol (LDAP) server can provide a large portion of this information.
* Vulnerability scanners, configuration scanners, and network mapping tools can find and provide basic information about all the hosts in the organization’s IP ranges.
* Tools that manage/track software licenses can perform a large portion of this task.
* DLP solutions typically have a discovery capability that can serve this purpose.

#### Process Considerations

First, the organization must define the authoritative inventory list or system of record and the process by which the inventory should be refreshed or updated; this includes defining an appropriate frequency for updating the inventory, although many agile organizations will do this on an as-needed basis.

In addition to the regular interval inventory updates, it is also a good practice to manually notify the inventory tool administrator when an asset is installed or removed or when the components are updated/changed in a significant way, just to verify that those changes were captured by the inventory tools.

Inventory management can be accomplished in a different way for environments that make heavy use of virtualized components, including managed cloud service implementations.

For on-premises assets, it is often helpful to augment the inventory process with the use of geolocation information/geotags or the use of radio-frequency identification (RFID) inventory tags.

### Asset Management

#### Information Technology Asset Management

Information technology asset management (also known as IT asset management, or just ITAM) is a set of business practices related to governing and managing IT assets, including hardware, software, data, and related processes.
ITAM helps an organization ensure that its assets are accounted for, maintained, upgraded, and retired when appropriate.

The International Standards Organization (ISO) has established an official set of standards related to ITAM. ISO 19770 is a family of standards, last updated in 2017, that aims to assist organizations with managing risks and costs associated with IT assets.

ISO 19770 consists of five major parts, discussed here:

* **ISO/IEC 19770-1:**
Establishes a process framework that outlines best practices and allows an organization to demonstrate compliance with an ITAM standard.

* **ISO/IEC 19770-2:**
Establishes an ITAM data standard for software identification (or SWID) tags, which provide authoritative identifying information for installed software or other licensable items. SWID tags allow your organization to uniquely identify software that’s deployed on your hardware assets.

* **ISO/IEC 19770-3:**
Provides an ITAM data standard that establishes common terminology to be used when describing software entitlement rights, limitations, and metrics.

* **ISO/IEC 19770-4:**
Establishes a data standard that supports standardized reporting of resource utilization. This standard is especially important when managing cloud-based systems or other complex assets and licenses.

* **ISO/IEC 19770-5:**
Provides an overview of ITAM and defines related vocabulary.

### Configuration Management

Related to keeping the inventory current, system and software configurations must be tightly controlled and thoroughly documented - that’s the role of configuration management.

There are two types of baselines with which you should be familiar.
* A **system baseline** identifies the versions and settings of all configuration items (CIs) in a product, system, or subsystem; system baselines answer the question “what do I need to build the system correctly?”
* A **security baseline** is a minimum set of safeguards (e.g., security controls) required to protect a given system.

A leading source that is publicly available is the **National Checklist Program (NCP)**, defined by **NIST SP 800-70**. This is the U.S. government repository for up-to-date and detailed guidance for security configurations.

A popular example in the EU is the “**Baseline Security Recommendations for IoT**” guidance that establishes a set of recommended configurations for critical information infrastructures.

### Change Management

Change management is an IT discipline focused on ensuring that organizations employ standardized processes to make changes to their assets.
Organizations must develop policies and procedures to prevent arbitrary and unexpected modifications to their hardware and software inventory.

Change management includes all activities that allow your organization to roll out and prioritize changes in a controlled manner that does not adversely impact your production environment or customer expectations.
This includes change control (which is the set of processes and tools that allow you to verify that authorized changes are implemented correctly), enforcement (i.e., prevention of unauthorized changes), verification of changes, and audit.


## MANAGE DATA LIFECYCLE

Maintaining data security requires that you understand where the data is in the overall data lifecycle.

1. **Collect:** Data is generated or aggregated.
2. **Store:** Data is saved into a storage system or repository.
3. **Use:** Data is processed and/or analyzed, by users or systems, for its intended purposes.
4. **Share:** Data is shared with authorized external users and systems.
5. **Retain:** Data is kept (e.g., archived) for a predefined period of time.
6. **Destroy:** Data is deleted and permanently removed from storage, making it inaccessible and unusable.

### Data Roles

#### Data Owners

The data owner (sometimes referred to as the organizational owner or senior manager) is the person who has ultimate organizational responsibility for data.
The owner is typically the chief executive officer (CEO), president, or a department head (DH).

Data owners identify the classification of data and ensure that it is labeled properly. They also ensure that it has adequate security controls based on the classification and the organization’s security policy requirements.
Owners may be liable for negligence if they fail to perform due diligence in establishing and enforcing security policies to protect and sustain sensitive data.

NIST SP 800-18 Rev. 1, “Guide for Developing Security Plans for Federal Information Systems,” outlines the following responsibilities for the information owner, which can be interpreted the same as the data owner:
* Establishes the rules for appropriate use and protection of the subject data/information (rules of behavior)
* Provides input to information system owners regarding the security requirements and security controls for the information system(s) where the information resides
* Decides who has access to the information system and with what types of privileges or access rights
* Assists in the identification and assessment of the common security controls where the information resides

#### Asset Owners

The asset owner (or system owner) is the person who owns the asset or system that processes sensitive data.

NIST SP 800-18 outlines the following responsibilities for the system owner:
* Develops a system security plan in coordination with information owners, the system administrator, and functional end users
* Maintains the system security plan and ensures that the system is deployed and operated according to the agreed-upon security requirements
* Ensures that system users and support personnel receive appropriate security training, such as instruction on rules of behavior (or an AUP)
* Updates the system security plan whenever a significant change occurs
* Assists in the identification, implementation, and assessment of the common security controls

#### Business/Mission Owners

The business/mission owner role is viewed differently in different organizations.
NIST SP 800-18 refers to the business/mission owner as a program manager or an information system owner.
As such, the responsibilities of the business/mission owner can overlap with the responsibilities of the system owner or be the same role.

Business owners might own processes that use systems managed by other entities.
As an example, the sales department could be the business owner, but the IT department and the software development department could be the system owners for systems used in sales processes.

In businesses, business owners are responsible for ensuring that systems provide value to the organization.

Organizations often implement IT governance methods such as Control Objectives for Information and Related Technology (COBIT).
These methods help business owners and mission owners balance security control requirements with business or mission needs.
The overall goal is to provide a common language that all stakeholders can use to meet security and business needs.

#### Data Controllers

In this context, the data controller is the person or entity that controls the processing of the data. The data controller decides what data to process, why this data should be processed, and how it is processed.

#### Data Custodians

Data owners often delegate day-to-day tasks to a data custodian. A custodian helps protect the integrity and security of data by ensuring that it is properly stored and protected.

#### Data Processors

Generically, a data processor is any system used to process data.
However, in the context of the GDPR, data processor has a more specific meaning.
The GDPR defines a data processor as “a natural or legal person, public authority, agency, or other body, which processes personal data solely on behalf of the data controller.”

#### Administrators

You’ll often hear the term administrator(s). However, the term means different things in different contexts.
If Sally logs onto the Administrator account in a Windows system, she is an administrator.
Similarly, anyone added to an Administrators group in Windows is also an administrator.

However, many organizations view anyone with elevated privileges as administrators, even if they don’t have full administrative privileges.
For example, help desk employees are granted some elevated privileges to perform their job but aren’t granted full administrative privileges.
In this context, they are sometimes referred to as administrators.

In the context of data roles, a data administrator may be a data custodian or someone in another data role.

#### Data Users

A user is any person who accesses data via a computing system to accomplish work tasks. Users should have access only to the data they need to perform their work tasks.
You can also think of users as employees or end users.

#### Data Subjects

A subject is any entity that accesses an object such as a file or folder. Subjects can be users, programs, processes, services, computers, or anything else that can access a resource.

The GDPR defines a data subject (not just a subject) as a person who can be identified through an identifier, such as a name, identification number, or other means.
As an example, if a file includes PII on Sally Smith, Sally Smith is the data subject.

### Data Collection

The data lifecycle (refer to Figure 2.5) begins with data collection.
This phase may include data creation, acquisition, aggregation, or any circumstance where data is “new” to your system.
New data may be freshly generated content, data that is newly introduced to your environment, or content that has been updated/modified into a new state.

One of the easiest ways to prevent the loss of data is to simply not collect it.
The guideline is clear. If the data doesn’t have a clear purpose for use, don’t collect it and
store it. This is also why many privacy regulations mention limiting data collection.

### Data Location

With the growth of cloud-based storage, data location is an increasingly discussed topic.
Many jurisdictions or governments have laws that require a citizen’s (or resident’s) data be collected, processed, or stored inside the country.
The data may still be transferred internationally, but it has to originate from the country and can be transferred only after local privacy or data protection laws are met.

An example of these conditions is notifying a user how the information will be used and obtaining their consent. This is data localization or residency before the data is exchanged outside of the jurisdiction.
In some cases, data localization or residency mandates that data about a nation’s citizens or residents must be deleted from foreign systems before being removed from systems in the data subject’s nation.
Some regulations prohibit certain data (like military secrets, for example) from leaving the country of origin under any circumstances.

With the use of a cloud provider, data localization or residency highlights several important considerations, including knowing where your data will reside (or where it might travel) and the contractual obligations the cloud provider has to support the data owner’s requirements.
Data localization or residency is another valid reason to mandate that the data controller holds the encryption keys to cloud data stores.
If the nation requires international organizations to destroy data before the nation does, deleting the encryption key can be a compensating control to make sensitive data unreadable and unusable.

Data location refers to the location of data backups or data copies. Imagine a small organization’s primary business location is in Norfolk, Virginia. The organization stores all the data on site. However, they regularly perform backups of the data.

A best practice is to keep a backup copy on site and another backup copy off site. If a disaster, such as a fire, destroys the primary business location, the organization would still have a backup copy stored off site.

The decision of how far off site to store the backup needs to be considered.
If it’s stored in a business located in the same building, it could be destroyed in the same fire.
Even if the backup was stored 5 miles away, it is possible a hurricane or flood could destroy both locations.

Some organizations maintain data in large data centers. It’s common to replicate this data to one or more other data centers to maintain the availability of the critical data.
These data centers are typically located in separate geographical locations.
When using cloud storage for backups, some organizations may need to verify the location of the cloud storage to ensure it is in a separate geographical location.
