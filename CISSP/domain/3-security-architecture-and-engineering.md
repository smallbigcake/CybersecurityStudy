# Security Architecture and Engineering

## RESEARCH, IMPLEMENT, AND MANAGE ENGINEERING PROCESSES USING SECURE DESIGN PRINCIPLES

System and application development generally consists of the following stages:
* Design
* Development
* Testing
* Implementation
* Maintenance
* Decommissioning

While this is often necessary, it is best that security be incorporated into the design process (and updated over time, as necessary) for two primary reasons:
* It is less expensive to incorporate security when the overall functional system design is developed rather than trying to add it on later (which will often require redesign, if not reengineering, of already developed components).
* The need for security controls is not just to prevent the user from performing unauthorized actions, but to prevent components of the system itself from violating security requirements when acting on the user’s requests.
If security is not intrinsic to the overall design, it is not possible to completely mediate all the activities that can compromise security.

Fundamental to any security architecture, regardless of the design principles employed, are the basic requirements outlined in 1972 by James Anderson in Computer Security Technology Planning Study (USAF):
* Security functions need to be implemented in a manner that prevents their being bypassed, circumvented, or tampered with.
* Security functions need to be invoked whenever necessary to implement the security control.
* Security functions need to be as small as possible so that defects are more likely to be found.

### ISO/IEC 19249

In 2017, the International Organization for Standardization (ISO) published its first revision of standard 19249, “Information technology - Security techniques - Catalogue of architectural and design principles for secure products, systems and applications.”

The aim of ISO 19249 is to describe architectural and design principles to be used to foster the secure development of systems and applications. ISO 19249 specifies five architectural principles and five design principles.

The five architectural principles from ISO/IEC 19249 are as follows:
* Domain separation
* Layering
* Encapsulation
* Redundancy
* Virtualization

* The five design principles from ISO/IEC 19249 are as follows:
* Least privilege
* Attack surface minimization
* Centralized parameter validation
* Centralized general security services
* Preparing for error and exception handling

#### ISO/IEC 19249 Architectural Principles

ISO/IEC 19249’s architectural principles are examined in the following five sections.

##### Domain Separation

A domain is a concept that describes enclosing a group of components together as a common entity. As a common entity, these components, be they resources, data, or applications, can be assigned a common set of security attributes.

The principle of domain separation involves the following:
* Placing components that share similar security attributes, such as privileges and access rights, in a domain. That domain can then be assigned the necessary controls deemed pertinent to its components.
* Only permitting separate domains to communicate over well-defined and (completely) mediated communication channels (e.g. application programming interfaces, or APIs).

Examples where domain separation is used in the real world include the following:
* A network is separated into manageable and logical segments. Network traffic (inter-domain communication) is handled according to policy and routing control, based on the trust level and workflow between segments.
* Data is separated into domains in the context of classification, categorization, and security baseline. Even though data might come from disparate sources, if that data is classified at the same level, the handling and security of that classification level (domain) is accomplished with like security attributes.

##### Layering

Layering is the hierarchical structuring of a system into different levels of abstraction, with higher levels relying upon services and functions provided by lower levels, and lower levels hiding (or abstracting) details of the underlying implementation from higher levels.

Layering is seen in network protocols, starting with the classic OSI seven-layer model running from physical through to application layers.

The purpose of layering is to do the following:
* Create the ability to impose specific security policies at each layer
* Simplify functionality so that the correctness of its operation is more easily validated

From a security perspective:
* Higher levels always have the same or less privilege than a lower level.
* If layering to provide security controls, it must not be possible for a higher level to bypass an intermediate level.
For example, if a program is able to bypass the filesystem layer and issue direct block-level I/O requests to the underlying disk storage device, then the security policies (i.e., file permissions) enforced by the filesystem layer will be for naught.

##### Encapsulation

Encapsulation is an architectural concept where objects are accessed only through functions that logically separate functions that are abstracted from their underlying object by inclusion or information hiding within higher level objects.

##### Redundancy

Redundancy is designing a system with replicated components, operating in parallel, so that the system can continue to operate in spite of errors or excessive load.
From a security perspective, redundancy is an architectural principle for addressing possible availability and integrity compromises or issues.

Examples where redundancy is used in the real world include the following:
* High availability solutions such as a cluster, where one component or system takes over when its active partner becomes inaccessible
* Having storage in redundant array of inexpensive disks (RAID) configurations where the data is made redundant and fault tolerant
* Cloud-based storage, where data is replicated across multiple data centers, zones, or regions

##### Virtualization

Virtualization is a form of emulation in which the functionality of one real or simulated device is emulated on a different one.

#### ISO/IEC 19249 Design Principles

##### Least Privilege

The principle of least privilege asserts that access to information should only be granted on an as-needed basis (i.e., a subject should only be granted the privileges needed to complete an assigned or authorized task).
Every process, service, or individual ought to operate with only those permissions absolutely necessary to perform the authorized activities and only for as long as necessary and no more.

By limiting permissions, one limits the damage that can be done should a mistake, defect, or compromise cause an undesired action to be attempted.

Granting permissions based on the principle of least privilege is the implementation of the concept of need-to-know, restricting access and knowledge to only those items necessary for the authorized task.

##### Attack Surface Minimization

A system’s attack surface is the sum of all possible security risk exposures through which an attacker may compromise the system - think of this as the number of doors and windows on a house through which a burglar may enter.
The more entry points, the greater the attack surface.

System hardening, the disabling and/or removal of unneeded services and components, is a form of attack surface minimization.
This can involve blocking network ports, removing system daemons, and otherwise ensuring that the only services and programs that are available are the minimum set necessary for the system to function as required.
In our house example, hardening may include adding locks to doors, bars to windows, and a guard dog out front.

##### Centralized Parameter Validation

As will be discussed later in this chapter in the discussion of common system vulnerabilities, many threats involve systems accepting improper inputs.

Since ensuring that parameters are valid is common across all components that process similar types of parameters, using a single library to validate those parameters enables the necessary capability to properly review and test that library.

Full parameter validation is especially important when dealing with user input, or input from systems to which users input data.
Invalid or malformed data can be fed to the system, either unwittingly, by inept users, or intentionally by malicious attackers.

Examples where centralized parameter validation is used in the real world include the following:
* Validating input data by secure coding practices
* Screening data through an application firewall

##### Centralized General Security Services

The principle of centralizing security services can be implemented at several levels. At the operating system level, your access control, user authentication and authorization, logging, and key management are all examples of discrete security services that can and should be managed centrally.
Simplifying your security services interface instead of managing multiple interfaces is a sensible benefit.

The centralized general security services principle is a generalization of the previously discussed centralized parameter validation principle: by implementing commonly used security functions once, it is easier to ensure that the security controls have been properly reviewed and tested.

It is also more cost-effective to concentrate one’s efforts on validating the correct operation of a few centralized services rather than on myriad implementations of what is essentially the same control.

Examples where centralized security services are used in the real world include the following:
* Centralized access control server
* Centralized cryptographic processing
* Security information and event management (SIEM)
* Security orchestration, automation, and response (SOAR)

##### Preparing for Error and Exception Handling

Errors happen. Systems must ensure that errors are detected and appropriate action taken, whether that is to just log the error or to take some action to mitigate the impact of the issue.

Error handling should not leak information, for example, by displaying stack traces or internal information in error reports that might disclose confidential information or provide information useful to an attacker.

Systems must be designed to fail safe (as discussed later) and to always remain in a secure state, even when errors occur.

Errors can also be indicators of compromise. Detecting and reporting such errors can enable a quick response that limits the scope of the breach.

### Threat Modeling

Threat modeling is a process by which potential security threats and vulnerabilities can be identified, and mitigations can be prioritized.
Threat modeling can be used to help securely develop applications or to help reduce risk in an already deployed application.

There are numerous approaches to threat modeling, but three of the most commonly used are called STRIDE, DREAD, and PASTA.

#### STRIDE
STRIDE is a model developed at Microsoft in the late ‘90s to help identify and classify computer security threats.

The name itself is a mnemonic for the following six categories of security threats:
* **Spoofing:** Spoofing is an attack during which a person or system assumes the identity of another person or system by falsifying information.
Strong passwords, multifactor authentication, and digital signatures are common controls to protect against spoofing.
* **Tampering:** Data tampering is an attack on the integrity of data by maliciously manipulating data.
Strong access controls and thorough logging and monitoring are good ways to prevent and detect data tampering.
* **Repudiation:** Repudiation is the ability of a party to deny that they are responsible for performing an action. Repudiation threat occurs when a user claims that they did not perform an action, and there is no evidence to prove otherwise.
Digital signatures and secure logging and auditing are the primary controls to provide nonrepudiation.
* **Information disclosure:** Information disclosure — commonly referred to as a data leak - occurs when information is improperly shared with an unauthorized party.
Encryption, data loss prevention (DLP), and strong access controls are common controls to protect against information disclosure.
* **Denial of service (DoS):** A denial-of-service (DoS) attack involves a malicious actor rendering a system or service unavailable by legitimate users.
System redundancy, network filtering, and resource limits are common protections against DoS attacks.
* **Elevation of privilege:** Elevation of privilege (or privilege escalation) occurs when an unprivileged application user is able to upgrade their privileges to those of a privileged user (such as an administrator).
Strong access control and input validation are common protections against privilege escalation.

#### DREAD
The DREAD model, developed in 2002, is a quantitative risk analysis model that involves rating the severity of security threats by assigning numeric values (typically from 1 to 10) that represent different levels of severity.

DREAD is a mnemonic that describes the five key points and associated questions that you must answer for any given threat:
* **Damage:** What is the total amount of damage the threat is capable of causing to your business?
* **Reproducibility:** How easily can an attack on the particular threat be replicated?
* **Exploitability:** How much effort is required for the threat to be exploited by an attacker?
* **Affected users:** How many people, either inside or outside of your organization, will be affected by the security threat?
* **Discoverability:** How easily can the vulnerability be found?

Once each of these categories is rated, the sum is then calculated. The sum of all ratings for a given risk can be used to prioritize different risks.

#### PASTA

The Process for Attack Simulation and Threat Analysis (PASTA) is a seven-step risk-based threat model, developed in 2012, that supports dynamic threat analysis.
Unlike STRIDE, which is strictly intended as a framework for threat identification, the PASTA methodology provides a robust process for identifying and mitigating threats.
PASTA integrates business objectives with technical requirements, system risks, and attack modeling.

The PASTA model is intended to provide an attacker-centric perspective of the application and infrastructure and help security teams develop a mitigation strategy based on threat enumeration and impact analysis.
These are the seven stages of the PASTA methodology:

1. **Define objectives.**

    During this first stage, key business objectives are defined, and critical security and compliance requirements are identified.
    In addition, a preliminary business impact analysis (BIA) is conducted to identify potential business impact considerations.

2. **Define technical scope.**

    During this stage, the boundaries of the technical environment and the scope of all technical assets for which threat analysis is needed are defined.
    In addition to the application boundaries, you must discover and document all infrastructure, application, and software dependencies.
    The goal is to capture a high-level but comprehensive view of all servers, hosts, devices, applications, protocols, and data that need to be protected.

3. **Application decomposition.**

    During this stage, an evaluation of all assets (i.e., the application components) needs to be conducted, and the data flows between these assets need to be identified.
    As part of this process, all application entry points and trust boundaries should be identified and defined.
    This stage is intended to establish a clear understanding of all data sources, the parties that access those data sources, and all use cases for data access within the application - in other words, who should perform what actions on which components of the application.

4. **Threat analysis.**

    This stage is intended to identify and analyze threat information from within the system, such as SIEM feeds, web application firewall (WAF) logs, etc., as well as externally available threat intelligence that is related to the system.
    Threat-attack scenarios that are relevant to the specific application, environment, and data should be identified and understood. The output of this stage should include a list of the most likely attack vectors for the given application or system.

5. **Vulnerability analysis.**

    During this stage, all vulnerabilities within the application’s code should be identified and correlated to the threat-attack scenarios identified in step 4.
    Operating system, application, network, and database scans should be conducted, and dynamic and static code analysis results should be evaluated to enumerate and score existing vulnerabilities.
    The primary output of this stage is a correlated mapping of all threat-attack vectors to existing vulnerabilities and impacted assets.

6. **Attack modeling.**

    During this stage, attacks that could exploit identified vulnerabilities (from step 5) are modeled and simulated.
    This helps determine the likelihood and impact of each identified attack vector.
    After this stage, your organization should have a strong understanding of your application’s attack surface (i.e., what bad things could happen to which assets within your application environment).

7. **Risk and impact analysis.**

    During this final stage, your business impact analysis (from step 1) should be refined based on all the analysis performed in the previous six steps.
    Risks should be prioritized for remediation, and a risk mitigation strategy should be developed to identify countermeasures for all residual risks.

### Secure Defaults

The concept of secure defaults (or secure-by-default) essentially means that systems should be designed with the best security possible without users needing to turn on security features or otherwise think about security configurations.

Secure-by-default means that a system’s default configuration includes the most secure settings possible, which may not always be the most highly functioning settings.

### Fail Securely

It’s essential to consider how your systems will behave if an error or exception should occur.
For some systems, a fail-open design, where systems continue to allow access when exceptions occur, may be preferable to ensure that access to important information remains readily available during a system error or exception.
Conversely, a fail-secure (also known as a fail-safe or fail-closed) system blocks access by default, ensuring that security is prioritized over availability.

For systems with sensitive data, security controls should be designed such that in the absence of specific configuration settings to the contrary, the default is to not permit the action.
Access should be based on permission (e.g., allowed list), not exclusion (e.g., blocked list). This is the principle behind “deny all” default firewall rules and also relates to the concept of least privileged (discussed in an earlier section).

Generally speaking, it is best to design systems so that if an error is detected, the system fails in a deny (or safe) state of higher security rather than failing in an open, less secure state.

### Separation of Duties

Separation of duties (SoD) requires two (or more) actions, actors, or components to operate in a coordinated manner to perform a security-sensitive operation.

### Keep It Simple

Complexity is the enemy of security. The simpler and smaller the system, the easier it is to design, assess, and test.
When the system as a whole cannot be simplified sufficiently, consider partitioning the problem so that the components with the most significant risks are separated and simplified to the extent possible.

This is the concept behind a security kernel - a small separate subsystem with the security-critical components that the rest of the system can rely upon.

### Trust, but Verify

In the information security world, “trust, but verify” has been used to describe the use of perimeter firewalls and other controls that use a party’s identity, location, and other characteristics to verify that they are a trusted user or system from a trusted location
- in other words, “trust, but verify” assumes everything behind your corporate firewall is safe and verifies that anything passing through that firewall into your network is safe to allow in essentially, “verify once, trust forever.”

This model of security has become less-preferred in recent years, in favor of the zero trust model (discussed in the next section).

The phrase “trust, but verify” may also be used colloquially when dealing with third parties or when describing the need to validate the operation and effectiveness of internal security controls.
If there is a single security concept that comes to mind when discussing “trust, but verify,” it might be the concept of auditing.

When working with third parties (such as partners, cloud providers, or anyone else outside of your organization), a certain level of trust is required in order to execute day-to-day business operations.
The notion of “verify” comes in when you consider the need to periodically audit those relationships to ensure they continue operating as agreed upon and expected.

When looking inward, “trust, but verify” also plays a large role in how we assess and monitor our security architecture to ensure ongoing compliance and secure functionality - there should never be a “set-and-forget” approach to security controls.

“Trust, but verify” also shows up in our use of threat intelligence products and information to determine whether a potential threat is viable. Ultimately, the concept of “trust, but verify” is yet another reminder that maintaining security is a never-ending task.

### Zero Trust

Zero trust architecture was first described in the early 2010s and has since become a mainstream approach to secure system architecture, with the National Institute of Standards and Technology (NIST) formalizing guidance, in 2020, in NIST SP 800-207, “Zero Trust Architecture.”

Zero trust is a security model that is predicated on the idea that an organization should not automatically trust anything outside or inside its perimeters - instead, they must verify anything and everything trying to connect to its systems before allowing access.
This model is a drastic departure from the previously mentioned “trust, but verify” model that involves fiercely defending your perimeters while assuming anything inside your network is safe.

The zero trust model preaches a “never trust, always verify” mindset that requires every access request to be fully authenticated, authorized, and encrypted before granting access.

With this approach, an attacker who successfully breaches your perimeter is much less able to move laterally within your network, because every device is protected from the others, thus reducing the blast radius (or total impact) of a successful compromise.

The zero trust model is based on the following core principles:
* Always verify. Authenticate and authorize every access request based on user identity, location, system health (e.g., patch levels), data classification, user behavior analytics, and any other available data points.
* Use least privilege access. Always assign the minimum rights required for the specific access requested, on a Just in Time (JIT) basis.
* Assume breach. Instead of trusting devices on your network, assume the worst-case scenario (i.e., that you’ve already been breached) and minimize the blast radius to prevent further damage.

### Privacy by Design

Privacy by Design (abbreviated PbD) is a systems engineering approach, initially developed by former Information and Privacy Commissioner of Ontario, Ann Cavoukian, in the 1990s and later formalized into a framework in 2009;
the framework focuses on extending the use of privacy-enhancing technologies and establishes seven foundational principles (discussed next).

Privacy-enhancing technologies (PETs) are technologies that support data protection and PbD by minimizing personal data use and maximizing data security.

PbD involves building privacy directly into the design, operation, and management of a system or process, rather than considering privacy after the fact.
The seven PbD principles aim to ensure privacy of personal data while also giving users more control over their personal information.

Those seven principles, as identified by Cavoukian, are summarized here:

1. Proactive not Reactive; Preventative not Remedial:
Design systems and processes to proactively take action before a privacy incident, not afterward.
In other words, anticipate and prevent invasive privacy events before they happen, rather than relying on detecting and responding to them once they already occur.
As you design and develop your systems, you should determine what privacy risks exist and plan for them, rather than putting out privacy fires later.

2. Privacy as the Default Setting:
Ensure that all personal data is automatically protected in all IT systems or business processes, with no added action required by any individual.
This principle places the responsibility for privacy on the system, rather than on the individual.
Practical examples include anonymizing or masking personal information, restricting access to personal information to those who absolutely need it (i.e., least privilege), and deleting such information when it is no longer needed.

3. Privacy Embedded into Design:
Privacy measures should be fully integrated components of the system and associated processes, rather than added on after the fact; privacy should be treated as a core functionality of the system.
Examples of this principle include building encryption and authentication mechanisms into your system, rather than finding ways to add these functionalities in afterwards.

4. Full Functionality - Positive - Sum, not Zero-Sum:
PbD encourages a “win-win” approach to all legitimate system design goals and discourages unnecessary trade-offs being made.
Both privacy and security are important - both can and should be achieved. For example, internet cookies provide necessary web functionality, and they can be implemented in a secure and private manner.

5. End-to-End Security - Full Lifecycle Protection:
Ensure security and privacy of personal data from cradle to grave; data should be created, managed, and destroyed in a secure fashion.
Encryption and authentication are standard at every stage, but you should pay close attention to what security and privacy mechanisms may be required throughout the data lifecycle.

6. Visibility and Transparency - Keep it Open:
This is a “trust, but verify” principle (discussed earlier) that seeks to assure all stakeholders that the system operates securely and maintains data privacy as intended.
The clearest example of this principle is establishing a well-documented privacy policy that is shared with all impacted parties.

7. Respect for User Privacy - Keep it User-Centric:
When it’s all said and done, privacy is about the user, and this principle reinforces that notion.
System architects, developers, and operators must keep the interests of the individual as their utmost priority by providing strong privacy defaults, appropriate notice, and a user-friendly experience.
One of the most practical ways to keep privacy user-centric is by requiring the user to take action (e.g., by clicking a button or ticking a check box) in order to give consent.

### Shared Responsibility

The shared responsibility model is a cloud security framework that describes the obligations of a cloud service provider (CSP) and its customers in keeping cloud systems and data secure.

In a traditional data center model, your organization is responsible for security across your entire environment - all applications, servers, physical assets, and so on.

In a cloud environment, the CSP takes on much of the operational burden, including a great deal of security responsibility - but not all of it.
The specific breakdown of responsibility varies by cloud provider and by cloud service type.

### Defense in Depth

Defense in depth (or layered security) is the concept of applying multiple, distinct layers of security technologies and strategies to achieve greater overall protection.
In the context of information security, the U.S. National Security Agency (NSA) first used the phrase to describe the use of multiple types, locations, and layers of defense combined with the ability to detect and analyze breaches for prompt reaction and mitigation.

By using combinations of security controls, the impact from the failure of any single control can be reduced if not eliminated.
Many of the security principles mentioned earlier are types of defense in depth.

Defense in depth is related to the concept of assumption of breach, which means managing security on the assumption that one or more security controls have already been compromised.
The assumption of breach mindset shifts thinking from being simply focused on defending the perimeter (or perimeters) to a balanced approach of establishing multiple defenses so that the compromise of one control does not immediately lead to a successful breach and of considering detection and mitigation to be as important as prevention.

### Techniques for Ensuring CIA

#### Confinement

Software designers use process confinement to restrict the actions of a program. Simply put, process confinement allows a process to read from and write to only certain memory locations and resources.
This is also known as sandboxing. It is the application of the principle of least privilege to processes. The goal of confinement is to prevent data leakage to unauthorized programs, users, or systems.

The operating system, or some other security component, disallows illegal read/write requests. If a process attempts to initiate an action beyond its granted authority, that action will be denied.
In addition, further actions, such as logging the violation attempt, may be taken. Generally, the offending process is terminated.
Confinement can be implemented in the operating system itself (such as through process isolation and memory protection), through the use of a confinement application or service (for example, Sandboxie at sandboxie. com), or through a virtualization or hypervisor solution (such as VMware or Oracle’s VirtualBox).

#### Bounds

Each process that runs on a system is assigned an authority level. The authority level tells the operating system what the process can do.

In simple systems, there may be only two authority levels: user and kernel. The authority level tells the operating system how to set the bounds for a process.
The bounds of a process consist of limits set on the memory addresses and resources it can access. The bounds state the area within which a process is confined or contained.

In most systems, these bounds segment logical areas of memory for each process to use. It is the responsibility of the operating system to enforce these logical bounds and to disallow access to other processes.

More secure systems may require physically bounded processes. Physical bounds require each bounded process to run in an area of memory that is physically separated from other bounded processes, not just logically bounded in the same memory space.
Physically bounded memory can be very expensive, but it’s also more secure than logical bounds. Bounds can be a means to enforce confinement.

#### Isolation

When a process is confined through enforcing access bounds, that process runs in isolation.
Process isolation ensures that any behavior will affect only the memory and resources associated with the isolated process.

Isolation is used to protect the operating environment, the kernel of the operating system, and other independent applications.
Isolation is an essential component of a stable operating system.
Isolation is what prevents an application from accessing the memory or resources of another application, whether for good or ill.
Isolation allows for a fail-soft environment so that separate processes can operate normally or fail/crash without interfering or affecting other processes.
Isolation is achieved through the enforcement of containment using bounds.

#### Summary of Confinement, Bounds, and Isolation

These three concepts (confinement, bounds, and isolation) make designing secure programs and operating systems more difficult, but they also make it possible to implement more secure systems.

