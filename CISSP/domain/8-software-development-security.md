# Software Development Security

## UNDERSTAND AND INTEGRATE SECURITY IN THE SOFTWARE DEVELOPMENT LIFE CYCLE (SDLC)

Software is created in response to the needs of a user group that seeks to achieve a particular information handling goal, such as a desire to efficiently search for data contained in various records rather than reading each record one by one.
This creation process, known as development, often follows an iterative lifecycle; as user needs change, so too must the software be updated to meet these new requirements.
The repeated or iterative quality means the process is often referred to as the software development lifecycle (SDLC).

Like all lifecycles, the SDLC is broken down into phases that are logically ordered based on the inputs they require and the outputs they produce.

Some of these are obvious; for example, developers must understand what users need in the requirements phase before they progress to the development phase where software is created to meet those needs.
Others are less obvious, such as the need to perform design phase activities like interface mockups before beginning development.
This gives rise to different methodologies such as Waterfall, which is rigid and mandates completion of all activities in a phase before progressing to the next.
Other methodologies are more flexible, such as prototyping; reviews and input on a finished prototype are used to create a new, improved design.

Regardless of the SDLC methodology in use, security activities must be integrated throughout each phase to effectively implement software security.
A Certified Information Systems Security Professional (CISSP) may not be directly in charge of the software development organization, but providing clear input and guidance on these requirements to developers is crucial.
This means identifying security requirements for the system before development begins and providing adequate resources to support the design, development, and testing of security features or controls implemented to meet those requirements.

It is also important to note that the system lifecycle (SLC) covers additional phases of the information system after its development (SDLC) is completed.
This includes operations and maintenance as well as decommissioning and disposal, during which key security controls such as vulnerability management and media sanitization must be addressed.

### Development Methodologies

An organization’s choice of development methodology will be guided by a number of factors such as the time available, tolerance for errors or bugs in the software, and complexity of the project.
There may also be multiple methodologies in use at the same organization, as different groups will have different requirements. In general, all methodologies contain similar fundamental phases, though they differ in the actual execution of each phase.

#### Software Development Lifecycle Phases

The model of SDLC activities as an isolated process is increasingly expanded by more holistic views of an organization’s engineering processes, such as those defined by ISO/IEC/IEEE 15288, “Systems and software engineering — Systemlife cycle processes.”
The National Institute of Standards and Technology Special Publication (NIST SP) that described security in the SDLC, SP 800-64, “Security Considerations in the System Development Life Cycle,” has been withdrawn and replaced by SP 800-160, “Systems Security Engineering,” which aligns security considerations to the SLC processes identified in ISO 15288.

This is not to say that SDLC models or phases are unimportant; rather, this reflects the need to address security not as a standalone function, but from an organization-wide, holistic perspective.
It also provides more flexibility for an organization to implement processes (including security) in a way that best fits the evolving nature of software development.

For example, testing and verification of security controls in a platform as a service (PaaS) environment may not be part of an individual system development effort, but part of an organization’s larger cloud security efforts.
This is a shared control that all development teams can utilize, and the responsibility for performing the testing rests with a cloud architecture team.

There are many SDLC models available with different names for each phase, though they execute roughly the same steps in logical order. These include the following:

* **Initiation:** The business need and case for a system is expressed, requirements are documented, and resources are allocated.
* **Development:** Activities are conducted to design the system and underlying architecture needed to meet requirements; then the system is created by developing custom code, purchasing or integrating external code, or otherwise constructing the system.
* **Deployment and delivery:** The system is placed into the operating environment and made ready for use, which will include testing to ensure the system is fit for purpose and meets requirements.
* **Operations and maintenance:** Most operations and maintenance activities are outside the scope of development work, but the SDLC can be iterated as user needs evolve, so crucial processes like change management may kick off another round of development activities.
* **Disposal:** Activities in this phase are almost entirely the purview of the SLC, but some development may be required to perform activities such as archiving or transitioning data to a replacement system.

#### Waterfall

The Waterfall methodology is one of the oldest and has fallen out of favor in many organizations due to its inflexibility and difficulty in meeting the complex requirements of modern information systems.
The phases of a typical Waterfall development project include requirements, design, implementation, testing, deployment, and maintenance.

Like a waterfall in nature, this methodology follows a sequential series of phases, which require that all tasks be completed before the project progresses to the next phase.
The Waterfall methodology is not designed to be iterative, which presents difficulties when requirements change.

To progress to the design phase, all requirements must be gathered, documented, and agreed upon; once the project moves on to the design phase, new requirements cannot be incorporated.

##### Benifits

This rigor can be a security benefit, as the Waterfall method enforces strict control processes such as requirements gathering and testing.
If security is properly integrated in the development project, this will result in well-documented and understood security requirements and robust testing of the final system.

However, security benefits are inconsequential if the system is not fit for user needs.

##### Drawbacks

The rigidity of the Waterfall model makes it useful for projects where it is possible to know all requirements up front and where no changes will be required once development has started.
In the era of mainframe computing with limited capabilities and expensive hardware, it made sense. However, the malleable nature of software and virtualized hardware mean a more adaptable approach is possible to allow for fast and flexible software deployment.
Rapidly evolving security requirements, which may necessitate major changes to system functionality, are particularly underserved by this model.

#### Agile

Recognizing that rigid development models like Waterfall do not adapt well to modern software development needs, a new high-level model emerged in early 2001 from a group of developers called the Agile Alliance.
The group comprised members with diverse development backgrounds from methodologies such as Extreme Programming, Scrum, and Feature-Driven Development, many of which contained evolutions designed to address shortcomings of legacy methodologies like Waterfall.

##### Core Philosophy

We are uncovering better ways of developing software by doing it and helping others do it. Through this work we have come to value:

* **Individuals and interactions** over processes and tools
* **Working software** over comprehensive documentation
* **Customer collaboration** over contract negotiation
* **Responding to change** over following a plan

That is, while there is value in the items on the right, we value the items on the left more.

##### 12 Principles

The Agile Alliance documented 12 principles to form the Agile Manifesto, which can be found at agilemanifesto.org/principles.html.
The manifesto principles are designed to better structure development teams and allocate resources with the goal of increasing flexibility of development activities.

For example, two of the principles state the following:

* **Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.**
Rather than striving for a complete set of requirements before a project begins, Agile development can identify the highest priority items and work to deliver them first and then repeatedly iterate to elicit deliver on the remaining requirements.
The focus of development is to meet needs, rather than blindly follow processes.

* **Welcome changing requirements, even late in development. Agile processes harness change for the customer’s competitive advantage.**
By focusing on customer (user) value, Agile development strives to deliver systems that meet user needs.
This obviously supports the security goal of availability, but it also means complex software systems can be better designed to meet changing confidentiality and integrity needs, such as more robust encryption or data validation controls that were not initially identified as requirements.
As needs change over time, such as new security requirements, so too can the software project evolve.

###### Full List of Principles

The 12 principles, as stated in the Agile Manifesto, are as follows:

* Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
* Welcome changing requirements, even late in development. Agile processes harness change for the customer’s competitive advantage.
* Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
* Business people and developers must work together daily throughout the project.
* Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.
* The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.
* Working software is the primary measure of progress.
* Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.
* Continuous attention to technical excellence and good design enhances agility.
* Simplicity — the art of maximizing the amount of work not done — is essential.
* The best architectures, requirements, and designs emerge from self-organizing teams.
* At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

The 12 Agile principles are not themselves a development methodology that can be followed to develop software but are instead guiding ideals for managing software development projects.
When implemented correctly, they strive to achieve value by delivering functional software faster and with increased ability to respond to changes.
Software is released quickly with basic functionality; then the development process iterates to include additional functionality, avoiding large all-at-once releases in favor of smaller, more frequent releases.

Each iteration will also take into account lessons learned from customers (e.g., changed requirements) as well as lessons learned by the development team.

The team should ideally comprise cross-functional members from both development and business backgrounds and should emphasize clear and frequent communication among stakeholders.
This development meta-methodology requires organizations to identify all relevant stakeholders, which must include the security team.
All stakeholders should be involved at a minimum during requirements gathering and testing to ensure the system needs are documented and tests are conducted to verify they are met.

Changes to requirements, including evolving security needs, are well-supported by Agile methodologies, since they are designed to re-assess requirements frequently and incorporate those in the iterative development.

##### Agile Testing Approaches

Agile places a high value on speed and efficient use of resources, which gives rise to the use of integrated testing to support the delivery of functional software.
Unlike the Waterfall methodology where testing is a separate phase conducted after development activities are completed, Agile methodologies integrate testing activities closer to the actual development activities.
The goal is twofold. First, testing is on a smaller, more manageable target, so fixes are generally easier.
Second, the need to be responsive to changing requirements necessitates robust testing to ensure newly delivered functionality does not introduce bugs, flaws, or vulnerabilities.

###### Automation

The use of automated testing tools allows for security tests to be conducted closer to the time of development and against smaller targets.
These support a goal of preventing defects from reaching production environments, as well as making test results easier to manage due to their smaller size.

Maintaining the speed of software delivery under Agile methodologies leads to a strong focus on automation.
This is particularly true for repeated processes such as functional testing, which benefits from increased reliability since automated processes are less subject to human error.
Security testing benefits from automation as well, as critical controls like software code reviews and vulnerability scanning can be conducted automatically and more frequently.
Automated testing is an essential enabler of continuous integration/continuous delivery (CI/CD), which is discussed later in this chapter.

##### Agile Development Methodologies

