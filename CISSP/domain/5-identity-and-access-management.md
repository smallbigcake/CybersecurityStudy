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

##### Smartcards

A smartcard is a credit card–sized ID or badge and has an integrated circuit chip embedded in it. Smartcards contain information about the authorized user that is used for identification and/or authentication purposes. Most current smartcards include a microprocessor and one or more certificates.
The certificates are used for asymmetric cryptography such as encrypting data or digitally signing emails. Smartcards are tamper-resistant and provide users with an easy way to carry and use complex encryption keys.
Users insert the card into a smartcard reader when authenticating. It’s common to require users to also enter a PIN or password as a second authentication factor with the smartcard.

##### Tokens

A token device, or hardware token, is a password-generating device that users can carry with them. A common token used today includes a display that shows a six- to eight-digit number.
An authentication server stores the details of the token, so at any moment, the server knows what number is displayed on the user’s token. Tokens are typically combined with another authentication mechanism.

For example, users might enter a username and password (in the something you know factor of authentication) and then enter the number displayed in the token (in the something you have factor of authentication). This provides multifactor authentication.

Hardware token devices use dynamic onetime passwords, making them more secure than static passwords. These are typically six or eight PINs.

The two types of tokens are synchronous dynamic password tokens and asynchronous dynamic password tokens:

* **Synchronous Dynamic Password Tokens**
Hardware tokens that create synchronous dynamic passwords are time based and synchronized with an authentication server. They generate a new PIN periodically, such as every 60 seconds. This requires the token and the server to have accurate time.
A common way this is used is by requiring the user to enter a username, a static password, and the PIN into a web page. Other times, the system prompts users to enter the PIN after first entering their username and password.

* **Asynchronous Dynamic Password Tokens**
An asynchronous dynamic password does not use a clock. Instead, the hardware token generates PINs based on an algorithm and an incrementing counter. When using an incrementing counter, it creates a dynamic onetime PIN that stays the same until it is used for authentication.
Some tokens create a onetime PIN when the user enters a PIN provided by the authentication server into the token.
For example, a user would first submit a username and password to a web page. After validating the user’s credentials, the authentication system uses the token’s identifier and incrementing counter to create a challenge number and sends it back to the user via the web page.
The challenge number changes each time a user authenticates, so it is often called a nonce (short for “number used once”). The challenge number will only produce the correct onetime password on the device belonging to that user.
The user enters the challenge number into the token, and the token creates a password. The user then enters the password into the website to complete the authentication process.

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


## FEDERATED IDENTITY WITH A THIRD-PARTY SERVICE

**Identity as a service (IDaaS)** is an extension of the federated identity concept, which addresses increased demand for collaboration across different teams, business units, and organizations.
This may be driven by the increased sharing of data and information systems among business partners or by organizations adopting cloud services that are hosted outside the organization’s direct control.

Rather than developing custom methods for extending the IAM scheme to external entities, a third-party IDaaS can provide native integration with both legacy systems and external or cloud-based systems.
IDaaS implements federation solutions like SAML and OAuth by default, and these solutions are typically designed to meet the needs of enabling IAM across both internal and external systems.

#### Primary Risks

The decision to use a third-party IDaaS requires a security practitioner to balance the operational need of access to external systems against two primary risks.

First, the IDaaS can be a single point of failure — systems that rely on the IDaaS for access control are unavailable if it is down, though if the organization already uses a centralized IAM, this risk is minimal.
IDaaS may actually decrease the risk if the chosen third party has more robust uptime capabilities than the organization’s internal hosting, though of course if the IDaaS provider drops support for the target system or ceases operations, the organization will find itself in trouble.

The second risk to consider is the loss of control inherent in using a third party, which is common to any decision to use a cloud service. Identification is the foundation of access control, so the potential risk of outsourcing this function can be high.
If the IDaaS provider suffers a data breach, the organization’s identity and access management information could be compromised.

### On Premises

On premises, sometimes shortened to on-prem, describes an architecture that exists in a facility controlled by the organization, such as a Lightweight Directory Access Protocol (LDAP) or Microsoft Active Directory (AD) system hosted in the organization’s offices or data center.
Many organizations have these systems deployed to support existing or legacy applications and infrastructure.

#### Benefits and Costs

Key benefits of on-premises management systems include total control over the hardware and software used in the IAM system, unlike cloud or third-party systems where the organization gives up some control to the service provider.
As a CISSP, it is important to review the benefit of total control against the additional costs incurred, such as full-time administrators needed to maintain a complex IAM system like Microsoft AD.

#### Difficulties and Risks

Extending an existing on-premise identity management system to cloud-based applications or federating it with external parties like business partners can prove difficult or impossible, if the tools in use were not designed to support this type of use.
Retaining control over both the IAM system and the hardware offers security control opportunities, but limited federation capabilities can force organizations to seek alternatives.
Many legacy IAM solutions can be quite complex to administer, which presents additional risk in the form of cost to maintain them and the potential for misconfiguration due to lack of adequate skills or understanding of a complex system.

The process of extending an existing IAM typically requires additional software and proper security configuration that allows the on-premise IAM to communicate with Federated Identity with a Third-Party systems outside the organization’s control.
This might be achieved with native extensions or plugins to the IAM tool or with a separate application like a SAML gateway or SSO provider.

### Cloud

Newer organizations may be “cloud-first” or “cloud-native,” meaning they lack any on-premise or legacy infrastructure. Older organizations may pursue a strategy of migrating to cloud-only solutions due to the cost savings they provide.
In both cases, a legacy IAM solution would be a poor fit due to significant costs to acquire hardware, software, and personnel skills to manage it; a cloud-based IDaaS is likely to be a more cost-effective solution.

Cloud-based IDaaS solutions act as an IAM broker and can be used to manage access controls for the organization’s cloud-based systems and federated with other applications, services, or even organizations using the same IDaaS.
Organizations migrating into the cloud can take advantage of hybrid IDaaS, which extends the IDaaS to support identity and access management for legacy applications, or SSO portal features, which allow users to access non-SSO applications by storing the credentials and facilitating automatic sign in.

