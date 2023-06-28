# Identity and Access Management

**IDENTITY AND ACCESS MANAGEMENT (IAM or IDAM)** is fundamental to information security.
Controlling access to resources requires the ability to identify and validate the entities requesting access and to hold them accountable for the actions they take.
Entities can be users, systems, applications, or processes, and IAM consists of four foundational elements: identification, authentication, authorization, and accountability (IAAA).

## CONTROL PHYSICAL AND LOGICAL ACCESS TO ASSETS

**Physical access controls** should be familiar to virtually all readers — doors, curtains, fences, etc., are common everyday objects used to control physical access to buildings like homes, schools, and office buildings.

**Logical access controls** are similarly omnipresent, though they are not always as obvious to the untrained eye. Systems that require a password, personal identification number (PIN), or shared symmetric key for access are all examples of logical access controls.

Both logical and physical access measures are designed to restrict which users or systems can access specific assets like data in a system or valuables stored in a safe.

### Access Control Definitions

Access control models use a standard set of terms to discuss various concepts. These include the following, which are used throughout the remainder of this chapter:
* **Objects** are assets that require access control. Common objects include information like files or datasets as well as system objects like compute resources and networks.
Physical access control models deal with facilities as objects, such as office buildings, computer rooms, and sensitive information handling facilities.
All objects share a common need for protection of basic security attributes including _confidentiality, integrity, availability, nonrepudiation, and authenticity (CIANA)_.
* **Subjects** can be human users or nonhuman entities like systems, processes, and devices. Subjects require access to objects like files, systems, and facilities, and the fundamental practice of access control defines how such access is granted, used, and monitored.
* **Access** is anything a subject is permitted to do with or to an object.
For example, a human user can be allowed or denied entry to a facility, a system user can be allowed read access but denied write and update access to a file, and nonhuman users like system processes can be allowed or denied access to specific data objects based on the sensitivity level of the objects in question.
Important concepts related to controlling access including authorization are discussed throughout this chapter.

### Information

Information is typically an object in an access control model, and access control systems are designed to restrict access based on the credentials presented by a subject.
The most obvious example is to preserve confidentiality - a system verifies a user’s credentials before granting access, which prevents unauthorized users from gaining access to data.

### Systems

System is a term that can be difficult to define. Any collection of hardware, software, personnel, policies, procedures, and other resources may constitute a system, though the term is usually used to discuss electronic information systems.
A security practitioner must understand the functions and objectives of the systems in use at their organization, as well as components like analog processes, hard-copy data, or electronic elements of the system, to design appropriate identity and access management controls.

Systems requirements may demand multiple security objectives, such as confidentiality, availability, or integrity of critical information, availability of the system itself, or authenticity and nonrepudiation of the system’s users.
Proper implementation of access controls, particularly within information systems where sensitive data and information objects exist, is a fundamental task for a CISSP to perform.
Access controls are vital for both security and privacy of data and support the basic security concepts of CIANA, which are covered in Chapter 1, “Security and Risk Management.”

Common ways that the CIANA concepts can be implemented in system-level IAM include the following:
* **Confidentiality** requires information in a system to be kept secure from unauthorized access.
Physical access controls at the facility level will be important, as will system-or component-level restrictions for both physical access controls, like a locked safe, and logical access controls, like full disk encryption (FDE).
* **Integrity** can be supported via access controls by preventing unauthorized users from making changes to information.
* **Availability** controls and integrity controls often share a common implementation; for example, locked server cabinets prevent unauthorized users from maliciously or accidentally shutting down a system.
This can prevent data loss or corruption as well as loss of system availability.
* **Authenticity** leverages the use of authentication in IAM to prove the information, commands, or other information in a system can be trusted.
It may be possible to make a decision about the trustworthiness of the subject or any data they supply, provided they have successfully proven an identity.
* **Nonrepudiation** shares commonality with authenticity. Nonrepudiation means a user or system is prevented from denying a specific action, and requires the IAM system to implement sufficient accountability to prove the action was taken by the specific subject.
This rests on the ability of the IAM system to uniquely identify and authenticate subjects, as well as logging of system actions and identifying information.

**Centralized IAM** administration uses a dedicated access control function, like a team or specific department to manage all access control, which offers the advantage of very strict oversight and monitoring.
Centralized IAM has the disadvantage of a single point of failure.

**Decentralized IAM** administration breaks the function out and typically assigns access control decisions to system or information owners.
This can offer greater freedom and flexibility, with the potential downside of inconsistent enforcement and lack of unified oversight.

### Devices

Devices are components of an information system, as well as systems themselves, and therefore they require adequate IAM.
User workstations including laptops, desktops, and tablet computers are all full information systems with storage, processing, and networking abilities, and these capabilities create the need for appropriate security controls like restricted logical access.
The increased use of cloud computing services to store and process data has also increased the number of devices that an organization must consider, since these services can be accessible from any internet-connected device.

#### IAM for Devices

A primary concern for device IAM is ensuring access is restricted to only authorized users. The explosion of new device types accessing data has led to IAM challenges, such as early smartphones that supported only four-digit PINs instead of complex passwords.
The rapid evolution of these devices has also offered security benefits such as the commoditization of biometric sensors like fingerprint readers and facial geometry scanners.
The lower cost and better effectiveness of these devices means they can be incorporated into a broader variety of systems, which provides additional options for multifactor authentication (MFA).

One element of effective IAM for devices is proper endpoint security. It is essential that access controls be applied with respect to the security of these devices.
For example, an asset inventory maintained in a mobile device management (MDM) system should indicate the owner, primary user, or custodian of each device. This supports incident response capabilities in the event a device is compromised.

#### Devices as Subjects and Objects

