# Risk Management

Risk management employs a vast terminology that must be clearly understood, especially for the CISSP exam. This section defines and discusses all the important risk-related terminology:

**Asset** An asset is anything used in a business process or task. If an organization relies on a person, place, or thing, whether tangible or intangible, then it is an asset.

**Asset Valuation** Asset valuation is value assigned to an asset based on a number of factors, including importance to the organization, use in critical process, actual cost, and nonmonetary expenses/costs (such as time, attention, productivity, and research and development). When performing a math-based risk evaluation (i.e., quantitative; see the “Quantitative Risk Analysis” section, later in this chapter), a dollar figure is assigned as the asset value (AV).

**Threats** Any potential occurrence that may cause an undesirable or unwanted outcome for an organization or for a specific asset is a threat. Threats are any action or inaction that could cause damage, destruction, alteration, loss, or disclosure of assets or that could block access to or prevent maintenance of assets. They can be intentional or accidental. They can originate from inside or outside. You can loosely think of a threat as a weapon that could cause harm to a target.

**Threat Agent/Actors** Threat agents or threat actors intentionally exploit vulnerabilities. Threat agents are usually people, but they could also be programs, hardware, or systems. Threat agents wield threats in order to cause harm to targets.

**Threat Events** Threat events are accidental occurrences and intentional exploitations of vulnerabilities. They can also be natural or person-made. Threat events include fire, earthquake, flood, system failure, human error (due to a lack of training or ignorance), and power outage.

**Threat Vector** A threat vector or attack vector is the path or means by which an attack or attacker can gain access to a target in order to cause harm. Threat vectors can include email, web surfing, external drives, Wi-Fi networks, physical access, mobile devices, cloud, social media, supply chain, removable media, and commercial software.

**Vulnerability** The weakness in an asset or the absence or the weakness of a safeguard or countermeasure is a vulnerability. In other words, a vulnerability is a flaw, loophole, oversight, error, limitation, frailty, or susceptibility that enables a threat to cause harm.

**Exposure** Exposure is being susceptible to asset loss because of a threat; there is the possibility that a vulnerability can or will be exploited by a threat agent or event. Exposure doesn’t mean that a realized threat (an event that results in loss) is actually occurring, just that there is the potential for harm to occur. The quantitative risk analysis value of exposure factor (EF) is derived from this concept.

**Risk** Risk is the possibility or likelihood that a threat will exploit a vulnerability to cause harm to an asset and the severity of damage that could result. The more likely it is that a threat event will occur, the greater the risk. The greater the amount of harm that could result if a threat is realized, the greater the risk. Every instance of exposure is a risk. When written as a conceptual formula, risk can be defined as follows:

            risk = threat * vulnerability    
        or  
            risk = probability of harm * severity of harm

Thus, addressing either the threat or threat agent or the vulnerability directly results in a reduction in risk. This activity is known as risk reduction or risk mitigation, which is the overall goal of risk management. When a risk is realized, a threat agent, a threat actor, or a threat event has taken advantage of a vulnerability and caused harm to or disclosure of one or more assets. The whole purpose of security is to prevent risks from becoming realized by removing vulnerabilities and blocking threat agents and threat events from jeopardizing assets.

**Safeguards** A safeguard, security control, protection mechanism, or countermeasure is anything that removes or reduces a vulnerability or protects against one or more specific threats. This concept is also known as a risk response. A safeguard is any action or product that reduces risk through the elimination or lessening of a threat or a vulnerability. Safeguards are the means by which risk is mitigated or resolved. It is important to remember that a safeguard need not involve the purchase of a new product; reconfiguring existing elements and even removing elements from the infrastructure are also valid safeguards or risk responses.

**Attack** An attack is the intentional attempted exploitation of a vulnerability by a threat agent to cause damage, loss, or disclosure of assets. An attack can also be viewed as any violation or failure to adhere to an organization’s security policy. A malicious event does not need to succeed in violating security to be considered an attack.

**Breach** A breach, intrusion, or penetration is the occurrence of a security mechanism being bypassed or thwarted by a threat agent. A breach is a successful attack.


## Quantitative Risk Analysis

