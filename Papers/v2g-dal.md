---
draft:
title: A Network in Motion
tags:
  - Paper📃
aliases:
---
#### The Promise and Practical Feasibility of Vehicle-to-Grid Communication.

Alexandre DesAulniers, Lorne MacLean, Michael Doyle, Ashton Dudley, Liam Legge | December 2025 | [[ECED3101 Power Systems — V2X Report.pdf|PDF]]

>[!abstract] 
>The following report provides a comprehensive analysis of Vehicle-to-Everything (V2X) technology, emphasizing the critical role of Vehicle-to-Grid (V2G) capabilities. V2X proves to be an interesting advancement in grid resilience that positions Electric Vehicles as mobile energy storage assets, utilizing bidirectional power flow for vital functions like grid balancing, stability, and the integration of intermittent renewable energy sources. The report's primary objective is to identify and critically evaluate V2X/V2G’s principal implementation challenges across three key areas: technical viability (e.g., infrastructure standardization), economic feasibility, and the necessary political/regulatory frameworks. These hurdles are directly contrasted with the technology's considerable societal and economic advantages, demonstrating how V2X can improve energy resilience during periods of high demand. A Network in Motion’s analysis is structured to cover the foundational concepts, the current technical landscape, and the future economic and political outlook of the sector. 
>
  >This all culminates in a need to determine the influence these factors have on the economic, political, and technological potential of V2X as an implementable technology. This report’s findings conclude that Vehicle-to-Grid (V2G) technology is currently struggling to be widely adopted due to high infrastructure costs, the need for cooperation among power companies and regulators, and a lack of industry-wide rules. In contrast, Vehicle-to-Load (V2L) and Vehicle-to-Home (V2H) applications are finding success with consumers, and are becoming widely adopted.

^0450a1
# Introduction

Vehicle-to-Grid (V2G) technology, a critical advancement in energy management & strategy, has garnered significant attention over the past three decades [^33] At its core, V2G refers to the bidirectional power flow capability that allows the batteries of Electric Vehicles (BEVs<sup> 1</sup>) to not only draw power from the electrical grid for charging, but also to feed surplus power back into it.

This use of EV batteries transforms BEV’s<sup> 1</sup> from simple grid load elements, to mobile energy storage. By supplying power back to the grid, particularly during periods of peak power usage or high demand, V2G has the potential to significantly contribute to grid balancing, stability, and resilience [^14]. This functionality is enabled by bidirectional charging connectors and hardware, and their accompanying standards & protocols, which facilitate the controlled flow of electricity both in and out of the BEV<sup> 1</sup> battery. While this capability represents a shift in how vehicle ownership interfaces with existing energy infrastructure, the number of current-production EVs fully capable of two-way discharging remains limited [^28].


![[Pasted image 20251227172701.png|center|600]]
<center><sub>Figure 1: Operation of an Electric Vehicle as backup power supply. <i>(Monteiro et al., 2014)</i></sub></center>


The foundational concept of V2G has since been expanded to include Vehicle-to-Home (V2H) and Vehicle-to-Load (V2L) applications, all of which are collectively described by the comprehensive term, Vehicle-to-Everything (V2X). This shift positions the large scale decentralized storage capacity of EV fleets as an incredibly flexible source of power, and a crucial component for integration of intermittent renewable energy sources; such as solar and wind power.

The purpose of the following report is to conduct a comprehensive analysis of the V2G/V2X ecosystem and market. Specifically, it will identify the principal technical, political, and economic challenges associated with V2X’s advancement and its widespread implementation within the global auto and energy industries. 

This analysis will be balanced by a comparison against the numerous advantages the technology offers, detailing how it can be leveraged to benefit rate payers, increase economic activity, and improve global energy security through operational and emergency events.

The subsequent sections of this report will provide a deep dive into: 

1. **The foundational concepts and architectural requirements of V2X technology**

2. **The technical viability and operational challenges that have yet to be overcome**

3. **The future outlook of the sector, covering its economic market potential and the political and regulatory frameworks required for mass adoption.** 

Each section’s analysis will be used to determine the influence these factors have on the economic, political, and technological potential of V2X as an implementable technology.

---
# Foundational Concepts (V2X)

Vehicle-to-Everything (V2X) is a comprehensive term describing the ability of a vehicle — typically a Battery Electric Vehicle (BEV<sup> 1</sup>) — to both draw energy from and return stored electrical energy to an external system or load. This functionality is commonly known as bidirectional charging.

The V2X framework establishes the communication protocols necessary for secure handshaking and power-flow management between the vehicle and the external interface. These interactions are primarily governed by the ISO 15118 series of international standards [^19], which ensure interoperability across different vehicle manufacturers and charging infrastructures.

While V2X serves as the foundational communication standard, energy delivery applications are categorized by the destination of the power flow:

<center><sub>Table 1: Description of Common V2X use cases. </sub></center>

![[Pasted image 20251227173258.png|center]]

#### Key Technologies

The core functionality of an electric vehicle (EV) is driven by three interconnected technical systems. First, the tractive system, comprising of the electric motor and associated gearbox, converts electrical energy into the mechanical torque required to drive the vehicle's wheels. Power management for this process is facilitated by the power inverter, a DC-AC converter that transforms high-voltage direct current from the battery into the precise alternating current supply needed to operate the motors.

The high-voltage battery system serves as the primary energy reservoir, utilizing battery cells, a dedicated Battery Management System (BMS), and integrated thermal controls to regulate the environment for safe and optimal performance. Engineered for high reliability, these systems depend on rigorous standardization to ensure cross-platform compatibility across various vehicle models and the seamless integration of differing battery chemistries within a unified architecture.
##### Vehicle Tractive Systems

A vehicle's tractive system is the high-voltage power system within an electric or hybrid vehicle, which is responsible for converting the stored electric energy of the high-voltage DC battery pack into usable mechanical power, typically through an AC synchronous motor/generator [^4]: . 

Most tractive systems consist of the following components:

- A high-voltage battery pack, which acts as the primary energy source while in operation.

