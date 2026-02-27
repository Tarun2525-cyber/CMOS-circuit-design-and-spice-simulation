
## BASICS OF NMOS DRAIN CURRENT(Id) vs DRAIN TO SOURCE VOLTAGE

   ## Intro to Circuit design and SPICE simulation:
   
   ## 0-L1 : Why do we need SPICE simulations:
 
* Logic gates are constructed by arranging PMOS and NMOS transistors in specific configurations to achieve outputs such as AND, NOR, NOT, and OR.
* By connecting these gates together, we can create fundamental circuits like inverters.
* In circuit design, we study how different combinations of PMOS and NMOS transistors influence the type of output produced.
* The graph below illustrates the characteristic curve of an NMOS transistor.
* For a PMOS transistor,the characteristic curve is the inverted version.

<img width="611" height="334" alt="Screenshot 2026-02-23 at 9 37 11 AM" src="https://github.com/user-attachments/assets/afa50862-0dec-4c46-a1a2-a259e3f7a53f" />

<img width="1103" height="845" alt="Screenshot 2026-02-20 at 11 18 22 AM" src="https://github.com/user-attachments/assets/e3e9985d-0421-4c7b-9f53-6ba72078a58b" />

* When you simulate these transistors in SPICE, you obtain switching curves like those shown above.
* The resulting waveforms are used to determine the delay of the transistor.
* To modify the delay, you can adjust the W/L ratio (width/length) of the transistors by changing either the width (W), the length (L), or both.

**SPICE** simulations are primarily conducted to analyze these delays for optimization purposes.
* Each cell (such as a buffer) has a delay table that relates the delay to two factors: input slew and output load.
* Every buffer has its own unique delay table because the individual transistor sizes and arrangements can vary from one buffer to another.

<img width="1393" height="872" alt="Screenshot 2026-02-20 at 11 57 40 AM" src="https://github.com/user-attachments/assets/1824d8b8-4f9b-4a9b-a929-901c2e12b9cd" />

For example, if a buffer’s output load is 60 fF and the input slew is 40 ps, you can use the delay table to determine that its delay falls between the values for 50 and 70 fF.
By referring to these tables, we can accurately estimate the delay of a cell based on its specific input and output conditions.


   ## 1-L2 Intro to Basic element in circuit design NMOS: 

## NMOS Transistor Structure and Operation: 
* NMOS is a four-terminal device consisting of:
* A p-type substrate (in contrast, PMOS uses an n-type substrate)
* Isolation regions
* Two n+ diffusion regions (one acts as the source, the other as the drain)
* Polysilicon gate
Gate oxide
Total 4 Terminals: G (Gate), S (Source), D (Drain), B (Body)

<img width="564" height="621" alt="Screenshot 2026-02-20 at 12 05 09 PM" src="https://github.com/user-attachments/assets/1174926c-13a9-4bd6-8726-d091823ad62c" />
Threshold Voltage (V<sub>t</sub>) in MOSFETs

* The threshold voltage (V<sub>t</sub>) is a key parameter in MOSFET operation.
* **Accumulation** in NMOS (V<sub>g</sub> < 0)
<img width="1345" height="450" alt="Screenshot 2026-02-20 at 12 09 52 PM" src="https://github.com/user-attachments/assets/ee1683fa-8cc0-4320-8938-ed7f16d7ac19" />
## When the gate voltage is negative:
* Holes (majority carriers in p-type substrate) are attracted toward the oxide.
* Hole concentration increases near the surface (accumulation).
## Depletion in NMOS (Small Positive V<sub>g</sub>)
* When the gate voltage is small and positive:
* Positive voltage repels holes away from the oxide.
* Only negative charges remain, creating a region with fixed negative charge.
* This area, lacking mobile carriers, is known as the depletion region.
## Inversion in NMOS (V<sub>g</sub> > V<sub>t</sub>)
* When the gate voltage exceeds the threshold voltage (V<sub>t</sub>):
* A strong positive voltage attracts electrons (minority carriers) to the surface.
* These electrons gather at the oxide–semiconductor interface, forming an n-type inversion layer.

## 2-L3 Strong Inversion and Threshold Voltage:
  
   ## Depletion and Inversion in NMOS
* At the interface between the n+ region and the p-type substrate, a depletion region forms.
* When a positive voltage is applied to the gate, the region near the interface loses its majority carriers (holes), becoming depleted.
* Applying a high positive gate voltage causes strong inversion:
* Negative charges in p substarte are attracted to the surface.
* A narrow surface region accumulates these electrons—this is known as **strong inversion**.
<img width="1345" height="450" alt="Screenshot 2026-02-20 at 12 09 52 PM" src="https://github.com/user-attachments/assets/ee1683fa-8cc0-4320-8938-ed7f16d7ac19" />

* The specific gate voltage at which strong inversion occurs is called the threshold voltage (V<sub>t</sub>).
* Increasing the gate voltage further does not result in more attraction or repulsion, as there are no additional majority or minority carriers left to affect.
* Negative charges from the n+ source region move toward the gate, widening the channel, while the depletion region width remains unchanged.
* A conductive channel forms from source to drain; applying a voltage between source and drain allows current to flow through this channel.
  
## Effect of Body Terminal on Threshold Voltage
*The body terminal also influences the threshold voltage of the MOSFET.

Consider these two scenarios:

<img width="1208" height="547" alt="Screenshot 2026-02-22 at 10 36 52 AM" src="https://github.com/user-attachments/assets/c191b425-9b1c-4bb1-b0a5-06e152df6565" />

* No voltage applied to the body terminal
* Body terminal connected to the source
In the second scenario, the depletion region is larger because the body-source connection creates an additional reverse bias, increasing the depletion width.
As a result, inversion in the second case occurs at a higher gate-to-source voltage compared to the first scenario.


   ## 3-L4: Threshold voltage with positive substarte potential: 
   
 <img width="1349" height="871" alt="Screenshot 2026-02-22 at 10 45 03 AM" src="https://github.com/user-attachments/assets/9d6c5779-38c1-4215-8269-a5d4e0e86542" />
 
* When the n+ source is connected to a positive terminal, negatively charged particles (electrons) are more strongly attracted and accumulate near the source.
* The accumulated -ve charge are pulled through the source region.
* For a specific gate voltage, inversion (formation of the conductive channel) occurs in the first scenario, while in the second scenario (with body-source potential), the channel formation is more gradual (ascending order).
* This demonstrates that an additional potential is needed for strong inversion when there is a voltage difference between the body and source.
* The threshold voltage equation for the MOSFET is:

<img width="732" height="339" alt="Screenshot 2026-02-22 at 10 55 23 AM" src="https://github.com/user-attachments/assets/6acab037-69de-4446-8cf4-6b148cbcd025" />
The following equations represent the MOSFET operation and relationships:

<img width="490" height="287" alt="Screenshot 2026-02-22 at 10 56 33 AM" src="https://github.com/user-attachments/assets/dfec0c88-4141-4b36-b512-e5e38ba82077" /> <img width="581" height="167" alt="Screenshot 2026-02-22 at 10 56 52 AM" src="https://github.com/user-attachments/assets/b2cb88c4-7fb2-4adf-8235-ad65be31cb82" />


## NMOS Resisitve region and saturation region of operation:

* Resistive Operation of NMOS
* When V<sub>GS</sub> > V<sub>T</sub>, a more conductive region is formed in the channel.
* As V<sub>GS</sub> increases, the channel width increases because the number of induced charges is directly proportional to (V<sub>GS</sub> - V<sub>T</sub>).
* If a small drain-to-source voltage (V<sub>DS</sub>) is applied, for example V<sub>GS</sub> = 1V, V<sub>DS</sub> = 0.05V, and V<sub>T</sub> = 0.45V:
* Since V<sub>GS</sub> > V<sub>T</sub>, a conductive channel is formed and current can flow.
  
