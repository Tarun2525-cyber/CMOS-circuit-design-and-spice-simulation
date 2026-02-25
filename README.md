# CMOS-circuit-design-and-spice-simulation

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


-------------------------------------------------------
Day 2 lec 2 :
This experiment looks at how the drain current changes with gate voltage when VDS is fixed at 2.5 V, comparing a long-channel MOSFET (L = 1.2 µm) and a short-channel MOSFET (L = 0.25 µm).

The SPICE setup remains the same except for a single sweep command that scans VGS from 0 to 2.5 V while holding VDS constant at 2.5 V.

For the long-channel device, the ID–VGS curve follows the expected square-law behavior, showing a smooth parabolic rise as VGS increases.

The current stays near zero in the cutoff region, begins rising near the threshold voltage, and then grows quadratically for the rest of the sweep—matching the classic long-channel saturation equation.

The short-channel device begins similarly, with quadratic behavior at low VGS, but the curve quickly deviates from the square-law pattern.

As VGS increases further, the current stops following a parabola and instead becomes almost linear, a direct result of velocity saturation in the shorter channel.

This shift from quadratic to linear behavior causes the short-channel device to produce higher currents and a noticeably straighter ID–VGS curve compared to the long-channel MOSFET.

Side-by-side, the long-channel device maintains its curved, quadratic profile, while the short-channel device bends upward initially and then transitions into a straight-line trend.

Physically, the long-channel MOSFET allows carriers to accelerate normally, but the short-channel one creates such high electric fields that carriers hit their maximum velocity, breaking the square-law model.

Overall, the comparison clearly shows how shrinking channel length introduces strong short-channel effects, making the ID–VGS relationship linear and signaling the need for advanced models like BSIM in deep-submicron technologies.

---------------------------------------------------

Day 2 lec 3 :
Sweeping VGS from 0 to 2.5 V at a fixed VDS = 2.5 V gives ID–VGS curves for both long- and short-channel MOSFETs.

The long-channel device follows pure square-law behavior, with ID ∝ (VGS – VT)² across the entire sweep.

The short-channel MOSFET matches the quadratic trend only at low VGS but shifts to a linear rise at higher VGS.

This shift happens because the electric field becomes so high that carriers reach their saturation velocity (VSAT).

Once velocity saturates, increasing VGS only increases charge, not carrier speed → resulting in linear ID–VGS behavior.

The transition point is tied to the critical field EC = VSAT / μn.

Modern analysis uses a unified model with Vmin = min(VGT, VDS, VDSAT) to cover all operating regions.

Short-channel devices now have four regions: cutoff, linear, classical saturation, and velocity saturation.

This velocity saturation effect is dominant in deep-submicron devices and breaks long-channel square-law assumptions.

Overall, the comparison shows that long-channel MOSFETs stay quadratic, while short-channel MOSFETs turn linear at high VGS due to velocity saturation.


--------------------------------------------
Day 2 lec 4 
The unified MOSFET model uses two key terms—VGT = VGS − VT and Vmin = min(VGT, VDS, VDSAT)—to decide which region the device operates in.

With this approach, the same equation covers cutoff, linear, saturation, and velocity-saturation regions without switching formulas.

For VGT < 0, the device is off and ID = 0; once VGT ≥ 0, the drain current follows the unified expression involving VGT and Vmin.

When Vmin = VGT, the device enters saturation and the model reduces to the familiar long-channel equation ID ∝ VGT².

When Vmin = VDS, the device is in the linear region, giving the standard resistive form where ID grows with VDS.

When Vmin = VDSAT (short-channel only), the MOSFET enters velocity saturation, causing ID to depend linearly on VGS instead of quadratically.

In this region, carrier velocity has reached its maximum limit, so extra gate voltage only increases charge, not speed—flattening the current.

Because velocity saturation appears early in short-channel devices, they show lower peak currents even when W/L is kept the same


---------------------------------------
Day 2 lec 5 :
A deeply scaled MOSFET with W = 0.39 µm and L = 0.15 µm was simulated for ID–VDS and ID–VGS, with VDS and VGS swept up to 1.8 V.

In the ID–VDS curves, the device shows a quadratic increase at low VDS, but quickly transitions into almost straight-line behavior as VDS grows.

This linear portion appears because the carrier velocity saturates early at such short channel lengths, preventing ID from rising quadratically.