As mentioned, Agile is a high-level set of principles and is implemented to some degree across a variety of development methodologies.
Three examples of development methodologies implementing Agile principles include Extreme Programming, Test-Driven Development, and Scrum.

* **Extreme Programming:**
Sometimes written as XP, this methodology introduces the use of integrated teams including developers, customers, and managers to drive the delivery of high-value software features.
User stories are documented to capture what users are trying to achieve as well as the acceptance criteria of software that implements those features, and the stories are prioritized based on value.

  For example, in a system with 500 users who need to log in and save data to a database but 10 users who need to print records from the database, the ability to log in and save data will be prioritized. Full details of XP methods and implementation are at www.extremeprogramming.org.

  * XP utilizes a concept known as pair programming, which pairs developers. The developers take turns writing code and offering advice/input, with the goal of achieving higher quality code by providing extra oversight and knowledge to draw upon.
  * Refactoring code can mean many things, but it is essentially a way of removing obsolete, redundant, or unneeded code to improve software’s functionality. Developers may have made decisions in the past that were sound but are no longer relevant as the system and requirements evolved.
  Refactoring can be used to ensure systems do not contain unnecessary junk code or functions known as cruft.

* **Test-Driven Development (TDD):**
In education, there is an idea known as “teaching to the test”; classroom instruction is geared to ensure students are able to successfully pass an exam like a driver training course designed to prepare students for a driving test.
TDD, as the name implies, is driven by the use of test cases: first a test is written, then it is run. If it fails, code is written or refactored as needed to make the test succeed; the ultimate goal is to ensure that all tests pass.
Having the end goal in mind can be useful for developers to better understand the desired functionality they are trying to build.
TDD is especially effective for existing systems where modifications or updates must be implemented with a minimum of complexity, such as implementing code-level security controls like fixing a buffer overflow or injection vulnerability.

* **Scrum:**
The foundation of a Scrum project is a lightweight set of team members continuously iterating development work to achieve the overall product goal. Scrum has introduced many words that are associated with Agile development projects, such as sprints and backlogs.
It focuses on a cross-functional team comprising three key members, a timeframe known as a sprint around which key activities are performed, and several important artifacts.

  Scrum roles and artifacts include the following:

  * **Scrum master:**
  The Scrum master is in some ways akin to a facilitator, whose role is to remove impediments to the team’s success. These include tasks such as coaching team members on self-organizing work, gathering input from key stakeholders, and facilitating team events.

  * **Product owner:**
  As the voice of the customer, the product owner is responsible for ensuring developers understand the goals their software is being designed to meet.
  The product owner also owns the product backlog, where all work to be done is broken down into work units and prioritized, such as new features and bug fixes.

  * **Development team:**
  This is a broad team that includes traditional developers who write code, architects who design system infrastructure, data scientists or analysts, and, crucially to security, testers and Quality Assurance (QA) staff.
  Security testing should be done for all development work, so many code- and application-level security controls will be delegated to members of the development team.

  * **Backlogs:**
  One key artifact maintained in Scrum is the backlog. The overall product backlog contains all requirements the product owner has identified, along with prioritization based on value to the customer.
  Requirements may include a measure of effort or complexity to build, and a cross-functional effort is often needed to determine these numbers.

    The sprint backlog is a smaller list of requirements drawn from the product backlog that, in the team’s estimation, can be delivered in the time allotted.
  Higher priority items are obviously delivered sooner, though low-complexity/effort/priority items might be added if there are free resources in a sprint, but not enough to address a higher priority or more complex item.

* **Key Scrum** activities and key inputs from the artifacts are described in the following points.

  * **Sprint:**
  A sprint is simply a time-boxed set of work to be done on the project; for example, all development work to be completed in two weeks is considered a sprint.
  While Scrum, as an Agile methodology, embraces change, changes are avoided if at all possible once work is committed to a sprint. Changed requirements can be addressed in a future sprint.

  * **Sprint planning:**
  Prior to beginning a development sprint, the team meets to perform sprint planning. Based on priorities set by the product owner, certain backlog requirements will be selected for the sprint, and the team agrees upon the work they feel can be achieved in the given time period.
  Once this plan is set, changes are to be avoided, so this scoping and planning is a critical activity.

  * **Daily Scrum:**
  The development team should meet daily to discuss progress, blocking issues, and the plan for the day’s activities. According to the Agile Manifesto, these meetings are best conducted face to face and are often known as standup meetings.

  * **Sprint review and retrospective:**
  Two key events happen at the end of a sprint. The sprint review identifies work completed and includes a demo to the customer, supporting the goal of integrating users and developers.
  A sprint retrospective is an opportunity for the development team to perform continuous improvement by reflecting on successes, failures, and opportunities based on the recent sprint.

#### DevOps

DevOps is an integration of the traditionally disparate functional areas of development and operations, with the goal of better supporting the organization’s information system resources.
Developers and operational personnel traditionally worked in silos, and inefficient handoff procedures between the two meant critical information was lost when systems moved from development into production.

DevOps teams implement practices advocated in Agile, such as combined cross-functional teams with an emphasis on frequent communication to overcome these challenges.

DevOps practices include the use of automation, frequent testing, and an emphasis on frequent software integration and deployment. Software delivery is sped up by following an assembly line approach, known as a pipeline, with a focus on building quality in.
Developers are given a manageable unit of work to complete within a specific period of time (the requirements included in a sprint), and automated testing aims to identify and remediate flaws before the code is delivered to production.

##### QA

QA is the third member of the DevOps team in addition to development and operations and is responsible for implementing many aspects of the cross-functional communication.
Members of a QA team will typically participate in up-front activities related to testing, such as defining criteria for success, and then provide crucial feedback to developers when a test fails.
These testing activities are included in the scope of work for a sprint, so the development team must ensure adequate time and resources are allocated to develop, test, and remediate any issues in the code being delivered during that sprint.

This QA focus can be a crucial point of enforcing security in the SDLC, if security requirements have been properly documented and QA is required to verify the system meets those requirements.
Automated security testing and faster delivery reduce the number of vulnerabilities introduced when new software is deployed, and provide the benefit of quicker patch creation and deployment when a vulnerability is discovered in a system.

##### Security in DevOps

While there are benefits to speedier software delivery, developing and deploying secure software should not be sacrificed in favor of simply adding new functionality more quickly.
There is a crucial governance task to consider for organizations using DevOps: the privileged role and permissions held by the DevOps team.
Lengthy processes like change management reviews may frustrate the goal of fast software delivery, but they do provide useful checkpoints for security activities such as vulnerability scans and manual reviews.
These must be replaced by automated tests where necessary, and defined procedures should also exist for software changes that cannot be fully tested via automated tools.

Members of the DevOps team are likely to have privileged access, such as being able to make changes in production environments, create new users and permissions, and access log data.
Like all privileged access, additional monitoring is likely justified, as are controls like multifactor authentication (MFA) and additional training for these staff members.

While cross-functional teams are useful, principles of least privilege and separation of duties must still be implemented.
Members of DevOps require permissions specific only to their primary role, rather than having access to all abilities granted to the DevOps team; for example, developers may be able to mark their code complete and ready for deployment, but another user is required to verify that all required testing has been performed before the code is deployed.

Here again, automation plays a crucial role, such as the use of an automated code deployment tool that systematically validates that all testing and other requirements have been met before pushing code to production.

#### DevSecOps

Although QA can perform critical security-related functions in DevOps if security is properly implemented in the SDLC, you will notice that security is not specifically addressed.
The Agile transition of legacy software development has been mirrored in the security community as well with the creation of DevSecOps, right down to a manifesto and guiding principles documented at www.devsecops.org.

The goal of DevSecOps is to favor iteration over perfection, where a workable security solution delivered today and improved tomorrow is preferred over a perfect solution delivered years from now — by which time the system may have suffered attacks or exploits!

The DevSecOps principles provide guidance for better integrating security and compliance activities and data into development processes.
These principles demonstrate a focus on better communicating security in addition to the traditional DevOps and include data and security science over fear, uncertainty, and doubt, as well as red and blue teams exploiting testing over relying on scans and theoretical vulnerabilities, both of which help security practitioners deliver actionable knowledge.
Rather than saying a theoretical vulnerability may lead to the complete loss of an organization’s data, a DevSecOps practitioner, such as a CISSP, performs red team testing to determine the exact nature of a vulnerability.
This, combined with real-world risk data, gives the organization’s leaders and developers a justified and actionable path to mitigate risk.

The ultimate goal of DevSecOps, as the name suggests, is to ensure security is built into the process an organization uses to develop and operate its information systems.
Traditional information security practices are often an add-on to the SDLC, and they suffer from the same challenges identified in legacy development methodologies.

This evolution is also reflected in the evolution of standards documents, such as the migration in NIST documentation from SDLC security to security engineering processes, though it is helpful to note that there is not standard approach to implementing DevSecOps.
Much like security risk mitigation controls, each organization may create or adapt processes to fit their unique environments.

#### Other Methodologies

There are other software development methodologies in addition to the Waterfall and the family of Agile methodologies previously discussed.
While a CISSP is not expected to be familiar with all possible methodologies, it is a good idea to have a basic familiarity with popular methodologies and their associated security benefits and drawbacks.

##### Modified Waterfall

For projects that need a small increase in flexibility over the traditional Waterfall, the modified Waterfall may be appropriate.
This methodology provides two minor options to address projects that are not served by the rigorous approach demanded by the traditional Waterfall method.
First, it may be possible to proceed to the next phase before all current phase activities are finished; for example, testing may begin on completed code while some code is still under development.
Second, it is possible to step back a phase and iterate work if necessary.
If the developers realize that architectural assumptions made during design are off in some way, the project can step back one phase, update the system design to address the deficiencies, then progress to implementation once again.

