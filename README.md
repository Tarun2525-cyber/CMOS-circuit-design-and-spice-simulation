# CMOS-circuit-design-and-spice-simulation
 lec 1 :
 
Logic gates are made up of P mos and N mos in particular arrangemnet which gives a particular output be like and, nor, not, or gates etc, gates are tied together and this king of connection gives you invertor,In circuit design we try to understand different p mos and n mos transistors gives you which kind of output, the following graphs represent characterisitcs graphs of N mos 
<img width="611" height="334" alt="Screenshot 2026-02-23 at 9 37 11 AM" src="https://github.com/user-attachments/assets/afa50862-0dec-4c46-a1a2-a259e3f7a53f" />
<img width="1103" height="845" alt="Screenshot 2026-02-20 at 11 18 22 AM" src="https://github.com/user-attachments/assets/e3e9985d-0421-4c7b-9f53-6ba72078a58b" />


the inverted one repressents that of P mos, when you after simulating in spice  you get a curve like the below one 
the waveforms determines the delay of the transistor. based on delay we can tune w/l ratio(width/length). to tune delay we should tune w and l.
Spice is done to do with delays.which can be good for us in 
There is delay table to calculate delay of particular cell, which is combination of input slew, and output load,each buffer has its own delay table because the transistos used in it and the way those are arranged are different for different buffers as each and every transistors width and length are not in same dimension 
<img width="1393" height="872" alt="Screenshot 2026-02-20 at 11 57 40 AM" src="https://github.com/user-attachments/assets/1824d8b8-4f9b-4a9b-a929-901c2e12b9cd" />

if considering a a buffer and its output load is 60fF and input slew of 40pF as shown in fig its between 50 and 70 then the delay of the buffer is also between 50 and 60 which x9'
by these tables we decide delay of the cell, 
lec 2 : 
N MOS
it's a 4 terminal device , consists of p substarte whcih is opposite in case of P MOS which is made up of n substrate, isolation region, n+ diffusion regions one of which is source and the other is  drain ,poly silicon gates, gate oxide, G-Gate, S-Source, D-Drin, B-Body terminal,
<img width="564" height="621" alt="Screenshot 2026-02-20 at 12 05 09 PM" src="https://github.com/user-attachments/assets/1174926c-13a9-4bd6-8726-d091823ad62c" />


the most important one is Threshold voltage(Vt) considerations  in mosfets,

 Accumulation in N mos is  when Vg < 0 (negative gate voltage)
<img width="1345" height="450" alt="Screenshot 2026-02-20 at 12 09 52 PM" src="https://github.com/user-attachments/assets/ee1683fa-8cc0-4320-8938-ed7f16d7ac19" />

What physically happens:

Negative gate voltage pulls holes (majority carriers in p-type) toward the oxide.

Hole concentration at the surface increases → “accumulates”
Depletion region in N mos is when V<sub>G</sub> = small +ve voltage (positive but not too high)

What physically happens:

Positive gate voltage repels holes away from the oxide.

Only ionized acceptor atoms (A⁻) remain → fixed negative charge.

This region with no mobile carriers = depletion region.

Inversion region in N mos is when V  > Vt (threshold voltage)

What physically happens:

A strong positive gate voltage bends bands enough to pull electrons (minority carriers in p-type) to the surface.

These electrons accumulate at the oxide–semiconductor interface and form an n-type inversion layer.

lect 3:
there will be a depletion region at n+ and p substrate this means when you apply +ve voltageg your region near it gets depleted about its majority carriers,

there is strong inversion of carriers when you apply high +ve voltage in this case its electrons coming near surface,

there will be a small surface where minority carriers get accumulated due to high +ve potential at gate this phenomenon is called "Strong inversion"
<img width="1345" height="450" alt="Screenshot 2026-02-20 at 12 09 52 PM" src="https://github.com/user-attachments/assets/ee1683fa-8cc0-4320-8938-ed7f16d7ac19" />
and the potential at which it happens is called  "Threshold voltage"

if you increase further the gate voltage but there will not be any minority carriers left or majority carriers left to attract or repel respectively.

here the electrons from n+ source areas get attracted towards the gate the channel width gets increased and no change in depletion region width 

there will be a  continuous channel from source to drain and now after applying voltage to source ther will be flow of current through the channel.

Body terminal also effects the threshold voltage of the mosdfet.

