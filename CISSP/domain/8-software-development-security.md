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

---

## ASSESS THE EFFECTIVENESS OF SOFTWARE SECURITY

### Auditing and Logging of Changes

Events can happen several thousand times a day in information systems of even moderate complexity.
Users log in and out, applications and services start and stop, users enter incorrect passwords, servers and processes are restarted, and so on, all of which are nonmalicious and expected actions.
For example, a standard Windows 10 workstation used during a regular workday can easily generate tens of thousands of logged events; reviewing each of these manually is a virtually impossible task.

Most events change the state of the system in some way; for example, a server restarting means the system is not available for a period of time. This could be caused by an unexpected power failure or by a new deployment of code that adds user-demanded functionality.
Keeping track of these changes and providing visibility into which are normal and which are not is crucial for diagnosing issues and for remediating events that rise to the level of security incidents.

Auditing and logging are different, though often confused, terms. They are often used interchangeably, such as in audit logs, even though each term actually has its own definition.
These crucial terms, along with other related concepts, are defined here:

* **Auditing** is an official or systematic inspection of something such as an account, documents, or practices.
In software environments, audits focus on the implementation and effectiveness of software security controls, and they often rely on an official standard of comparison such as the ISO, NIST, or OWASP security frameworks.
Auditing processes like change management and QA often rely on data captured during normal process execution, which is where log data becomes important.
Logs themselves may be subject to audit to identify instances of behavior that go against organization requirements, such as users attempting to access unauthorized resources.

* **Logging** is merely the recording of events. In a software system, logs are generated by all system events, like users signing into an application, and the logs should capture sufficient detail to definitely identify critical information about the event.
This includes what the event was, who/what initiated the action, when it occurred (often called a timestamp), and other metadata about the event like a criticality level.
Some events will be categorized as incidents if they violate security controls or cause a degradation of the system.

* **Accountability** is the ability to identify who or what is responsible for events that occur and is a key element of identity and access management.
Sufficient data is obviously required; if log files do not record usernames or timestamps, it will be impossible to identify which user took a particular action at any given time.

* **Nonrepudiation** is an indisputable proof of a unique individual having performed a specific action. This concept is often confusing because it is a negative — repudiating an action means refusing to accept responsibility.
Nonrepudiation, therefore, means having sufficient proof to prevent a user from denying that they took the action.
Not all log data will support nonrepudiation; for example, physical access logs collected at a main door are not sufficient to prove a particular employee was in a specific location within the building, unless access controls create log data as the employee moves about the facility.

#### Applications of Logging and Auditing

##### Logs

Log generation and routine audits are both reactive and detective controls. Logs are generated after an action has occurred, so they do not work to prevent a risk being realized, though they support monitoring activities that detect when something has gone wrong.
Logs are only made useful when audit and monitoring processes make use of them; much like policies, they are useless if documented but never read or used.

SIEM tools ingest log data as a primary input and then perform monitoring activities on the collected data to look for suspicious or unwanted behavior.
SIEMs typically perform this monitoring on a continuous and near real-time basis, and alerts generated are key inputs to the detection phase of incident response procedures.

##### Audits

Audits are a more formal and structured process of reviewing activity against an expected baseline, often as a way to demonstrate compliance with a legal, regulatory, or other compliance burden.
Assessments are a more informal process of review and are often conducted to satisfy internal oversight goals rather than external compliance requirements.

Log data is crucial for audits, as it presents a record of system activity over a period of time, which confirms if an organization is functioning in accordance with documented governance.
For example, if all software changes must follow change management procedures, then version history in the software repository should align with documented change requests.

##### Source Code Management (SCM)

Source code management (SCM) is a particularly important application of logging and auditing for software security. SCM provides capabilities to track code changes being stored in a repository, sometimes down to the level of individual lines of code.
These logs can be useful for operational troubleshooting if a particular piece of code is causing errors and can also be used to audit compliance by identifying code changes that might diverge from identified requirements.
Code integrity is also maintained, as unintended or unwanted changes can be rolled back to known good versions.

##### Logging and Events

Logging in operational environments provides insight into the activities being performed by users and processes while a system is in active use. These logs are often used for access reviews or audits, as well as investigations of both operational and security incidents.
Examples of events that are typically logged include users signing in and out of systems or applications, application errors encountered during processing, and even environmental control issues like power fluctuations and hardware disruptions.
Events like user sign-ins may be useful only for audit and forensic analysis, but operations teams may monitor log data for hardware and environmental controls, as these may be precursors to a failure that negatively impacts system availability.

##### Log Data Usage

Log data can be used for a variety of monitoring purposes by multiple teams in an organization, including the following:

* **Change management:**
Logs of system changes like new app installations or changes to access permissions can be used to verify whether changes made correspond to approved change requests.

* **Security incidents:**
Live production environments, especially those with public- or external-facing elements like web servers, will see a variety of suspicious and malicious activity.
Logging and monitoring these actions are crucial tasks for security practitioners and often form a key pillar of security analysts’ and incident responders’ job functions.

* **Performance management:**
Although not an obvious security task, availability is a component of security.
Ensuring systems are running, reachable, and able to support the required user load can be achieved by monitoring various metrics from log files, such as CPU utilization, memory consumption, and network bandwidth usage.

* **Cloud environment changes:**
When consuming cloud services, most organizations will lose physical and some logical visibility over parts of their IT infrastructure.
Rather than deploying network sensors to detect problems, web pages or APIs with status information will provide vital logs and monitoring data, such as when a service began to experience degradation or an outage and when it is restored.
As with other control modifications to accommodate cloud computing, logging and monitoring must take into account what types of data are made available for monitoring and how to make effective use of the data.

##### Standards and Frameworks

There are definitive resources for logging and monitoring practices as well as audit standards. NIST SP 800-92, “Guide to Computer Security Log Management,” and the OWASP Logging Cheat Sheet cover basics like policy requirements and best practices for implementing logging functions.
Many compliance frameworks mandate certain types of logs or require that logs generally contain sufficient data to support accountability.
These compliance frameworks, such as PCI DSS, also provide auditing standards for assessing the implementation and operating effectiveness of security controls including logging.

#### Software Development Auditing

Audits are an important compliance tool for verifying conformance with established governance and are discussed in more detail in Domain 6.
Software development projects should be audited to ensure desired security controls are followed when creating secure software, as well as to ensure software under development is implementing the required functions to meet security requirements.
Audits are useful across multiple aspects of the business outside of security as well, such as schedule, budget, and resource management, to ensure projects are running smoothly and meeting deadlines, which enables business objectives like launching new products or staying ahead of competitors.

Auditing activities differ at various phases of the SDLC, and the audit program needs to be adaptable to fit various SDLC methodologies.
An annual audit schedule may catch large Waterfall projects in the same phase each year, so evidence collection should be an ongoing activity throughout the year to ensure auditors have a complete picture when they perform reviews.

Considerations at each phase of the SDLC include the following:

* **Requirements phase:**
Audit artifacts from this phase will mostly be documentation such as requirements analysis documents and the documented requirements themselves.
Key activities to audit include reviews like privacy impact assessment (PIA) and data classification or system categorization.
Ensuring complete requirements and documented understanding is critical to designing and building a system with adequate protection mechanisms for data.

* **Design phase:**
During design, alternatives will be evaluated against requirements, such as cloud versus on-premises hosting for a system.
Key activities to be audited include the formal risk assessment and decision processes utilized to determine which of the proposed solution alternatives adequately meet the stated requirements, and formal acceptance of the residual risk.

* **Implementation phase:**
Hands-on activities like writing code, testing system functionality, and security tests like code reviews or penetration tests should all be in scope for the audit program.
Auditors may perform documentation reviews to verify testing activities were conducted and the results properly acted upon, and they may conduct interviews with developer personnel to test the level of knowledge regarding key processes and procedures.

  Testing is also an important audit method used to demonstrate that processes and technical controls respond as expected, like trying actions known to violate separation of duties policies and ideally observing the actions being blocked.
For example, an auditor might write and attempt to deploy code using the same user account to verify that system controls are in place to block the deployment.

