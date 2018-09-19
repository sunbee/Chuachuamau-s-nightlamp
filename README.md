# Chuachuamau-s-nightlamp

#### Your child wakes up and night and cries out loud?
#### Chuachua-lamp's soothing glow shall soothe the little one's anxiety.
#### Psychologists attest to Chuachua-lamp's efficacy.
#### Say "Goodbye!" to fatigue and "Hello!" to a good night's sleep.

## Mechanical Schematic
![chuachua-lamp mechanical-01](https://user-images.githubusercontent.com/5471571/45725970-3682ae80-bb72-11e8-8b7c-f77dcac852eb.png)
The string LED lights (white LED, 4.5V) in a decorative glass bottle sit on a base housing the electronics. I have used PVC pipe for the base. The end-cap is fitted on a section of pipe. I have drilled a hole in the end-cap (1.25") with a saw drill. The base also has the Passive Infra-Red (PIR) sensor, modified with a Light Detect Resistor (LDR) soldered on so as to "detect motion in the dark". In the absence of motion or presence of light, the PIR sensor reads digital low. 

## Electrical Schematic
![pi mosfet led](https://user-images.githubusercontent.com/5471571/45726032-69c53d80-bb72-11e8-9e78-d760282ea3bb.jpg)
The project does not require a microprocessor, though connectors are provided for a nodemcu. The schematic has a n-channel mosfet (IRF520). The gate voltage is set by PIR signal pin and the load is connected on the drain-side and ground connected to source. When the gate receives a digital high, (which is when motion is detected in the dark,) the drain and source are shorted so current flows and the LED strip is switched on. When the gate receives a digital low, the drain and source are open and no current can flow. The LED strip is switched off.

The circuit was assembled on a PCB with soldering after first testing on a breadboard. Circuit construction is in three steps.

![chuachua-lamp electric-02](https://user-images.githubusercontent.com/5471571/45725971-371b4500-bb72-11e8-900b-5cf7a01cf619.png)
First, mount the MOSFET and provide terminal connectors for the power/ground rails. While the LED is rated for 4.5V, it is sufficient to provide 3.3V.

![chuachua-lamp electric-03](https://user-images.githubusercontent.com/5471571/45725972-371b4500-bb72-11e8-956b-d18797988085.png)
Second, connect the PIR sensor's signal to the MOSFET gate. The gate is the first pin, then drain, then source. The PIR sensor also needs power which it draws off the power rail.

![chuachua-lamp electric-04](https://user-images.githubusercontent.com/5471571/45725973-371b4500-bb72-11e8-90db-a48cea09736a.png)
Third, add the LED lights. One pin goes to the power rail. The other goes to the drain of the MOSFET. The MOSFET's source is connected to ground rail. 

## Digital Schematic
When the PIR sensor triggers the MOSFET, drain and source are shorted and current can flow, turning on the LED lights.

# Final Product
![chuachua-lamp dancinglights](https://user-images.githubusercontent.com/5471571/45726935-6c299680-bb76-11e8-85cf-3c47755ada65.jpg)
![chuachua-lamp dancinglightsday](https://user-images.githubusercontent.com/5471571/45726936-6c299680-bb76-11e8-9dce-62ae504fb989.jpg)
![chuachua-lamp dancinglightsnodemcu](https://user-images.githubusercontent.com/5471571/45726937-6c299680-bb76-11e8-9c50-f2f72b047797.jpg)