- One or more AC synchronous motors, which can act as generators to improve efficiency during braking, reclaiming some mechanical energy. These motors are typically wired in a 3-phase delta configuration.

- One or more bidirectional AC-DC converters, which control the power input and output of the tractive motors. 

- An onboard AC-DC bidirectional grid-tied inverter, with the primary purpose of charging the tractive battery pack. In North America, vehicles are equipped with DC to single-phase AC chargers, compliant with CCS2 or SAE J34003. Some regions, such as the EU, also support three-phase charging via the CCS2 standard.


![[Pasted image 20251227173502.png|center|600]]
<center><sub>Figure 2: Tractive System Equivalent Circuit, <i>DalFSAE EV — DMS-25</i></sub></center>

 	
##### Power Inverters 

An inverter is a device that converts a direct current (DC) power signal into an alternating current (AC) power signal

It can be said that: 
$$ P_{AC}=V_{AC}I_{AC}cos(\phi) \space \text{   and},$$
$$P_{DC}=V_{DC}I_{DC}$$
$$ \text{so,}  \space V_{AC}I_{AC}cos(\phi)=V_{DC}I_{DC} $$

An ideal inverter can be described by $P_{AC} = P_{DC}$ . However, a real system must account for some loss, hence.

$$\eta_{eff} = \frac{P_{OUT(AC)}}{P_{IN(DC)}}$$

To synchronize with the grid, the AC output of the inverter must match said grid's waveform and frequency. In large power systems, grid-tied inverters are also often used. A grid-tied inverter operates solely as a voltage source; hence, the output waveform is controlled by the existing grid voltage, frequency, and phase [^35]. This is typically accomplished with a phase-locked loop (PLL), which can be implemented with relatively simple and affordable hardware [^10]: .

Grid-following inverters cannot operate without a live grid, preventing them from powering external loads. This dependence makes them unsuitable for V2G applications.

##### Bi-Directional Power Inverters

Bidirectional power inverters are the key technology that enables the highly efficient tractive systems of modern electrified vehicles [^4]: . While traditional inverters only allow current to flow in one direction, a bidirectional inverter supports the flow of energy in both directions, between either the vehicle battery and traction motors or the larger AC electrical grid. 

Unlike a simple one-way inverter, a bidirectional inverter can operate in either:

- DC to AC mode, where the battery is acting as the voltage source, and
- AC to DC mode, where the tractive motor, or grid, is acting as the voltage source.

Bidirectional Inverters use an onboard microcontroller to calculate a standalone target voltage, frequency, and phase. This feedback is used to control the switching pattern of the circuit, and therefore the output signal. This enables a seamless transition between each mode, transitioning from forward propulsion and regenerative braking. Similar bidirectional inverters are employed at the BMS charging circuit, enabling V2X.

The inverter circuit is typically connected via a bidirectional DC-DC converter, which uses a similar switching methodology. The DC-DC converter accommodates voltage mismatches between the grid and the traction battery. This addition stage gives the inverter full control over the output/input voltage [^4]: . 

##### Frequency Regulation and Grid-Forming Inverters



![[Pasted image 20251227174346.png|center]]
<center><sub>Figure 3: PWM voltage modulated as a series of pulses, <i>(Wikimedia Commons, 2007)</i></sub></center>


Fundamentally, an inverter uses a high-frequency switching circuit to convert a power signal between the DC domain and the AC domain.  The switching is typically performed by high-performance field-effect transistors, such as MOSFETs and JFETs, or bipolar junction transistors (BJTs), controlled by a PWM signal from the system's microcontroller. Such a system can be described by the following relation: [^36]

$$P_{DC}(t) \leftrightarrow  P_{AC}(t) $$

A 50% duty cycle square wave acts as the fundamental harmonic. To create a sufficient approximation of a sine wave, additional square waves can be added to the output signals. When combined with a sufficiently low-pass filter, an approximation sine wave can be achieved.

This process gives the inverter full control over the output voltage and phase. 

This process is also symmetrical; when in AC-DC mode, the inverter utilizes its switching circuit to function as a full-bridge rectifier. 

Apparent power is defined as the total complex power in an AC circuit, composed of real power and reactive power.

It is defined by the relation:

$$S=P+jQ$$
Where:

- S is Apparent Power (*VA*)
- P is Real Power (*W*)
- Q is Reactive Power (*VAR*)

Apparent power is also calculated using the voltage (*V*) and the complex conjugate of the current (I<sup>*</sup>):

$$S=VI^*$$
$$P=VIcos(\theta), \text{and} \space Q=VI(\theta), $$
Where,

- V is controlled by the bidirectional DC-DC converter,
- $\theta$ is controlled by the PWM of the switching circuit.
- P is the real power
- Q is the reactive power.

A typical AC synchronous generator is fully dependent on the power factor of the grid and would be forced to produce reactive power. However, a PWM inverter is directly in control of its  value. Thus, the bidirectional inverter is capable of correcting the power factor of a connected AC system.


![[Pasted image 20251227174914.png|center]]
<center><sub>Figure 4: Connection of a tractive battery to a single-phase AC grid, based on the DalFSAE EV charging schematic</sub></center>

##### Cellular-V2X

In the design of autonomous vehicles, it is of utmost importance that all necessary information (obstacles, navigation etc.) is received by the vehicle as quickly as possible. Cellular V2X (C-V2X) allows for exactly this, completely wirelessly. Through various types of communication, a vehicle can obtain timely information about and from other vehicles on the road (V2V), roadway infrastructure such as traffic signals (V2I), existing telecommunication networks, such as GPS (V2N), and even pedestrians via smartphones and other devices (V2P). With the integration of all this information, autonomous and assisted driving becomes possible and/or much more feasible. According to Papathanassiou & Khoryaev, C-V2X is the most suitable candidate to meet the near-term vehicular communication requirements [^27]. Compared to its contemporary technologies, C-V2X features a significant increase in communication range, with a greater packet reception ratio (PRR) at long distances. The figure below compares the PRR of some alternatives over several distances:

![[Pasted image 20251227175005.png|center]]
<center><sub>Figures 5 & 6: Packet Reception Falloff <i>(Papathanassiou & Khoryaev, 2017)</i></sub></center>

