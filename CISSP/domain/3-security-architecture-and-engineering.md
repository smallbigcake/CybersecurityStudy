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