* **Verification phase:**
Audits of testing activity are important to verify oversight functions are implemented and effective.
These should include checks for adequately designed test cases or data, coverage of testing, execution of all required testing, and successfully passing required tests before system deployment.

* **Operation and maintenance phase:**
Since systems will spend most of their life in this phase, the bulk of auditing occurs here. Systems in this phase may also be subject to more external audits, as many laws and regulations require auditing on live production systems.
Many audit frameworks now incorporate live system audits as well as SDLC auditing, due to the key role that secure software development plays in overall system security.

### Risk Analysis and Mitigation

Software development and security requires ongoing assessment and mitigation of risks, so these concepts must be applied across all SDLC phases and software environments including development and end user or live production.
The goals are still the same, chiefly identifying assets to protect, likelihood and impact of various vulnerabilities and related threats, and the most cost-effective ways to manage the risks.

Software risks require unique analysis approaches, and the first step is determining targets for analysis.
Aspects of software development environments and practices that should be considered when performing this risk assessment include the following:

* **Data risks:**
Information systems store, transmit, and process information that requires protection, so the systems themselves are often at risk due to their role in handling data.
The complex assortment of software, hardware, and technology services like network connections and data centers make it difficult to find a starting point for the analysis, and the sheer number of information systems in many organizations multiplies the challenge.
Security practitioners should prioritize based on classification levels; systems handling the most sensitive or highly regulated data are likely to cause the most impact in case of a breach.
That doesn’t mean lower-sensitivity systems can be ignored, however, and the possibility of an adversary compromising a lower-classified system and pivoting to a higher one must also be considered.

* **New technology risk:**
Information systems running standardized commercial software with well-known configuration and support needs (and with proper support and maintenance) are usually less risky than emerging technologies.
A lack of knowledge and expertise increases the likelihood of a misconfiguration when deploying systems based on new or emerging technology, and their novelty can mean security options are not yet available.
Smartphones are a recent example — although workstation operating systems had advanced full disk encryption (FDE) when smartphones were originally popularized, hardware and software limitations meant FDE support on smartphones was limited.
This restricted the risk mitigation options available to organizations using these devices.

* **System changes:**
There are a variety of reasons a system might change over time. Organizational needs evolve, new technologies become available, and old technologies cease to be supported.
System changes can introduce new risks and significantly alter existing risks, though in some cases, changes may reduce or eliminate risks as well.

  Migrating a legacy application from on-premises hosting to a cloud-based microservices architecture can reduce the likelihood of system outages due to high availability cloud services, but the loss of physical control over data center hardware adds physical security risk while simultaneously changing the mitigation options available.
  Rather than physical locks and access controls, organizations might use insurance to transfer risk of data theft at a cloud provider, as well as additional encryption to reduce the impact of data theft.

  These risks should be identified as part of change management, and requirements must be documented and carried through all SDLC phases to address these risks appropriately and test the mitigations in place.

* **Code risks:**
Software is code, and unintended or malicious changes introduce serious risk to all elements of security.
Improperly handled changes can introduce bugs or flaws rendering a system unavailable, while the integrity and authenticity of data processed by a system can be compromised by unapproved code changes.
SDLC activities like code reviews, change management, testing, and vulnerability management should all be designed to detect and correct these risks.
de is also a source of confidentiality risk, as improperly programmed and configured systems will not implement the desired levels of data confidentiality.

#### Risk Assessment and Treatment

Risk assessment methodologies are covered in Domain 1 and include a variety of approaches for understanding the likelihood and impact of various risks on the organization’s operations.
There are best practice–based standards for performing risk assessments across entire organizations or individual information systems, including ISO and NIST.

Frameworks for risk assessments in technology and information security include Operationally Critical Threat, Asset, and Vulnerability Evaluation (OCTAVE) and Failure Modes and Effect Analysis (FMEA).

Risk analysis is one component of risk assessment and involves a systematic review of the identified risks for the impact or likelihood.
Specifically, to software development security, a CISSP should be able to assist various teams responsible for software development and delivery with tasks like identifying system- or software-specific risks.
Once identified, these risks require mitigation plans to reduce either the likelihood or impact to a level below the organization’s defined risk threshold.

Sources of risk in software development or points where risks can be detected in the SDLC include the following:

* **Planning:**
The organization’s approach to system development can introduce operational risks like schedule or budget concerns.
If security is broadly planned as one day of testing before a system launches, it is unlikely the security effort will be effective, or findings will be adequately remediated.

* **Requirements:**
New system features, like exposing systems to access from the internet or adding new features like credit card processing, introduce risks such as new attack vectors or regulatory compliance burdens.

* **Design:**
The chosen design for a system may increase or decrease various risks like remote access, lack of features to support needed security controls, or cloud vendor lock-in.
For example, a choice of one cloud vendor and DBMS may introduce limits to the granularity of access controls or available encryption options.
The cost of an alternative DBMS or cloud provider may be too high, which drives the need for compensating security controls.

* **Development:**
While being developed, all the security controls discussed in this chapter must be addressed to mitigate software development risks.
This includes appropriate use of developer toolsets, proper use of secure coding guidelines and standards, and testing to ensure the software being developed meets both functional and security requirements.

* **Operations and maintenance:**
The vast majority of risks against a system impact it during live use by end users. The routine assessment of risk and a continuous monitoring program will be crucial to measuring these risks and the effectiveness of chosen mitigations.
Key sources for identifying new risks will include the routine risk assessment as well incident response processes.

  Ongoing processes like patch and vulnerability management, monitoring threat intelligence and continuous monitoring via the SOC all take place during the operations phase.
  Addressing maintenance issues like applying patches, system upgrades, or preventative maintenance are also crucial risk mitigation activities performed during this phase.

#### Mitigation Strategies

When discussing security control selection for software development, it is important to note that implementation of these controls must be integrated into existing SDLC processes for the systems they are designed to protect.

Some costs to be measured when performing the analysis include direct costs like software or product purchases, professional services support, and operating costs like support contracts.

##### Direct Costs and Indirect Costs

Indirect costs may be more difficult to define or measure discretely due to the commingling of many factors in a development project.
For example, it might be difficult to definitely state how much additional testing time is attributable to implementation of a new security control when a development sprint also included other features.
Indirect impacts like staff productivity can also be difficult to discretely measure.
A drop in productivity after the launch of a new security control process might be attributable to the control’s overhead, but other factors like seasonal productivity loss during summer and winter vacations or a large number of untrained new hires could also be the cause.

##### Measuring Costs

Costs must be measured to guide selection of a mitigation strategy, but uncertainty and accounting for other factors should also be considered, and in very complex situations, a qualitative measurement may be the best course of action to prevent becoming bogged down by the measurement process.

Measuring the benefits of security controls can be similarly difficult, especially if the benefits are a negative or hypothetical.
Measuring the cost of a user abandoning a signup process, which leads to lost business, can be done by looking at the average revenue generated by a customer.
Deciding whether to add additional authentication requirements that lead to some users abandoning the signup process can utilize this data.
The cost of, for example, not being sued due to inadequate authentication security measures or negligence is difficult to quantify, while the price of a lawsuit against the organization is obviously easier to measure but difficult to hypothesize before it occurs.

Qualitative impact measurement can help in these situations; for example, a “minor” incident is unlikely to result in a business-ending fine, while a “catastrophic” incident could cause the business to become insolvent.
Partial quantitative measurements can also be made by looking at publicly available data on similar events that impacted peer organizations or publicly available studies like the annual Verizon Data Breach Investigation Report (DBIR), available at enterprise.verizon.com/resources/reports/dbir.

Security practitioners will often find that they need to justify security controls based on nonsecurity benefits as well, such as enhanced usability of a cloud-based system for a mobile or remote workforce.
In many cases, the end result of the cost-benefit analysis will be a presentation to management of various alternatives to mitigate, transfer, and ultimately accept residual risk, so the costs as well as any benefits resulting from controls must be clearly documented and communicated.


## ASSESS SECURITY IMPACT OF ACQUIRED SOFTWARE

### Commercial Off-the-Shelf