Considering 2 scenarios:
<img width="1208" height="547" alt="Screenshot 2026-02-22 at 10 36 52 AM" src="https://github.com/user-attachments/assets/c191b425-9b1c-4bb1-b0a5-06e152df6565" />


one is having no voltage applied to body terminal and one is connected to source 

the depletion region in the second is more compared to the first because you have additional reverse bias acting upon the body termianl this increases the depletion region width. and observation ishtat 
 inversion happens in the second diagram is a bit late compared to first if you increase the gate to source voltage.

 lect 4: 
 <img width="1349" height="871" alt="Screenshot 2026-02-22 at 10 45 03 AM" src="https://github.com/user-attachments/assets/9d6c5779-38c1-4215-8269-a5d4e0e86542" />

 the negatively charged particles are attarcted more in the source as the n+ source is connected to +ve terminal the accumulated negatively charged particle are pulled throught source area

 for a particular gate voltage the inversion happens in the first one but the channel is in the ascending order in the second one due to applied potential between body and source.
 conclusion fromthis is that we need a additional potential for strong inversion.

 the threshold voltage equation is  
 <img width="732" height="339" alt="Screenshot 2026-02-22 at 10 55 23 AM" src="https://github.com/user-attachments/assets/6acab037-69de-4446-8cf4-6b148cbcd025" />


this equation represents the mosfet

<img width="490" height="287" alt="Screenshot 2026-02-22 at 10 56 33 AM" src="https://github.com/user-attachments/assets/dfec0c88-4141-4b36-b512-e5e38ba82077" />

<img width="581" height="167" alt="Screenshot 2026-02-22 at 10 56 52 AM" src="https://github.com/user-attachments/assets/b2cb88c4-7fb2-4adf-8235-ad65be31cb82" />


Lec 5
 Resistive Operation 
 
if we increase Vgs>Vt we get more conductive region  at channel region
as we increase the Vgs the chanel width increases as induced charges is directly proportional to (Vgs -Vt)

 applying small drain to source voltage at Vgs = 1V and Vds = 0.05 v where Vt = 0.45V
 as Vgs >Vt we get condnuctive channel after applying small voltage here ,
 <img width="870" height="739" alt="Screenshot 2026-02-22 at 11 33 13 AM" src="https://github.com/user-attachments/assets/8e1130a2-32ad-4e6c-a945-f6dd32bcc492" />


 there is voltage gradient in the channel when the Vds is applied but before applying its constant through out channel.

 the channel length is greater than effective channel length (L) 
  the potential at different part or length of channel is different due to application of Vds 
  now before applying Vds every point on the channel has voltage of Vgs but after applying we get (Vgs - Vx)

   L6 :Drift current theory 

   induced charge at any point in the region is Qi(x) = -Cox([Vgs - V(x)]-Vt)
   <img width="418" height="137" alt="Screenshot 2026-02-22 at 11 41 18 AM" src="https://github.com/user-attachments/assets/d4ce8fbf-2442-4d12-8c89-76b158451dd5" />

here  we have 2 kinds of current :
1. Drift current (current due to potential difference)
2. Diffusion current( current due to  difference in carrier concentration)

Drift current in channel as there is potenital gradient so there is drift current there
Drift current equation:[Id]
(velocity of charge  X available charge) over channel width 

Lec 6 :
generating  drift current equation
Id = -Vn(x).Qi(x).W
velocity Vn(x) = mobility * electric field
next is to intergrate dx over L will give theh V-I relation of N mos
drift current equation pics here 
<img width="1054" height="334" alt="image" src="https://github.com/user-attachments/assets/658f029e-9640-4229-a6b4-2a97ddd21585" />
<img width="942" height="120" alt="image" src="https://github.com/user-attachments/assets/6e655121-b888-46fa-b212-4cdf2211a176" />
<img width="1040" height="616" alt="image" src="https://github.com/user-attachments/assets/c571d9a2-0eb8-403a-9e39-4ee1b34d2475" />

for the given one s the VDS ≤ (VGS − Vt) the mosfet operates in the linear region the channel is continuous from source to drain 


L4 Spice conclusion to resisitve operation

drain current is linear function of Vgs-Vt 
 the impact of Vgs and Vds on Id 
 taking different values of Vgs and observing changes in the Id and we can sweep Vds from 0 to 0.05v 
 to take this and sweep and all this process needs a medium and that medium is SPICE it does it all .