Confinement is making sure that an active process can only access specific resources (such as memory).
Bounds is the limitation of authorization assigned to a process to limit the resources the process can interact with and the types of interactions allowed.
Isolation is the means by which confinement is implemented through the use of bounds.

The goals of the concepts is the ensure that the predetermined scope of resource access is not violated and any failure or compromise of a process has minimal to no affect on any other process.

#### Access Controls

To ensure the security of a system, you need to allow subjects to access only authorized objects. Access controls limit the access of a subject to an object.
Access rules state which objects are valid for each subject. Further, an object might be valid for one type of access and be invalid for another type of access.
There are a wide range of options for access controls, such as discretionary, role-based, and mandatory.

#### Trust and Assurance

A **trusted system** is one in which all protection mechanisms work together to process sensitive data for many types of users while maintaining a stable and secure computing environment.
In other words, trust is the presence of a security mechanism, function, or capability.

**Assurance** is the degree of confidence in satisfaction of security needs.
In other words, assurance is how reliable the security mechanisms are at providing security.

Assurance must be continually maintained, updated, and reverified. This is true if the secured system experiences a known change (good or bad—i.e., a vendor patch or a malicious exploit) or if a significant amount of time has passed.
In either case, change has occurred at some level. Change is often the antithesis of security; it often diminishes security.
This is why change management, patch management, and configuration management are so important to security management.

Assurance varies from one system to another and often must be established on individual systems.
However, there are grades or levels of assurance that can be placed across numerous systems of the same type, systems that support the same services, or systems that are deployed in the same geographic location.
Thus, trust can be built into a system by implementing specific security features, whereas assurance is an assessment of the reliability and usability of those security features in a real-world situation.


## UNDERSTAND THE FUNDAMENTAL CONCEPTS OF SECURITY MODELS

A model is a hypothetical abstraction of a system, simplified to enable analysis of certain aspects of the system without the complexity and details of the entire system being analyzed.
A security model is a model that deals with security policy.

Security models can be formal, intended for mathematical analysis to assist in the verification that a system complies with a specific policy, or they can be informal, serving to illustrate and simplify the assessment of a system without the rigor of a proof.

Security models can be useful tools during requirements development, information asset classification and categorization, and also during system analysis and testing.

The structured approach of codifying security requirements in a security model can help reduce ambiguity and potential misunderstanding as to what, exactly, a security architecture is trying to accomplish.

It distills the essential requirements into clear rules and analyzes the design to ensure that those rules are adhered to at every step in the process.
Ensuring that a security architecture conforms to a well-designed security model greatly strengthens it.

### Primer on Common Model Components

#### Finite State Machine

A finite state machine (or just state machine) is a conceptual computer that can be in one of a finite number of states.
The computer implements a state transition function that determines the next state, given the current state and the next input and that can, optionally, produce output.

#### Lattice

A lattice is a finite set with a partial ordering. A partial ordering is a binary relation that is reflexive, anti-symmetric, and transitive.
Reflexive means that each item in the set is comparable to itself.
Anti-symmetricmeans that no two different elements precede each other. Transitive means that if a yields b, and b yields c, then a yields c.

In short, a lattice security model does the following:
* Defines a set of security levels
* Defines a partial ordering of that set
* Assigns every subject (e.g., user or process) and object (e.g., data) a security level
* Defines a set of rules governing the operations a subject can perform on an object based on the relationship between the security levels of the subject and object

### Trusted Computing Base Model

The trusted computing base (TCB) design principle is the combination of hardware, software, and controls that work together to form a trusted base to enforce your security policy.
The TCB is a subset of a complete information system. It should be as small as possible so that a detailed analysis can reasonably ensure that the system meets design specifications and requirements.

The TCB is the only portion of that system that can be trusted to adhere to and enforce the security policy.
It is the responsibility of TCB components to ensure that a system behaves properly in all cases and that it adheres to the security policy under all circumstances.

### Security Perimeter

The security perimeter of your system is an imaginary boundary that separates the TCB from the rest of the system (Figure 8.2). This boundary ensures that no insecure communications or interactions occur between the TCB and the remaining elements of the computer system.

For the TCB to communicate with the rest of the system, it must create secure channels, also called **trusted paths**.
A trusted path is a channel established with strict standards to allow necessary communication to occur without exposing the TCB to security exploitations.

A security perimeter may also allow for the use of a **trusted shell**. A trusted shell allows a subject to perform command-line operations without risk to the TCB or the subject.

A trusted shell prevents the subject from being able to break out of isolation to affect the TCB and in turn prevents other processes from breaking into the shell to affect the subject.

### Reference Monitors and Kernels

The part of the TCB that validates access to every resource prior to granting access requests is called the reference monitor.
The reference monitor stands between every subject and object, verifying that a requesting subject’s credentials meet the object’s access requirements before any requests are allowed to proceed.

Effectively, the reference monitor is the access control enforcer for the TCB.
The reference monitor enforces access control or authorization based on the desired security model, whether discretionary, mandatory, role-based, or some other form of access control.

The collection of components in the TCB that work together to implement reference monitor functions is called the security kernel.
The reference monitor is a concept or theory that is put into practice via the implementation of a security kernel in software and hardware.

The purpose of the security kernel is to launch appropriate components to enforce reference monitor functionality and resist all known attacks.
The security kernel mediates all resource access requests, granting only those requests that match the appropriate access rules in use for a system.

### State Machine Model

The state machine model describes a system that is always secure no matter what state it is in.

It’s based on the computer science definition of a finite state machine (FSM).
An FSM combines an external input with an internal machine state to model all kinds of complex systems, including parsers, decoders, and interpreters.

Given an input and a state, an FSM transitions to another state and may create an output.

Mathematically, the next state is a function of the current state and the input
> the next state = F(input, current state).

Likewise, the output is also a function of the input and the current state
> the output = F(input, current state).

According to the state machine model, a state is a snapshot of a system at a specific moment in time. If all aspects of a state meet the requirements of the security policy, that state is considered secure.

A transition occurs when accepting input or producing output. A transition always results in a new state (also called a state transition). All state transitions must be evaluated.

If each possible state transition results in another secure state, the system can be called a secure state machine.
A secure state machine model system always boots into a secure state, maintains a secure state across all transitions, and allows subjects to access resources only in a secure manner compliant with the security policy.

The secure state machine model is the basis for many other security models.

### Information Flow Model

The information flow model focuses on controlling the flow of information. Information flow models are based on the state machine model.
Information flow models don’t necessarily deal with only the direction of information flow; they can also address the type of flow.

Information flow models are designed to prevent unauthorized, insecure, or restricted information flow, often between different levels of security (known as multilevel models).
Information flow can be between subjects and objects at the same or different classification levels. An information flow model allows all authorized information flows, and prevents all unauthorized information flows.

Another interesting perspective on the information flow model is that it is used to establish a relationship between two versions or states of the same object when those two versions or states exist at different points in time.
Thus, information flow dictates the transformation of an object from one state at one point in time to another state at another point in time. The information flow model also addresses covert channels by specifically excluding all undefined flow pathways.

### Noninterference Model

The noninterference model is loosely based on the information flow model.
However, instead of being concerned about the flow of information, the noninterference model is concerned with how the actions of a subject at a higher security level affect the system state or the actions of a subject at a lower security level.

Basically, the actions of subject A (high) should not affect or interfere with the actions of subject B (low) or even be noticed by subject B.
If such violations occur, subject B may be placed into an insecure state or be able to deduce or infer information about a higher level of classification.
This is a type of information leakage and implicitly creates a covert channel. Thus, the noninterference model can be imposed to provide a form of protection against damage caused by malicious programs, such as Trojan horses, backdoors, and rootkits.

### Take-Grant Model

The take-grant model employs a directed graph (Figure 8.3) to dictate how rights can be passed from one subject to another or from a subject to an object.
Simply put, a subject (X) with the grant right can grant another subject (Y) or another object (Z) any right that subject (X) possesses.
Likewise, a subject (X) with the take right can take a right from another subject (Y).

In addition to these two primary rules, the take-grant model has a create rule and a remove rule to generate or delete rights.
The key to this model is that using these rules allows you to figure out when rights in the system can change and where leakage (that is, unintentional distribution of permissions) can occur.

In essence, here are the four rules of the take-grant model:
* Take rule: Allows a subject to take rights over an object
* Grant rule: Allows a subject to grant rights to an object
* Create rule: Allows a subject to create new rights
* Remove rule: Allows a subject to remove rights it has

### Access Control Matrix

An access control matrix is a table of subjects and objects that indicates the actions or functions that each subject can perform on each object.
Each column of the matrix is an access control list (ACL) pulled from objects. Once sorted, each row of the matrix is a capabilities list for each listed subject.

An ACL is tied to an object; it lists the valid actions each subject can perform. A capability list is tied to the subject; it lists valid actions that can be taken on each object included in the matrix.

### Bell–LaPadula Model

The U.S. Department of Defense (DoD) developed the Bell–LaPadula model in the 1970s based on the DoD’s multilevel security policies.
The multilevel security policy states that a subject with any level of clearance can access resources at or below its clearance level.
However, within clearance levels, access to compartmentalized objects is granted only on a need-to-know basis.

By design, the Bell–LaPadula model prevents the leaking or transfer of classified information to less secure clearance levels.
This is accomplished by blocking lower-classified subjects from accessing higher-classified objects.
With these restrictions, the Bell–LaPadula model is focused on maintaining confidentiality and does not address any other aspects of object security.

This model is built on a state machine concept and the information flow model.
It also employs mandatory access controls and is a lattice-based access control concept.
The lattice tiers are the classification levels defined by the security policy of the organization.

There are three basic properties of this state machine:
* The Simple Security Property states that a subject may not read information at a higher sensitivity level (no read-up).
* The * (star) Security Property states that a subject may not write information to an object at a lower sensitivity level (no write-down). This is also known as the Confinement Property.
* The Discretionary Security Property states that the system uses an access matrix to enforce discretionary access control.

These first two properties define the states into which the system can transition. No other transitions are allowed.
All states accessible through these two rules are secure states. Thus, Bell–LaPadula–modeled systems offer state machine model security.

The Bell–LaPadula properties are in place to protect data confidentiality.
A subject cannot read an object that is classified at a higher level than the subject is cleared for.
Because objects at one level have data that is more sensitive or secret than data in objects at a lower level, a subject (who is not a trusted subject) cannot write data from one level to an object at a lower level.
That action would be similar to pasting a top-secret memo into an unclassified document file. The third property enforces a subject’s job/role-based need to know in order to access an object.

### Biba Model
The Biba model was designed after the Bell–LaPadula model, but it focuses on integrity.
The Biba model is also built on a state machine concept, is based on information flow, and is a multilevel model. In fact, the Biba model is the inverted Bell–LaPadula model.

The properties of the Biba model are as follows:
* The Simple Integrity Property states that a subject cannot read an object at a lower integrity level (no read-down).
* The * (star) Integrity Property states that a subject cannot modify an object at a higher integrity level (no write-up).

Consider the Biba properties. The second property of the Biba model is pretty straightforward. A subject cannot write to an object at a higher integrity level. That makes sense.

What about the first property? Why can’t a subject read an object at a lower integrity level? The answer takes a little thought.
Think of integrity levels as being like the purity level of air. You would not want to pump air from the smoking section into the clean room environment.

The same applies to data. When integrity is important, you do not want unvalidated data read into validated documents. The potential for data contamination is too great to permit such access.

Biba was designed to address three integrity issues:
* Prevent modification of objects by unauthorized subjects
* Prevent unauthorized modification of objects by authorized subjects
* Protect internal and external object consistency

Biba requires that all subjects and objects have a classification label (it is still a DoD-derived security model). Thus, data integrity protection is dependent on data classification.

Critiques of the Biba model reveal a few drawbacks:
* It addresses only integrity, not confidentiality or availability.
* It focuses on protecting objects from external threats; it assumes that internal threats are handled programmatically.
* It does not address access control management, and it doesn’t provide a way to assign or change an object’s or subject’s classification level.
* It does not prevent covert channels.

### Clark–Wilson Model

The Clark–Wilson model uses a multifaceted approach to enforcing data integrity.
Instead of defining a formal state machine, the Clark–Wilson model defines each data item and allows modifications through only a limited or controlled intermediary program or interface.

The Clark–Wilson model does not require the use of a lattice structure; rather, it uses a three-part relationship of subject/program/object (or subject/transaction/object) known as a triple or an access control triplet.
Subjects do not have direct access to objects. Objects can be accessed only through programs.
Through the use of two principles—well-formed transactions and separation of duties—the Clark–Wilson model provides an effective means to protect integrity.

Clark–Wilson defines the following items and procedures:
* A constrained data item (CDI) is any data item whose integrity is protected by the security model.
* An unconstrained data item (UDI) is any data item that is not controlled by the security model. Any data that is to be input and hasn’t been validated, or any output, would be considered an unconstrained data item.
* An integrity verification procedure (IVP) is a procedure that scans data items and confirms their integrity.
* Transformation procedures (TPs) are the only procedures that are allowed to modify a CDI. The limited access to CDIs through TPs forms the backbone of the Clark–Wilson integrity model.

The Clark–Wilson model uses security labels to grant access to objects, but only through transformation procedures and a restricted interface model.

A restricted interface model uses classification-based restrictions to offer only subject-specific authorized information and functions.

One subject at one classification level will see one set of data and have access to one set of functions, whereas another subject at a different classification level will see a different set of data and have access to a different set of functions.
The different functions made available to different levels or classes of users may be implemented by either showing all functions to all users but disabling those that are not authorized for a specific user or by showing only those functions granted to a specific user.

Through these mechanisms, the Clark–Wilson model ensures that data is protected from unauthorized changes from any user.
In effect, the Clark–Wilson model enforces separation of duties. The Clark–Wilson design makes it a common model for commercial applications.

### Brewer and Nash Model

The Brewer and Nash model was created to permit access controls to change dynamically based on a user’s previous activity (making it a kind of state machine model as well).

This model applies to a single integrated database; it seeks to create security domains that are sensitive to the notion of conflict of interest 
(for example, someone who works at company C who has access to proprietary data for company A should not also be allowed access to similar data for company B if those two companies compete with each other).

This model creates a class of data that defines which security domains are potentially in conflict and prevents any subject with access to one domain that belongs to a specific conflict class from accessing any other domain that belongs to the same conflict class.

Metaphorically, this puts a wall around all other information in any conflict class.
Thus, this model also uses the principle of data isolation within each conflict class to keep users out of potential conflict-of-interest situations (for example, management of company datasets).
Because company relationships change all the time, dynamic updates to members of and definitions for conflict classes are important.

Another way of looking at or thinking of the Brewer and Nash model is of an administrator having full control access to a wide range of data in a system based on their assigned job responsibilities and work tasks.
However, at the moment an action is taken against any data item, the administrator’s access to any conflicting data items is temporarily blocked.
Only data items that relate to the initial data item can be accessed during the operation.
Once the task is completed, the administrator’s access returns to full control.

Brewer and Nash was sometimes known as the Chinese Wall model, but this term is deprecated.
Instead, other terms of “ethical wall” and “cone of silence” have been used to describe Brewer and Nash.

### Goguen–Meseguer Model

The Goguen–Meseguer model is an integrity model, although not as well known as Biba and the others.
In fact, this model is said to be the foundation of noninterference conceptual theories.
Often when someone refers to a noninterference model, they are actually referring to the Goguen–Meseguer model.

The Goguen–Meseguer model is based on predetermining the set or domain (i.e., a list) of objects that a subject can access.
This model is based on automation theory and domain separation.
This means subjects are allowed only to perform predetermined actions against predetermined objects.
When similar users are grouped into their own domain (that is, collective), the members of one subject domain cannot interfere with the members of another subject domain.
Thus, subjects are unable to interfere with each other’s activities.


### Sutherland Model

The Sutherland model is an integrity model. It focuses on preventing interference in support of integrity. It is formally based on the state machine model and the information flow model.

However, it does not directly indicate specific mechanisms for protection of integrity. Instead, the model is based on the idea of defining a set of system states, initial states, and state transitions.
Through the use of only these predetermined secure states, integrity is maintained and interference is prohibited.

A common example of the Sutherland model is its use to prevent a covert channel from being used to influence the outcome of a process or activity.

### Graham–Denning Model

The Graham–Denning model is focused on the secure creation and deletion of both subjects and objects.

Graham–Denning is a collection of eight primary protection rules or actions that define the boundaries of certain secure actions:
* Securely create an object.
* Securely create a subject.
* Securely delete an object.
* Securely delete a subject.
* Securely provide the read access right.
* Securely provide the grant access right.
* Securely provide the delete access right.
* Securely provide the transfer access right.

Usually the specific abilities or permissions of a subject over a set of objects is defined in an access matrix (aka access control matrix).

### Harrison–Ruzzo–Ullman Model

The Harrison–Ruzzo–Ullman (HRU) model focuses on the assignment of object access rights to subjects as well as the resilience of those assigned rights.

It is an extension of the Graham–Denning model. It is centered around the establishment of a finite set of procedures (or access rights) that can be used to edit or alter the access rights of a subject over an object.

The state of access rights under HRU can be expressed in a matrix, where the rows are subjects and the columns are objects (which will include the subjects because they can be objects as well).
The intersection of each row and column will include the specific procedures that each subject is allowed to perform against each object.

Additionally, a finite set of commands or primitives is defined that controls how the matrix can be modified by authorized subjects.
These primitives include adding or removing access rights, subjects, and/or objects from the matrix.

There are also integrity rules, such as: in order to create or add a subject or object to the matrix, it must not already exist; in order to remove a subject or object from the matrix, it must already exist; and if several commands are performed at once, they must all operate successfully or none of the commands will be applied.

## SELECT CONTROLS BASED UPON SYSTEMS SECURITY REQUIREMENTS

Selecting the security controls appropriate for an information system starts with an analysis of the security requirements. The security requirements are determined by the following:

* An analysis of any regulatory or compliance requirements placed on the system 
(e.g., regulatory frameworks such as the Federal Information Security Management Act (FISMA) in the United States; 
privacy legislation such as GDPR in the EU or the Health Insurance Portability and Accountability Act (HIPAA) in the United States; 
contractual obligations such as Payment Card Industry Data Security Standard (PCI DSS); 
or voluntary compliance programs such as ISO 27001 certification or Service Organization Control (SOC) 1/2/3 audits)
* An analysis of the threats the system is likely to face (see the “Understand and Apply Threat Modeling Concepts and Methodologies” section in Chapter 1)
* A risk assessment of the system (see the “Understand and Apply Risk Management Concepts” section in Chapter 1)

If an organization has not yet adopted a certain framework, it is beneficial to start with an established information security framework such as ISO 27001, NIST Special Publication 800-37 “Risk Management Framework,” or the NIST Cybersecurity Framework (CSF), ISA624443, or COBIT 5 (to name a few), as this will help ensure that you have considered the full spectrum of controls and that your process is defined, repeatable, and consistent.

There are a few things to understand about these security frameworks:
* They are not mandatory.
* They are not mutually exclusive of each other.
* They are not exhaustive (i.e., they don’t cover all security concerns).
* They are not the same as a standard or a control list.

Of course, selecting controls is just the beginning. You need to do the following:
* Consider the control and how to implement and adapt it to your specific circumstances (the “Plan” phase)
* Implement the control (the “Do” phase)
* Assess the effectiveness of the control (the “Check” phase)
* Remediate the gaps and deficiencies (the “Act” phase)

In addition to the periodic review of the control selection, the following specific events warrant taking a fresh look at your security controls:
* A security incident or breach
* A significant change in organization structure or major staffing change
* A new or retired product or service
* A new or significantly changed threat or threat actor
* A significant change to an information system or infrastructure
* A significant change to the type of information being processed
* A significant change to security governance, the risk management framework, or policies
* A widespread social, economic, or political change (e.g., COVID-19)

### Common Criteria

The Common Criteria (CC) defines various levels of testing and confirmation of systems’ security capabilities, and the number of the level indicates what kind of testing and confirmation has been performed.
Nevertheless, it’s wise to observe that even the highest CC ratings do not equate to a guarantee that such systems are completely secure or that they are entirely devoid of vulnerabilities or susceptibilities to exploit.

The Common Criteria was designed as a dynamic subjective product evaluation model and replaced previous static systems, such as the U.S. Department of Defense’s Trusted Computer System Evaluation Criteria (TCSEC) and the EU’s Information Technology Security Evaluation Criteria (ITSEC).

A document titled “Arrangement on the Recognition of Common Criteria Certificates in the Field of IT Security” was signed by representatives from government organizations in Canada, France, Germany, the United Kingdom, and the United States in 1998, making the document an international standard.
Since then, 23 additional countries have signed the arrangement.
The original arrangement documentation has been formally adopted as a standard and published as ISO/IEC 15408-1, -2, and -3 and primarily labeled as “Information technology — Security techniques — Evaluation criteria for IT security.”

The objectives of the CC guidelines are as follows:
* To add to buyers’ confidence in the security of evaluated, rated IT products
* To eliminate duplicate evaluations (among other things, this means that if one country, agency, or validation organization follows the CC in rating specific systems and configurations, others elsewhere need not repeat this work)
* To keep making security evaluations more cost-effective and efficient
* To make sure evaluations of IT products adhere to high and consistent standards
* To promote evaluation and increase availability of evaluated, rated IT products
* To evaluate the functionality (in other words, what the system does) and assurance (in other words, how much can you trust the system) of the target of evaluation (TOE)

The Common Criteria process is based on two key elements: protection profiles and security targets.

Protection profiles (PPs) specify for a product that is to be evaluated (the TOE) the security requirements and protections, which are considered the security desires, or the “I want,” from a customer.

Security targets (STs) specify the claims of security from the vendor that are built into a TOE. STs are considered the implemented security measures, or the “I will provide,” from the vendor.

In addition to offering security targets, vendors may offer packages of additional security features.
A package is an intermediate grouping of security requirement components that can be added to or removed from a TOE (like the option packages when purchasing a new vehicle).

This system of the PP and ST allows for flexibility, subjectivity, and customization of an organization’s specific security functional and assurance requirements over time.

An organization’s PP is compared to various STs from the selected vendor’s TOEs. The closest or best match is what the client purchases.
The client initially selects a vendor based on published or marketed evaluation assurance levels (EALs) for currently available systems.

Using Common Criteria to choose a vendor allows clients to request exactly what they need for security rather than having to use static fixed security levels.
It also allows vendors more flexibility on what they design and create.

A well-defined set of Common Criteria supports subjectivity and versatility, and it automatically adapts to changing technology and threat conditions.
Furthermore, the EALs provide a method for comparing vendor systems that is more standardized (like the old TCSEC).