As the name implies, commercial off-the-shelf (COTS) software is readily available for sale to the public and may be purchased, licensed, or leased.
COTS can be expensive, but the expense is offset by the availability of support, a more robust feature set available from a dedicated vendor, or the speed at which the software can be deployed due to its design for specific use cases.

The most immediate security drawback of COTS software is the lack of visibility into the source code and development practices, and organizations using it have no ability to make direct changes — they may be able to request changes, but the vendor is not obliged to make them.
Most software vendors do not provide any visibility, though some share audit and assurance reports like code scanning or a certification like ISO 27001, which provides assurance over the vendor’s security program, or ISO 27034, which provides assurance over the vendor’s application security controls.

The US Cybersecurity & Infrastructure Security Agency (CISA) maintains a best practices guide for managing COTS software security: (www.us-cert.cisa.gov/bsi/articles/best-practices/legacy-systems/security-considerations-in-managing-cots-software).

Although cloud hosting and novel IT services like serverless and microservices architectures are increasingly adopted for modern information systems, the guidance provided in the COTS Security Considerations document is relevant to many organizations with legacy or on-prem hosted systems.
This includes the following:

* **Identifying why COTS is risky:**
Well-known and widely used software such as Microsoft Windows and Internet Information Services are also well known by threat actors.
Wide adoption of these systems increases the profitability of exploiting them since the pool of potential targets is bigger, and the software developer typically has limited liability in the event a flaw in their software leads to a security ncident.
A CISSP should be aware of the cost-benefit trade-offs of using COTS, which should be factored into organizational risk-based decisions such as build versus buy.

* **Common methods of attack:**
COTS software is often subject to malicious modification or interference like remote code execution (RCE) flaws or DOS attacks.
The black-box nature of the source code also means the COTS software may contain unwanted malware or functionality, which the organization is unable to identify through conventional means like SAST.

* **Standard risk assessment and mitigation strategies:**
Organizations using COTS software must have adequate risk management practices adapted to their use cases.
This includes compiling an accurate inventory of COTS software and components and identifying sources of information for vulnerabilities, such as vendor disclosures, penetration testing, and routine security reviews.
Defect prevention strategies during the SDLC are not an option, so mitigation must focus on corrective and compensating controls such as intrusion detection systems and network access controls.

### Open Source

Open-source software (OSS) is a category of software that, as the name implies, makes its source code freely available.
OSS is typically developed by a community for the benefit of all, allowing organizations to share and collaborate to improve the software while offering the benefit of source-code visibility.
Unlike COTS, all organizations using OSS can perform code testing to verify security, bugs, or unwanted functionality, and they can share fixes made to address security flaws back to the software project for the benefit of the community.

The community-driven approach of OSS has arguable security implications. On the one hand, the open nature means that bugs or flaws should eventually be caught, and the software is generally freely available for use.
On the other hand, the complexity of OSS projects, the technical skills required to use the software, and the lack of dedicated support can make them less attractive than COTS alternatives.

When evaluating OSS, there are a number of key concerns:

* **Performing sufficient evaluation:**
There is an assumption that with sufficient eyeballs on software code, all flaws will become apparent. This is true but leaves out one crucial element: time.
The Heartbleed bug existed in the OpenSSL for nearly five years before it was discovered, and the software is one of the most widely used on the internet.
Relying on testing and evaluation performed by untrusted outside parties can also lead to testing with insufficient coverage, differing objectives, or even results that are outdated or inaccurate if not performed by qualified testers.
Similarly, it may be possible for a system administrator to pull open-source software from a project repository and build a functional system from it without sufficient knowledge to review the code and find potential bugs.
Simply relying on the wisdom of the community or an administrator is insufficient.

* **Validate source code integrity:**
OSS repositories are typically configured for public visibility and contributions, meaning anybody can add, modify, or delete source code.
There have been multiple instances where OSS projects had malicious code inserted, as well as instances of prepackaged OSS being made available from inauthentic sources.
In both cases, unsuspecting users who downloaded and deployed the software got unwanted malware in addition to the legitimate software.
Always ensure you review the changes made to OSS to ensure they are expected and properly documented, and only download OSS from the legitimate, official repositories.

* **Look for commercial support:**
OSS is typically licensed for free use and distribution, which means organizations are also left to find their own support.
Companies such as Red Hat have sprung up by offering support for popular OSS like Linux, and the dedicated resources of such an arrangement have beneficial impacts on the overall quality and security of the OSS.
These firms may be able to attract dedicated talent to projects and also offer the benefit of contributing lessons learned from support back to the community in the form of documentation and code updates.

### Third-Party

Third-party software is developed under contract by a firm outside your organization’s direct control, and the resulting software is typically for your organization’s exclusive use.
The outside organization usually specializes in software development and has skills, resources, and knowledge that make them more proficient at software development.
This reduces project risks to the contracting organization from unfamiliar technology or lack of software development process maturity; lack of familiarity or maturity in development processes can also lead to less secure software development as developers are prone to make simple mistakes because they lack knowledge.
The more experienced, shared resources of the third-party development organization are less likely to make such mistakes, so the added cost of contracting is offset by decreased project and security risks.

As with all acquired software, there are risks inherent in giving up control of the software development process, and specialized mitigation strategies are required to enforce contracts, service-level agreements (SLAs), and additional acceptance testing to ensure the delivered software meets the organization’s requirements.
The use of a third party to develop software is a decision that should be made after a deliberate consideration of the costs and benefits.
Increased costs for high-quality development and project management oversight required may be justified by the quality or speed of delivery that a specialized third-party development firm can provide.

The availability of the source code itself is another important aspect of third-party software security to consider.
If the development organization goes out of business, the contracting organization may find itself without support for critical systems; code escrow is a contractual arrangement often used to prevent this eventuality.
The developing organization deposits a copy of the source code with a trusted third party, called an escrow agent.
The contracting organization can get access to the code under limited circumstances, such as the developer going out of business or breaching the contract, which enables continued support and development of the system.

### Managed Services (SaaS, IaaS, PaaS)

A combination of financial drivers and the availability of innovative services has driven organizations across all industries to adopt cloud computing.
Direct financial incentives like reducing costs for unneeded hardware or software capacity, as well as indirect incentives like secure remote accessibility to enable distributed teams, have combined to push many organizations to consume information systems as managed services.
These services are billed via metered consumption, which is often a pay-as-you-use model. Choosing the correct services will depend on an organization’s needs and technical abilities.

Widely agreed upon definitions of the various cloud service models are found in NIST SP 800-145, “The NIST Definition of Cloud Computing,” and are also covered in Chapter 3.
Emerging cloud services must be considered with respect to software security, including serverless and microservices architectures, which combine elements of managed software, infrastructure, and platform to enable faster deployment of code.
The choice of cloud services impacts the consumer’s software security assessment abilities and responsibilities.

#### Assessing Shared Responsibilities
The shared responsibility model defines a demarcation line between the cloud service provider (CSP) and cloud consumer with respect to handling various security tasks.
For example, in all service models, the CSP is responsible for physical security of the data center, while in all service models, the consumer retains legal liability and responsibility for safeguarding data placed in a cloud environment.

Other responsibilities vary depending on the service model chosen. For example, in Infrastructure as a Service (IaaS) the consumer is responsible for applying software patches to any software they deploy, while in SaaS, that responsibility falls to the CSP.

Software assessment responsibilities follow a similar split based on the service model:

* In all service models, it is the responsibility of the consumer to verify the CSP’s suitability for particular uses, like processing highly sensitive data.
The choice of a particular CSP or cloud deployment model will be informed by the level of control available when performing software assessment; for example, a private or community cloud will offer greater direct control over assessment than a large public CSP whose policies do not allow consumers to directly audit the service.

* In IaaS, the consumer will have the most flexibility to deploy software and therefore the most ability to perform software assessments.
IaaS offers building blocks of information system functionality, so assessment software security assessment will incorporate COTS, OSS, and third-party software as appropriate to the type of software the consumer deploys in the IaaS environment.

* In PaaS, some options are removed from the consumer’s control, so compensating processes like reviewing audit reports and SLAs for software assurance are needed.

* SaaS offers consumers the fewest options for directly assessing the security of software. However, given the shared nature of SaaS providers, there are often audit reports and robust control documentation available regarding the CSP’s software development, testing, and hosting security practices.