##### Spiral

Another evolution of the traditional Waterfall approach is the Spiral methodology. The Spiral methodology is iterative; that is, it is designed to be executed in a repetitive series, and it places a heavy focus on risk assessment, analysis, and evaluation.
Large, complex, and costly projects are a common use for this model, as it emphasizes risk control over time via repeated evaluation of project risks, costs, and benefits.

The process iterates through four phases:

1. Determine objectives, alternatives, and risks
2. Evaluate alternatives and resolve risks
3. Development and testing
4. Plan next phase

Other SDLC methodologies may be used within each phase to perform activities such as gathering requirements or scheduling and performing development, and the iterative nature means changing or evolving requirements can be easily addressed.
This model is expensive and introduces a great deal of overhead in the form of the repeated risk assessments at each phase; this overhead may be justified for projects where requirements are difficult to determine or long-term projects with requirements that are likely to change.

##### Prototype

Some development methodologies were designed with iteration in mind and assume the project will be repeated. The Prototype model is one example, where a simplified version of a system or app is built and released for feedback and review.
A subsequent round of development is done based on the feedback and then released for additional review, and so on, until the stakeholder’s needs have been met.

This methodology is useful for new categories or types of systems where clear needs may be impossible to elicit or when novel approaches will be tried.

##### Cleanroom

Unlike iterative models, the Cleanroom methodology assumes that flaws cannot be fixed once development is complete. It focuses exclusively on defect prevention.
The concept follows models used for delicate tasks like chip fabrication where the introduction of a flaw can render hardware completely unusable; this low-risk tolerance demands expensive preventative controls such as garments designed to trap hair or dust, as well as special air handling systems.

In software development, similar controls can be deployed at the expense of development agility. The ultimate goal is to produce software that meets a defined level of reliability, sometimes known as zero-defect, with a focus on robust design and implementation rather than testing and remediation.
The Cleanroom methodology is usually implemented with another development model such as Waterfall and demands a focus on gathering statistical data regarding flaws and control measures.
These metrics are used to justify decisions like the release of software meeting the defined level of reliable, nondefective functionality.

### Maturity Models

Maturity models provide a way of measuring an organization’s progress on continuous improvement in a discipline, such as security management or software development.
Much the same way music is graded based on the musician’s level of practice, maturity model levels detail the skills and abilities that are expected in an organization performing certain tasks with a goal of improvement.

Business maturity models are often known as _capability maturity models_ and are usually specific to a particular organizational discipline like software development.

These models provide a baseline to measure the organization’s current state of ability, define a desired goal state, and provide systemic recommendations for improving the capability.
This is known as process improvement, and in general, an organization is more mature when its processes are more formal, repeatable, and well-managed rather than chaotic.

Although discussed in the context of software development, process improvement and maturity models can be applied to organizations that acquire their key IT functions as services, as well as other disciplines such as managing the improvement of security capabilities.

#### Common Maturity Model Components

Maturity models are usually structured with similar concepts, with the key difference being the process areas the model is designed for, such as software development or systems integration.
Components that are similar across maturity models include the following:

* **Domains:**
The domains are the processes or business aspects that the model is designed to help measure and are usually common activities such as measurement and analysis.
The domains include descriptions of practices related to that domain, such as defining the source and frequency of metrics gathering.

* **Levels:**
Maturity models organize sets of practices in each domain into a series of increasing levels, typically ranging from 1 to 5.
Levels are arranged in a scale showing the organization’s increasing capabilities and may describe individual process areas or the overall collection of processes described by the maturity model.
Each level also includes audit or evaluation criteria, which are used by the organization or an outside auditor to determine the organization’s current maturity level.

* **Criteria:**
To achieve a specific level of maturity, an organization must meet the criteria for that level. In some models, specific domains are associated with each level, such as basic process definition being a low-level criteria while metrics-driven process analysis is a higher-lever criteria.

  Logically, an organization cannot measure an ad hoc or undefined process, so that practice is not introduced until the organization matures fundamental practices.
In other models, each domain has a series of increasing requirements within each domain that correspond to increasing domain maturity, such as ad hoc documentation at lower maturity or template-driven documentation at higher maturity.

* **Targets:**
A target describes the organization’s desired maturity level. Just as security controls entail a cost-benefit analysis of risk reduction, so too must the choice to improve processes lead to a defined organizational benefit.
While increased process maturity reduces the risk of failed or mismanaged projects, it also introduces cost and complexity; different organizations will choose different levels of desired maturity.
The target can be used to perform a gap analysis and prioritize activities needed to close identified gaps.

  In some cases, like contracting organizations, a specific maturity level may be a requirement of doing business with certain entities like government agencies, while in other cases, demonstrating maturity to customers or business partners offers a competitive advantage.

The choice of a maturity model, specific domains or practice areas, and a target will be primarily guided by the organization’s objectives.
Some models are well-adopted in specific industries or are most applicable to organizations engaged in specific undertakings like software development.
In other cases, maturity models have been established around common security practices like secure data handling and are quickly being adopted as a requirement for service providers handling data on behalf of clients and customers.

#### Capability Maturity Model

One of the earliest maturity models to be widely adopted, the Capability Maturity Model (CMM), was developed jointly by the U.S. Department of Defense and the Software Engineering Institute (SEI) at Carnegie Mellon University.
It arose from the need to measure and improve the burgeoning field of software development in the 1980s, as increasing processing power and decreasing costs led to widespread adoption of computer systems.

Development projects were often poorly estimated, controlled, and managed due to computer science being a nascent field at the time, so SEI formalized a set of best practices common across successful projects.
The initial purpose of the model was to evaluate the capabilities of government contractors to deliver projects on time and on budget, but other development and business processes began to adopt the maturity model mindset.

#### Capability Maturity Model Integration

Recognizing that the CMM was being adapted to new business processes, the SEI designed the Capability Maturity Model Integration (CMMI).
It was originally designed with specialized applications in development (CMMI-DEV), services (CMMI-SVC), and product and service acquisition (CMMI-ACQ), and the most recent version 2.0 of the framework was released in 2018.
The model is now under the control of the CMMI Institute run by ISACA (cmmiinstitute.com/cmmi) and has been adapted to address Agile development as well as new areas of business concern including development, services, supplier management, and people (workforce management and professional development), as well as an emerging Cybermaturity program designed to apply maturity model concepts to governance and reporting of cybersecurity.

CMMI models are broken down into domains called process areas and five levels of maturity. Some process areas include increasing requirements at higher maturity, while others apply only at or above certain levels.
The levels are as follows:

1. Initial: Processes are unpredictable and largely reactive. This is typical of an organization largely performing only ad hoc processes.
2. Managed: Processes are characterized or documented for projects and are often reactive. Certain projects may be well-managed and repeatable, but that success is not leveraged across the entire organization.
3. Defined: Processes are characterized for the organization and are proactive. An organization at level 3 has documented processes shared across various projects/efforts and takes proactive steps to ensure projects are successful, such as project risk management.
4. Quantitatively managed: Processes are measured and controlled by the measurements. This is an organization collecting and responding to metrics.
5. Optimizing: The organization focuses on process improvement. An organization at level 5 has documented processes, proactively controls them using lessons learned, and has a robust oversight function to gather metrics and manage activities.


#### Software Assurance Maturity Model

The Software Assurance Maturity Model (SAMM) is maintained by the Open Web Application Security Project (OWASP), located at owaspsamm.org. SAMM is a prescriptive framework for implementing a software security program and focuses on integrating security activities into an existing SDLC.
It provides an action plan for assessing the current state, identifying a target state, and implementing necessary improvements across the SDLC including updates to processes, people, knowledge, and tools.
As with other models, there are domains, subdivided into security practices, as shown in Figure 8.3.

| Domain             | Practices                                                                      |
|--------------------|--------------------------------------------------------------------------------|
| **Governance**     | Strategy and Metrics <br> Policy and Compliance <br> Education and Guidance    |
| **Design**         | Threat Assessment <br> Security Requirements <br> Security Architecture        |
| **Implementation** | Secure Build <br> Secure Deployment <br> Defect Management                     |
| **Verification**   | Architecture Assessment <br> Requirements-Driven Testing <br> Security Testing |
| **Operations**     | Incident Management <br> Environment Management <br> Operational Management    |

Within each set of practices, there are streams of activity, which often represent different responsibilities.
In Security Testing Stream A, for example, automated security testing tools, which can be managed by a QA function, are required, while in Stream B, manual security testing of high-risk components is required.
This testing is a specialized function that requires application security or penetration testing experience. Each security practice is also represented in three levels of maturity.

For example, the Security Testing maturity levels are as follows:

1. Perform security testing (both manual and tool based) to discover security defects.
2. Make security testing during development more complete and efficient through automation complemented with regular manual security penetration tests.
3. Embed security testing as part of the development and deployment processes.

#### Building Security-In Maturity Model

The Building Security-In Maturity Model (BSIMM), as its name implies, is a maturity model focused on determining the current state of secure software creation capabilities, identifying improvement opportunities, and prioritizing efforts to improve secure software development.
More information and the BSIMM documentation can be found at www.bsimm.com.

It is an attempt to bring rigor to the practice of software security by determining which practices are actually effective, as determined through interviews with practicing software security professionals.
These software security initiatives (SSIs) are ordered based on their observed frequency in the interviews.
SSIs that are observed more frequently are considered to be widely adopted practices, while less-frequently observed practices may be either new concepts or performed only by organizations with a very high maturity.