Popular cloud services, including software as a service (SaaS) tools, offer native integration with popular cloud IDaaS platforms, which reduces administrative overhead associated with user provisioning.
This can be used to implement JIT provisioning for new user accounts on cloud services; when a user attempts to log into a service for the first time, their authorization to use it is checked with the IDaaS provider.

If they are authorized, an account is created; this benefits users and administrators, as it automates the process of checking authorizations and provisioning accounts.

### Hybrid

#### As a Migration Strategy

Hybrid IDaaS is a combined deployment of IAM elements in both the cloud and on premises and is often used as part of a migration strategy in organizations where legacy infrastructure requires an on-premise solution.
For example, this hybrid approach is commonly used in Windows environments that rely on legacy AD for current applications migrating to a cloud-based setup with Azure AD, which is a cloud-based IDaaS platform hosted in the Microsoft Azure cloud.
Both the legacy AD and Azure AD run simultaneously and synchronize information, with the ultimate goal of total migration to the cloud-based solution once all legacy applications have been identified and migrated.

#### As a Permanent Solution

Other third-party IDaaS solutions can also integrate with existing on-premise IAM tools and act as a centralized point for credential management.
Even if the organization does not plan to migrate completely to cloud solutions, legacy applications continue to use the on-premise IAM provider, while any cloud services or federated third parties can use the cloud-based IDaaS provider.
This divided access control approach offers benefits to users, who are required to maintain only one set of credentials, and acts like an SSO to reduce management overhead.

#### Risks

The risks of a hybrid setup like this include the need to dedicate sufficient resources to maintaining dual IAM implementation.
Many organizations assume a move to the cloud means no resources are required for on-premise maintenance, but the hybrid approach does not completely remove this need.
Additionally, the hybrid approach introduces the same risk as cloud-based IAM due to a third party managing identities and can pose additional risk if a breach of the IDaaS grants access to internal resources that rely on on-premise IAM synchronized with the IDaaS provider.


## IMPLEMENT AND MANAGE AUTHORIZATION MECHANISMS

#### Authorization Concepts

Authorization can be the decision to grant a subject access to an object and confirmation that a subject is authorized to access an object when they attempt to access it.
This implies decisions that are made before access, when a user is first enrolled in an IAM, as well as decisions made at the time of use when a user makes a request, such as trying to open a file or access a system.

Authorization is simple to manage if a few subjects, like users or processes, require access to a few objects, like documents or an entire information system.
However, complex organizations with hundreds or thousands of subjects accessing millions of objects are impossible to manage without a structured and orderly methodology.
Even an organization with a hundred users and multiple information systems for various teams or departments will find that manually managing access on a per-user basis is inefficient at best, and at worst is totally impossible.

#### Access Control Models

Access control models, which are described in the following sections, provide ways of identifying subjects and objects and establishing relationships to determine authorization.
These relationships are foundational to access control systems, and the decision to allow or deny access supports fundamental security objectives like maintaining confidentiality, integrity, and authenticity of data.
These models also provide a variety of methods for managing complex subject-object access needs, so they are useful to security practitioners in organizations with more than a few users and systems.

Modern information systems and IT environments often implement a mix of access control models, such as firewalls utilizing rule-based access control, file sharing systems with discretionary access control, and HR departments that identify specific job functions and associated permissions needed for role-based access control.

NIST SP 800-192, “Verification and Test Methods for Access Control Policies/Models,” provides definitions of these models and guidance on how to identify requirements for an access control model to apply to a specific system or organization.

#### Extensible Access Control Markup Language (XACML)

XACML is used to express security policies and access rights to assets provided through web services and other enterprise applications.

SAML is just a way to send around your authentication information, as in a password, key, or digital certificate, in a standard format. SAML does not tell the receiving system how to interpret and use this authentication data.

Two systems have to be configured to use the same type of authentication data.
If you log into System A and provide a password and try to access System B, which only uses digital certificates for authentication purposes, your password is not going to give you access to System B’s service.
So both systems have to be configured to use passwords. But just because your password is sent to System B does not mean you have complete access to all of System B’s functionality.
System B has access policies that dictate the operations that specific subjects can carry out on its resources.

The access policies can be developed in the XACML format and enforced by System B’s software. XACML is both an access control policy language and a processing model that allows for policies to be interpreted and enforced in a standard manner.
When your password is sent to System B, there is a rules engine on that system that interprets and enforces the XACML access control policies.
If the access control policies are created in the XACML format, they can be installed on both System A and System B to allow for consistent security to be enforced and managed.

XACML uses a **Subject** element (requesting entity), a **Resource** element (requested entity), and an **Action** element (types of access).
So if you request access to your company’s CRM, you are the Subject, the CRM application is the Resource, and your access parameters are outlined in the Action element.


#### Comparing Permissions, Rights, and Privileges

When studying access control topics, you’ll often come across the terms permissions, rights, and privileges. Some people use these terms interchangeably, but they don’t always mean the same thing.

##### Permissions

In general, permissions refer to the access granted for an object and determine what you can do with it. If you have read permission for a file, you’ll be able to open it and read it. You can grant user permissions to create, read, edit, or delete a file on a file server.
Similarly, you can grant a user access rights to a file, so in this context, access rights and permissions are synonymous. For example, you may be granted read and execute permissions for an application file, which gives you the right to run the application.
Additionally, you may be granted data rights within a database, allowing you to retrieve or update information in the database.

##### Rights

A right primarily refers to the ability to take an action on an object. For example, a user might have the right to modify the system time on a computer or the right to restore backed-up data. This is a subtle distinction and not always stressed.
However, you’ll rarely see the right to take action on a system referred to as a permission.

##### Privileges

Privileges are a combination of rights and permissions. For example, an administrator for a computer will have full privileges, granting the administrator full rights and permissions on the computer.
The administrator will be able to perform any actions and access any data on the computer.

