# Traffic-light-controller
   I.INTRODUCTION


Traffic jams are major problem faced in many of the
metropolitan cities and towns all over the earth. Traffic
congestion causes many problems and challenges in
cities. To travel within the cities has become a big
problem. Due to these problems people lose their time,
money and most importantly the energy resources will
be get exhausted very rapidly due to the continual use
in the automobiles. This traffic jam decreases the
productivity of the workers, traders, suppliers and in
all effecting the market. To solve these traffic related
problems, we have to build new devices &
infrastructure to make ease of transport but at the same
time we have to make them smart. The only
disadvantage in construction of the more roads on
good facilities is that it makes the surroundings more
obstructed and congested, but then this TLC system
would be able to provide much relief from the traffic
and it will provides new ways to ease the traffic. All
the countries are working to solve the problem of
traffic flow and advance transportation and reduce the
demand of vehicle use.
Lights of system have been used to manage and
control the congestion of traffic at each road of
intersection using light cycle schedules. The traffic
light works on the specific manner switching of red,
yellow and green lights in a particular way with unique
time form. They provide safe management of traffic to
share the road intersection. The constant delay at each
road intersection decreases the traffic flow and then
these results into decrement of the traffic efficiency all
over the road network.
Traditional traffic control system had a drawback due
to fixed timing of traffic signals, the traffic had to hold
for long time on the lane with less vehicle while the
lane having more vehicle cannot pass in short time. So,
we need to develop a reliable, fast and smart traffic
control system capable to control the traffic in rush
hours without a need of traffic man.
Our project is basically first be digitally designed
using logic gates. It is a sequential machine which can
be model it in Verilog by different methods just like
Gate Level Modeling, Data Flow Modeling & Finite
State Machine. We use Finite State Machine (FSM)
method to model our TLC. Our whole project (i.e.
Schematic, Verilog Code, Synthesis) done using
XILINX 14.7 design suit. TLC is further implemented
on Field Programmable Gate Array using Xilinx
software.

II.OBJECTIVE

Traffic Light Controllers are used to manipulate
traffics at areas that are shared among multiple lanes
called intersections by managing the access of traffics
to the particular lane in intersections and create
effective interval of time between various junctions.
The primary objective of this project is to control the
traffic movement of crossing lanes and acquire the
finest use of the traffic light. Generally, traffic light
control system of all main roads are managed with a
rigid timing system but on the other hand the smaller
roads are controlled by the sensors autonomously.
Our main objective is to design a specific four-way
traffic system that have flexible waiting time with
respect to density of vehicles as such it does not create
any congestion at the intersection and save time of the
people. 

III.DESIGN OF TRAFFIC LIGHT CONTROL

3.1 ROAD STRUCTURE:

Our objective to design traffic control system, so we
have taken a four-way simple intersection as shown in (MECHANISM)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/fb71ba54-b770-4825-bae5-02fc84462b45)
      
We have taken 4 direction and each direction has there
3 specific lights (RED, GREEN, YELLO W). We have
provided a fixed time difference as for default case. As
timing plays very important role in the TLC that must
be set very wisely and precisely, so that any dangerous
situation i.e. accident of cars can be avoided. The TLC
timing setting are as follow: -
•Green
The green light timer is 16sec for rush lane and 8sec
for not rush lane.
•Yellow
The timing of yellow to be set for 4 sec for rush and
not rush lane.
•Red
The timing of red to be fixed for 2 sec for rush and not
rush lane

3.2 FUNCTIONAL BLOCK:

Here we have proposed the system for the abovedescribed problem as shown in figure2. In this figure
we have shown the Logic Block diagram(BLOCK DIAGARM OF SYSTEM)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/b7dd1a4b-99fa-43ea-8ca2-4b68f9986a56)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/194e73ce-be63-48cc-80e2-7a9f4dc355f1)

		of our traffic light controller it consists of four main
units are as follows combinational, sequential, timing
and display unit. Each unit has its own functionality to
perform in the controller.

3.2.1 SEQUENTIAL UNIT:

Sequential unit responsible for generating state
transition state for the combinational unit to perform
respective task. This unit consists of the counters here
is the example of asynchronous counter.
Asynchronous Up counter is a sequential circuit that
counts from 0 to some defined state. It is an
asynchronous counter built using T flip flops. Here we
are using 7 bit counter that counts 128 states i.e. from
0 to 127. Following is the representation of schematic
and RTL view of the same.

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/93528d6e-4950-46d6-87ab-f233cf8e5a73)

RTL AND SCHEMATIC VIEW OF
COUNTER

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/2136ece0-cca2-4b4e-8f12-3cc711df581d)

3.2.2 COMBINATIONAL UNIT:

Combinational unit main task to perform the
comparison of generated state transition state to a
fixed state stated. So to do so we use a comparator to
compare bits and perform desired task which to
provide display unit and traffic indicator a specific
value.
The comparator is combinational logic circuit that
compare 2 binary numbers and produce result on
comparison of those two numbers. Here we are using
8-bit comparator that takes 8-bit inputs of input A & 8
inputs of input B & have 3 outputs : AGB(input1 is
greater than input2); AEB(input1 & input2 are equal)
BGA(input2 is greater than input1). This comparator
has an additional feature of the reset pin that is when
reset pin is active low(0) then all three outputs are
zero.(comparator 8 bit)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/177e77ae-1937-4c7a-bfb5-0103bc05e50f)

( RTL AND SCHEMATIC VIEW OF
COMPARATOR)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/57577e77-60e8-41f7-a356-19f87a19c611)

3.2.3 TIMING UNIT:

Timing unit provide the clock signal to the whole
design which is further responsible for the proper
generation of the clock pulse with desired frequency
to provide desired output.
This asynchronous clock is a clock whose time period
is 1 second or frequency is 1 hertz. This clock is built
using connecting number of T flip flops in series.

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/55d93b63-80cd-49bb-a3dd-7e5c43ae14fa)


![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/78bab262-19dd-463e-864b-f4083f4ffaf6)

3.2.4 DISPLAY UNIT:

Display unit is responsible for the generation of the
signal required for the seven segment of the board.
It generates the combinational output to a specific bits
to generate desired output at the seven segment.
Here we are using 3X8 decoder that have 3 inputs, 8
outputs & 1 enable line.
The decoder will works only when the enable pin is in
active high state. When the enable is low, the output
of decoder is zero.(RTL AND SCHEMATIC VIEW OF
DECODER)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/1c34575a-0d62-4960-86d3-a88603f495c6)

![image](https://github.com/Roki523/Traffic-light-controller/assets/109354329/08762f63-0672-4f0a-84d2-89591b37eab0)

DIGITAL DESIGNING:

For better learning and understanding of TLC we have
to design the schematic of the controller using basic
logic gates. We have to design this sequential machine
using basic component of sequential circuit. We first
design flip flop, latches and further counters to
complete our project. Our project also requires some
combinational circuitry to provide better timing logics
to design we use bottom up approach to construct the
project. We design schematic on Xilinx tool.
