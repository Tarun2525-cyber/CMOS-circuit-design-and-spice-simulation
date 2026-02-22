# CMOS-circuit-design-and-spice-simulation
 lec 1 :
 
Logic gates are made up of P mos and N mos in particular arrangemnet which gives a particular output be like and, nor, not, or gates etc, gates are tied together and this king of connection gives you invertor,In circuit design we try to understand different p mos and n mos transistors gives you which kind of output, the following graphs represent characterisitcs graphs of N mos 
pict here
the inverted one repressents that of P mos, when you after simulating in spice  you get a curve like the below one 
the waveforms determines the delay of the transistor. based on delay we can tune w/l ratio(width/length). to tune delay we should tune w and l.
Spice is done to do with delays.which can be good for us in 
There is delay table to calculate delay of particular cell, which is combination of input slew, and output load,each buffer has its own delay table because the transistos used in it and the way those are arranged are different for different buffers as each and every transistors width and length are not in same dimension 
if considering a a buffer and its output load is 60fF and input slew of 40pF as shown in fig its between 50 and 70 then the delay of the buffer is also between 50 and 60 which x9'
by these tables we decide delay of the cell, 
lec 2 : 
N MOS
it's a 4 terminal device , consists of p substarte whcih is opposite in case of P MOS which is made up of n substrate, isolation region, n+ diffusion regions one of which is source and the other is  drain ,poly silicon gates, gate oxide, G-Gate, S-Source, D-Drin, B-Body terminal,

the most important one is Threshold voltage(Vt) considerations  in mosfets,
just explain the inversion , accumulation and depletion of N MOS,
 Accumulation in N mos is  when Vg < 0 (negative gate voltage)

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

and the potential at which it happens is called  "Threshold voltage"

if you increase further the gate voltage but there will not be any minority carriers left or majority carriers left to attract or repel respectively.

here the electrons from n+ source areas get attracted towards the gate the channel width gets increased and no change in depletion region width 

there will be a  continuous channel from source to drain and now after applying voltage to source ther will be flow of current through the channel.

Body terminal also effects the threshold voltage of the mosdfet.

Considering 2 scenarios:
picture here 

one is having no voltage applied to body terminal and one is connected to source 

the depletion region in the second is more compared to the first because you have additional reverse bias acting upon the body termianl this increases the depletion region width. and observation ishtat 
 inversion happens in the second diagram is a bit late compared to first if you increase the gate to source voltage.

 lect 4: pic here 
 the negatively charged particles are attarcted more in the source as the n+ source is connected to +ve terminal the accumulated negatively charged particle are pulled throught source area

 for a particular gate voltage the inversion happens in the first one but the channel is in the ascending order in the second one due to applied potential between body and source.
 conclusion fromthis is that we need a additional potential for strong inversion.

 the threshold voltage equation is  pic here:

this equation represents the mosfet

 gamma eqn pic here
 phi f pic here

Lec 5
 Resistive Operation 
 
if we increase Vgs>Vt we get more conductive region  at channel region
as we increase the Vgs the chanel width increases as induced charges is directly proportional to (Vgs -Vt)

 applying small drain to source voltage at Vgs = 1V and Vds = 0.05 v where Vt = 0.45V
 as Vgs >Vt we get condnuctive channel after applying small voltage here ,

 there is voltage gradient in the channel when the Vds is applied but before applying its constant through out channel.

 the channel length is greater than effective channel length (L) 
  the potential at different part or length of channel is different due to application of Vds 
  now before applying Vds every point on the channel has voltage of Vgs but after applying we get (Vgs - Vx)

   L6 :Drift current theory 

   induced charge at any poin tint ht eregion is Qi(x) = -Cox([Vgs - V(x)]-Vt)
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

for the given one s the VDS ≤ (VGS − Vt) the mosfet operates in the linear region the channel is continuous from source to drain 


L4 Spice conclusion to resisitve operation

drain current is linear function of Vgs-Vt 
 the impact of Vgs and Vds on Id 
 taking different values of Vgs and observing changes in the Id and we can sweep Vds from 0 to 0.05v 
 to take this and sweep and all this process needs a medium and that medium is SPICE it does it all .

Lec 5 Pinch off region condition:

 
what happens when Vds > (Vgs - Vt) it will be in saturation region
we are here increasing Vds from 0.05 to 0.45 v as  seen in the table 
during Vds upto 0.45 Vgs - Vds is greater than Vt
but if increased more then comes where Vgs- Vds  = Vt
here things will change 
where channel near source is at 1 v and channel near drain has a voltage of 0.45 v  
where the source is already inversion region but the channel near drain is just about inverted so the channel will be like  
pic here of pinch off type of thing :

the phenomenon of the channel getting disappered is called "Pinch off phenomenon"

after increasing more Vds where Vt >Vgs-Vds here the channel just disappears and this region is called saturation region



L6: Drain current model for saturation region of operation


the channel voltage remains constant in saturation region 
channel length is modulated with Vgs
its no more functiton of Vds 
as we got earlier equatioon of drain current [Id] :
drain current is function of all the  constants

effective conductive channel length is modulated by applied Vds 
Vds increases  then depletion region at drain increases and effective channel length decreases.
more accurate equation and where we add lamda as a channel length modulation

L1 Basic SPICE setup:

 























































































