# Full-Adder_with_hybrid_design_IITH_hackathon

# Abstract
 Here, I am going to design and implement 1-bit Full Adder cell in full-swing hybrid logic style using 28nm technology.This proposed adder is supposed to achieve improvement in Propagation delay, improvement in average power and also improvement in power delay product in comparison to conventional CMOS mirror Full-Adder while operating at 0.8 volts. As a whole, the performance is better than rest od the adder cell.
 
# Introduction
Full-Adder Digital circuit design using full swing hybrid design style Using Synopsys Custom-compiler in 28nm technology
 Here, I am going to design and implement 1-bit Full Adder cell in full-swing hybrid logic style using 28nm technology.This proposed adder is supposed to achieve improvement in Propagation delay, improvement in average power and also improvement in power delay product in comparison to conventional CMOS mirror Full-Adder while operating at 1.8 
volts. As a whole, the performance is better than rest od the Full Adder cell.

# Truth Table for Full-Adder
![tt](https://user-images.githubusercontent.com/38467140/156208854-d7bd19f1-1a86-4c0b-b109-c3166c5cdbed.JPG)

# Proposed Circuit
![Circuit diagram](https://user-images.githubusercontent.com/38467140/156209679-288de7e9-4fb4-4c06-ac66-54df08f7d35d.JPG)

# Proposed sum generation circuit
Table 2 presents input‐output logic along with the full swing transistor paths for Sum signal generation. The operation of the Sum generation circuit can be explained as follows:

Case 1 (Cin ¼ 0 and AB ¼ 00= 11): The XNOR signal is 1 which turns ON n7. Source/ drain side input of n7 isCin ¼ 0; which is passed towards the output Sum node as a strong logic 0.

Case 2 (Cin ¼ 0 and AB ¼ 01= 10): Cin ¼ 0 turns ON p6. Source/ drain side input of p6 is XOR = 1, which is passed towards the output Sum node as strong logic 1.

Case 3 (Cin ¼ 1 and AB ¼ 00= 11): The XOR signal is 0 which turns ON p7. Source/ drain side input of p7 is Cin ¼ 1; which is passed towards the output Sum node as strong logic1.

Case 4 (Cin ¼ 1 and AB ¼ 01= 10): Cin ¼ 1 turns ON n6.Source/ drain side input of n6 is XNOR = 0, which ispassed towards the output Sum node as strong logic 0.


# Carry generation circuit
The carry generation circuit used in the proposed FA cell is similar to the carry circuit. The operation of the carry generation circuit used in the proposed FA cell is described as follows:


Case 1 (Cin ¼ 0=1 and AB ¼ 00): XNOR = 1 turns ON n8.
The diffusion side input of n8 is B ¼ 0. This B ¼ 0 is passed towards the output Cout node as strong logic 0.

Case 2 (Cin ¼ 0 and AB ¼ 01= 10): XOR = 1 turns ON n9.
The diffusion side input of n9 is Cin ¼ 0; which is passed towards the output Cout node as strong logic 0.

Case 3 (Cin ¼ 1 and AB ¼ 01= 10): XNOR = 0 turns ON p8.
The diffusion side input of p8is Cin ¼ 1; which is passed towards the output Cout node as strong logic 1.

Case 4 (Cin ¼ 0=1 and AB ¼ 11): XOR = 0 turns ON p9.
The diffusion side input of p9 is A ¼ 1; 1 which is passed towards the output Cout node as strong logic 1.

It is clear from Table 2 that the carry generation circuit of the proposed FA provides full swing output.
# Circuits and Waveforms
/Invertor and XOR-XNOR circuit generation:
![XOR_XNOR_ _Invertor_circuit](https://user-images.githubusercontent.com/38467140/156210171-bc420f64-525e-4591-8282-0a01273d7cd6.JPG)

/Sum-generator circuit:
![sumJPG](https://user-images.githubusercontent.com/38467140/156210298-786758b2-176b-4379-ac2a-ac4dcc107b08.JPG)

/Carry-generator Circuit:
![carry](https://user-images.githubusercontent.com/38467140/156210412-ebf1f4f3-480f-46f9-a1e2-00766be52982.JPG)

/Test-bench Circuit:
![tb](https://user-images.githubusercontent.com/38467140/156211109-28adbb85-c943-48d7-ab84-feb35ebae03f.JPG)

/Final Waveform:
![actual_waveform](https://user-images.githubusercontent.com/38467140/156211180-85cf5578-1068-4f2b-8cc6-33c89f76ac02.JPG)


# Netlist
*  Generated for: PrimeSim
*  Design library name: FA_lib1
*  Design cell name: testbench
*  Design view name: schematic
.lib '/PDK/SAED_PDK32nm/hspice/saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Tue Mar  1 16:50:41 2022

.global gnd! vdd!
********************************************************************************
* Library          : FA_lib1
* Cell             : carry
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt carry a_input b_input c_input carry_output xnor_input xor_input
+ vt_bulk_n_gnd! vt_bulk_p_vdd!
xm1 carry_output xnor_input b_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 carry_output xor_input c_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm3 carry_output xor_input a_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm2 carry_output xnor_input c_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
.ends carry

********************************************************************************
* Library          : FA_lib1
* Cell             : fa
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt fa a_input b_input gnd_1 vdd xnor xor vt_bulk_n_gnd! vt_bulk_p_vdd!
xm9 xor b_input net39 vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm8 xor net39 b_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm7 xnor net24 a_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm6 xnor a_input b_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm0 vdd a_input net39 vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm5 xor net24 a_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm4 xor a_input b_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm3 xnor net39 b_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm2 xnor b_input net39 vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm1 gnd_1 a_input net39 vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
.ends fa

********************************************************************************
* Library          : FA_lib1
* Cell             : sum
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt sum c_input xnor_input xor_input sum_output vt_bulk_n_gnd!
+ vt_bulk_p_vdd!
xm2 sum_output xor_input c_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm0 sum_output c_input xor_input vt_bulk_p_vdd! p105 w=0.1u l=0.03u nf=1 m=1
xm4 sum_output xnor_input c_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
xm3 sum_output c_input xnor_input vt_bulk_n_gnd! n105 w=0.1u l=0.03u nf=1 m=1
.ends sum

********************************************************************************
* Library          : FA_lib1
* Cell             : testbench
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 a_input b_input c_input carry net27 net9 gnd! vdd! carry
xi1 a_input b_input gnd! net17 net27 net9 gnd! vdd! fa
xi2 c_input net27 net9 sum gnd! vdd! sum
v3 net17 gnd! dc=1.8
vc_input c_input gnd! dc=1.8 pulse ( 1.8 0 0 1p 1p 20n 40n )
vb_input b_input gnd! dc=1.8 pulse ( 1.8 0 0 1p 1p 10n 20n )
va_input a_input gnd! dc=1.8 pulse ( 1.8 0 0 1p 1p 5n 10n )
c10 carry gnd! c=1f
c11 sum gnd! c=1f

.tran '0.001*(100ns-0)' '100ns' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(a_input) v(b_input) v(c_input) v(carry) v(sum)

.temp 25

.option primesim_output=wdf

.option parhier = LOCAL

.end

# Reference
1.  A high‐performance full swing 1‐bit hybrid full 
adder cell [Shahbaz Hussain1 | Mehedi Hasan2,3 | 
Gazal Agrawal1 | Mohd Hasan1 1 Department of 
Electronics Engineering, Aligarh Muslim University, 
Aligarh, Uttar Pradesh, India ]
2. Design of Analog CMOS Integrated Circuits
# Acknowledgements
-Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.

-Cloud Based Analog IC Design Hackathon

-Synopsys India

-Sameer Durgoji, NIT Karnataka

-Chinmay panda, IIT Hyderabad
# Author
Bikram Keshari Panda

Masters Grad at NIT , Jamshedpur

Specialisation: Embedded System Design

Email ID: vikramkeshari002@gmail.com
