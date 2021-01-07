<h1>:point_right:Project idea </h1>
<h4> The main idea of this project is that we control the stepper motor speed through two modes half speed and full speed and we can also control its shutdown using three switches and show the current mode in seven segment. </h4>
<h1>:point_right:Used components </h1>
<ul><h4>
  <li> 8086 Microprocessor </li>
  <li> 8255A PPI</li>
  <li> 74HC373 latch </li>
  <li> ULN2003A motor driver </li>
  <li> Unipolar Stepper motor </li>
  <li> switch (3) </li>
  <li> 7-Segment-com-cath </li>
  </h4>
</ul>
<h1>:point_right:Stepper motor </h1>
<h3>A stepper motor has the following features:</h3>
<ul><h4>
  <li> Both-direction rotation </li>
  <li> precision angular incremental changes</li>
  <li> capability for digital control </li>
  <li> holding torque at zero speed </li>
  <li> Unipolar Stepper motor </li>
  <li> repetition of accurate motion or velocity profiles </li>
  </h4>
</ul>
<h3>we choose the unipolar stepper motor:</h3>
<h4>Unipolar stepping motors have a center tap wired to the positive supply on each of two windings. The two ends of each winding are alternately grounded to reverse the direction of the magnetic field. The rotor would require proportionally more poles for higher angular resolutions. 30 degree per step mot4or is a common permanent magnet motor design. Control sequences in the windings spin the motor. The magnet is rotated one step at a time and the two halves of each winding are never energized at the same time.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103836193-02a85b80-5091-11eb-8146-49a13cbb3036.jpg" width="350" height="300">
<h1>:point_right:ULN2003A motor driver </h1>
<h4>The ULN2003A is an array of seven NPN Darlington transistors capable of 500 mA, 50 V output. It features common-cathode flyback diodes for switching inductive loads.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103838495-dfcc7600-5095-11eb-9521-2b9796aadb39.PNG" width="350" height="350">

<h1>:point_right:Programmable peripheral interface 8255</h1>
<h4>PPI 8255 is a general purpose programmable I/O device designed to interface the CPU with its outside world. It consists of three 8-bit bidirectional I/O ports i.e. PORT A, PORT B and PORT C. We can assign different ports as input or output functions. It consists of 40 pins each port has 8 pins and operates in +5V regulated power supply.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103838041-b95a0b00-5094-11eb-9662-3358d5a6b94b.png" width="250" height="400">
<h4>Depending upon the value if CS’, A1 and A0 we can select different ports in different modes as input-output function or BSR. This is done by writing a suitable word in control register (control word D0-D7).</h4>
<h4>:heavy_check_mark:the control word we use is 10000010</h4>
<img src="https://user-images.githubusercontent.com/42392736/103838495-dfcc7600-5095-11eb-9521-2b9796aadb39.PNG" width="350" height="350">
<img src="https://user-images.githubusercontent.com/42392736/103839133-603fa680-5097-11eb-848d-01f3b30570c4.jpeg" width="370" height="370">
<h1>:point_right:74HC373 latch</h1>
<h4>We use 74HC373 latch to latch the address of wanted port in 8255A PPI from microprocessor and then send the data to this port. Microprocessor send address of the wanted port in 8255A PPI to 74HC373 and then enable latch (LE). 74HC373 will latch D1 nad D2, then microprocessor send data to the wanted port in 8255A PPI through 74HC373.</h4>
<h4>The 74HC373 is an octal D-type transparent latch featuring separate D-type  inputs for each latch and 3-state outputs for bus oriented applications. A latch enable (LE) input and an output enable (OE) input are common to all latches.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103842706-30949c80-509f-11eb-8858-4bda201a7061.jpg" width="250" height="250">