| Level | Assurance level                              | Description                                                                                                                                                                                                                                                                                                                                                               |
|-------|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EAL1  | Functionally tested                          | Applies when some confidence in correct operation is required but where threats to security are not serious. This is of value when independent assurance that due care has been exercised in protecting personal information is necessary.                                                                                                                                |
| EAL2  | Structurally tested                          | Applies when delivery of design information and test results are in keeping with good commercial practices. This is of value when developers or users require low to moderate levels of independently assured security. It is especially relevant when evaluating legacy systems.                                                                                         |
| EAL3  | Methodically tested and checked              | Applies when security engineering begins at the design stage and is carried through without substantial subsequent alteration. This is of value when developers or users require a moderate level of independently assured security, including thorough investigation of TOE and its development.                                                                         |
| EAL4  | Methodically designed, tested, and reviewed  | Applies when rigorous, positive security engineering and good commercial development practices are used. This does not require substantial specialist knowledge, skills, or resources. It involves independent testing of all TOE security functions.                                                                                                                     |
| EAL5  | Semi-formally designed and tested            | Uses rigorous security engineering and commercial development practices, including specialist security engineering techniques, for semi-formal testing. This applies when developers or users require a high level of independently assured security in a planned development approach, followed by rigorous development.                                                 |
| EAL6  | Semi-formally verified, designed, and tested | Uses direct, rigorous security engineering techniques at all phases of design, development, and testing to produce a premium TOE. This applies when TOEs for high-risk situations are needed, where the value of protected assets justifies additional cost. Extensive testing reduces risks of penetration, probability of covert channels, and vulnerability to attack. |
| EAL7  | Formally verified, designed, and tested      | Used only for highest-risk situations or where high-value assets are involved. This is limited to TOEs where tightly focused security functionality is subject to extensive formal analysis and testing.                                                                                                                                                                  |


## UNDERSTAND SECURITY CAPABILITIES OF INFORMATION SYSTEMS

Some of the most foundational information system security (ISS) capabilities include the following:
* Memory protection
* Trusted Platform Modules (TPMs)
* Cryptographic modules
* Hardware Security Modules (HSMs)

### Memory Protection

One of the basic foundational security controls on all systems that allows multiple programs to run simultaneously is memory protection.
This feature enables the operating system to load multiple programs into main memory at the same time and prevent one program from referencing memory not specifically assigned to it.
If a program attempts to reference a memory address it is not permitted to access, the system blocks the access, suspends the program, and transfers control to the operating system.
In most cases, the operating system will terminate the offending program.

A related hardware feature that is required to support memory protection is dual-mode operation.
This means the processor can operate in one of (at least) two modes: privileged (or kernel) mode and unprivileged (or user) mode.
The operating system runs in privileged mode, which grants it permission to set up and control the memory protection subsystem.
Privileged mode also permits the operating system to execute special privileged instructions that control the processor environment.

Once a program has been loaded into memory and the memory protection is configured to limit that program’s access to those areas of memory assigned to it by the operating system, the operating system transfers control to the program and simultaneously transitions to unprivileged mode.

The program runs in unprivileged mode, which limits it to accessing only the specific memory area dictated by the operating system.
Should it make an illegal memory reference, attempt to execute a privileged CPU instruction, or use up the time slice granted to it by the operating system, control is returned to the operating system (running in privileged mode).

The operating system determines if control has been returned to the operating system because of an illegal operation by the user program, and decides how to handle the transgression (i.e., returning control to the user program with an error indication or terminating the program).

Another security control, address space layout randomization (ASLR), seeks to mitigate the risks of predictable memory address location.
The location in memory for a known instruction becomes a risk when there is a threat of exploiting that location for an attack.
For example, a buffer overflow attack requires knowing two things: the exact amount by which to overflow the memory to facilitate executing malicious code, and where exactly to send the overflow. ASLR defeats the second item by randomizing the location.

#### Potential Weaknesses

Proper memory protection relies upon both the correct operation of the hardware and the correct design of the operating system that uses the underlying memory protection hardware to prevent programs from accessing memory they have not been given permission to access.
A defect in either can compromise the security provided by memory protection.

Note that this protection prevents the direct disclosure of memory contents that are blocked from an unauthorized program, but does not necessarily prevent side-channel exploits from revealing information about memory that is protected from access.

Attacks that leverage ineffective isolation and memory protection can have catastrophic effects.
As the Spectre and Meltdown exploits in 2018 revealed, flaws in the design of Intel and some other CPU chips permitted clever programming techniques to deduce the contents of memory locations that those programs were not permitted to access directly.

### Secure Cryptoprocessor

The challenge with standard microprocessors is that code running with the highest privilege can access any device and any memory location, meaning that the security of the system depends entirely on the security of all the software operating at that privilege level.
If that software is defective or can be compromised, then the fundamental security of everything done on that processor becomes suspect.

To address this problem, hardware modules called secure cryptoprocessors have been developed that are resistant to hardware tampering and that have a limited interface (i.e., attack surface), making it easier to verify the integrity and secure operation of the (limited) code running on the cryptoprocessor.

Cryptoprocessors are used to provide services such as the following:
* Hardware-based true random number generators (TRNGs)
* Secure generation of keys using the embedded TRNG
* Secure storage of keys that are not externally accessible
* Encryption and digital signing using internally secured keys
* High-speed encryption, offloading the main processor from the computational burden of cryptographic operations

The following are features of cryptoprocessors that enhance their security over standard microprocessors (that could do most of the above in software):
* Tamper detection with automatic destruction of storage in the event of tampering, and a design that makes it difficult to tamper with the device without leaving obvious traces of the physical compromise.
These protections can range from tamper-evident stickers that clearly show attempts to access the device’s internal components to secure enclosures that detect unauthorized attempts to open the device and automatically erase or destroy sensitive key material.
* Chip design features such as shield layers to prevent eavesdropping on internal signals using ion probes or other microscopic devices.
* A hardware-based cryptographic accelerator (i.e., specialized instructions or logic to increase the performance of standard cryptographic algorithms such as AES, SHA, RSA, ECC, DSA, and ECDSA, which are discussed in detail later in this chapter).
* A trusted boot process that validates the initial boot firmware and operating system load.

There are many types of secure cryptoprocessors such as:
* Proprietary, such as Apple’s “Secure Enclave” found in iPhones
* Open standard, such as the TPM as specified by the ISO/IEC 11889 standard and used in some laptops and servers
* Standalone (e.g., separate standalone device with external communications ports)
* Smartcards

#### Trusted Platform Module

A TPM is a secure cryptoprocessor that provides secure storage and cryptographic services as specified by ISO/IEC 11889.

A TPM is essentially a security chip that is hardwired into a system (e.g., on a motherboard).
At its core, a TPM is responsible for the following functions:
* **Attestation:** Creates a cryptographic hash of the system’s known good hardware and software state, allowing third-party verification of the system’s integrity
* **Binding:** Encrypts data using a cryptographic key that is uniquely associated with (or bound to) the system
* **Sealing:** Ensures that ciphertext can be decrypted only if the system is attested to be in a known good state

A TPM can be used by the operating system, processor BIOS, or application (if the OS provides access to the TPM) to provide a number of cryptographic and security services such as:
* Generate private/public key pairs such that the private key never leaves the TPM in plaintext, substantially increasing the security related to the private key.
* Digitally sign data using a private key that is stored on the TPM and that never leaves the confines of the TPM, significantly decreasing the possibility that the key can become known by an attacker and used to forge identities and launch man-in-the-middle (MITM) attacks.
* Encrypt data such that it can only be decrypted using the same TPM.
* Verify the state of the machine the TPM is installed on to detect certain forms of tampering (i.e., with the BIOS) and ensure platform integrity.

##### Potential Weaknesses

The **endorsement key (EK)** is a fundamental component of a TPM’s security. This key is generated by the TPM manufacturer and burned into the TPM hardware during the manufacturing process.
Because of this, the user/system owner depends upon the security of the TPM manufacturer to ensure that the PEK remains confidential.

#### Cryptographic Module

A cryptographic module is typically a hardware device that implements key generation and other cryptographic functions and is embedded in a larger system.

The advantages of using a cryptographic module as opposed to obtaining the equivalent functionality from a cryptographic software library include the following:

* By performing critical cryptographic functions on a separate device that is dedicated to that purpose, it is much harder for malware or other software-based attacks to compromise the security of the cryptographic operation.
* By isolating security-sensitive functionality in an isolated device with limited interfaces and attack surfaces, it is easier to provide assurances about the secure operation of the device.
It also makes it easier to provide secure functions to larger systems by embedding a cryptographic module within the larger system.
* By separating cryptographic functions into a separate module, you gain increased availability of noncryptographic dedicated resources.
* Most secure cryptographic modules contain physical security protections including tamper resistance and tamper detection, making it difficult to compromise the security of the device even if the device has been physically compromised.
* Some cryptographic modules can enforce separation of duties so that certain sensitive operations, such as manipulating key storage, can be done only with the cooperation of two different individuals who authenticate to the cryptographic module separately.

#### Hardware Security Module

A Hardware Security Module (HSM) is a type of cryptographic module designed to stand alone as an appliance and to provide cryptographic services over an externally accessible API (typically over a network or USB connection).

HSMs are frequently found in certificate authorities (CAs) that use them to protect their root private keys, and payment processors that use them to protect the symmetric encryption keys used to protect cardholder data.

HSMs are also used in many national security applications or other environments where proper management of cryptographic material is critical to the business process.

In addition, HSMs are used by enterprise network backbones as part of encryption management of archives, east-west data movement, and even VPN traffic.


## ASSESS AND MITIGATE THE VULNERABILITIES OF SECURITY ARCHITECTURES, DESIGNS, AND SOLUTION ELEMENTS


### Protection Rings

* **Ring 0:** OS Kernel/Memory (Resident Components)
* **Ring 1:** Other OS Components
* **Ring 2:** Drivers, Protocols, etc.
* **Ring 3:** User-Level Programs and Applications

* Rings 0–2 run in supervisory or privileged mode. 
* Ring 3 runs in user mode.

### Emanation Security

Many electrical devices emanate electrical signals or radiation that can be intercepted and may contain confidential, sensitive, or private data.
Obvious examples of emanation devices are wireless networking equipment and mobile phones, but many other devices are vulnerable to emanation interception that you might not expect, including monitors, network cables, modems, and internal or external media drives (hard drives, USB thumb drives, CDs, and so on).
With the right equipment, adversaries can intercept electromagnetic or radio frequency signals (collectively known as emanations) from these devices and interpret them to extract confidential data.

The types of countermeasures and safeguards used to protect against emanation attacks are known as TEMPEST countermeasures.
TEMPEST was originally a government research study aimed at protecting electronic equipment from the electromagnetic pulse (EMP) emitted during nuclear explosions.
It has since expanded to a general study of monitoring emanations and preventing their interception.

Simply because of the kinds of electronic components from which they’re built, many computer hardware devices emit electromagnetic (EM) radiation during normal operation.
The process of communicating with other machines or peripheral equipment creates emanations that can be intercepted. These emanation leaks can cause serious security issues but are generally easy to address.

TEMPEST-derived technology allows the electronic emanations that devices produce (known as Van Eck radiation) to be read from a distance (this process is known as Van Eck phreaking).
TEMPEST eavesdropping or Van Eck phreaking countermeasures include the following:

#### Faraday Cage

A Faraday cage is a box, mobile room, or entire building designed with an external metal skin, often a wire mesh that fully surrounds an area on all sides.
This metal skin acts as an EM absorbing capacitor that prevents electromagnetic signals (emanations) from exiting or entering the area that the cage encloses.
Faraday cages can be designed to block specific frequencies while allowing others—for example, blocking Wi-Fi while allowing walkie talkies and mobile phones.

#### White Noise

White noise simply means broadcasting false traffic to mask and hide the presence of real emanations.
White noise can consist of a real signal from another source that is not confidential, a constant signal at a specific frequency, a randomly variable signal, or even a jam signal that causes interception equipment to fail.
Although this is similar to jamming devices, the purpose is to convolute the signal only for the eavesdropper, not the authorized user, rather than stopping even valid uses of emanations.

#### Control Zone

A third type of TEMPEST countermeasure, a control zone, is simply the implementation of both a Faraday cage and white noise generation to protect a specific area in an environment; the rest of the environment is not affected.
A control zone can be a room, a floor, or an entire building.

### Client-Based SystemsClient-Based Systems

Broadly speaking, software vulnerabilities in client-based systems involve weaknesses in client-side code that is present in browsers and applications.

Client-based vulnerabilities may fall into the following categories:
* Vulnerabilities related to the insecure operation of the client:
  * Storing temporary data on the client system in a manner that is insecure (i.e., accessible to unauthorized users through, for example, direct access to the client device’s filesystem)
  * Running insecure (e.g., out-of-date or unpatched) software versions
* Vulnerabilities related to communications with the server, such as client software that connects to remote servers but does not take appropriate steps to do the following:
  * Validate the identity of the server
  * Validate or sanitize the data received from the server
  * Prevent eavesdropping of data exchanged with the server
  * Detect tampering with data exchanged with the server
  * Validate commands or code received from the server before executing or taking action based on information received from the server

To address these vulnerabilities, one can consider the following:
* Evaluate your operating systems and applications for unpatched software or insecure configurations
* Using a recognized secure protocol (e.g., transport layer security (TLS)) to validate the identity of the server and to prevent eavesdropping of, and tampering with, data communicated with the server
* Using appropriate coding techniques to ensure that the data or commands received from the server are valid and consistent
* Using digital signing to verify executable code received from the server prior to execution

In many cases, the client may use software libraries, applets, or applications to process data received from the server. For example, the client may rely upon image display components to permit the viewing of files.
These components (e.g., Flash, Java Development Kit, etc.) will typically be provided by third parties and, as such, will need to be part of a vulnerability management program so that vulnerabilities that are discovered later can be patched in a timely manner.

If the client is a browser, then the browser ought to be configured in accordance with hardening guidelines available for the major web browsers.
Similarly, the appropriate steps to protect and patch the underlying system that runs the client software need to be taken.

Excellent sources of such guidance for browsers and client operating systems include The Center for Internet Security (CIS) and the Defense Information Systems Agency’s Security Technical Implementation Guides.

The client system also needs to be protected from other threats as appropriate, based on the risk assessment and threat modeling. This could include firewalls, physical security controls, full-disk encryption, and so on.

If the software has been developed specifically for this application, then the appropriate secure software development process as described in Chapter 8 must be employed.

### Server-Based Systems

Server vulnerabilities mirror many of the same vulnerabilities described earlier, just from the server’s perspective.
It’s important to remember that client and server systems are usually similar; the terms client and server only indicate the role a system plays in the overall system operations.

The server needs to validate the identity of the client and/or the identity of the user of the client. This can be done using a combination of Identity and Access Management (IAM) techniques along with a secure communications protocol such as TLS, using client-side certificates.

TLS will also protect the server from eavesdropping and tampering, such as might happen from a MITM attack. The server also must validate all inputs and not assume that simply because the commands and data coming from the client are originating from (and have been validated by) the corresponding client-side software, they are valid and have been sanitized.
The client must be considered untrusted, and it must be assumed that the client-end can insert or modify commands or data before being encrypted and transmitted over the secure (e.g., TLS) link.

Depending on the nature of the environment, it might be appropriate to protect the server from DoS attacks by using techniques such as rate-limiting, CAPTCHA, and other approaches.

Certainly, a vulnerability management program is needed to ensure that updates and patches are applied in a timely fashion.
This holds true regardless of whether the server-side software is developed in-house or is based in part or completely on software obtained from a third party (such as commercial off-the-shelf software, or COTS).

If the software has been developed specifically for this application, then the appropriate secure software development process must be employed.
This includes ensuring that the server application runs only with the minimum permissions necessary, commonly understood as the “principle of least privilege.”
If and when privilege escalation is needed, the period during which the server operates with elevated privileges is minimized.
Best practices include the server using filesystem ownership and permissions to avoid data leakage, logging and monitoring appropriate information (such as successful and failed login attempts, privileged access, etc.), and capturing forensic information to permit analysis of a possible or actual security incident.

Finally, threats to the server itself need to be addressed.
This may include physical and environmental threats, threats to the communications infrastructure, and server hardening as per industry recommendations such as those promulgated by the CIS (www.cisecurity.org/cis-benchmarks) or collected and indexed in NIST’s National Checklist Program Repository (nvd.nist.gov/ncp/repository).

#### Server Hardening Guidelines
The details of the specific issues that need to be addressed when hardening a specific
operating system will vary slightly depending on the OS, but generally involves the
following:
* Installing updates and patches
* Removing or locking unnecessary default accounts
* Changing default account passwords
* Enabling only needed services, protocols, daemons, etc. (conversely, disabling any not needed)
* Enabling logging and auditing
* Implementing only one primary function per server
* Changing default system, filesystem, service, and network configurations as needed to improve security (including full-disk encryption if appropriate)
* Removing (or disabling) unneeded drivers, executables, filesystems, libraries, scripts, services, etc.

### Database Systems

Securing database systems is a special case of the more general server-based system security discussed in the previous section.
If the database is accessible over a network, then all the security controls discussed there apply as well as those outlined below.
If the database is not network accessible, then there are fewer risks, and some server security controls may not be necessary.

Database-specific security controls include the following:
* Consult the CIS’s hardening guidelines for the database system being used. These guidelines include several of the recommendations below, and many others.
* Only install or enable those components of the database system that are needed for your application.
* Place data stores and log files on nonsystem partitions.
* Set appropriate filesystem permissions on database directories, data stores, logs, and certificate files.
* Run database services using a dedicated unprivileged account on a dedicated server.
* Disable command history.
* Do not use environment variables, command line, or database configuration files to pass authentication credentials.
* Do not reuse database account names across different applications.
* Disable “anonymous” accounts (if supported by the database).
* Mandate that all connections use TLS if access or replication traffic travels over untrusted networks.
* Use unique certificates for each database instance.
* Use restricted views.
* Ensure that all DBMS vendor-provided sample or test databases are removed or not accessible from user endpoints and clients.
* Change all default passwords, ensure all accounts have secure passwords, and consider enabling multifactor or certificate-based authentication (where supported).
* Ensure user account permissions have been assigned using the principle of least privilege and in alignment with enterprise-wide access control policies and procedures.
Database privileges can be complex and interact in unexpected ways - avoid default roles and define those you need with only the permissions needed for each.
* Disable or remove unneeded accounts, especially those with administrative permissions.
* Manage all accounts according to best practices (see Chapter 5).
* Enable logging of sensitive operations and route logs to your log monitoring and alerting system.
* Use bind variables where possible to minimize injection attack surfaces.
* Assign unique admin accounts for each administrator (i.e., do not share admin accounts between more than one admin).
Carefully consider a risk-based, role-based approach that supports a least-privilege and separation-of-duties model in which each admin only has those admin permissions necessary to discharge their specific responsibilities.
Where possible, ensure that critical operations require the cooperation of two admins.
* Enable logging at a sufficiently detailed level to provide the forensic information needed to identify the cause of events related to security incidents (but ensure logging does not include passwords), and protect the logs from tampering by database admins, either through permissions on the database system itself or by transmitting the log data in real time to a separate secure logging system.
* Consult vendor database documentation for database-specific security controls.
For example, Oracle supports a control known as data dictionary protection, which provides an additional level of least-privilege control, restricting certain operations to a subset of those with database admin privileges.
* For databases that are only accessed through application software (e.g., the typical n-tier web server application), run the database on private networks only accessible to the business logic servers that need access.

Database encryption deserves special attention. The encryption of data at rest can happen at any (or all) of several different levels:
* Full-disk encryption (FDE) at the lowest level protects all the data on the storage media, protecting against the physical theft or loss of the drive itself.
It provides no protection from threat actors who have logical access to the system, as the operating system or drive itself will decrypt all data that is read from the storage media before it is passed to the application without regard to the identity of the requester (other than the permission to access the file).
This can be implemented through firmware (self-encrypting drives) or through the operating system (e.g., BitLocker).
* Filesystem-level encryption allows the encryption to occur at the filesystem level.
This can be done at the volume, directory, or file level, depending on the capabilities of the operating system.
* Transparent data encryption (TDE) protects the data from those who have direct access to the filesystem (i.e., the “root” user), but do not have permission to access the database system and the specific database item.
It does not protect against malicious database administrators or attacks, such as SQL injection, that are able to bypass the application-level controls and issue database access commands directly.
While TDE provides protection beyond FDE, there are significant vulnerabilities it does not mitigate, so it is not meant to be used alone.
Note also that with some database systems, if the attacker can obtain both the operating system image and the TDE-protected database, the unencrypted contents can be extracted.
Cell-level encryption (CLE) or application-level encryption (covered next) are necessary to protect against threats that TDE does not address.
* CLE encrypts database information at the cell or column level. With this approach, data remains encrypted when read from the database and is decrypted only when requested.
It also permits the user to exert very granular control over the cryptographic keys.
This additional security and flexibility is not without its drawbacks.
Key management, and handling the decryption/encryption requests can add considerable complexity to the application, and depending on the types of queries (and whether they include CLE-protected data), the performance can be affected, sometimes drastically.

Application-level encryption is a high-level approach that provides protection even if access to the database system is compromised.
In this case, the business-logic or application layer is responsible for encrypting the data to be protected before it is passed to the database and for decrypting it once it has been retrieved.
The database itself sees only binary data and does not have any access to the encryption keys. This approach is the most complex, but provides greater security (if properly implemented and managed) than the other approaches.

To maximize the benefit of this approach, applications ought to encrypt as early as possible and decrypt as late as possible. Or to put it another way, handle the encryption/decryption as close to the point of use as possible.
For example, if your server-side application has a number of layers (refer to Figure 3.1), then the cryptographic component ought to be called from the business-logic layer, not the storage management layer.

Note, however, that performing the decryption completely externally to the database will make certain database functions unavailable (certain types of search, for example).

The decision as to which combination of database encryption approaches to use will be influenced by considerations such as the following:
* Performance, especially if searches reference data encrypted using CLE.
* Backups, which will be protected using TDE or CLE, but not necessarily when using FDE (unless the backup is on another FDE-protected drive).
* Compression as encrypted data does not compress, so the use of encryption may significantly increase the size of backups. Some databases support decrypting the data prior to compression, and then re-encrypting so the backup is compressed and encrypted. That may, however, introduce other vulnerabilities in the process.

### Cryptographic Systems

As American cryptologist Bruce Schneier famously stated, “All cryptography can eventually be broken - the only question is how much effort is required.”
The challenge then becomes one of weighing the value of the encrypted information to the attacker against the level of effort required to compromise the cryptographic system.

In making this decision, the potential attacker has a number of avenues that can be followed to compromise a cryptographic system. These include the following:
* Algorithm and protocol weaknesses
* Implementation weakness
* Key management vulnerabilities

#### Algorithm and Protocol Weaknesses

Designing a secure cryptographic algorithm or protocol is difficult, and only those algorithms that have been carefully examined by many experts and have stood the test of time ought to be used.

Next, realize that as computing power increases and more time is spent analyzing algorithms and protocols, weaknesses in what were previously robust approaches to cryptology will be found.
Cryptology never gets stronger; it only gets weaker with the passage of time, so managing cryptologic products through their lifecycle is essential.

These are the conclusions to be drawn:
* Cryptology is hard, and even the experts get it wrong.
* The cryptographic attack surface includes not only the algorithm, but the people, processes, and technology that implement the cryptographic protections, all of which are potentially vulnerable to attack.
* Cryptanalysis becomes more effective over time, owing to advances in computing, mathematical breakthroughs, and other improvements in cryptanalytic methods.

#### Implementation Weaknesses

