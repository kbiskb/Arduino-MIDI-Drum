# Arduino MIDI Drum

Xiao He

University of Regina 

CS207

#Abstract
This project demonstrates how to use piezo transducer and Arduino to create a simple electronic drum set which connects to the MIDI software in computer. The purpose of this project is that using cheap common materials and Arduino board to building an percussion instrument device which connect to the MIDI software in the computer in order to simulate the a electronic drum set. This page is going to showcase that the preparation for this project, as well as the procedure of parts assembly, coding and the connecting of each software.


Setup
- 
- 4x Piezo transducers
- 4x CD
- Paper plates (enough to cut 8 circles as big as the CD)
- Arduino + USB cable
- 4x 1M Ohm resistors
- PCB or breadboard
- Some wire

Instruction
- 
- Make sure that the wire on the piezo transducer is well soldered
- Follow the circuit diagram, connect the piezo transducers, resistors and Arduino
![alt tag](https://cloud.githubusercontent.com/assets/14918833/11733934/5536ea08-9f78-11e5-98a1-604af0025b58.jpg)
- After finishing the circuit, open Arduino and run the source code
- Download and install the LoopMIDI software from http://www.tobias-erichsen.de/software/loopmidi.html
- Run the LoopMIDI, click the "+" buttom to create a virtual port for the MIDI software
![alt tag](https://cloud.githubusercontent.com/assets/14918833/11733993/dad518d8-9f78-11e5-97e8-a9274e54ce17.PNG)
- Download and install the Hairless MIDI software from http://projectgus.github.io/hairless-midiserial/
- Run the Hairless MIDI, select the same USB serial port as the one in your source code. Select the MIDI in & out port as the one you just created from the LoopMIDI
- Make sure the MIDI input of your MIDI software is correctly selected
- Enjoy the drum beats!