#### Roles of Standards

In the development and implementation of vehicle-to-grid technology, standards play a crucial role in the success of a unified system. This is evident in the advantages of standardizing the technology, such as promoting compatibility of electric vehicles between jurisdictions, increasing the speed at which the technology is adopted, and enabling more efficient knowledge transfer. It also ensures future compatibility of the system as a whole [^3]: . These features are key factors in the long term goals of V2G technology, and without them, the technology would never progress. If standardization were not adopted, electric vehicle manufacturers would be forced to develop and produce region-specific versions. This lack of universality would severely restrict manufacturers' operational efficiency and significantly drive up production costs. Such cost pressures would likely necessitate the exclusion of features, such as V2G capabilities, from final product designs. The combination of these factors clearly demonstrates the importance of developing standardization for V2G, which, as expected, is already very much in place for the technology.

There are currently multiple standards related to V2G technology. These standards each relate to different aspects of V2G technology, as can seen below in Table 2. The standards below regulate the connection between the vehicle and grid, safety guidelines, functions of the vehicle (providing/receiving power), and communication between the vehicle and the EVSE<sup> 4</sup>. While listed are the major standards currently in use, it is by no means comprehensive. There are many other standards that have also been adopted, as outlined by Das et al. [^11]: . Having many standards poses its own challenges in development of V2X technology. Each design must choose a standard or attempt to adhere to as many of them as possible, which can increase the difficulty of each V2X implementation.


<center><sub>Table 2: List of global V2G standards: Adapted from <i>Mafazy (2022) </i></sub></center>

![[Pasted image 20251227175207.png]]


Overall, the use of standards in each implementation of V2X exists to make the process more universal and accessible. Each category of standard has multiple standards, and sub-standards developed by different entities. This can cause difficulty in final implementations, considering the goal is to have one consistent implementation method across all jurisdictions. Despite this, standards definitions are vitally important, and help move toward a consistent implementation globally.

---

# Technical Viability and Challenges of V2G/V2X

The rate at which Vehicle-to-Grid technology can be successfully developed and fully utilized depends critically on overcoming several systemic and physical limitations. The current most significant challenge lies in the integration of new V2G technology with existing, legacy electrical grid infrastructure (Taylor et al., 2025).

This integration is limited by factors spanning both the vehicle and the infrastructure. On the physical front, the progress of V2G is directly affected by hardware constraints on the bidirectional charging connectors and the lack of standardized communication protocols [^34]. Simultaneously, the viability of the technology is constrained by the impact of frequent discharging on battery degradation and capacity, which presents a major consumer acceptance issue. Finally, the ability of the current electric grid to effectively handle the storage and reliably supply large-scale two-way power flows, a capability not initially designed for, will fundamentally dictate the future progress of V2G technology.

#### V2G Barriers to Adoption

There are numerous issues with the widespread adoption of V2X technology in the present. The current lack of cohesive standard implementation plays a role in the safety of hardware implementation and universal connection to the technology [^34]. Battery quality limitations also make it difficult to quickly implement a solution that does not degrade BEV<sup> 1</sup> battery health long-term. Furthermore, the lack of existing momentum, continues to make implementation difficult.

##### Hardware Limitations

One of the biggest safety limitations when connecting back to the grid is that of fault protection. As most grid-related safety factors are set up at installation, adding additional safety features may be difficult. Unintentional short-circuit levels may increase as more EVs are being connected to the grid [^2]: . Therefore, more overcurrent protections will have to be installed throughout distribution systems to eliminate changes in the fault characteristics [^31]. Reliable, sensitive, and selective overcurrent protection has to be installed to detect minor and major short-circuits, and allow for service to continue with minimum disconnections of equipment on the system [^31].

Another challenge is that of communication technology. Discharging activities will require fast and safe real-time entity authentication and communication of the discharge procedure to ensure safe and accurate reporting of power transmission from the vehicle back to the grid [^2]: . 

Controlled two-way communication bandwidth must be implemented to transfer information concerning car model, battery capacity and discharge rate [^2]: . This communication requires for smart charge management to be introduced, such that the vehicle, EVSE<sup> 4</sup>’s, network operators and energy service providers can analyze information about the hardware operating on local grid. [^24]

##### Grid Limitations

One of the primary challenges in sustaining a large scale power grid is that of supplying power during peak usage hours. The grid must be capable of sustaining the absolute peak of each consumers' usage, essentially simultaneously. Because of this, many electricity providers will impose a monetary charge proportional to the consumer’s peak usage. Two vital concepts emerge from this fact: Peak-shaving and load-balancing.

Because a consumer stands to benefit economically from decreased peak usage, it becomes very useful to be able to offset their strain on the grid during their highest usage times. V2G is a very strong candidate for this, as the consumer can strategically discharge their vehicle’s power when their use spikes, effectively reducing their magnitude (peak shaving). Additionally, because the EV charges when not in use, it is quite feasible to charge it during the hours of lowest electrical demand, avoiding large spikes in power usage (load balancing). Load balancing can also be used as a strategic cost savings measure. According to one study, with optimal synergy between numerous EVs, an 8.91% reduction in operational costs and 39.4% mitigation in grid load factor (the ratio between total use to use during peak hours) can be achieved [^38].

Furthermore, the variable nature of V2X compliments renewable energy solutions. Solar and wind energy, being dependent on external factors, are inherently variable, and thus their energy production will not always coincide with peak usage. Unused energy is often discarded, with up to ~9% of produced energy meeting this fate [^26]. Excess & intermittent energy produced from variable renewable energy (VRE<sup> 5</sup>) sources can be mitigated with V2X, as local EV fleets act as large scale energy storage, further strengthening the degree of peak-shaving and load-balancing.

##### Battery Degradation
A large concern with V2G technology is increased rate of battery degradation, especially for the owners of EV’s. Considering that increased number of charge/discharge cycles reduce battery longevity, effectively reducing the feasible lifetime for an EV, this skepticism is warranted. Understandably, this concern has posed a barrier to large scale implementation of V2G technology [^37]. In order for V2G to be successful, these concerns must be addressed and mitigated in a way that encourages owners of EVs to opt in to such a program.