At the highest gate bias (VGS = 1.8 V), the peak current is around ~196 µA, much lower than what a long-channel device with the same W/L would have given.

The ID–VGS sweep at fixed VDS = 1.8 V shows an almost fully linear curve from start to end, with hardly any visible quadratic region.

This happens because VDSAT is very small at L = 0.15 µm, so the device immediately enters the velocity-saturation regime where Vmin = VDSAT.

As a result, ID becomes proportional to VGS, matching the unified short-channel model and confirming the dominance of velocity saturation.

The combination of quadratic behavior at low VDS and linear behavior at high VDS clearly shows how strong electric fields cap carrier velocity


-----------------------------------------------
Day 2 lec 6
ID–VGS curve at VDS = 1.8 V shows the device turning on sharply near its threshold, even though the rest of the curve is linear due to strong velocity saturation.

By drawing a tangent along the steepest rising part of the curve and extending it to the VGS axis, the threshold voltage can be extracted.

This extrapolation gives VT ≈ 0.77 V, matching the expected onset of conduction for the 0.15 µm short-channel MOSFET.

The method works because the turn-on region still follows the square-law behavior ID ∝ (VGS − VT)² before velocity saturation takes over.

Combined with the earlier ID–VDS and ID–VGS results, this confirms a complete short-channel picture: early VT, immediate velocity saturation, and linear current growth.

------------------------------------------------
Day 2 Part 2 lec 1 :
At this stage, the MOSFET is viewed less like an analog device and more like a digital switch, which makes understanding CMOS logic easier.

A MOSFET basically turns ON when its gate-to-source voltage crosses the threshold and stays OFF when it doesn’t, and expressing this as |VGS| ≥ |VT| gives one rule for both NMOS and PMOS.

A CMOS inverter is just a PMOS on top and an NMOS on the bottom, both driven by the same input and sharing a common output node.

When the input is high, the NMOS turns on while the PMOS turns off, which pulls the output down to ground and creates the inverter’s “flipped” result.

This simple switch-based perspective is what we use to build the inverter truth table and later derive the Voltage Transfer Characteristic (VTC).


----------------------------------------------
Day 2 part 2 lec 2 :
To build the CMOS inverter’s VTC, we first look at the two extreme input cases—VIN = VDD and VIN = 0—and replace each transistor with its ON/OFF switch equivalent.

When the input is high, the NMOS turns ON and acts like a resistive path to ground, while the PMOS turns OFF, leaving the output node to discharge through the NMOS until it reaches 0 V.

When the input is low, the PMOS becomes the conducting device and behaves like a resistor to VDD, while the NMOS is OFF, allowing the output node to charge back up to VDD.

These ON resistances, RN for NMOS and RP for PMOS, are not fixed values but depend on device operating regions, and they later govern the VTC shape and the rise/fall delays.

To prepare for the full VTC derivation, voltage and current labels like VGSN, VGSP, VDSN, IDSP, etc., are defined so both transistors can be analyzed together during the switching transition.

With these two boundary cases and naming conventions set, the next step is to solve both device equations simultaneously and find the switching point where NMOS and PMOS currents balance.


-----------------------------------------------
day 2 part 2 lec 3 :
Before deriving the CMOS inverter’s VTC, we first clean up our voltage naming: NMOS uses VGSN and PMOS uses VGSP, because PMOS voltages naturally come out negative and need their own notation to avoid sign mistakes.

The lecture also clarifies current directions: the NMOS pulls current upward through the output node when discharging, while the PMOS pushes current downward when charging, which means IDSP = –IDSN and this relationship becomes the heart of VTC derivation.

For the NMOS, things are simple—its VGSN equals VIN and its VDSN equals VOUT, since its source is grounded; for the PMOS, both VGS and VDS become negative because its source is tied to VDD.

Once these voltages are defined, the NMOS load curve (IDSN vs VDSN) and the PMOS load curve (IDSP vs VDSP) can be plotted; the PMOS curves are essentially mirror images of the NMOS curves in the negative quadrant.

These two curve families matter because the VTC is simply the point where NMOS sinking current and PMOS sourcing current balance—meaning IDSN(VIN, VOUT) = –IDSP(VIN, VOUT)—and this balance defines VOUT for every input value.

With voltage definitions, current directions, and both load curves in place, the next lecture will plug in the nonlinear drain-current equations for NMOS and PMOS and solve for VOUT as VIN varies, finally producing the CMOS inverter’s VTC.

