# Security and Risk Management

## (ISC)2 Code of Professional Ethics

### Code of Ethics Preamble

* The safety and welfare of society and the common good, duty to our principals, and to each other requires that we adhere, and be seen to adhere, to the highest ethical standards of behavior.
* Therefore, strict adherence to this Code is a condition of certification.

### Code of Ethics Canons

* I. Protect society, the common good, necessary public trust and confidence, and the infrastructure. Security professionals have great social responsibility. We are charged with the burden of ensuring that our actions benefit the common good.
* II. Act honorably, honestly, justly, responsibly, and legally. Integrity is essential to the conduct of our duties. We cannot carry out our duties effectively if others within our organization, the security community, or the general public have doubts about the accuracy of the guidance we provide or the motives behind our actions.
* III. Provide diligent and competent service to principals. Although we have responsibilities to society as a whole, we also have specific responsibilities to those who have hired us to protect their infrastructure. We must ensure that we are in a position to provide unbiased, competent service to our organization.
* IV. Advance and protect the profession. Our chosen profession changes on a continuous basis. As security professionals, we must ensure that our knowledge remains current and that we contribute our own knowledge to the community's common body of knowledge.


### Code of Ethics Complaints

* Any member of the general public may file a complaint involving canons I or II.
* Only an employer or someone with a contracting relationship with the individual may file a complaint under canon III.
* Other professionals may file a complaint under canon IV. It is important to note that this is not limited to cybersecurity professionals. Anyone who is certified or licensed as a professional and subscribes to a code of ethics as part of that licensure or certification is eligible to file a canon IV complaint.


## Ethics and the Internet

### RFC 1087 - Ethics and the Internet

Issued by the Internet Activities Board (IAB) in 1989

RFC 1087 states that any activity with the following purposes is unacceptable and unethical:
* Seeks to gain unauthorized access to the resources of the internet
* Disrupts the intended use of the internet
* Wastes resources (people, capacity, computer) through such actions
* Destroys the integrity of computer-based information
* Compromises the privacy of users

### Ten Commandments of Computer Ethics

Issued by the Computer Ethics Institute (CEI) in 1992

1. Thou shalt not use a computer to harm other people.
2. Thou shalt not interfere with other people's computer work.
3. Thou shalt not snoop around in other people's computer files.
4. Thou shalt not use a computer to steal.
5. Thou shalt not use a computer to bear false witness.
6. Thou shalt not copy proprietary software for which you have not paid.
7. Thou shalt not use other people's computer resources without authorization or proper compensation.
8. Thou shalt not appropriate other people's intellectual output.
9. Thou shalt think about the social consequences of the program you are writing or the system you are designing.
10. Thou shalt always use a computer in ways that ensure consideration and respect for your fellow humans.

### Code of Fair Information Practices

Issued by the U.S. Department of Health, Education, and Welfare (HEW) in 1973

1. There must be no personal data record-keeping systems whose very existence is secret.
2. There must be a way for a person to find out what information about the person is in a record and how it is used.
3. There must be a way for a person to prevent information about the person that was obtained for one purpose from being used or made available for other purposes without the person's consent.
4. There must be a way for a person to correct or amend a record of identifiable information about the person.
5. Any organization creating, maintaining, using, or disseminating records of identifiable personal data must assure the reliability of the data for their intended use and must take precautions to prevent misuses of the data.


## DETERMINE COMPLIANCE AND OTHER REQUIREMENTS

### Legislative and Regulatory Requirements

#### U.S. Computer Security Act of 1987
Enacted by the U.S. Congress in 1987 with the objective of improving the security and privacy of sensitive information stored on U.S. federal government computers.

#### U.S. Federal Information Security Management Act (FISMA) of 2002
Enacted by the U.S. Congress in 2002 that greatly extends the Computer Security Act of 1987.  
FISMA acknowledges the importance of information security to the United States' economic and national security interests and requires that all U.S. federal government agencies and nongovernment organizations that provide information services to these agencies conduct risk-based security assessments that align with the NIST Risk Management Framework (RMF).