Devices can be both objects and subjects in an access control model. If they contain sensitive data or grant access to sensitive functions, then it is important to control access to the device objects.
Devices can also be treated as subjects or nonhuman users; a known workstation can be identified by a device fingerprint, digital certificate, cookie file, or the like.
When the device attempts to gain access to sensitive objects, these identifiers may be presented to authenticate the device.
If a new, untrusted device is used to sign in, the access control system should be configured to require additional authentication, such as MFA, before the device is granted access.
This concept is applied in network access control (NAC), which treats devices as objects and applies additional criteria to new devices joining a network.
For example, a user’s personal laptop may be placed in a quarantine network until its patch level and EDR software can be verified.

#### Modern Device Challenges and Solutions

The portability of many modern computing devices also poses a challenge to confidentiality. Devices like laptops, tablets, smartphones, and even some powerful desktop computers are now small and light enough to be carried easily.
This means they are vulnerable to being stolen, misplaced, or even accessed without the user’s knowledge if a device is left unattended. Tools like MDM can counter risks to these devices and the data they contain, with features like these:
* **Device protection:**
This enforces security policies on each device, including password complexity, software updates, and restricting what apps can be installed or used.
EDR software can also be useful to identify suspicious or malicious activity and engage additional protections like quarantining, locking, or wiping a device.

* **Device restrictions:** This identifies hardware that is not supported or systems that have been jailbroken, which removes standard restrictions on the device and its operating system.
Jailbreaking a device also removes standard protections imposed by the manufacturer, which can lead to unauthorized data access.

* **Remote lock or wipe:** If a device is reported stolen/missing, this allows the organization to prevent unauthorized users from gaining access.
Remote lock can be reversed if the device is found, while remote wipe may either delete all data or render the device unusable; it is usually only used in situations where the device cannot be recovered.

* **Containerization:** Placing organization data into a logical contain isolates it from being accessed by other apps on the device.
This is a common choice for organizations with a bring your own device (BYOD) policy that allows users to access organization resources from a personal device.
Enforcing restrictions on the personal device may be difficult, so the restrictions are instead limited to the container, which can be locked or wiped if the user loses the device or leaves employment.

#### Physical Access Controls for Devices

Physical access controls are a key element of device security controls. In a typical office environment, the organization’s physical access controls provide shared protection for all devices inside the facility.
Portable devices present a challenge because the devices often leave the secure facility.
In this case, appropriate policies and training must be provided to users of the portable devices, such as never leaving them unattended in public places, or securing the devices in an unmarked bag or hotel safe when traveling.

### Facilities

Facilities provide shared security for all the systems, devices, and information they contain, so ensuring adequate protections is vital.
Physical security is particularly important when discussing information system security - if an attacker is able to gain physical access to a device, then even the best logical security controls may not be sufficient to prevent unwanted data access.

Traditional facility physical security measures often follow a secure perimeter paradigm, with layered defenses that provide increasing levels of security.

#### Physical Access Control Systems

Physical access control systems (PACSs) include physical security implementations like gates, fencing, turnstiles, security badges, and guards.
They also include administrative procedures required to operate these controls, such as guard surveillance schedules, badge requirements, loading dock procedures, and visitor registration and escort.

When designing a PACS, it is critical to establish requirements for protection, as making changes to physical infrastructure is more difficult than changes like software upgrades.
The first requirement that must be identified is who exactly needs access to a specified facility.
Functional areas like computer rooms or wiring closets may require only limited, infrequent access, which makes the tasks of implementing physical security easier due to the small population of users.
Other facilities, particularly office buildings, will have more complex access requirements as more individuals require access and the use of such facilities by visitors or business partners may be common.

Once the requirements for access have been determined, a PACS design can be developed and implemented.
The complexity of the controls chosen must reflect the value of the assets being protected — a facility with no sensitive data or assets is unlikely to require 24/7 guards and advanced intrusion detection sensors.

Elements might include one or more of the following:

* **User identification:**
People, vehicles, and other resources entering or leaving a secured area should be identified. This may be accomplished via a badge, sticker, radio frequency ID (RFID) tag, barcode, etc., as appropriate.
Human beings will typically be identified with an ID card, sticker, or badge, while vehicles or deliveries may be identified with RFID tags, barcodes, or Quick Response (QR) codes.

* **Device identification:**
Nonhuman users may be tracked throughout the facility or at ingress and egress points using a variety of methods including identification stickers and RFID tags.
This allows for tracking and controlling the flow of assets entering and leaving the facility and may be integrated with property and asset management systems.

* **Fences and gates:**
Fences can prevent unwanted access or be designed to guide people to a controlled entry point, depending on the sensitivity of the facility.
Gates offer the ability to implement additional checks, such as presenting an ID badge or entering a code, where identification and authentication occurs.

* **Secured doors:**
Similar to gates, a secured door offers the opportunity to make an access decision — unauthorized users are denied access, while those who can present proper credentials are granted access.
This could be done by presenting some form of ID or an authorization token like a smart card, smartphone app, or PIN code.

* **Locks and keys:**
Although often implemented on gates or doors, locks can also be used to control physical access to individual assets such as hard-copy data in a filing cabinet, a sensitive laptop stored in a safe, or a locked server rack housing sensitive systems.
Locks may be analog and require possession of a key or knowledge of a code to control access. Digital locks can provide unique identification of multiple users by requiring knowledge of a unique code or by utilizing biometrics.

* **Intrusion detection sensors:**
These are a detective control and can be useful to identify if improper access has been gained.
Examples include heat (infrared), sound (sonic), and weight or pressure sensors, which can detect an intruder based on body heat, sounds like breaking glass, or movement as the intruder walks about.