<img width="870" height="739" alt="Screenshot 2026-02-22 at 11 33 13 AM" src="https://github.com/user-attachments/assets/8e1130a2-32ad-4e6c-a945-f6dd32bcc492" />

* Before applying V<sub>DS</sub>, the voltage is uniform across the channel.
* After applying V<sub>DS</sub>, a voltage gradient develops along the channel, so the potential varies at different points (lengths) of the channel.
* The channel length is greater than the effective channel length (L).
* After applying V<sub>DS</sub>, the voltage at any point x along the channel becomes (V<sub>GS</sub> - V<sub>x</sub>) instead of just V<sub>GS</sub>.

  
## 5L-2 :Drift current theory :

* Induced Charge and Current Mechanisms in the Channel
* The induced charge at any point x in the channel is given by:
* Q<sub>i</sub>(x) = -C<sub>ox</sub> * ([V<sub>GS</sub> - V(x)] - V<sub>T</sub>)
  
<img width="418" height="137" alt="Screenshot 2026-02-22 at 11 41 18 AM" src="https://github.com/user-attachments/assets/d4ce8fbf-2442-4d12-8c89-76b158451dd5" />

## There are two types of current in the channel:

**Drift current**: Due to the potential difference (voltage gradient) across the channel.

**Diffusion current**: Due to the difference in carrier concentration.

* In the channel, drift current dominates because there is a potential gradient when V<sub>DS</sub> is applied.
*The drift current equation [I<sub>D</sub>] is based on the product of the velocity of charge and the available charge, divided by the channel width.


## 6 L-3 Drain current model for linear region operaation:

* Drift Current Equation in NMOS
* The drift current in the channel is given by:
  I<sub>D</sub> = -V<sub>n</sub>(x) · Q<sub>i</sub>(x) · W

* Where V<sub>n</sub>(x) is the carrier velocity
 Q<sub>i</sub>(x) is the induced charge at position x
* W is the channel width
* The carrier velocity is:
* V<sub>n</sub>(x) = μ · E

* Where μ is the mobility and E is the electric field.
* To derive the current-voltage relationship for NMOS, you integrate dx over the channel length L.

* The drift current equation and further derivation steps are shown below:

<img width="1054" height="334" alt="image" src="https://github.com/user-attachments/assets/658f029e-9640-4229-a6b4-2a97ddd21585" /> <img width="942" height="120" alt="image" src="https://github.com/user-attachments/assets/6e655121-b888-46fa-b212-4cdf2211a176" /> <img width="1040" height="616" alt="image" src="https://github.com/user-attachments/assets/c571d9a2-0eb8-403a-9e39-4ee1b34d2475" />

* When V<sub>DS</sub> ≤ (V<sub>GS</sub> − V<sub>T</sub>), the MOSFET operates in the linear region, and the channel is continuous from source to drain.

## 7 L-4 Spice conclusion to resisitve operation

* Drain Current Characteristics and SPICE Simulation
* The drain current (I<sub>D</sub>) is a linear function of (V<sub>GS</sub> − V<sub>T</sub>).
* Both V<sub>GS</sub> and V<sub>DS</sub> impact the value of I<sub>D</sub>.
* By taking different values of V<sub>GS</sub> and sweeping V<sub>DS</sub> from 0 to 0.05 V, you can observe how I<sub>D</sub> changes.
* This entire process of sweeping and analyzing the output is performed using SPICE simulation.
  
<img width="544" height="619" alt="Screenshot 2026-02-22 at 12 15 49 PM" src="https://github.com/user-attachments/assets/0d314d7b-465c-4b53-9f79-4c1991ce50f0" />


## 8 L-5 Pinch off region condition:

 
**NMOS Saturation Region and Pinch-Off Phenomenon**

* When V<sub>DS</sub> > (V<sub>GS</sub> − V<sub>T</sub>), the MOSFET enters the saturation region.
* In the example, V<sub>DS</sub> is increased from 0.05 V up to 0.45 V. During this range, V<sub>GS</sub> − V<sub>DS</sub> is still greater than V<sub>T</sub>.
* If V<sub>DS</sub> increases further so that V<sub>GS</sub> − V<sub>DS</sub> = V<sub>T</sub>, a significant change occurs:
* The channel near the source is strongly inverted (V = 1 V), but near the drain (V = 0.45 V) it is only just inverted.
* The channel shape appears as shown below:
* 
<img width="577" height="542" alt="Screenshot 2026-02-22 at 12 24 02 PM" src="https://github.com/user-attachments/assets/6824c0e1-43e8-4fbc-8247-12aa08e7a4fc" />

* The point where the channel disappears near the drain is known as the "Pinch-Off Phenomenon".
  
* When V<sub>DS</sub> increases further and V<sub>T</sub> > (V<sub>GS</sub> − V<sub>DS</sub>), the channel vanishes at the drain end, and the device is fully in the saturation region.
  
<img width="1032" height="332" alt="image" src="https://github.com/user-attachments/assets/4d13c065-357e-4d13-914b-75adacd9e1ce" />


## 9 L-6: Drain current model for saturation region of operation


**Drain Current in Saturation and Channel Length Modulation**

* In the saturation region, the channel voltage remains constant.
* The channel length is modulated by V<sub>GS</sub> and is no longer a function of V<sub>DS</sub>.
* The previously derived drain current (I<sub>D</sub>) equation is:
  
<img width="618" height="120" alt="image" src="https://github.com/user-attachments/assets/1ec958e4-d34f-4aa0-bd93-112c57a2b837" /> <img width="946" height="214" alt="image" src="https://github.com/user-attachments/assets/33c92b44-20eb-431c-8205-afa2082fe5c7" />

* Drain current in saturation is a function of various constants (device parameters and applied voltages).
* The effective conductive channel length is influenced by the applied V<sub>DS</sub>:
* As V<sub>DS</sub> increases, the depletion region at the drain widens, which reduces the effective channel length.
* For a more accurate model, the effect of channel length modulation is included by introducing the parameter λ (lambda).



## Introduction to SPICE
   ## 10 L-1 Basic SPICE setup:
* we have understood what Threshold Voltage, Body Effect, and SPICE Simulation Parameters are and 
* We have explored several equations involving threshold voltage, body effect coefficient, and Fermi level. These parameters must be accurately defined to ensure correct simulation results.
* The linear region drain current equation provides the best approximation for drain current in that region.
* For advanced (lower technology node) processes, the technology constants are specified by the industry and should be directly used in simulations.
  
<img width="1328" height="627" alt="Screenshot 2026-02-23 at 10 01 02 AM" src="https://github.com/user-attachments/assets/b71cfa10-df1e-4f61-99b0-53e7d72e233a" />

* The parameters marked in yellow are the key SPICE model parameters.

* The SPICE setup for simulating MOSFET behavior should look like the examples below:

<img width="688" height="631" alt="Screenshot 2026-02-23 at 10 04 32 AM" src="https://github.com/user-attachments/assets/93a9948a-3bd6-4129-8086-663caad138cb" />
<img width="579" height="397" alt="Screenshot 2026-02-23 at 10 06 58 AM" src="https://github.com/user-attachments/assets/3fad0478-d8be-4866-8bcf-2003e7562a97" />

## 11 L-2 Circuit description in SPICE syntax

## How to Start a SPICE Simulation
* Define Nodes
  