To address this, the true degradation of EV batteries due to V2G must first be explored. Many factors are at play when considering the degradation of batteries, making quantifying the exact effect of V2G more difficult. Despite this, there have been models created, and case studies conducted to provide some data on this topic. Wang et al. demonstrates a lifetime reduction of the EV of less than a year, as shown in Figure 7 [^37]. Another study done by Sagaria et al. found degradation was increased by 3% over 10 years when using V2G [^30]. These results show encouraging results with minimal increased degradation of battery life when using V2G. Despite these results, it is unlikely that EV owners will be enthusiastic to participate in V2G if they are knowingly, actively, degrading their vehicle’s battery without return.


![[Pasted image 20251227175336.png|center|500]]
<center><sub>Figure 7: Comparison of Long Term Capacity loss with, and without V2G, adapted from <i>Wang et al. (2016)</i></sub></center>


To encourage the adoption of V2G, an incentive of some sort would need to be implemented to account for the battery degradation and inconvenience of providing power to the grid. This would encourage more EV owners to enable V2G capabilities and make the technology more viable. The compensation would need to, at the very least, account for the value loss from battery degradation. Sagaria et al. found that the necessary compensation to cover the cost of battery degradation and installation of a bidirectional charger is around €132/MWh (~213CAD/MWh), which is likely to reduce to €70/MWh (~113CAD/MWh) by 2050 as battery costs decrease [^30].

This compensation model is not feasible when considering the cost of electricity in a province such as Nova Scotia. According to Nova Scotia Power, the current residential rate for power is $0.18561/KWh [^25]. If the compensation for using V2G is converted to the same metric, EV owners would need to be compensated approximately $0.21/KWh. This would require the customer to be compensated at a higher rate than the utility provider charges for power. This would be extremely unlikely, and the compensation would be much lower in practice, unless federal programs were established to subsidize the cost. As all of this is put together, it complicates the compensation model for EV owners and makes the implementation of V2G more challenging. Overall, in today’s climate, the effects of V2G on battery degradation are still too high of a cost to make V2G appealing to the broader market, and may take years before this imbalance is corrected.


##### Interconnection Standards

The Combined Charging System (CCS<sup> 2</sup>) has become the primary dominant charging connector standard for electric vehicles globally, utilizing the CCS1 variant in North America and the CCS2 variant across Europe. CCS<sup> 2</sup> uses PLC-based communication, compliant with the ISO 15118 family of standards (PVPSCS, 2025). CCS<sup> 2</sup> DC interconnections have a maximum 1000V charging voltage. The connector has one of the highest power outputs at 350kW with the J1772 + CCS<sup> 2</sup> combo connector [^12]: . CCS<sup> 2</sup> is the most common and flexible connection type, as 74.6% of new BEV’s<sup> 1</sup> sold utilized a CCS<sup> 2</sup> charger [^7]: .



![[Pasted image 20251227175424.png|center|500]]
<center><sub>
Figure 8: Global Vehicle Connection Standards</sub></center>


The North American Charging Standard (NACS<sup> 3</sup> ), officially designated as SAE J3400, is the proprietary electric vehicle (EV) connector standard developed by Tesla, Inc. The connector utilizes power-line communication (PLC) over the control pilot line. This communication is compatible with the Vehicle-to-Grid (V2G) protocol defined in the ISO 15118-3 standard [^17] . As of May 2025, the latest standard for the J3400 connector supports voltages up to 1000V. However, most current Tesla vehicles primarily operate on a 400V system [^20]. While NACS/J3400<sup> 3</sup>  is currently used predominantly by Tesla vehicles, it is poised for wider acceptance across the North American electric vehicle market. Its flexibility and Tesla's extensive existing installation base contribute to its probable widespread adoption. Despite its growing momentum, the connector is not yet universal and currently serves approximately 10% of BEVs<sup> 1</sup> on the road [^7]: . For NACS/J3400<sup> 3</sup>  to become the agreed-upon North American universal connector, it requires complete open standardization through the SAE International group. This formal standardization is necessary to ensure proper open regulatory compliance with the ISO 15118-3 standard and seamless integration into all other North American manufacturers' BEVs’<sup> 1</sup>.

GB/T is China’s nationally mandated charging standard, a comprehensive framework that governs all electric vehicles and infrastructure within the country. Unlike the globally shared Combined Charging Standard (CCS<sup> 2</sup>), or CHAdeMO standard, GB/T was engineered specifically for China’s unique electrical grid demands. This created a highly standardized, but closed domestic EV ecosystem. [^32]
GB/T’s primary communication standard for DC charging is GB/T 27930. This standard is generally comparable to ISO 15118 in its purpose—providing general, physical, and signalling requirements. However, GB/T does not natively use the same Power Line Communication (PLC) technology as ISO 15118. Instead, the GB/T 27930 protocol historically relies on the Controller Area Network (CAN) bus for communication between the charger and the vehicle's battery management system [^32].  While GB/T chargers and vehicles are being developed with V2G functionality, it is not directly interoperable with the ISO 15118 standard. 

Finally, CHAdeMO is the Tokyo Electric Power Company’s (TEPCO) implementation of a charging connector for EV vehicles, initially aimed at the Japanese domestic market. It is a very mature, fully DC standard, with bi-direction EV charging functionality, allowing it to fully operate as a V2G source [^9]: . The connector is not compliant with the ISO 15118 standard, instead it uses CAN-bus for EV-to-EVSE signaling [^32].  According to N.R Canada, CHAdeMO is facing a significant decline in North American market share, sitting at 8.1% of total operational high voltage DC fast charging infrastructure in the country [^7]: . 

#### V2G Security Limitations 

Involved in V2X is an extensive bidirectional transfer of energy and. Consequently, cybersecurity and data privacy are critical concerns for the technology. The following section will elaborate on some of these concerns.

##### Cybersecurity