* **Turnstile or mantrap:**
Turnstiles and mantraps are both designed to explicitly limit the rate of access to a facility.
Turnstiles typically allow only one person through at a time, while a mantrap requires a user to enter a secure vestibule space by presenting one set of credentials and then requires a different set of credentials to move from the vestibule into the main space.
These can be useful to guard against piggybacking, where one user attempts to gain access without presenting credentials by closely following an authorized user.

* **CCTV surveillance:**
Video surveillance can serve multiple control functions. The presence of video cameras may be sufficient to deter or prevent some unwanted access, and footage captured can be used to detect and respond to situations.
closed-circuit television (CCTV) footage typically requires review by a human for effectiveness.
However, recent advances in artificial intelligence (AI) have provided the ability for cameras to detect motion or even specific objects like animals or people, which can be used to perform continuous monitoring and generate more intelligent alerts.

* **Guards:**
Guard staff are one of the most useful, flexible, and also most expensive forms of physical access control.
Unlike technology systems that can only follow programmed responses, guards can respond dynamically, can think critically, and can mobilize to an incident location if needed.
However, guards also incur additional costs that technology systems do not, such as benefits, time off, and an inability to work continuously.

##### Emergency Considerations

Emergency considerations must also be taken into account when designing a PACS, since human life, health, and safety are always a primary concern.
The goal of the PACS under normal circumstances is to restrict physical access; in an emergency such as a fire or workplace violence situation, access controls should be designed to allow quick and efficient egress.
Secured doors may be integrated with fire detection systems and designed to fail open in the event of a fire alarm or may be equipped with an override that allows the door to open but also sets off an alarm.

#### An Expanded Definition of Facilities

A combination of forces has created a new definition of what an organization’s facilities comprise.
Rather than servers in a computer room communicating with an organization-controlled desktop workstation, a cloud service provider (CSP) and personally owned smartphones are the new “office” many organizations need to protect.
Ensuring physical security for assets outside the organization’s control is virtually impossible, so alternative, compensating controls may be required in place of a PACS.

##### Training for Device Users

As discussed in Chapter 1, asset owners and custodians share responsibility for proper security measures. Users are the owners of BYOD or personal devices used for work purposes, and custodians of organization-owned assets assigned to them for use.
Training on proper security procedures for these devices should be mandatory for all users who are either owners or custodians.
This training should cover common security measures like maintaining physical control over the devices, never leaving them unlocked or otherwise accessible when unattended, and preventing access by unauthorized parties to sensitive resources.

##### MDM and MFA

MDM and MFA can be combined to provide powerful compensating control for challenges arising from increased remote work, cloud-based systems, and BYOD. Traditionally, a user and the device they connect from were both considered to be trusted.
The emerging paradigm of zero trust means that no users, devices, or processes are considered trusted; instead, all access must include proper authentication and may require the requesting party to meet certain criteria.
MFA allows the organization to gain greater assurance about the entity requesting access, and MDM can be used to enforce security policy restrictions such as the use of a complex passcode or encryption on a user device.

##### Identity Federation

Identity federation is also driving changes to the definition of facilities. Users in a federated identity system will not all belong to the same organization and are unlikely to work in the same facilities.
In addition to the technical implementation of federated identity, which is discussed later in this chapter, the security practitioner should ensure that supply chain risk management practices are applied to any third parties sharing identities via federation.

##### Cloud Services

Expanded use of cloud services is also driving IAM evolution.
Organizations using cloud services share control over the data and systems in the cloud — the CSP is always responsible for physical security and aspects of logical security related to infrastructure, while the organization is always responsible for controlling logical access to its data in the cloud.
Organizations moving to the cloud lose the capability to design, implement, and manage the physical and logical controls owned by the CSP.

##### Risk Assessment and Compensating Controls

Migrating to the cloud typically involves significant IT cost savings; a CISSP should ensure that risk assessments capture the increased risk inherent in this loss of control and that adequate compensating controls are in place.
Compensating controls might include increased logging and oversight of activity, use of only approved CSPs or specific services at a given CSP, and additional data encryption prior to storage in cloud applications with organization control of the encryption keys.
If the cost of the compensating controls is greater than the cost savings from migrating to the cloud, then it makes sense for the organization to instead pursue its own hosting.

### Applications

Access to applications must be granted based on sound access management principles, like need to know and least privilege. Applications provide access to data, and designing an IAM strategy for them should consider access from the following perspectives:

* **Access to applications:**
Not all users will require access to all applications in use at an organization — members of the sales team are unlikely to need access to Human Resources (HR) applications, while members of the HR team do not need access to internal accounting applications.
A role-based access control (RBAC) model can be helpful in identifying common need-to-know criteria and granting access that is appropriate but not excessive.

* **Access by applications to specific data:**
Access controls can be utilized to enforce restrictions on how data flows between applications. This is especially relevant in MDM where containerized apps are deployed to users’ personal devices.
These apps are logically isolated from other apps on the device, preventing unmanaged, unauthorized apps from gaining access to organization data.

* **Access within applications:** Applications typically offer multiple levels of user access, such as regular user and superuser or admin access.
Large applications may also contain multiple datasets, like a document management system with unique folders for each project or department.
Granularity describes the level at which access can be controlled — an application with high granularity supports tailoring each user’s access to specific objects, while an application with low granularity allows only a basic allow/deny to the application and all data it contains.
Inadequate granularity can cause a loss of security if a user, even an internal, nonmalicious one, gains unauthorized access.


#### Applications as Subjects and Objects

Applications can be treated as subjects in an access control system as well. They are nonhuman users who access other systems, applications, and data.
This access often occurs without direct oversight from a human user, such as scheduled jobs or batch processes that run automatically.