### Industry Standards and Other Compliance Requirements

#### U.S. Sarbanes–Oxley Act of 2002 (SOX)
Enacted by the U.S. Congress in 2002 to protect investors from fraudulent accounting activities by corporations.


#### System and Organization Controls (SOC, a.k.a. Service Organization Controls)
Released by the American Institute of Certified Public Accountants (AICPA) in 2011 to replace the SAS 70 audit standard.
The Statement on Standards for Attestation Engagements document 18 (SSAE 18), titled Reporting on Controls, provides a common standard to be used by auditors performing assessments of service organizations with the intent of allowing the organization to conduct an external assessment instead of multiple third-party assessments and then sharing the resulting report with customers and potential customers.
Outside of the United States, similar engagements are conducted under the International Standard for Attestation Engagements (ISAE) 3402, Assurance Reports on Controls at a Service Organization.


##### 3 Forms
* SOC 1: An audit and compliance report that focuses strictly on a company's financial statements and controls that can impact a customer's financial statements. A company that performs credit card processing is likely to require a SOC 1 audit and compliance report.
* SOC 2: An audit and compliance report that evaluates an organization based on AICPA's five “Trust Services principles”: privacy, security, availability, processing integrity, and confidentiality. Many organizations undergo SOC 2 auditing and present a SOC 2 report to regulators and customers to demonstrate compliance with industry standard security controls.
  * Privacy
  * Security
  * Availability
  * Processing integrity
  * Confidentiality
