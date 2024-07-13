# Nasscom-VSD-vlsi
## DAY-1
### SK1- Lecture1

#### 1. Locating the Microcontroller
This image showcases an Arduino board with the microcontroller circled. This chip is the central processing unit responsible for executing your code and controlling the board's functionalities.

![1](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/intro/Screenshot%202024-07-13%20095151.png)

#### 2. Microcontroller Internal Structure
This diagram illustrates the internal architecture of a typical microcontroller. Key components include:
Processor/SoC (System on a Chip): The "brain" of the microcontroller responsible for executing instructions.
SDRAM (Synchronous Dynamic Random Access Memory): Volatile memory used for temporary data storage while the microcontroller is running.
Direct I2C, SPI, GPIO, PWM: These are communication protocols and input/output pins that allow the microcontroller to interact with external sensors, actuators, and other devices.
![2](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/intro/Screenshot%202024-07-13%20095251.png)

#### 3. Zooming into the Microcontroller Die
This image provides a magnified view of the silicon die inside the microcontroller. Notable features:
RISC-V SoC: Indicates that the microcontroller utilizes the RISC-V instruction set architecture, known for its efficiency and open-source nature.
GPIO bank: A group of General Purpose Input/Output pins that can be configured as either inputs or outputs for interfacing with external components.
SRAM: Static RAM, a type of memory that retains its contents even when power is off, often used for storing critical program data.
Foundry IP's: Intellectual Property blocks licensed from semiconductor foundries, representing pre-designed and verified circuit modules integrated into the microcontroller.
Macros: Refers to larger functional blocks within the microcontroller's design, encompassing multiple logic gates and components.

![3](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/intro/Screenshot%202024-07-13%20095935.png)

### SK1- Lecture2
#### Visualizing a RISC-V CPU Core: From Code to Silicon Layout
1. RISC-V Assembly Code (Left):
We start with a snippet of assembly code written for the RISC-V architecture.
Each line represents a low-level instruction, demonstrating the fundamental operations the CPU is designed to execute.
2. Implementation in Hardware Description Language (Bottom):
This section displays the implementation of the picorv32 CPU core using a Hardware Description Language (likely Verilog or SystemVerilog).
It demonstrates how the assembly instructions are translated into logical operations and register transfers within the CPU's architecture.
Parameters for configuring the core's features (like enabling counters or cache) are also visible.
3. Physical Layout (Right):
This represents the actual physical layout of the picorv32 CPU core, visualized using a tool like "qflow."
Different colors and labels represent various circuit elements like logic gates (AND2X2, BUFX2), flip-flops (DFFPOSx1), and interconnections.
This layout dictates how the transistors and wires are arranged on the silicon die to implement the CPU's functionality.
Key Takeaways:
The image illustrates the intricate link between software and hardware in CPU design.
Starting from high-level code, we traverse down to the physical realization of a RISC-V core, showcasing the different levels of abstraction involved.
This visual representation helps in understanding how CPU design choices in the hardware description language translate into the physical layout of the silicon chip.

![4](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/riscv/Screenshot%202024-07-13%20100329.png)

### SK1- Lecture3
#### Bridging the Gap: From Software to Silicon
1. Application Software (Top Left):
Our journey begins with the software applications we use daily.
These applications, written in languages like C++, Java, or Python, interact with the underlying system through a defined set of instructions.
2. System Software and Compilation (Top):
The Operating System (OS) acts as an intermediary, managing system resources and providing an interface for applications to interact with the hardware.
Compilers translate high-level code (e.g., C++) into lower-level assembly language instructions specific to the target CPU architecture.
3. Assembly and Machine Code (Middle):
The Assembler further converts assembly code into binary machine code (0s and 1s) that the hardware can directly understand and execute.
The Instruction Set Architecture (ISA) serves as the abstract interface between software and hardware, defining the set of instructions a processor can execute.
4. Hardware Implementation (Bottom):
  Register Transfer Level (RTL):
    This stage describes the hardware behavior using a Hardware Description Language (HDL) like Verilog or VHDL. RTL defines the flow of data between registers and the logical operations         performed.
   
  Netlist Synthesis:
    The RTL description is synthesized into a netlist, a detailed representation of the circuit's interconnected components (gates, flip-flops).
    
  Physical Design:
    Finally, the netlist guides the physical placement and routing of transistors and wires on the silicon die, resulting in the tangible hardware that executes the original software             instructions.
    