Applications may also be objects in access control, with a variety of needs for controlling access. The ability to run an application often permits access to data, so any subjects accessing the application have access to that data.

The application itself can be a valuable object, since access may require a license. Managing licenses and users with access to all applications in use can be a full-time job in larger organizations.


## MANAGE IDENTIFICATION AND AUTHENTICATION OF PEOPLE, DEVICES, AND SERVICES

All IAM systems must implement four crucial elements: identification, authentication, authorization, and accountability (IAAA).
Creating user identities, granting them permissions on systems, authorizing users when they log in, and performing oversight of user actions all rely on adequate controls being implemented in IAM systems.

**Identification** is the process of a subject, like a user, system, or process, asserting an identity. This is often done by supplying a digital username or user ID, but may also utilize physical credentials like an ID card.
It is important to note that identity management is a unique process that begins even before a subject attempts to access an object, and the process of identity management is covered in more detail in a later section.

**Authentication** is the process of proving the asserted identity, which the subject does by supplying some information they are in control of. Factors that can be used for authentication include something a user knows, something a user has, or a measurement of something the user is.
These are known as factors, and examples include the following:
* **Type 1:** This is something the user or entity knows, like a password, passphrase, or the answer to a security question.
* **Type 2:** This is something the user or entity has possession of, such as a preregistered mobile device or physical key card.
* **Type 3:** This is a measurement of one of the user’s biological characteristics, such as hand geometry, fingerprint, iris scan, or facial geometry.
* **Type 4:** This is an emerging area of authentication, and formal definitions may vary.
Access control systems can take into account details of how and where a subject is trying to authenticate from, such as whether the access is from a previously used device or a new device.
Policy-based access controls can provide various authentication paths depending on this information such as if the user is on a known, trusted device then they are only required to provide a username and password.
If the access is from a new device or location, then an MFA prompt is generated.

**Authorization** is a two-part concept. When an identity is created during provisioning, it must be granted access or permissions, which is an authorization action.
Each time the subject makes requests for access, the system should again confirm authorization to ensure the subject is still authorized to access the given object.

Additionally, systems should enforce **accountability** for system actions taken by a subject, which is often done by logging the actions for review.

### Identity Management Implementation

Identity management (IdM) systems are useful not only for managing the identities for user access, but the identities they manage enable the functions of authentication, authorization, and accountability as well, since these rely on a proven identity.
Functionalities of an IdM can be provided by a standalone system or may be integrated with a larger IAM tool. These functions support critical tasks throughout the access management lifecycle and can include one or more of the following:

* Provisioning:
The IdM tool may provide a method for initiating the access management lifecycle by requesting identity creation, as well as supporting access request review and approval processes.
Requests may be initiated by a variety of parties, including the user, the user’s manager, or even an HR department, depending on the IAM model implemented within the organization.

* Deprovisioning:
Similar processes for deprovisioning users should also be supported by the IdM; requests to deprovision may be initiated by an access reviewer, HR, system owner, or the like.
Deprovisioning actions can include suspending the user’s account temporarily, as in the case of a leave of absence, or permanently if the user is retiring. Other actions may include deleting or disabling the identity.
The choice of action should be driven by requirements for accountability — disabling a user account prevents the same identity from being reused in the future and possibly causing confusion if historical logs are needed.

* Identity and account management:
The IdM can support centralized and decentralized functions for account management, such as password resets through a centralized authority (help desk) or decentralized service (self-serve).

* Authorization management:
Once an identity is created, the IdM supports the initial authorization of access for the identity. For example, once a user account is created, it can be placed into a group that has specific permissions assigned.

* Identity review:
IdM supports oversight of identities and access by providing key details about the authorizations that are granted to an identity. This list of accounts and access forms the basis of an access review — all current access is reviewed for appropriateness and deprovisioned if no longer needed.

IdM supports additional functions like identity federation, discussed elsewhere in this chapter, and single sign-on (SSO), which is an example of a feature that can offer both security and operational benefits.
In an SSO environment, users are required to authenticate only once, possibly to an SSO portal or to a primary application like webmail. From there, access is granted to other resources by sharing a token generated by the initial authentication action.
This offers a security benefit by reducing the number of passwords a user must remember, thereby reducing the likelihood the user will write down or choose bad passwords. The user benefits as well by having fewer passwords to remember.

Despite the benefits offered, SSO can also be a single point of failure in one of two ways. First, if the SSO is offline or unreachable, access to all SSO-enabled applications is also unavailable.
Second, if a user’s identity is compromised, the broad access granted through SSO is magnified — by contrast, in a non-SSO environment, if a user’s identity is compromised, it grants access to only one system.

Interestingly, this same capability makes recovering from an identity compromise easier, because an attacker using an SSO identity can be locked out of all systems once.
Balancing benefits against potential risks of an SSO is a key task for a security practitioner when choosing an SSO. Specific benefits and drawbacks of various SSO solutions are discussed later in this chapter, including Kerberos and Open Authorization (OAuth).

### Single/Multifactor Authentication

Authentication requires supplying information that proves the validity of an asserted identity; that is to say, the user truly is who they claim to be.

There are three types of authentication factors, which are differentiated by what they utilize to prove the asserted identity.
These include something the user knows (Type 1), something the user has (Type 2), or a measurement of something the user is or does (Type 3).

#### Single Factor

Single-factor authentication requires just one factor to verify an identity. The best known example is the username, which is the identity, and a password, which is a Type 1 authentication factor.
Virtually all systems support this combination, and users are well accustomed to using these when logging in.

#### Multifactor