#### Audits and Assurance

As with all third-party and supply-chain security concerns, assurance is a key concept for managed software services.
Direct observation and control are not available, because the organization is not responsible for software development, so a trusted third party is often involved to perform an impartial review in the form of an audit.
This prevents the CSP from being subjected to constant review by consumers, while providing consumers with a trusted source of information on the design, implementation, and effectiveness of security controls.

There are multiple security and compliance frameworks related to cloud computing, and these are covered in detail in Chapter 6.
Frameworks like the Service Organization Controls (SOC), Cloud Security Alliance Security Trust Assurance and Risk (CSA STAR), and the ISO 27000 family (including ISO 27001, 27017, 27018, and 27034) all provide some assurance related to cloud services and applications.
Maturity or compliance with other frameworks like CMMI or BSIMM may also be reported by CSPs as a way of providing consumers with assurance that the software development and hosting practices of the CSP are robust and do not present unacceptable risks.

The benefit of so many organizations sharing the CSP’s resources is obvious: the CSP has a vested interest in providing the most robust security to ensure it retains these customers, and the pooled resources of so many consumers make robust security control and oversight programs financially feasible.
The downside, obviously, is that the consumers give up some measure of direct control over their risks.


## DEFINE AND APPLY SECURE CODING GUIDELINES AND STANDARDS

### Security Weaknesses and Vulnerabilities at the Source-Code Level

Weaknesses and vulnerabilities are closely related, but there is a nuanced difference between the two terms.
Vulnerabilities exist due to the presence of a software weakness such as a bug or flaw in the system’s source code, which may result from errors or incorrect design choices made when architecting, developing, and implementing the system.
Weaknesses can exist in a system with no practicable method of exploiting them, in which case they are not vulnerabilities; weaknesses can also impact nonsecurity aspects of a system, such as a poor database design that causes slow search performance.

As a CISSP, the distinction is important to recognize, as nonsecurity weaknesses may be addressed by other teams in the organization, while vulnerabilities are directly related to the security risk a CISSP is responsible for.

A vulnerability, by contrast, is the way in which a weakness could be exploited in a software system.
Nonsecurity weaknesses obviously are not exploitable, and some insecure source-code-level weaknesses may be compensated for by other parts of the overall system, such as an OS memory manager that prevents buffer overflow conditions otherwise allowed by poorly written source code.

This is one of the challenges presented in software security testing: if a source code weakness is not exploitable, the cost-benefit analysis of fixing the weakness may not support the effort and resources needed to fix it.
Definitively asserting a weakness is not exploitable can be difficult, so subjective measurements are used that are open to debate.

Vulnerabilities are typically tracked by the software in which they exist, and more specifically by the affected version, allowing organizations to determine if a vulnerability affects their systems.
Weaknesses and vulnerabilities are cataloged and scored using common systems to aid in identifying, communicating, and testing for them.
This tracking and scoring are useful for prioritizing fixes like patches or the deployment of compensating controls.

#### Common Weakness Enumeration

The Common Weakness Enumeration (CWE) is maintained by the Mitre Corporation in partnership with various U.S. government agencies including the Department of Homeland Security.
It is freely available and is integrated with security products such as scanning tools as a common way of identifying and reporting on potential weaknesses in information systems.

CWE is best defined on the Mitre website, cwe.mitre.org:

> CWE™ is a community-developed list of software and hardware weakness types.
  It serves as a common language, a measuring stick for security tools, and as a baseline for weakness identification, mitigation, and prevention efforts.

This community-developed list identifies common weaknesses in hardware, software source code, and implementations of software features that can lead to exploitable vulnerabilities.
Each CWE is given a unique identifier such as CWE-561: Dead Code, as well as the following:

* **Description, Extended Description:**
Details of the weakness and its effects. The description for CWE-561 is: “The software contains dead code, which can never be executed.” This is code that, when executed, skips over certain portions or never calls those functions, thereby preventing it from ever being run.

* **Relationships:**
Other types of related weaknesses, such as the high-level category of Bad Coding Practices.

* **Modes of Introduction, Applicable Platforms:**
This identifies when this weakness may be introduced to software by SDLC phase, which is useful when designing security controls to deploy in the SDLC. Applicable Platforms identifies what languages or systems are susceptible.
CWE-561 arises during the implementation phase and impacts all programming languages.

* **Common Consequences, Demonstrative Examples:**
These sections are self-explanatory. Consequences of dead code include the likelihood of unintended program behavior, since the function expected of the dead code will never be performed.
Demonstrative examples help software developers by showing example code demonstrating the weakness.

* **Observed Examples:**
If the weakness has led to an actual exploit, the relevant Common Vulnerabilities and Exposures (CVE) reference is included. CVEs are discussed in detail in the following section.

* **Potential Mitigations, Detection Methods:**
These categories are most useful for security practitioners, as they provide actionable guidance to detect and mitigate the weaknesses, such as static code analysis to detect dead code, and mitigation tactics.
In the case of CWE-561, the mitigation is deceptively simple: remove the dead code. However, if the dead code had an intended purpose, new code that does not exhibit the same weakness is required.

* **Miscellaneous metadata:**
CWEs contain additional metadata like ordinality, taxonomy, references, and version history of the weakness.

#### Common Weakness Scoring System

The Common Weakness Scoring System (CWSS) is an attempt to score weaknesses and determine a priority for addressing them based on the score.
This can help identify high-risk weaknesses that should be addressed first given limited time and may also be used to identify low-risk weaknesses that will not be addressed due to the costs required and small benefit achieved.

The CWSS score comprises an evaluation of several factors, which are organized into three groups: Base Finding, Attack Surface, and Environmental.
Each factor has values to account for uncertainty inherent in complex software projects, as well as the evolution over time of how much information is available about a weakness.

The factors are as follows:

* **Base Finding:**
This helps quantify results of a weakness being exploited. Metrics include the following: Technical Impact (TI), Acquired Privilege (AP), Acquired Privilege Layer (AL), Internal Control Effectiveness (IC), and Finding Confidence (FC).

* **Attack Surface:**
This provides an explanation of the factors needed to exploit the weakness. Metrics include Required Privilege (RP), Required Privilege Layer (RL), Access Vector (AV), Authentication Strength (AS), Level of Interaction (IN), and Deployment Scope (SC).

* **Environmental:**
This describes the impact and likelihood of exploiting the weakness. Metrics include Business Impact (BI), Likelihood of Discovery (DI), Likelihood of Exploit (EX), External Control Effectiveness (EC), and Prevalence (P).

Universal scores rarely provide enough context for an organization to use without modification, so the CWSS score may be a useful starting point to categorize weaknesses and then perform further analysis within your own organization to determine prioritization of fixes.
Full details of the CWSS are at cwe.mitre.org/cwss.

#### Common Vulnerabilities and Exposures

Similar to CWE, the Common Vulnerabilities and Exposures provides a consistent way to not only identify but also describe common cybersecurity vulnerabilities.
CVEs are often tied back to CWEs. For example, the “goto” fail vulnerability in Apple’s macOS and iOS (CVE-2014-1266) resulted from poor coding practices that lead to code never being executed, which is an example of the previously discussed CWE-561, Dead Code.

The CVE ID consists of two key pieces of information: the year in which the vulnerability was registered on the CVE list and a numeric ID.
Given the number of vulnerabilities disclosed each year, this prevents the ID from being too long to be useful. Note that the year indicates only when a formal entry on the CVE list was created, not when the vulnerability was discovered or reported.

CVE records include a description of the vulnerability with details like impacted software and versions, any versions that are not impacted, risks related to the vulnerability, and workarounds or fixes.
References are also provided, and they often consist of vendor-issued material like knowledge base articles or patching information, and links to relevant material about the discovery of the vulnerability.
Security researchers often publish the details of their research in blog posts, proof-of-concept code, and presentations, and the references typically contain these links as well.

The full list of all CVEs reported, which goes back to 1999, is available at cve.mitre.org/index.html.

#### Common Vulnerability Scoring System