Not only is designing a secure cryptographic algorithm or protocol hard, securely implementing an algorithm is no easier. Use industry-standard and tested algorithms, implemented in published libraries.
Don’t invent or implement algorithms yourself.

A **side-channel attack** is the analysis of artifacts related to the implementation of the algorithm, such as the time the algorithm takes to execute, the electrical power consumed by the device running the cryptographic implementation, or the electromagnetic radiation released by the device.

Defeating side-channel attacks is often difficult since detecting an attack that does not interfere with the operation of the cryptosystem is difficult.
The best defense is to use standard cryptographic libraries that have been tested over time for side-channel information leakage.

There are also a number of steps one can take to minimize the possibility of leaking information via side channels.
For example (and this is only a partial list of implementation traps lying in wait for the unsuspecting developer):
* Compare secret strings (e.g., keys, plaintext, unhashed passwords) using constant-time comparison routines
* Avoid branching or loop counts that depend upon secret data
* Avoid indexing lookup tables or arrays using secret data
* Use strong (i.e., “cryptographic grade”) random number generators

One also needs to be aware that compiler optimizations can change or remove code to introduce side-channel vulnerabilities.
The system security requirements need to identify these possible weaknesses, and the testing and code validation need to verify that they have been adequately addressed.

Vulnerabilities can also be introduced by misusing an otherwise securely implemented, sound cryptographic algorithm.

Block ciphers can be used in a number of different modes (discussed later in this chapter), some of which may leak significant information when used with certain types of data.
Selecting the correct mode is as important as selecting the block cipher itself.

#### Key Management Vulnerabilities

There are a number of vulnerabilities that can be introduced through the incorrect use, storage, and management of cryptographic keys.

Keys should be generated in a manner appropriate for the cryptographic algorithm being used. The proper method to generate a symmetric key is different from a public/private key pair.
NIST SP 800-133, “Recommendation for Cryptographic Key Generation,” provides specific guidance.

Keys should not be reused and should be rotated (replaced) periodically to ensure that the amount of data encrypted using a single key is limited, and the lifetime of data encrypted using a given key is likewise limited.

Symmetric and private keys depend upon confidentiality to be effective. This means great care must be taken with how the keys are stored to reduce the possibility of their becoming known to unauthorized entities.

There are a number of approaches to secure key storage. These are some common examples:
* Key management software
* Key management services provided by cloud service providers
* Dedicated hardware devices that keep the keys stored internally in a tamper-resistant secure device

Keys that have reached the end of their lifetime (and all properly managed keys ought to have a defined lifetime) must be securely destroyed to prevent their misuse in the future.

Another vulnerability can arise from insider threats. A rogue employee with access to key material can use that access to defeat the security of encrypted material (or enable another to do the same).
Dual control or segregation of duties can be employed to ensure that at least two people must be actively involved before any key management operation that might compromise the security of the keys or the system can be completed.

The final leg of the CIA Triad must also be considered: availability. If the key management system cannot provide access to the key material to authorized processes when required, then access to the encrypted material will be denied, even if the encrypted data is readily accessible.

Key operations must be logged in a manner that ensures accountability and traceability so that should a compromise be suspected, the forensic evidence will be available to analyze the possible breach.

Finally, where possible, key management functions ought to be automated. Manual processes are more prone to error (either of commission or omission), leading to weaknesses in the system that depends upon the keys for security.

### Industrial Control Systems

Industrial control systems (ICSs) are used to automate industrial processes and cover a range of control systems and related sensors.
Security in this context concentrates mostly on the integrity and availability aspects of the CIA Triad: integrity of the data (e.g., sensor inputs and control setpoints) used by the control system to make control decisions, and availability of the sensor data and the control system itself.

There are a number of organizations that provide guidance or regulations related to ICS security:
* ISA/IEC-62443 is a series of standards, technical reports, and related information that define procedures for implementing electronically secure Industrial Automation and Control Systems (IACS).
* The North American Electric Reliability Corporation (NERC) provides a series of guides referred to as the Critical Infrastructure Protection (CIP) standards.
NERC CIP standards are mandatory in the United States and Canada for entities involved in power generation/distribution.
* The European Reference Network for Critical Infrastructure Protection (ERNCIP) is an EU project with similar aims to those of NERC CIP.
* NIST and the UK National Centre for the Protection of National Infrastructure (CPNI). See, for example, NIST publication SP800-82.

ICS security shares many of the same threats, vulnerabilities, and risks as any information system, and a review of the controls outlined in the standards described earlier shows strong similarities to other information security frameworks.

These are the challenges specific to industrial control:
* The difficulty of patching device firmware to address vulnerabilities in the software discovered after placing the device into production in the field
* Failure to change factory-default settings, especially those related to access controls and passwords
* The long production lifetime of industrial systems as compared to IT systems
* The reliance on air-gapped networks as a compensating control without proper supervision of network connections

With ICSs, patching can be difficult or impossible:
* With industrial systems operating nonstop, it may not be feasible to remove an ICS device from operation to update its firmware.
* Similarly, with continuous production being important, the risk of an update breaking something (such as patching the underlying operating system and interfering with the ICS app running on that OS) can be too great (and greater than the perceived risk of running obsolete software).
Consider an air traffic control system or an oil and gas pipeline, for example.
These systems are hugely important and rely on nearly 100 percent uptime. Often, organizations must weigh the risk of operating an unpatched system with the risk of a patch disrupting service.
* Finally, the location of the ICS device in the field may make the simple matter of reaching the device physically to connect a laptop to install the firmware update a significant undertaking.

Many IT departments plan to replace systems every three to five years. Most computer vendors stop supporting devices five to seven years after their first release, and no longer provide patches to address security issues.
Most industrial process equipment is designed to operate for 10 to 20 years and longer.
Further, the greater reliance on commercial off-the-shelf operating systems increases the known attack surface for many ICS implementations, especially once those COTS operating systems have reached end-of-life while the ICS remains in service.

If the physical security of the ICS is adequate, then the primary threats are from the internet. In that case, a reasonable and common compensating control is to air-gap the networks used by the industrial control devices.
This can provide adequate security if properly enforced, but keeping the air-gapped network safe requires careful diligence and technical controls to prevent foreign equipment from being connected.
If external equipment must be connected periodically, say for maintenance purposes, consider using a firewall or proxy between the maintenance laptop and ICS network to provide an additional layer of security.

At a minimum, computers used to maintain and manage industrial systems must ever be used for any other purpose (or removed from the facility). They must be regularly updated, employ anti-malware protection, and carefully scan any removable media (e.g., USB thumb drives) before being used.
See the guidance published by the organizations listed earlier for more specifics.

If complete isolation from the corporate LAN and the internet is not an option, then it is essential to limit and screen permitted traffic accessing the ICS network through the use of carefully configured firewalls and network proxies.
Consideration ought to be given to further segmenting the ICS network itself to limit the lateral spread of a compromise.

For ICSs that must be remotely accessible, compensating controls such as installing a web proxy or VPN should be considered to add an additional layer of security on top of whatever access controls are implemented on the ICS itself.

Security awareness training is also particularly important, and advocating security principles among all the technicians and plant operators is critically important.
If those personnel burdened with the need to observe security controls understand the importance and rationale associated with those controls, they are less likely to view them as an impediment to their job of running the plant and something to be avoided or circumvented.

### Cloud-Based Systems

According to NIST, “Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction.”
In short,cloud-based systems are remotely located, separately managed systems that are accessible by the internet.

NIST SP 800-145 and ISO/IEC 17788 define a number of characteristics that describe cloud computing:
* Broad network access: Resources (physical and virtual) are accessible and managed over the network.
* Measured service: Users pay only for the services they use.
* On-demand self-service: Users can provision and manage services using automated tools without requiring human interaction.
* Rapid elasticity and scalability: Services can be rapidly and automatically scaled up or down to meet demand.
* Resource pooling and multitenancy: Physical or virtual resources are aggregated to serve multiple users while keeping their data isolated and inaccessible to other tenants.

There are three primary cloud service models, as shown in Table 3.2.

| CLOUD SERVICE MODEL                | SERVICE PROVIDED                                                                                                        | SERVICE PROVIDER RESPONSIBILITIES                                                                                                          | CUSTOMER RESPONSIBILITIES                                                                           |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| Software as a service (SaaS)       | Software application accessible to the customer over the internet (via a browser or API)                                | Provide and manage all infrastructure from server and network hardware to applications software                                            | Provide the client device and manage user-specific configuration settings                           |
| Platform as a service (PaaS)       | Web-based framework for developers to create customized applications                                                    | Provide and manage all infrastructure from server and network hardware to the libraries and runtime services necessary to run applications | Provide the application and manage the hosting environment                                          |
| Infrastructure as a service (IaaS) | Infrastructure, including servers, network, storage, and operating systems, delivered through virtualization technology | Provide network and server infrastructure to support VMs and other virtualized resources                                                   | Provide and manage all components that run on the VM as well as limited aspects of network services |   


#### Software as a Service (SaaS)

Software as a service (SaaS) models provide fully functional applications typically accessible via a web browser.
For example, Google’s Gmail is an SaaS application. The vendor (Google in this example) is responsible for all maintenance of the SaaS services. Customers do not manage or control any of the cloud-based assets.

#### Platform as a Service (PaaS)

Platform as a service (PaaS) models provide consumers with a computing platform, including hardware, operating systems, and a runtime environment.
The runtime environment includes programming languages, libraries, services, and other tools supported by the vendor. Customers deploy applications that they’ve created or acquired, manage their applications, and possibly modify some configuration settings on the host.
However, the vendor is responsible for maintenance of the host and the underlying cloud infrastructure.

#### Infrastructure as a Service (IaaS)

Infrastructure as a service (IaaS) models provide basic computing resources to customers. This includes servers, storage, and networking resources.
Customers install operating systems and applications and perform all required maintenance on the operating systems and applications.
The vendor maintains the cloud-based infrastructure, ensuring that consumers have access to leased systems.

The cloud deployment model also affects the breakdown of responsibilities of the cloud-based assets. The four cloud deployment models available are as follows:
* A **public cloud** model includes assets available for any consumers to rent or lease and is hosted by an external CSP.
Service-level agreements can effectively ensure that the CSP provides the cloud-based services at a level acceptable to the organization.
* The **private cloud** deployment model is used for cloud-based assets for a single organization.
Organizations can create and host private clouds using their own on-premises resources. If so, the organization is responsible for all maintenance.
However, an organization can also rent resources from a third party for exclusive use of the organization.
Maintenance requirements are typically split based on the service model (SaaS, PaaS, or IaaS).
* A **community cloud** deployment model provides cloud-based assets to two or more organizations that have a shared concern, such as a similar mission, security requirements, policy, or compliance considerations.
Assets can be owned and managed by one or more of the organizations. Maintenance responsibilities are shared based on who is hosting the assets and the service models.
* A **hybrid cloud** model includes a combination of two or more clouds that are bound together by a technology that provides data and application portability.
Similar to a community cloud model, maintenance responsibilities are shared based on who is hosting the assets and the service models in use.

In particular, the cloud service provider is exclusively responsible for the following:
* Physical security
* Environmental security
* Hardware (i.e., the servers and storage devices)
* Networking (i.e., cables, switches, routers, firewalls, and internet connectivity)

The cloud service provider and the customer share responsibility for the following:
* Vulnerability and patch management: Using Figure 3.9 as a guide to determine which organization is responsible for which activities, the cloud service provider is responsible for patching the software below the responsibility dividing line, the customer is responsible for everything above the line (i.e., in the case of SaaS, the customer is responsible only for the computers and browsers used to access the cloud).
* Configuration management: The cloud service provider is responsible for the infrastructure, the customer for everything above.
Network configuration and security is a special case, as the customer of an IaaS provider typically has configuration control over significant aspects of the network routing and firewalls through APIs and web-based management consoles.
As these network controls are a key component of the security of an IaaS cloud deployment, the customer must take great care in ensuring their proper configuration.
* Training: Both the cloud provider and customer are responsible for the specific training required for their own personnel.

### Distributed Systems

A distributed system is a collection of systems designed to appear as a single system to users. Distributed systems are built to achieve a number of objectives, including reliance, performance, and scalability.

Because a distributed system, by definition, involves multiple subsystems, possibly distributed geographically, and interconnected in some manner, the attack surface is much larger than that of a single system.

It is important to model threats to the overall system and identify the relative risks that need to be addressed.

Consider the following:
* The need for encryption and authentication on the connections between the subsystems to ensure attackers cannot intercept, eavesdrop, or spoof communications between subsystems
* The need to protect against DoS attacks against the communications links or the subsystems themselves
* The risks from a lack of homogeneity across subsystems (e.g., different versions and patch levels of operating systems, middleware, and application software; difficulty of maintaining consistent configurations across disparate and distributed systems) and mechanisms to mitigate those risks
* The need to maintain consistency should communications be disrupted (delayed or interrupted) between groups of (normally) connected subsystems (sometimes referred to as the “split-brain” problem)
* The challenge of ensuring comparable security controls in the case of geographically distributed components (e.g., physical, environmental, and personnel)
* The requirements of privacy and data sovereignty regulations that may limit the transfer of personal data across international borders

These risks are not unique to distributed systems, but the nature of distributed systems can make their mitigation much more complex than for nondistributed systems.

### Internet of Things

The term Internet of Things (IoT) describes a network of physical objects that are embedded with technologies (e.g., sensors and software) that enable them to connect to and exchange data with other devices over the internet.
These physical objects - or “things” - include all manner of devices in business, government, and commercial use.

#### IoT Security from an Equipment Manufacturer’s Perspective

During development, you will want to conduct threat modeling to determine likely vulnerabilities and to ensure that appropriate mitigations are deployed.
You must review their product’s security architecture to determine if the general guidelines outlined earlier in this section have been observed in the design of the firmware.

The development team will need to pay particular attention to secure software development guidelines such as those from the open web application security project (OWASP) and SANS.
And the quality assurance (QA) team will need to perform active white-and black-box penetration testing.

Many of the vulnerabilities that have been exploited in IoT devices in the past could have been mitigated through basic security hygiene such as changing default credentials and updating the firmware to patch known vulnerabilities.

As an IoT product developer, apart from trying to design and develop as secure an IoT device as you can, you need to make implementing the previous two security controls as easy as possible.
You can make your device the most secure IoT device on the planet, but once it’s in your customers’ hands, it is out of your control.
You need to make it as easy as possible for them to properly secure and maintain the device.

While ease of use is a key factor in the commercial success of IoT devices, one has to draw the line where ease of use is directly connected to ease of compromise.

#### IoT Security from a User’s Perspective

As a user of IoT devices, there are steps you can take to mitigate the risks related to devices with poor design or support so that you do not become part of a botnet used to attack others, and your IoT devices are not used as a beachhead from which your other information systems can be attacked.

To start, you can protect yourself (and others that might be a target of your compromised devices) through the same two basic security controls previously mentioned:
* Change default credentials as soon as possible, and before you connect the device to the internet.
* Keep your device updated with the current firmware release, either by enabling auto-update (if supported by your device) or by periodically checking with the manufacturer’s website for firmware updates.

In addition, you can employ security in depth through additional controls:
* Do not place IoT devices on the open internet, but rather behind a firewall so that they are not directly accessible externally.
* Segment your network so that your IoT devices do not have access to other sensitive devices or servers on your internal networks.
* If you have to be able to access your IoT device externally, then at the very least put the device behind a router that does reverse NAT mapping.
Recall that reverse NAT provides network address translation, but from an external source to an internal private address. Hence, it is NAT but in reverse.
Preferably, put the device behind a proxy that can perform its own user authentication before providing access to the IoT device.

Note, of course, that the router or proxy is also a potential vulnerability and must itself be operated securely: it must be properly configured (change default credentials) and maintained (patched and updated).

Relying on the security of an IoT device is unwise given the history of unpatched vulnerabilities in such devices.
By placing the device behind another that acts as an access gateway, one implements security in depth and security layering, requiring the compromise of two different devices before the IoT device can be breached.

And if you have properly segmented your network, even the compromise of your IoT devices will have limited impact on the confidentiality and integrity of your information systems (the availability of those systems in the face of an IoT DDoS attack is another matter).
In fact, taking network segmentation to the extreme leads to Google’s BeyondCorp paradigm: a network in which access to resources is not granted based on network location but by user privileges.

### Microservices

Microservice architecture is a modular software development style that involves developing a single application as a collection of loosely coupled smaller applications or services (microservices), each running its own processes.
The microservices are built to be independently deployable and work together through lightweight communications protocols.
Microservices can be contrasted with the more traditional monolithic architecture, which involves developing an application as a single, indivisible unit, typically with a large codebase that lacks modularity.

Microservice architectures are highly distributed and dynamic and present unique security concerns that must be considered from the first stages of design and throughout the entire development lifecycle.
Two key principles to consider when securing microservices are: isolation and defense in depth.

Isolation is a core principle of microservices, and each microservice must be able to be deployed, modified, maintained, and destroyed without impacting the other microservices around it.
By architecting microservices with the principle of isolation in mind, you can better ensure that weaknesses in one microservice are contained and cannot negatively affect other microservices in the application.

The principle of defense in depth, while important in any architecture, is particularly critical when dealing with microservices.
Defense in depth is a security strategy that calls for multiple layers of security controls to be implemented throughout an application or system.
It is essential in a microservice architecture to independently monitor and protect each microservice and the communications between each microservice in the overall environment.

### Containerization

A container is unit of software that packages up an application and its dependencies so that the application can be decoupled from its environment and developed, deployed, and run consistently across multiple environments (e.g., public cloud, private cloud, local systems, etc.).
Instead of running an entire operating system (like a VM does), a container uses the operating system’s kernel and only the resources required to operate the given application.
Thus, by design, containers are lightweight and flexible, allowing faster application development than noncontainerized applications.

Containers were made popular with the development of the open-source Kubernetes platform.
Kubernetes and other container platforms are particularly useful in hybrid cloud environments, as they allow developers and users to seamlessly move applications from one cloud to another, or even between cloud and on-prem environments.

#### Security Concerns

Containerization comes with its own set of security challenges, as container technology is inherently flexible and open.
Because containers allow you to rapidly scale up and down resources, asset management and configuration management are perhaps even bigger security concerns than traditional systems.

Container security risks generally fall into two major categories:
* Compromise of a container image or the entire container repository
* Misuse of a container to attack other containers or the host OS

Careful management of your container images is the key to container security. Your base container image is the most important, because it is used as a starting point for derivative images.
Container security begins with using signed base images from trusted sources. Follow careful configuration management practices when adding applications or other variables to your images.
In addition, all container images should adhere to strict vulnerability scanning and patching requirements.

In addition to managing secure image baselines, you must also ensure proper access controls to all of your container images. Use role-based access controls, where possible, to manage access to your container images.

Securing the host OS that runs your containers is a foundational part of securing your containers.
Host operating systems should run only the minimally required services necessary to operate the containers and exclude applications like web servers, databases, and others that increase the attack surface.
Proper configuration is also important, and host OSs must be included in your configuration management plans.

In addition, communications between containers should be restricted based on the principle of least privilege - only allow containers to communicate with those containers that are absolutely required for operation.
Container orchestration and management tools, like Kubernetes, allow you to implement network controls that restrict communication paths, where appropriate.

### Serverless

Serverless computing is a cloud computing model that involves the cloud provider managing servers, and dynamically allocating machine resources, as needed.
With serverless computing, infrastructure management tasks like provisioning and patching are handled by the cloud provider, leaving the customer primarily responsible for writing the code that executes on these servers.
AWS Lambda, Azure Functions, and Google Cloud Functions are popular serverless frameworks available from public cloud providers.

Serverless computing comes with some notable security benefits.

To start, serverless functions are typically ephemeral (i.e., short lived). These functions typically spin up for a few seconds, run their code, and then die.
This short-lived nature creates a moving target that adds a high degree of difficulty for attackers to compromise.

In addition, serverless functions are commonly much smaller codebases than even the smallest containers.
Given this fact, you are able to apply much more granular access control rules to each function, rather than relying on container-level rules that might require granting excessive permissions to achieve the same functionality.

Finally, with serverless architecture, your responsibility (as a cloud customer) for security is drastically reduced, and largely transferred to the cloud provider, who is responsible for all OS hardening, patching, and runtime security.
Of course, this is only a security benefit if the cloud provider executes these tasks reliably.

#### Security Concerns

Despite its benefits, serverless computing is not without its security challenges.

Effective serverless security is built on ensuring code integrity, tight access permissions, and proper monitoring.
You should maintain least-privileged access for serverless functions, as you do other services - serverless functions should be granted only the access and permissions necessary to execute their task.
Code should be routinely scanned for vulnerabilities and configuration issues.
In addition, runtime protection should be used to detect suspicious events or errors that may lead to unexpected behavior or compromise.
Most large cloud providers offer features to achieve these goals, and there are various third-party vendors with additional support for serverless security.

### Embedded Systems

Embedded systems are dedicated information processing components built into larger mechanical or electrical systems, intended to provide a limited set of functions.

Embedded systems can be found in a wide range of technologies, including the following:
* Domestic appliances (e.g., dishwashers, clothes washers and dryers, refrigerators, and televisions)
* Office equipment (e.g., printers, scanners, and fax machines)
* Networking devices (e.g., routers, switches, and firewalls)
* Cars and other automobiles
* ATMs
* Medical devices (e.g., heart monitors, glucose meters, and IV infusion pumps)
* Mass transit vehicles, stations, and systems
* Building automation and control systems
* Traffic control and monitoring systems

Assessing the vulnerabilities in an embedded system ought to start with an enumeration of the attack surfaces available and then examining each.
As described in greater detail earlier in this chapter, this examination can be done in a number of ways, including code inspection, threat modeling, and white-or black-box penetration testing.

Generally, these attack surfaces will fall into the following categories:
* User interface (UI, which are buttons or other methods of user input)
* Physical attacks
* Sensor attacks
* Output attacks
* Processor attacks

### High-Performance Computing Systems

High-performance computing (HPC) refers to the use of one or more supercomputers, generally for the purpose of highly complex computational science and other mathematically involved applications.

Generally speaking, HPC systems experience many of the same security concerns as traditional systems and other cloud-based systems (as discussed in earlier sections).
They typically run Linux-based operating systems and are subject to software vulnerabilities, configuration issues, and compromised credentials.
All of the traditional security measures should be considered here.

A distinction, however, may come in the form of highly specialized, purpose-built hardware and software that supports the HPC environment.
Any customized hardware and software present an added threat vector that must be secured.
In the case of high-performance computing, the challenge becomes ensuring secure operation without adversely impacting performance.

As a best practice, HPC systems should be moved to their own physical enclave or logical security zone that is separate from traditional systems.
Doing so segregates HPC systems from other types of computing systems that may have different security needs or regulations.
The separate enclave provides a single point for ingress and egress monitoring of the HPC environment.

Accommodating the high volume of data traffic that passes through HPC systems requires a modified approach to network monitoring.
Instead of using stateful firewalls for deep packet inspection, it’s typically best to use firewalls that inspect packet headers, but not the payloads themselves.
Separately, deep packet inspection may be used for intrusion detection, because stateful IDSs are not used inline, thus not introducing throughput delays.
Here, using separate tools allows achieving traditional security intentions that accommodate for the uniqueness of HPC systems.