Multifactor authentication, as the name implies, requires the use of more than one authentication factor such as a username, password, and a randomly generated code from an authenticator app.
In this example, both Type 1 and Type 2 authentication factors are utilized, so this is two-factor authentication (2FA).
A system that requires a username, an authenticator app code, and a fingerprint is truly MFA, as it requires all three authentication factors.

MFA is useful to guard against account compromises like phishing attacks. Simply stealing a user’s password is not sufficient, and the extra work to steal the additional authentication can make the attack less feasible or even impossible.
The more information a user can provide to authenticate, such as a password and a code from an authenticator app on a trusted smartphone, the more trust a system has that the user is legitimate.

As with other security technologies, there is a requirement to ensure balance between security and usability objectives — requiring a user to open a smartphone app and type in a code every time they log in could become burdensome.
In a facility where the organization can implement physical access controls, the risk of unauthorized access may be partially mitigated, meaning MFA could be required only once a day when a user first logs in.
For users on mobile devices working from facilities outside the organization’s physical control, more frequent MFA might be appropriate if the data or systems being accessed are sufficiently sensitive.

Sophisticated phishing attacks have been conducted in which a fake website is set up for users to log into with their username, password, and the randomly generated authenticator code from a smartphone app.
Since these codes expire quickly (often 90 seconds or less), these sophisticated attacks rely on automation. The captured credentials must be used immediately on the legitimate website for the attackers to gain access.

#### Type 1 Authentication Factors

Type 1 authentication factors are something the user knows, such as a password, PIN, or the answer to a security question.
Kowledge-based authentication is widely understood and accepted; passwords, passphrases, secret words, or similar are widely used in everyday life.

Passwords or passphrases are a common Type 1 authentication factor, and most operating systems, applications, and information systems support their use.
Although widely accepted, there has been a recent paradigm shift in guidance for password security practices.

##### Password Security Guidance Paradigm Shift

Previous guidance, which was largely based on National Institute of Standards and Technology Special Publication (NIST SP) 800-63, will be familiar to both security practitioners and everyday users.
So-called strong passwords should be at least eight characters, be changed frequently, and contain a mix of uppercase, lowercase, special, and numeric characters.

While this guidance was sound at a time when attackers employed largely manual means when attempting to circumvent access controls, in the era of cheap, high-powered computing hardware, it is demonstrably inadequate.
The NIST SP 800-63 series of documents now contains guidance for managing digital identities, federating IdM, and authentication factor management.
This updated guidance, specifically 800-63B, “Digital Identity Guidelines, Authentication and Lifecycle Management,” applies a risk-based approach to managing authentication factors.

This includes Type 1 factors, with specific guidance:

* **Emphasis on usability over complexity:**
Requirements for complex passwords or passphrases lead to passwords that are difficult to remember, but easy for attackers to guess, like using a base word with changing numbers at the end like “password123” and “password 246.”
Updated guidance emphasizes allowing longer passphrases of common words without added complexity requirements, and more generous input attempts to account for a user mistyping.

* **Increased length over complexity:**
Systems that implement passphrases over passwords are preferred, as they create more easily remembered authentication material. An example passphrase might be “RiskBasedSecurityIsTheFuture” in contrast to a complex password like “r!skB@s3d.”
The former is easier for a user to remember, while the latter is likely to result in more unintended user lockouts.

* **Less frequent changes:**
Updated guidance requires password changes less frequently due to their increased complexity. A passphrase is harder to guess or crack, so current guidance requires changing it only if it has been compromised.

##### Weaknesses of Type 1 Authentication Factors

All Type 1 authentication factors share common strengths and weaknesses. Since they rely upon users to remember the secret information, they can be ineffective if a user has forgotten the secret.
When used for system accounts where a program or script has the password stored, forgetting the information is not a concern; instead, a compromise of the authentication factor is the primary weakness, since a computer system is unable to determine if a valid user is supplying the password or if the information is supplied by an attacker who has compromised the authentication information.

##### Password Managers

Although current password guidance places an emphasis on usability as well as security, many organizations and individuals find themselves with a multitude of passwords to create and manage.
SSO can help in some cases, but a password manager is also an important tool.

A password manager is a software application that can manage authentication material like passwords, passphrases, and answers to secret questions. These tools offer support across desktop and mobile operating systems and can serve to offload the work of creating, remembering, and filling in passwords.
When a user signs up for a new web application, service, or app, the password manager automatically creates a new random password, which is automatically saved in a vault.
When the user logs in to the web application again, the password manager automatically supplies the password. Instead of remembering passwords for each service they have signed up for, the user is only required to remember the password needed to unlock their vault.

Password managers support good password hygiene by removing the need for users to create passwords manually, which often results in the creation of bad passwords, such as “MyPasswordServiceName,” where ServiceName is replaced by the name of the service the user is signing up for.
In this case, a user’s password to other services can be easily guessed by simply replacing the service name when trying stolen credentials on another web application or service.

Password managers can also be used for important organizational functions such as password backup, recovery, and escrow, which allows administrators to retrieve passwords and gain access in the event a user is not available.
The ability to access another user’s credentials is risky due to the probability that it could be abused, so most password managers implement this ability as a centralized administrative function with additional auditing available.

#### Type 2 Authentication Factors

Type 2 authentication factors are something the user has, such as a digital certificate, identification badge, or smart card. Trusted devices are also an increasingly popular Type 2 factor, as portable computing devices have become ubiquitous.
Physical authentication tokens and smartphone-based authenticator apps are also popular Type 2 factors.

These provide additional authentication information in the form of a numeric code that the user must enter during login, further proving the authenticity of their asserted identity — only the specified user should have knowledge of their password and access to the authenticator token or app.