* SOC 3: This is a “lite” version of a SOC 2 report and abstracts or removes all sensitive details. A SOC 3 report generally indicates whether an organization has demonstrated each of the five Trust Services principles without disclosing specifics (like exactly what they do or don't do). Companies make SOC 3 reports available to the public and restrict SOC 2 reports to trusted parties.

##### 2 Types of Reports
* Type I Reports These reports provide the auditor's opinion on the description provided by management and the suitability of the design of the controls. Type I reports also cover only a specific point in time, rather than an extended period. You can think of the Type I report as more of a documentation review where the auditor is checking things out on paper and making sure that the controls described by management are reasonable and appropriate.
* Type II Reports These reports go further and also provide the auditor's opinion on the operating effectiveness of the controls. That is, the auditor actually confirms that the controls are functioning properly. The Type II report also covers an extended period of time: at least six months of operation. You can think of the Type II report as more like a traditional audit. The auditors are not just checking the paperwork; they are also going in and verifying that the controls function properly.

#### Payment Card Industry Data Security Standard (PCI DSS)

The PCI DSS includes more than 200 security controls organized into 12 requirements, further categorized into 6 goals that generally align with security best practices. Per the PCI SSC, the PCI DSS covers the following:
* Build and Maintain a Secure Network
  * Requirement 1: Install and maintain a firewall configuration to protect cardholder data.
  * Requirement 2: Do not use vendor-supplied defaults for system passwords and other security parameters.
* Protect Cardholder Data
  * Requirement 3: Protect stored cardholder data.
  * Requirement 4: Encrypt transmission of cardholder data across open, public networks.
* Maintain a Vulnerability Management Program
  * Requirement 5: Use and regularly update antivirus software or programs.
  * Requirement 6: Develop and maintain secure systems and applications.
* Implement Strong Access Control Measures
  * Requirement 7: Restrict access to cardholder data by business need to know.
  * Requirement 8: Assign a unique ID to each person with computer access.
  * Requirement 9: Restrict physical access to cardholder data.
* Regularly Monitor and Test Networks
  * Requirement 10: Track and monitor all access to network resources and cardholder data.
  * Requirement 11: Regularly test security systems and processes.
* Maintain an Information Security Policy
  * Requirement 12: Maintain a policy that addresses information security for employees and contractors.

## UNDERSTAND LEGAL AND REGULATORY ISSUES THAT PERTAIN TO INFORMATION SECURITY IN A HOLISTIC CONTEXT

### Cybercrimes and Data Breaches

A cybercrime is any criminal activity that directly involves computers or the internet. In a cybercrime, a computer may be the tool used to execute the criminal activity, or it may be the target of the criminal activity. There are three major categories of cybercrimes:
* **Crimes against people:** These crimes include cyberstalking, online harassment, identity theft, and credit card fraud.
* **Crimes against property:** Property in this case may include information stored within a computer, or the computer itself. These crimes include hacking, distribution of computer viruses, computer vandalism, intellectual property (IP) theft, and copyright infringement.
* **Crimes against government:** Any cybercrime committed against a government organization is considered an attack on that nation's sovereignty. This category of cybercrime may include hacking, theft of confidential information, or cyber terrorism. Hacktivism is another cybercrime that involves hackers seeking to make a political statement with their attacks. Hacktivists often target government entities but may also target other organizations with whom they disagree.

#### U.S. Computer Fraud and Abuse Act of 1986
 

The major provisions of the original CCCA made it a crime to perform the following:
* Access classified information or financial information in a federal system without authorization or in excess of authorized privileges
* Access a computer used exclusively by the federal government without authorization
* Use a federal computer to perpetrate a fraud (unless the only object of the fraud was to gain use of the computer itself)
* Cause malicious damage to a federal computer system in excess of $1,000
* Modify medical records in a computer when doing so impairs or may impair the examination, diagnosis, treatment, or medical care of an individual
* Traffic in computer passwords if the trafficking affects interstate commerce or involves a federal computer system

When Congress passed the CFAA, it raised the threshold of damage from $1,000 to $5,000 but also dramatically altered the scope of the regulation. Instead of merely covering federal computers that processed sensitive information, the act was changed to cover all “federal interest” computers. This widened the coverage of the act to include the following:
* Any computer used exclusively by the U.S. government
* Any computer used exclusively by a financial institution
* Any computer used by the government or a financial institution when the offense impedes the ability of the government or institution to use that system
* Any combination of computers used to commit an offense when they are not all located in the same state

##### CFAA Amendments of 1994
* Outlawed the creation of any type of malicious code that might cause damage to a computer system
* Modified the CFAA to cover any computer used in interstate commerce rather than just "federal interest" computer systems
* Allowed for the imprisonment of offenders, regardless of whether they actually intended to cause damage
* Provided legal authority for the victims of computer crime to pursue civil action to gain injunctive relief and compensation for damages

##### Protected Computer in a 1996 amendment

In plain English, a protected computer is a computer used by the U.S. government or financial institutions, or one used for interstate and foreign communications and financial transactions.  
It's important to note here that this definition is broad enough to apply to any computer that is "used in or affecting" government and commerce - a computer does not need to be directly used or targeted by a cybercriminal to be considered protected under this definition.

The CFAA in a 1996 amendment establishes seven criminal offenses related to computer fraud and abuse and identifies the penalties for each:
* Obtaining national security information
* Accessing a computer and obtaining information
* Trespassing in a government computer
* Accessing to defraud and obtain value
* Damaging a computer or information
* Trafficking in passwords
* Threatening to damage a computer

#### U.S. Electronic Communications Privacy Act (ECPA) of 1986
Enacted by Congress in 1986 
The Electronic Communications Privacy Act (ECPA) was enacted by the U.S. Congress in 1986 to extend restrictions on government wire taps to include computer and network-based communications (rather than just telephone calls).  
The ECPA complements the CFAA by prohibiting eavesdropping, interception, and unauthorized monitoring of all electronic communications (including those sent over computer networks).

#### U.S. Economic Espionage Act of 1996
The Economic Espionage Act (EEA) was enacted by the U.S. Congress and signed into law by President Clinton in 1996. The EEA was the first federal law to broadly define and establish strict penalties for theft or unauthorized use of trade secrets. The EEA makes it a criminal offense to copy, download, upload, alter, steal, or transfer trade secrets for the benefit of a foreign entity. The EEA establishes penalties for economic espionage that include fines up to $10 million and imprisonment up to 15 years, as well as forfeiture of any property used to commit economic espionage or property obtained as a result of the criminal act.

This law has these two major provisions:
* Anyone found guilty of stealing trade secrets from a U.S. corporation with the intention of benefiting a foreign government or agent may be fined up to $500,000 and imprisoned for up to 15 years.
* Anyone found guilty of stealing trade secrets under other circumstances may be fined up to $250,000 and imprisoned for up to 10 years.

#### U.S. Child Pornography Prevention Act of 1996
The Child Pornography Prevention Act (CPPA) was issued in 1996 to restrict and punish the production and distribution of child pornography on the internet.

#### U.S. Identity Theft and Assumption Deterrence Act of 1998
#### USA PATRIOT Act of 2001
#### U.S. Homeland Security Act of 2002
#### U.S. Controlling the Assault of Non-Solicited Pornography and Marketing (CAN-SPAM) Act of 2003
#### U.S. Intelligence Reform and Terrorism Prevention Act of 2004
#### The Council of Europe's Convention on Cybercrime of 2001
#### The Computer Misuse Act 1990 (U.K.)
#### Information Technology Act of 2000 (India)
#### Cybercrime Act 2001 (Australia)


## ESTABLISH AND MAINTAIN A SECURITY AWARENESS, EDUCATION, AND TRAINING PROGRAM

### Methods and Techniques to Present Awareness and Training

A standard security awareness program should include, at a minimum:
* new user orientation
* lectures or computer-based trainings (CBTs)
* printed materials like posters and handouts that share security tips

In addition:
* phishing and other social engineering exercises
* security champions
* gamification

to help raise awareness of important security topics.

### Periodic Content Reviews

### Program Effectiveness Evaluation

There are several methods by which you can evaluate the effectiveness of your security
awareness program. Some examples include the following:
* **Training metrics:** Simple metrics like training completion rates are a great place to start when evaluating the effectiveness of your security awareness program. These types of metrics can tell you whether your training resources are reaching a sufficient percentage of your employees and may alert you if alternate delivery methods are necessary.
* **Quizzes:** This is one of the most effective methods of measuring program effectiveness through knowledge retention. Quizzes are most reliable when measuring the effectiveness of security policies and related information. Analysis of quiz results should be conducted to identify trends that reveal necessary modifications to your training materials; if a substantial number of your employees get the same question wrong, it likely means you need to provide further (or clearer) information about that topic.
* **Security awareness days or weeks:** By sponsoring security awareness days or weeks, you not only have an opportunity to provide security education, but you can also use this as an opportunity to solicit feedback from your employees on the program itself. You can provide attendees with anonymous questionnaires that allow them to express their opinion about the current program and propose new ideas on content delivery.
* **Inherent evaluation:** As previously stated, you can also measure the effectiveness of your awareness program by evaluating your organization's overall security posture. Certain metrics, such as the number of phishing emails and other security issues reported to IT, can provide a great deal of insight into the effectiveness of your program. As your company's employees are increasingly educated on security risks, you should start to see the number of self-reported security issues rise. It's better to see a rise in reported suspected issues than a rise in successful compromises.

#### Inherent Risk
Inherent risk is the level of natural, native, or default risk that exists in an environment, system, or product prior to any risk management efforts being performed. Inherent risk can exist due to the supply chain, developer operations, design and architecture of a system, or the knowledge and skill base of an organization. Inherent risk is also known as initial risk or starting risk. This is the risk that is identified by the risk assessment process.

#### Residual Risk
Once safeguards, security controls, and countermeasures are implemented, the risk that remains is known as residual risk. Residual risk consists of threats to specific assets against which upper management chooses not to implement a response. In other words, residual risk is the risk that management has chosen to accept rather than mitigate. In most cases, the presence of residual risk indicates that the cost/benefit analysis showed that the available safeguards were not cost-effective deterrents.

#### Total Risk
Total risk is the amount of risk an organization would face if no safeguards were implemented.

#### Controls Gap
The controls gap is the amount of risk that is reduced by implementing safeguards.

> threats * vulnerabilities * asset value = total risk

> total risk – controls gap = residual risk


