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