Successful implementation of BSIMM relies upon an internal function dedicated to software security known as the software security group (SSG).
The BSIMM sets out 121 activities across four domains of practice: _Governance_, _Intelligence_, _Software Security Development Lifecycle (SSDL)_, and _Deployment_.
The SSG is responsible or accountable for implementing and maturing the organization’s chosen SSIs.

As with all maturity models, not every organization must be at the same level, but BSIMM is a useful source of empirically based guidance for organizations to measure and improve the software security.

#### Cybersecurity Maturity Model Certification (CMMC)

A recently developed maturity model important to the field of cybersecurity is the Cybersecurity Maturity Model Certification (CMMC), which is published by the U.S. Department of Defense.
Although broadly related to cybersecurity including but not limited to software development security, CMMC is designed for contractors who are handling sensitive information, known as _controlled unclassified information (CUI)_, on behalf of government clients.

It is freely available and contains broadly applicable guidance on assessing and maturing cybersecurity and information security capabilities.
CMMC can be implemented and assessed at an organizational level or on specific projects or units as appropriate. The model and supporting documentation can be found at www.acq.osd.mil/cmmc/draft.html.

The maturity levels in CMMC are similar to CMMI, ranging from level 1, Performed (the activities associated with basic cyber hygiene are in place and functioning at the organization), up to level 5, Optimizing (an advanced, continuously optimized, and proactive cybersecurity program is in place).

These maturity levels assess the organization’s implementation of processes, capabilities, and practices, and are organized into domains that will look familiar to practitioners experienced in the NIST SP 800-53 control families:

* Access Control (AC)
* Asset Management (AM)
* Audit and Accountability (AU)
* Awareness and Training (AT)
* Configuration Management (CM)
* Identification and Authentication (IA)
* Incident Response (IR)
* Maintenance (MA)
* Media Protection (MP)
* Personnel Security (PS)
* Physical Protection (PE)
* Recover (RE)
* Risk Management (RM)
* Security Assessment (CA)
* Situational Awareness (SA)
* Systems and Communication Protection (SC)
* System and Information Integrity (SI)

#### Maturity Model Summary

Maturity models are useful in determining the level of competency and effectiveness that an organization’s practices have achieved, as well charting a course to improvement.
They are useful for complex activities such as software development and security where consistent, repeatable practices are desired, and where incremental improvements can be measured to justify the costs associated with management, operational, or security overhead.

Each of the models discussed comes with some form of assessment, whether informal internal assessment guides like BSIMM or formal external guides like CMMC, which requires an independent third-party assessment and certification.
While useful for measurement, maturity models are not a guarantee of success in any particular endeavor, as they do not address all possible risks a software development project might face.

### Operation and Maintenance

Operation and maintenance, often written O&M, is the phase when systems are in live use and running in what is known as a production environment, meaning they are actively being used by end users.
Testing, verification, and validation activities mark the end of development, and the transition to O&M is often known as promotion or deployment.
To keep software both running and secure, there are a number of critical tasks that must be performed during this phase.

Not all tasks during O&M are the responsibility of a security practitioner since system operations is usually outside the purview of the security team.
Some, like ongoing security testing or vulnerability assessments, are directly assigned to the security team; all operations and security tasks do support the goals of system security and particularly the goal of availability.

These concerns include the following:

* **Continuity:**
Resilience of systems in the face of adverse conditions, as well as the ability to recover when an interruption does occur, are critical. Activities for business continuity, disaster recovery, and cyber resilience all occur during the O&M phase, such as generating system backups.

* **Monitoring and incident response:**
Live production systems are where a majority of security incidents occur, so a significant portion of the organization’s monitoring capability will be focused on this environment.
When an incident is detected, the process of investigation and recovery typically focuses on remediating the issue and restoring production to normal. Processes such as help-desk response and digital forensics will be critical to ensure security incidents are investigated properly.

* **Vulnerability and patch management:**
Scanning systems for flaws and remediating them is a significant, ongoing security task. Some flaws may cause an iteration of the SDLC, especially for custom software, though routine patch deployment for third-party software is the bulk of this work.

* **Access control:**
While controlling access to development and test environments is important, most systems typically have far more users than developers, and sensitive data is not usually used in testing or development.
Procedures to provision, review, and deprovision access will primarily focus on operational systems.

* **Change and configuration management:**
System-level change and configuration management is discussed in Chapter 7, “Security Operations,” while the specifics of manging changes to source code are discussed separately in this chapter.
It is worth noting that operational systems are likely to be placed under configuration management with defined processes for requesting, reviewing, and implementing changes to maintain a secure baseline.

During a system’s life, a variety of maintenance tasks will also be performed to keep it operational and preserve security.
These include identifying upgrades or updates necessary to keep the system running, such as end-of-life operating systems that require system upgrades or replacement of failing hardware.

Maintenance can have a negative impact on system availability, and proactive scheduling is essential to preserve uptime.
Maintenance windows are announced well in advance, and users are notified that the system will be unavailable; unannounced emergency maintenance typically requires an urgent situation as justification.

Testing must be included in maintenance tasks, particularly regression testing designed to identify unintended consequences or loss of existing functionality due to a system change.

### Change Management

One key aspect of managing security for many systems is to maintain them in a known, secure state, which is the function of configuration management.
However, change is necessary, and so processes by which changes can be requested, reviewed, implemented, and tested are also necessary, which is the goal of change management.
These structured processes enable flexibility for systems to adapt to changing requirements or circumstances, while also sufficiently addressing security concerns to prevent changes that adversely affecting the security posture of the system.

It is important to remember that change management is typically not under the purview of the security department, but security practitioners do need to actively participate in the process.
Changes must be reviewed for potential security impacts, testing plans must be documented to ensure security is not adversely affected, and security processes may be triggered in the event a change goes poorly.
For example, a failed change could invoke business continuity processes until the change can be reversed.

Change management processes may be implemented on a number of different levels, with corresponding levels of rigor and sets of processes.

At the organization level, changes such as operating system (OS) replacements would require significant budget and resource planning.

At a source-code level, developers may follow secure coding standards like commenting code and performing peer reviews before code is checked into a repository, which acts as the configuration and change management system for the organization’s source code.
The code is maintained in a known good state, and approved methods of changing it such as pull requests and commits must follow rules to ensure the integrity of the source code is not lost by unapproved developer changes.

At some point, code may also reach a state of completion after which no changes are permitted, in a process known as a freeze.
This is useful for performing testing, verification, and validation exercises, as testing code that is undergoing changes may result in false positives or nonsensical findings.

#### Change Management Phases and Security Practices

Most organizations implement a formal change management body, and common names include some variation on change “something” board, like change management, change control, or change advisory (CMB, CCB, or CAB).
The composition of a CMB typically includes permanent essential members from IT and security teams, as well as ad hoc members like finance or HR for changes with impacts on or input required from those departments.
For example, a major OS shift will require significant investments, so finance and accounting will be involved, while HR will be able to contribute details regarding training and productivity impacts of the change.

The CMB is responsible for shepherding the change management process, which, much like the name of the group, will be unique across different organizations.
A high-level change management process is outlined here, along with corresponding security practices recommended at each phase:

* **Request:**
Many change processes involve the submission of a ticket or other formal request for a change; the advantage of a ticketing system is the ability to capture all details related to the change in a single location.
The request must capture full details of the change as well as anticipated resource requirements and impacts.

* **Analysis and approval:**
Once documented, the change is reviewed by the CMB to identify all anticipated requirements and impacts of the change.
This follows a set of documented criteria, which should include reviewing any security impacts like introducing new risks or adverse effects on existing security controls.
As an example, a change to transition all users from on-premises to remote access will have repercussions on virtually all the security controls an organization has implemented.
Understanding these impacts and ensuring adequate resources are available to address them are crucial before the CMB can approve the change.

* **Change development:**
Once a change is approved, the responsible parties must develop a plan to actually execute the change, such as scheduling time to perform needed IT tasks, gathering necessary resources, and purchasing or developing the changed system components.
These actions must follow the documented and approved change request.

* **Implementation:**
With a plan developed, the change can be implemented. As with the development phase, all approved change procedures must be followed.
In the event a change is not successful, back-out or rollback procedures are required, and the creation of such plans and procedures is typically a requirement for change approval.

* **Testing:**
The newly changed system must be tested to ensure the changes are working as expected, existing functions were not broken, and the security controls are still operating as intended.
Depending on the organization and the magnitude of the change, this testing may include highly formal activities like certification and accreditation.

* **Postmortem:**
There are a number of post-change activities typically required. Documentation of the changes performed must be completed, as the changed system is the new known state, which will be maintained by configuration management.
Newly implemented features may require user training, and any lessons learned should be documented for continuous process improvement.

  This phase may also be called an _after-action_ report, _lessons learned_, or _retrospective_, but the goal of identifying improvement opportunities is the same.

#### Emergency Change Management

Delay is an implicit part of change management processes, mainly because time is required to gather information and resources needed.
There will be situations when this delay is unacceptable, such as a change needed to address a major outage or newly discovered critical vulnerability.
In these cases, the risk of waiting for a change to be documented and reviewed at a weekly CMB meeting outweighs the risk of taking immediate action, so an emergency change management process is required.

Details of standard processes and specific emergency change processes are discussed in Chapter 7, “Security Operations.”

##### Special Approval

Emergency changes, unlike normal changes, are implemented either without approval or with very limited approval.
Rather than requiring review by the entire CMB, a single member may grant approval, or IT personnel may be authorized to implement the change without any prior approval.