The use of trusted device authentication factors can be static or dynamic. A static example is an organization-issued workstation that is provisioned with a digital certificate used to log on to a virtual private network (VPN).
During login, the user must provide their password, and the VPN client also provides the certificate for verification. While not foolproof, this approach reduces the usability of stolen user credentials and reduces user friction, or the difficulty users encounter when using the system.

If the VPN requires a password and token code at each login, the user must remember to keep their token with them at all times. Storing a second authentication factor on the device reduces the workload for the user while also achieving a security objective.

##### Advantages and Disadvantages of Type 2 Authentication Factors

Unlike Type 1 factors, there is no requirement for users to remember information related to Type 2 factors — a user who changes a password right before leaving on vacation may struggle to recall it, but using an authenticator app does not pose the same issue.

However, some Type 2 factors do require the user to remember to physically bring a device, such as a token, smart card, or trusted smartphone.
If the device is lost or stolen or requires power but has a dead battery, as in the case of a smartphone authenticator app, the user cannot authenticate successfully.

##### Safeguarding Type 2 Authentication Factors

Safeguarding the confidentiality and availability of the physical devices is an important security consideration if they are used.
Users should be trained in adequate security procedures related to these devices, such as maintaining physical control over them and reporting immediately if a device is lost or stolen.
It is also important to have incident response scenarios and procedures defined to deal with these issues related to Type 2 authentication factors.
Help desk personnel should be trained on how to handle a lost or stolen smartphone or authentication hardware, and adequate technical controls like a central console to deregister or deauthorize these devices must also exist.

##### Unsecure SMS and Email

The use of SMS and email to deliver one-time passwords (OTPs) or two-factor authentication codes is not considered a security best practice, since both email and SMS are not secure delivery methods. Wherever possible, alternatives should be used.

##### Conditional MFA

Dynamic trusted device authentication can also be used to both increase security and provide greater usability. This is known as conditional MFA and is a key element of attribute-based access control (ABAC), which relies on a set of policies to make authentication decisions.

If a user logs in on a previously unseen device at a new IP address, there is an increased likelihood this event is suspicious. For example, perhaps an attacker has successfully phished credentials.
In this circumstance, additional authentication is a wise precaution, so a second authentication factor is required to prove the user’s identity.
If the user can successfully authentication, as software token such as a cookie is placed on their device and submitted with future logins to reduce the overhead on the user.

#### Type 3 Authentication Factors

Biometrics are measurements of a human user and are often referred to as something you are or do. The uniqueness of human physiological characteristics or behavior allows these to be used to prove an identity.
These include measuring geometry of body parts by scanning, like with facial or fingerprint recognition, recording and comparing speech samples, or even monitoring the rhythm and cadence of the user typing a sample text like a passphrase.
Type 3 authentication is not often used as a single factor but is often used as a second or third factor for MFA.

Biometrics provide one of the strongest methods to prove authenticity of an identity, as the characteristics measured are highly unique — only a small number of people in the world will have significantly similar fingerprints or retinas.
Sophisticated biometric systems can also detect fake credentials, though all systems are subject to compromise or being spoofed, and some are subject to flaws or biases, such as facial recognition systems that have difficulty distinguishing users of certain ethnicities or skin colors.

Additional weaknesses of biometrics include the following, which require the security practitioner to balance the needs for authentication and acceptance of a biometric solution:

* **Cultural acceptance:**
Although not invasive, biometric scanners do require visible skin and public access to body parts that may be culturally unacceptable.
An exterior door that requires facial scans will be problematic in a country where facial coverings are common, so security practitioners must balance user and cultural requirements when designing authentication schemes.

* **Accessibility:**
Disabled users may have difficulty using biometric systems or even lack the needed body parts — a user who is missing a right hand will not be able to utilize a hand geometry scanner that supports right-hand scans only.
The use of biometrics also introduces concerns of disease transmission; if users must put body parts in contact with the scanner, the proper sanitization must also be considered.

* **Body changes:**
Over time, some of the characteristics used for biometric authentication may change, such as a user losing their voice due to an illness, eye degeneration, or diseases that can change physical characteristics.
The biometric system must support a way for users to update their authentication information if this is the case, as the changing biometric will cause false rejections.

* **No easy way to change:**
Unlike Type 1 and Type 2 authentication factors, users do not have an easy way to change biometrics if the authentication system is compromised. It is not possible for human beings to easily change physical characteristics like fingerprints or facial geometry.
These systems should always be classified as containing personally identifiable information (PII), since biometrics can be used to uniquely identify individuals. The choice to use such a system introduces additional risks due to the type of data it will store and process.

##### Weaknesses of Biometrics

There are many issues related to the use of biometrics, including the relative difficulty of maintaining their secrecy. Human beings cannot easily prevent their fingerprints from being left on physical objects, and high-quality photographs are nearly ubiquitous due to social media and surveillance.
An important test for biometric systems is their ability to determine the “liveness” of a subject or whether the biometric data being presented is from a live human being or a reproduction like a photograph.

#### Common Access Control Errors

Authentication systems can suffer errors of either false rejection or false acceptance. False rejection occurs when a system denies access to a subject that is properly authorized, while false acceptance occurs when a system grants access to a subject that is not authorized.
Access control systems can be measured for how frequently they exhibit these errors, and the measures are known as **false rejection rate (FRR)** and **false acceptance rate (FAR)**, also known as **Type 1** and **Type 2 errors**.

Access controls, like all security controls, incur costs to implement. More expensive systems may offer additional features, while adding more steps to user logins can decrease productivity as users spend more time performing security actions.
A more costly system may include more sensitive authentication mechanisms like biometric sensors that increase FRR.
By contrast, a cheaper system with a less-sensitive biometric mechanism might suffer from higher FAR, thereby granting access to unauthorized users.

