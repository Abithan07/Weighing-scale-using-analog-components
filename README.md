# Weighing-scale-using-analog-components
The devised system aims to accurately measure weight at 1g precision utilizing a 10kg load cell and Analog electronic components.

Block Diagram of the Weighing scale:

![blockdiagram](https://github.com/user-attachments/assets/a4bfde00-f721-4b04-baf9-c016ec7a85cd)

The important part of the design is an instrumental amplifier employing three ADA4062-2BRZ operational amplifiers, strategically configured to achieve a high ideal gain of 401. In addition to that, a voltage adder circuit, integrated for offset correction, fine-tunes the system's accuracy. This architecture not only accommodates the load cell's output voltage but also leverages the ADA4062-2BRZ Op-Amps for their low offset voltage and capability to handle high input voltages (up to 6V reference to ground). The dual supply, providing +12V and -12V, serves not only to power the Op-Amps but also as a measure to minimize noise interference.

instrumentation amplifier is used for our weighing scale because of the following characteristics.
1. High Input Impedance: Due to its high input impedance, we can restrict it from drawing even minor currents from the load cell which can cause false readings.
2. Differential Input: This amplifier amplifies the voltage difference between two input signals. This allows us to get rid of noise signals which are common to both inputs.
3. Low Drift: Since the output from the load cell is significantly small the reading need to be as precise as possible. Instrumental amplifiers have low drift over environmental factor variations which makes this suitable  for our product. 
4. Low Noise Interference: Since the instrumental amplifier only has the differential voltage, any noise available in the power supply could be neglected.

Voltage adder circuit for reference:

![adder](https://github.com/user-attachments/assets/1dd06a0f-faa8-4684-85c9-5c6d5c97a2cd)

Operational Amplifier circuit for reference:

![Ins](https://github.com/user-attachments/assets/f811dbac-35f3-470d-9282-8ca6dd0eaba8)

Schematic Diagram of our Circuit:

![5](https://github.com/user-attachments/assets/a9bd57c5-d465-43f6-8e01-36364330c46e)

A linear power supply had to be made to power up the Weighing scale.
First, the 220/240V AC is converted to 15V AC using a step-down transformer. The primary terminals of the transformer are connected to the household supply while the secondary terminals are connected to the rectifier circuit. It is important to highlight that we have used a center-tapped transformer since it is easier to produce positive voltage as well as negative voltage from the same circuit. A 15V center-tapped transformer will measure 30V AC across the outer two taps (winding as a whole), and 15V AC from each outer tap to the center-tap (half winding). These two 15V AC supplies are 180 degrees out of phase with each other.

After that, by using a full bridge rectifier 15V AC supply is converted to a DC supply. 1000uF/50V capacitors are used to filter out the ripples and make it a pure DC supply. Then L7812 IC is used to get +12V regulated output and L7912 IC is used to get -12V regulated output. From the +12V regulated output, another +5V regulated output is produced using the IC L7805. 10uF/25V and 0.1uF capacitors are used to remove any kind of ripples in the DC supply and remove any high-frequency noise in the DC output.

Schematic Diagram:

![powersupply](https://github.com/user-attachments/assets/feef5c6f-1fd6-4773-a355-b461c911813b)

A microcontroller unit had to be implemented to display the output on a 16x2 LCD display.
The augmentation of the weight measurement system involves the integration of a 16-bit ADS1115 Module and an ESP32 WROOM 32E module. This addition enhances the capabilities of the instrumental amplifier and the voltage adder circuit. The ADS1115 Module serves as a high-precision Analog-to-Digital Converter (ADC), while the ESP32 WROOM 32E module acts as the micro-controller responsible for data processing and interfacing with the external display. The collaboration of these components introduces digital processing capabilities to the analog weight measurement system. The schematic for microcontroller is below

![6](https://github.com/user-attachments/assets/b44531e9-52e1-42a6-ac90-851d7d5f9a32)

PCB Layout:

![7](https://github.com/user-attachments/assets/9bcf2b4d-b7cb-4d3b-8d17-59f69787ba2f)
![10](https://github.com/user-attachments/assets/7d69f172-fd68-4c5f-85f2-e3259b64c1b7)

Enclosure:

![enc](https://github.com/user-attachments/assets/4c52742f-4a28-41b7-9f17-0f0a9162d507)
![12](https://github.com/user-attachments/assets/21cda94e-5eb3-45b7-b686-18a0ceb594f4)