<img width="753" height="622" alt="Screenshot 2026-02-23 at 10 09 31 AM" src="https://github.com/user-attachments/assets/0968afdb-7ab7-4f9d-9d1e-8598cb9f6dd8" />

* You can assign any names to the nodes.
* The typical nomenclature for defining components in SPICE is:
* For MOSFETs:
* Component Name, Drain, Gate, Source, Substrate, MOSFET Model Name (from technology file), Width, Length
* For Resistors: R1, First Terminal, Second Terminal, Resistance Value
* For Voltage Sources (Vdd, Vin): Vdd, First Terminal, Second Terminal, Value
* Vin, First Terminal, Second Terminal, Value
* Example of SPICE netlist naming conventions:
* 
<img width="667" height="220" alt="Screenshot 2026-02-23 at 10 16 12 AM" src="https://github.com/user-attachments/assets/45a48be3-d185-425c-966d-3021ba6b4801" />


## L3 define technology parameters:

## Technology File in SPICE
* All model parameters are provided together as a package in a technology file.
* To use the technology file in your simulation, include it as shown below:

<img width="609" height="373" alt="Screenshot 2026-02-23 at 10 21 37 AM" src="https://github.com/user-attachments/assets/4897324c-860c-4b9d-b384-66ccb08415d4" />

* Save the technology model parameters as a .mod file:

<img width="870" height="606" alt="Screenshot 2026-02-23 at 10 23 30 AM" src="https://github.com/user-attachments/assets/44ce9d45-ba71-4b09-a8e7-d536fc26cd1e" />

* After including the technology file, you need to add simulation commands to your SPICE netlist.


## 13 L-4 First SPICE Simulation: 
* Clone the Sky130 repository and navigate into its directory to access all SPICE resources:
* Device cell definitions
  
* Complete process technology information

* Each has separate model files for different corners.
* These models define parameters like mobility, threshold voltage (VT), channel length modulation (λ), etc.
* Sky130 only supports certain W/L combinations (for example, 1.26 µm / 0.15 µm).
* Using unsupported width or length values will result in SPICE simulation errors.
* To use the correct model in your netlist:

* MOSFET device definition in SPICE: Mname D G S B model W=<width> L=<length>
* For NFETs, connect the bulk (B) terminal to ground.
* For PFETs, connect the bulk (B) terminal to VDD.
* Run simulations using ngspice:
* Use commands like plot I(M1) to view drain current trends.
* Analyze the I<sub>D</sub>–V<sub>DS</sub> curves to observe linear and saturation region behavior
<img width="1612" height="912" alt="image" src="https://github.com/user-attachments/assets/37c5e0f9-226c-4943-a9b3-22d096753b3f" />
<img width="1378" height="1088" alt="image" src="https://github.com/user-attachments/assets/d7a0f238-226c-4c5d-86c6-9d47dd2044c0" />


## 14 L-5 SPICE lab with sky130 models :
* Exploring the Models Folder in Sky130
* Inside the models folder of the Sky130 repository, you’ll find a file named all.spice.
* Opening all.spice reveals the supported scales of Width (W) and Length (L) for the transistors.
* These values indicate which W/L combinations are allowed for simulation using the Sky130 PDK.

<img width="1656" height="1088" alt="image" src="https://github.com/user-attachments/assets/4d72dec0-4695-46be-b204-80d8a4f72afb" />

<img width="1600" height="923" alt="image" src="https://github.com/user-attachments/assets/a798f9d4-73ac-41e8-9879-111ca598bf51" />

**disclaimer: "These the above plots are done in cloud but the rest after 15 L-1 are done in virtual machines as cloud based was frequently logging out.**

## Velocity Saturation and Basics of CMOS Inverter VTC:
   ## SPICE simulation for lower nodes and velocity saturation effect:
   ## 15 L-1  :

##  ID–VDS Characteristics and Short-Channel Effects
* ID–VDS curves were plotted for VGS = 0, 1.0, 1.5, 2.0, and 2.5 V:
* 
<img width="2002" height="1298" alt="image" src="https://github.com/user-attachments/assets/347a1ef5-36d9-48be-bdf8-c15e60fc78c7" />

* At VGS = 0 V, the device remains in cutoff (ID ≈ 0).
* For low VDS, ID increases linearly—this is the linear region.
* When VDS ≥ (VGS − VT), the curves flatten out, indicating entry into the saturation region, as seen in the figure below:
  
<img width="1790" height="1066" alt="image" src="https://github.com/user-attachments/assets/f57d6bf2-d817-45d9-a960-964984218631" />

* The slight slope in the saturation region is caused by channel-length modulation.
* For a short-channel device (L = 0.25 µm), you observe: Higher ID values
* Stronger channel-length modulation effects
* Reduced spacing between curves, mainly due to mobility degradation and velocity saturation
* Even with the same W/L ratio, short-channel effects cause deviation from the ideal square-law behavior.



## 16 L-2 
## Drain current vs Gate voltage for long and short channel devices
* Observation on how drain current (ID) responds to changes in gate voltage (VGS) for long and short MOSFETs, with VDS fixed at 2.5 V.

<img width="1030" height="499" alt="Screenshot 2026-02-24 at 11 42 51 AM" src="https://github.com/user-attachments/assets/d6141e30-bf00-4bd7-b84f-0d8598d47099" />

* For the long-channel MOSFET (L = 1.2 µm), the ID–VGS curve is smooth and curved (parabolic).
* For the short-channel MOSFET (L = 0.25 µm), the curve starts curved but quickly becomes a straight line as VGS goes up.
* This happens because, in short devices, electrons reach their top speed (velocity saturation) much sooner.
* So, short-channel MOSFETs provide more current, but the relationship between ID and VGS is more linear, not curved.
* As MOSFETs get shorter, their behavior changes, so we need better models to predict how they work.



## 17 L-3  : 
   ## Velocity saturation at lower and higher electric fields
   
## ID–VGS Curves: Long vs. Short Channel MOSFETs
* Sweeping VGS from 0 to 2.5 V at a fixed VDS = 2.5 V gives the following ID–VGS curves for both long- and short-channel MOSFETs:

<img width="1081" height="532" alt="Day 2 lec3 " src="https://github.com/user-attachments/assets/c580e84b-95dc-462d-8097-5338ac39ca91" />

* Long-channel MOSFETs (blue curve) follow ideal square-law behavior:
* ID ∝ (VGS – VT)² across the whole range.
* Short-channel MOSFETs (green curve) start off quadratic at low VGS, then quickly shift to a straight-line (linear) rise at higher VGS.
* This change happens because, in short-channel devices, the electric field gets so high that carriers reach their saturation velocity (VSAT) much sooner.
* Once velocity is saturated, raising VGS only increases the amount of charge—not the speed of carriers—so ID rises linearly with VGS.
  
<img width="814" height="418" alt="day 2 lec 3 1" src="https://github.com/user-attachments/assets/fe5dbd6c-a91b-4f16-a62d-3b41c604a283" />

* The point where this transition occurs is related to the critical electric field (EC = VSAT / μn).
* Modern models use a unified approach (with Vmin = min(VGT, VDS, VDSAT)) to describe all regions of operation, including velocity saturation.
  
<img width="540" height="342" alt="day 2 lec 3 2" src="https://github.com/user-attachments/assets/e6602371-f669-4ccf-8fc9-a806e781859a" />

* Short-channel MOSFETs now have four regions: cutoff, linear, classical saturation, and velocity saturation.
* Velocity saturation dominates in deep-submicron devices and breaks the old square-law assumption.
* In summary:
               Long-channel: ID–VGS curve stays curved (quadratic).
               Short-channel: ID–VGS curve turns linear at high VGS due to velocity saturation.



