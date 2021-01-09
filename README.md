<h1>:point_right:Project idea </h1>
<h3>First idea:</h3>
<h4> The main idea of this project is that we control the stepper motor speed through two modes half speed and full speed and we can also control its shutdown using three switches and show the current mode in seven segment. </h4>
<h3>Second idea:</h3>
<h4>We control the speed of stepper motor through potentiometer, the potentiometer adjust the speed to zero (stop), half speed, full speed or in between.</h4>
<h1>:point_right:Used components </h1>
<ul><h4>
  <li> 8086 Microprocessor </li>
  <li> 8255A PPI</li>
  <li> 74HC373 latch </li>
  <li> ULN2003A motor driver </li>
  <li> Unipolar Stepper motor </li>
  <li> switch (3) </li>
  <li> 7-Segment-com-cath </li>
  <li> Potentiometer</li>
  <li> ADC0804</li>
  </h4>
</ul>

<h1>:point_right:8086 Microprocessor </h1>
<h4>Intel 8086 is a 16-bit processor designed by Intel. It is a processor that handles a 16-bit word at a time. The data is stored inside the processor in the registers and the different addresses are stored in it. We use it to control the speed of stepper motor</h4>
<img src="https://user-images.githubusercontent.com/42392736/103960593-2cc65000-515b-11eb-9f09-f7ef19612bad.jpeg" width="450" height="450">


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
<img src="https://user-images.githubusercontent.com/42392736/103959149-92184200-5157-11eb-8fca-cd4cdd7c1ea3.jpg" width="450" height="300">

<h1>:point_right:ULN2003A motor driver </h1>
<h4>The ULN2003A is an array of seven NPN Darlington transistors capable of 500 mA, 50 V output. It features common-cathode flyback diodes for switching inductive loads.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103940688-6e90cf80-5136-11eb-93fb-060149a6cfc3.jpeg" width="350" height="350">
<h3>The connection between stepper motor and ULN2003A motor driver:</h3>
<h4>If the driver take high inpit the output to stepper motor will be low becouse of NPN transistors, then the coil in stepper motor will be energized because 2,5 of motor connected to supply.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103941080-04c4f580-5137-11eb-8321-8c2f3d31264e.jpeg" width="600" height="370">
<h4>The figure below illustrate the word wich we give to driver to move the stepper motor to the corresponding angle:  </h4>
<img src="https://user-images.githubusercontent.com/42392736/103947644-1ad7b380-5141-11eb-9261-b989cc38ce3f.jpeg" width="480" height="200">
<img src="https://user-images.githubusercontent.com/42392736/103946104-e531cb00-513e-11eb-8143-d49ae5924278.PNG" width="500" height="500">

<h1>:point_right:Programmable peripheral interface 8255A</h1>
<h4>PPI 8255 is a general purpose programmable I/O device designed to interface the CPU with its outside world. It consists of three 8-bit bidirectional I/O ports i.e. PORT A, PORT B and PORT C. We can assign different ports as input or output functions. It consists of 40 pins each port has 8 pins and operates in +5V regulated power supply.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103838041-b95a0b00-5094-11eb-9662-3358d5a6b94b.png" width="250" height="400">
<h4>Depending upon the value if CS’, A1 and A0 we can select different ports in different modes as input-output function or BSR. This is done by writing a suitable word in control register (control word D0-D7).</h4>
<h4>:heavy_check_mark:the control word we use is 10000010</h4>
<img src="https://user-images.githubusercontent.com/42392736/103838495-dfcc7600-5095-11eb-9521-2b9796aadb39.PNG" width="350" height="350">
<img src="https://user-images.githubusercontent.com/42392736/103839133-603fa680-5097-11eb-848d-01f3b30570c4.jpeg" width="370" height="370">

<h1>:point_right:74HC373 latch</h1>
<h4>We use 74HC373 latch to latch the address of wanted port in 8255A PPI from microprocessor and then send the data to this port. Microprocessor send address of the wanted port in 8255A PPI to 74HC373 and then enable latch (LE). 74HC373 will latch D1 nad D2, then microprocessor send data to the wanted port in 8255A PPI through 74HC373.</h4>
<h4>The 74HC373 is an octal D-type transparent latch featuring separate D-type  inputs for each latch and 3-state outputs for bus oriented applications. A latch enable (LE) input and an output enable (OE) input are common to all latches.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103951933-32ff0100-5148-11eb-8927-67fb7010e5b0.jpg" width="350" height="300">

<h1>:point_right:Seven segment (only used in first idea)</h1>
<h4>We use seven segment as indecator for the mode of the speed of motor if we press the stop button the seven segment will display S, if we press half speed button the seven segment will display H and if we press the full speed button it will display F.</h4>
<h4>We use common cathode seven segment and the figures below illustrate the how turn on the wanted leds of seven segment.</h4>
<img src="https://user-images.githubusercontent.com/42392736/103959138-862c8000-5157-11eb-8cb9-e51969026dd3.jpeg" width="350" height="300">
<img src="https://user-images.githubusercontent.com/42392736/103959143-8a589d80-5157-11eb-8677-5f6a2e74f945.jpeg" width="600" height="125">

<h1>:point_right:ADC0804 (only used in second idea)</h1>
<h4>We use ADC0804 to convert analog voltage from potentiometer to digital Byte, RD is always 0 to read the input voltage and WR is activated by microprocessor to write output with Consideration of conversion time. We use the internal clock so, we don't need CLK 1N and CLK R pins. VREF/2 connected to 2.5V</h4>
<h4>The delay between each step is determined by the value of potentiopmeter</h4>
<h4>The conversion equation is : Delay = -8*ADC reading + 3070</h4>


<h1>:point_right:Used software</h1>
<h4>1- Protues </h4>
<h4>2- 8086 emulator with MASM </h4>

<h1>:point_right:Final output</h1>
<img src="https://user-images.githubusercontent.com/42392736/103961141-8713e080-515c-11eb-9ff0-15708af2aea9.jpeg" width="900" height="500">

<h3>Click <a href="https://drive.google.com/drive/folders/1z2TzqNHUqyom_a3JSKWFnRi2yTt0ns6R?fbclid=IwAR1vklL28VaapCjOJnxKrqtcrWCAHoyKdaGmzMS5CzshH2tQiasO6wQ6pFI">here</a> to show the simulation video</h3>

<h1>:point_right:Collabrators</h1>
<ul>
  <li><h2>Mostafa mokhtar</h2></li>
  mostafa160875@feng.bu.edu.eg
  <li><h2>Hader Ashraf</h2></li>
  hadeer160958@feng.bu.edu.eg
  <li><h2>Mohamed Mahmoud</h2></li>
  mohamed160733@feng.bu.edu.eg
  <li><h2>Salah Rasmy</h2></li>
  salah160393@feng.bu.edu.eg
  <li><h2>Michael Magdy</h2></li>
  Mikael160570@feng.bu.edu
</ul>
