# MP2494 DC-DC Converter

This repository contains the hardware design files for a **DC/DC Buck Converter** based on the **MP2494 Step-Down Regulator IC**. The design focuses on **Low EMI**, **High Efficiency**, and **Reliable PCB Layout Practices** to ensure stable operation. You will find resources such as datasheets, specifications, design considerations, schematics, layouts, and 3D previews of the board.  

## 📑 Datasheet  

The MP2494 is a **monolithic step-down switch mode converter**. It delivers up to **2A continuous output current** across a wide input voltage range with excellent load and line regulation.  

- Features low EMI signature with controlled switching edges.  
- Built-in protections: **cycle-by-cycle current limiting** and **thermal shutdown**.  
- Requires only a few standard external components.  
- Available in **SOIC8** and **SOIC8E** packages.  

The MP2494 uses a **current-mode control architecture**:  
- At the start of a cycle, the switch turns on, connecting the inductor to the input supply.  
- The inductor current is sensed and compared with the Error Amplifier output.  
- When the sensed current exceeds the control threshold, the switch is turned off.  
- A Schottky diode carries inductor current during the off cycle.  

![Datasheet Diagram_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/MP2494_Datasheet_1.png)
##
![Datasheet Diagram_2](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/MP2494_Datasheet_2.png)

## ⚙️ Specifications

* Input Voltage Range: **10V – 48V**
* Nominal Voltage: **12V**
* Output Voltage: **5V**
* Output Current: **2A**
* Switching Frequency: **100kHz (typical)**
* Inductor Ripple Current: **38%**
* Slew Rate of Transient: **1 A/µs**
* Protection: **OCP, Thermal Shutdown**
* Efficiency (measured): **~85.55%**

# MPS Design Tool Simulation
![Specifications](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/MPS-DCDC-Designer-MP2494.png)

## 🛠️ Design Considerations

When designing the PCB, follow these layout guidelines for stable operation and reduced EMI:

1. Place the **input capacitor** and **freewheel diode** on the same PCB layer as the IC and as close as possible to the IC pins.
2. Use **thermal vias** if necessary to improve heat dissipation.
3. Place the **inductor close to the IC**, but it does not need to be as close as the input capacitor. Keep copper area for the switching node minimal to reduce noise radiation.
4. Place the **output capacitor close to the inductor**.
5. Keep the **ground return path** away from noise-sensitive components.

Additional Notes:

* For mounting holes, GND connection depends on mechanical and shielding needs.
* Edge plating is not required for all boards but can help in high-current, EMI-sensitive designs.
* The EN pin can be tied to VIN (always-on) or controlled via a resistor divider (optional R7).

![Layout Considerations_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_Consideration_1.png)
##
![Layout Considerations_2](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_Consideration_2.png)
##
![Layout Considerations_3](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_Consideration_3.png)


## 📐 Schematic

![Schematic](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Schematic.png)

## 🧩 Layout

![Layout_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_1.png)
##
![Layout_2](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_Top.png)
##
![Layout_3](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Layout_Bottom.png)

## 🎨 3D View

![3D_View_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Project_MP2494_3D_1.png)
##
![3D_View_2](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/Project_MP2494_3D_2.png)

## 📌 Notes

* Efficiency achieved: **~85.5%** (very good for this design).
* Mounting hole GND connection is optional, depending on mechanical and EMI needs.
* R7 is optional: if EN pin should be always active, tie directly to VIN.
* Edge plating is not mandatory unless your design requires **high shielding or structural robustness**.

## 🏭 Manufacturing

The PCB for this project can be fabricated using standard FR4 process.  
Gerber files are provided in the repository for direct upload to PCB manufacturers.

For interactive inspection of the Gerber layers, you can use **PCBWay Online Gerber Viewer**:  

[![Open in PCBWay Gerber Viewer](https://img.shields.io/badge/Open%20Gerber%20Viewer-PCBWay-brightgreen?style=for-the-badge&logo=pcb)](https://www.pcbway.com/project/OnlineGerberViewer.html)

Simply click the button above and upload the provided Gerber `.zip` file to view all PCB layers online.

![Gerber View_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/GerberView_1.png)
##
![Gerber View_1](https://raw.githubusercontent.com/mustafaeminadak/MP2494-DC-DC-Converter/main/MP2494-DC-DC-Converter/Hardware/Project_MP2494/Images/GerberView_2.png)

## 📜 License 
This project is released under the MIT License.
