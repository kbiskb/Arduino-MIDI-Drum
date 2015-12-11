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
![alt tag](https://cloud.githubusercontent.com/assets/14918833/11734040/3de48dbe-9f79-11e5-8cac-e8a4ba3bb400.png)
- Make sure the MIDI input of your MIDI software is correctly selected
- Enjoy the drum beats!


Drum Tuning 
- 
You can change certain parts of the code to adjust the setup and the sound of your drum set

- PadNote: These are the MIDI notes that will be played when a drum pad is triggered. They range from 0 to 127, where middle C is the number 60. Do not use a value above 127.
![alt tag](https://cloud.githubusercontent.com/assets/14918833/11734172/49d8465a-9f7a-11e5-89e2-f6e5df5b6ae5.PNG)

- PadCutOff: The Arduino reads analog values as a number from 0 to 1023. When you hit a drum pad the piezo creates a voltage spike and ripple. We are reading the value of this voltage spike. The padCutOff is the minimum value of this spike that we will accept as a drum hit. You can set it higher or lower. Lower will make more false triggers, but easier to make drum hits if your pads are thick. Higher will require you to hit the pads harder to make them sound, but you will get less false triggers from hitting a nearby pad if they are on the same surface.

- MaxPlayTime: Is a delay based on the number of times the main loop of the program runs through. This delay is intended to keep the kit from sounding multiple hits for one drum hit, since the Arduino is fast enough to read the same voltage spike a few times. If you are getting two hits etc, when you hit the drum only once, increase this number if there is too large a delay when you play a drum roll, then decrease this number. 

- VelocityFlag: Is a true or false setting to use velocity or not. Velocity is the value of how hard you hit the drum pad. A higher velocity would produce a louder drum sound.

(The above information is cited from SpikenzieLabs - Drum Kit - Kit, http://www.spikenzielabs.com/SpikenzieLabs/DrumKitKit.html)

Additional Information
- 
- The source code does not need library, however, I have unploaded the Arduino MIDI library on the Github. The source code is compatible with the Arduino MIDI Library. If you want to use the library, you need to initialise the Serial port after the MIDI library, like this:

    void setup() {

        MIDI.begin();
 
        Serial.begin(115200);

    }

  For more information please check the main page of the Hairless MIDI: http://projectgus.github.io/hairless-midiserial/



- According to my inspiration of this project: MIDI Arduino Drums by anouskadg 

  If you are using Mac OX instead of the Windows, you don't need to download LoopMIDI and Hairless MIDI, neither using your own MIDI   software. You can download the "Ardrumo" software, it would directly connect to your Arduino. More information please check his     instructable page (http://www.instructables.com/id/MIDI-Arduino-Drums/?ALLSTEPS)

Creadit
- 
This project is largly influenced by 
- MIDI Arduino Drums by anouskadg

http://www.instructables.com/id/MIDI-Arduino-Drums/?ALLSTEPS

- Drum Kit - Kit from SpikenzieLabs

http://www.spikenzielabs.com/SpikenzieLabs/DrumKitKit.html