## 18 L-4 Velocity Saturation Drain current Model:

* The unified MOSFET model uses:
                                  VGT = VGS − VT
                                  Vmin = min(VGT, VDS, VDSAT)
* This approach lets one equation describe all regions: cutoff, linear, saturation, and velocity saturation.
How it works:
* If VGT < 0, the MOSFET is off (ID = 0).
* If VGT ≥ 0, the drain current (ID) is calculated using VGT and Vmin.
* Vmin = VGT: Device is in saturation (long-channel), and ID ∝ VGT².
* Vmin = VDS: Device is in the linear region, and ID grows with VDS.
* Vmin = VDSAT (short-channel): Device is in velocity saturation, so ID grows linearly with VGS.

<img width="798" height="445" alt="day 2 lec 4 1" src="https://github.com/user-attachments/assets/35f47b7b-3ec1-43cf-ad27-efd7bd4ff9e6" />
<img width="665" height="168" alt="day 2 part 1 lec 4 1" src="https://github.com/user-attachments/assets/c4db46d9-3e40-433c-afd2-fee0a5dec917" />
<img width="669" height="355" alt="Screenshot 2026-02-25 at 10 54 26 PM" src="https://github.com/user-attachments/assets/1f2b6bb6-0328-4686-8692-1ad892b2148c" />
<img width="613" height="338" alt="Screenshot 2026-02-25 at 10 54 42 PM" src="https://github.com/user-attachments/assets/c6decd5b-d93f-48ad-9b80-51d3d30f99a6" />
<img width="632" height="364" alt="Screenshot 2026-02-25 at 10 54 55 PM" src="https://github.com/user-attachments/assets/b4713d07-ef68-42a9-9fa3-4f2bf037d562" />
<img width="620" height="295" alt="Screenshot 2026-02-25 at 10 55 05 PM" src="https://github.com/user-attachments/assets/587a2303-c4a6-495c-af04-1c3a3f6e656a" />

* In velocity saturation, carrier speed hits its max—so extra VGS just adds charge, not speed, resulting in a flatter ID curve.
* Short-channel devices reach velocity saturation earlier, so they show lower peak currents, even with the same W/L ratio.
* same in this observation we have ,the saturation current for lower nodes is low instead of being high. This is because Velocity saturation tends to saturate the device early so the peak current we see for lower nodes is much lesser than for higher nodes.


## 19 L-5 Labs sky130 Id vs Vgs :

* A short-channel MOSFET (W = 0.39 µm, L = 0.15 µm) was simulated with VDS and VGS swept up to 1.8 V.
* ID–VDS curves: pics here
  imgs
* Show a quadratic rise at low VDS.
* Quickly switch to a straight-line (linear) increase as VDS grows, due to early velocity saturation at this short channel length.
* At VGS = 1.8 V, the peak current is ~196 µA—much less than a long-channel device with the same W/L.
* ID–VGS sweep (at VDS = 1.8 V):
* The curve is almost fully linear, with barely any quadratic region.
* This is because VDSAT is very small for L = 0.15 µm. The device immediately enters velocity saturation (Vmin = VDSAT)
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7a9ef779-3cb9-4574-9f30-8c8e74c26d77" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/80a4b7c2-ebdd-44a2-aaca-70ae57df9b29" />

## 20 L-6 Lans sky130 V<sub>t</sub>:
* The ID–VGS curve at VDS = 1.8 V rises steeply near threshold, even though the rest of the curve is linear due to strong velocity saturation.
* Drawing a tangent along the steepest part of the curve and extending it to the VGS axis allows you to extract the threshold voltage (VT).
* This method gives VT ≈ 0.77 V, matching the expected turn-on point for a 0.15 µm short-channel MOSFET.
* This works because the initial turn-on still follows the square-law (ID ∝ (VGS − VT)²) before velocity saturation dominates.
* These results—early threshold, immediate velocity saturation, and linear current growth—confirm the key characteristics of short-channel device behavior.
  
  <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5a12a8e4-c45b-48f5-9916-61126a7b506e" />

  <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/47034736-d5ff-4b10-aafa-b88f5b2fde04" />

## CMOS Voltage Transfer Characteristics:

## 21 L-1 MOSFET as Switch:
* MOSFET as a Digital Switch & CMOS Inverter Basics
* At this point, a MOSFET can be understood more as a digital switch than an analog device, which is helpful for CMOS logic.
  
<img width="262" height="262" alt="day 2 part 2 lec1" src="https://github.com/user-attachments/assets/65273a2e-e1c2-453b-adce-630491f1e693" />
 
* A MOSFET turns ON when its gate-to-source voltage (|VGS|) is greater than its threshold (|VT|), and stays OFF otherwise.
* The rule |VGS| ≥ |VT| works for both NMOS and PMOS.
* A CMOS inverter consists of a PMOS on top and an NMOS on the bottom, both controlled by the same input and sharing a common output:
  
<img width="422" height="410" alt="day 2 part 2 lec 1 1" src="https://github.com/user-attachments/assets/d31603c4-b619-4c85-8b3a-0f1208994e0f" />

* When the input is high:
                        The NMOS turns on conversely The PMOS turns off
* The output is pulled down to ground, inverting the input signal
* This switch-based view makes it easy to build the inverter truth table and later analyze the Voltage Transfer Characteristic (VTC) for CMOS logic gates.
  

## 22 L-2 Introduction to standard voltage current parameters :
* To construct the CMOS inverter’s VTC, start by examining the two extreme input cases: VIN = VDD and VIN = 0. In both cases, replace each transistor with its ON/OFF switch equivalent.
* When VIN = VDD (input high):

* The NMOS turns ON and acts like a resistive path to ground.
* The PMOS turns OFF.
* The output node discharges through the NMOS until it reaches 0 V.
* When VIN = 0 (input low):

* The PMOS turns ON and conducts like a resistor to VDD.
* The NMOS turns OFF.
* The output node charges up to VDD through the PMOS.
* The ON resistances, RN for NMOS and RP for PMOS, are not constant—they depend on the operating region of each device. These resistances will affect the shape of the VTC and the inverter’s rise/fall delays.

* To analyze switching transitions, we assign voltage and current labels (like VGSN, VGSP, VDSN, IDSN, IDSP, etc.) to both transistors, so their operation can be examined together.

<img width="1055" height="643" alt="day 2 part 2 lec 2 1" src="https://github.com/user-attachments/assets/ab209730-72dc-4d8c-9788-bebb21f84644" />

* With the two boundary cases and naming conventions established, the next step is to solve both transistor equations at once. This allows us to find the switching point where NMOS and PMOS currents are equal—the heart of the VTC.


## 23 L-3 PMOS/NMOS Drain current vs Drain Voltage :

* Before we start deriving the VTC for a CMOS inverter, let’s get our voltage names straight:
* For NMOS, we use VGSN (gate-to-source voltage) and VDSN (drain-to-source voltage).
* For PMOS, we use VGSP and VDSP. PMOS voltages come out negative, so it’s important to use different symbols to avoid confusion.
* 
<img width="356" height="301" alt="day 2 lec 3 1" src="https://github.com/user-attachments/assets/6f2ee424-4328-4e85-b838-297b958b90a7" />

<img width="322" height="190" alt="day2 lec 3 1 5" src="https://github.com/user-attachments/assets/a6dc199e-97b5-47ae-bc7f-bceaebd29dce" />

* NMOS pulls current up through the output (when discharging).
* PMOS pushes current down (when charging).
* The relationship between them is: IDSP = –IDSN. This is really important for figuring out the VTC.
* For NMOS:
          VGSN = VIN (because the source is at ground)
          VDSN = VOUT
