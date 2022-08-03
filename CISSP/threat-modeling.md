# Threat Modeling

## STRIDE
Microsoft developed a threat categorization scheme known as the STRIDE threat
model. STRIDE is an acronym standing for the following:

- Spoofing: An attack with the goal of gaining access to a target system through the use of a falsified identity. When an attacker spoofs their identity as a valid or authorized entity, they are often able to bypass filters and blockades against unauthorized access.
- Tampering: Any action resulting in unauthorized changes or manipulation of data, whether in transit or in storage.
- Repudiation: The ability of a user or attacker to deny having performed an action or activity by maintaining plausible deniability. Repudiation attacks can also result in innocent third parties being blamed for security violations.
- Information disclosure: The revelation or distribution of private, confidential, or controlled information to external or unauthorized entities.
- Denial of service (DoS): An attack that attempts to prevent authorized use of a resource.
This can be done through flaw exploitation, connection overloading, or traffic flooding.
- Elevation of privilege: An attack where a limited user account is transformed into an account with greater privileges, powers, and access.

## PASTA
Process for Attack Simulation and Threat Analysis (PASTA) is a seven-stage threat modeling
methodology. PASTA is a risk-centric approach that aims at selecting or developing
countermeasures in relation to the value of the assets to be protected. The following are the
seven steps of PASTA:
- Stage I: Definition of the Objectives (DO) for the Analysis of Risks
- Stage II: Definition of the Technical Scope (DTS)
- Stage III: Application Decomposition and Analysis (ADA)
- Stage IV: Threat Analysis (TA)
- Stage V: Weakness and Vulnerability Analysis (WVA)
- Stage VI: Attack Modeling & Simulation (AMS)
- Stage VII: Risk Analysis & Management (RAM)


## Reduction Analysis
In the decomposition process, you must identify five key concepts:
- Trust Boundaries Any location where the level of trust or security changes
- Dataflow Paths The movement of data between locations
- Input Points Locations where external input is received
- Privileged Operations Any activity that requires greater privileges than of a standard user account or process, typically required to make system changes or alter security
- Details about Security Stance and Approach The declaration of the security policy, security foundations, and security assumptions