--------------------------------------------
day2 part 2 lec 4 :
Inside a CMOS inverter, we technically have four transistor voltages (VGSN, VDSN, VGSP, VDSP) and two drain currents (IDSN, IDSP), but digital logic only “sees” VIN and VOUT — everything else is internal.

To derive the VTC, the lecture focuses on rewriting every PMOS and NMOS voltage in terms of just VIN and VOUT, since the final curve must be VOUT as a function of VIN only.

The first transformation is converting the PMOS gate voltage VGSP into the input voltage using VIN = VGSP + VDD, which shifts negative VGSP values into the positive VIN axis.

Next, the PMOS drain current is mirrored into NMOS coordinates using IDSN = –IDSP, because PMOS current flows in the opposite direction, giving us a PMOS-equivalent load curve expressed entirely in terms of positive current.

After converting each PMOS point (VGSP, IDSP) into (VIN, IDSN), the PMOS load curve becomes directly comparable to NMOS curves, letting both devices be plotted on the same VIN–IDSN axes.

This step is crucial because the CMOS VTC comes from solving where NMOS current equals PMOS current; once both sides are rewritten as IDSN(VIN, VOUT), their intersection gives the output voltage.

The lecture ends with VGSP and IDSP fully eliminated, and the next one will remove the remaining internal voltages (VDSN and VDSP) so the final VTC equation can be formed purely from VIN and VOUT.

------------------------------------------

day 2 part 2 lec  5:
This lecture finishes the job of removing all internal PMOS/NMOS voltages so that both devices can finally be described only with VIN, VOUT, and the current IDSN — exactly what we need for the CMOS VTC.

The key step is converting the PMOS drain-to-source voltage using VDSP = VOUT – VDD, which shifts the entire PMOS I–V curve horizontally and replaces the negative VDSP axis with a clean VOUT axis.

After this shift, every PMOS data point can now be expressed as (VIN, VOUT, IDSN) — meaning VGSP, VDSP, and IDSP are completely eliminated, and the PMOS load curve is now in inverter-ready form.

The NMOS side is much simpler: since its source is at ground, VGSN = VIN and VDSN = VOUT, so the NMOS I–V curves directly become the NMOS load curve just by renaming axes.

With both curves expressed as IDSN(VIN, VOUT), the stage is set: the VTC comes from solving where NMOS current equals PMOS current, and this merging of their load curves forms the complete VOUT vs VIN characteristic.

----------------------------------------
day 2 part 2 lec 6 :
The lecture explains that the CMOS VTC comes from overlaying the NMOS and PMOS load curves and finding where their currents balance, since both devices share the same VIN, VOUT, and output current. Once both curves are expressed as IDSN(VIN, VOUT), the process is simple: for each VIN, take the NMOS and PMOS curves at that value and their intersection gives the corresponding VOUT. As VIN sweeps from 0 to 2 V, the intersections move from VOUT = 2 V to VOUT = 0 V, with the sharp switching region appearing around VIN ≈ 1 V when both devices are in saturation. Connecting these points produces the classic S-shaped inverter characteristic. This approach also makes it clear which region each transistor operates in at every VIN, setting up the analysis of gain, noise margins, and delay.


------------------------------------------
day 3 lec 1 :
This lecture kicks off the practical SPICE setup for generating the CMOS inverter VTC, which means writing a clean netlist with correct device terminals, node names, and model references.

The inverter schematic is the usual one: PMOS at the top connected to VDD, NMOS at the bottom connected to ground, both gates tied to the input, their drains tied to the output, and the bodies tied to their respective supplies.

Substrate connections are highlighted because SPICE needs them explicitly, and they influence threshold voltage through the body effect.

Both the PMOS and NMOS are given identical dimensions (W = 0.375 µm, L = 0.25 µm) for demonstration, even though real designs typically use a wider PMOS.

A simple 10 fF load capacitor is placed at the output, and VDD is set to 2.5 V, with VIN planned to sweep from 0 to 2.5 V.

The lecture identifies all the inverter nodes (in, out, VDD, 0, sub_p, sub_n) and then writes the first SPICE line: the PMOS entry with drain, gate, source, and body explicitly listed.

The session ends after defining the PMOS; the next lecture will add the NMOS, the capacitor, the VIN source, model cards, and finally run the DC sweep to plot the VTC.







