* For PMOS:
          Both VGS and VDS are negative (since the source is at VDD).
  
<img width="713" height="441" alt="day 2 lec 3 2" src="https://github.com/user-attachments/assets/1487ff52-0145-4c42-bb17-ba564e8d5665" />

* plot the NMOS load curve (IDSN vs VDSN) and the PMOS load curve (IDSP vs VDSP). The PMOS curve is basically a mirror of the NMOS curve in the negative direction.


## 24 L-4 Step1 - Convert PMOS gate-source voltage to Vin :

* In a CMOS inverter, there are four transistor voltages (VGSN, VDSN, VGSP, VDSP) and two currents (IDSN, IDSP), but in digital logic, we care about only VIN and VOUT.
* To get the VTC (VOUT vs VIN), we rewrite all PMOS and NMOS voltages in terms of VIN and VOUT.
* First, we convert the PMOS gate voltage using VIN = VGSP + VDD, so everything is on the VIN axis.
* Next, since PMOS current flows opposite to NMOS, we use IDSN = –IDSP to plot both on the same current axis.
* This lets us directly compare NMOS and PMOS load curves using just VIN and IDSN.
  
<img width="1088" height="764" alt="day 2 lec 4 " src="https://github.com/user-attachments /assets/4b97d6dc-43f8-4607-8f01-ed040b18c7c5" />
   
* The VTC is found where NMOS and PMOS currents are equal (intersection point).



## 25 L-5 Step2 & 3 Convert PMOS and NMOS drain source voltage to Vout:

* Both PMOS and NMOS devices are described only by VIN, VOUT, and IDSN—perfect for deriving the CMOS inverter VTC.
  
<img width="1074" height="755" alt="day 2 lec 5 2" src="https://github.com/user-attachments/assets/095fcfba-eee6-4c5b-aa90-e7616cebcee9" />
<img width="692" height="673" alt="day 2 lec 5 3" src="https://github.com/user-attachments/assets/76767468-5894-4ced-b73f-6d63f4c74ec4" />

* The key step is rewriting the PMOS drain voltage as VDSP = VOUT – VDD, so now every PMOS data point is just (VIN, VOUT, IDSN).
* For NMOS, it’s even easier: VGSN = VIN, VDSN = VOUT—the NMOS I–V curve already maps to (VIN, VOUT, IDSN).
* Now, both PMOS and NMOS load curves are in the same format and ready to be combined to find the VTC.
  
<img width="1079" height="485" alt="day2 lec 5 4" src="https://github.com/user-attachments/assets/1a0a40f3-5452-4f83-b5d7-bfc054162d0c" />


## 26 L-6 Merge PMOS and NMMOS Load curves and plot VTC:

* The CMOS VTC is created by overlaying the NMOS and PMOS load curves and finding where their currents are equal.
* With both curves expressed as IDSN(VIN, VOUT), you simply look for their intersection at each VIN to get the corresponding VOUT.
* As VIN sweeps from 0 to 2 V, the intersection points move from VOUT = 2 V (output high) to VOUT = 0 V (output low).
* The sharp transition—the inverter’s “switch”—happens around VIN ≈ 1 V when both transistors are in saturation.
* Connecting these intersection points creates the classic S-shaped VTC curve.
* This method also shows which region (cutoff, linear, saturation) each device is in for every value of VIN, which is useful for analyzing gain, noise margins, and delay.
  
<img width="663" height="318" alt="day2 lec 6  1" src="https://github.com/user-attachments/assets/4a5cf6a8-c1c4-47e7-8424-138e9a57b635" />
<img width="1073" height="765" alt="day lec 6 2" src="https://github.com/user-attachments/assets/200a399c-3653-4b62-9d94-041fd4d1f8dd" />







## CMOS Switching threshold and dynamic simulations:
   ## Voltage transfer characteristics – SPICE simulations:
   ## 27 L-1 SPICE deck creation for CMOS inverter:
   
* This lecture starts the hands-on part: setting up a clean SPICE netlist for the CMOS inverter VTC.
* PMOS at the top (connected to VDD)
* NMOS at the bottom (connected to ground)
* Both gates connected to the input, drains tied together at the output, and bodies tied to their respective supplies.
  
<img width="1057" height="475" alt="day 3 lec 1 " src="https://github.com/user-attachments/assets/ae59d945-8909-4bef-8852-3a71c145855a" />

* Substrate (body) connections are important in SPICE since they affect threshold voltage via the body effect.
* For this demo, both PMOS and NMOS use W = 0.375 µm and L = 0.25 µm (real designs usually make PMOS wider).
* A 10 fF load capacitor is added at the output, VDD = 2.5 V, and VIN will sweep from 0 to 2.5 V.
  
<img width="606" height="446" alt="day 3 lec 2 " src="https://github.com/user-attachments/assets/fdd77b87-f59f-400a-9455-7cc240e6a124" />


## 28 L-2 SPICE simulation for CMOS inverter:

* now, we focus on connectivity for both PMOS and NMOS in the inverter.
* PMOS (M1) connections:
                        Drain terminal: connected to OUT (output), Gate terminal: connected to IN (input), Source and substrate: connected to VDD
* NMOS (M2) connections:
                        Drain: connected to OUT, Gate: connected to IN, Source and substrate: connected to 0 (ground)
Device dimensions for both: W = 0.375 µm, L = 0.25 µm
* Connectivity summary:
                      Output load capacitor: connected between OUT and 0
                      Supply voltage: VDD (between VDD and 0)
                      Input voltage (Vin): applied between IN and 0
* SPICE simulation commands:
                             .op for operating point
                             .dc Vin 0 2.5 0.05 (sweeps Vin from 0 V to 2.5 V in 0.05 V steps)
* Output voltage (VOUT) is measured for each input value
* Model file:
              The included model file (e.g., tsmc_025um_model.mod) contains all process information: oxide thickness, threshold voltage, and other coefficients.

<img width="1407" height="633" alt="Screenshot 2026-02-26 at 12 41 08 AM" src="https://github.com/user-attachments/assets/1a0062ea-af30-4998-a38e-cfaa97eda695" />

* Plotting & Results:
* Set up the plot to show DC characteristics: plot OUT vs IN.
* The transfer curve may be slightly shifted to the left.
* Width variation experiment:
* New simulation: WN = 0.375 µm, WP = 0.9375 µm, Ln = Lp = 0.25 µm (WP is now 2.5 times wider than NMOS).
  
<img width="445" height="332" alt="image" src="https://github.com/user-attachments/assets/12b24c65-ffea-49e9-8569-cb2884351d7b" />
<img width="441" height="340" alt="image" src="https://github.com/user-attachments/assets/4ec7230a-36df-4004-9f12-02a0971723ca" />

  

## 29-L3 Labs Sky130 SPICE simulation for CMOS:
* Device sizing:
                PFET width (Wp): 0.84 μm, NFET width (Wn): 0.36 μm
W/L ratio: 2.3 (for both, with same length)
* DC Analysis:
              Sweep input (Vin): from 0 V to 1.8 V, in steps of 0.01 V
* Plot: Vout vs Vin to get the inverter transfer curve
* Switching threshold: Where Vout = Vin, found at 0.876 V for this W/L ratio
* Transient Analysis:
                     Input waveform: Use a pulse source for Vin, Rise time: 0.1 ns, Fall time: 0.1 ns, Pulse width: 2 ns