#### Understanding Authorization Mechanisms

Access control models use many different types of authorization mechanisms, or methods to control who can access specific objects. Here’s a brief introduction to some common mechanisms and concepts:

##### Implicit Deny

A fundamental principle of access control is implicit deny, and most authorization mechanisms use it. The implicit deny principle ensures that access to an object is denied unless access has been explicitly granted to a subject.

For example, imagine an administrator explicitly grants Jeff Full Control permissions to a file but does not explicitly grant permissions to anyone else. Mary doesn’t have any access even though the administrator didn’t explicitly deny her access.
Instead, the implicit deny principle denies access to Mary and everyone else except for Jeff. You can also think of this as deny by default.

##### Access Control Matrix

In short, an access control matrix is a table that includes subjects, objects, and assigned privileges. When a subject attempts an action, the system checks the access control matrix to determine if the subject has the appropriate privileges to perform the action.

For example, an access control matrix can include a group of files as the objects and a group of users as the subjects. It will show the exact permissions authorized for each user for each file. Note that this covers much more than a single access control list (ACL).
In this example, each file listed within the matrix has a separate ACL that lists the authorized users and their assigned permissions.

##### Capability Tables

Capability tables are another way to identify privileges assigned to subjects. They are different from ACLs in that a capability table is focused on subjects (such as users, groups, or roles).
For example, a capability table created for the accounting role will include a list of all objects that the accounting role can access as well as the specific privileges assigned to the accounting role for these objects.
In contrast, ACLs are focused on objects. An ACL for a file would list all the users and/or groups that have authorized access to the file and the specific access granted to each.

##### Constrained Interface

Applications use constrained interfaces or restricted interfaces to restrict what users can do or see based on their privileges. Users with full privileges have access to all the capabilities of the application. Users with restricted privileges have limited access.
Applications constrain the interface using different methods. A common method is to hide the capability if the user doesn’t have permission to use it.

For example, commands might be available to administrators via a menu or by right-clicking an item, but if a regular user doesn’t have permissions, the command does not appear.
Other times, the application displays the menu item but shows it dimmed or disabled. A regular user can see the menu item but will not be able to use it.

The Clark–Wilson model (covered in Chapter 8) discusses the technical details of how it implements a constrained interface.

##### Content-Dependent Control

Content-dependent access controls restrict access to data based on the content within an object. A database view is a content-dependent control. A view retrieves specific columns from one or more tables, creating a virtual table.

For example, a customer table in a database could include customer names, email addresses, phone numbers, and credit card data. A customer-based view might show only the customer names and email addresses and nothing else.
Users granted access to the view can see the customer names and email addresses but cannot access data in the underlying table.

##### Context-Dependent Control

Context-dependent access controls require specific activity before granting users access.

As an example, consider the data flow for a transaction selling digital products online. Users add products to a shopping cart and begin the checkout process.
The first page in the checkout flow shows the products in the shopping cart, the next page collects credit card data, and the last page confirms the purchase and provides instructions for downloading the digital products.
The system denies access to the download page if users don’t go through the purchase process first.

It’s also possible to use date and time controls as context-dependent controls.

For example, it’s possible to restrict access to computers and applications based on the current day and/or time. If users attempt to access the resource outside the allowed time, the system denies them access.

##### Need to Know

This principle ensures that subjects are granted access only to what they need to know for their work tasks and job functions.
Subjects may have clearance to access classified or restricted data but are not granted authorization to the data unless they actually need it to perform a job.

##### Least Privilege

The principle of least privilege ensures that subjects are granted only the privileges they need to perform their work tasks and job functions. This is sometimes lumped together with need to know.
The only difference is that least privilege will also include rights to take action on a system.

##### Separation of Duties and Responsibilities

The separation of duties and responsibilities principle ensures that sensitive functions are split into tasks performed by two or more employees. It helps prevent fraud and errors by creating a system of checks and balances.

### Role-Based Access Control

RBAC is a model that maps subjects to a set of objects based on the user’s role in the organization. A role is a set of job functions, often defined by a department or position, and the access granted is based on the needs of that particular role.
Roles are mapped to object access authorizations, and all subjects granted a particular role are given the same access.

#### Example

For example, a user with security responsibility might be given the role of security analyst.
Users with the security analyst role are granted read/write access to the security information and event management (SIEM) platform, but are denied system administrator privileges like Windows domain admin or Linux sudo.
In this case, the role grants access to security logs, but prevents the analysts from accessing systems being monitored, which serves two purposes.

First, the analysts do not require access to perform system admin functions, and nonanalyst users do not need access to the SIEM, so the roles implement least privilege.

Second, this role-based access can preserve data integrity, which supports accountability.
In a properly designed RBAC model, so-called toxic role combinations should be prevented.
In this example, any user with a system admin role should be barred from the security analyst role, preventing an administrative user from taking malicious action on a system and also erasing evidence of their actions from logs on the SIEM.

#### Benefits

RBAC reduces the management and overhead of creating and managing authorizations for users. If members of the legal department need access to 15 systems, it is more efficient to create a role with access to these systems and then put new members in a group associated with that role.
This supports important security objectives of access control, while also reducing resources required to implement security, which aligns with business or organization objectives.

#### Task-Based Access Control (TBAC)

Another method related to RBAC is task-based access control (TBAC). TBAC is similar to RBAC, but instead of being assigned to one or more roles, each user is assigned an array of tasks. These items all relate to assigned work tasks for the person associated with a user account.
Under TBAC, the focus is on controlling access by assigned tasks rather than by user identity.
As an example, Microsoft Project uses TBAC. Each project has multiple tasks. The project manager assigns tasks to project team personnel. Team personnel can address their own tasks (adding comments, indicating progress, and so on), but they cannot address other tasks.
Microsoft Project handles the underlying details.

### Rule-Based Access Control

Rule-based access control, which is usually spelled out to avoid confusion with role-based models or shortened to RuBAC, is based on a list of predefined rules to determine authorization.
In physical terms, a guest list is RuBAC model. If a person is on the guest list, they are granted access to the party; otherwise, they are denied entry.