CVEs are merely identifiers of a vulnerability and do not provide any useful way to identify high-priority vulnerabilities. The Common Vulnerability Scoring System (CVSS) provides that information, similar to CWSS.
Currently in version 3.1, CVSS provides context related to the impact and severity of each CVE. They are accessible in the National Vulnerability Database (NVD) maintained by NIST at nvd.nist.gov/vuln-metrics/cvss.

CVSS scores measure three categories of information related to each vulnerability, which are used to calculate three subscores that together comprise the overall CVSS score.

A CVSS vector is also created, which provides a text-based reference to the underlying vulnerability measurements, such as CVSS:3.1/AV:A/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N. This is made up of the scores on each metric, as detailed here:

* Base Score metrics are related to the exploitability and impact of a particular vulnerability and, once established, do not typically change.
Exploitability metrics include the Attack Vector (AV), Attack Complexity (AC), Privileges Required (PR), User Interaction (UI), and Scope (S). Impact metrics cover the standard security triad of Confidentiality (C), Integrity (I), and Availability (A).

* Temporal Score metrics capture how the risk of a particular vulnerability changes over time, which means this number also changes over time.
When a vulnerability is first discovered, it may be a highly manual process to exploit it, which is technically difficult and reduces risk, though organizations are unlikely to have patches in place to remediate, which increases the risk.
Over time, vulnerability exploitation is automated and included in tools like Metasploit, which increases the risk, but organizations also respond by patching, which decreases risk.
Metrics comprising the temporal score include Exploit Code Maturity (E), Remediation Level (RL), and Report Confidence (RC).

* Environmental Score metrics capture how a particular vulnerability impacts an individual organization.
A highly exploitable, high-impact vulnerability sounds drastic, but if an organization’s only system with that vulnerability is in a secure physical location and not connected to a network, the patching process is not an emergency that should interrupt all other work.

  Environmental score metrics modify metrics from the other categories and are subdivided into three groups:

  * Exploitability includes Attack Vector (MAV), Attack Complexity (MAC), Privileges Required (MPR), User Interaction (MUI), and Scope (MS).
  * Impact measures the specific effect of the vulnerability against the organization’s CIA triad, including Confidentiality Impact (MC), Integrity Impact (MI), and Availability Impact (MA).
  * Impact Subscore Modification modifies the Base Score impact metrics to tailor them to the organization’s specific CIA requirements, including Confidentiality Requirement (CR), Integrity Requirement (IR), and Availability Requirement (AR).

CVSS scores range from 0 to 10, with higher numbers denoting a more critical vulnerability that should be prioritized for fixing. A score of 0 is categorized None and is mainly informational.
A score between 0.1 and 3.9 is Low severity, between 4.0 and 6.9 is Medium severity, between 7.0 and 8.9 is High severity, and a score between 9.0 and 10 is Critical.

Security practitioners can monitor the NVD and use the CVSS calculators to determine the environmental scores of specific vulnerabilities to prioritize remediation activities.
As an example, the previously discussed Apple “goto” fail vulnerability, CVE-201401266, had a score of 5.8 resulting from the high impact of a loss of confidentiality due to no encryption, while also considering the limited likelihood as the software flaw did not always cause a loss of encryption.

#### OWASP Top 10

The Open Web Application Security Project (OWASP) is a community-driven effort that originally started to share knowledge and develop best practices around web application development.
It has since expanded in scope to include other application types, such as mobile apps, driven mainly by the increased prevalence of applications that rely on system components or services accessed over the internet and the wide variety of languages that are used for both web and traditional desktop apps.

One of OWASP’s most visible projects is the Top Ten, which is a compilation of the 10 most commonly seen vulnerabilities in web applications (owasp.org/www-project-top-ten/).

Note the Top Ten list is not a collection of discrete vulnerability identifiers like CVE, nor is it a scoring/prioritization system like the CVSS.
Instead, it provides guidance to developers, QA and testing practitioners, and security practitioners to help them identify common vulnerabilities and attempt to avoid them when programming or catch them with testing and security monitoring.

The vulnerabilities on the list are identified by a numeric identifier and the year they appeared on the list, which was last updated in 2017.
Each vulnerability is also broken down into the threat agents and/or attack vectors likely to exploit it, the security weakness posed by the vulnerability, and the impact an exploitation of the vulnerability is likely to cause.

The current list includes the following:

* **A1:2017-Injection:**
Injection is the unwanted insertion of code through channels not intended for code, like data form fields on a web page. If an attacker enters a SQL code statement rather than an account number in a data field, this value may be passed to an application that executes the SQL.

* **A2:2017-Broken Authentication:**
Authentication is a key pillar of access control, so if users are able to bypass or break the authentication, they are likely to gain unauthorized access. This vulnerability can include credential stuffing attacks against applications as well as session hijacking attacks.

* **A3:2017-Sensitive Data Exposure:**
This vulnerability is quite simple. Application flaws may expose sensitive data to unauthorized users, such as by including it in error messages. This can also be a secondary effect of an application with broken authentication.

* **A4:2017-XML External Entities (XXE):**
This is a highly technical vulnerability related to improper handling of user-supplied XML.
Rather than just expected data, the XML may include references to external entities like files or storage locations, which causes the application to execute unwanted remote code or load malicious data from the external storage location.
This is due to the vulnerable functioning of the XML processor, which must accept and process untrusted data.

* **A5:2017-Broken Access Control:**
This one is also self-explanatory, though it can be easily confused with A2.
Vulnerabilities that fall into this category include bypassing access controls by modifying a URL to gain access to unauthorized resources, replay attacks like sending the same session credentials, or improper granularity of access control within an application.

* **A6:2017-Security Misconfiguration:**
Misconfigurations are often the biggest category due to the complexity of modern software environments. Ensuring the correct parameters are set, boxes are checked, and services are configured is error prone.
A web server with unwanted support for outdated Secure Sockets Layer (SSL) or TLS versions is an example of a misconfiguration.

* **A7:2017-Cross-Site Scripting (XSS):**
XSS exploits the dynamic and remote nature of web applications, which are designed to accept and execute remote code like JavaScript.
An application vulnerable to XSS may load untrusted or unsanitized data from a remote source and execute any code it contains, allowing a remote attacker to perform unwanted actions in the user’s browser like redirecting them to malicious sites, reading data, or even hijacking a user’s session with a secure site.

* **A8:2017-Insecure Deserialization:**
This is another complex technical vulnerability. Data is serialized by transforming it into a common format to be embedded into a communications stream, like data being structured using JSON and sent over the internet.
The receiving system then deserializes the data and translates it into a format that the recipient software can understand. Insecure deserialization, like executing code embedded in the deserialized data, may lead to unwanted or unauthorized application behavior.

* **A9:2017-Using Components with Known Vulnerabilities:**
Modern programs are rarely created entirely by a single entity. Developers rely on libraries and open-source modules, which make software delivery faster, more efficient, and more secure.
However, components like web servers, code libraries, and other dependencies can introduce vulnerabilities.
An otherwise secure application could be compromised if an external library used to format data has a flaw, similar to building an entirely secure house but putting a lock that can be easily bypassed on the front door.

* **A10:2017-Insufficient Logging & Monitoring:**
This is another human factor in software security and is similar to misconfigurations. Applications without sufficient monitoring or logging capabilities in place simply do not support incident detection and response.
If an incident occurs on a system but no alert is generated, no security countermeasures will be deployed.
Similarly, an incident without any data to support investigation and recovery is unlikely to be dealt with effectively due to the lack of intelligence available to the security responders.

Each of the vulnerabilities on the Top Ten list are presented with tips and guidance on how to prevent them, such as using code frameworks that automatically implement anti-XSS or implementing repeatable and audited hardening procedures to avoid and correct security misconfigurations.
These should be incorporated into security and awareness materials in the organization, specifically for developers working on applications and security practitioners with responsibility for access controls, configuration management, and application security.

#### Software Composition Analysis

##### Benefits of FOSS

One emerging area of security concern is the increasing use of open-source components, libraries, and modules in modern programs. These show up even in custom-developed applications, and their use is directly related to Top 10 item A9:2017-Using Components with Known Vulnerabilities.
These components are often known as free and open-source software (FOSS) dependencies and bring obvious benefits such as faster development and increased reliability if well-known components are used.
FOSS means that these software components can be used at no charge, and the code is open for inspection or modification.