<img width="544" height="619" alt="Screenshot 2026-02-22 at 12 15 49 PM" src="https://github.com/user-attachments/assets/0d314d7b-465c-4b53-9f79-4c1991ce50f0" />

Lec 5 Pinch off region condition:

 
what happens when Vds > (Vgs - Vt) it will be in saturation region
we are here increasing Vds from 0.05 to 0.45 v as  seen in the table 
during Vds upto 0.45 Vgs - Vds is greater than Vt
but if increased more then comes where Vgs- Vds  = Vt
here things will change 
where channel near source is at 1 v and channel near drain has a voltage of 0.45 v  
where the source is already inversion region but the channel near drain is just about inverted so the channel will be like  
<img width="577" height="542" alt="Screenshot 2026-02-22 at 12 24 02 PM" src="https://github.com/user-attachments/assets/6824c0e1-43e8-4fbc-8247-12aa08e7a4fc" />


the phenomenon of the channel getting disappered is called "Pinch off phenomenon"

after increasing more Vds where Vt >Vgs-Vds here the channel just disappears and this region is called saturation region

<img width="1032" height="332" alt="image" src="https://github.com/user-attachments/assets/4d13c065-357e-4d13-914b-75adacd9e1ce" />


L6: Drain current model for saturation region of operation


the channel voltage remains constant in saturation region 
channel length is modulated with Vgs
its no more functiton of Vds 
as we got earlier equatioon of drain current [Id] :
<img width="618" height="120" alt="image" src="https://github.com/user-attachments/assets/1ec958e4-d34f-4aa0-bd93-112c57a2b837" />

<img width="946" height="214" alt="image" src="https://github.com/user-attachments/assets/33c92b44-20eb-431c-8205-afa2082fe5c7" />

drain current is function of all the  constants

effective conductive channel length is modulated by applied Vds 
Vds increases  then depletion region at drain increases and effective channel length decreases.
more accurate equation and where we add lamda as a channel length modulation

L1 Basic SPICE setup:
we have seen many equations on threshold voltage, body effect coefficient , and fermilevel, where these are given correctly to get our simulation done neatly.

linear region drain current equation is most better approximation of the drain current
 the technology constants for lower nodes are given by the industry and are just implimented as it is to get our values
 <img width="1328" height="627" alt="Screenshot 2026-02-23 at 10 01 02 AM" src="https://github.com/user-attachments/assets/b71cfa10-df1e-4f61-99b0-53e7d72e233a" />

the "yellow" marked are spice model parameters. 
THE SPICE SETUP SHOULD LOOK LIKE 
<img width="688" height="631" alt="Screenshot 2026-02-23 at 10 04 32 AM" src="https://github.com/user-attachments/assets/93a9948a-3bd6-4129-8086-663caad138cb" />
<img width="579" height="397" alt="Screenshot 2026-02-23 at 10 06 58 AM" src="https://github.com/user-attachments/assets/3fad0478-d8be-4866-8bcf-2003e7562a97" />

L2 Circuit description in SPICE syntax

How to start SPICE simulation:
1.define nodes
<img width="753" height="622" alt="Screenshot 2026-02-23 at 10 09 31 AM" src="https://github.com/user-attachments/assets/0968afdb-7ab7-4f9d-9d1e-8598cb9f6dd8" />

you can define any name for the nodes
the nomenclature give for it is as 
name of component , Drain, Gate, Source, Substrate, mosfet name(technology file) ,width , length  
named R1, first terminal, last terminal, resistance
Vdd, first terminal, last terminal, value
Vin , first terminal,last terminal, value
 as seen in 
 <img width="667" height="220" alt="Screenshot 2026-02-23 at 10 16 12 AM" src="https://github.com/user-attachments/assets/45a48be3-d185-425c-966d-3021ba6b4801" />

L3 define technology parameters

Technology File:
all model parameters comes as a package 
the way you apply it is : 
<img width="609" height="373" alt="Screenshot 2026-02-23 at 10 21 37 AM" src="https://github.com/user-attachments/assets/4897324c-860c-4b9d-b384-66ccb08415d4" />
lastly save it as mod file 
<img width="870" height="606" alt="Screenshot 2026-02-23 at 10 23 30 AM" src="https://github.com/user-attachments/assets/44ce9d45-ba71-4b09-a8e7-d536fc26cd1e" />

 after that we need to add simulation commands 















































