The crossover error rate (CER) is the point at which Type 1 and Type 2 errors are equal, and the CER is an important factor when choosing an authentication system.
The risk of Type 2 (FAR) errors on a low-value asset is less severe than the impact on a high-value asset, as unauthorized access to the high-value asset would have a greater impact.

### Accountability

A system that provides accountability provides a mechanism for users and processes to be held responsible for their actions and decisions.
Knowing who (user or process) did what (action) is the foundation of accountability and relies on unique identification and proven authenticity of users or processes.

Logging and monitoring actions are the most common way of enforcing accountability, and performing audits or reviews is a common way of utilizing the information gathered to verify activities performed in the system.

#### Strong Authentication

Strong authentication is required in order to enforce accountability. If all users share the same credentials, it is impossible to identify which user took a specific action even if all actions are logged.
The level of accountability needed should be documented as a system requirement when choosing IAM tools.

For example, a financial management system needs strong accountability like MFA for regulatory purposes, since many financial transactions are subject to auditing.
A system designed for internal social interactions may only require a basic username and password, which serves to hold users accountable for material they share on the platform.

#### Separation of Duties

Designing processes or systems with separation of duties (SOD) can be useful for enforcing accountability. The requirement for a second user to review and approve or execute a request provides a method for holding a user accountable to specific policies or requirements.

For example, if user expense reports require receipts for all expenses, the report reviewer can enforce this requirement by verifying the submitted information and returning any incomplete reports to the submitters.

### Session Management

A session is an exchange between communicating devices, such as a client and server exchanging information when a user requests web pages or functions like filling an online shopping cart and placing an order.
Session management is the practice of initiating, managing, and terminating sessions, and is critical because session information is an authentication method.

Hypertext Transfer Protocol (HTTP) is stateless — each request sent to a web server is handled without knowledge of any previous requests.
Sessions can be used to maintain a persistent state, such as the items a user has placed in an online shopping cart, which in turn allow for more complex applications.
Each user’s session is identified uniquely, and the items they have browsed or placed in a cart are tied to a unique session identifier.
The ability to create a stateful experience, where the context of interactions is tracked, has led to a multitude of security issues when implemented using the stateless HTTP.

In the shopping cart example, a session is created when a user logs in to the shopping application by providing their username and password.
The session ID is provided to the user in a cookie file, which is then sent back to the web app when subsequent requests are made.
This allows the application to place the request in context of previous actions for that specific user — for example, proceeding to check out with all the items in a shopping cart.

The implementation of session management by tracking a token has given rise to a number of security vulnerabilities, including the following:

* **Session hijacking:**
A session is hijacked if one of the authentic communicating parties is impersonated by an attacker, often with the goal of misdirecting information. Man-in-the-middle attacks are often used to hijack sessions as information is flowing between the two parties.
Session replay attacks are similar and involve an attacker intercepting a session token and later using it to impersonate an authorized user.

* **Session sidejacking:**
A session can be sidejacked by a user on the same network performing packet sniffing to steal session cookie information, which allows the attacker to impersonate the authorized user.

* **Session fixation:**
Fixation attacks occur against web applications that reuse session IDs. This reuse allows an attacker to use an existing session ID to trick a user’s browser into authenticating with the specific session ID. Once authenticated, the credentials granted to that ID can also be used by the attacker.

#### Session Management Guidance

Guidance on securely issuing and managing session IDs includes ensuring they are sufficiently long and complex to avoid weaknesses like guessing valid session IDs and to ensure the session token does not contain obviously identifiable information like cleartext of a username and password.
For web applications where session tokens take the form of cookies, it is also recommended to configure proper security such as setting the Secure attribute to force the browser to use HTTPS when sending the cookie.

### Registration, Proofing, and Establishment of Identity

Provisioning user access begins with the creation of an identity, which requires some amount of information to be provided by the user and verified by the provisioning organization.
This can be as simple as choosing a screen name to claim an identity when signing up for an online application or as complex as submitting government-verified proof of identity when gaining access to systems or facilities with sensitive data.

NIST SP 800-63-3, “Digital Identity Guidelines,” details a process of identity proofing that a credential service provider (CSP) can use when creating identities.
This framework comprises Identity Assurance Levels (IALs) that correspond to different levels of risk to be mitigated when performing identity proofing.

* **IAL1:**
This is the lowest level and only requires the user to self-assert an identity. The CSP is not required to link the individual to a verified, real-life identity.
IAL1 would be appropriate for systems where accountability does not extend to real-world consequences like the need to take criminal action in response to user actions.

* **IAL2:**
This level requires submission of identity documentation and proofing either in-person or remotely by the CSP, and the evidence required must link the user to a real-world identity.
IAL2 is frequently used in employment situations where valid identification documents must be submitted to the employer.

* **IAL3:**
This is the highest level of assurance and requires physical presence for identity proofing, presentation of highly reliable identity evidence like government-issued ID, and formal review of the identity and supporting documentation by trained CSP staff.
The CSP staff can verify the person’s identity and documentation in person, and the in-person requirement provides extra confidence that the user is who they claim to be.

#### Identity Establishment

Once identity information has been presented, verified, and validated to the appropriate level, an identity can be established for the user.
This often takes the form of creating a user account or username on a system, but may also result in the issuance of credentials like a facility badge or authentication token.
If the facility allows visitor access, a streamlined process is likely to exist for visitors upon entering the facility: they must present credentials to be verified by a guard or receptionist, and a visitor badge is issued.

#### Security Considerations