### Edge Computing Systems

Edge computing is a distributed computing model that brings compute and storage resources closer to the location where it is needed, improving response times and reducing bandwidth.

Today, edge computing helps manage the tremendous growth we’re seeing with IoT devices. Edge computing allows pseudo-local data processing to minimize data sent over the internet.

#### Security Concerns

From a security standpoint, edge computing presents a few challenges.

Devices located at the edge, rather than centrally managed in a data center or other tightly managed facility, may not always receive the same diligence as their peers.
You must be sure to apply the same security rigor to edge devices as your centrally managed devices.
This includes hardening, patching, and providing the right level of physical security for edge computing systems.
SOAR (covered in Chapter 7) can help organizations observe and harden their devices, including those located at the edge.

Data must be encrypted when in transit between edge devices and centralized systems (or the cloud), and VPN tunneling may also be advisable for sensitive data when managing remote systems.

There are also availability concerns for edge devices. Redundancy and failover management of edge computing systems is important to ensure that data continues to be processed and transmitted in the event a single edge node fails.
In addition, edge devices must be monitored for such failures so that errors and failures can be remedied as quickly as possible.

### Virtualized Systems

Operating systems provide programs with a set of services to enable them to operate more efficiently (and to be more easily designed and run) than if the program had to run on the computer directly.

In some sense, an operating system provides a type of virtual computer, a computer that does not exist in reality (i.e., hardware) but that is much easier for applications to use than the physical hardware and that makes more efficient use of the hardware by sharing it among different programs (see Figure 3.12).

Virtualization takes this concept a step further. Virtualization is the act of creating virtual (i.e., not real) compute, storage, and network resources - in other words, virtualization allows you to create software versions of hardware.
VMs, for instance, are software instances of actual computers.
Likewise, software-defined networks (SDNs) are software instances of physical networks.

Instead of just one operating system enabling multiple application programs running on the same hardware, virtualization enables multiple operating systems to run on the same computer, each unaware of and unable (in a properly designed system) to affect the other operating systems.
Virtualization is the primary technology behind cloud computing (discussed earlier in this section).

The most common implementation of virtualization is a **hypervisor**. A hypervisor is a computing layer that allows multiple operating systems to run simultaneously on a single piece of hardware, with each operating system viewing the machine’s resources as its own dedicated resources.
A hypervisor allows multiple guest virtual machines to run on a single physical host.

A **type I hypervisor** is a native or bare-metal hypervisor (Figure 9.3, top). In this configuration, there is no host OS; instead, the hypervisor installs directly onto the hardware where the host OS would normally reside.
Type 1 hypervisors are often used to support server virtualization. This allows for maximization of the hardware resources while eliminating any risks or resource reduction caused by a host OS.

A **type II hypervisor** is a hosted hypervisor (Figure 9.3, bottom). In this configuration, a standard regular OS is present on the hardware, and then the hypervisor is installed as another software application.
Type II hypervisors are often used in relation to desktop deployments, where the guest OSs offer safe sandbox areas to test new code, allow the execution of legacy applications, support apps from alternate OSs, and provide the user with access to the capabilities of a host OS.

Virtualization is the foundation upon which cloud providers such as AWS or Google Cloud Platform (GCP) provide VMs to different clients who may well end up running on the same physical computer, unknown to each other.

The advantages of virtualization include the following:
* More efficient use of the underlying hardware (just as operating systems permitted a single computer to be shared by multiple programs and users)
* Dynamic scaling of infrastructure in response to demand
* Additional separation and isolation between programs and applications running on different operating systems (as opposed to running on the same OS) - supporting the security principles of defense in depth and layers of security outlined earlier

#### Potential Weaknesses

As with memory protection, virtualization depends on the correct operation of both the hardware and the hypervisor (which may include hardware and/or software).
Hardware defects such as Meltdown break the underlying assumption that the hardware will prevent an unauthorized program (and possibly a completely unrelated client) from accessing memory assigned to another program (and client).

Similarly, software defects in hypervisors can improperly permit software running on one VM to access data on a different VM on the same computer.
An exploit known as virtual machine escape, for example, occurs when a program is able to break out of its VM and directly interact with the underlying host operating system; once able to access the host OS, an attacker may be able to pivot into other VMs or cause service outages for tenants of the host system.
When such defects are discovered, they are usually disclosed to the largest cloud service providers so that they can be patched before the vulnerability becomes widely known.

There is always the possibility that these unpatched defects in the hardware or hypervisor might be known to a threat actor who is then able to compromise the protections that are supposed to prevent unrelated clients on VMs from interacting.
To mitigate this risk, some IaaS cloud providers offer dedicated hosts that guarantee that only VMs assigned to your account will be permitted to run on the dedicated host.

## SELECT AND DETERMINE CRYPTOGRAPHIC SOLUTIONS

Cryptography can be used across your environment to accomplish several objectives of information security, including two of three core principles from the CIA Triad (confidentiality and integrity), among others (namely, privacy, authenticity, nonrepudiation):
* **Confidentiality (and privacy):** One of the main uses of cryptography is to protect the confidentiality of information, both at rest and in transit.
This offers the critical feature of “privacy” when applied to personally identifiable information (PII) and protected health information (PHI).
* **Integrity:** Another common application of cryptography is the use of hashing algorithms and message digest to provide assurance of data integrity (or accuracy).
These cryptographic applications help ensure that data being accessed is intact and as expected.
* **Authenticity (and nonrepudiation):** Cryptography can also be used for authentication services as well as nonrepudiation through digital signatures and digital certificates.

### Cryptography Basics

The following definitions from (ISC)2 are core to the topic of cryptography, and you will see (and likely use) them frequently:
* Plaintext: The message in its natural format, which has not been turned into a secret.
* Cleartext: The message in readable, usable form that is not intended to be obscured by cryptographic means.
* Ciphertext: The altered form of a plaintext message, so as to be unreadable for anyone except the intended recipients (in other words, something that has been turned into a secret).
* Encryption: The process of converting the message from its plaintext to ciphertext.
* Decryption: The reverse process from encryption - it is the process of converting a ciphertext message back into plaintext through the use of the cryptographic algorithm and the appropriate key that was used to do the original encryption.
* Cryptographic algorithm: A mathematical function that is used in the encryption and decryption process.
* Key: The input that controls the operation of the cryptographic algorithm; it determines the behavior of the algorithm and permits the reliable encryption and decryption of the message.
Symmetric/private keys (discussed later in this chapter) must be kept private, while public keys (also discussed later in this chapter) are shared to enable authentication and other use cases.

#### Kerckhoffs’s Principle

All cryptography relies on algorithms. An algorithm is a set of rules, usually mathematical, that dictates how encryption and decryption processes are to take place.
Most cryptographers follow Kerckhoffs’s principle, a concept that makes algorithms known and public, allowing anyone to examine and test them.
Specifically, Kerckhoffs’s principle (also known as Kerckhoffs’s assumption) is that a cryptographic system should be secure even if everything about the system, except the key, is public knowledge.
The principle can be summed up as “The enemy knows the system.”

### Cryptographic Lifecycle

The cryptographic lifecycle involves algorithm selection, key management, and the management of encrypted data at rest, in transit, and in use.

Algorithm selection involves a number of choices:
* The type of cryptography appropriate for the purpose (e.g., symmetric, public key, hashing, etc.)
* The specific algorithm (e.g., AES, RSA, SHA, etc.)
* The key length (e.g., AES-256, RSA-2048, SHA-512, etc.)
* The operating mode (ECB, CBC, etc.)

### Cryptographic Methods

| USE CASE                                   | TYPE OF CRYPTOGRAPHY                        |
|--------------------------------------------|---------------------------------------------|
| Protect confidentiality of stored data     | Symmetric                                   |
| Protect confidentiality of data in transit | Symmetric (possibly aided by asymmetric)    |
| Verify identity                            | Public key infrastructure                   |
| Protect integrity (detect tampering)       | Hashing (e.g., Message Authentication Code) |
| Protect passwords                          | Hashing (with salt and pepper)              |
| Nonrepudiation                             | Digital signature                           |


#### Symmetric Encryption

Symmetric encryption is the most common approach and the one most people think of when speaking of cryptography.
Symmetric encryption takes a message (referred to as the plaintext) and an encryption key and produces output (called the ciphertext) that does not reveal any of the information in the original plaintext.
The output can be converted back into the original plaintext if a person has the encryption key that was used to perform the original encryption.

For symmetric encryption to work, both the sender and the receiver must share the key. For the message to remain confidential, the key must be kept secret.
For these reasons, symmetric cryptography is sometimes referred to as secret-key or shared-secret encryption.

A stream cipher is an encryption algorithm that works one character or bit at a time (instead of a block).
They are typically used to encrypt serial communication links and cell-phone traffic and specifically designed to be computationally efficient so that they can be employed in devices with limited CPU power, or in dedicated hardware or field programmable gate arrays (FPGAs).

Block ciphers use a deterministic algorithm that takes a fixed-sized block of bits (the plaintext) and a key value, and produces an encrypted block (the ciphertext) of the same size as the plaintext block.
Different key values will produce different ciphertexts from the same plaintext.

##### Stream Ciphers

American cryptographer Claude Shannon proved in 1949 that if the key is truly random, the same length as the plaintext, and used only once, then the system is secure and unbreakable (assuming the key remains secret).
This type of encryption is called a **one-time pad** because the key is used for only one round of encrypting and decrypting.
The problem with this approach is that the key must be the same length as the message and cannot be reused, making the method completely impractical except for the shortest of messages or for situations (typically government) in which the cost of securely delivering large amounts of key material can be justified.

Practical ciphers use a fixed-length key to encrypt many messages of variable length.
As we will see in the section on cryptanalysis, some ciphers can be broken if the attacker comes into possession of enough ciphertexts that have been encrypted with the same key.
Changing the key periodically so that the amount of ciphertext produced with each unique key is limited can increase the security of the cipher.

**Synchronous ciphers** require the sender and receiver to remain in perfect synchronization in order to decrypt the stream. Should characters (bits) be added or dropped from the stream, the decryption will fail from that point on.
The receiver needs to be able to detect the loss of synchronization and either try various offsets to resynchronize or wait for a distinctive marker inserted by the sender to enable the receiver to resync.

**Self-synchronizing stream ciphers**, as the name implies, have the property that after at most N characters (N being a property of the particular self-synchronizing stream cipher), the receiver will automatically recover from dropped or added characters in the ciphertext stream.
While they can be an obvious advantage in situations in which data can be dropped or added to the ciphertext stream, self-synchronizing ciphers suffer from the problem that should a character be corrupted, the error will propagate, affecting up to the next N characters.
With a synchronous cipher, a single-character error in the ciphertext will result in only a single-character error in the decrypted plaintext.

##### Block Ciphers

Block ciphers process blocks of n bits at a time, using a key of size k. The output of the processed block then becomes the input for the next iteration of the cipher function. The number of iterations that occur are referred to as rounds.

| BLOCK CIPHER | BLOCK SIZE (N) | KEY SIZE (K) | ROUNDS |
|--------------|----------------|--------------|--------|
| DES          | 64             | 56           | 16     |
| AES-128      | 128            | 128          | 10     |
| AES-192      | 128            | 192          | 12     |
| AES-256      | 128            | 256          | 14     |

The DES cipher is no longer considered secure because of its short key size, but it introduced the modern age of cryptography and so is historically important.
Because DES was no longer secure, finding its replacement was crucial. AES was selected after a five-year process to evaluate and select an algorithm from over a dozen candidates.
Triple DES (3DES) is an important evolution of DES and is discussed later in this section.

Most block ciphers, including DES and AES, are built from multiple rounds of mathematical functions, as illustrated in Figure 3.17.
While more rounds mean greater security, it also slows down the algorithmic process, so the choice is a trade-off between security and speed.

The differences between different block ciphers are in the transformations performed during each round, and the manner in which the encryption key is stretched and then divided to provide a unique key for each round.

There are a couple of standard building blocks used to construct block ciphers:
* Substitution or S-boxes
* Permutations or P-boxes

AES uses multiple rounds of substitutions and permutations, while DES uses a 16-round Feistel network.

##### Block Cipher Modes of Operation

To handle messages that are not a multiple of the cipher’s block length, one mechanism is to add padding before encryption and remove the padding after encryption.
There are many ways to do this, but one approach is to add bytes to the end of the message, with each byte containing the count of the number of bytes that have been added (see Figure 3.20).
Because the decryption process will examine the last byte of the last block to determine how many padding bytes have been added (and thus need to be removed), if the plaintext is a multiple of the block size, then a final block that just contains padding must be added.

###### Electronic Code Book Mode

Electronic Code Book (ECB) mode is the simplest mode to understand and the least secure. Each time the algorithm processes a 64-bit block, it simply encrypts the block using the chosen secret key.
This means that if the algorithm encounters the same block multiple times, it will produce the same encrypted block.
If an enemy were eavesdropping on the communications, they could simply build a “code book” of all the possible encrypted values.
After a sufficient number of blocks were gathered, cryptanalytic techniques could be used to decipher some of the blocks and break the encryption scheme.

This vulnerability makes it impractical to use ECB mode on any but the shortest transmissions.
In everyday use, ECB is used only for exchanging small amounts of data, such as keys and parameters used to initiate other cryptographic modes as well as the cells in a database.

###### Cipher Block Chaining Mode

In Cipher Block Chaining (CBC) mode, each block of unencrypted text is XORed with the block of ciphertext immediately preceding it before it is encrypted.
The decryption process simply decrypts the ciphertext and reverses the XOR operation.
CBC implements an IV and XORs it with the first block of the message, producing a unique output every time the operation is performed.
The IV must be sent to the recipient, perhaps by tacking the IV onto the front of the completed ciphertext in plain form or by protecting it with ECB mode encryption using the same key used for the message.
One important consideration when using CBC mode is that errors propagate - if one block is corrupted during transmission, it becomes impossible to decrypt that block and the next block as well.

###### Cipher Feedback Mode

Cipher Feedback (CFB) mode is the streaming cipher version of CBC. In other words, CFB operates against data produced in real time.
However, instead of breaking a message into blocks, it uses memory buffers of the same block size. As the buffer becomes full, it is encrypted and then sent to the recipients.
Then the system waits for the next buffer to be filled as the new data is generated before it is in turn encrypted and then transmitted.
Other than the change from preexisting data to real-time data, CFB operates in the same fashion as CBC. It uses an IV, and it uses chaining.

###### Output Feedback Mode

In Output Feedback (OFB) mode, ciphers operate in almost the same fashion as they do in CFB mode.
However, instead of XORing an encrypted version of the previous block of ciphertext, OFB XORs the plaintext with a seed value.
For the first encrypted block, an initialization vector is used to create the seed value. Future seed values are derived by running the algorithm on the previous seed value.
The major advantages of OFB mode are that there is no chaining function and transmission errors do not propagate to affect the decryption of future blocks.

###### Counter Mode

Counter (CTR) mode uses a stream cipher similar to that used in CFB and OFB modes.
However, instead of creating the seed value for each encryption/decryption operation from the results of the previous seed values, it uses a simple counter that increments for each operation.
As with OFB mode, errors do not propagate in CTR mode.

###### Galois/Counter Mode

Galois/Counter Mode (GCM) takes the standard CTR mode of encryption and adds data authenticity controls to the mix, providing the recipient assurances of the integrity of the data received.
This is done by adding authentication tags to the encryption process.

###### Counter with Cipher Block Chaining Message Authentication Code Mode

Similar to GCM, the Counter with Cipher Block Chaining Message Authentication Code Mode (CCM) combines a confidentiality mode with a data authenticity process.
In this case, CCM ciphers combine the Counter (CTR) mode for confidentiality with the Cipher Block Chaining Message Authentication Code (CBC-MAC) algorithm for data authenticity.
CCM is used only with block ciphers that have a 128-bit block length and require the use of a nonce that must be changed for each transmission.

##### Data Encryption Standard

The U.S. government published the Data Encryption Standard in 1977 as a proposed standard cryptosystem for all government communications. Because of flaws in the algorithm, cryptographers and the federal government no longer consider DES secure.
It is widely believed that intelligence agencies routinely decrypt DES-encrypted information. DES was superseded by the Advanced Encryption Standard in December 2001.

It is still important to understand DES because it is the building block of Triple DES (3DES), a stronger (but still not strong enough) encryption algorithm discussed in the next section.
DES is a 64-bit block cipher that has five modes of operation: Electronic Code Book (ECB) mode, Cipher Block Chaining (CBC) mode, Cipher Feedback (CFB) mode, Output Feedback (OFB) mode, and Counter (CTR) mode.
All of the DES modes operate on 64 bits of plaintext at a time to generate 64-bit blocks of ciphertext. The key used by DES is 56 bits long.

DES uses a long series of exclusive OR (XOR) operations to generate the ciphertext. This process is repeated 16 times for each encryption/decryption operation.
Each repetition is commonly referred to as a round of encryption, explaining the statement that DES performs 16 rounds of encryption. Each round generates a new key that is then used as the input to subsequent rounds.

##### Triple DES

As mentioned in previous sections, the Data Encryption Standard’s (DES) 56-bit key is no longer considered adequate in the face of modern cryptanalytic techniques and supercomputing power.
However, an adapted version of DES, Triple DES (3DES), uses the same algorithm to produce encryption that is stronger but that is no longer considered adequate to meet modern requirements.
For this reason, 3DES encryption should be avoided, although it is still supported by many products.

There are several different variants of 3DES that each use different numbers of independent keys.
The first two, DES-EDE3 and DES EEE-3, use three independent keys: K1, K2, and K3.
The difference between the two are the operations used, which are represented by the letter E for encryption and D for decryption.

DES-EDE3 encrypts the data with K1, decrypts the resulting ciphertext with K2, and then encrypts that text with K3.
DES-EDE3 can be expressed using the following notation, where E(K,P) represents the encryption of plaintext P with key K, and D(K,P) represents the decryption of ciphertext C with key K: E(K1,D(K2,E(K3,P)))

DES-EEE3, on the other hand, encrypts the data with all three keys in sequential order, and may be represented as follows: E(K1,E(K2,E(K3,P)))

Mathematically, DES-EEE3 and DES-EDE3 should have an effective key length of 168 bits. However, known attacks against this algorithm reduce the effective strength to 112 bits.

DES-EEE3 is the only variant of 3DES that is currently considered secure by NIST.
The other variants, DES-EDE1, DES-EEE2, and DES-EDE2, use either one or two keys, repeating the same key multiple times, but these modes are no longer considered secure.

It is also important to note that NIST recently deprecated the use of all 3DES variants and will disallow their use in federal government applications at the end of 2023.

##### International Data Encryption Algorithm

The International Data Encryption Algorithm (IDEA) block cipher was developed in response to complaints about the insufficient key length of the DES algorithm.
Like DES, IDEA operates on 64-bit blocks of plaintext/ciphertext. However, it begins its operation with a 128-bit key.
This key is broken up in a series of operations into 52 16-bit subkeys. The subkeys then act on the input text using a combination of XOR and modulus operations to produce the encrypted/decrypted version of the input message.
IDEA is capable of operating in the same five modes used by DES: ECB, CBC, CFB, OFB, and CTR.

The IDEA algorithm was patented by its Swiss developers. However, the patent expired in 2012, and it is now available for unrestricted use.
One popular implementation of IDEA is found in Phil Zimmerman’s popular Pretty Good Privacy (PGP) secure email package.

##### Blowfish

Bruce Schneier’s Blowfish block cipher is another alternative to DES and IDEA. Like its predecessors, Blowfish operates on 64-bit blocks of text.
However, it extends IDEA’s key strength even further by allowing the use of variable-length keys ranging from a relatively insecure 32 bits to an extremely strong 448 bits.
Obviously, the longer keys will result in a corresponding increase in encryption/decryption time.
However, time trials have established Blowfish as a much faster algorithm than both IDEA and DES.
Also, Schneier released Blowfish for public use with no license required. Blowfish encryption is built into a number of commercial software products and operating systems. A number of Blowfish libraries are also available for software developers.

##### Skipjack

The Skipjack algorithm was approved for use by the U.S. government in Federal Information Processing Standard (FIPS) 185, the Escrowed Encryption Standard (EES).
Like many block ciphers, Skipjack operates on 64-bit blocks of text. It uses an 80-bit key and supports the same four modes of operation supported by DES.

Skipjack was quickly embraced by the U.S. government and provides the cryptographic routines supporting the Clipper and Capstone encryption chips.

However, Skipjack has an added twist-it supports the escrow of encryption keys. Two government agencies, the National Institute of Standards and Technology (NIST) and the Department of the Treasury, hold a portion of the information required to reconstruct a Skipjack key.
When law enforcement authorities obtain legal authorization, they contact the two agencies, obtain the pieces of the key, and are able to decrypt communications between the affected parties.

Skipjack and the Clipper chip were not embraced by the cryptographic community at large because of its mistrust of the escrow procedures in place within the U.S. government.

##### Rivest Ciphers

Ron Rivest, of Rivest-Shamir-Adleman (RSA) Data Security, created a series of symmetric ciphers over the years known as the Rivest Ciphers (RC) family of algorithms.
Several of these, RC4, RC5, and RC6, have particular importance today.

###### Rivest Cipher 4 (RC4)

RC4 is a stream cipher developed by Rivest in 1987 and very widely used during the decades that followed. It uses a single round of encryption and allows the use of variable-length keys ranging from 40 bits to 2,048 bits.
RC4’s adoption was widespread because it was integrated into the Wired Equivalent Privacy (WEP), Wi-Fi Protected Access (WPA), Secure Sockets Layer (SSL), and Transport Layer Security (TLS) protocols.
A series of attacks against this algorithm render it insecure for use today. WEP, WPA, and SSL no longer meet modern security standards for both this and other reasons. TLS no longer allows the use of RC4 as a stream cipher.

###### Rivest Cipher 5 (RC5)

RC5 is a block cipher of variable block sizes (32, 64, or 128 bits) that uses key sizes between 0 (zero) length and 2,040 bits.
It is important to note that RC5 is not simply the next version of RC4. In fact, it is completely unrelated to the RC4 cipher. Instead, RC5 is an improvement on an older algorithm called RC2 that is no longer considered secure.
RC5 is the subject of brute-force cracking attempts. A large-scale effort leveraging massive community computing resources cracked a message encrypted using RC5 with a 64-bit key, but this effort took more than four years to crack a single message.

###### Rivest Cipher 6 (RC6)

RC6 is a block cipher that was developed as the next version of RC5. It uses a 128-bit block size and allows the use of 128-, 192-, or 256-bit symmetric keys.
This algorithm was one of the candidates for selection as the Advanced Encryption Standard (AES) discussed in the next section, but it was not selected and is not widely used today.

##### Advanced Encryption Standard

In October 2000, the National Institute of Standards and Technology announced that the Rijndael (pronounced “rhine-doll”) block cipher had been chosen as the replacement for DES.
In November 2001, NIST released FIPS 197, which mandated the use of AES/Rijndael for the encryption of all sensitive but unclassified data by the U.S. government.