Creating a large network for vehicle communication can be seen as inherently ambivalent. On the one hand, many of the technologies discussed become possible. On the other hand, a whole new domain of cyber-threats are introduced. For instance, a bad actor and/or security researchers could conceivably abuse  large scale pools to obstruct traffic remotely via distributed denial-of-service DDoS<sup> 6</sup> attacks, or have these large scale V2G pools act as a larger DDoS<sup> 6</sup> attack nodes. The mitigation and prevention of such attacks is among the most vital challenges faced by V2X. One study proposes a machine-learning based approach in mitigation of such attacks [^18] . With this approach, identification of attacks can be streamlined, and the appropriate measures taken promptly. Another approach would be rate limiting and priority queueing; in other words, implementing a maximum data transfer per unit time, and assigning an “urgency” to data packets to control the transmission order.

##### Data Privacy

Because vehicles engaging in V2X invariably involves the transfer of large amounts of data, privacy concerns naturally emerge. Even in the simplest case where vehicles solely share positional data for navigational purposes, there is a risk of an ill-intentioned third party obtaining this data. To mitigate this risk, a few solutions have been recommended, such as data encryption and deletion upon use. The act of issuing pseudonyms in data transmission has shown promise to this effect [^5]. This approach involves transmitting data under constantly changing randomized false names, making it much more difficult to trace specific data to a certain user. While promising, this technique does have the drawback of relying on a “highly trusted, centralized Authorization Authority” [^5]: . If this authority is compromised, data privacy cannot be guaranteed. 

---
# Future Outlook

The future trajectory of the entire V2X ecosystem depends largely on the economic benefits it can provide to both major stakeholders: energy companies and individual vehicle owners.

For utilities and energy companies, investment is strictly contingent upon a clear financial justification. If the monetary return on the V2X energy services—through reduced peak demand costs and new revenue streams—is not adequate, then energy companies will not invest in the necessary innovation and infrastructure [^23].

For vehicle owners, the incentives are dual: financial and practical. Beyond potential monetary compensation for providing power to the grid, a significant non-monetary benefit is the utility of having an energy backup for emergency situations. This capability is often termed Vehicle-to-Load (V2L), allowing the vehicle battery to power appliances or a home.

#### Economic Landscape

The economic landscape is difficult to predict. With economics and politics playing a huge role in the progression of an electrification project across the globe. The initial capital investing into a project this size is substantial. According to the Natural Renewable Energy Laboratory (2023, p. 58), estimates suggest that $53-$127 billion in cumulative capital investment is required to support the 33 million electric vehicles by 2030 in America. To date, it has been reported that estimated investments are $23.7 billion. These estimates can be compared to the requirement that Canada would need for the same implementation. 

##### Electric Vehicle Owners

To date, there are few consumer benefits for vehicle owners to participate in the transition towards V2X. They would have to compete with new capacity installations, and the economic return (money made from batteries supplying energy) would be negligible [^23] . As cited in Eltohamy et al, where energy usage is 5 kWh/day/owner or 10 kWh/day/owner, there is no financial gain as the cost to repair outweighs the money made from selling excess electricity [^14]: . It is only when usage is 20 kWh/day/owner that a break-even point is reached after approximately 7 years. 


![[Pasted image 20251227175608.png|center|500]]
<center><sub>Figure 9: Economic Feasibility of V2G Technology <i>(Etlohamy et al., 2025)</i></sub></center>


However, for emergency relief, and portable load applications, V2H, & V2L technologies prove to be useful, and enticing to consumers, especially in areas that are remote [^23]. As listed by Avery, several current EV models already support V2L and are compliant with the industry standard ISO 15118 for two-way communication and charging [^1]:  :

- **Ford F-150 Lightning**
- **Rivian R1T**
- **Hyundai Ioniq 5**
- **Hyundai Ioniq 6**
- **Kia EV6**
- **Kia EV9**
- **Genesis GV60**
- **Cadillac Lyriq**
- **Chevrolet Silverado EV RST**

It is important to note that Tesla Inc. has also implemented bidirectional charging capabilities through its Tesla Powershare system and its Cybertruck. However, this is currently based on a Tesla Inc. proprietary standard, which is non-conformant to the universally adopted ISO 15118 (Tesla.com, 2023). Weak enforcement of standard compliance poses as one of many potential challenges for broad, standardized V2G integration.

Consumer trends have shown that V2L applications, such as providing mobile power camping, running tools on construction sites, and offering emergency backup during power outages have proven to be popular uses, and require little additional infrastructure to implement. [^23]

##### Utilities/Grid Operation Companies

For Vehicle-to-Grid (V2G) technology to be fully adopted, there must be a clear and quantifiable increase in profits and operational benefits for the utilities and grid operation companies to justify the investment. [^23]

Utilities primarily stand to gain by leveraging EVs as flexible, decentralized energy resources. V2G enables the grid operator to:

- Reduce Peak Demand Costs: By discharging power from EV batteries during periods of high demand (peak usage), utilities can avoid or defer the high cost of running expensive, inefficient “peaker” power plants. This can turn out to be a massive cost-saving measure.

- Monetize Grid Services: EVs can provide essential grid services, such as frequency regulation (keeping the grid frequency stable) and voltage support. Utilities can monetize these services, turning the EV fleet into a revenue stream rather than just a load.

- Integrate Renewables: V2G allows for the storage of excess power generated by intermittent sources (like solar or wind) and its subsequent release, thereby minimizing curtailment losses and making renewable energy more valuable.

--

However, the initial fixed costs associated with upgrading the grid's capabilities to handle two-way power flow are indeed significant. This required investment covers several complex areas:

- Centralized Management Systems: Utilities must install sophisticated centralized management hardware, software, and network equipment [^23]. This includes a Distribution Management System (DMS) or similar platform capable of communicating with thousands of individual EVs in real-time, managing bidirectional flow, and ensuring grid safety.

- Infrastructure Reinforcement: The existing distribution grid—especially local transformers and feeders—was designed for unidirectional power flow (from the substation to the customer). V2G requires infrastructure reinforcement to prevent overloading or damage from reverse power flow at the local level.