Testing and verification processes are similarly streamlined. A patch to close a critical system vulnerability may be deployed to a single system and limited or ad hoc testing conducted before it is rolled out to all systems.
In this case, the risk of operational downtime due to a flawed patch is acceptable compared to the risk of the vulnerability being exploited.

##### After-the-Fact Documentation

Emergency changes do not imply a total lack of process or procedures, but rather a modification designed for speed.
Documentation is still required, and many organizations perform retroactive change review and approval after the change has been deployed to ensure any unintended consequences or unforeseen impacts are understood, documented, and appropriately handled.
After-the-fact documentation is required to support this review, and testing should include regression tests or security assessments like vulnerability scanning and pen testing, depending on the change.
When addressing a critical vulnerability, the priority is obviously to mitigate the risk as soon as possible rather than write complete documentation, but the documentation is still expected once the vulnerability has been addressed.

### Integrated Product Team

Integrated product teams (IPTs) are collections of multidisciplinary individuals with a collective responsibility for delivering a product or process, similar to the combinations seen in DevOps, DevSecOps, and Agile software development.
The guiding concept is that groups with diverse viewpoints — including users, customers, developers, and contractors, who are all stakeholders in the final product or process — can achieve success and enhance speed of delivery for complex projects such as software development.

The goal of IPT is to either assemble or make readily available all resources with a role, skills, or knowledge relevant to a project, and by assembling these resources, traditional delays or impediments can be removed.
This includes security practitioners who understand the security and compliance requirements that a system needs to meet and who should be included as early as possible in the development or acquisition of a system.
IPT is a concept that originated in the U.S. Department of Defense to integrate key stakeholders in complex projects.

The goal of integrated product and process development (IPPD) is to combine both product and process design to ensure a product, often an information system, has a holistic set of requirements used to design both systems and business processes.
This holistic set of requirements should include security needs such as data encryption and access control, and a CISSP may be a key member of the IPT tasked with system development using IPPD practices.

IPPD relies on extensive modeling and testing of both system and process prototypes and on the use of IPTs.
These teams combine stakeholders from the user community and developers with the goal of deepening the understanding of what users need from the system and any technical constraints that need to be overcome.
This prevents decisions from being made with incomplete information and provides timelier feedback, with the goal of meeting cost and performance objectives for systems while reducing wasteful development efforts.

These concepts are related to DevOps and Agile development methodologies, both of which foster closer collaboration between stakeholder groups to enable quicker development and closer integration between teams.


## IDENTIFY AND APPLY SECURITY CONTROLS IN SOFTWARE DEVELOPMENT ECOSYSTEMS

### Programming Languages

Since code is the foundation of software and information systems, it is also a primary focus of security efforts.
These efforts include ensuring code does not violate the integrity of systems by adding unwanted functions and testing systems to identify unintended flaws that could negatively impact the confidentiality or integrity of data, or the availability of the overall system.

To perform these functions, it is important to understand several basic concepts.

Programming languages represent a set of instructions used to build programs that are executed by a computer, typically with a goal of processing information.
These languages consist of instructions and a particular way of writing these instructions (known as syntax), as well as methods to manipulate data. These are combined to create algorithms, or specific sets of instructions, to achieve a data processing goal.
Just as we use sentences, paragraphs, and punctuation to convey meaning in human languages, programming languages also have logical structures designed to allow computers to understand them, execute the instructions, and control the flow of data.

#### Language Types

There are two types of software language, and their main difference is the sequence of steps required to turn human-readable instructions like print('Hello, world!') into instructions a particular hardware system can execute.

##### Compiled Languages

Compiled languages are translated into machine-readable form before being run in a process known as compiling.
The developer uses a program called a complier to perform this task, which takes the written program as input and produces machine-executable code, often called a binary, as an output.

Compiled programs can be run only by the system type for which they were compiled and are often optimized for that specific system type; for example, a program compiled to run on the Windows OS will not function if you try to run it on macOS or Linux.

The optimization means the program can take advantage of specific system features at the cost of portability.
In addition, compiled programs do not expose their source code to the end user, so if code is a valuable intellectual property asset, a compiled language is the best way to distribute it while preserving confidentiality.

C# and Swift are examples of compiled languages.

##### Interpreted Languages

Interpreted languages are translated into machine-readable format when they are run, also known as on the fly.
This makes interpreted code more portable across system types, as users on various platforms can install an interpreter specific to their system so the developer does not need to compile system-specific versions.

There are downsides to interpreted languages, and security can be particularly troublesome. Code is distributed as written or in an intermediate form, which is in human-readable form, so interpreted languages may expose sensitive intellectual property.
Due to the interpretation process, there is additional operational overhead that makes interpreted programs slower than a compiled program, though the speed of modern computing systems makes this a negligible concern in many cases.

JavaScript and Python are examples of interpreted languages. Security concerns with mobile code include its dynamic nature — since it is loaded at runtime, there is the possibility an attacker could modify the code that is requested when a user runs the application.
This means previously tested code may not be loaded, but instead an attacker’s malicious code is loaded and executed.

##### Structured Query Language

Database systems also have languages used to define their data structures, interact with stored data, and manage the database itself.
Structured query language (SQL) is one example, which includes sublanguages for interacting with a database management system (DBMS).
This includes the _data definition language (DDL)_ for creating databases and tables, as well as _data manipulation language (DML)_ for performing actions such as querying or inserting new records.
The _data control language (DCL)_ is primarily concerned with access control for data stored in the database, which makes it critical for implementing security.

##### Security Testing

Security testing is also impacted by the choice of language type. A compiled program installed on a particular computing system can be thoroughly tested, but many interpreted programs are delivered remotely in the form of mobile code in web applications.
Integrity of program code may be a concern for some organizations, as interpreted program code is loaded anew each time the user requests a webpage.
Variations among interpreters may also introduce security issues that are difficult to test for, as the number of testing targets is increased, and resources may not be available to perform thorough testing across all possible system and interpreter combinations.

#### Type Checking and Type Safe Languages

One important aspect of programming that often impacts security is the data a program is handling. In programming languages, data is usually categorized into different types like strings of text, numeric integers, or Boolean values like true/false.
Data types have associated memory structures in code, which are often used as placeholders to represent data that does not exist when a program is created — variables that the program accepts as input.

If a user enters data that does not conform to the expected structure (e.g., a user types their name into a field designed to hold numeric information about their birthday), the program is likely to encounter an error.

##### Static Type Checking
Static type checking is performed by a compiler to verify if the program’s functionality matches type constraints for data inputs. For example, the expression price + tax can be successfully evaluated if both input variables are integer types storing values that represent currency.
However, if the program has declared an integer and a text value of “yes” or “no” to define if sales tax applies to the item, attempting to add those two pieces of data isn’t possible. Type checking can identify such programming flaws.

##### Dynamic Type Checking

Dynamic type checking checks the values stored in a program’s variables as it is running to ensure data matches the expected type.

Languages that implement these features are known as _type-safe_, and they support important security goals related to integrity of data.

Strongly typed languages require all variable type declarations to be checked at compile time, while a loosely or weakly typed language allows for dynamic type checking when an application is run.
The use of a strong or weak typed language may can be a key architectural concern to be decided when a system is being developed.
The requirements used to determine the use of a strong or weak language may be tied to data integrity or system availability goals, since applications written a strongly typed language should not perform functions with invalid data, resulting in errors.
However, code written in a strongly typed language may be less reusable for different functions, leading to additional development work required.

#### Programming Paradigms

There are certain features of programming languages based on how they achieve the desired process of manipulating or handling data.

##### Declarative Programming

Declarative programming expresses the logic of a task without describing how it should be executed; in these languages, a system must interpret the logic and execute appropriate tasks.

SQL is an example of a declarative paradigm, where users issue commands and the DBMS is responsible for executing the commands following its own internal constraints.
This abstraction is an important security capability, as it presents opportunities to control what users can and cannot do; for example, a DBMS may implement additional authentication requirements for sensitive SQL functions based on the user’s identity.

##### Imperative Programming

The imperative paradigm of programming uses statements or commands that change a program’s state, similar to issuing imperative commands in human languages like “stand up” or “study for the CISSP.”
Although this kind of direct control could be a security challenge, modern imperative programming often focuses on the use of procedures, sometimes known as subroutines or functions, which provide for greater control over how the program operates.

A standardized subroutine for accessing data in a filesystem can be tested for access control flaws; each time that subroutine is reused, there is assurance that it will implement access controls in a consistent manner.

##### Procedural Programming

Procedural programming is related to the imperative paradigm and is based on the concept of a program calling procedures, which are similar to routines or subroutines.
Procedures are a set of steps to be executed and allow these steps to be logically grouped and called dynamically when needed.

##### Structured Programming

Apart from procedures, languages may implement other structures for grouping elements of a program and the logical flow of a program’s code.
This offers the benefits of increased readability and clarity of the code’s function, as well as increased maintainability over time since the code is more easily understood.
This practice is called structured programming, because the code is structured using constructs like if/then statements that make it obvious what steps a program will execute at a given time.

##### Block-Structured Programming

Block-structured programming languages utilize blocks as an organizational unit; the scope of program elements like variables and functions is restricted to the block to prevent conflicts with other elements elsewhere in the code.

##### Object-Oriented Programming (OOP)

Object-oriented programming (OOP) is a paradigm that focuses on objects rather than actions in programming.
Instead of writing specific commands to gather input data and perform procedures on it, OOP treats both data and functions as objects, known as classes, which can be linked together through defined interactions.

