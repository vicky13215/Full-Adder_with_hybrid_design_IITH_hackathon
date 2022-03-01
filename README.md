# Full-Adder_with_hybrid_design_IITH_hackathon
Full-Adder Digital circuit design using full swing hybrid design style Using Synopsys Custom-compiler in 28nm technology
The performance of arithmetic circuits determines the 
overall performance of a digital device like processors. The
addition operation plays a basic role since several complex 
operations requires addition, that’s why FA is the most 
elementary building block. FA has to be pursued vigorously 
to bring overall improvement in any kind of circuit design 
with arithmetic unit. This design includes a full-swing 
hybrid FA based on XOR-XNOR logic-gates with invertors 
and pass transistors.
 Other conventional ways of designing FA cell are 
less effective than the proposed design of full-swing hybrid 
approach. Such conventional procedures are PassTransistor Method (PT) , complementary CMOS logicbased Mirror FA, series XOR-XNOR With delay between 
sum and output carry bit, GDI (Gate Diffusion Input ). The 
PT method suffers from threshold voltage drop issue. So for 
this additional buffer is required to restore the voltage level.
Complementary CMOS solves the voltage drop issue in PT 
method but it introduces high input impedance which slows 
down the circuit and high Transistor count increases silicon 
area. GDI method can be implemented with fewer 
transistors but it faces voltage degradation issue. GDI can be 
an excellent choice for designs or devices that requires low 
voltage or less silicon area. The proposed method id the 
modified version of CCMOS and GDI method where 
CCMOS logic deals with threshold voltage drop and GDI
deals with providing full swing with low voltage input.
 Here we are taking in total 18 – Transistors. The
whole circuit is divided in three stages, those are Invertor 
stage, XOR-XNOR stage and Pass Transistor stag. Two
different compartment is considered for sum and output
carry to eliminated Cell -to cell propagation delay. The 
proposed FA is expected to act as a single bit adder without 
any voltage drop issue in any internal nodes