##### Drawbacks of FOSS

There is a security drawback, however: if a dependency has a flaw or bug, the resulting application will also be vulnerable.
This mirrors the complexity of systems reliant on underlying architecture, such as a web application that is also subject to vulnerabilities in its underlying web server and OS software.

An OWASP presentation given in 2019 found that the percentage of FOSS components in applications increased from around 10 percent in 1998 to 90 percent in 2019, but many organizations struggled to reckon with the security implications of these FOSS components (wiki.owasp.org/images/b/bd/Software_Composition_Analysis_OWASP_Stammtisch_-Stanislav_Sivak.pdf).
Asset inventories should capture all elements of a system, such as underlying OSs and hardware, and this inventory is a key input to the vulnerability and patch management process.
However, the practice of inventorying and analyzing dependencies for flaws had not kept pace to address their rising usage.

##### Software Composition Analysis (SCA)

Software composition analysis (SCA) is a security practice specifically designed to address FOSS component vulnerabilities and their impact on software.
There are a number of tool vendors and approaches, but most include basic functionality to create an inventory of all dependencies and identify vulnerabilities they contain.
Open-source projects often publish security notices or include release notes or documentation addressing remediated vulnerabilities with updates, which an SCA tool can use to continuously identify vulnerabilities in an application using that component.
This process is similar to OS vendors publishing notes about vulnerabilities and updates.

##### Remediation

Once a vulnerability has been identified in a dependency, the remediation step is usually to apply an update. In some cases, the FOSS flaw does not translate to a vulnerability in a given system dependent on that component, so no action is required.
Alternatively, the organization may need to iterate the SDLC in response to changes in the component’s functionality as a result of the flaw.

DevOps and DevSecOps practices can also be utilized to address these flaws, such as CI/CD pipelines that incorporate automatic checks and incorporate the latest update dependencies when building an application.
This is the equivalent of automatic patch deployment and can automate vulnerability remediation, though sometimes at the expense of availability if a patch breaks functionality.

### Security of Application Programming Interfaces

An API provides standardized access to the features of a system without the need to understand its inner workings. Features that are accessible through an API are often referred to as being exposed via API, meaning they can be called using standardized methods such as HTTP requests.
Representation state transfer or REST APIs expose functions using URLs similar to web applications and accept commands using common HTTP verbs like GET and POST for retrieving or sending data to the API.
Rather than creating a custom communication scheme for each application, the use of a REST API allows other programs to interact using these commonly understood protocols.

APIs are a form of modular software development, and modern application architectures often rely on APIs to send data between functions, modules, or tiers of complex systems.
There are other forms of APIs as well, including internal software APIs in modern OSs for access to generic system functions like creating interactive windows in a user interface, simple object access protocol (SOAP) APIs designed for exchanging messages between system components, and RPC APIs that are used for executing functions across nodes in distributed systems.
Most cloud services are built on an API foundation, with tasks such as cloud environment administrative, data handling, and services like data storage buckets and machine learning models exposed to users via URLs, commonly known as API endpoints.

APIs function much the same as web applications, and the security requirements are often similar for both. The first and most obvious step is to understand the risks facing a particular system and its API.
Is it a publicly accessible API that grants access to read or update sensitive information? Such an API would obviously face high risks against confidentiality and integrity and should implement appropriate security controls to ensure information is not read or altered by unauthorized users or programs via the API.
Is the API read-only access to public information like weather data? In this case, confidentiality and access controls are unlikely to be a high priority.

### API Security Best Practices

API security guidelines and standards are similar to secure coding guidelines and standards, though they are slightly less mature since APIs are a newer concept.
OWASP publishes a number of freely available resources on API security, including a cheat sheet for REST APIs (cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html) and an API Security Top 10 list detailing common vulnerabilities and issues facing API security (owasp.org/www-project-api-security).

In addition to OWASP’s guidance, there are a number of key practices to keep in mind when building and security systems with APIs to handle data. Although similar to security requirements for web applications, the extensive use of APIs for system-to-system interactions rather than human interfaces does present unique challenges.

#### Authentication and Access Control

APIs typically do not utilize the same combination of username and password that a web application uses, but the goals of authenticating the user of an API, called a consumer, are still the same.
The consumer must prove their identity and should only be granted access to appropriate resources based on that identity.

Authentication can be done in a number of ways, each with various advantages:

* **Basic authentication** utilizes a simple authentication scheme that is part of the HTTP protocol and sends a username:password string encoded in base64. Since this is not a form of encryption, this form of authentication method should never be used alone.
Stronger authentication methods are preferred, but if basic authentication must be used, the communication channel requires protection, such as TLS encryption.

* **Key-based authentication** serves dual purposes. A secret, shared symmetric key is used to encrypt data being passed. If the recipient can decrypt the data with a secret key associated with a unique identity, then the sender’s identity can be authenticated, and the data is also protected in transit.
Many applications with APIs allow users to log into a secure web application to retrieve the API key needed for encryption and authentication, providing an out-of-bound channel for key distribution.

* **Certificate-based authentication**, as the name implies, relies on authenticating an identity using digital certificates. This can be one-way, in which only one party provides a certificate asserting an identity, or mutual authentication where both parties exchange certificates and validate them.
This obviously requires a Public Key Infrastructure (PKI) in place, meaning this may not be a valid choice for all situations.

* **Federated and single sign-on authentication** relies on another organization’s identity and access management (IDAM) tools to control access. Technologies like security assertion markup language (SAML) and Oauth can be used to federate, or combine, IDAM capabilities across organizations.
API security can rely on these federations to delegate access control decisions; rather than the API provider enforcing access controls, consumers grant permissions to their users and then pass relevant authentication and access control information via SAML statements or Oauth assertions.

Access control must be implemented for authenticated consumers. There are a variety of methods for implementing this, similar to controlling access for users in an application, such as role-based access control, access control lists, and the like.
When designing systems with APIs, care must be taken to ensure adequately granular access controls are available to restrict access to data and functions, whether access is requested by an individual user of a web app or a consuming system via an API.

#### Input Validation and Sanitization

Whenever data is supplied by an outside system or user, it should be considered untrusted and treated appropriately. This can avoid unwanted application behavior like code injection attacks and may also be implemented as a control for data integrity.
The API layer of an application is a key control point as it accepts and processes untrusted data supplied by external users or systems.

##### Escaping Content

Escaping content places characters around it to explicitly denote it as data and not code; this is a form of input sanitization, where the supplied data is rendered harmless, and is a safeguard against injection attacks.
The configurations, characters, and methods used for escaping content vary between languages and technologies, so input validation must be documented as a requirement and appropriate design decisions made to enable it.

The OWASP SQL Injection Cheat Sheet provides examples of various escaping strategies: cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html.

Input validation checks should be implemented at the API layer to validate the incoming data matches expectations.

##### Syntactic and Semantic Validation

Syntactic validation enforces correct syntax of data, for example, a U.S.-formatted phone number should consist of 10 digits grouped nnn-nnn-nnnn, and semantic validation, which enforces correct values; for example, “555” is not a valid area code in the U.S. calling system and should be rejected as an invalid phone number.
A phone number in Zimbabwe, by contrast, should consist of a proper area code, prefixing number, and subscriber number such as (027) 2317555, which requires different application logic to perform semantic validation.

Performing syntactic and semantic validation can help avoid data integrity issues and unwanted system behavior due to unexpected values, while semantic validation can also help identify unwanted content like SQL statements in a field such as Last_Name where a simple text string is expected.

Unfortunately, semantic validation is extremely difficult, as the various combinations of human language make it tough to write the rules needed to check. For example, the ' character has special meaning in SQL and could be an unwanted character in a name field, but rejecting it would cause common names like O’Brian to be rejected.
As a result, escaping content is considered a better safeguard against injection attacks, while semantic validation is generally more useful for data integrity. The OWASP Input Validation Cheat Sheet provides a comprehensive resource on validation strategies: cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html.

#### Protection of Resources