#### Access Control Lists (ACLs)

Information systems often implement RuBAC via an access control list (ACL).
Common examples include static firewall rulesets, which define allowed and blocked IP addresses or ports, and file ACLs, which define users who are authorized to access a file and their permissions like read or write.
When an access attempt is made, the system performs a review against the ruleset.
A traditional or nonstateful firewall reviews an incoming packet to determine if it comes from an IP address that is allowed, while a filesystem reviews the current user against the file’s ACL to determine if the requested action is allowed.

#### Implicit and Explicit Permissions

Rule-based systems also implement the concepts of implicit and explicit permissions.

In an implicit allow system, all access is allowed unless a rule is defined to prohibit access, much like a shop is open to any member of the public except specific customers who are known to shoplift. These unwanted users are explicitly denied entry.

Implicit deny is the opposite — only people on an approved list are allowed entry, while everyone else is denied. This is sometimes known as deny all or allow by exception and is a fundamental security best practice as it reduces the chance of unauthorized access.

### Mandatory Access Control

The mandatory access control (MAC) model is often associated with military or government organizations, and it employs a static and hierarchical approach to access control.
MAC can be described as a _nondiscretionary access control_ model, in which access control is enforced systematically and is not at the discretion of data owners or others.

MAC is achieved by applying security labels to both subjects and objects; for example, Top Secret, Secret, and Unclassified. When an object is created, the owner or creator is responsible for assigning a proper security label.
When a subject attempts to access an object, the system verifies the security labels and enforces appropriate access control.
For example, a user with a security label of Secret will be denied access to files with a security label of Top Secret, but will be granted access to files labeled Secret or Unclassified.

The Bell–LaPadula and Biba security models discussed in Chapter 3, “Security Architecture and Engineering,” are examples of MAC and are often used as foundational principles in modern systems’ access control features.
The basic rules described by both models implement MACs using label-based descriptions of data confidentiality or integrity.
The properties of each model describe how access to objects is restricted based on the subject security label of the subject and the label of the object they attempted to access.

### Discretionary Access Control

Access decisions in a discretionary access control (DAC) model are made by a system or data owner, who decides at their discretion which subjects can access an object.
In the case of a file, the file’s owner can define other users who can access the file. This extends to the functions those users can perform, like reading or updating the file.
This may take the form of granting public read access to a document, while specifying a small group of editors who can make changes to the file.

DAC is a distributed model and can be useful when no central authority has sufficient information to make access control decisions.
Social media sites are a common example; the users who upload content like pictures are best suited to determine if the content should be accessible to any other user of the platform, or if it should be restricted to a specific group of users like close friends or family.
In business settings, the owner is often the owner, creator, or custodian of a system or dataset. A centralized IT department may not be able to determine who needs access to specific files on a shared drive, but the owner of the folder does know which users need access to collaborate.

The flexibility and decentralized nature of DAC is also a potential security drawback. It is more difficult to enforce consistency when a large group of data owners is making access control decisions, and the ability for a data owner to make permission changes can be abused by an insider threat.

### Attribute-Based Access Control

Attribute-based access control (ABAC), sometimes referred to as policy-based access control, is an emerging access control model that combines attributes about the subject and evaluates them against a policy to make an access control decision.
For example, attributes might be the user’s identity, role as a data entry professional, and the time of day. When a user attempts to access a system, these attributes are compared against a policy stating that access for data entry users is allowed only during standard business hours.
If the data entry user attempts this access outside of normal business hours, the access request is denied.

ABAC provides more flexibility than other access control models and can be used to achieve more dynamic and risk-based access control.
For example, users might be required to enter multifactor authentication only when logging in from a new device. ABAC is similar to RBAC models, but defines a complex policy to allow or deny access rather than a binary allow/deny decision.
Stateful firewalls are one example of ABAC; incoming traffic to a host is allowed if it corresponds to a previously established session of communication; otherwise, traffic to the host is denied.
A traditional or nonstateful firewall could be a hindrance to an organization if it blocked such traffic, which highlights the importance of choosing access control mechanisms with sufficiently robust capabilities to support organizational needs.

A system implementing ABAC utilizes a set of policy attributes to make access control decisions.
Examples of attributes that can be tested include where the subject or object is located, when the request is being made, the role of the requestor, and whether the request is coming from a new device.
For example, a routine user requesting access from their standard workstation to a sensitive production file outside of normal working hours can be allowed.
If the same user attempts to access the same data, but the request comes from a previously unseen device in a foreign country, access should be denied.
The user might be traveling and trying to stay productive, but there is a significant chance the user’s credentials have been stolen.

### Risk-Based Access Control

A risk-based access control model is designed around an assumption that risks change over time. Unlike other models that consider risks to be static and do not account for changing risks over time, risk-based models can provide dynamic access control using a variety of parameters to determine authorization.
In other models such as RBAC or RuBAC, the dynamic nature of risks over time must be accounted for with manual updates to access controls, such as provisioning or deprovisioning access. Systems that implement these models cannot respond to these dynamic changes in real time.

For example, the IAM can integrate threat intelligence data and make dynamic authentication decisions based on the intelligence available.
If another business unit or a partner organization has come under attack by a phishing campaign, then the IAM might temporarily increase the frequency of required MFA at login in response to the increased threat.
Similarly, if the organization’s SIEM has identified an increase in the number of failed login attempts, temporary firewall rules could be automatically implemented to block traffic associated with the failed logins, which could make a brute-force attack difficult or impossible.

Risk-based models can utilize a number of factors to dynamically define authentication requirements. Financial institutions often utilize this model to detect fraud at an individual account level.
Accounts that belong to a person who rarely travels or makes online purchases have a different risk profile compared to frequent travelers or online shoppers, so writing static rules that apply to all account holders is nearly impossible.
Instead, one account’s fraud indicators are any purchases made outside a specific geographic region, while another account’s indicators are purchases made in physical retail stores instead of online retailers.