An object is anything that has a state that can be tracked, like data pending a mathematical transformation to render it unreadable (the process of encryption).
Code objects are self-contained modules of functions that are “called” to perform their designated function.

Many modern smartphone apps offer image transformations like sharpening a photo; in this case, the photo is a data object, and standard image transformations are code objects in the app.
The photo is passed to the image transformation function, and the processed photo is passed back to the user interface once completed.

###### OOP Security Concepts

There are a number of security concepts related to OOP that are important, many of which relate to the abstraction inherent in viewing data and functions as objects that communicate in predefined ways.
These concepts include the following:

* **Encapsulation:**
This is also known as data hiding and is effectively a way of isolating data from being accidentally mishandled.
Direct access to a class can be denied to external objects, thereby restricting access to only approved functions known as methods.

* **Inheritance:**
Classes of data objects can have subclasses that inherit some or all of the main class’s characteristics, such as access restrictions.
For example, the Employee data class might have a Salary subclass, which implements the same methods for manipulating the data but additional role-based access control restrictions.
This subclass can be reused as a building block, which speeds development.

* **Polymorphism:**
This term refers to the multiple (poly) forms (morphs) an object may take when being created or instantiated.
Instantiating a new object from an existing object typically duplicates the attributes and methods of the existing object, but data of a different type may cause security concerns because the new data type requires different methods.
For example, a function that prints data to the screen is useful for a word processing program but could present security concerns if called to print sensitive data like a password.

* **Polyinstantiation:**
This term means making multiple (poly) copies (instances) of an object, typically with the goal of supporting different levels of confidentiality and integrity for that object.
Operating systems may create multiple instances of a shared resource space, like virtual memory, to prevent different processes from reading or writing over each other, or databases may create a copy of records for each classification level, omitting information above that classification level.
This prevents users at a lower level from even knowing that more-sensitive information exists, reducing the likelihood of inference attacks.

#### Markup and Scripting Languages

When many people think of computer programming languages, they imagine complex languages like C, which require specialized knowledge and skills.
However, languages that provide structure to data or automate basics sets of tasks also meet the definition, as these languages provide instructions as input to computer systems for handling data.

The security of these languages is often overlooked as they are simple enough for even relatively unskilled users to write.
However, their use in mobile code environments like web pages delivered via the internet requires that the security be considered, with controls governing where such code may be loaded from or blocking remote code like JavaScript altogether due to its untrusted nature.

These languages include the following:

* **Hypertext Markup Language (HTML):** Specifies layout or display elements of text delivered to a web browser.
* **Cascading Style Sheets (CSS):** Allows definition for how a web document should be styled for display, including fonts, color, and layout/spacing of elements on the page.
* **JavaScript:** Provides interactive applications inside a web browser on a client system, often for displaying and manipulating data on the user’s screen.
JavaScript may require access to privileged functions on user machines such as local file access, which is a major security concern since the code comes from an untrusted party across the internet.
* **Python:** A high-level language that can be used for a variety of uses ranging from small personal programs to large web applications.
As an interpreted language, it can run on a variety of platforms and interact with data in other applications, such as a local script written by a single user to automate repetitive tasks like cleaning up data in a spreadsheet, or a distributed web app that communicates with other systems and user browsers via Application Programming Interface (API) calls.

### Libraries

Software libraries are prewritten repositories of common functions, code, classes, scripts, procedures, or other software elements.
They allow developers to more quickly and easily integrate functionality into programs without the need to write code from scratch, as relevant modules from the library can be called where needed.
Many platforms like operating systems, social media networks, and cloud computing services include them in what is known as a software development kit (SDK), which speeds the task of developers building programs that integrate these platform’s capabilities.
In addition to the code or functions, many libraries also include other supporting elements such as help documentation and prewritten code templates.

#### Benefits of Libraries

The features of a library are shared among all programs written using the language or platform of the library, and their value comes from the easy reuse of elements.
Not only does this reuse speed development, but it also offers increased dependability of software since these shared functions are likely to be extensively tested and improved by the community of developers and systems implementing the library.
Many libraries also offer compliance-focused features, such as user interface components that are designed to meet accessibility requirements, or regulated functions such as credit card processing that can be implemented without the need to address Payment Card Industry Data Security Standard (PCI DSS) compliance.

#### Standard Features

Libraries typically implement a number of standard features, including subroutines, global variables, and class definitions.
Depending on the library, additional capabilities may also be offered, such as prebuilt algorithms for common tasks like encryption, as well as data structures like lists, tables, and arrays.
Libraries for specific platforms like operating systems also offer interaction with various functions of the OS, including filesystem access, handling data input/output, and accessing and controlling device through drivers.
Programmers using libraries can easily implement these features like building blocks in their programs without going through the full task of writing software for each task.

#### Library Security

The use of libraries in the organization should be governed by a number of requirements, including the need for validated libraries that meet proven security requirements.
Organizations may use trusted vendor’s libraries, develop libraries internally that can be shared across projects, or even use open-source project if the risks are considered acceptable.
A library containing vulnerable or malicious code poses a risk to the entire application relying on it.

### Toolsets

There are a wide variety of tools to assist programmers, engineers, testers, and others to develop software and systems.
They perform various functions including creating and debugging code, maintaining consistency of code when multiple people are working on it, and enabling testing.

Many of these tools are combined into toolsets that serve a number of developer needs, such as the following:

* **Source code editors**, which provide developers the ability to both write and check their code.
These are similar to text editors, but include development-specific features like syntax checkers to identify incorrectly written code, library integrations that can automatically suggest appropriate functions, and even prebuilt templates of common functionality that developers can leverage to speed up their work.
Functions like comment and documentation generation may also be part of the editor, allowing developers to write explanatory comments that help other developers understand the purpose of a given piece of code or that can be used to automatically generate user documentation about the particular features of a program.

* **Code repositories and revision control tools** provide centralized storage and integrity protection for code.
Centralized storage supports multiple developers working simultaneously, while version control ensures that developers are not able to interfere with one another’s work by locking code that is already open for edits and maintaining revision history with timestamps and details of the user who made changes.

* **Debuggers and bug databases** help developers find and fix issues with their code. Some work by highlighting known issues or identifiable flaws, such as function calls with incorrect inputs, while others can provide line-by-line execution of a program to identify where a particular error is occurring.

* **Compilers** are designed to create platform-specific application binaries that consist of machine language that can be run on a specific architecture.
Many programming languages can be compiled to run on a variety of platforms, allowing developers to write a single program and then use an appropriate compiler for systems they want to support.

* **Testing tools** typically include static code analysis and unit testing tools. Static code analysis reviews the underlying code of a program without actually running the program itself; the goal is to identify problems like improper coding that could lead to buffer overflow conditions.
Data flow analysis may also be performed by these tools, where possible values that a function could generate are reviewed to ensure they meet expected parameters.

Toolsets in use at the organization should be governed by security practices like configuration management, patch management, and audits.
Proper versions of approved tools and controlled changes to those tools should be implemented, and the developers using these tools should be trained on their proper use and procedures for maintaining security.
This includes only installing approved modules or functions, seeking approval for new modules, and making use of the existing tools to enforce security controls as defined by the organization’s secure SDLC procedures.

### Integrated Development Environment

An integrated development environment (IDE) is a combination of tools in a single environment, like a desktop program or web application, which supports the work of developers.
The goal of combining and integrating tools is to enhance productivity as well as to ensure consistency by reducing the overhead of managing multiple tools.

Capabilities frequently incorporated in an IDE include a source code editor, debugging tools, build automation tools like compilers, testing tools, and deployment automation like integrations with container orchestration and deployment platforms including Docker and Kubernetes.

IDEs for OOP languages typically include support features specific to the language, such as a browser for objects available in the language or classes that have been created for the specific program under development, similar to the formula editor in Microsoft Excel.
Features of the source code editor may be specific to the language, such as visual programming for languages where classes or objects can be arranged and linked in visual layouts that model the flow of data or execution of a program.

As with toolsets, the security of the IDE should be a focus of the security program as well. The fundamental security of any application under development is impacted by the tools used to build it, so ensuring components of the IDE are approved and maintained is critical.

### Runtime

Quite simply, a runtime is the collection of all hardware and software required to actually run an application.
For many systems, this will be quite complex, as hardware may contain its own software (known as firmware) for proper operation, device drivers may be required to allow apps to communicate with the hardware, and an OS will need to coordinate actions and mediate access to the hardware.
The various layers of hardware and software required to deliver these information system services are discussed as part of system architecture in Chapter 3, “Security Architecture and Engineering.”

The combination of compiled program code, OS, device drivers, and firmware may be all the elements required for a compiled language program to function, though many will access functions or data needed to operate via APIs, remote procedure calls (RPCs), or other service calls.
Interpreted languages will also require an interpreter as part of the runtime, which performs the translation of the code to a machine-executable format and may also be responsible for enforcing security controls like sandboxing.
As with all information systems, security opportunities and vulnerabilities exist in all elements of a runtime and must be considered and addressed.

#### Trusted Computing Base (TCB)

For high-security applications, secure hardware such as a trusted computing base (TCB) may be required.
A TCB comprises all hardware, software, and firmware responsible for enforcing security and serves the function of a reference monitor to control access and enforce security policies within the system.
Properly design, testing, and isolation of the TCB elements is required to achieve the TCB, which then supports trusted secure access to the system and its resources.
The TCB is a primary candidate for configuration and change management, as are all OSs and information system components since they are obvious implementation points for both technical security controls like encryption and process security controls like patch management.