APIs must be designed with the same level of rigor applied to user access management to ensure the functionality exposed cannot be exploited to attack the system’s confidentiality, integrity, or availability.
This is a broad category of security concern but one that is often overlooked since APIs are typically designed for system-to-system communication or for privileged access, and the possibility of their use in an attack is not considered during threat modeling.

Take, for example, the Facebook developer API, which offered a “View As” feature designed to let developers see a Facebook profile as if they were a particular user.
Rather than just showing the profile, the API also delivered a user authentication token, which allowed hackers to access Facebook with that user’s credentials.
Since developers are considered trusted users, the level of rigor applied to testing this functionality was obviously not sufficient, or it was assumed that nondevelopers would not be able to access the feature for malicious uses.
Facebook has since changed the behavior of this API to prevent this unintended behavior.

#### Protecting Communications

Web applications and other communications implement protections like TLS for encrypting data in transit, and API access should be no different.
Luckily, encryption serves multiple purposes — symmetric key-based authentication not only can verify a user’s identity but also provide security of data in transit, as can certificate-based authentication where a public key can be used either for encryption of data or for a session key.

The use of standard web protocols is a benefit of REST APIs, as they utilize HTTPS with little developer effort.
The level of communications security required should of course be driven by the sensitivity level of the data — public data may need only integrity validation, while highly sensitive information should implement strong encryption for confidentiality and hashing for integrity.

#### Cryptography

Cryptography is covered in detail in Domain 3 and can be used for a number of security functions. As a general best practice, cryptographic modules that are trusted, tested, or validated are preferred custom-built cryptography.
When applied to APIs, cryptography can provide the following:

* **Confidentiality:**
As discussed previously, both symmetric and asymmetric keys can be used, depending on the system requirements. A key design choice that must be made is when to encrypt data, as it can be encrypted prior to transport or utilize secure communications channels.

* **Integrity:**
Hash functions should be applied whenever the integrity of data being accepted through an API needs to be validated.

* **Authenticity:**
Proving the authenticity of data often relies on proving that the parties in communication are the legitimate sender and recipient. Strategies such as Hashed Message Authentication Code (HMAC) can be used to verify that the communications partners are still the intended parties.

* **Nonrepudiation:**
Proving the source of data or the identity of a system actor rests on identifying the holder of keying material. For example, if Alice can decrypt data using a secret key shared only with Bob or with Bob’s public asymmetric key, she can reliably assume Bob sent the data in question.

* **Access control:**
Access to encrypted data relies on decrypting it, so by extension, controlling access to the key controls access to the data. In the case of symmetric keys, this involves implementing secure distribution and management mechanisms for the encryption keys.
For asymmetric encryption, it involves the choice of which key is used to encrypt data. Using a sender’s private key will allow anybody to decrypt the data with the corresponding public key, which proves authenticity but provides no confidentiality.
Using a recipient’s public key to encrypt data provides confidentiality because only the recipient’s private key can decrypt it, but without proof of the sender’s identity since the public key is widely available.

#### Security Logging, Monitoring, and Alerting

System actions performed via API must be part of a logging and monitoring strategy to verify that system usage via the API meets security requirements.
Actions to be logged might include successful or unsuccessful authentication of an API consumer, results of input validation against supplied data, and details of API connections including the sender’s IP address and timestamp.
The events to be logged should be determined by the system’s requirements for both operational and security monitoring. Major cloud service providers offer API gateways that provide functions to secure and monitor custom-developed APIs hosted on the CSP’s infrastructure, including logging access and forwarding logs to a customer’s SIEM.

Logs are made meaningful by reviewing them, so they must be either reviewed by a person or ingested into a log monitoring tool like a SIEM that automates the process, depending on the organizaiton’s monitoring strategy and resources.
Events that violate security constraints or indicate operational issues should generate alerts to invoke processes like incident response to investigate.
Where possible, log data from multiple sources should be correlated to provide investigators with a holistic view of the incident, like network device logs showing traffic, application logs showing API access and use, and even, possibly, external data such as known malicious IP addresses that can be used to determine whether a security incident is a malicious attack.

#### Security Testing APIs

As with all system functionality, APIs must be tested to verify they meet security, performance, and user requirements. All the testing methods and considerations presented in Domain 6 apply to APIs, such as designing a testing strategy with appropriate depth and coverage as indicated by the API’s risk profile.
An internal API used to exchange financial data between departments without any public access should not be scheduled for a pentest before undergoing functional testing to ensure proper data integrity, since the risk to integrity is greater than the risk of breaching confidentiality.

There are a number of API security tools available to design and test APIs. The choice of a tool and associated testing strategy should be driven by the technologies in use, such as SOAP or REST, the sensitivity level of data being handled by the API, and the features exposed by the API.
OWASP also has a dedicated API security project, which contains resources such as a Security Top 10 and planned cheat sheet for API security, available at owasp.org/www-project-api-security.

### Secure Coding Practices

Secure coding practices comprise the entirety of actions taken during software and systems development processes. Nonexistent, disorganized, or poorly understood organizational practices tend to produce software and systems with flaws or bugs, which in turn become weaknesses and vulnerabilities.
Standardized secure coding practices that are well-documented, disseminated to all stakeholders, and applied effectively throughout the organization can increase the quality of development projects.
This leads to software and system development processes that seek to minimize flaws and bugs, as well as testing and monitoring processes designed to catch and fix vulnerabilities as soon as possible.
Although a CISSP may not be directly involved with the daily use of secure coding standards, they play a crucial role in defining requirements for such practices and validating organizational practices designed to meet these requirements.

#### Standards for Secure Software Development

As with many practices in software security, there are well-regarded standards available that bring together common knowledge and conventions related to secure coding and development.
Remember that no standard is a guaranteed match for every organization, so these should be used as starting points from which organizations can develop and implement their own practices, in a process known as tailoring.

The OWASP project contains a multitude of resources for secure coding practices. The Cheat Sheet Series (owasp.org/www-project-cheat-sheets) is an entirely library of guidance on secure practices, such as the following:

* Implementing authentication and access controls
* Preventing common vulnerabilities and attacks like XSS and injection
* Architectural security for technologies like microservices, REST APIs, and SAML
* Technology-specific security guidance including XML, HTML5, Docker, and Kubernetes

A technology-neutral OWASP Secure Coding Practices Quick Reference Guide (owasp.org/www-pdf-archive/OWASP_SCP_Quick_Reference_Guide_v2.pdf) is also available and provides recommendations and best practices across a set of common development activities.
Although primarily written for web and mobile apps, the guidance is broadly applicable to almost any application and system architecture.
Each category contains key focus areas for secure coding practices, and these practices can be used to guide the development and implementation of organization-specific practices tailored to your unique technology stack, programming languages, and security requirements.

There are 13 categories, each of which contain a checklist of common practices, covering the following:

* Input validation
* Output encoding
* Authentication and password management
* Session management
* Access control
* Cryptographic practices
* Error handling and logging
* Communication security
* System configuration
* Database security
* File management
* Memory management
* General coding practices

The Carnegie Mellon University Software Engineering Institute (CMU SEI) publishes guides covering both secure coding practices as well as secure coding standards.
The Top 10 Secure Coding Practices, which actually contains two bonus practices, is a very high-level set of principles for implementing secure coding like using input validation and following the “keep it simple” rule.
The Coding Standards are a set of publications designed to provide standards for secure software development in specific languages including C/C++, Android, and Perl. While not entirely focused on security, they do cover best practices for each language and include some security-specific guidance.
These documents and others related to secure coding can be found at the CMU SEI CERT Secure Coding wiki at wiki.sei.cmu.edu/confluence/display/seccode/SEI+CERT+Coding+Standards.

#### Education and Culture

Documentation alone is not enough to solve security problems; the daily activities of all members in the organization must follow the guidance laid out in policies, standards, and procedures.
This is the essence of building a security culture, in which all stakeholders understand, support, and actively carry out security efforts, and it is essential that this is widely adopted across the organization, since cybersecurity is a broad discipline underpinning any process that relies on data and information systems.
Building security culture obviously encompasses more than just software and system development, but these activities are especially important given their pivotal role in designing secure systems.