* Plotting Vout vs time to observe the inverter’s dynamic response to a switching input

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/faaee55e-8652-4584-b3d1-2d185aff1b9a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0cdf3bb1-6983-47e3-ac58-e33e3c1caebf" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/a2daf822-76dd-4bca-a7bf-29b7da2d233a" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/538522fe-d570-4856-9c86-05e27f09b4cd" />


## Static behaviour evaluation -CMOS inverter robustness- switching threshold

## 30 L-1 Switching Threshold Vm:

* Comparison setup for :
                        NMOS width (Wn): 0.375 µm
                        PMOS width (Wp): 0.935 µm
* Observation:
* The shape of both inverter VTC (Voltage Transfer Characteristic) graphs is the same.
* This shows that the CMOS inverter is robust: when Vin is low, Vout is high, and when Vin is high, Vout is low—the classic inverter behavior.
* This symmetry and reliability are key reasons why CMOS logic is widely used in digital applications.

<img width="2800" height="1432" alt="image" src="https://github.com/user-attachments/assets/df754287-9a07-4273-b054-375ec03b1fb4" />

* Parameters Defining CMOS Robustness
* Switching Threshold
* The point where Vin = Vout on the transfer curve.
* This is often marked by the intersection point on the graph.

<img width="2696" height="1256" alt="image" src="https://github.com/user-attachments/assets/4549b915-714d-40f0-98d2-42735ec7ed1e" /> 

<img width="2824" height="1226" alt="image" src="https://github.com/user-attachments/assets/f31c9b7b-fab0-4dd1-8bb4-fc8966a4b862" />


## 31 L-2 Analytical expression of Vm as a function of (W/L)p and (W/L)n:
Here Switching Threshold (VM)
* Vm is where VIN = VOUT.
At this voltage, the inverter output flips—this is the switching threshold.
At Vm:
        * IDSP + IDSN = 0 (by KCL at the output)
* NMOS and PMOS carry equal and opposite currents.
* VM affects:
            Noise margins, VTC symmetry, CMOS gate behavior
2. Conditions at Switching Threshold
* Devices operate near the velocity saturation region.
* At switching: VDS ≈ VGS, so use velocity-sat current equations.
* Approximations: Ignore channel-length modulation (λ ≈ 0).
  
3. Drain Current Equations
* NMOS:
      IDSN = kn · (VM – VTn) · VDSATn – (VDSATn² / 2)
* PMOS:
       VGSP = VM – VDD
       IDSP = kp · (VGSP – |VTp|) · VDSATp – (VDSATp² / 2)

<img width="1358" height="834" alt="image" src="https://github.com/user-attachments/assets/c695f484-6750-4fdd-a5fe-655f02511bce" />

4. Apply KCL at Output: 
* At VIN = VOUT = VM:
                      IDSP + IDSN = 0
Solve this equation for VM (the switching threshold).

5. Analytical Formula for VM
  
<img width="968" height="373" alt="Screenshot 2026-02-26 at 3 51 44 AM" src="https://github.com/user-attachments/assets/ed3b4a36-5128-4dfd-8548-47a22f56cad2" />

6. Examples
Case A: (WP/WN) = 3.75 → VM ≈ 1.2 V
Case B: (WP/WN) = 1.5 → VM ≈ 0.98 V

* Larger PMOS (bigger W/L) pushes VM closer to VDD.
7. Inverse Design:
                  If you want a specific VM (e.g., 1.25 V for symmetric switching), Use the formula: VM = (R / (1 + R)) · VDD

## 32 L-3 Analytical expression of (W/L)p and (W/L)n as a function of Vm:

<img width="1670" height="788" alt="image" src="https://github.com/user-attachments/assets/ffedfa8f-9cc2-48d1-878d-fa45ebc142ac" />

* we calculate VM from given W/L values, but now we do the reverse: given VM, find the needed W/L for PMOS and NMOS.
* Target: VM = 1.25 V (half of VDD = 2.5 V). This is important for applications like clock inverters needing centered switching.
* Start with the current equation (IDSN = –IDSP), rearrange, and expand Kn and Kp to get W/L terms.

<img width="966" height="190" alt="image" src="https://github.com/user-attachments/assets/6d5c5c64-b4b0-4285-9329-a8f8d5c168c4" />

<img width="968" height="214" alt="image" src="https://github.com/user-attachments/assets/567a642c-b5ea-4508-92e6-ccf24f109764" />

* After simplifying, you get:
                             * W/L(PMOS) = 2.5 × W/L(NMOS) (for VM = 1.25 V).
* This means PMOS must be 2.5x wider than NMOS for center switching, which makes sense as PMOS is slower.

<img width="1894" height="670" alt="image" src="https://github.com/user-attachments/assets/0a1df436-d77c-451d-855c-815e1ecf6724" />

* To verify, run SPICE simulations: keep NMOS size fixed, increase PMOS size in steps, and observe how the switching threshold changes.
* NMOS W/L = 0.375/0.25; try PMOS W/L = 0.75/0.25 (2× wider) and see VM shift.
* Also, record rise and fall delays for each case to get a glimpse of CMOS dynamic behavior.



## 33 L-4 Static and Dynamic simulation of CMOS inverter:
* Circuit: NMOS W/L = 0.375/0.25, PMOS W/L = 0.375/0.25
* Run a DC simulation and plot the transfer curve (Vout vs Vin).
* Finding Switching Threshold (Vm)by drawing a 45° line from the origin on the DC curve.
* Where this line crosses the curve is Vm (since Vin = Vout).
* For equal NMOS/PMOS sizes: Vm ≈ 0.99 V
  
* Rise & Fall Delay Calculation
* How to Measure:
                 Measure delay between 50% points (1.25 V) of input and output.
* Rise Delay:

        Input falls, output rises.
        Output at 1.25 V: t₁ = 1.0144 ns
        Input at 1.25 V: t₂ = 1.1627 ns
        Rise Delay = t₂ − t₁ ≈ 148 ps
* Fall Delay:

        Input rises, output falls.
        Output at 1.25 V: t₁ = 2.00486 ns
        Input at 1.25 V: t₂ = 2.07653 ns
        Fall Delay = t₂ − t₁ ≈ 71 ps
<img width="1137" height="564" alt="Screenshot 2026-02-26 at 2 13 51 PM" src="https://github.com/user-attachments/assets/640929b0-b434-445d-bcae-71e99d834c31" />


## 34 L-5 Static and Dynamic simulation of CMOS inverter with increased PMOS width:
* Here we are incresing the width of PMOS in integral terms and repeating the content from the previous lecture:
  
<img width="2274" height="1128" alt="image" src="https://github.com/user-attachments/assets/ab58018e-b6bc-4d65-9cd0-5c408ead92f0" />
<img width="2542" height="1214" alt="image" src="https://github.com/user-attachments/assets/286aed76-ace6-4335-a4bd-9bc748c1937a" />
<img width="2572" height="1190" alt="image" src="https://github.com/user-attachments/assets/9a299e12-5fd6-4ff8-b0e4-ca6ef20f219a" />
<img width="2566" height="1168" alt="image" src="https://github.com/user-attachments/assets/00dbda92-a5b5-482a-8a33-805d30a3c984" />
<img width="2554" height="1150" alt="image" src="https://github.com/user-attachments/assets/b193634e-625b-4284-8408-c9d2732c2325" />
* we can see the change in rise delay, fall delay compare to the first simulation.
* 
<img width="1604" height="598" alt="image" src="https://github.com/user-attachments/assets/347420d2-c1af-45f0-b5dd-b95c065cc387" />