#### IoT and Edge Computing

The traditional model of a runtime many people visualize consists of a desktop computer (or laptop) running a standard OS like macOS or Windows.
Trends like Internet of Things (IoT) and edge computing now mean that the collection of hardware and software needed to perform computing functions is much broader.
Smart washing machines, thermostats, and sensor-enabled devices are part of the runtime environment and may include some basic data acquisition and processing capabilities.
Many of these devices rely on networking technologies like WiFi or Bluetooth to synchronize data, meaning these are part of the overall IoT runtime environment and must be considered as part of the organization’s security plan.

### Continuous Integration and Continuous Delivery

Development methodologies like Agile dramatically reduce the time it takes to deliver functional software, often cutting development time from years to months or even weeks.
The driving factor is to support users by releasing functional software more rapidly to meet business and functional needs.

#### Continuous Integration (CI)

Continuous integration (CI) is the practice of continuously merging developer’s code to a shared main location, often known as a repository.
Integrating code more frequently reduces the cost and time required to do large-scale reconciliation and integration activities like debugging any issues caused by the newly written or modified code.
This in turn supports the Agile goal of delivering a progressive set of features with each iteration, rather than a monolithic deployment.

#### Code Repository

A code repository is an implementation of configuration management that enforces rules on how items enter and leave the controlled state.
As an example, in the GitHub repository model, a developer creates a pull request that highlights the changes being introduced with the new code.
The pull request must undergo inspection like manual review by other developers or automated testing before it is merged back into the base code branch.

Automated security testing can also be combined with these integration activities. Although automated scanning can’t find everything, performing it more frequently and on smaller units of code can increase its overall effectiveness.

#### Continuous Delivery (CD)

Continuous delivery (CD) is a process that delivers code automatically to an environment other than live production or requires some manual steps to deploy to a production environment.
This is often used in software development where a testing environment with manual testing processes is required, such as systems processing regulated or sensitive data, or complex systems where automation may not be possible.
In these cases manual verification must be performed before new code goes live. The completion of testing can be an automated trigger to deploy the new code, or deployment may be manual after the testing is completed.

#### Continuous Deployment

A closely-related and somewhat confusing term is continuous deployment (also referred to with the acronym CD), which extends the concept of CI by taking the integrated code and deploying it to the production environment automatically with no manual intervention needed — unless an automated step fails.
Achieving continuous deployment demands a high degree of maturity in an organization’s automated QA and testing processes, to ensure that code is thoroughly tested and passes before being deployed.
Automated functional, integration, and regression testing are often required to ensure the newly developed code does not break the system or introduces bugs.

#### CI/CD Pipeline

The combination of tools and processes to implement CI/CD is often known as a pipeline, and this pipeline includes all the steps and requirements to deliver functional software to the production environment.
This will include manual steps like writing code and addressing any errors that arise, as well as automated steps like running tests and scans.
Packaging the code, such as building containers, and deploying it are the final stages of the pipeline.
CI/CD pipelines will span multiple systems from an IDE to a code repository to a cloud hosting environment, and each system and step in the pipeline is a chance to implement security controls like integrity verification, encryption to protect confidentiality, and manual or automated testing and reviews.

#### Emphasis on Testing in CI/CD Pipelines

##### Infrastructure as Code (IaC)

CI/CD relies heavily on automation to achieve speed.
Rather than manually building the computer hardware, OSs, and enabling applications like web servers, a CI/CD pipeline will likely take advantage of virtualized or cloud computing where these activities can be automated and orchestrated using definition files.
These definition files specify the required computing resources that need to be provisioned when an application is deployed, and this practice is called infrastructure as code (IaC).
Configuration management, testing, and auditing are much easier since definition files exist to specify exactly what the software and virtual hardware configuration should be; a CISSP can achieve a great deal of security impact by implementing small, automated, and repeatable security checks into this automated pipeline.

##### Automated Security Testing

Application security (AppSec) is another important automated testing function supporting CI/CD pipelines. Although automated testing is not a total replacement for manual testing activities, it does offer several advantages.
It can be performed more frequently than manual testing, often with each deployment or change, and it can test a larger portion of the application due to the speed of computerized testing.
Unit, functional, and regression testing should all be included in automated testing activities, as well as security-specific testing like vulnerability scanning.
DevOps and security practitioners can identify ways to design an AppSec program using Agile principles, with the goal of integrating security within a CI/CD pipeline to ensure security requirements are met without impeding the agility of the organization.
Practices like continuous security codify many of these principles, and more details can be found at devops.com/9-pillars-of-continuous-security-best-practices.

Automated testing tools can shift the balance of work away from the security team and break down an important barrier that often leads to issues. Security testing is typically done by security personnel, and then results must be communicated to the developers.
This transfer can cause information to be lost or miscommunicated, leaving security vulnerabilities unaddressed. Automated tools can be integrated into the IDE, allowing the testing results to be communicated directly to developers.

For example, an application security vulnerability scanner may run automatically as code progresses to the testing environment, where it finds a SQL injection flaw on a particular page of a web app.
Using an API, this finding — including the specific test case, address of the page, and other details — can be put immediately into a ticket and assigned to the developer responsible for that web app feature.
The developer still has the code fresh in their mind and can easily use the data supplied to fix the flaw.

### Security Orchestration, Automation, and Response

Security orchestration, automation, and response (SOAR) is a recently introduced term that combines multiple processes and domains, typically offered as a software platform or set of integrated tools.
Its primary goal is to speed the time to detect and respond to security incidents, and it achieves this by integrating disparate data sources and systems to coordinate automated actions.

SOAR is often confused with security information and event management (SIEM), but SIEM tools simply ingest data to support response activities by correlating data and generating alerts for human responders.
The difference is similar to intrusion detection versus intrusion prevention: intrusion detection systems (IDSs) generate an alert, while intrusion prevention systems (IPSs) take action automatically to stop the intrusion.

#### Orchestration

This is where SIEM and SOAR have some overlap, in that they both integrate data from disparate systems into a single data set.
However, SOAR goes beyond logs and includes data from security tools like user and entity behavior analytics (UEBA), IDS/IPS, external threat intelligence services, and domain-specific solutions like email anti-phishing tools, anti-malware, application security scanners, etc.

In many cases, alerts on suspicious activity from a SIEM will be an input to a SOAR platform, relying on the SIEM’s ability to correlate data across networks or systems.
The use of APIs is critical for data ingestion as well as exposing functionality on the target systems to enable automation of responses.
For example, a user receiving a phishing email that includes a malicious file will trigger alerts from an anti-malware tool and a UEBA agent, which the SOAR can identify as being related to a specific user, email, and set of actions.
Orchestrating data from these disparate systems into coherent, actionable intelligence is the first step of value in a SOAR solution.

#### Automation

In the previous example, the malicious file download might trigger anti-malware action on the affected user’s machine, such as quarantining the file, deleting malicious data, and alerting an administrator to the infection.
However, that alert in isolation might miss the fact that other users received the same email or that the attachment exploited a flaw that could execute a worm that spread itself to other endpoints, where detection may or may not occur.
Such a holistic overview of the problem requires an incident responder to investigate not only the cause of the malware but also its impact across the network, and this is a complex, time-consuming, and error-prone task.
Orchestrated intelligence flowing to the SOAR enables automated response much faster than the speed of a human investigation.

Automation follows a set of machine-executable rules, often collected in a playbook or other set of instructions designed to respond to specific triggers like malware detection.
The advantage of SOAR over legacy methods is the speed with which it executes. Speed is critical since this is a countermeasure activated after a risk event has occurred, and the goal is to reduce the duration and impact of the incident.
Automating actions like forcing a password change after a user’s workstation has been impacted by malware, isolating the affected machine from the network, quarantining or deleting the email from other users’ inboxes, and opening an incident response case with relevant details prepopulated saves time and reduces the window of opportunity for the attack to do damage.

#### Response

SOAR evolves incident response from the legacy model of detecting and manually responding to a coordinated, automated response in which human expertise, knowledge, and talent are utilized in the most efficient manner possible.
Information systems can receive and act on data faster than human analysts; even a fully staffed, 24/7 security operations center (SOC) will exhibit slower response times compared to an automated system with visibility into and automation abilities across the infrastructure.

Repetitive or easily automated tasks can be handled by the SOAR platform, like identifying a malicious email received by one user and deleting it from the inboxes of other users before they click on links or open malicious attachments.
This frees up human time and attention to focus on novel threats; the SOAR can also augment human capabilities by pulling together meaningful information to speed decision-making and reduce the time needed to respond to incidents, which again reduces their impact on the organization.

By way of example, consider the previously detailed malicious email incident. The original user who opened a phishing email likely triggered alerts due to the presence of malware on the network. The SOAR can take in relevant information as part of orchestration and then execute automated responses triggered by incoming data.
In addition to the isolation steps mentioned already, the SOAR could also initiate malware scans to detect lateral movement throughout the network and institute firewall blocks to prevent traffic to any malicious sites or IP addresses associated with the phishing email and malware.
These actions can be performed in mere seconds, while a human might take minutes just reading the initial alerts.

SOAR doesn’t seek to completely remove human intervention in incident response. Many of the platforms include incident response case-management tools, with the aim of consolidating information needed for decision-making and providing automated chains of actions that can initiated by the responder.
To continue the malicious email example, once the automated response is carried out, an incident case file may be created and assigned to a human responder.
The case will include all relevant data including the impacted users, automated actions like password resets, and recommended manual next steps in the process.
Presenting all information relevant to the incident in a single location allows the responder to make better informed and quicker decisions and can also provide a consistent source of information to all members of the response team.