## MANAGE THE IDENTITY AND ACCESS PROVISIONING LIFECYCLE

The act of creating an account is known as provisioning. This encompasses actions such as reviewing proof that a user is who they claim to be before creating their account, as well as procedures designed to review and approve access requests.
When an account is no longer needed, access is removed via deprovisioning, which happens when a user leaves or changes roles, or when a system account is terminated during decommissioning.

Reviews must be conducted periodically to identify if all provisioned accounts are still accurate. Any accounts that are not needed or permissions that are excessive should be terminated using appropriate deprovisioning actions like revoking, disabling, or deleting the account or authorizations.
This deprovisioning typically focuses on removing access, but deprovisioning does not necessarily mean an account is deleted. Instead, it may be maintained for accountability purposes, since the user’s actions are recorded in log files.

Reviews may also identify access that is needed but not currently granted, which can be addressed by provisioning new access.

### Account Access Review

User accounts are associated with individuals, while system accounts are associated with nonhuman access needs. These often take the form of system or service accounts needed to perform crucial system functions like backups, database maintenance, or executing requests or processes on behalf of a user.
Nonhuman accounts include devices as well, such as Internet of Things (IoT) or system Application Programming Interface (API) calls. Both user and system accounts must be periodically reviewed to ensure they are granted access only as needed to perform their intended functions.

When crafting an access review policy, a security practitioner must balance a number of important factors. Both the cadence of reviews and the accounts to be reviewed may be dictated by legal or regulatory obligations.
For example, nonadministrative access might have an annual review cycle, while administrative accounts must be reviewed quarterly. The increased damage that could be caused by an improperly provisioned administrative account justifies the increased overhead of performing more frequent reviews.

#### User Account Access Review

Review procedures for user access must include identifying what systems, data, and permissions a user is granted. Once identified, these access attributes must be checked against the organization’s access policies as well as IAM practices like least privilege.

The review should encompass the following elements for each user, as well as a check of the appropriateness of the access:
* All accounts the user can access, whether by direct assignment or via shared credentials if used.
* All sensitive datasets or systems the user can access
* What actions the user can perform on each system or dataset, such as read, write, or delete.
* Identify any permissions that are excessive, such as a user who is not performing administrative actions but is granted administrative access.
* Inactive or dormant accounts, particularly those assigned to users who have left the organization or changed roles.
* Roles assigned to the user and any potential toxic combinations of access granted by roles. A toxic combination occurs when a user’s role-based access violates controls like separation of duties or creates a conflict of interest.

#### System Account Access Review

Policies for system and service accounts should also be defined and must balance the frequency of review with the privileges granted. Nonhuman accounts will undergo less change than user accounts, as they are not subject to human actions like promotion or job change that require adjustment of privileges.
However, they can still present a security risk due to inappropriate levels of access — for example, a default local administrator account might be enabled during troubleshooting. If it is not properly deactivated or disabled when troubleshooting is completed, it is at risk of being exploited.

In other cases, system or service accounts may be granted escalated privileges by default, but when implemented in a particular system, these permissions are not needed.
Systems may include default local administrator accounts that are not needed if the computer in question is part of a remote management scheme like a Windows domain or MDM, or service accounts remain enabled even if the particular service is not active on the workstation.
In these cases, access reviews are similar to configuration audits; they both share a goal of identifying system configurations, like default system account privileges, that are out of alignment with the secure baseline.

#### Automated Access Reviews

Performing access reviews can be time-consuming and potentially disruptive if an account is improperly flagged for inappropriate access.
Implementing automation is critical to performing timely reviews, and some access management tools can be used to supplement the review with proactive controls like disabling accounts that are not used within a set time period.
Security tools like SIEM or security orchestration, automation, and response (SOAR) can be useful to perform these automated reviews.
The risk of not performing the reviews is inappropriate or unintended access, which can be exploited by insider threats or an attacker who has compromised a valid user account.

### Account Usage Review

User, system, and nonhuman accounts should all be subject to review of the actions they have performed. This can help the organization identify unwanted or inappropriate use of permissions, as well as account permissions that are inappropriate.
The usage review may be part of access reviews, may be performed using automated tools like a SIEM, or might even involve a process of occasional oversight like a random audit of system activity several times a year to spot unexpected or inappropriate usage.

A CISSP can achieve multiple security objectives with a usage review, though the primary reason is to enforce accountability for system usage.
Automated system usage reviews should be integrated where JIT identity systems are in use, to perform reviews when privileges are used.
For example, if a user accesses administrative credentials, it could be a legitimate support case or a privilege escalation by an attacker.
Correlating the privilege escalation to a work ticket or support case demonstrates that the access was needed, while access to the administrative credentials for no reason is a suspicious incident worthy of investigation.

### Provisioning and Deprovisioning

Provisioning is the action of enabling or creating access, and deprovisioning is the opposite action and may include suspending, terminating, or even deleting the access credentials.
These processes are usually related to staff changes like onboarding or offboarding (joining or leaving an organization), job transfers, or role changes like promotions.
These staff management processes are usually not handled by a security practitioner, so it is imperative that the security team properly coordinate the process with responsible teams like HR or IT to ensure security measures are designed, integrated into the process, and properly executed.

Deprovisioning is a particularly important task, as there is increased risk if users who no longer require access are still able to access data and systems.
An access review must be performed to identify which systems and data the user has access to, and confirmation must be obtained when the access has been deprovisioned.

The access management policy and procedures should account for user access changing under three main scenarios:
* Hostile or involuntary circumstances include a staff member being let go at the company’s decision. This type of departure carries higher risk because employees may be disgruntled or act out in retaliation, and procedures will typically require faster deprovisioning and more oversight.
* Friendly or voluntary circumstances include a staff member resigning or retiring and generally carry less risk. Access deprovisioning in these cases may occur more slowly, and verification may be left until the next access review to catch any mistakes.
* Job changes are treated by some high-security organizations the same as a friendly deprovisioning as an extra precaution. The user’s current access is entirely deprovisioned, and new access is requested and provisioned for the user’s changed job role.