The major steps or phases in quantitative risk analysis are as follows (see Figure 2.3, with terms and concepts defined after this list of steps):
1. Inventory assets, and assign a value (asset value [AV]).
2. Research each asset, and produce a list of all possible threats to each individual asset. This results in asset-threat pairings.
3. For each asset-threat pairing, calculate the exposure factor (EF).
4. Calculate the single loss expectancy (SLE) for each asset-threat pairing.
5. Perform a threat analysis to calculate the likelihood of each threat being realized within a single year—that is, the annualized rate of occurrence (ARO).
6. Derive the overall loss potential per threat by calculating the annualized loss expectancy (ALE).
7. Research countermeasures for each threat, and then calculate the changes to ARO, EF, and ALE based on an applied countermeasure.
8. Perform a cost/benefit analysis of each countermeasure for each threat for each asset. Select the most appropriate response to each threat.

The cost functions associated with quantitative risk analysis include the following:
Exposure Factor The exposure factor (EF) represents the percentage of loss that an organization would experience if a specific asset were violated by a realized risk. The EF can also be called the loss potential. In most cases, a realized risk does not result in the total loss of an asset. The EF simply indicates the expected overall asset value loss because of a single realized risk. The EF is usually small for assets that are easily replaceable, such as hardware. It can be very large for assets that are irreplaceable or proprietary, such as product designs or a database of customers. The EF is expressed as a percentage. The EF is determined by using historical internal data, performing statistical analysis, consulting public or subscription risk ledgers/registers, working with consultants, or using a risk management software solution.

Single-Loss Expectancy The single-loss expectancy (SLE) is the potential loss associated with a single realized threat against a specific asset. It indicates the potential amount of loss an organization would or could experience if an asset were harmed by a specific threat occurring.  
The SLE is calculated using the following formula:  

        SLE = asset value (AV) * exposure factor (EF)
    or more simply:  
        SLE = AV * EF  
The SLE is expressed in a dollar value. For example, if an asset is valued at $200,000 and it has an EF of 45 percent for a specific threat, then the SLE of the threat for that asset is $90,000. It is not always necessary to calculate an SLE, as the ALE is the most commonly needed value in determining criticality prioritization. Thus, sometimes during risk calculation, SLE may be skipped entirely.

Annualized Rate of Occurrence The annualized rate of occurrence (ARO) is the expected frequency with which a specific threat or risk will occur (that is, become realized) within a single year. The ARO can range from a value of 0.0 (zero), indicating that the threat or risk will never be realized, to a very large number, indicating that the threat or risk occurs often. Calculating the ARO can be complicated. It can be derived by reviewing historical internal data, performing statistical analysis, consulting public or subscription risk ledgers/registers, working with consultants, or using a risk management software solution. The ARO for some threats or risks is calculated by multiplying the likelihood of a single occurrence by the number of users who could initiate the threat. ARO is also known as a probability determination. Here’s an example: the ARO of an earthquake in Tulsa may be .00001, whereas the ARO of an earthquake in San Francisco may be .03 (for a 6.7+ magnitude), or you can compare the ARO of an earthquake in Tulsa of .00001 to the ARO of an email virus in an office in Tulsa of 10,000,000.

Annualized Loss Expectancy The annualized loss expectancy (ALE) is the possible yearly loss of all instances of a specific realized threat against a specific asset. The ALE is calculated using the following formula:  

        ALE = single loss expectancy (SLE) * annualized rate of occurrence (ARO)  
    or  
        ALE = asset value (AV) * exposure factor (EF) * annualized rate of occurrence (ARO)  
    or more simply:  
        ALE = SLE * ARO  
    or  
        ALE = AV * EF * ARO  

For example, if the SLE of an asset is $90,000 and the ARO for a specific threat (such as total power loss) is .5, then the ALE is $45,000. If the ARO for a specific threat (such as compromised user account) is 15 for the same asset, then the ALE would be $1,350,000.

## Risk Responses

These risk responses are all related to an organization’s risk appetite and risk tolerance.

_Risk appetite_ is the total amount of risk that an organization is willing to shoulder in aggregate across all assets. Risk capacity is the level of risk an organization is able to shoulder. An organization’s desired risk appetite may be greater than its actual capacity.