Any system that implements automated responses, such as a SOAR or IPS, can suffer the problem of false positives leading to unwanted action.
A SOAR might suspend a user’s account if suspicious login activity is detected, but if the user is legitimately traveling or working outside normal hours on a critical time-sensitive task, the SOAR has created a denial-of-service (DOS) condition.
Adjusting these tools to reduce the chances of false positives is achieved by tuning, which effectively trains them on the specifics of an organization’s environment. This process is discussed in more detail in Domain 7, especially in the context of tools implementing artificial intelligence (AI).

### Software Configuration Management

Software configuration management (SCM) is the implementation of configuration and change management practices to support secure software development.
Its main purpose is to provide integrity for key software resources like source code and program resources like requirements documentation.
These items placed under configuration management are known as configuration items (CIs). Each CI must be uniquely identified, and changes to CIs must follow a rigorous change process to ensure the changes are coordinated and do not introduce flaws or break functionality.

#### Balancing Number of Items with Criticality

Common CIs include source code, software libraries, and individual configuration settings such as patch levels or software settings; together, a group of CIs represents a baseline, which is a known good configuration of a system.
When choosing a set of CIs, it is important to balance the number of items being managed with their criticality.
Controlling every script file or line of help documentation may be desired, but the extra time and overhead of managing so many items under configuration control can introduce unwanted operational delays.

#### Changes of Baselines

Baselines represent a stable set of immutable configuration items that collectively provide a functional system — note that this term is also used in the context of security controls, where a baseline represents the minimum set of required controls.
SCM baselines are often associated with desired system characteristics such as security settings and configurations or functionality requirements, such as the known good settings to enforce encryption requirements or versions of COTS products required for system functionality.
Because the CIs comprising a baseline are under configuration management, changes to baselines must follow the change management process. This is often done by creating a branch, which is a set of versioned CIs undergoing development or change separate from the known baseline.
Testing, quality assurance, and acceptance criteria must all be satisfied before the branch is merged back and the changes are incorporated into the baseline.

SCM’s chief goal is to promote visibility and control over the state of and changes to all the elements in a software system.
Changes can introduce bugs or flaws that negatively impact fundamental security concepts of confidentiality, integrity, availability, nonrepudiation, and authenticity (CIANA), and it is imperative to preserve the integrity of system elements like source code, requirements documentation, and settings.
Uncontrolled changes can introduce vulnerabilities or have other unintended consequences. In the field of SCM, version control is often used as a way to identify software elements, based on a version number, and control changes to them by enforcing rules about how and when new versions are created.
Tools that implement this management are known as source code version control or revision control systems.

### Code Repositories

Repositories, or repos as they are commonly known, are a cornerstone of modern software development and provide key features needed to support multi-user teams developing software.
They provide a centralized storage location and support collaborative work by allowing multiple users to access and make changes, as well as implementing restrictions such as branching, which allow a user to pull code and make nondestructive changes isolated from the main code.
When complete, the changes can be tested and merged back into the main code.

#### Protecting Source Code

Source code is a valuable asset that faces risks just like any other data in the organization.
A repository provides many points of control over the source code in support of the security fundamentals of CIANA, and the repository itself is a valuable asset due to its control capabilities and valuable contents.

Implementing controls on the repository can be used to achieve security objectives including the following:

* **Confidentiality:**
Repos provide access controls in the form of authorization. Some are more granular than others and allow for developers to be granted separate read and write permissions to specific projects, code modules, or branches, while others simply restrict the repo to access only by authorized users.
Additional features to protect confidentiality may also include restrictions such as preventing copying of data to local computers or portable media devices, which allows for greater control over the dissemination of source code.

* **Integrity:**
Most code repositories implement some form of configuration management and version control for software.
Open-source collaborative projects may configure the repo to allow any authorized user to make changes, while a tightly controlled project may require a developer be specifically authorized to work on a particular software element.
Some repos integrate with project management or ticketing systems to allow for dynamic access controls; for example, a developer is assigned a task to update a specific module, which grants them temporary write access that module’s code.
Version control systems that allow rollback to a previous version can also be used as a countermeasure to unintended or undesirable changes.

* **Availability:**
The centralized nature of a repo can be a single point of failure. Having a single system hosting all data also makes it easier to back up and restore the system, as a robust backup schedule for that system guarantees that all the required data is available when needed.

* **Nonrepudiation:**
Access control mechanisms implemented in repositories — such as unique user IDs, audit trails, and version history — can be used to identify and hold users accountable for changes they made to source code.

* **Authenticity:**
Data is authentic if it can be proven that no corruption or unwanted alteration has occurred, and source code repositories can implement this using version control to roll back unwanted changes and using backups to support integrity.

#### Protecting the Repository

Apart from offering security benefits for managing code, software repos are themselves valuable assets in need of protection.
They are valuable targets for a number of reasons, including the fact that they host sensitive data and can be used to introduce unwanted software or functionality.
For this reason, the repo itself needs to be treated like all other valuable assets, with a risk assessment and corresponding security mitigations such as the following:

* **Data:**
Tools like data loss prevention (DLP) and intrusion detection should be deployed to monitor data and activity on repository systems and hosts.

* **Communication and network:**
Proper security measures to control and monitor access to the repository must be in place.
Due to the remotely accessible nature and increased trend of distributed systems, it is particularly important to secure remote network access by implementing protocols like HTTPS and Transport Layer Security (TLS), or secure access solutions like a VPN or proxy service.

* **Access control:**
Principles of minimum necessary and least privilege must be considered, and access control procedures such as request approvals and routine reviews should also be implemented.

* **Backup and availability:**
Since software is the foundation of most modern business processes, the source code and resources needed to deploy it, such as IaC definitions or build instructions, are fundamentally important assets for preserving availability.
Cloud-hosted software repositories offer high availability and resilient configurations, though organizations with stricter requirements may be forced to host and maintain their own repos.
In all cases, the configurations should support the organization’s availability goals by ensuring software code is accessible when needed.

### Application Security Testing

Application security starts with the security of the code comprising the program. In an ideal world, this would require only a preventative approach — with unlimited time and resources, all possible bugs could be prevented.
Sadly, that is not how most software development projects work, and there are a number of factors, such as legacy code and the evolution of software exploits, which mean application security must incorporate active hunting for vulnerabilities.
This full lifecycle approach encompasses application design and SDLC management practices as discussed throughout this chapter, as well as ongoing assessment and hunting for flaws or vulnerabilities in existing code.

There are a number of application testing paradigms, outlined next. The best approach to application security testing will combine multiple approaches based on what components make up the system, as well as the organization’s tools, knowledge, and maturity at performing software testing.

* **Static application security testing (SAST):**
SAST evaluates source code and other nonrunning application elements like compiled binaries.
It can be easily incorporated in an IDE and the developer workflow, with automated testing performed when developers check code in and immediate feedback to developers in a format that is easy for them to understand.
Testing is performed in development or testing environments, which means there is no impact to live production environments.

  * **SAST disadvantages:**
  SAST tools can typically understand only one programming language, so different tools will be required if multiple languages are in use.
  They may also be difficult for nondevelopers to access due to their IDE integration, meaning security practitioners who aren’t developers are excluded.
  Since they do not test running applications, complex vulnerabilities due to interfaces between code and underlying system elements like OS exploits cannot be detected.

* **Dynamic application security testing (DAST):**
The word dynamic is part of DAST and describes how these testing tools execute the application to look for flaws.
They can typically run against any application with an interface or API regardless of underlying language and are not as tightly integrated with an IDE, which means access is easier for nondevelopers.
Some include integrations with IDE or CI/CD pipeline tools; for example, an automated DAST scan is initiated when new code is pushed to a testing environment, and any findings are automatically pushed into developer tickets or task assignments.

  * **DAST disadvantages:**
  Due to their possible existence outside the developer’s toolset, there may be organizational challenges related to getting information to the correct developer.
  Some DAST tools are designed for continuous monitoring of production environments as a detective measure; this may cause performance issues and, more importantly, allows software with flaws to enter production environments where it could be exploited until discovered.

* Interactive application security testing (IAST):
This emerging set of tools and abilities combines elements of SAST, DAST, and penetration testing, often using complex algorithms and machine learning to analyze source code and correlate vulnerabilities discovered during dynamic testing.
It has largely emerged since the rise of CI/CD practices, so most tools offer integrations with both developer tools and security platforms, ensuring better visibility into the testing efforts and results.

  * **IAST disadvantages:**
  Like any emerging technology, there will be growing pains like higher costs for in-demand new features and a lack of expertise in the marketplace.
  Since IAST incorporates source-code analysis like SAST, it is also language-dependent, meaning some languages may not be supported and the dynamic elements of IAST may cause performance issues if run in a production environment.

* **Runtime application self-protection (RASP):**
As the name runtime implies, RASP executes alongside the application as it is run; RASP is also less of a testing tool but is often incorporated into overall application security to complement SAST and DAST.
A RASP security tool integrates with an application and analyzes the program’s execution to spot unusual or unexpected behavior, and then it takes corrective action.
This can include blocking specific requests or functions to shut down an active attack and also implementing preventative measures like virtually patching an application to prevent the same attack vector from being used in the future.

  * **RASP disadvantages:**
  Like any automated reactive technology, false positive RASP hits can lead to DOS, much like an IPS shutting down unexpected but legitimate traffic.
  Similar to IAST, as a relatively recent technology, RASP will suffer from compatibility and a gap in skills to configure and manage the tools.