#### Service Provisioning Markup Language (SPML)

The Service Provisioning Markup Language (SPML) allows for the exchange of provisioning data between applications, which could reside in one organization or many; allows for the automation of user management (account creation, amendments, revocation) and access entitlement configuration related to electronically published services across multiple provisioning systems; and allows for the integration and interoperation of service provisioning requests across various platforms.

When an organization hires a new employee, that employee usually needs access to a wide range of systems, servers, and applications. Setting up new accounts on every system, properly configuring access rights, and then maintaining those accounts throughout their lifetimes is time-consuming, laborious, and error-prone.
What if the organization has 20,000 employees and thousands of network resources that each employee needs various access rights to? This opens the door for confusion, mistakes, vulnerabilities, and a lack of standardization.

SPML allows for all these accounts to be set up and managed simultaneously across the various systems and applications. SPML is made up of three main entities:
* the **Requesting Authority (RA)**, which is the entity that is making the request to set up a new account or make changes to an existing account;
* the **Provisioning Service Provider (PSP)**, which is the software that responds to the account requests;
* and the **Provisioning Service Target (PST)**, which is the entity that carries out the provisioning activities on the requested system.

So when a new employee is hired, there is a request to set up the necessary user accounts and access privileges on several different systems and applications across the enterprise.

This request originates in a piece of software carrying out the functionality of the RA.
The RA creates SPML messages, which provide the requirements of the new account, and sends them to a piece of software that is carrying out the functionality of the PSP.
This piece of software reviews the requests and compares them to the organization’s approved account creation criteria. If these requests are allowed, the PSP sends new SPML messages to the end systems (PST) that the user actually needs to access.
Software on the PST sets up the requested accounts and configures the necessary access rights.

If this same employee is fired three months later, the same process is followed and all necessary user accounts are deleted. This allows for consistent account management in complex environments.

#### Self-Provisioning and Self-Deprovisioning

Systems that support self-provisioning or self-deprovisioning must have access control requirements addressed as part of the system development. For example, an online shopping site that allows users to register themselves for accounts will mostly likely implement RBAC.
One role will be “customer,” with permission to access information related to that specific user, while another role might be “customer support,” which is for internal users who need access to limited information across all customers.

The requirements for users to provision their own accounts will vary depending on the type of application, and the identity proofing requirements must be considered in light of any legal or regulatory compliance requirements associated with the identity proofing material that must be collected.
Deprovisioning is likely to fall under privacy legislation or regulation, so appropriate methods for disabling and possibly deleting data associated with the user must be provided

### Role Definition

Roles simplify access management by providing a common set of access requirements for all users assigned the specific role.
For example, an organization’s roles might be defined according to department, so users with the IT role are granted access to all IT systems, while finance users are granted access to finance systems.
When a new user joins, they are placed in a group or assigned a particular role, which grants them access to the appropriate systems.
This simplifies the process of access provisioning and deprovisioning, as only one action needs to be performed instead of multiple actions to add the user to each system.

The process of defining roles must follow access management principles like least privilege and may also be used as a way to implement security controls like separation of duties.
For example, if users are able to upload their own personal data into an HR system but should not be able to query the system, then non-HR roles can be granted write permissions and denied read permissions.
A matrix of systems and roles can be useful to visualize these permissions.

### Privilege Escalation

Escalating privileges is the process of gaining elevated permission. For example, if a user with read-only access finds a bug that allows them to write data, this escalates their privileges beyond what they should have.
The escalation can lead to negative security outcomes like loss of confidentiality, integrity, authenticity, or even availability if the users’ elevated privileges allow them to disrupt system operations.

#### Valid Use Cases

There are valid use cases for privilege escalation. A user with authorization to perform administrative functions should not use their administrator account at all times, as they generally do not need access to all its functionality and could inadvertently execute commands.
Features like sudo on Unix systems or credential vaults for other systems can be used to implement a break-the-glass process. When needed, the user can virtually break the glass and gain access to the credentials, which may trigger actions like a security alert or increased logging.
If the access is inappropriate, these actions give defenders a greater chance of discovery.

#### Privilege Escalation Methods

A well-engineered IAM should limit user access to privileged accounts and allow access only when necessary.
For example, even a system administrator does not need to use their administrative privileges to perform routine tasks like checking email or reading news in a web browser.
Implementing restrictions to administrative privileges reduces the likelihood those privileges can be misused accidentally or intentionally.
For instance, a drive-by download from a malicious website can be restricted from executing with administrative-level credentials if the user is not signed in as an administrator while performing casual web browsing.

Examples of methods to implement this type of privilege escalation include the following:
* sudo on Linux and Unix systems allows an authenticated user to perform superuser actions for a limited amount of time if they can provide the proper credentials.
The extra act of authenticating creates a barrier to accidental misuse of administrative privileges.
* Break-the-glass procedures or credential vaulting place administrative credentials in a restricted-access tool. Gaining access to the credentials requires a deliberate process and can be a trigger for alerts or alarms, thereby providing security with insight into the use of these credentials.
* Managed service accounts are nonhuman accounts designed to perform specific functions. They are typically configured to perform only their designated function and cannot be used to log in to a system, which makes attacks like phishing these account credentials nearly impossible.

#### Privilege Escalation Attacks

Privilege escalation attacks are a common security threat as well.
In a vertical escalation attack, the attacker is seeking to gain increased privileges on a system, such as using Structured Query Language (SQL) injection to gain direct database access when the user is only authorized to access data through a web front end.
Horizontal privilege escalation, also known as lateral movement, is an attack method that grants access to systems or resources the user is not authorized for and may exploit improperly configured IAM tools or features like roles.
Horizontal escalation is often targeted at accessing other systems using already compromised credentials; goals may include performing vertical escalation on another system or gaining access to additional sources or types of data.


## IMPLEMENT AUTHENTICATION SYSTEMS

