# CMOS-circuit-design-and-spice-simulation
Logic gates are made up of P mos and N mos in particular arrangemnet which gives a particular output be like and, nor, not, or gates etc, gates are tied together and this king of connection gives you invertor,In circuit design we try to understand different p mos and n mos transistors gives you which kind of output, the following graphs represent characterisitcs graphs of N mos 
pict here
the inverted one repressents that of P mos, when you after simulating in spice  you get a curve like the below one 
the waveforms determines the delay of the transistor. based on delay we can tune w/l ratio(width/length). to tune delay we should tune w and l.
Spice is done to do with delays.which can be good for us in 
There is delay table to calculate delay of particular cell, which is combination of input slew, and output load,each buffer has its own delay table because the transistos used in it and the way those are arranged are different for different buffers as each and every transistors width and length are not in same dimension 
if considering a a buffer and its output load is 60fF and input slew of 40pF as shown in fig its between 50 and 70 then the delay of the buffer is also between 50 and 60 which x9'