_Risk tolerance_ is the amount or level of risk that an organization will accept per individual asset-threat pair. This is often related to a risk target, which is the preferred level of risk for a specific asset-threat pairing. A risk limit is the maximum level of risk above the risk target that will be tolerated before further risk management actions are taken.

You need to know the following information about the possible risk responses:

**Risk Mitigation** Reducing risk, or risk mitigation, is the implementation of safeguards, security controls, and countermeasures to reduce and/or eliminate vulnerabilities or block threats. Deploying encryption and using firewalls are common examples of risk mitigation or reduction. Elimination of an individual risk can sometimes be achieved, but typically some risk remains even after mitigation or reduction efforts.

**Risk Assignment** Assigning risk or transferring risk is the placement of the responsibility of loss due to a risk onto another entity or organization. Purchasing cybersecurity or traditional insurance and outsourcing are common forms of assigning or transferring risk. Also known as assignment of risk and transference of risk.

**Risk Deterrence** Risk deterrence is the process of implementing deterrents to would-be violators of security and policy. The goal is to convince a threat agent not to attack. Some examples include implementing auditing, security cameras, and warning banners; using security guards; and making it known that the organization is willing to cooperate with authorities and prosecute those who participate in cybercrime.

**Risk Avoidance** Risk avoidance is the process of selecting alternate options or activities that have less associated risk than the default, common, expedient, or cheap option. For example, choosing to fly to a destination instead of driving to it is a form of risk avoidance. Another example is to locate a business in Arizona instead of Florida to avoid hurricanes. The risk is avoided by eliminating the risk cause. A business leader terminating a business endeavor because it does not align with organizational objectives and that has a high risk versus reward ratio is also an example of risk avoidance.

**Risk Acceptance** Accepting risk, or acceptance of risk, is the result after a cost/benefit analysis shows countermeasure costs would outweigh the possible cost of loss due to a risk. It also means that management has agreed to accept the consequences and the loss if the risk is realized. In most cases, accepting risk requires a clearly written statement that indicates why a safeguard was not implemented, who is responsible for the decision, and who will be responsible for the loss if the risk is realized, usually in the form of a document signed by senior management.

**Risk Rejection** An unacceptable possible response to risk is to reject risk or ignore risk. Denying that a risk exists and hoping that it will never be realized are not valid or prudent due care/due diligence responses to risk. Rejecting or ignoring risk may be considered negligence in court.

_Inherent risk_ is the level of natural, native, or default risk that exists in an environment, system, or product prior to any risk management efforts being performed. Inherent risk can exist due to the supply chain, developer operations, design and architecture of a system, or the knowledge and skill base of an organization. Inherent risk is also known as _initial risk_ or _starting risk_. This is the risk that is identified by the risk assessment process.

Once safeguards, security controls, and countermeasures are implemented, the risk that remains is known as residual risk. Residual risk consists of threats to specific assets against which upper management chooses not to implement a response. In other words, residual risk is the risk that management has chosen to accept rather than mitigate. In most cases, the presence of residual risk indicates that the cost/benefit analysis showed that the available safeguards were not cost-effective deterrents.

_Total risk_ is the amount of risk an organization would face if no safeguards were implemented. A conceptual formula for total risk is as follows:

    threats * vulnerabilities * asset value = total risk
The difference between total risk and residual risk is known as the controls gap. The controls gap is the amount of risk that is reduced by implementing safeguards. A conceptual formula for residual risk is as follows:

    total risk – controls gap = residual risk


## Quantitative risk analysis formulas

| Concept                                                       | Formula or meaning                     |
|---------------------------------------------------------------|----------------------------------------|
| Asset value (AV)                                              | $                                      |
| Exposure factor (EF)                                          | %                                      |
| Single loss expectancy (SLE)                                  | SLE = AV * EF                          |
| Annualized rate of occurrence (ARO)                           | # / year                               |
| Annualized loss expectancy (ALE)                              | ALE = SLE * ARO or ALE = AV * EF * ARO |
| Annual cost of the safeguard (ACS)                            | $ / year                               |
| Value or benefit of a safeguard (i.e., cost/benefit equation) | (ALE1 – ALE2) – ACS                    |