- Cybersecurity Investment: As previously discussed in 2.2 V2G Security Limitations, given that a system involves connecting thousands of personal vehicles to critical infrastructure, significant investment in advanced cybersecurity protocols and monitoring is necessary to prevent cascading failures or malicious attacks.

Ultimately, grid operators will only move forward when the net present value of the long-term operational savings and new revenue streams outweighs the substantial initial capital expenditure for these complex system upgrades.

#### 3.2 Policy and Pilot Programs

As yet, current global regulation for distributed V2G grid attached networks is continually developing. According to Fortune Business Insights, notable early legal framework adopters include China, France, Sweden, the United Kingdom, and Japan [^15]: .

Legal compliance and alignment with the ISO 15118 series of standards has the primary objective of several countries and regulatory bodies, such as the CSA group in North America. (Taylor et al., 2025). ISO 15118 (Road vehicles – Vehicle to grid communication interface) is the most complete standard governing V2G. It defines the digital communication protocol between the BEV<sup> 1</sup> and the EVSE<sup> 4</sup> (Electric Vehicle Supply Equipment, or charging station) (ISO 2019).

In Canada, The Electric Vehicle and Alternative Fuel Infrastructure Deployment Initiative was launched in 2016 by Natural Resources Canada, to attempt to promote fast EV charger development [^7]: . N.R Canada’s pilot program is aimed to assist organizations in constructing these large projects to assist in vehicle market electrification efforts in Canada.

While the Electric Vehicle and Alternative Fuel Infrastructure Deployment Initiative focuses on general charger rollout, Canada’s measure of V2G development lies in demonstration projects that test the grid-serving capabilities of EVs. These projects are primarily focused on demand response<sup> 7</sup> and grid resilience. Notable examples include the V2G-DR Pilot – Ontario, performed at Brock University by local grid operator Blackstone Energy Services Inc, and the Nova Scotia Vehicle Grid Integration Pilot, performed by Nova Scotia Power Inc (Canada, 2025a), (Canada, 2025b).

Implementation aligning with ISO 15118 in North America is currently based on the CCS<sup> 2</sup> charging standard. Other proprietary efforts based on the SAE J3400 standard have been implemented by operators such as Tesla Inc, but are not derived from ISO 15118. These efforts have not, and will not, receive federal funding from N.R Canada in the near future, as they are not currently standardized (Taylor et al., 2025). As the SAE J3400 standard continually evolves from Tesla Inc’s proprietary North American Charging Standard (NACS<sup> 3</sup> ), incorporation of ISO 15118 is a future possibility [^12]: , (Taylor et al., 2025). 

While regulation is continually developing, the primary focus for global bodies is on standardizing the communication protocols that enable V2X and V2G. This ensures interoperability across different manufacturers and grids.

Efforts by organizations like the SAE International and the European Telecommunications Standards Institute (ETSI) are focused on the communication layers (e.g., using cellular V2X or Dedicated Short-Range Communications) needed for vehicle-to-vehicle and vehicle-to-infrastructure safety and efficiency applications.

---
# Conclusion

Vehicle-to-Everything (V2X) technology, especially its grid operator-facing Vehicle-to-Grid (V2G) applications, is a rapidly developing sector with huge potential benefits for sustainable energy management and grid stability. Recent investment and expansion into the larger V2X ecosystem show interest in standard diversification, which lowers the barrier to entry for the mass market, signaling a promising area for continued investment and development.

However, to accelerate large-scale V2G adoption, further technological advancements are needed. Future development must focus on improving EV battery health management systems to mitigate concerns about accelerated degradation from frequent discharging cycles. Additionally, widespread adoption requires the urgent standardization of bidirectional charging hardware and communication protocols across different manufacturers and regions. Integrating smart, real-time algorithms to optimize discharge schedules based on predicted grid needs and user patterns will also maximize efficiency and acceptance.

The ultimate future prospect of V2X is entirely linked to economic sense; specifically, the financial incentives individuals would receive for actively assisting with grid management, along with improved uptime and reduced rates, among other benefits. While finding more consumer success in V2L, and V2H — V2G currently faces significant adoption hurdles, including high initial infrastructure costs, the need for extensive utility and regulatory coordination, and comprehensive standardization. While these factors present considerable challenges, it is entirely possible that large-scale V2G implementations will achieve widespread adoption once these regulatory and cost barriers are addressed through supportive policy and technological maturation.


--- 
## Glossary of Terms

###### BEV<sup> 1</sup>

Battery Electric Vehicle, as defined by Natural Resources Canada (2025) “A BEV is a type of EV that only uses electric motors and the energy stored in its rechargeable battery packs. It does not use an internal combustion engine (ICE).“ (N.R Canada, 2025)

###### CCS2<sup> 2</sup> 

The Combined Charging System, is the physical hardware standard for high-voltage direct current (DC) vehicle charging, primarily used in North America and Europe. It serves as the underlying platform that supports the advanced digital communication protocol defined by ISO 15118, enabling features like smart charging and Vehicle-to-Grid (V2G) functionality. In the above report, unless directly specified, all references to CCS refer to the Combo 1 configuration, standard in North America. CCS2 specified the European standard of CCS connectors.

###### SAE J3400 / NACS<sup> 3</sup> 

The North American Charging Standard, as labelled by Tesla, Inc. Colloquially known as the Tesla Supercharger. NACS is a proprietary standard, owned and operated by Tesla, Inc, however, is currently in the process of transitioning into the open standard SAE J3400. SAE J3400 which will be managed by international standards group, SAE Group (DesAulniers, 2024). 

###### EVSE<sup> 4</sup>   

Electric Vehicle Supply Equipment (EVSE) is the formal term for the charging station, wall box, or pedestal that connects a vehicle to the power grid. Its primary function is to serve as a critical safety and communication interface rather than just a power conduit. The EVSE regulates the electrical current delivered to the vehicle, ensuring safe transfer and code adherence. Crucially for V2X (Vehicle-to-Everything) applications, the EVSE contains the intelligence (compliant with ISO 15118) that allows it to communicate with the vehicle's onboard systems to negotiate charging rates. In the case of Vehicle-to-Grid (V2G) applications, EVSE manages the bidirectional flow of energy both into and out of the battery.