The Advanced Encryption Standard (AES) cipher allows the use of three key strengths: 128 bits, 192 bits, and 256 bits. AES only allows the processing of 128-bit blocks, but Rijndael exceeded this specification, allowing cryptographers to use a block size equal to the key length.

The number of encryption rounds depends on the key length chosen:
* 128-bit keys require 10 rounds of encryption.
* 192-bit keys require 12 rounds of encryption.
* 256-bit keys require 14 rounds of encryption.

##### CAST

The CAST algorithms are another family of symmetric key block ciphers that are integrated into some security solutions. The CAST algorithms use a Feistel network and come in two forms:
* CAST-128 uses either 12 or 16 rounds of Feistel network encryption with a key size between 40 and 128 bits on 64-bit blocks of plaintext.
* CAST-256 uses 48 rounds of encryption with a key size of 128, 160, 192, 224, or 256 bits on 128-bit blocks of plaintext.

The CAST-256 algorithm was a candidate for the Advanced Encryption Standard but was not selected for that purpose.

##### Twofish

The Twofish algorithm developed by Bruce Schneier (also the creator of Blowfish) was another one of the AES finalists. Like Rijndael, Twofish is a block cipher. It operates on 128-bit blocks of data and is capable of using cryptographic keys up to 256 bits in length.

Twofish uses two techniques not found in other algorithms:
* Prewhitening involves XORing the plaintext with a separate subkey before the first round of encryption.
* Postwhitening uses a similar operation after the 16th round of encryptio

##### Comparison of Symmetric Encryption Algorithms

| Name                               | Block size          | Key size                   |
|------------------------------------|---------------------|----------------------------|
| Advanced Encryption Standard (AES) | 128                 | 128, 192, 256              |
| Rijndael                           | Variable            | 128, 192, 256128, 192, 256 |
| Blowfish (often used in SSH)       | 64                  | 32-448                     |
| Data Encryption Standard (DES)     | 64                  | 56                         |
| IDEA (used in PGP)                 | 64                  | 128                        |
| Rivest Cipher 4 (RC4)              | N/A (Stream cipher) | 40–2,048                   |
| Rivest Cipher 5 (RC5)              | 32, 64, 128         | 0–2,040                    |
| Rivest Cipher 6 (RC6)              | 128                 | 128, 192, 256              |
| Skipjack                           | 64                  | 80                         |
| Triple DES (3DES)                  | 64                  | 112 or 168                 |
| CAST-128                           | 64                  | 40–128                     |
| CAST-256                           | 128                 | 128, 160, 192, 224, 256    |
| Twofish                            | 128                 | 1–256                      |


#### Asymmetric Encryption (Public Key Cryptography)

A trapdoor function, as they are called, is one for which computing f(x) is easy, but calculating the inverse function (e.g., determining x if one only knows the value of f(x)) is extremely difficult unless one knows the value of a second variable, y.

##### Diffie–Hellman–Merkle Key Exchange

Diffie–Hellman–Merkle key exchange is a method of securely exchanging cryptographic keys.
Developed in 1976 by Whitfield Diffie and Martin Hellman, this is the first known implementation of public key cryptography.
Like many of the asymmetric key algorithms that came after it, the Diffie–Hellman–Merkle algorithm is based on logarithmic mathematics.
Unlike the encryption algorithms before it, the Diffie–Hellman–Merkle algorithm is not used for encryption or decryption, but instead is used to enable two parties to securely generate a shared secret key to use for their (symmetric-key) encrypted communications.

##### RSA

RSA (Rivest-Shamir-Adleman) is an asymmetric-key algorithm used for encrypting and signing data. The security of the algorithm is based on the difficulty of factoring two large prime numbers.
The RSA algorithm was first developed by Dr. Ron Rivest, Adi Shamir, and Len Adleman in 1978, and continues to be one of the most commonly used public key encryption algorithms.

##### ElGamal

ElGamal is an asymmetric-key algorithm used for transmitting digital signatures and key exchanges.
The ElGamal algorithm is derived from the Diffie–Hellman–Merkle algorithm (discussed earlier) and is again based on discrete logarithmic problem solving.

##### Elliptic Curve Cryptography

ECC is an approach to public key cryptography that is based on far more complex computations than other public key algorithmic approaches.
Whereas the security of earlier public key systems was based on the difficulty of factoring sets of large prime integers, ECC is based on the algebraic structure of elliptic curves (see Figure 3.25), which can become quite complex.

A key benefit of ECC is that it allows smaller keys to be used for equivalent security.
For example, a 256-bit ECC key would be equivalent to a 3,072-bit RSA key.
Using smaller keys leads to faster computations; as such, ECC is more efficient than other public key algorithms, allowing it to be used in more applications - particularly applications with resource constraints.

Several discrete logarithm-based algorithms have been adapted to ECC.
While it is often discussed with RSA, there is the Elliptic Curve Diffie–Hellman–Merkle (ECDH) scheme based on the traditional Diffie–Hellman–Merkle scheme, the Elliptic Curve Digital Signature Algorithm (ECDSA) based on the Digital Signature Algorithm, and several others.

##### Quantum Cryptography

One property of quantum mechanics that lends itself to cryptography is that any attempt to observe or measure a quantum system will disturb it.
This provides a basis to transmit a secret encryption key such that if it is intercepted by an eavesdropper, it can be detected.
So, Alice first sends Bob a secret key using quantum key distribution (QKD), and Bob checks to see if it has been intercepted. If it has, he asks for another key.
If it hasn’t, he signals Alice to start sending messages encrypted using a symmetric cipher or a one-time pad and the key, knowing that only Alice and he have access to the key and therefore the communications will remain secret.
QKD infrastructures continue to grow in popularity around the globe.

### Public Key Infrastructure

#### Certificates

Digital certificates provide communicating parties with the assurance that the people they are communicating with truly are who they claim to be.
Digital certificates are essentially endorsed copies of an individual’s public key. When users verify that a certificate was signed by a trusted certificate authority (CA), they know that the public key is legitimate.

The standard for public key certificates (also known as digital certificates) is X.509, defined by the International Telecommunications Union (ITU).
An X.509 certificatecontains the following:
* Version number
* Serial number
* Signature algorithm ID
* Issuer (CA) name
* Validity period (not before, not after)
* Subject name
* Subject public key (algorithm, public key)
* Key usage
* Optional extensions
* Certificate signature (algorithm, signature)

In PKI certificates used for encrypted email, code signing, or digital signatures, the subject of the certificate is an individual or organization.
For PKI certificates used to secure TLS (the protocol that protects secure HTTPS browser connections), the subject is the server (e.g., domain name of the website).

Certificates may be issued for a variety of purposes. These include providing assurance for the public keys of
* Computers/machines
* Individual users
* Email addresses
* Developers (code-signing certificates)

For web certificates, the owner of the website generates a public/private key pair and then prepares a key signing request that contains the folowing:
* The domain name of the website (with or without wildcards)
* The identity of the website owner
* The public key of the website owner
* A digital signature of the website owner


#### Certificate Authorities

Certificate authorities (CAs) are the glue that binds the public key infrastructure together.
These neutral organizations offer notarization services for digital certificates. To obtain a digital certificate from a reputable CA, you must prove your identity to the satisfaction of the CA.

The following list includes some of the major CAs who provide widely accepted digital certificates:
* Symantec
* IdenTrust
* Amazon Web Services
* GlobalSign
* Comodo
* Certum
* GoDaddy
* DigiCert
* Secom
* Entrust
* Actalis
* Trustwave

#### Certificate Lifecycle

The technical concepts behind the public key infrastructure are relatively simple.
In the following sections, we’ll cover the processes used by certificate authorities to create, validate, and revoke client certificates.

##### Enrollment

Enrollment When you want to obtain a digital certificate, you must first prove your identity to the CA in some manner; this process is called enrollment.
As mentioned in the previous section, this sometimes involves physically appearing before an agent of the certificate authority with the appropriate identification documents.
Some certificate authorities provide other means of verification, including the use of credit report data and identity verification by trusted community leaders.

Once you’ve satisfied the certificate authority regarding your identity, you provide them with your public key in the form of a certificate signing request (CSR).
The CA next creates an X.509 digital certificate containing your identifying information and a copy of your public key.
The CA then digitally signs the certificate using the CA’s private key and provides you with a copy of your signed digital certificate.
You may then safely distribute this certificate to anyone with whom you want to communicate securely.

Certificate authorities issue different types of certificates depending upon the level of identity verification that they perform.
The simplest, and most common, certificates are Domain Validation (DV) certificates, where the CA simply verifies that the certificate subject has control of the domain name.
Extended Validation (EV) certificates provide a higher level of assurance and the CA takes steps to verify that the certificate owner is a legitimate business before issuing the certificate.

##### Verification

When you receive a digital certificate from someone with whom you want to communicate, you verify the certificate by checking the CA’s digital signature using the CA’s public key.
You then must check the validity period of the certificate to ensure that the current date is after the starting date of the certificate and that the certificate has not yet expired.
Finally, you must check and ensure that the certificate was not revoked using a certificate revocation list (CRL) or the Online Certificate Status Protocol (OCSP).

At this point, you may assume that the public key listed in the certificate is authentic, provided that it satisfies the following requirements:
* The digital signature of the CA is authentic.
* You trust the CA.
* The certificate is not listed on a CRL.
* The certificate actually contains the data you are trusting.

**Certificate pinning** approaches instruct browsers to attach a certificate to a subject for an extended period of time.
When sites use certificate pinning, the browser associates that site with their public key. This allows users or administrators to notice and intervene if a certificate unexpectedly changes.

##### Revocation

Occasionally, a certificate authority needs to revoke a certificate. This might occur for one of the following reasons:
* The certificate was compromised (for example, the certificate owner accidentally gave away the private key).
* The certificate was erroneously issued (for example, the CA mistakenly issued a certificate without proper verification).
* The details of the certificate changed (for example, the subject’s name changed).
* The security association changed (for example, the subject is no longer employed by the organization sponsoring the certificate).

You can use three techniques to verify the authenticity of certificates and identify revoked certificates:

**Certificate Revocation Lists**

Certificate revocation lists (CRLs) are maintained by the various certificate authorities and contain the serial numbers of certificates that have
been issued by a CA and that have been revoked, along with the date and time the revocation went into effect.
The major disadvantage to certificate revocation lists is that they must be downloaded and cross-referenced periodically, introducing a period of latency between the time a certificate is revoked and the time end users are notified of the revocation.

**Online Certificate Status Protocol (OCSP)**

This protocol eliminates the latency inherent in the use of certificate revocation lists by providing a means for real-time certificate verification.
When a client receives a certificate, it sends an OCSP request to the CA’s OCSP server. The server then responds with a status of valid, invalid, or unknown.
The browser uses this information to determine whether the certificate is valid.

**Certificate Stapling**

The primary issue with OCSP is that it places a significant burden on the OCSP servers operated by certificate authorities.
These servers must process requests from every single visitor to a website or other user of a digital certificate, verifying that the certificate is valid and not revoked.

Certificate stapling is an extension to the Online Certificate Status Protocol that relieves some of the burden placed on certificate authorities by the original protocol.
When a user visits a website and initiates a secure connection, the website sends its certificate to the end user, who would normally then be responsible for contacting an OCSP server to verify the certificate’s validity.
In certificate stapling, the web server contacts the OCSP server itself and receives a signed and timestamped response from the OCSP server, which it then attaches, or staples, to the digital certificate.
Then, when a user requests a secure web connection, the web server sends the certificate with the stapled OCSP response to the user.
The user’s browser then verifies that the certificate is authentic and also validates that the stapled OCSP response is genuine and recent.
Because the CA signed the OCSP response, the user knows that it is from the certificate authority, and the timestamp provides the user with assurance that the CA recently validated the certificate. From there, communication may continue as normal.

#### Certificate Formats

Digital certificates are stored in files, and those files come in a variety of different formats, both binary and text-based:
* The most common binary format is the Distinguished Encoding Rules (DER) format. DER certificates are normally stored in files with the .der, .crt, or .cer extension.
* The Privacy Enhanced Mail (PEM) certificate format is an ASCII text version of the DER format. PEM certificates are normally stored in files with the .pem or .crt extension.
* The Personal Information Exchange (PFX) format is commonly used by Windows systems. PFX certificates may be stored in binary form, using either .pfx or .p12 file extensions.
* Windows systems also use P7B certificates, which are stored in ASCII text format.

| Standard                            | Format | File extension(s) |
|-------------------------------------|--------|-------------------|
| Distinguished Encoding Rules (DER)  | Binary | .der, .crt, .cer  |
| Privacy Enhanced Mail (PEM)         | Text   | .pem, .crt        |
| Personal Information Exchange (PFX) | Binary | .pfx, .p12        |
| P7B                                 | Text   | .p7b              |

### Key Management Practices

Secure use of cryptography depends on keeping symmetric and private keys confidential.
Attackers who can obtain or guess a secret key can compromise the confidentiality and integrity of the data protected by that key.

Proper cryptographic key management includes the following:
* Secure key generation
* Secure key storage and use
* Separation of duties, dual control, and split knowledge
* Timely key rotation and key change
* Key destruction

#### Secure Key Generation

There are two factors that make for a secure cryptographic key: length and randomness. Long, random keys have a higher “key strength,” as discussed earlier in this section.

Generally, the longer the key, the more difficult it is to attack encrypted messages - but what constitutes a secure key length changes with time as computer power increases and cryptanalysis techniques become more sophisticated.
In 1977, the U.S. government selected a symmetric block cipher it dubbed the DES, which was considered secure for nonclassified use (e.g., banking, e-commerce, etc.).
In 1999, it was demonstrated that DES-encrypted messages could be cracked in less than 24 hours.

Estimates are that, using modern computers, a brute-force attack on a 128-bit key would take longer than the age of the universe (~14 billion years) to crack.
Of course, as computing power continues to increase, and with the growing maturity of quantum computing, these estimates will someday be shattered, and the need for additional key length will surface.

The strength of a symmetric key also depends on its being unpredictable (i.e., unguessable). Even if only some of the bits can be guessed, that can significantly reduce the strength of the cipher.
Using a mechanism that will generate high-quality (i.e., cryptographically secure) random numbers is essential for key generation.
The best method is to use hardware-based true random number generators that rely on physical phenomena known to be truly random.
Such devices are embedded in various cryptographic hardware devices such as TPMs and HSMs, discussed earlier, as well as some microprocessors.

Software-based random number generators (RNGs), best referred to as pseudorandom number generators, are hard to get right.
For example, from 2006 until 2008, a defect introduced into the OpenSSL package in the Debian and Ubuntu Linux distributions caused all keys generated to be weak because of a bug in the random number generator (CVE-2008-0166).

#### Secure Key Storage and Use

Once you have generated a nice long and random key, how do you keep it secret?
Obviously, the first step is to encrypt your data encryption key (DEK) with another key, the key encryption key (KEK).
That solves the problem but creates another: how do you secure your KEK? This depends on the sensitivity of the underlying data being encrypted and the mechanisms that are appropriate for the system you are designing.

An HSM is specifically designed to securely generate and store KEKs and is among the more secure methods of protecting keys.
HSMs also provide for secure ways of replicating the KEKs between redundant HSMs and for enforcing controls so that no one individual can use the KEK to decrypt a data encryption key.
Compliance regimes on banks, payment processors, and other highly regulated organizations often require the use of an HSM.

For less demanding applications, the approach must be tailored to the specific requirements and risks. One could store the master key in any of the following:
* A hardware-encrypted USB key
* A password management app
* A secrets management package

#### Separation of Duties, Dual Control, and Split Knowledge

Some keys and data are so sensitive that the risk of an insider threat (e.g., a rogue or disgruntled employee) is too great to permit a single individual to have access to the key encryption key, the data encryption key, and the encrypted data, or sole access to administrative functions of the HSM.

These are three types of controls used to mitigate the risk of a rogue employee:
* Separation of duties
* Dual control
* Split knowledge

These three concepts are related but different.

**Separation of duties** (sometimes called **segregation of duties**) means that certain processes should require at least two different individuals to complete from beginning to end.
In the financial world, this might involve ensuring that the person who has authority to write checks is not the person who reconciles the bank statements.
In the cryptography world, it might dictate that the person with access to the encryption keys does not have access to the encrypted data.
Another form of separation of duties is ensuring that the people who administer a system do not have the authority to interfere with the logging system or tamper with the logs.

**Dual control** means that a specific step in a process requires two or more individuals.
In the financial world, this would be the requirement that two signatures be present on every check.
In the cryptography world, it might require that two or more individuals present their credentials to be able to use the key encryption key to decrypt a data encryption key.

For access to a system that supports multifactor authentication, dual control could involve entrusting the password to one individual, and the MFA device to a different individual.

Note that dual control is often incorrectly referred to as the separation of duties. Be aware of the difference and examine the control to determine if it is truly separation of duties or dual control.

**Split knowledge** is when a key (or password) is split into two or more pieces such that each piece is unusable by itself, and it requires that two (or more) pieces be brought together to decrypt the data (or access the system).

For example, a vendor might generate a large key and split it into (say _m_) multiple pieces.
In this model, a minimum of _n_ pieces are required to recreate the key encryption key. The numbers _n_ and _m_ are configurable so that one can, for example, split the key into a dozen pieces, but only require any three of the key holders to come together to unlock the key.

#### Timely Key Rotation and Key Change

Keys should have a limited lifespan. If there is evidence or even suspicion that a key has been compromised, it ought to be rotated as soon as feasible.
Even if the confidentiality of the key has been maintained, it ought to be replaced periodically.
Further, best practice is to also perform key rotation when essential personnel with access to cryptographic material leave their positions.

Why rotate keys?
* To limit the damage should the key be discovered by an attacker
* To limit the amount of data encrypted by the same key (the more data encrypted using the same key, the easier it is to crack the encryption)
* To limit the time available to the attacker to crack the cipher (if none of your data is encrypted with the same key for longer than one year, then any brute-force attack must be able to be completed within a year of the key’s generation)

#### Key Destruction

Once a key has been retired and it has been determined that there is no data that has been encrypted using that key that will need to be decrypted, then the key must be securely destroyed.
This involves locating every copy of the key and deleting it in a manner appropriate for the media on which it was stored to ensure that it cannot be recovered.

Depending on the media and the risk of it becoming accessible to unauthorized individuals, this may require overwriting the storage, degaussing of the media, or physical destruction of the media or device containing the media.

Records ought to be kept that document the locations of the destroyed keys and the means used to ensure secure destruction.

### Digital Signatures and Digital Certificates

**Digital signatures** use cryptographic techniques to replicate the intent of a signature: authentication (to give the recipient confidence that the message originated with a specific entity), nonrepudiation (evidence that the originator did, in fact, compose the message), and integrity (confidence the message has not been altered after it was signed).

The message to be signed is passed through a cryptographically secure hash function that produces a fixed-length output (typically between 160 and 512 bits) called a **Message Digest**.
This hash value is then encrypted using the message author’s private key to produce a digital signature. The digital signature is transmitted as an appendix to the message.

When a recipient wants to verify the document, they compute the Message Digest for the message, as received.
They then decrypt the digital signature using the author’s public key to produce the originator’s Message Digest. If the two are identical, then the recipient knows the following:
1. The message has not been tampered with (i.e., integrity has been preserved).
2. The message has originated with the owner of the public/private key pair (i.e., authentication and nonrepudiation).

To protect the security of digital signatures, it is strongly recommended that the private key used to sign messages only be used for digital signing and not for any other purpose (such as general message encryption).

There are a number of possible vulnerabilities with digital signatures:
* Hash collision
* Private key disclosure
* CA compromise

#### HMAC

The hashed message authentication code (HMAC) algorithm implements a partial digital signature - it guarantees the integrity of a message during transmission, but it does not provide for nonrepudiation.

HMAC can be combined with any standard message digest generation algorithm, such as MD5, SHA-2, or SHA-3, by using a shared secret key.
Therefore, only communicating parties who know the key can generate or verify the digital signature.
If the recipient decrypts the message digest but cannot successfully compare it to a message digest generated from the plaintext message, that means the message was altered in transit.

Because HMAC relies on a shared secret key, it does not provide any nonrepudiation functionality (as previously mentioned).
However, it operates in a more efficient manner than the digital signature standard described in the following section and may be suitable for applications in which symmetric key cryptography is appropriate.
In short, it represents a halfway point between unencrypted use of a message digest algorithm and computationally expensive digital signature algorithms based on public key cryptography.

#### Digital Signature Standard

The National Institute of Standards and Technology specifies the digital signature algorithms acceptable for federal government use in Federal Information Processing Standard (FIPS) 186-4, also known as the Digital Signature Standard (DSS).
This document specifies that all federally approved digital signature algorithms must use the SHA-3 hashing functions.

DSS also specifies the encryption algorithms that can be used to support a digital signature infrastructure. There are three currently approved standard encryption algorithms:
* The Digital Signature Algorithm (DSA) as specified in FIPS 186-4. This algorithm is a variant of an algorithm developed by Dr. Taher Elgamal, the creator of the ElGamal asymmetric cryptosystem discussed earlier in this chapter.
* The Rivest–Shamir–Adleman (RSA) algorithm, as specified in ANSI X9.31.
* The Elliptic Curve DSA (ECDSA), as specified in ANSI X9.62.

As this book went to press in 2021, the next version of the Digital Signature Standard, FIPS 186-5, remained in draft form.
The draft proposal removes DSA as an approved algorithm, retains RSA and ECDSA, and adds the Edwards-Curve Digital Signature Algorithm (EdDSA) to DSS.

### Nonrepudiation

Nonrepudiation is the ability to prove that a message must have originated from a specific entity.
This can be critically important, for example, with contracts or other legal documents, as well as instructions to banks or orders to suppliers.
Only with the ability to demonstrate nonrepudiation of the received communication can the recipient act on the message with confidence that the originator is accountable for the content of the message.

Nonrepudiation is accomplished by the originator’s signing the message using a private key known only to the originator, and which the originator commits to protecting.
Protecting a private signing key means keeping it confidential and, if the key is compromised, promptly revoking the matching public key.

#### Blockchain and Nonrepudiation

Another approach to nonrepudiation is to use a blockchain.
Blockchain is a form of a decentralized and distributed ledger in which records are recorded and linked together, using cryptographic hashes, meaning that to change any record in the blockchain, one must change every subsequent block.
Since the blockchain is distributed (i.e., stored by multiple systems), it requires the collusion of a majority of the blockchain participants.
For a sufficiently widely (and independently) operated blockchain, this is infeasible. For example, Bitcoin currently (early 2021) has approximately 12,000 nodes across 100 countries.

### Integrity

Cryptographic methods can do more than just protect the confidentiality of messages and help prove the identity of the originator. They can also be used to protect the integrity of messages by detecting tampering.

A hash function is an algorithm that takes a block of data (i.e., a message or file) and computes a derived value such that any change to the data will result in a change to the hash value.
Effective hashing functions need additional properties too, as will be covered in this chapter.

This function can be used to verify the integrity of the data by comparing the hash value of the original data with the hash value of the data at some later point in time.