## 35 L-6 Applications of CMOS inverter in clock network and STA :
* when PMOS size is varied between 2× and 3× of the NMOS, the switching threshold only shifts by about 50 mV.
* This is a huge advantage because during fabrication, the actual transistor size may not come out exactly as planned but it might be slightly off.
  
  <img width="1079" height="263" alt="Screenshot 2026-02-26 at 3 29 57 PM" src="https://github.com/user-attachments/assets/99cb9b76-92e0-4435-bac8-0ff72f826c3d" />

* Here Vm barely changes across a range of PMOS sizes, the inverter still behaves as we require even with slight off in fabrication.
* At a certain PMOS size (around 2× to 2.5× of NMOS), rise delay ≈ fall delay -> This symmetry is critical for clock cells
* A clock buffer with matched rise/fall delay preserves the waveform shape all the way to the endpoint.
  
  <img width="1433" height="861" alt="Screenshot 2026-02-26 at 3 30 18 PM" src="https://github.com/user-attachments/assets/9def9ece-3f1b-41c4-8610-b6172189f399" />

* This is achieved by sizing PMOS such that PMOS resistance ≈ NMOS resistance


## CMOS Noise Margin robustness evaluation:
   ## Static behaviour evaluation - CMOS Noise Margin robustness evaluation
   ## 36 L-1 Introduction to Noise Margin 
   
*  **Noise Margin** : It is a measure of how much unwanted electrical noise a logic circuit can tolerate on its input without producing an incorrect output.
*  <img width="354" height="370" alt="Screenshot 2026-02-26 at 4 05 41 PM" src="https://github.com/user-attachments/assets/f077a6de-2e1c-49e0-8e2c-45a655cb0fb2" />
<img width="386" height="329" alt="Screenshot 2026-02-26 at 4 05 49 PM" src="https://github.com/user-attachments/assets/6bb60b6b-8fac-460c-9594-a93607e4b33c" />

<img width="1422" height="868" alt="image" src="https://github.com/user-attachments/assets/8a1c9eab-43be-4bb3-bc8d-88a98148fef3" />
<img width="497" height="67" alt="Screenshot 2026-02-26 at 4 07 59 PM" src="https://github.com/user-attachments/assets/c1ebcb76-b479-4f4a-887e-231234aa71f6" />
<img width="555" height="92" alt="Screenshot 2026-02-26 at 4 08 09 PM" src="https://github.com/user-attachments/assets/f2b41341-6db1-43a8-81ea-49ef6c92a4e9" />
<img width="519" height="79" alt="Screenshot 2026-02-26 at 4 07 32 PM" src="https://github.com/user-attachments/assets/f9e9c88d-029b-4b10-8883-59f76ad73e04" />
<img width="534" height="73" alt="Screenshot 2026-02-26 at 4 07 43 PM" src="https://github.com/user-attachments/assets/5cd83308-5bca-4e49-85e2-2fd9a834b0c3" />

* Ideal Case:
              * At Vm (VDD/2), output flips instantly from VDD to 0, Slope is infinite—perfectly vertical transition.
Practical Case:

* Real devices have resistance and capacitance, so output transitions over a range—not instantly, Slope is finite (not vertical), and output might not hit exactly 0 V or VDD.

## 37 L-2 Noise margin voltage parameters:
* The ideal inverter transfer curve has a perfectly vertical (infinite slope) transition at the switching threshold its shown in right side of curve in the below figure.
* In reality (practical curve), the transition is more gradual because of device resistances and capacitances it is shown in the below figure left sided curve.
* The practical VTC shows a sloped transition region, not an abrupt drop, which is what we actually see in measurements and simulations.

<img width="905" height="502" alt="Screenshot 2026-02-26 at 4 33 21 PM" src="https://github.com/user-attachments/assets/abf1f694-ad7a-4adc-957d-ea475650b255" />

<img width="529" height="437" alt="Screenshot 2026-02-26 at 4 29 44 PM" src="https://github.com/user-attachments/assets/59f7392f-9223-45e6-9b34-26f292b580f0" />


## 38 L-3 Noise margin equation and summary:
* Noise Margin and Voltage Levels – Student Notes
To find noise margin, we plot voltage levels (VOH, VIH, VIL, VOL) on the inverter’s transfer characteristic.

<img width="409" height="428" alt="Screenshot 2026-02-26 at 4 50 51 PM" src="https://github.com/user-attachments/assets/11f18864-b282-4926-a85e-c23063f1fd0c" />

* These values are specifications for the chip and must be well defined.
* Logic 1: Input between VIH and VOH; output stays HIGH.
* Logic 0: Input between VOL and VIL; output stays LOW.
* If a noise bump falls between VIH and VOH or between VIL and VOL, it’s still safe—the circuit interprets the logic correctly.
* The region between VIL and VIH is called the undefined region—the output could be interpreted as either 0 or 1.
* If a glitch lands in this undefined area, it’s risky and the design should be improved.

<img width="919" height="565" alt="Screenshot 2026-02-26 at 4 50 30 PM" src="https://github.com/user-attachments/assets/a2e35e5b-b707-4140-ae69-6183cabfd371" />

  
* Summary: Noise margin defines how much noise can be tolerated. If noise stays out of the undefined region, the circuit works safely. If not, action may be needed

## 39 L-L4 Noise margin variation with respect to PMOS width:
* By looking at the inverter curves, we can see if the CMOS inverter is robust (good noise margin, reliable logic levels).
* The PMOS helps hold charge on the output capacitor and provides a low-resistance path when output should be high.
* Increasing PMOS width usually increases noise margin—the inverter becomes more robust but with limitations.
  <img width="2834" height="1310" alt="image" src="https://github.com/user-attachments/assets/f3b07cec-3d36-4799-a14a-f48377114944" />
  <img width="2820" height="1258" alt="image" src="https://github.com/user-attachments/assets/659a9464-5e79-458a-9a9e-f8eda67220c8" />
  <img width="2894" height="1314" alt="image" src="https://github.com/user-attachments/assets/2b7bd9dd-1f99-441d-88a0-c47138e87c0c" />
  <img width="2832" height="1276" alt="image" src="https://github.com/user-attachments/assets/27276aba-e449-4a42-93dd-d755f1a9c8e6" />
  <img width="1397" height="645" alt="Screenshot 2026-02-26 at 5 13 32 PM" src="https://github.com/user-attachments/assets/7bfdfa8c-e33e-49fa-a46d-f647a1174c62" />

  
* However, there are limits to how wide you can make the PMOS:
* Fabrication constraints make it hard to make PMOS more than ~2 times wider than NMOS.
* Very large PMOS widths (like 5× NMOS) are not practical.
* The area of the CMOS inverter is also important for digital design—it affects chip size and layout so some are made for analog devices and other for digital ones based on ones usage.

<img width="1896" height="1290" alt="image" src="https://github.com/user-attachments/assets/ed054757-248c-4f55-a44a-205e9e70d7db" />

<img width="969" height="639" alt="Screenshot 2026-02-26 at 5 09 52 PM" src="https://github.com/user-attachments/assets/36d4a5bd-b7ae-4336-a580-075445a5aa7b" />



## 40 L-5 Sky130 Noise margin labs:

SIMULATIONS:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/49f91ea7-495f-4ea8-97f5-4c47897e69b2" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/43219a39-d0e7-44fb-9b36-6a1fd2b2eb6a" />



## CMOS power supply and device variation robustness evaluation
   ## Static behavior evaluation – CMOS inverter robustness – Power supply variation
   ## 41 L-1 Smart SPICE simulation for power supply variations:
* Power supply scaling is important as technology scales down; MOSFETs need lower VDD to operate correctly and reliably.
* When designing an inverter, PMOS is usually made wider than NMOS to match their resistance and keep switching behavior consistent.
* To test inverter robustness with lower supply voltages:
* Use the same device sizes.
* Sweep the power supply from 2.5 V down to 1 V in steps of 0.5 V.
  
  <img width="1334" height="715" alt="Screenshot 2026-02-26 at 6 36 11 PM" src="https://github.com/user-attachments/assets/6e04f10f-a71d-42d4-a5d5-439d88cb2e79" />

* The goal is to check if the inverter’s switching action remains proper as VDD decreases.
* In SPICE, set powersupply = 2.5V, then use .alter vdd=powersupply and step down the supply voltage.
* Run simulations and plot the resulting transfer curves at each VDD.
* All control commands and data processing can be handled between .control and .endc in your SPICE deck


## 42 L-2 Adavntages and Disadvantages using low supply voltage
* The CMOS inverter can still work at low supply voltages (like 0.5 V), as seen in previous experiments.
* Gain factor in an inverter is how much the output changes for a small change in input (slope of the VTC curve).
* At lower VDD, the VTC curve gets steeper, so gain increases—here, gain improved by about 56% (to 11.53).

<img width="2138" height="1262" alt="image" src="https://github.com/user-attachments/assets/99190df8-98a5-4fa5-983f-919f78e4e682" />
<img width="2162" height="1284" alt="image" src="https://github.com/user-attachments/assets/31fd3aa0-846d-42ae-8306-92a9716dd816" />


* Advantages of lower supply voltage:
* Power consumption drops dramatically.Energy used per switch is ( \frac{1}{2}CV^2 ), so lowering VDD from 2.5 V to 0.5 V reduces energy by about 96%.
* Disadvantages of lower supply voltage:
* The inverter can’t fully charge/discharge the load capacitance at very low VDD (like 0.5 V).
* Rise and fall times increase (switching is slower) because there’s not enough voltage to move charge quickly.
  
* for 0.5 v rise and fall
  <img width="1113" height="665" alt="Screenshot 2026-02-26 at 7 45 13 PM" src="https://github.com/user-attachments/assets/d28dea3f-0726-4b99-bddf-34f0ab96e9b3" />
* for 2.5 v rise and fall
  <img width="2216" height="1370" alt="image" src="https://github.com/user-attachments/assets/22bfc0a6-7a14-496f-9b0a-126513fd65ac" />
* for 1v rise and fall
<img width="2270" height="1272" alt="image" src="https://github.com/user-attachments/assets/e7cd0d65-21fd-4145-a0b5-689ec4e5e0aa" />

* At higher VDD (like 2.5 V), charging and discharging are faster and more complete.

## 43 L-3 Sky130 Supply Variation Labs

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b967cc0b-0ef7-40f3-aa57-4c7969809b9f" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/eb530968-11a7-4742-bd21-ef9b4276fed0" />



## Static behavior evaluation – CMOS inverter robustness – Device variation
## 44 L-1 Sources of variation – Etching process:
* Etching process variation is one of the main sources of variation in CMOS fabrication.

  <img width="1384" height="555" alt="Screenshot 2026-02-26 at 8 04 17 PM" src="https://github.com/user-attachments/assets/a1ed877d-df1f-4550-8176-182f555ae2c0" />
  <img width="980" height="603" alt="Screenshot 2026-02-26 at 8 03 57 PM" src="https://github.com/user-attachments/assets/50d74a6e-038f-4f63-abbf-0dac84f79bce" />
  <img width="1388" height="671" alt="Screenshot 2026-02-26 at 8 04 36 PM" src="https://github.com/user-attachments/assets/56191e56-0edd-42d7-ba6b-439c2f4144c2" />
  <img width="1079" height="744" alt="Screenshot 2026-02-26 at 8 05 00 PM" src="https://github.com/user-attachments/assets/7e44ca96-d8e6-47d7-b824-6320c99230ec" />

* Etching defines the physical structure of each device, which directly affects the delay and performance of the cell.
* In layout images, each color usually represents a different metal layer or region.
* In a chain of inverters, you might see:
                                         Mask overlap issues: Misalignment during fabrication can cause variations.
* Defects in the middle vs. at the ends: The gates in the middle of the inverter chain may have a certain type of fault, while those at the ends might have different defects.
   <img width="2858" height="1532" alt="image" src="https://github.com/user-attachments/assets/1173ca0c-fdca-477e-9559-30dbe6687bbd" />

* These process variations can cause devices to behave differently, impacting the overall circuit performance.


## 45 L-2 Sources of variation – oxide thickness:
* Oxide thickness variation is another key source of process variation in CMOS.
* Changes in gate oxide thickness directly affect the transistor’s threshold voltage and overall performance.

<img width="2754" height="1246" alt="image" src="https://github.com/user-attachments/assets/cb227890-8dd3-486f-904b-1b6608cf2b2b" />

<img width="1772" height="1498" alt="image" src="https://github.com/user-attachments/assets/9d97fcfb-76b0-4412-856d-91ebf3b77ccd" />

<img width="2150" height="602" alt="image" src="https://github.com/user-attachments/assets/e3c53cac-6a2c-4c4f-8b7e-5ab6f2da4f35" />

<img width="1166" height="178" alt="Screenshot 2026-02-26 at 8 16 50 PM" src="https://github.com/user-attachments/assets/19140b3c-9c55-47cc-9bdb-fca34c3795d9" />


## 46 L-3 L3 Smart SPICE simulation for device variations:

* Weak PMOS (small W/L, high resistance) and strong NMOS (large W/L, low resistance)
NMOS pulls down the output quickly; PMOS pulls up more slowly.
* The switching threshold (Vm) shifts closer to ground, and the output fall is faster than the rise.
  
<img width="1429" height="226" alt="Screenshot 2026-02-27 at 10 14 22 PM" src="https://github.com/user-attachments/assets/b023b99c-e0f2-4e1e-a5a9-1c56996de23c" />
<img width="567" height="329" alt="Screenshot 2026-02-27 at 10 16 18 PM" src="https://github.com/user-attachments/assets/cc4954f7-eb63-4b0a-9c01-af09dd976f00" />
<img width="447" height="291" alt="Screenshot 2026-02-27 at 10 16 42 PM" src="https://github.com/user-attachments/assets/9303d2be-a3e5-4317-b387-277f50c1a337" />
<img width="418" height="292" alt="Screenshot 2026-02-27 at 10 16 52 PM" src="https://github.com/user-attachments/assets/eff82834-c4b9-4203-80eb-5ee206788c70" />
<img width="703" height="528" alt="Screenshot 2026-02-27 at 10 17 11 PM" src="https://github.com/user-attachments/assets/84b5f2b0-7eeb-4e32-9992-4dea0177422b" />





## 47 L-4 Conclusion:

* comaparing the characteristics we got .

<img width="1349" height="765" alt="Screenshot 2026-02-26 at 8 25 25 PM" src="https://github.com/user-attachments/assets/920efd14-6976-4fdf-a2da-b6ae0526125f" />

<img width="988" height="648" alt="Screenshot 2026-02-26 at 8 29 51 PM" src="https://github.com/user-attachments/assets/935d2fae-5a94-4b08-81a0-0d8f9c4d8d0a" />

<img width="1075" height="666" alt="Screenshot 2026-02-26 at 8 31 30 PM" src="https://github.com/user-attachments/assets/9895222f-46aa-402a-a1a2-3582d8da523e" />
* There is not much variation in Noise Margins in both the high endcases, that means it behaves as a robust inverter in both the cases.

## 48 L-5 Sky130 Device Variation Labs:

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1ca57bff-41f0-4f16-baa1-206a3a3d2e15" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/70d3204b-ea3b-44bf-82d1-4dfeb337d6be" />



