### OpenID Connect/Open Authorization

#### OAuth

Open Authorization (OAuth) is an “open protocol to allow secure authorization in a simple and standard method from web, mobile, and desktop applications,” as defined by the OAuth community website (oauth.net).
The project is an Internet Engineering Task Force (IETF) working group, which lends its broad, global support, and, as the name implies, it is focused on authorization rather than authentication.
The community website contains a variety of resources including specifications for platform-specific implementations and best-practice guides for using OAuth in various applications.

OAuth defines four key roles that systems in an OAuth federation must implement to exchange authorization information:
* **Resource owner:** Any entity that grants access to a protected resource, such as an information system or dataset.
* **Resource server:** Any server hosting the protected resource, which accepts and responds to access requests.
* **Client:** Any application making requests for access to protected resources.
* **Authorization server:** Any server issuing access tokens to clients after successful authentication; tokens are used across the federated system to gain access.

#### OpenID

OpenID is also an open standard, but it is maintained by the OpenID Foundation rather than as an RFC standard.
It provides decentralized authentication, allowing users to log into multiple unrelated websites with one set of credentials maintained by a third-party service referred to as an OpenID provider.

#### OpenID Connect (OIDC)

Open ID Connect (OIDC) adds authentication functions built on top of OAuth version 2.0 and federates identity management to provide users with an authentication experience similar to SSO.
It is often implemented in web applications; and in OIDC, the user is presented with a choice of identity providers (IdPs), which are usually common email or social media platforms like Gmail, LinkedIn, or Twitter.
The user selects an IdP, which then provides authentication information to the relying party using OAuth.
The authentication information in OIDC is passed from an OIDC provider (OP) to the relying party (RP) in the form of a token, which contains claims about the user and authentication of their asserted identity.
IDaaS provider Okta has an illustrated developer blog highlighting the key steps of OIDC authentication (developer.okta.com/blog/2019/10/21/illustrated-guide-to-oauth-and-oidc).

##### JavaScript Object Notation (JSON) Web Token (JWT)

It builds on the technologies created with OpenID but uses a JavaScript Object Notation (JSON) Web Token (JWT), also called an ID token. OpenID Connect uses a web service to retrieve the JWT. In addition to providing authentication, the JWT can also include profile information about the user.

##### OpenID Connect Flows

Most of this occurs behind the scenes, but you can see it in action by logging onto eBay with a Google account. These processes and interfaces change over time, but the general steps are as follows:
1. If you don’t have a Google account, create one first.
2. Ensure you’re logged out of eBay and Google, go to ebay.com, and click Sign In.
3. Click Continue With Google. A dialog box opens, prompting you to enter your Google email. It also indicates what Google will share with ebay.com.
4. Enter your email address and press Enter.
5. Enter your password and click Next.
6. If you’ve enabled 2-Step Verification on your Google account, you’ll be prompted to get the code and enter it.

### Security Assertion Markup Language

Security Assertion Markup Language (SAML) is an open XML-based standard commonly used to exchange authentication and authorization (AA) information between federated organizations. It provides SSO capabilities for browser access.

SAML is a framework for different systems to exchange security assertions, which consist of information needed to enforce access controls. It uses Extensible Markup Language (XML) to format messages regarding identities, resources, and access information like authentication and authorization.
In SAML, there are three roles: first is the user agent (like a web browser) that makes a request to the second role, which is a service provider (like a web application).
The service provider relies on the assertion made by the third role, called an identity provider (IdP), for user identification, authentication, and authorization.

There are four components in SAML:
* **Assertions** define SAML attributes like how authentication and authorization message protocols or frameworks are to be used by the services.
* **Bindings** define the request-response pairs to be used by the three roles to communicate.
* **Protocols** include HTTP and simple object access protocol (SOAP), which are used to package and exchange messages between roles.
* **Profiles** are the combination of assertions, bindings, and protocols in use within a specific SAML implementation.

The IdP can send three types of XML messages known as assertions:
* **Authentication Assertion** This provides proof that the user agent provided the proper credentials, identifies the identification method, and identifies the time the user agent logged on.
* **Authorization Assertion** This indicates whether the user agent is authorized to access the requested service. If the message indicates access is denied, it indicates why.
* **Attribute Assertion** Attributes can be any information about the user agent.

The current version of SAML, v2.0, is an OASIS standard. Documentation and best practices for SAML implementation are maintained on the SAML wiki (wiki.oasis-open.org/security/FrontPage).
SAML is most often used to provide an SSO experience to end users. Users access resources using normal system functions like clicking links to access a web application.
Security assertion information can be provided as part of a custom URL pointing to the web application or sent as a cookie to the web application.
This information is based on the user’s previously provided information, such as their login credentials entered when signing into their computer or a web portal, which then grants access to other SAML-enabled applications.

### Comparing SAML, OAuth, OpenID, and OIDC

It’s easy to mix up the differences between SAML, OAuth, OpenID, and OIDC. This section summarizes key points of each one and points out some of the differences.

The following bullets outline the key points about SAML:
* SAML 2.0 is an open XML-based standard.
* OASIS adopted it as a standard in 2005.
* It utilizes three entities: a principal (such as a user), a service provider (such as a website), and an identity provider (a third party that holds the authentication and authorization information).
* It can provide authentication, authorization, and attribute information on the principal.

The following bullets outline the key points about OAuth:
* It’s an authorization framework, not an authentication protocol.
* RFC 6749 describes OAuth 2.0.
* It exchanges information using APIs.
* An app obtains an access token from an identity provider.
* Later, the app includes the access token for authorization.

The following bullets outline the key points about OpenID:
* OpenID is an authentication standard.
* It is maintained by the OpenID Foundation.
* An OpenID provider provides decentralized authentication.
* Users enter their Open ID identifier (such as bobsmith2021.myopenid.com) on a site and the OpenID provider verifies the identifier.