Using a cryptographic hash to detect tampering of a message involves the following three steps (as illustrated in Figure 3.28):
1. Generate the hash value (H1) by applying the hash function to the original block of data or message (M1).
2. Generate the hash value (H2) by applying the hash function to the block of data or message (M2) to be verified.
3. If (H1) is the same as (H2), then that indicates that the two messages are likely to be identical and have not been tampered with.
As we shall shortly see, however, the key question is “how likely?” What degree of confidence should we have that two messages are identical if their hash values are identical?

When two different messages generate the same hash value, it is called a collision, so we need a hashing function that makes it almost impossible to create an intentional collision.

In our previous example, two factors made it trivial to create a collision:
* The simplicity of the algorithm made it easy to determine what changes need to be made to the modified message to change the hash (checksum) to match the original message’s.
* Even if the algorithm had been complex, the shortness of the hash (16 bits) means that, with only 65,536 possible hash values, it would not take long to repeatedly make random changes to the end of the message until one happened upon a collision.

Cryptographically secure hash algorithms must therefore be sufficiently complex that it is not possible to determine what changes need to be made to a message to create a specific hash result, and the length of the hash value (i.e., number of bits) must be sufficiently large to make brute-force attacks computationally infeasible.

According to RSA Security, there are five basic requirements for a cryptographic hash function:
* The input can be of any length.
* The output has a fixed length.
* The hash function is relatively easy to compute for any input.
* The hash function is one-way (meaning that it is extremely hard to determine the input when provided with the output). One-way functions and their usefulness in cryptography are described in Chapter 6.
* The hash function is collision resistant (meaning that it is extremely hard to find two messages that produce the same hash value).

#### SHA

The Secure Hash Algorithm (SHA) and its successors, SHA-1, SHA-2, and SHA-3, are government standard hash functions promoted by the National Institute of Standards and Technology (NIST) and are specified in an official government publication - the Secure Hash Standard (SHS), also known as Federal Information Processing Standard (FIPS) 180.

SHA-1 takes an input of virtually any length (in reality, there is an upper bound of approximately 2,097,152 terabytes on the algorithm) and produces a 160-bit message digest.
The SHA-1 algorithm processes a message in 512-bit blocks. Therefore, if the message length is not a multiple of 512, the SHA algorithm pads the message with additional data until the length reaches the next highest multiple of 512.

Cryptanalytic attacks demonstrated that there are weaknesses in the SHA-1 algorithm, and therefore, NIST deprecated SHA-1 and no longer recommends its use for any purpose, including digital signatures and digital certificates.
Web browsers dropped support for SHA-1 in 2017.

As a replacement, NIST announced the SHA-2 standard, which has four major variants:
* SHA-256 produces a 256-bit message digest using a 512-bit block size.
* SHA-224 uses a truncated version of the SHA-256 hash that drops 32 bits to produce a 224-bit message digest using a 512-bit block size.
* SHA-512 produces a 512-bit message digest using a 1,024-bit block size.
* SHA-384 uses a truncated version of the SHA-512 hash that drops 128 bits to produce a 384-bit digest using a 1,024-bit block size.

The cryptographic community generally considers the SHA-2 algorithms secure, but they theoretically suffer from the same weakness as the SHA-1 algorithm.
In 2015, the federal government announced the release of the Keccak algorithm as the SHA-3 standard.
The SHA-3 suite was developed to serve as drop-in replacement for the SHA-2 hash functions, offering the same variants and hash lengths using a different computational algorithm.
SHA-3 provides the same level of security as SHA-2, but it is slower than SHA-2, so SHA-3 is not commonly used outside of some specialized cases where the algorithm is efficiently implemented in hardware.

#### MD5

The Message Digest 2 (MD2) hash algorithm was developed by Ronald Rivest (the same Rivest of Rivest, Shamir, and Adleman fame) in 1989 to provide a secure hash function for 8-bit processors.
In 1990, Rivest enhanced his message digest algorithm to support 32-bit processors and increase the level of security with a version called MD4.

In 1991, Rivest released the next version of his message digest algorithm, which he called MD5. It also processes 512-bit blocks of the message, but it uses four distinct rounds of computation to produce a digest of the same length as the MD2 and MD4 algorithms (128 bits).
MD5 has the same padding requirements as MD4 - the message length must be 64 bits less than a multiple of 512 bits.

MD5 implements additional security features that reduce the speed of message digest production significantly. Unfortunately, cryptanalytic attacks demonstrated that the MD5 protocol is subject to collisions, preventing its use for ensuring message integrity.
Specifically, Arjen Lenstra and others demonstrated in 2005 that it is possible to create two digital certificates from different public keys that have the same MD5 hash.

Some tools and systems still rely on MD5, so you may see it in use today, but it is now far better to rely on more secure hashing algorithms, such as SHA-2.

#### RIPEMD

The RIPE Message Digest (RIPEMD) series of hash functions is an alternative to the SHA family that is used in some applications, such as Bitcoin cryptocurrency implementations.

The family contains a series of increasingly sophisticated functions:
* RIPEMD produced a 128-bit digest and contained some structural flaws that rendered it insecure.
* RIPEMD-128 replaced RIPEMD, also producing a 128-bit digest, but it is also no longer considered secure.
* RIPEMD-160 is the replacement for RIPEMD-128 that remains secure today and is the most commonly used of the RIPEMD variants. It produces a 160-bit hash value.

#### Comparison of Hash Algorithm Value Lengths

| Name              | Hash value length                         |
|-------------------|-------------------------------------------|
| HAVAL             | 128, 160, 192, 224, and 256 bits          |
| HMAC              | Variable                                  |
| MD5               | 128                                       |
| SHA-1             | 160                                       |
| SHA2-224/SHA3-224 | 224                                       |
| SHA2-256/SHA3-256 | 256                                       |
| SHA2-384/SHA3-384 | 384                                       |
| SHA2-512/SHA3-512 | 512                                       |
| RIPEMD-128        | 128                                       |
| RIPEMD-160        | 160                                       |
| RIPEMD-256        | 256 (but with equivalent security to 128) |
| RIPEMD-320        | 320 (but with equivalent security to 160) |

## UNDERSTAND METHODS OF CRYPTANALYTIC ATTACKS

### Brute Force

In a brute-force attack, the attacker tries all possible key values until they find the one that works.
In the case of a symmetric cipher, this means the attacker tries all possible keys until they have decrypted the ciphertext into something that matches the known plaintext.
In many cases, full knowledge of the plaintext is not needed.
If one knows the general format of the message or the language of the message, one can check the output of the decryption against certain heuristics to determine if the output is likely to be the original plaintext (i.e., reading the output to see if it makes sense).

Obviously, the primary defense against brute-force attacks on symmetric ciphers is key length, which is why the minimum key length for AES is 128 bits.

In the case of cryptographically secure hashes (such as are used for securing passwords), the attack scenario assumes one has a dump of the system’s password file containing all the passwords encrypted using a secure hash.
The attacker then tries to compare the password hashes with guesses to see which passwords can be determined.

There are two defenses against such attacks, neither of which was used by LinkedIn at the time:
* Hashing complexity
* Salting

When it comes to password hashing, slower is better . . . much better.
One of the currently recommended algorithms is the Password-Based Key Derivation Function 2 (PBKDF2) - using the same eight-GPU engine, one can generate only 10,000 hashes per second (i.e., roughly 7 million times slower).

The counterattack to slow hashing is a precomputed database of hashes.
The attacker takes a dictionary of common passwords (hundreds of millions of passwords from past breaches are freely available online) and every possible password up to, say, eight characters, and runs it through the hashing algorithm in advance.
When coming into possession of a breached password file, there is no need to lumber through 10,000 hashes per second; if the password hashes are already known, all that is needed is just to look up each hash.

If the storage space it would take to store these hashes is too large, to compress the hashes at the cost of slightly longer lookup times, the technique called rainbow tables can be used.

The defense against stored dictionary or rainbow table attacks is to combine the password with a unique large random number (called the salt) and then store the combined hash of the password and salt.
In this manner, one would have to precompute 2<sup>n</sup> rainbow tables (if the salt has n bits), so the attack is not feasible.

So, the password file contains two fields (in addition to the user’s login name and other metadata):
* The salt
* The output of HASH (salt + password)

To be secure, the salt must be the following:
* Long (at least 16 bytes, and preferably 32 or 64 bytes)
* Random (i.e., the output of a cryptographically secure pseudo-random number generator)
* Unique (calculate a new salt for every user’s password, and a new salt every time the password is changed)
  
Some go one step further and encrypt the hash using a symmetric cipher, but this is considered to be unnecessary and adds little additional security.
In keeping with the nomenclature used in password cryptography, this step is called **pepper**.

### Ciphertext Only

In this situation, an attacker only has access to the encrypted traffic (ciphertext).
In many cases, some information about the plaintext can be guessed (such as the language of the message, which can lead to knowledge of the character probability distribution or the format of the message, which can give clues to parts of the plaintext).

WEP, the original security algorithm for WiFi, is vulnerable to a number of ciphertext-only attacks.
By capturing a sufficient number of packets (which typically can be gathered within minutes on a busy network), it is possible to derive the key used in the RC4 stream cipher.

### Known Plaintext

In this situation, the attacker knows some or all of the plaintext of one or more messages (as well as the ciphertext).
This frequently happens when parts of the message tend to be fixed (such as protocol headers or other relatively invariant parts of the messages being communicated).

An example of a known-plaintext attack is the famous German Enigma cipher machine, which was cracked in large part by relying upon known plaintexts.
Many messages contained the same word in the same place, or contained the same text (e.g., “Nothing to report”), making deciphering the messages possible.

### Chosen Plaintext Attack

In this situation, the attacker is able to submit any plaintext the attacker chooses and obtain the corresponding ciphertext.

The classic example of a chosen-plaintext attack occurred during WWII when the U.S. intercepted messages indicating the Japanese were planning an attack on a location known as “AF” in code.
The United States suspected this might be Midway Island, and to confirm their hypothesis, they arranged for a plaintext message to be sent from Midway Island indicating that the island’s water purification plant had broken down.
When the Japanese intercepted the message and then transmitted a coded message referring to “AF,” the United States had the confirmation it needed.

### Frequency Analysis

In cryptanalysis, frequency analysis is the study of the frequency of characters (letters, numbers, or groups of either) in ciphertext.
This attack works best against rudimentary cryptographic approaches such as substitution ciphers that map each character in a given set (e.g., alphabet) to another character (for example, a = z, b = y, and so on).
By understanding the typical distribution of characters in a given language, frequency analysis can help a cryptanalyst deduce plaintext equivalents of commonly occurring ciphertext characters.
Most modern cryptographic algorithms are not susceptible to frequency analysis.

### Chosen Ciphertext

In this situation, the attacker is able to submit any ciphertext and obtain the corresponding plaintext.

An example of this was the attack on SSL 3.0 developed by Bleichenbacher of Bell Labs, which could obtain the RSA private key of a website after trying between 300,000 and 2 million chosen ciphertexts.

### Implementation Attacks

Implementation attack is a broad term used to describe any attack that exploits implementation weaknesses, such as in software, hardware, or the encryption algorithm itself.

### Side-Channel Attacks

Side-channel attacks involve measuring artifacts of the cryptographic process to deduce information to assist with compromising encrypted information. These artifacts can include the following:
* Timing
* Cache access
* Power consumption
* Electromagnetic emanations
* Error information

The time taken to encrypt or decrypt a block of data can vary depending on the key or plaintext, and a careful analysis of the time taken to encrypt or decrypt the data can reveal information.
The time to perform a cryptographic operation can vary for a number of reasons:
* Conditional branches within the code, which can change the time of execution depending on the branches taken, which in turn depend on the value of the key or plaintext
* CPU instructions that take variable time to complete depending on the operands (e.g., multiplication and division)
* Memory access, which can vary depending on where the data is located (type of memory) or the access history (thus affecting the cache and thus the speed of memory access)

Cache attacks typically involve processes running on different virtual machines on the same physical processor.
As the VM performing the encryption is time sliced with the VM running the attacker’s processes, the attacker can probe the processor’s cache to deduce information about the plaintext and the key, and thus compromise the encryption process.

The power consumed by the device performing the cryptographic operation may vary depending on the instructions executed, which in turn depend on the key and data being encrypted.
By carefully monitoring the power consumed by the device, it can sometimes be possible to extract information about the key or plaintext.
This type of attack has been most successfully demonstrated against smartcards because of the relative ease with which the device’s power consumption can be monitored, but the attack mechanism has wide applicability.

All electronic systems emit electromagnetic radiation, and it is possible to capture this, sometimes at some distance from the device.
These radio signals can sometimes be analyzed to reveal information about the data being processed by the device.
Early examples of this type of attack involved analyzing the emanations of cryptographic devices that printed the decrypted message on teletypewriters to determine which characters were being printed.

Countermeasures exist, but in some cases, they can be very difficult to implement or can exact a considerable performance penalty.
In the case of timing attacks, it is necessary to modify the algorithm so that it is isochronous, which is to say it runs in constant time regardless of the key and data being processed.

Error information provided (or leaked) by decryption software can provide useful information for attackers.
In the Padding Oracle Attack, a system that can be sent any number of test messages, and which generates a distinctive error for encrypted messages that are not properly padded, can be used to decrypt messages without knowing the key.
The defense is to report generic errors and not to distinguish between padding errors and other errors.

### Fault Injection

Fault injection attacks are side-channel attacks that involve deliberately injecting faulty or erroneous inputs and observing the errors and outputs. See the “Side-Channel Attacks” section for more detail.

### Timing Attacks

A timing attack is a side-channel attack that involves the attacker attempting to compromise a cryptosystem by monitoring the time taken to execute algorithmic functions. See the “Side-Channel Attacks” section for more detail.

### Meet in the Middle

Attackers might use a meet-in-the-middle attack to defeat encryption algorithms that use two rounds of encryption.
This attack is the reason that Double DES (2DES) was quickly discarded as a viable enhancement to the DES encryption (it was replaced by Triple DES, or 3DES).

In the meet-in-the-middle attack, the attacker uses a known plaintext message. The plaintext is then encrypted using every possible key (k1), and the equivalent ciphertext is decrypted using all possible keys (k2).
When a match is found, the corresponding pair (k1, k2) represents both portions of the double encryption.
This type of attack generally takes only double the time necessary to break a single round of encryption (or 2<sup>n</sup> rather than the anticipated 2<sup>n</sup> * 2<sup>n</sup>), offering minimal added protection.

### Man-in-the-Middle

An MITM attack requires that the attacker be able to intercept and relay messages between two parties.

To defend against such attacks, Alice needs to have confidence that the message containing Bob’s key actually originated from Bob (and not the MITM attacker, Michelle).
In the case of encrypted HTTPS web traffic, this is done by relying upon public key certificates attested to by a CA (as described earlier in the “Public Key Infrastructure” section). But if the CA is compromised, the attacker can circumvent the identity authentication protections of HTTPS.

### Pass the Hash

Pass the hash is an attack that occurs when an attacker obtains a password hash and passes it through for authentication.
With this type of attack, the attacker does not need to decrypt the hash or otherwise obtain the plaintext password.
This type of attack targets the authentication protocol, as opposed to the hash or any other cryptographic elements.

A least privilege security model can help limit the likelihood and impact of a potential pass-the-hash attack by reducing an attacker’s ability to gain and use elevated privileges.
Password management processes and tools that rotate passwords (preferably automatically) can also help fight against this attack.

### Kerberos Exploitation

Kerberos is a network authentication protocol that uses symmetric-key encryption to provide strong authentication for client/server environments.
The protocol operates on the basis of tickets that allow nodes (systems) on a network to prove their identity to one another.

As with any widely used protocols, hackers have sought and found ways to compromise Kerberos.
Most of successful Kerberos exploits take advantage of system vulnerabilities (such as using weak algorithms), malware, or weak passwords.
A common exploit, called pass the ticket, is the process of an attacker forging a ticket and passing it along to authenticate to a resource.

Multifactor authentication should be used to defeat phishing attacks and password weaknesses in Kerberos implementations.
Logging and monitoring of your Active Directory domains should also be enabled to detect access to resources without proper authentication (e.g., via pass the ticket).

Kerberos exploitation attacks include the following:

**Overpass the Hash**
This is an alternative to the PtH attack used when NTLM is disabled on a network. Even if NTLM is disabled on a network, systems still create an NTLM hash and store it in memory.
An attacker can request a ticket-granting ticket (TGT) with the user’s hash and use this TGT to access network resources.
This is sometimes called pass the key.

**Pass the Ticket**
In a pass-the-ticket attack, attackers attempt to harvest tickets held in the lsass.exe process.
After harvesting the tickets, attackers inject the ticket to impersonate a user.

**Silver Ticket**
A silver ticket uses the captured NTLM hash of a service account to create a ticket-granting service (TGS) ticket.
Service accounts (user accounts used by services) use TGS tickets instead of TGT tickets.
The silver ticket grants the attacker all the privileges granted to the service account.

**Golden Ticket**
If an attacker obtains the hash of the Kerberos service account (KRBTGT), they can create tickets at will within Active Directory.
This gives them so much power it is referred to as having a golden ticket. The KRBTGT account encrypts and signs all Kerberos tickets within a domain with a hash of its password.
Because the password never changes, the hash never changes, so an attacker only needs to learn the hash once.
If an attacker gains access to a domain administrator account, they can then log on to a domain controller remotely and run Mimikatz to extract the hash.
This allows attackers to create forged Kerberos tickets and request TGS tickets for any service.

**Kerberos Brute-Force**
Attackers can use the Python script kerbrute.py on Linux systems or Rubeus on Windows systems.
In addition to guessing passwords, these tools can guess usernames. Kerberos reports whether or not usernames are valid.

**ASREPRoast**
ASREPRoast identifies users that don’t have Kerberos preauthentication enabled. Kerberos preauthentication is a security feature within Kerberos that helps prevent password-guessing attacks.
When preauthentication is disabled, attackers can send an authentication request to a KDC. The KDC will reply with a ticket-granting ticket (TGT), encrypted with the client’s password as the key.
The attacker can then perform an offline attack to decrypt the ticket and discover the client’s password.

**Kerberoasting**
Kerberoasting collects encrypted ticket-granting service (TGS) tickets. Service accounts (user accounts used by services) use TGS tickets instead of TGT tickets.
After harvesting these tickets, attackers can crack them offline.
A TGS ticket is used by services running in the context of a user account. This attack attempts to find users that don’t have Kerberos preauthentication.

### Ransomware

Ransomware is malicious software that infects a system, encrypts the victim’s files, and renders them unavailable until a ransom is paid.
In a typical ransomware attack, the victim is given instructions on how to pay a fee to get the decryption key required to recover their data.
Attackers will often request payment in Bitcoin, due to its anonymity.

Protection against ransomware is similar to best practices for protecting your systems against any type of malware.
Keep your operating systems and applications patched and up-to-date, limit use of administrative privileges (i.e., least privilege), and use trusted antimalware software with updated signatures, among the other system hardening best practices.

Aside from maintaining overall good security hygiene, backing up your data frequently is the best way to recover from a ransomware attack - without paying the fee!
With routine backups stored securely, you will be able to revert to a known good state, should you be faced with such an attack.


## APPLY SECURITY PRINCIPLES TO SITE AND FACILITY DESIGN

The general security principles outlined earlier for information security also have application to site and facility design.
The CIA Triad and supporting security principles apply here and guide our application of security principles to this challenge:
* **Confidentiality and Integrity:** The primary physical threat to confidentiality and integrity is unauthorized access (e.g., intruders and theft).
* **Availability:** In addition to the threat to availability from unauthorized access, availability can also be compromised intentionally or accidentally by a range of events:
  * Environmental events such as fire, floods, storms, or earthquakes
  * Infrastructure events such as power outages, cooling (HVAC) failure, floods (from burst water pipes)


## DESIGN SITE AND FACILITY SECURITY CONTROLS

### Wiring Closets/Intermediate Distribution Facilities

The vulnerabilities related to networking distribution differ slightly between a data center and an office.

In a data center owned and managed for a single company (or cloud-hosting provider), usually the network distribution will be within the same perimeter as the servers themselves, so the physical and environmental security controls will apply to both.

In a colocation facility, different clients will have access to different areas of the facility (to access the equipment owned by or assigned to them for their exclusive use).
In this situation, the wiring closets are managed by the hosting provider and must not be accessible to clients, as it would permit even authorized clients to access or affect service to other clients.

In an office, intermediate distribution facilities need to be protected from both malicious outsiders and insider threats, not to mention environmental risks.

Not all insider threats are malicious - well-meaning staff trying to troubleshoot a networking problem can wreak havoc in a wiring closet.

Too often, network switches and other pieces of intermediate distribution equipment are placed in any convenient out-of-the-way location, sharing space with other building infrastructure (e.g., electrical, plumbing, heating, or ventilation).
When this is being contemplated, consider the additional risks from environmental impacts (flooding, overheating, or electromagnetic interference from electrical equipment).
A small wiring closet full of network switches with poor (or no) ventilation can overheat, at a minimum shortening the life of your equipment, causing random resets, errors, and even total failure in the worst case.

Wiring closets can also be at risk from threats such as burst or leaking pipes that pass through or near the space or overflowing washrooms on the floors above.
Again, if the obvious solution (moving the location of the wiring closet) is not an option, one must consider compensating controls - in this case a shield over the top of the equipment to deflect any falling water, and a rack (to keep all equipment and wiring sufficiently high off the floor) to prevent any pooling of water from affecting the equipment.

One must consider not just network infrastructure that you install for your internal purposes, but also cabling for other services (telephone, alarm, electronic door locks, etc.) that may transit spaces outside of your control.
How useful are your electronic door locks if the cables powering them are in the suspended ceiling in the hallway outside your office?
What good is your alarm going to be if the signal is carried on telephone wires that can be found behind an unlocked panel in the public hallway and easily tampered with?

### Server Rooms/Data Centers

Just as with office space, the physical security of your data center can span a wide range of controls. You need to determine the risks in order to ensure you secure, but do not over-secure, your data center.

Security controls need to be selected to address the following:
* Physical access risks (see the “Apply Security Principles to Site and Facility Design” section)
* HVAC (see the “Utilities and Heating, Ventilation, and Air Conditioning” section)
* Environmental risks (see the “Environmental Issues” section)
* Fire risks (see the “Fire Prevention, Detection, and Suppression” section)

It is not enough to design and build your server room or data center properly, one must also have the proper procedures in place to ensure the data center continues to operate properly and securely.
These controls should cover, at a minimum, the following:
* Personnel (e.g., background checks, training, or access procedures)
* Maintenance
* Logging, monitoring, and alerting
* Control testing and auditing

The art and science of data center design is well understood. Anyone charged with the responsibility of working on such a project (or selecting a vendor to provide hosting or colocation) ought to review the guidance available from organizations such as the following:
* American Society of Heating, Refrigerating and Air-Conditioning Engineers (ASHRAE)
* ANSI / BICSI: ANSI/BICSI 002-2014, Data Center Design and Implementation Best Practices
* Electronic Industries Association and Telecommunications Industries Association (EIA/TIA): ANSI/TIA-942, Telecommunications Infrastructure Standard for Data Centers
* European Union (EU): EN 50600 series of standards
* International Organization for Standardization (ISO): ISO/IEC 30134 series, “Information technology – Data centres – Key performance indicators”
* Uptime Institute: Tier Standards