###### VRE<sup> 5</sup> 

Variable Renewable Energy is referred to as energy from wind and solar. This is due to their nature of availability. Depending on conditions such as cloud coverage, time of year, location, wind speed, etc, the energy output of these renewable sources can fluctuate. VRE sources need electrical storage systems in order to store energy when variable production is at its highest, and to supply the power when the generation is at its lowest. 

###### DDoS<sup> 6</sup> 

Distributed Denial-of-Service refers to a manner of cyberattack that attempts to disrupt the normal traffic of a targeted server, service, or network. The attack is carried out by overwhelming the host or surrounding infrastructure with HTTP request, UDP packets and DNS requests via numerous, possibly infected, nodes to amplify and reflect traffic to the host. 

###### Demand Response<sup> 7</sup>

Demand Response, in the context of Electric Vehicles, refers to the use of a vehicle's charging flexibility as a tool to balance and support the electricity grid by a local grid operator during periods of high grid load/stress. 

---

[^1]: Avery, D. (2025, February 9). Everything you need to know about bidirectional charging and which EVs support it. CNET. https://www.cnet.com/home/electric-vehicles/bidirectional-charging-and-evs-how-does-it-work-and-which-cars-have-it/

[^2]: Biswas, P., Rashid, A., Habib, A. K. M., Mahmud, M., Motakabber, S. M. A., Hossain, S., Rokonuzzaman, M., Molla, A. H., Harun, Z., Khan, M. M. H. (2025). Vehicle to Grid: Technology, Charing Station, Power Transmission, Communication Standards, Techno-Economic Analysis, Challenges, and Recommendations. World Electric Vehicle Journal. 16, 142. DOI: 10.3390/wevj16030142

[^3]: Brown, S., Pyke, D., & Steenholf, P. (2010). Electric vehicles: The role and importance of standards in an emerging market. Energy Policy, 38(7), 3797-3806. https://doi.org/10.1016/j.enpol.2010.02.05

[^4]: Byrne, D., Director Industry Marketing, & TTI Europe. (2017). An engineer’s guide to the DC Power train architecture of an electric vehicle. In TTI, Inc. TTI Europe, Inc. https://www.ttieurope.com/content/dam/ttiinc/resources/literature/TTIW018-DC%20power%20train%20architecture%20for%20EVs-EN-FINAL.pdf

[^5]: Cai, X., Song, R., Xie, B., Xiao, Q., & Xiao, B. (2025). PSP: A Privacy-Preserving Self-certify Pseudonym Protocol for V2X. Association for Computing Machinery, 651–664. https://doi.org/10.1145/3708821.3736212

[^6]: Canada, N. R. (2025, June 12). Types of zero-emission vehicles. Natural Resources Canada. https://natural-resources.canada.ca/energy-efficiency/transportation-energy-efficiency/zero-emission-vehicles/types-zero-emission-vehicles

[^7]: Canada, N. R. (2025a, October 21). Vehicle to Grid Demand Response (V2G-DR). Natural Resources Canada. https://natural-resources.canada.ca/funding-partnerships/vehicle-grid-demand-response-v2g-dr

[^8]: Canada, N. R. (2025b, September 26). Nova Scotia Vehicle Grid Integration Pilot. Natural Resources Canada. https://natural-resources.canada.ca/funding-partnerships/nova-scotia-vehicle-grid-integration-pilot

[^9]: CHAdeMO Association. (n.d.). Protocol Development. Retrieved December 2, 2025, from https://www.chademo.com/technology/protocol-development 

[^10]: Collins, I. (2018). Phase-Locked Loop (PLL) Fundamentals. In Analog Devices (Analog Dialogue 52-07,). Analog Dialogue. https://www.analog.com/media/en/analog-dialogue/volume-52/number-3/phase-locked-loop-pll-fundamentals.pdf

[^11]: Das, H.S., Rahman, M.M., Li, S., Tan, C.W., (2020). Electric vehicles standards, charging infrastructure, and impact on grid integration: a technological review. Renewable and sustainable energy reviews, 120, 1-27. https://doi-org.ezproxy.library.dal.ca/10.1016/j.rser.2019.109618 

[^12]: DesAulniers, P. A. (2024). National Charge: Canadian Federal EV Standards Regulation. https://reseau.cabot.place/Papers/nationalcharge

[^13]: Electric Vehicle and Alternative Fuel Infrastructure Deployment Initiative. (2023, October 27). Natural Resources Canada. Retrieved November 26, 2025 from https://natural-resources.canada.ca/energy-efficiency/transportation-alternative-fuels/infrastructure/electric-vehicle-alternative-fuels-infrastructure-deployment-initiative/18352

[^14]: Eltohamy, M. S., Tawfiq, M. H., Ahmed, M. M. R., Alaas, Z., Mohammed, B., Amhed, I., Youssef, H., Raouf, A. (2025). A comprehensive review of vehicle-to-grid (V2G) technology: Technical, economic, regulatory, and social perspectives. Energy Conservation and Management: X. (24). DOI: 10.1016/j.ecmx.2025.10113

[^15]: Fortune Business Insights. (2025). Vehicle-to-Grid (V2G) Market Size, share | Growth Report [2032]. In Fortune Business Insights (No. FBI107673). Retrieved November 29, 2025, from https://www.fortunebusinessinsights.com/vehicle-to-grid-v2g-market-107673

[^16]: Gideon Odogwu, I. (2020). Phase-Locked loop control in Low-Inertia grid- connected Voltage-Source converters. In Jack N. Averitt College of Graduate Studies. Georgia Southern University. https://digitalcommons.georgiasouthern.edu/cgi/viewcontent.cgi?params=/context/etd/article/3299/&path_info=Ifechukwude_odogwu_Revised_Thesis.pdf

[^17]: Goldberg, L. (2024, March 7) EV-Pluribus Unum: An Introduction to the SAE J3400/NACS EV Charging Interface (Part 1). Electronic Design. https://www.electronicdesign.com/markets/automotive/article/21284134/electronic-design-ev-pluribus-unum-an-introduction-to-the-sae-j3400-nacs-ev-charging-interface-part-1