Key Takeaways:
This diagram highlights the layered abstraction involved in bridging the gap between software and hardware.
It emphasizes the crucial role of compilers, assemblers, and hardware design tools in translating abstract instructions into physical circuits.
Understanding this flow provides valuable insights into the relationship between software, hardware, and the underlying computer architecture.

![5](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/software%20to%20hardware/Screenshot%202024-07-13%20104219.png)
![6](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/software%20to%20hardware/Screenshot%202024-07-13%20104157.png)
![7](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk1/software%20to%20hardware/Screenshot%202024-07-13%20100706.png)

### SK2- Lecture1
#### Creating ASICs with Open Source Tools and PDKs
This diagram outlines the key elements involved in developing Application-Specific Integrated Circuits (ASICs) using open-source tools and readily available Process Design Kits (PDKs).

ASIC (Center):Represents the custom-designed integrated circuit tailored for a specific application, offering performance and efficiency advantages over general-purpose chips.

Key Inputs for ASIC Design:
RTL Designs (Left): These are the hardware designs described in a Hardware Description Language (HDL) like Verilog or VHDL, forming the functional blueprint of the ASIC. Open-source RTL designs can be obtained from various repositories like LibreCores, OpenCores, GitHub, and more.

PDK Data (Right): Process Design Kits are provided by semiconductor foundries (e.g., Google + Skywater in this case). They contain essential information about the manufacturing process, including design rules, device models, and libraries required to ensure the ASIC can be physically manufactured.

EDA Tools (Top): Electronic Design Automation tools are software suites used for designing, simulating, and verifying ASICs. QFlow, OpenROAD, and OpenLANE are examples of open-source EDA tools that enable the entire ASIC design flow.

Workflow:

1. RTL Design: Design the ASIC's functionality using HDL and leverage open-source IP cores when needed.

2. EDA Tools: Employ open-source EDA tools for synthesis, placement, routing, and physical verification of the design.

3. PDK Integration: Utilize the foundry-provided PDK data to ensure compliance with manufacturing requirements.

Benefits:
1. Accessibility: Open-source tools and PDKs make ASIC design more accessible to individuals and smaller companies.

2. Cost Reduction: Leveraging open-source resources can significantly reduce the cost barrier associated with traditional ASIC development.

3. Flexibility: Open-source tools often allow for greater customization and control over the design process.

This diagram emphasizes the growing trend of open-source hardware development, enabling a wider range of innovators to design and produce custom ASICs.

![8](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l1/Screenshot%202024-07-13%20120549.png)

### SK2- Lecture2
#### Demystifying the ASIC Design Flow with OpenLANE
This series of screenshot provides a visual breakdown of the typical stages involved in designing an Application-Specific Integrated Circuit (ASIC) using the open-source toolchain OpenLANE.
1. Overall Flow (Top of Each screenshot):The common thread across the slides is the high-level ASIC design flow, progressing from RTL design to the final GDSII output:
2. RTL: Starting point is the Register Transfer Level (RTL) description of your circuit using a Hardware Description Language (HDL) like Verilog.
3. PDK: Process Design Kits (PDKs) from semiconductor foundries provide the essential design rules and libraries for the target manufacturing process.
4. Synthesis: Convert RTL into a gate-level netlist using standard cells from the PDK.
5. Floorplanning and Power Planning: Plan the chip layout, partition areas for different blocks, and plan power distribution.
6. Placement: Place the synthesized standard cells onto the chip floorplan.
7. Clock Tree Synthesis (CTS): Create a clock distribution network for reliable timing.
8. Routing: Connect all the placed cells using metal layers on the chip.
9. Sign Off: Perform final verifications to ensure the design meets all specifications.

Key Takeaway:
These screenshot demonstrate the essential steps and considerations in taking an ASIC design from RTL to GDSII using OpenLANE, showcasing the iterative and detail-oriented nature of chip design.
![14](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Screenshot%202024-07-13%20124109.png)
![9](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Capture.PNG)
![10](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Capture1.PNG)
![11](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Capture2.PNG)
![12](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Capture3.PNG)
![13](https://github.com/fortunespell/Nasscom-VSD-vlsi/blob/main/vsd/d1/d1_sk2/sky_l2/Capture4.PNG)