### Intrusion Detection Systems

#### Motion Detectors

A motion detector, or motion sensor, is a device that senses movement or sound in a specific area, and it is a common element of intruder detection systems.

Many types of motion detectors exist, including the following:
* A **digital motion detector** monitors for significant or meaningful changes in the digital pattern of a monitored area. This is effectively a smart security camera.
* A **passive infrared (PIR)** or **heat-based motion detector** monitors for significant or meaningful changes in the heat levels and patterns in a monitored area.
* A **wave pattern motion detector** transmits a consistent low ultrasonic or high microwave frequency signal into a monitored area and monitors for significant or meaningful changes or disturbances in the reflected pattern.
* A **capacitance motion detector** senses changes in the electrical or magnetic field surrounding a monitored object.
* A **photoelectric motion detector** senses changes in visible light levels for the monitored area. Photoelectric motion detectors are usually deployed in internal rooms that have no windows and that are kept dark.
* A **passive audio motion detector** listens for abnormal sounds in the monitored area.

#### Intrusion Alarms

Whenever a motion detector registers a significant or meaningful change in the environment, it triggers an alarm. An alarm is a separate mechanism that triggers a deterrent, a repellent, and/or a notification.

* **Deterrent alarms:** Alarms that trigger deterrents may engage additional locks, shut doors, and so on. The goal of such an alarm is to make further intrusion or attack more difficult.
* **Repellent alarms:** Alarms that trigger repellents usually sound an audio siren or bell and turn on lights. These kinds of alarms are used to discourage intruders or attackers from continuing their malicious or trespassing activities and force them off the premises.
* **Notification alarms:** Alarms that trigger notification are often silent from the intruder/attacker perspective but record data about the incident and notify administrators, security guards, and law enforcement.
A recording of an incident can take the form of log files and/or security camera recordings. The purpose of a silent alarm is to bring authorized security personnel to the location of the intrusion or attack in hopes of catching the person(s) committing the unwanted or unauthorized acts.

Alarms are also categorized by where they are located: local, centralized or proprietary, or auxiliary.
* **Local alarm system:** Local alarm systems must broadcast an audible (up to 120 decibels [dB]) alarm signal that can be easily heard up to 400 feet away.
Additionally, they must be protected from tampering and disablement, usually by security guards.
For a local alarm system to be effective, a security team or guards must be positioned nearby who can respond when the alarm is triggered.
* **Central station system:** The alarm is usually silent locally, but offsite monitoring agents are notified so that they can respond to the security breach.
Most residential security systems are of this type. Most central station systems are well-known or national security companies, such as Brinks and ADT.
A proprietary system is similar to a central station system, but the host organization has its own onsite security staff waiting to respond to security breaches.
* **Auxiliary alarm system:** Auxiliary alarm systems can be added to either local or centralized alarm systems.
When the security perimeter is breached, emergency services are notified to respond to the incident and arrive at the location. This can include fire, police, and medical services.

#### Secondary Verification Mechanisms

When motion detectors, sensors, and alarms are used, secondary verification mechanisms should be in place. As the sensitivity of these devices increases, false triggers occur more often.
Innocuous events such as the presence of animals, birds, bugs, or authorized personnel can trigger false alarms.
Deploying two or more detection and sensor systems and requiring two or more triggers in quick succession to occur before an alarm is issued may significantly reduce false alarms and increase the likelihood that alarms indicate actual intrusions or attacks.

### Media Storage Facilities

In addition to the usual threats to confidentiality, integrity, and availability faced by any facility containing information technology equipment, media storage facilities must implement additional environmental controls to ensure that the stored media do not degrade over time (or at least degrade as slowly as can reasonably be provided for).

The specific controls will depend on the media being stored, the manufacturer’s recommendations, and the specific threats anticipated, but typically they will include the following:
* Controlled and stable temperature and humidity
* Air filtration and positive air pressure to minimize infiltration by airborne dust and microfine particulate matter or contaminants (such as corrosive fumes and engine exhaust from diesel generators or nearby vehicles)
* Appropriate floor covering to minimize static electricity
* Careful siting of the media storage facilities to avoid magnetic fields that might arise from electrical equipment (e.g., transformers or motors)

Other considerations with respect to media storage include the following:
* If the environment of the media storage facility is different (in temperature or humidity) than the production environment in which the tape will be read, then time must be allowed for the tape to acclimate to the different environment before being processed.
* Some tape media needs to be “retensioned” (i.e., unspooled and respooled), depending on the tape manufacturer’s recommendations (e.g., every three years).
* For longer archival storage, it is advisable to read the data from the stored media and rerecord on new media. Again, the tape manufacturer’s recommendations ought to be followed with respect to the appropriate frequency (e.g., every six years).
* Appropriate procedures are necessary for the tracking of media that are placed in, and removed from, storage. This may include bar code scanning and separation-of-duties controls requiring two people to sign in and sign out media items.
* Fire detection and suppression systems may need to be installed.
* Proper housekeeping is required to reduce the possibility of fire and to reduce the fuel available should a fire break out.
On a related note, media storage facilities ought to be used only to store media and should not be shared with other general storage.
* Depending on the risk analysis and costs associated with managing on-premises media storage, it may be appropriate to retain the services of an off-site media storage service that will handle the physical security and environmental concerns related to secure long-term storage of media.
This can be used for all media, or a portion, in order to provide disaster recovery should the primary media storage facility be damaged by fire or other calamity.
* Appropriate media end-of-life procedures must be enforced to sanitize (e.g., by degaussing magnetic media) and securely destroy media before disposal so that sensitive information cannot be extracted from the media once it leaves the control of the organization.

### Evidence Storage

In addition to the security controls appropriate for other facilities (including media storage, should you be storing evidence in the form of magnetic media), evidence storage requires attention to physical controls that can assist in protecting the chain of custody necessary to prove that evidence used in court has not been tampered with or contaminated.

These controls include, at a minimum, a logbook that indelibly records every item that has been placed in, or removed from, evidence storage.
Additional controls that can increase the confidence in the chain-of-custody log with respect to the evidence storage room include the following:
* Strict policies surrounding who is permitted access to the evidence storage room, the information that is to be entered into the log, and procedures governing the management of the access keys to the evidence storage room
* Video monitoring
* Double locks on the evidence storage room doors, or a locked storage cabinet inside the locked evidence storage room, with separation of duties surrounding the control of the keys, so that two people are required to access the evidence storage

### Restricted and Work Area Security

Work area security must be designed in response to a risk assessment (including threat modeling) and in accordance with security principles and the appropriate controls to mitigate risk.
The considerations to be addressed include least privilege, need-to-know, separation of duties, dual control, defense in depth, and compliance obligations.
This is especially important in the context of implementing facility security controls. No other facet of site security controls more directly affects the people of an organization.

#### Least Privilege and Need-to-Know

Access to restricted and secure areas must be granted only to the extent necessary for individuals to carry out their responsibilities, in accordance with formally approved policies and procedures.
Access also must be periodically reviewed to ensure that the justification
for access has not changed. Furthermore, detailed auditable records attesting to the
previous must be maintained.

#### Separation of Duties and/or Dual Control

Depending on the risk assessment, it may be appropriate to require more than one
authenticated staff member to be present in order to obtain access to the secure work
area. This can be an administrative control, verified through guard records or video sur

#### Defense in Depth

The facility ought to be designed with layers of security controls supporting a hierarchy of security levels, from public on the exterior of the building (and possibly including common entrance areas), to low security areas such as reception, all the way to the highest security zones where the most sensitive or high-risk assets or work are located.

Passing from an area of lower security to an area of higher security ought to be obvious to the knowledgeable insider and must require successfully authenticating with an access control system (be it a receptionist/guard, door lock, card reader, biometric scanner, or other device for identifying the individual transitioning the security boundary).
The appropriate rigor and tolerable rate of false positives depend on the security level of the area being protected.

Furthermore, different types of security controls ought to be considered for the higher security zones.
For example, in addition to preventive controls such as door locks, detective controls such as video monitoring and corrective controls such as motion detectors and alarms can be used as compensating controls should the primary preventive control (e.g., the door lock) fail or be compromised.

Multifactor authentication techniques are as valuable for physical access as for logical (e.g., login) access.
Requiring a user to have an access card as well as enter a personal identification number (PIN) to unlock the door to higher security zones protects against loss of the access card and its use by an impostor.
Requiring the card (and not the PIN alone) protects against shoulder-surfing by a threat actor observing staff enter their PINs.

#### Compliance Obligations

Organizations handling government or military classified data will have to institute such security controls as required to meet the obligations of their facility security clearance.
The organization responsible for certifying compliance will provide detailed documentation on the controls that are necessary for the level of security clearance being sought, including requirements for the following:
* Personnel identification
* Guards
* Electronic access control
* Electronic intrusion detection
* Video monitoring
* Interior access controls

One solution for having confidential discussions is the Sensitive Compartmented Information Facility (SCIF). SCIF is a common term among U.S. and British military and governmental agencies with a need for isolated space to preserve confidentiality.
Typically, at least a room, if not a secured, hardened building, the SCIF can be temporary or permanent.
If you watch any movie where the military leaders are briefing the president on an important and sensitive situation, they are in a SCIF.

### Utilities and Heating, Ventilation, and Air Conditioning

Utilities (such as power) and HVAC are equally important to the reliable operation of your data center.
It matters little if you can maintain power to your server racks if your cooling system fails and the room temperature passes 105° F (40° C).
As with all aspects of data center design, you start with a risk assessment and then consider the relevant controls that can be used to reduce the risk to an acceptable level.
You also need to balance building a single particularly resilient data center versus two geographically separated, less resilient data centers.

There are many types of UPS systems that vary in their design and features. Battery UPS systems can differ in a number of important aspects:
* Load: The capacity of the unit to deliver a specified level of continuous power
* Capacity: The time during which the unit can maintain the load
* Filtering: The ability of the unit to isolate the equipment from noise, surges, and other problems with the utility power
* Reliability: Some designs trade low cost for reliability

Nonbattery UPS systems exist that use large-mass rotating flywheels connected to provide short-term backup.
These are appropriate for larger loads (> 200KW) and can provide higher reliability and lower lifetime costs than comparable battery UPS systems.

Typically, a UPS is intended only to carry the load during short outages, and for the short time it takes for a backup generator to start and be able to take the full load.
So, most data centers or server rooms will need a generator to handle the load, should the power interruption last longer than that which the UPS can handle.

Generators are available in a wide range of capacities and use different fuels (gasoline, diesel, natural gas, and hydrogen).
The advantage of natural gas is the elimination of the need to store fuel. The risk is that certain natural disasters can cause both power and gas distribution outages.

Ideally, power is consistently clean without any fluctuations, but in reality, commercial power suffers from a wide assortment of problems.
Here is a list of terms associated with power issues you should know:
* Fault: A momentary loss of power
* Blackout: A complete loss of power
* Sag: Momentary low voltage
* Brownout: Prolonged low voltage
* Spike: Momentary high voltage
* Surge: Prolonged high voltage
* Inrush: An initial surge of power usually associated with connecting to a power source, whether primary or alternate/secondary
* Ground: The wire in an electrical circuit that provides an alternate pathway for electricity to flow to the earth (i.e., the ground)

Cooling systems must be designed so that there are multiple units with sufficient capacity so that the data center not only can be maintained below the maximum safe operating temperature even in the face of the failure (or maintenance) of one or more units, but also the maximum rate of temperature change is kept within permitted limits (for example, less than 5°C/hour if magnetic tapes are being used, 20°C/hour otherwise), even if a unit is taken out of service for maintenance.

Finally, humidity also needs to be managed. Low humidity leads to increased static electricity, and high humidity can lead to condensation. Both conditions will lead to lower equipment reliability.

With both power (UPS and generator) and HVAC systems, due consideration has to be made for the following:
* Regularly scheduled maintenance
* Regular testing under full load (of UPS and generators, and backup HVAC equipment if not used in production)
* System fault detection and alerting (and regular tests of those subsystems)
* Periodic checks and audits to ensure all of the above are being properly and regularly performed

A variety of industry, national, and international standards cover HVAC, utilities, and environmental systems.
* The Uptime Institute’s Data Center design certification tiers assess areas including facility mechanical and electrical systems, as well as environmental and design considerations. Specifications for the tiers can be found at uptimeinstitute.com/resources/.
* The International Data Center Authority (IDC) provides open standards for data centers, facilities, and infrastructure at www.idc-a.org/data-center-standards.
* The ASHRAE standards for ventilation, refrigeration, building automation, and a variety of other related topics can be found at www.ashrae.org/technical-resources/standards-and-guidelines.

### Environmental Issues

Environmental issues that need to be considered include the likelihood of the following:
* Major storms (hurricanes, lightning, blizzards, ice storms, typhoons, tornadoes, blizzards, etc.)
* Earthquakes
* Floods and tsunamis
* Forest fires
* Internal building risks
* Vermin and wildlife
* Volcanoes

### Fire Prevention, Detection, and Suppression

There are a range of fire suppression technologies that can be deployed to protect technology infrastructure, facilities, and people.
The process, as with selecting any set of security controls, is to perform a risk assessment to determine the appropriate mitigation strategy.

As always, human safety is paramount, and any fire safety system must be designed first and foremost to protect the lives and health of those who work in the facility.
Enabling occupants to safely exit the building and ensuring that fire suppression systems are unlikely to compromise health or safety are more important than protecting systems and buildings.

Next, one has to balance the costs of the following:
* Downtime
* Restoration costs
* Fire suppression system costs (capital and ongoing maintenance)

Fire needs three things to start: heat, fuel, and oxygen (more generally, an oxidizing agent).
Fire prevention and suppression involves reducing one or more of these three elements such that fire cannot start or be sustained.
A more complete model adds the chemical reaction between the fuel and the oxidizing agent, creating the fire “tetrahedron.”
This model is useful in that some fire suppression systems block the chemical reaction itself rather than reducing one of the three components necessary for that reaction.

#### The Four Primary Stages of Fire

**Stage 1: The Incipient Stage** At this stage, there is only air ionization and no smoke.
**Stage 2: The Smoke Stage** In Stage 2, smoke is visible from the point of ignition.
**Stage 3: The Flame Stage** This is when a flame can be seen with the naked eye.
**Stage 4: The Heat Stage** At Stage 4, the fire is considerably further down the timescale to the point where there is an intense heat buildup and everything in the area burns.

Most jurisdictions have standards and guidelines for the fire protection systems for IT equipment:
* Canada and the United States: NFPA 75, “Standard for the Fire Protection of Information Technology Equipment,” and NFPA 76, “Fire Protection of Telecommunications Facilities.”
* UK: BS 6266:2011, “Fire protection for electronic equipment installations.” Code of practice.
* Germany: The VdS series of guidelines for fire protection and suppression.

#### Fire Detection Systems

Properly protecting a facility from fire requires installing an automated detection and suppression system. There are many types of fire detection systems.

**Fixed-temperature detection** systems trigger suppression when a specific temperature is reached. This is the most common type of detector and present in most office buildings.
The potentially visible sprinkler head serves as both the detection and release mechanism. The trigger is usually a metal or plastic component that is in the sprinkler head and melts at a specific temperature.

There is also a version with a small glass vial containing chemicals that vaporize to over-pressurize and shatter the container at a specific temperature.
This system is inexpensive and very reliable, even over long periods of time.

**Rate-of-rise detection** systems trigger suppression when the speed at which the temperature changes reaches a specific level.
These are often digital temperature measuring devices, which can be fooled by HVAC heating during winter months and thus are not widely deployed.

**Flame-actuated** systems trigger suppression based on the infrared energy of flames. This mechanism is fast and reliable but often fairly expensive. Thus, it is often only used in high-risk environments.

**Smoke-actuated** systems use photoelectric or radioactive ionization sensors as triggers.
Either method monitors for light or radiation obstruction or reduction across an air gap caused by particles in the air.
It is intended to be triggered by smoke, but dust and steam can sometimes trigger the alarm.
The radioactive ionization-based smoke detectors use americium as a source of alpha particles and a Geiger counter to detect the rate of these particles' transmission across the air gap.
This element produces such low levels of radiation that a layer of dead skin cells is sufficient to block its transmission.

**Incipient smoke detection** systems, also known as aspirating sensors, are able to detect the chemicals typically associated with the very early stages of combustion before a fire is otherwise detectible via other means.
These devices are even more costly than flame-actuated sensors and are also only used in high-risk or critical environments.



#### Wet-Pipe Water Sprinkler Systems

The simplest and most widely used system is the wet-pipe water sprinkler system.
These systems have water in the pipes at all times, and the sprinkler heads each have valves held closed either by a heat-sensitive glass bulb or a metal link, both designed to release the water at a specific temperature.
The advantages of wet-pipe systems include low installation and maintenance costs and relatively high reliability.
These systems also only release water through those sprinkler heads closest to the fire, thus limiting water damage.
The risk from wet-pipe water sprinklers is the damage that occurs due to accidental release from faulty sprinkler heads or physical damage (hitting a sprinkler head with a rack or ladder while working in the facility).

#### Dry-Pipe Water Sprinkler Systems

Dry-pipe systems have, as the name implies, no water in the supply pipes until a sprinkler head is triggered by fire.
These are used in warehouses and parking garages exposed to freezing temperature and are not relevant to data centers or most office buildings.
The advantage is that the pipes do not contain water, which can freeze and damage the pipes.
The disadvantages are increased corrosion and a delay in response time, as the air must be forced out of the sprinkler heads before the water reaches the fire.

#### Deluge Sprinkler Systems

Another specialized sprinkler system not usually deployed in data centers or office buildings is the deluge sprinkler.
This is a variant of the dry-pipe sprinkler but with open sprinkler heads.
Once a fire is detected (using a smoke, heat, or manual alarm), a valve opens to let water into the supply pipes and through all sprinkler heads (without regard to the specific location of the fire).
These systems are appropriate in certain industrial situations in which a large volume of water is required to prevent the spread of the fire.

#### Pre-Action Sprinkler Systems

Pre-action systems are a combination of one of the previous three types of sprinkler systems (wet-pipe, dry-pipe, or deluge) with a more sophisticated triggering mechanism.
A single-interlock pre-action system is a dry-pipe system with pressurized gas in the pipes, in which the activation of a smoke or heat detector causes water to be released into the supply pipes, essentially converting the dry-pipe system to a wet-pipe system.
The water, however, is released only if the sprinkler head is triggered.

This system sharply reduces the chance of an accidental release of water because should a sprinkler head trigger accidentally, the system will detect a drop in air pressure and set off a trouble alarm but not release any water.
A double-interlock pre-action system requires both the activation of a smoke or heat detector and the activation of sprinkler heads before water is released into the supply pipes.
This can be an advantage in refrigerated spaces but delays the release of water in the case of an actual fire event.

#### Limitations of Sprinkler Systems

Proper design of any sprinkler system requires professional advice and continued vigilance to ensure that later developments (such as the addition of suspended cable trays) do not impair the effectiveness of the system.
A limitation of sprinklers is that they do not work well in the confined space of a raised floor or suspended ceiling. These require either water mist or clean agent fire suppression systems.

#### Water Mist Sprinkler Systems

An alternative to standard sprinkler heads that can discharge high quantities of water per minute are water mist sprinklers, which release a much smaller amount of water in the form of microscopic water droplets.
These extinguish the fire both through removing heat (as a standard sprinkler does) as well as by displacing oxygen when the mist is converted to steam.

#### Clean Agent Fire Suppression Systems

In situations in which the impact of water damage would be significant, various “clean agent” extinguishants can be used.
These have the advantage of causing little or no damage to the equipment being protected. The disadvantage is their much higher installation and ongoing maintenance costs.

The original clean agents included carbon dioxide and halon. Carbon dioxide works primarily by displacing oxygen and additionally by removing heat.
Unfortunately, it can cause asphyxiation in concentrations well below that required for fire suppression and so requires pre-discharge alarms to ensure the space about to be flooded with CO<sub>2</sub> is evacuated prior to discharge.
Halon gas works by interfering with the chemical reaction (the fourth part of the “fire tetrahedron”) and has the advantage of being nontoxic at concentrations well above those needed.
This resulted in its widespread use in data centers and other facilities for several decades where sprinklers might cause more damage than a contained fire.

Halon, however, is very damaging. In Canada, the Montreal Protocol in 1994 phased out its use.

Newer clean agents that are ozone-friendly have been developed, each with specific advantages.
These include HFC-227ea, fluorinated ketone, and various gas mixtures (e.g., argon, nitrogen, and carbon dioxide).
These newer clean agents are more environmentally friendly and less toxic than earlier alternatives.

#### Physically Separating Critical Facilities

Just as network segmentation can limit the damage of a security breach in one part of the network, physically separating critical communications facilities in a separate room with a two-hour fire wall (literally) from less critical data processing facilities can also limit the damage by preventing a fire (and the water from the fire suppression system) in one area from affecting equipment in another.

Similarly, backup media that must be stored onsite can be stored in a separate room or in a fireproof storage vault.

#### Fire Extinguishers

Fire extinguishers are mandatory, but staff need to be trained in their purpose and proper use.
While they may serve to put out very small fires caught in their early stages, they are primarily there to enable staff in the server room to reach an exit should fire block their path.

Fires are categorized by the type of fuel:
* Class A: Ordinary solid combustibles (e.g., paper, wood, and plastic)
* Class B: Flammable liquids and gases (e.g., gasoline)
* Class C: Energized electrical equipment
* Class D: Combustible metals (e.g., lithium metal, but not lithium-ion batteries, which are considered Class B, although water will also work well with Li-ion battery fires)
* Class F or K: Cooking oils and greases

Fire extinguishers are rated based on the classes of fires they are designed to combat and the amount of extinguishant they contain.
A fire extinguisher rated 5BC may be used on Class B or C fires. A 10BC extinguisher would have twice the capacity of a 5BC extinguisher.

Use of the incorrect extinguisher not only can make the fire worse (e.g., using water on a gasoline fire can spread the fuel), it can be a grave safety hazard to the person using the extinguisher (e.g., using water on an electrical fire can result in a risk of electrocution).

#### Training

Training does not end with knowledge of how and when to use the fire extinguishers.
All staff who will normally be present in the data center need to be properly trained and rehearsed on how to respond to a fire alarm or fire event.

Make sure they know the following information:
* Where all the exits are (so they know the closest, and if blocked, the alternates)
* Where all the fire extinguishers are located as well as how and when to use them (different types of fire extinguishers are appropriate for different types of fires)
* How to disable (or delay the discharge of) the fire suppression system should a false fire detection be suspected
* How to manually trip the fire suppression system (in the case of gaseous suppression and some sprinkler systems) should early signs of fire be detected by staff before the fire detectors are triggered
* Where the fire alarm pull stations or call points are
* How to manually shut off power to the data center

#### Good Housekeeping

Finally, good housekeeping is an important part of fire suppression. The data center or server room must not be used for storage.
Cardboard boxes of computer parts or wooden reels of Cat 5 cabling must be stored in a separate part of the facility.
Wastepaper receptacles should be outside the facility or, if they must be inside the data center, small and frequently emptied.
The less fuel there is available, the less likely there will be a fire, and if there is a fire, less damage will result.