[^18]: Gorine, A, & Agboile, C. (2024). Securing V2X communication: DDOS attack implementation and mitigation via VEINS simulation. International Journal of Multidisciplinary Research and Publications, Volume 7(Issue 3), SSN (Online): 2581-6187. https://ijmrap.com/wp-content/uploads/2024/08/IJMRAP-V7N3P60Y24.pdf

[^19]: ISO (2019, April). ISO 15118-1:2019. International Organization for Standardization. https://www.iso.org/standard/69113.html

[^20]: Kane, M. (2025, June 3) SAE Expands the J3400 Family of Standards With SAE J3400/2. EV Charging Stations. https://evchargingstations.com/chargingnews/sae-expands-the-j3400-family-of-standards-with-sae-j3400-2 

[^21]: Mafazy, M. (2022). Paving the Way - Vehicle-to-grid (V2G) standards for electric vehicles. IREC. https://irecusa.org/wp-content/uploads/2022/01/Paving_the_Way_V2G-Standards_Jan.2022_FINAL.pdf 

[^22]: Monteiro, V., Exposto, B., Pinto, J. G., Almeida, R., Ferreira, J. C., Melendez, A. a. N., & Afonso, J. L. (2014). On-board electric vehicle battery charger with enhanced V2H operation mode. Annual Conference of IEEE, 1636–1642. https://doi.org/10.1109/iecon.2014.7048722

[^23]: Mullan, J., Harries, D., Braunl, T., Whitely, S. (2012). The Technical, Economic, and Commercial Viability of the Vehicle-To-Grid Concept. Energy Policy (48) pg. 394-406. DOI: 10.1016/j.enpol.2012.05.042

[^24]: National Renewable Energy Laboratory. (2023). The 2030 National Charging Network: Estimating U.S. Light-Duty Demand for Electric Vehicle Charging Infrastructure. United States Department of Energy. https://www.nrel.gov/docs/fy23osti/85654.pdf 

[^25]: Nova Scotia Power. (2025). Standard residential service rate (domestic service tariff). https://www.nspower.ca/your-home/residential-rates/standard-residential-service-rate 

[^26]: Novan, K., & Wang, Y. (2024). Estimates of the marginal curtailment rates for solar and wind generation. Journal of Environmental Economics and Management, 124, 102930. https://doi.org/10.1016/j.jeem.2024.102930

[^27]: Papathanassiou, A., & Khoryaev, A. (2017, June). Cellular V2X as the essential enabler of superior global connected transportation services. IEEE Future Networks. Retrieved November 29, 2025, from https://futurenetworks.ieee.org/tech-focus/june-2017/cellular-v2

[^28]: Pod Point. (2025, June 13). Vehicle-to-Grid (V2G) Explained. pod-point.com. https://pod-point.com/guides/vehicle-to-grid-v2g-explained?srsltid=AfmBOopmJ0pe3Ic8Ai9X3oL2D-pjkvS1pBGqAxgWzmHopQ81uMyPYRO7 

[^29]: Powershare. (2024). Tesla. Retrieved November 18, 2025, from  https://www.tesla.com/en_ca/powershare 

[^30]: Sagaria, S., Kam, M., Bostrӧm, T. (2025). Vehicle-to-grid impact on battery degradation and estimation of V2G economic compensation. Applied Energy, 377(Part B). https://doi-org.ezproxy.library.dal.ca/10.1016/j.apenergy.2024.124546 

[^31]: Saldarriago-Zuluaga, S., Lopez-Lezama, J., Rios, C., Jaramillo, A. (2022). Effects of the Incorporation of Electric Vehicles on Protection Coordination in Microgrids. World Electric Vehicle Journal. 13(9), 163. DOI: 10.3390/wevj13090163

[^32]: Standardization Administration of China & State Administration for Market Regulation (SAMR - SAC) - People’s Republic of China. (2024). GB/T 33993-2024. In GB - National Standard (No. 33993–2024). Standardization Administration of China. https://std.samr.gov.cn/gb/search/gbDetailed?id=71F772D81822D3A7E05397BE0A0AB82A

[^33]: Shariff, M. S., Iqbal, D., Alam, M. S., Ahmad, F.  (2019). A State of the Art Review of Electric Vehicle to Grid (V2G) technology. IOP Conference Series: Materials Science and Engineering, 561 012103. DOI:10.1088/1757-899X/561/1/012103

[^34]: Taylor, I., McEwen, B., Turner, J., Goyal, M. (2025). Charging Ahead: Unlocking Vehicle-Grid Integration in Canada. Canadian Standards Association, Toronto, ON. 

[^35]: Texas Instruments. (2020). Grid Connected Inverter Reference Design. In Texas Instruments (TIDM-HV-1PH-DCAC). https://www.ti.com/lit/ug/tidub21d/tidub21d.pdf

[^36]: Texas Instruments. (2023). 1.6-kW, Bidirectional Micro Inverter Based on GaN Reference Design. In Texas Instruments (TIDA-010933). https://www.ti.com/lit/ug/tiduf63a/tiduf63a.pdf

[^37]: Wang, D., Saxena, S., Coignard, J., Iosifidou, E. A. (2016, July 17-21). Quantifying electric vehicle battery degradation from driving vs. V2G services. 2016 IEEE Power and Energy Society General Meeting, Boston, MA, United States.

[^38]: Yu, J., Zhang, Y., Ya, Z., Ye, H., Fu, W., Deng, H., Qian, Z., Tongji University, ARTS Group Co., Ltd, Fuzhou Polytechnic, & CSCEC AECOM Consultants Co., Ltf. (2025). A coordinated scheduling approach with electricity peak shaving capability for integrated Office Building-EV system. In SSRN. Elsevier. https://doi.org/10.2139/ssrn.5287732

[^39]: File:PWM, 3-level.svg — Wikimedia Commons. (2007, March 24). https://commons.wikimedia.org/wiki/File:PWM,_3-level.svg