The following bullets outline the key points about OIDC:
* OIDC is an authentication layer using OAuth 2.0.
* It builds on the OpenID authentication standard.
* It provides both authentication and authorization.
* It builds on OpenID but uses a JSON Web Token.

### Kerberos

Kerberos is one of the earliest examples of an SSO designed to reduce the need for users to maintain separate accounts across multiple systems, and to reduce the overhead of individual information systems performing identification and authentication.
It is widely implemented in modern information systems including Microsoft AD.

In a Kerberos environment, applications or systems that have been “kerberized” instead rely on the Kerberos server to authenticate users. Information is exchanged via tickets, which identify if a user is authentic and if they should be granted access to specific resources.
User authenticity is proven using symmetric encryption, which requires users to maintain control over their secret key in order to authenticate identity.

#### Kerberos Components

Kerberos uses several different elements that are important to understand:

* **Key Distribution Center**
The Key Distribution Center is the trusted third party that provides authentication services. Kerberos uses symmetric-key cryptography to authenticate clients to servers.
All clients and servers are registered with the KDC, and it maintains the secret keys for all network members.

* **Kerberos Authentication Server**
The authentication server hosts the functions of the KDC: a ticket-granting service (TGS) and an authentication service (AS). However, it is possible to host the ticket-granting service on another server.
The authentication service verifies or rejects the authenticity and timeliness of tickets. This server is often called the KDC.

* **Ticket**
A ticket is an encrypted message that provides proof that a subject is authorized to access an object. It is sometimes called a service ticket (ST).
Subjects (such as users) request tickets to access objects (such as files), and if they have authenticated and are authorized to access the object, Kerberos issues them a ticket.
Kerberos tickets have specific lifetimes and usage parameters. Once a ticket expires, a client must request a renewal or a new ticket to continue communications with any server.

* **Ticket-Granting Ticket**
A ticket-granting ticket (TGT) provides proof that a subject has authenticated through a KDC and is authorized to request tickets to access other objects.
A TGT is encrypted and includes a symmetric key, an expiration time, and the user’s IP address. Subjects present the TGT when requesting tickets to access objects.

* **Kerberos Principal**
Kerberos issues tickets to Kerberos principals. A Kerberos principal is typically a user but can be any entity that can request a ticket.

* **Kerberos Realm**
Generically, a realm is an area controlled or ruled by something. A Kerberos realm is a logical area (such as a domain or network) ruled by Kerberos. Principals within the realm can request tickets from Kerberos, and Kerberos can issue tickets to principals in the realm.

#### Kerberos Authentication Process

The Kerberos login process works as follows:
1. The user types a username and password into the client.
2. The client encrypts the username with AES for transmission to the KDC.
3. The KDC verifies the username against a database of known credentials.
4. The KDC generates a symmetric key that will be used by the client and the Kerberos server. It encrypts this with a hash of the user’s password. The KDC also generates an encrypted timestamped TGT.
5. The KDC then transmits the encrypted symmetric key and the encrypted timestamped TGT to the client.
6. The client installs the TGT for use until it expires. The client also decrypts the symmetric key using a hash of the user’s password.

#### Kerberos Authorization Process

When a client wants to access an object, such as a resource hosted on the network, it must request a ticket through the Kerberos server. The following steps are involved in this process:
1. The client sends its TGT back to the KDC with a request for access to the resource.
2. The KDC verifies that the TGT is valid and checks its access control matrix to verify that the user has sufficient privileges to access the requested resource.
3. The KDC generates a service ticket and sends it to the client.
4. The client sends the ticket to the server or service hosting the resource.
5. The server or service hosting the resource verifies the validity of the ticket with the KDC.
6. Once identity and authorization are verified, Kerberos activity is complete. The server or service host then opens a session with the client and begins communications or data transmission.

### Remote Authentication Dial-In User Service/Terminal Access Controller Access Control System Plus

#### RADIUS

Remote authentication dial-in user service (RADIUS) was originally designed in the early 1990s, as evidenced by the name containing dial-in.
At that time, remote access typically meant utilizing a modem and traditional phone line, but the authentication, authorization, and accounting (AAA) functions it provides are implemented in many modern systems like 802.1X authentication, which is both widely supported and used by modern desktop and smartphone operating systems.
RADIUS accepts remote user credentials and performs authentication to enforce access control and also provides accounting of remote sessions like the amount of data transferred.
The RADIUS standard is specified in IETF RFC 2865, available at https://datatracker.ietf.org/doc/html/rfc2865.

##### RADIUS Callback

The RADIUS server can use callback security for an extra layer of protection. Users call in, and after authentication, the RADIUS server terminates the connection and initiates a call back to the user’s predefined phone number.
If a user’s authentication credentials are compromised, the callback security prevents an attacker from using them.

##### RADIUS Protocols and Ports

RADIUS uses the User Datagram Protocol (UDP) by default and encrypts only the password’s exchange. It doesn’t encrypt the entire session, but RADIUS can use other protocols to encrypt the data session.
The current version is defined in RFC 2865. RFC 6614, designated as Experimental, defines how RADIUS can use Transport Layer Security (TLS) over Transmission Control Protocol (TCP).

When using TLS, RADIUS uses TCP port 2083. RADIUS uses UDP port 1812 for RADIUS messages and UDP port 1813 for RADIUS Accounting messages.

#### TACACS+

Another protocol that provides AAA functionality is the Terminal Access Controller Access Control System Plus (TACACS+), which was originally designed by Cisco systems.
TACACS+ is generally implemented to control access to network infrastructure resources like routers and enables users logging in to perform maintenance and other administrative functions.
It supports authenticating users and provides a centralized method for authorizing user access, as well as auditing of user access and actions. It is described in IETF RFC 8907 at datatracker.ietf.org/doc/html/rfc8907.

It separates authentication, authorization, and accounting into separate processes, which can be hosted on three different servers if desired.
Additionally, TACACS+ encrypts all of the authentication information, not just the password, as RADIUS does. TACACS+ uses TCP port 49, providing a higher level of reliability for the packet transmissions.