A CISSP responsible for architecting an identity management system must consider the security requirements of the system and its data, like authenticity, confidentiality, and integrity.
A loss of one or more of these will cause different impacts, such as inconvenience or personal distress, loss of organization reputation, unauthorized disclosure of sensitive information, or possibly even personnel safety.
Airline operations, as an example, will likely have different identification requirements for various employees based on the sensitivity of their job.
A greeter who provides directions to passengers in the airport might not have any impact on life, health, and safety, and therefore require only IAL 2, while mechanics and maintenance personnel require more extensive vetting.

### Federated Identity Management

Users in a federated identity management (FIM) scheme can authenticate to any one system participating in the federation and are then granted access to other federated systems.
Organizations that need to share information and system access federate to reduce both the administrative and user overhead of managing multiple sets of credentials for each user.
These organizations can be separate entities, like business partners who need to collaborate on a project, or even divisions within an organization where unique IT systems are maintained, and the purpose of federating the identity systems is similar to an SSO.
It can simplify the administrative overhead of account creation and management, benefits the users by providing easier access, and allows for security benefits like simplified access deprovisioning.

The reduction in overhead is a primary advantage of federation and therefore provides a business justification for federating identity management across organizations.
It is imperative for a security practitioner to properly assess the risk present in federating; however, another organization’s identity management practices will now impact any systems where federation grants access.
If the federated organization does not have commensurate security controls, the risk present to the federated system increases.

### Credential Management Systems

A credential binds an authenticator, such as a password or digital certificate, to an identifier, like a username or process. Credential management systems (CMSs) provide tools to provision, manage, audit, and deprovision these credentials.
Password managers are one common example of a CMS, as are the registration authorities (RAs) and certificate authorities (CAs) used in public key infrastructure (PKI) to manage digital certificates.

The RA is a function designed to provide identity proofing in a PKI, and it is where users submit their identity information in order to prove an identity and acquire a digital certificate.
The CA is used by any user who has received a digital certificate to verify its authenticity.

A CMS should support processes needed to enroll users, proof the identities they claim, issue credentials to verified users, and support management and oversight of existing credentials. These include the following enrollment steps:

* **Sponsorship:**
An authorized entity, such as an employer, sponsors a user to request credentials from a service provider.

* **Enrollment:**
The user enrolls for credentials and supplies the required information to claim an identity, which will depend on the IAL implemented by the credential service provider.

* **Credential production:**
Credentials are produced by the service provider and may take the form of a digital certificate, identification badge, smart card, etc.

* **Issuance:**
The credentials are provided to the user.

* **Credential lifecycle management:**
It may be necessary to perform audits, oversight, or maintenance on the credential throughout its lifetime.
This may include revoking credentials that are no longer needed, reissuing in response to events like a user changing names or roles, suspending credentials if the user resigns, or suspending and reinstating credentials as users take leave and return to the organization.

### Single Sign-On

SSO describes a system where users have a unified login experience — they log in to a single service and are granted access to other tools or resources using the same credentials.
There are a variety of ways to implement SSO, with these two popular approaches:

* Web-based dashboard or portal:
Users log in to a specific website using a single set of credentials and are presented with links to access additional SSO-enabled applications.
This type of SSO often supports legacy software or applications where identity federation is not possible; instead, the SSO software stores the user’s credentials and transmits them to the target application when the user accesses it from the SSO portal.

* Federated identity:
Users log in to a single work resource like the Microsoft 365 or Google Workspace collaboration platforms. Once authenticated, they are able to log in to other, outside resources such as web or smartphone apps using their organization credentials.

#### Advantages and Disadvantages

SSO has major advantages and disadvantages related to usability and security. SSO reduces the burden of users memorizing and managing passwords, which has two key benefits: fewer weak passwords will be chosen, and users have less overhead to remember a variety of passwords.

However, the centralization inherent in SSO can be a disadvantage as well — if a user’s SSO account is compromised, then all SSO-enabled applications are also compromised. This single point of failure is not entirely a drawback, however.
A compromised SSO account does grant broad access, but also increases response speed, since suspending the compromised account also suspends access to all SSO-enabled apps.
An SSO can also serve as a single source of access log data since all access is governed by one system.
This centralized point of oversight can enable faster detection and response for compromised accounts or suspicious insider access since the log data is available for analysis in a single system.

### Just-In-Time

Just-in-time (JIT) identity and access management has two primary use cases, and both focus on provisioning access only when needed.
A user’s account provides the same level of access to the legitimate user and an attacker who has compromised the credentials, and JIT identity is a way to reduce some of this insider threat.

The first use case for JIT identity is to create user identities only when access is requested. In a typical example, an employee joins an organization and has a primary account created, often to provide email access.
Based on the user’s role or job function, they may require access to other systems as well. In a legacy access management model, this access must be granted system by system.
In a JIT model, the user is authorized to access resources based on a role, and Security Assertion Markup Language (SAML) is used to provision an identity and authorization upon the user first accessing a resource.
This reduces management overhead with respect to user administration.

JIT is often implemented as an element of privileged account management (PAM), which deals with the management of credentials for privileged accounts such as system administrators.
Due to the broad, and potentially disruptive, authorizations given to such users, it is advisable to follow the principle of minimum necessary access and heavily restrict these permissions.

Rather than always being available to users, a JIT access management strategy places the credentials needed to access these functions into a secure vault.
When a user needs access, they can elevate their permissions by accessing the vault, which provides additional control opportunities.
Accessing credentials in the vault, sometimes known as privilege escalation, is an event that can be logged and trigger additional security oversight.
This is often known as a break the glass process and refers to old-fashioned alarm systems that require a user to break a glass panel to access the alarm button, which reduced the likelihood of accidental activation.

PAM tools can also implement time limits for credentials and automatically change them after the time limit expires, thereby limiting the amount of time the elevated privileges can be used.