Security culture begins with clear and effective policies and other documentation that provides clear guidance to members of the organization on their security roles and responsibilities.
Reading policy documents alone is not sufficient, as many security policies will deal with or include concepts that are not familiar to all.
While the documentation should be clear enough for broad consumption, additional documentation like procedures, guidelines, standards, and checklists must be created to provide specific guidance to different stakeholders.

For example, a policy describing the desired levels of entropy in password construction is no doubt thorough, but the majority of users in the organization are unlikely to know what entropy is.
A password section of the acceptable use policy written in plain language, supplemented with training, education, and awareness materials on secure password practices, is a much more suitable way to communicate this requirement.

Incorporating security objectives into organizational goals and priorities and promoting engagement with security are also essential.
One crucial element of a security culture is the set of principles it is built on, and the foundational role played by software development means a number of key principles must be considered in order to create a successful security culture.

These principles include the following:

* **Secure by design:**
This principle largely stems from a paradigm shift as the field of software engineering matured and decisions that led to insecure technologies like DNS and SNMP were examined in light of modern information security risks.
Rather than attempting to retrofit security after deployment, this principle espouses practices that require the inclusion of security at the outset of a system: in the design phase.
Anticipating that the system will come under attack drives design and implementation decisions that provide inherent security abilities, rather than relying on more expensive and error-prone compensating controls.

* **Secure by default:**
This principle is a collection of best practices for delivering more secure software, such as the inclusion of layered security controls and conservative default settings designed for security.
Many data breaches share the underlying root cause of improperly secured cloud storage services exposing data to the public. In a secure by default configuration, those services should be private by default and require extra steps be taken to turn on public access.

* **DevSecOps:**
Although not strictly a security principle, one of the foundational ideas of DevSecOps is to shift security “to the left” — in other words, to push security activities earlier in the software development lifecycle rather than developing security strategies only after a system is built and deployed.
Implementing DevSecOps in an organization is, fundamentally, an opportunity to build a culture of security and deliver higher quality software.

* **Build security in:**
SAMM and BSIMM were discussed earlier in this chapter and represent a set of practices and principles that can be used to drive enterprise change to a culture of security.
The maturity model supports this by providing a convenient measure of the organization’s current state, metrics to track progress toward a desired future state, and a set of practices to implement to mature the secure software development capability.

### Software-Defined Security

The world of technology is rapidly evolving to software-defined replacements for systems that previously required a combination of physical hardware and software.
For example, software-defined networking (SDN) abstracts physical networking gear and software configurations into purely software-configurable virtual networks that can be reconfigured with far less effort than their hardware-based equivalents.
Cloud services also make use of software-defined infrastructure in the form of virtualization, with common infrastructure elements such as server and networking hardware replaced by more flexible software-only equivalents.

Software-defined security, sometimes abbreviated SDS or SDSec, mirrors this trend to create virtualized, software-controlled security infrastructure.
It extends concepts like virtualized infrastructure configuration via definition files, as well as leveraging SDN to provide easy reconfiguration of network functions, routes, and protection mechanisms.
Provisioning, monitoring, and management of security functions can be extensively automated and controlled via software configuration, which replaces previously manual, human-driven processes.
Deploying SDS represents an evolution of security architecture to support more targeted and flexible controls. It also accounts for new application and system architectures that do away with traditional designs due to novel services available in cloud computing.

Consider, for example, a legacy application that comprises three tiers: a web server, a business logic server, and a database server.
Each has traditional security tools installed like anti-malware, file integrity monitoring, IDS/IPS, etc., and is hosted in a data center with traditional perimeter controls like a firewall.
A modern application, by contrast, may comprise a web server delivering a browser-based application to users, whose actions create API calls to a set of microservices for specific tasks like processing data, which in turn involves API calls to a cloud-hosted database.

All of these system elements are also geographically disbursed and configured for high availability, so user requests may be processed in data centers all over the world with different hardware and software configurations.
There is no traditional perimeter, and the business logic and database cannot be monitored with traditional tools. The microservices don’t exist on a traditional server, and the cloud-hosted database server is not under the purview of the organization’s security program.

In this new paradigm, SDS can achieve a number of security goals and offers several important advantages:

* **Enhanced availability:**
Implementing security controls requires an element of determinism; for example, deploying a firewall requires the practitioner to know data will be flowing between two points, and the firewall is placed in the middle.
If a different communications channel is used, the firewall’s protection is rendered moot. Dynamic and geographically distributed cloud applications make this task difficult with traditional security, but an SDS paradigm can be used to ensure security controls follow the data.
Software definition files are easily portable, so it is possible to ensure a new virtual server will have the same configuration and protections regardless of its location. Increased security tool flexibility allows organizations to take advantage of high availability in cloud environments.

* **Infrastructure neutrality:**
Security controls often require administrators with system-specific configuration and administrative knowledge. SDS allows for a generic definition to be interpreted as appropriate for underlying system and for the process to be automated.
For example, an encryption setting of “AES with minimum 256-bit key length” can be interpreted by a virtualization server and appropriately applied to all new servers regardless of the host OS being deployed.
This is similar to the interpreted code paradigm, which allows for write-once, run-anywhere portability. SDS definitions also support increased configuration reliability and consistent application of security policy, similar to using standard configuration files rather than relying on manual build processes.

* **Micro-targeting:**
Security tools are often blunt and lack adequate granularity for enforcing controls, which requires trade-offs or compensating controls.
This is especially apparent in network segmentation, which is covered in Domain 4, “Communication and Network Security,” and it is a problem solved by the micro-segmentation that SDNs enable.
Rather than requiring a balance between protection of individual hosts and network administration overhead, individual hosts automatically receive appropriate firewall rules applied based on purpose-driven templates.
Other security tool deployment and configurations can be similarly automated, such as IDS with rules appropriate for the server’s function, or encryption configuration based on the classification label applied to the system.
This granularity avoids trade-offs between management overhead and insufficient granularity of controls.

* **Centralized management:**
Many security tools are platform- or technology-specific, and they tend to be siloed along these lines. SDS enables centralized management and oversight by abstracting security control details away from the infrastructure and associated management tools.
SDS enables security practitioners to see a consolidated view of access control policies and control implementations, while system administrators are still able to perform their tasks in system-specific tools like Active Directory or an LDAP server.

* **Standardization, integrations, and automation:**
Standardization and integrations are key to enabling the features of SDS discussed here. Definition files are written in standard formats such as YAML, which alternatively stands for Yet Another Markup Language or the recursive YAML Ain’t Markup Language.
These can be interpreted by various cloud providers, systems, or platforms to enforce the desired security configurations appropriate to the infrastructure. This standardization, coupled with integrations between infrastructure and security components like cloud services and SOAR tools, enables automated security control deployment, enforcement, and reconfiguration.

* **Dynamic response:**
Security controls can proactively reduce the likelihood of a risk or reactively reduce the impact of a risk after it is realized. SDS incorporates and extends automated capabilities from SOAR to enable faster response times.
Restricting the time an attacker has to move laterally from a compromised server to other hosts reduces their chances of successful malicious activity.
Dynamic response leverages the ease of reconfiguring virtualized software infrastructure to speed up the response, and the use of orchestration and automation capabilities means intelligence from an incident can be used to automatically deploy proactive mitigations to other hosts and systems.
Tools with these capabilities are often described as self-healing, though it is important to note that security practitioners must still maintain vigilance and perform some actions manually.

Just as cloud service providers have made enterprise-grade infrastructure available to a broader audience, SDS can deliver greater security capabilities to organizations with limited resources.
Integrations with common systems and platforms coupled with automation require fewer time and security practitioner resources and can free up existing personnel to focus on other concerns.
SDS may be the only option in some cases where legacy security tools are not compatible with novel architectures and technologies like microservices, where software agents cannot be deployed for monitoring.

Microsoft published a document outlining its shift away from traditional perimeter-based security and legacy tools to SDS.
The change is driven in part by the move to a cloud-first IT infrastructure, and the document lays out the strategy behind the change; it can be read here: microsoft.com/en-us/itshowcase/designing-a-software-defined-strategy-for-securing-the-microsoft-network.
