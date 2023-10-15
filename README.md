# pes_pd

# Day 1 - Inception of Open-Source EDA, OpenLANE & Sky130 PDK


<details>
  <summary> Introduction  </summary>
  
  ![Screenshot from 2023-09-20 17-12-48](https://github.com/lalithlochanr/pes_pd/assets/108328466/ff7fd005-fda7-4b36-94d8-d632cbdaddb6)

  - A semiconductor chip or integrated circuit(IC) is a complex electronic component that contains various elements to perform specific functions within electronic devices. Essential components to make up an IC are macros,Foundry IP's, IO pins and so on.

1. Macros (Macro Cells):
   - Predefined functional blocks for chip design.
   - Types include standard cells, memory macros, IO macros, etc.
   - Efficient building blocks for logic, memory, input/output functions.
   - Saves time and effort for chip designers.

2. Foundry IP (Intellectual Property):
   - Sets of intellectual property provided by foundries.
   - Includes standard cell libraries, memory compilers, interface IPs, and analog IPs.
   - Optimized for specific manufacturing processes.
   - Ensures reliable and efficient chip fabrication.
   - Helps avoid designing critical components from scratch.

3. IO Pins (Input/Output Pins):
   - Pins for interfacing the chip with the external world using IO pads.
   - Include input buffers, output drivers, voltage level shifters.
   - Essential for connecting the chip to external devices or other chips.

![Screenshot from 2023-09-20 17-24-36](https://github.com/lalithlochanr/pes_pd/assets/108328466/eb5ca2f9-cc53-415c-85e6-e14404f21b85)
![Screenshot from 2023-09-20 17-24-56](https://github.com/lalithlochanr/pes_pd/assets/108328466/c27f217f-b909-4733-b4f2-82cd00565cfe)
![Screenshot from 2023-09-20 17-25-29](https://github.com/lalithlochanr/pes_pd/assets/108328466/764720e3-4a90-4913-a1ef-f9bf81c069aa)  

![Screenshot from 2023-09-20 17-29-36](https://github.com/lalithlochanr/pes_pd/assets/108328466/559d6449-3d24-404e-b2ff-b1573130359b)



</details>

<details>
  <summary>How to talk to computers </summary>

1. QFN-48 Package:
   - QFN stands for "Quad Flat No-Lead."
   - It is a surface-mount integrated circuit (IC) package.
   - The "48" denotes the number of pins or leads on the package.

2. Chip:
   - A chip, also known as an integrated circuit (IC), is a small electronic device containing a complex network of transistors and other components.
   - It serves various functions in electronic devices, such as processing, memory, or signal amplification.

3. Pads:
   - Pads are metal areas on the surface of an IC package used for soldering connections to a circuit board.
   - In a QFN-48 package, there are 48 pads for connecting to the circuit.

4. Core:
   - The core of a microprocessor or microcontroller chip is the central processing unit (CPU) responsible for executing instructions and calculations.
   - It is the "brain" of the chip.

5. Die:
   - The die is the silicon wafer that contains the actual electronic components of an integrated circuit.
   - It is usually very small and houses transistors, resistors, and other elements that make up the chip's functionality.

6. IPs (Intellectual Property):
   - IPs in the context of electronics refer to pre-designed and pre-verified functional blocks or modules that can be integrated into a chip.
   - These can include processor cores, memory blocks, or specialized functions like communication interfaces.
   - Using IPs can speed up chip development and reduce design complexity.

* Flow:
    
  ![Screenshot 2023-09-18 103611](https://github.com/lalithlochanr/pes_pd/assets/108328466/a0323dbe-8072-4dcf-9f5d-f7dda3059180)  

  ![Screenshot 2023-09-18 103930](https://github.com/lalithlochanr/pes_pd/assets/108328466/0989080d-23bd-413c-9ab4-ea5ed9cea589)  

  ![Screenshot 2023-09-18 104105](https://github.com/lalithlochanr/pes_pd/assets/108328466/7a500dd6-61c5-4314-9bda-4d4ff797c7ad)  

</details>


<details>
  <summary> SoC Design & Openlane </summary>
  
 -  RTL IP's & EDA tools & PDK data = ASIC  
  
  ![Screenshot 2023-09-18 105124](https://github.com/lalithlochanr/pes_pd/assets/108328466/65d4669d-1ab6-48f0-992e-30182e429a40)  

 - Synthesis :  Synthesis in the context of ASIC (Application-Specific Integrated Circuit) design is a crucial step in the overall ASIC design flow. It involves converting a high-level hardware description language (HDL) representation of a digital design into a gate-level netlist, which consists of logical gates (AND, OR, XOR, etc.) and flip-flops (registers).

- Floor planning : Floor planning is the process of determining how the various functional blocks, or modules, of an ASIC will be physically placed on the silicon die. It defines the overall chip's dimensions, the location of key components, and the routing channels for interconnects.

- Power planning : Power planning, also known as power grid design, is the process of distributing power and ground throughout the ASIC to ensure stable and efficient power delivery. It involves creating a network of power rails and ground connections.

- Clock Tree Synthesis (CTS) :CTS aims to efficiently distribute clock signals to all flip-flops and sequential elements in the design. This ensures that all clocked elements receive a synchronized clock signal, minimizing clock skew (the variation in arrival times of clock signals) and ensuring consistent operation.

- Signal Routing : It involves the process of connecting various electronic components and interconnecting the signal paths to ensure proper functionality.

- Sign Off :
  - Physical Verifications
    - Design Rules Checking (DRC)
    - Layout vs. Schematic (LVS)
  - Timing Verification
    - Static Timing Analysis (STA)


* OpenLane:
   - OpenLane is an open-source software toolchain for designing and customizing digital integrated circuits (ICs) or chips.
   - It automates various steps in the chip design process, making it more accessible and cost-effective for semiconductor engineers and researchers.

* Strive Chipsets:
   - Strive chipsets are a family of semiconductor solutions developed by a specific company or organization.
   - These chipsets are designed with specific goals or applications in mind, such as high-performance computing, AI, or networking, and may include various integrated components optimized for those purposes.

![Screenshot 2023-09-18 110035](https://github.com/lalithlochanr/pes_pd/assets/108328466/3d4267e8-58fd-4d6b-bcc2-b18b239ed438)

- OpenLane ASIC flow : Produce a clean GDS2 with no human intervention
- - Clean means:
  - No LVS Violations
  - No DRC Violations


* OpenLane ASIC flow
 
![Screenshot 2023-09-18 110225](https://github.com/lalithlochanr/pes_pd/assets/108328466/7040ba1f-1d37-4ab7-ba31-43393f0f16cd)

* Design For Test (DFT)

- Scan Insertion
- Automatic Test Pattern Generation (ATPG)
- Test Patterns Compaction
- Fault Coverage
- Fault Simulation

* Physical implementation 
- Also called automated PnR (Place and Route)
  - Floor/Power Planning
  - End Decoupling Capacitors and Tap cells insertion
  - Placement: Global and Detailed
  - Post placement optimization
  - Clock Tree Synthesis (CTS)
  - Routing: Global and Detailed

* Logic Equivalence Check

- Every time the netlist is modified, verification must be performed
  - CTS modifies the netlist
  - Post Placement optimizations modifies the netlist
- LEC is used to formally confirm that the function did not change after modifying the netlist

 * Dealing with Antenna rules Violations
- When a metal wire segment is fabricated, it can act as an antenna.
  - Reactive ion etching causes charge to accumulate on the wire.
  - Transistor gates can be damaged during fabrication.
** Two solutions : **
- Bridging attaches a higher layer intermediary
  - Requires Router awareness (not there yet!)
- Add antenna diode cell to leak away charges
  - Antenna diodes are provided by the SCL


</details>


<details>
  <summary>Get familiar to open-source EDA tools</summary>

  ![Screenshot from 2023-09-18 11-19-47](https://github.com/lalithlochanr/pes_pd/assets/108328466/5ad003c1-9db5-4287-bcae-92915fc505b4)  

  ![Screenshot from 2023-09-18 11-22-42](https://github.com/lalithlochanr/pes_pd/assets/108328466/932e77c7-949d-48a8-b9c9-dc17ed3b0d65)

  ![Screenshot from 2023-09-18 11-25-26](https://github.com/lalithlochanr/pes_pd/assets/108328466/d82db253-c151-4370-a34d-8872ffa3a41e)


- skywate-pdk : all pdk related files  
- open_pdks : set of scrips and files that converts foundry level pdks to be compatible with open source pda tools  
- sky130A : variant of pdk.
- libs.tech : specific to technology
- libs.ref : specific to tools


  * Design Preparation Steps

    - After running these codes below the design setup is done.

  ````
  docker
  ./flow.tcl -interactive
  package require openlane 0.9
  prep -design picorv32a
  run_synthesis
  run_floorplan
  ````

![Screenshot from 2023-09-18 11-47-03](https://github.com/lalithlochanr/pes_pd/assets/108328466/27d218e7-54ed-4431-99aa-6b658c2ab2cc)

![Screenshot from 2023-09-18 11-50-29](https://github.com/lalithlochanr/pes_pd/assets/108328466/1703a705-0d76-4d29-bd4c-ffbea604ff0a)

![Screenshot from 2023-09-18 11-52-53](https://github.com/lalithlochanr/pes_pd/assets/108328466/ae8960e4-532a-42da-8557-7599cf73f2ad)

```` less config.tcl ````
![Screenshot from 2023-09-18 11-55-52](https://github.com/lalithlochanr/pes_pd/assets/108328466/5cbd93d5-3d13-4bf8-9015-2b131ffb16e0)  

````less sky130A_sky130_fd_sc_hd_config.tcl````

![Screenshot from 2023-09-18 11-57-57](https://github.com/lalithlochanr/pes_pd/assets/108328466/5d9fdaea-9840-4435-8197-e2310ce22061)


* Review the files after design preparation and run synthesis
  
![Screenshot from 2023-09-18 12-02-10](https://github.com/lalithlochanr/pes_pd/assets/108328466/f69946b9-8c71-48da-9f1f-1a6f6c6021b5)

```` less merged.lef ````
![Screenshot from 2023-09-18 12-04-18](https://github.com/lalithlochanr/pes_pd/assets/108328466/fe3a8d3a-3942-4dda-9c0f-7c1e721af438)

![Screenshot from 2023-09-18 12-05-19](https://github.com/lalithlochanr/pes_pd/assets/108328466/21b08995-3e9c-44df-97dd-37888cc0a5b3)

````
cd ..
less config.tcl
````
![Screenshot from 2023-09-18 12-07-33](https://github.com/lalithlochanr/pes_pd/assets/108328466/f62d84fb-9be7-4368-b14f-f47f2683f4d0)  


* Synthesis Results

![Screenshot from 2023-09-18 12-19-47](https://github.com/lalithlochanr/pes_pd/assets/108328466/b00e9323-db40-4cc2-aa16-e6661f3b5d7c)

-Number of cells(n):14876
-Number of dff(d):1613
-flop ratio: d/n=0.108

![Screenshot from 2023-09-18 12-26-45](https://github.com/lalithlochanr/pes_pd/assets/108328466/d912c2c5-d393-4470-9c36-ff525287ea85)
  
</details>


# Day 2 - Good floorplan vs bad floorplan and introduction to library cells

<details>
<summary>Chip floor planning considertions </summary>
   
  * Utilization Factor & Aspect Ratio
   
  - How do we find W & H?

    <img width="416" alt="268482689-88e3af4a-aa59-4e7d-811f-6188bae9a3a6" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/1f34ca15-3d37-473d-9f11-40264edd30d9">

  - Example

    <img width="448" alt="268482742-092f2da8-868b-4b05-802c-c729f6504d63" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/5e1fbfd9-e633-4832-88b9-7f48dc51d7a1">

  -convert into physical dimension
  
  <img width="417" alt="268482767-d1954fa7-ca86-4012-b785-d9daf431da7c" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/5bb47711-63ba-4b0f-ba87-8a47c3b7a3b1">

  - give unit area for each logic gate

    <img width="579" alt="268482840-bf87bf69-f41c-4d86-8022-9e2555b72e96" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/bff3b5bc-a348-477a-a37e-60ff29cb7029">

    - we implment this die multiple times on the silicon wafer to increase the throughput
    - implment the logic into the core,the logic cells occupied 100% of the core,thereby occupying Utilising 100% of the core

      <img width="582" alt="268482900-658e9ab3-8fe3-450d-8558-70882c27fe71" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/99ee594f-ba58-48d3-b286-1827032f2ebc">  


    * Utilization factor = Area occupied by netlist / Total area of core
      - we have taken utilization factor to be 1.

      ![Screenshot 2023-09-18 190913](https://github.com/lalithlochanr/pes_pd/assets/108328466/99f3e6bc-8065-4845-8efe-b154102b7cc3)

    * Aspect ratio = Height / Width
      -Aspect ratio refers to the ratio of the width to the height of a transistor. It is a critical parameter in the design and fabrication of integrated circuits.
      - we have taken aspect ratio to be 1.


![Screenshot 2023-09-18 191535](https://github.com/lalithlochanr/pes_pd/assets/108328466/0abc7b79-b265-43c3-ab21-0acac23d5b86)  

  * Concept of Pre-Placed cells  
    - Two different blocks and implementation of it seperately  

      <img width="547" alt="268483320-afe3334d-9e9d-4da0-9d79-a1d25c2c9a71" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/4d64ac82-096b-4eef-a957-74268833ba4d">  


      ![Screenshot 2023-09-18 191856](https://github.com/lalithlochanr/pes_pd/assets/108328466/9ab8571e-25ce-4143-83c1-045c2c5115e4)  

* Locations of Pre-Placed cells  
  - Automatic placing does not try to move these once placed  
    
    ![Screenshot 2023-09-18 192341](https://github.com/lalithlochanr/pes_pd/assets/108328466/9733f739-d2a2-4180-b74b-241fc367a40a)  

* Implementation of pre-placed cells is one time and can be reused multiple times.  
  
![Screenshot 2023-09-18 192738](https://github.com/lalithlochanr/pes_pd/assets/108328466/d4bb68d6-a741-4fec-a6c8-3dbc840fc2b5)  

* Decoupling capacitors
  - Decoupling capacitors are a fundamental tool in ensuring the reliable and noise-free operation of digital circuits and ICs. Properly selected and placed decoupling capacitors can help prevent signal integrity issues, reduce electromagnetic interference (EMI), and improve the overall performance and reliability of electronic systems.
 
<img width="577" alt="268483690-b2a968d9-b686-4b3a-8cc1-46e24a69d4fe" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/36b3a3f2-9834-4923-ac4b-dedebe8c2fc2">  

- If Vdd' goes below the noise margin, due to Rdd and Ldd, the logic '1' at the output of circuit wont be detected as logic '1' at the input of the circuit following this circuit.

-  Noise margin summary
<img width="462" alt="268483885-87f2781e-2052-4a53-b557-ede8d9032e33" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/f211bb1c-19de-4223-ad1e-7e060dc82311">

* Having a large distance from the power supply and the main circuit has a disadvantage as there are multiple voltage drops happening before it reaches the main circuit giving a less voltage at the main circuit due to voltage drops therefore we cannot gaurantee that our logic gates in the circuit are getting either a high voltage(logic 1) or a low voltage(logic 0) or a danger region or gray region(Either Logic can go to 1 or 0 giving high or low volts) hence we have a disadvantage of Voltage being far from our circuit design

* To solve this we use Decoupling Capacitors

- they are huge capacitors completely filled with charge,therefore if our main voltage is source is 1v our deocupling capacitors also get charged to 1V and when discharged it again replenishes using main power supply.

- <img width="579" alt="268483999-1c574b07-a6b5-452a-bce9-6921a89db806" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/869cd4b1-bc28-48f1-a78b-fd942254f01c">

- surround the preplaced cells with the decoupling capacitors in order to keep the current flow as required to not be altered with respect to voltage drops. Ensuring each preplaced cells are getting the supply from the Decoupling capacitors

<img width="415" alt="268484055-c2bee96c-6677-4295-913a-1d2ba3b720fa" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/0d1d2a3e-4253-48a9-94b0-658933a9e070">

* Power Planning
  - Power planning involves the management of power distribution, delivery, and consumption in an IC to ensure its proper functioning and efficiency.
 
    <img width="322" alt="268484173-8e51df59-d182-46ef-96b3-a230f46be2ab" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/5b494508-a173-46e7-b92a-8b804c530cd3">

- In the context of the provided circuit, which employs decoupling capacitors, we intend to transform it into a reusable Macro module. This Macro module is replicated numerous times across the chip, resulting in a distinct current requirement for each instance of the Macro. Within each Macro, there are two distinct functions: one acts as a driver, and the other as a loader. Both the driver and loader in each Macro are equipped with their respective decoupling capacitors. Our objective is to ensure that the signal transmitted from the driver to the loader within each Macro maintains its integrity along the specific interconnecting line.  

<img width="432" alt="268484345-5749c54e-6071-46a7-b5f0-881e67c62d1b" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/111897fb-9d92-4cea-b1f8-0d4ad2771b5b">

- The connection between the driver and the load must receive its power directly from the power supply, as it is not feasible to insert decoupling capacitors in this intermediate section. This arrangement introduces the potential for voltage drop because the power supply is situated some distance away from the signal line  

- To illustrate, let's examine a 16-bit bus connected to an inverter. When we feed logic signals into the inverter, the output will be the inverted value of the input. Consequently, any capacitors initially charged to logic 1 will discharge to logic 0, and conversely, capacitors initially charged to logic 0 will switch to logic 1.  

<img width="453" alt="268484398-7ab5589a-5f16-4b9d-9d2c-bf5a26820f51" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/130b64ad-4c43-445e-9902-28ecbbf73662">

<img width="437" alt="268484424-a137db98-0906-43ff-9eb4-86599a10993a" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/eeb7871c-a2c9-496c-a266-1adf1aa34b21">

<img width="440" alt="268484479-e6da813d-05d5-49f1-959d-72274e1e4410" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/452011dc-478f-4fc1-a76e-e501a5d5edff">

- Multiple supply lines are created to fulfill any power requirement.

* Pin placement & Logical Cell placement blockage

- Pin placement, often referred to as I/O (Input/Output) pad placement, involves the task of defining the positions and organization of input and output pins on an integrated circuit (IC) or printed circuit board (PCB). These pins serve the purpose of establishing connections with external devices or other components.
  <img width="443" alt="268485435-bb5f3c42-4a93-4410-9d14-c88622057eeb" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/b4e6e2d3-4eab-4c64-a8d2-1d1f89f60b69">

- Other designs using different implementation of clocks with preplaced cells
  
  <img width="465" alt="268485547-932631eb-512c-416a-828a-6246dcfffd82" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/f00a4f8c-2a5a-4e64-a049-b3820bb1739e">
  <img width="471" alt="268485634-08172ee4-f587-43b3-aa68-f303b8875487" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/8fcf86b7-82d5-4db6-bd6a-e226b92b17ad">  

  - Pin placement
   
![Screenshot 2023-09-18 195627](https://github.com/lalithlochanr/pes_pd/assets/108328466/8c2d2c7c-4946-4be5-bcab-05138eab6ab7)

- Following pin placement, it's essential to ensure that no automated placement or routing tool assigns cells to a specific region. This particular area is reserved for maintaining gaps between each clock port, and it should be prohibited from accommodating any cells. This restriction is implemented through a process known as logical cell placement blockage.
- Logical cell placement blockage is crucial for optimizing signal routing and minimizing delays. By creating these exclusion zones, it helps maintain signal integrity and reduces the risk of timing violations in high-performance integrated circuits.

<img width="508" alt="268485849-e5af433c-d0e8-4bb0-ac80-1001a2fc3b04" src="https://github.com/lalithlochanr/pes_pd/assets/108328466/917ad253-9d04-4e56-90be-ff6b210e9ed6">

* Steps to run floor plan using Openlane
````less README.md````
![Screenshot from 2023-09-18 20-06-43](https://github.com/lalithlochanr/pes_pd/assets/108328466/5fecbdf0-dd2f-49e7-bc07-7c3e92f2e100)

![Screenshot from 2023-09-18 20-06-32](https://github.com/lalithlochanr/pes_pd/assets/108328466/14d2c64c-f53a-4d97-9e06-4028cfe36e5c)

````less floorplan.tcl````
![Screenshot from 2023-09-18 20-08-32](https://github.com/lalithlochanr/pes_pd/assets/108328466/5c572cec-4a42-44f6-871b-e8069e090a2c)

````run_floorplan````
![Screenshot from 2023-09-18 20-27-25](https://github.com/lalithlochanr/pes_pd/assets/108328466/fa4e24d9-7bb7-4439-9fbd-bec60b5f53c2)   

![Screenshot from 2023-09-18 20-54-41](https://github.com/lalithlochanr/pes_pd/assets/108328466/4faaa77a-c430-4681-84fd-3a9006feb0a7)

-Use nano file open to make required changes into code
![Screenshot from 2023-09-18 20-54-07](https://github.com/lalithlochanr/pes_pd/assets/108328466/0fd729bb-0270-4332-94d8-4747d5374071)

````run_floorplan```` in openlane

* Review floorplan layout in Magic
````
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
````
![Screenshot from 2023-09-18 21-26-21](https://github.com/lalithlochanr/pes_pd/assets/108328466/3d29fbc5-288a-4662-aa89-644dbab727fd)

![Screenshot from 2023-09-18 21-30-42](https://github.com/lalithlochanr/pes_pd/assets/108328466/f3aa8216-6eb8-48de-a20e-5660308ebfeb)
    
</details>

<details>
  <summary>Library Binding and Placement</summary>
  * Netlist binding and intial place Design
  - Bind netlist with physical cells
  
  ![Screenshot 2023-09-19 012133](https://github.com/lalithlochanr/pes_pd/assets/108328466/7d936ced-39b4-484f-8e8b-451f7ebd47bd)  

  The library will have the information of shape, width, height and delay information of every cell required.

 - Placement
   - Stage where we estimate wire length and capaitance and based on that insert repeaters.
  ![Screenshot 2023-09-19 012432](https://github.com/lalithlochanr/pes_pd/assets/108328466/8fef7b04-8e65-4779-bd1d-a255c4743bbe)

* Optimize Placement using estimated wire length and capacitance with final optimization  
- Repeaters essentially regenerate the original signal, ensuring that it maintains its quality and integrity as it travels.  
  - This placement of the repeater ensures that whatever information is sent to Din2 is faithfully retained by FF1 of the 2nd stage, thereby maintaining signal integrity.  
- Slew rate (SLEW) is influenced by the capacitance value in the circuit. When a higher capacitance is used, it increases the time it takes to charge or discharge the capacitor, leading to slower signal transitions and potentially compromising signal quality.  
  - Between Din2 and FF1, repeaters should be added along this transmission path to address the slew rate issue and improve signal integrity.  

- Stage 1:  
![Screenshot 2023-09-19 022519](https://github.com/lalithlochanr/pes_pd/assets/108328466/c254fe20-f115-42bb-9d2c-1affc8173f40)  

- Stage 2:  
![Screenshot 2023-09-19 022616](https://github.com/lalithlochanr/pes_pd/assets/108328466/69faed36-a052-4274-9dff-ef23fc6caf43)  

- Stage 3:  
![Screenshot 2023-09-19 022649](https://github.com/lalithlochanr/pes_pd/assets/108328466/84672684-3a68-4fd5-ae33-1920376fc7d2)  

- Stage 4:  
![Screenshot 2023-09-19 022720](https://github.com/lalithlochanr/pes_pd/assets/108328466/a0dbb926-f869-4826-aae1-8b19fdd0fb54)  

* Need for libraries & characterization

1. Logic Synthesis: This process takes the RTL (Register Transfer Level) description and transforms it into a configuration of gates that represents the original functionality of the design.

2. Floorplanning: we import the Netlist generated from logic synthesis. During this phase, we determine the physical size and layout of the chip's core and die.

3. Placement: placement involves arranging the logic cells obtained from logic synthesis onto the chip's surface. The goal is to meet initial timing requirements, typically by grouping faster cells together and considering the functional dependencies among cells.

4. Clock Tree Synthesis (CTS): we design a clock distribution tree to ensure that the clock signal reaches all the logic cells at precisely the same time. This helps in synchronizing clocked elements such as flip-flops.

5. Routing: routing involves creating interconnections between the logic cells. The routing process is influenced by the characteristics of the individual cells and must adhere to specific routing constraints.

6. Static Timing Analysis (STA): This analysis determines critical timing parameters such as setup time, hold time, and the maximum achievable frequency of the circuit. STA ensures that the design meets its timing requirements and operates correctly.

![Screenshot 2023-09-19 023349](https://github.com/lalithlochanr/pes_pd/assets/108328466/19587f8e-c7ee-447a-83a4-549564ebd84e)  
![Screenshot 2023-09-19 023432](https://github.com/lalithlochanr/pes_pd/assets/108328466/8e6468c6-94ff-4356-87a0-76790a87ec91)  


![Screenshot 2023-09-19 024830](https://github.com/lalithlochanr/pes_pd/assets/108328466/86412b04-555d-48cc-8344-80b42dc532fb)
- The library consists of all the cells or gates required to model them as per requirement with the help of EDA tools.

* Congestion aware Placement using RePIAce
````run_placement````
![Screenshot from 2023-09-19 03-03-01](https://github.com/lalithlochanr/pes_pd/assets/108328466/5654c0e0-ff58-4ebc-870b-3b00863a91a0)

![Screenshot from 2023-09-19 03-30-44](https://github.com/lalithlochanr/pes_pd/assets/108328466/6c21ff37-92b8-4dfc-bc8f-f939947cd1c3)

![Screenshot from 2023-09-19 03-30-18](https://github.com/lalithlochanr/pes_pd/assets/108328466/98fcd65e-f1da-4392-9755-cf2d4f4e6071)

</details>

<details>
  <summary>Cell design and characterixation flows</summary>
* Inputs for design flow
- The cell design process is a fundamental stage in semiconductor chip development. It involves the systematic creation and optimization of discrete digital logic cells that make up a standard cell library. These libraries house pre-designed components like logic gates and flip-flops, essential for building integrated circuits. During this process, critical elements such as Process Design Kits (PDK), Design Rule Checking (DRC), Layout Versus Schematic (LVS) rules, SPICE models, and user-defined specifications are incorporated into the library. User-defined parameters, like pin placement and gate length, are carefully integrated by library developers to tailor the library to specific project requirements, ensuring a robust foundation for chip design and manufacturing.  

* Cell Design Flow
![Screenshot 2023-09-19 034415](https://github.com/lalithlochanr/pes_pd/assets/108328466/908b0208-6946-41ca-b285-ed1d2fbb7af5)

![Screenshot 2023-09-19 034510](https://github.com/lalithlochanr/pes_pd/assets/108328466/8afae67a-e48a-4eee-bbe8-2133f9562b01)

![Screenshot 2023-09-19 034623](https://github.com/lalithlochanr/pes_pd/assets/108328466/49a330f8-4e51-4837-a60d-9052adb11460)

![Screenshot 2023-09-19 034652](https://github.com/lalithlochanr/pes_pd/assets/108328466/484c29e8-f0d2-4a66-94b6-b2db011a7034)

- Libraries built on user defined specifications with respect to library defined cells.
  (eg- contact defined on metal 3,4,5 layers, pin location, drawn gate length, etc)

* Circuit design Steps
  - By combining NMOS and PMOS transistors we can design the required circuit and can be derived in terms of Euler's Path and represented in terms of stick diagram. 
![Screenshot 2023-09-19 035305](https://github.com/lalithlochanr/pes_pd/assets/108328466/f9d35b0e-d63c-4759-8c46-001f1d81632f)

* Layout Design Steps
- transform the stick diagram into a layout that adheres to the specified Design Rule Check (DRC) constraints
- extraction of parasitic elements, which include characteristics like resistances and capacitances, from the layout
- compile it into an extracted spice list

![Screenshot 2023-09-19 040143](https://github.com/lalithlochanr/pes_pd/assets/108328466/79bcecee-4950-4476-b860-70094e99038f)

![Screenshot 2023-09-19 040159](https://github.com/lalithlochanr/pes_pd/assets/108328466/398fa882-6ccf-4b1c-8314-37adbe069381)
- Extracted spice list that needs to be characterized


* Characterization flow

![Screenshot 2023-09-19 040502](https://github.com/lalithlochanr/pes_pd/assets/108328466/fd8696d6-f552-4024-8a4a-217ff5f91329)

![Screenshot 2023-09-19 040523](https://github.com/lalithlochanr/pes_pd/assets/108328466/b8f4c544-6ad7-44f6-b2f6-8fa4f5b0ab79)

- GUNA - gives you the timing, power models.
![Screenshot 2023-09-19 040600](https://github.com/lalithlochanr/pes_pd/assets/108328466/f0780d03-cf24-4b31-8bc0-2bfcdeeca809)

</details>

<details>
  <summary> General timing characterization parameters</summary>
- Timing threshold definition
  - the defintions are associated with parts of the graphs defining the characteristics 
  
  ![Screenshot 2023-09-19 041710](https://github.com/lalithlochanr/pes_pd/assets/108328466/86377357-40f5-4bcd-9fd5-0f819980331e)
  (the first four definitions)
  - the red graph refers to rise waveform
  - the blue graph refers to fall waveform

  
  ![Screenshot 2023-09-19 041946](https://github.com/lalithlochanr/pes_pd/assets/108328466/7b3a6a1a-970e-41b7-b64f-b26f01739600)
  (definition 5 & 7)
  - input and output waveform from which delay can be calculated
  - red - in_rise & blue - out_rise

  ![Screenshot 2023-09-19 042224](https://github.com/lalithlochanr/pes_pd/assets/108328466/156ab3da-15c6-445a-a7d7-a68adb6de68f)
  (definition 7 & 8)
  - red - in_fall & blue - out_fall


- Propagation Delay
- The time difference between when the transitional input reaches 50% of its final value and when the output reaches 50% of its final value.
- Propagation delay=time(out_fall_thr)-time(in_rise_thr)
  - the propagation delay can be calulated by following the timing threshold definitions
    ![Screenshot 2023-09-19 042626](https://github.com/lalithlochanr/pes_pd/assets/108328466/4cf33d86-08f1-49ee-b2a6-38dfc31d4d95)
  - negative delay is not possible and is obtained on choosing of poor threshold vaalues so should careful while choosing them
  - Delay=-42ps
    ![Screenshot 2023-09-19 042656](https://github.com/lalithlochanr/pes_pd/assets/108328466/a9bf99be-e12d-4bc2-9c5d-9f7418f012a7)

- Transistion Time
- The time it takes the signal to move between states is the transition time, where the time is measured between 10% and 90% or 20% to 80% of the signal levels.
- Rise transition time = time(slew_high_rise_thr) - time (slew_low_rise_thr)
- Fall transition time = time(slew_high_fall_thr) - time (slew_low_fall_thr)
    - the threshold definitions are mentioned below in the image
      ![Screenshot 2023-09-19 042556](https://github.com/lalithlochanr/pes_pd/assets/108328466/e4f0b920-051d-44cb-8595-b0646c6428a3)
  
</details>


# Day 3 - Design library cell using Magic Layout and ngspice characterization

<details>
  <summary> Labs for CMOS inverter ngspice simulations</summary>

* IO Placer
- An IO placer is a software tool used in semiconductor chip design's Place and Route (PnR) phase. It optimizes the placement of input/output (IO) pads or pins on the chip's physical layout, facilitating efficient signal routing, reduced signal delay, lower power consumption, and EMC compliance. The process is iterative, allowing adjustments to variables like pin configuration within the core area, transitioning from even distribution to alternative arrangements as needed for optimal chip performance.

- In openlane, run the procedure until run_floorplan
![Screenshot from 2023-09-20 18-10-05](https://github.com/lalithlochanr/pes_pd/assets/108328466/1ce0b1e6-b893-4f55-b917-a8dda22f194e)
- You can observe the IO ports placed uniformly
![Screenshot from 2023-09-20 18-11-14](https://github.com/lalithlochanr/pes_pd/assets/108328466/17d09e0f-6da5-4a11-9500-aa85a77eacda)

- In the file floorplan.tcl
![Screenshot from 2023-09-20 18-15-20](https://github.com/lalithlochanr/pes_pd/assets/108328466/4a4f3640-792d-44ca-bbb4-dbc2fe3fc30c)

- change the mode from 1 to 2 
````
set ::env(FP_IO_MODE) 2
run_floorplan
````
![Screenshot from 2023-09-20 18-10-05](https://github.com/lalithlochanr/pes_pd/assets/108328466/804e613c-2d76-4ec9-ab4f-33df6f3922ef)

![Screenshot from 2023-09-20 18-36-31](https://github.com/lalithlochanr/pes_pd/assets/108328466/6f811dd1-1ef3-4be3-a400-cad5821d662d)
- the ports are no longer equidistant

- utilize git clone for cloning PMOS and NMOS spice models, a VSD standard cell design file will be generated within OpenLane after the git clone.

````
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
````
![Screenshot from 2023-09-20 18-41-26](https://github.com/lalithlochanr/pes_pd/assets/108328466/dac22d25-b3ee-42e6-b73a-7edf945e5043)

````
magic -T sky130A.tech sky130_inv.mag &
````

![Screenshot from 2023-09-20 18-56-13](https://github.com/lalithlochanr/pes_pd/assets/108328466/3c312ac4-1fc2-45aa-881a-b4cf47e8a042)

![Screenshot from 2023-09-20 18-56-30](https://github.com/lalithlochanr/pes_pd/assets/108328466/456f880f-fbf2-40e9-a027-2186719ed190)  



* Spice deck creation for CMOS inverter
(VTC - SPICE simulations)

- Spice deck -Contains the connectivity information, inputs that has to be given to the simulation, tap points.

    -Component Connectivity
    -Component values.
     (ideally pmos >= 2*nmos)
    -Identify nodes.
    -Name nodes

  ![Screenshot from 2023-09-20 18-45-20](https://github.com/lalithlochanr/pes_pd/assets/108328466/9789d123-9bed-40c7-bd11-31ab07f3e3bf)

![Screenshot from 2023-09-20 18-45-34](https://github.com/lalithlochanr/pes_pd/assets/108328466/d219dc3e-069f-4484-82cd-16dfa924870d)

![Screenshot from 2023-09-20 18-45-40](https://github.com/lalithlochanr/pes_pd/assets/108328466/b8edbd05-6c09-4cd9-a100-302165db34c8)


- SPICE waveform
![Screenshot from 2023-09-20 18-46-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/2191e6b4-2938-46cc-96e3-052a3c50f50e)

* Switching Threshold Vm

![Screenshot from 2023-09-20 18-49-06](https://github.com/lalithlochanr/pes_pd/assets/108328466/e58aadc1-0b32-4d16-9a03-677817d724d3)

![Screenshot from 2023-09-20 18-49-17](https://github.com/lalithlochanr/pes_pd/assets/108328466/3c318f0a-23fd-44b7-bbdc-fb6a65119573)

![Screenshot from 2023-09-20 18-49-23](https://github.com/lalithlochanr/pes_pd/assets/108328466/272f48f7-aac2-4953-b6f9-89be6d7818a5)

![Screenshot from 2023-09-20 18-49-43](https://github.com/lalithlochanr/pes_pd/assets/108328466/31864140-9cd2-4c38-9713-aff6f7ef6e24)

![Screenshot from 2023-09-20 18-49-50](https://github.com/lalithlochanr/pes_pd/assets/108328466/fea7c30d-e34c-4565-a524-514f86cce904)

</details>


<details>
  <summary> Inception of Layout</summary>

* CMOS fabrication process

![Screenshot from 2023-09-20 19-00-03](https://github.com/lalithlochanr/pes_pd/assets/108328466/c6479499-4103-43c4-81f6-0861de264a2f)  

- Lightly Doped Drain (LDD)
  - The primary purpose of LDD formation is to reduce short-channel effects and improve the performance and reliability of these transistors.

- Layout
````
magic -T sky130A.tech sky130_inv.mag &
````
![Screenshot from 2023-09-20 19-13-18](https://github.com/lalithlochanr/pes_pd/assets/108328466/81c6d944-9adf-4549-8a3c-6e8299e9af51)

![Screenshot from 2023-09-20 19-15-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/6cf97197-3ae7-4c72-abeb-d0ebab2e259d)

![Screenshot from 2023-09-20 19-16-24](https://github.com/lalithlochanr/pes_pd/assets/108328466/629ae544-f38e-4633-89de-4c43d4dd7f91)

![Screenshot from 2023-09-20 19-16-46](https://github.com/lalithlochanr/pes_pd/assets/108328466/ae35bb1f-3ae7-4eb0-80d1-0db5f27c5347)

![Screenshot from 2023-09-20 19-16-34](https://github.com/lalithlochanr/pes_pd/assets/108328466/3a67563d-de0a-4e07-a9c2-c74547852fe2)
  
</details>

<details>
  <summary> Sky130 Tech File </summary>

  * Lab steps to create std cell layout and extract spice netlist
  ````
  pwd
  extract all
  ext2spice cthresh 0 rthresh 0
  ext2spice
  ````

![Screenshot from 2023-09-20 19-36-05](https://github.com/lalithlochanr/pes_pd/assets/108328466/d8eeb50a-788d-4c72-a4f2-1a57e00b626b)

![Screenshot from 2023-09-20 19-39-13](https://github.com/lalithlochanr/pes_pd/assets/108328466/4013931e-c928-4d3f-a241-bda501a02cb9)

![Screenshot from 2023-09-20 19-38-59](https://github.com/lalithlochanr/pes_pd/assets/108328466/8e310ea7-8055-48e4-a689-5a236a74a061)

- make the required changes into the file
![Screenshot from 2023-09-20 20-11-40](https://github.com/lalithlochanr/pes_pd/assets/108328466/e2235e08-725c-4ac1-9b33-50eceb264e5c)

![Screenshot from 2023-09-20 20-11-17](https://github.com/lalithlochanr/pes_pd/assets/108328466/3c88db15-7ccb-4e75-8dae-8773ad7486a3)

![Screenshot from 2023-09-20 20-16-10](https://github.com/lalithlochanr/pes_pd/assets/108328466/cae6ce24-a83c-497a-8ed7-7be8af96ddd7)

![Screenshot from 2023-09-20 20-15-54](https://github.com/lalithlochanr/pes_pd/assets/108328466/bdbf1de8-9c53-43eb-b088-d2452254ece7)

- rise time = 80% of rise time - 20% of rise time = 0.41ns
  ![Screenshot from 2023-09-20 20-48-20](https://github.com/lalithlochanr/pes_pd/assets/108328466/44bcc22d-8949-4e53-88a7-fb9944b01953)

- fall time = 20% of fall time - 80% of fall time = 0.58ns
  ![Screenshot from 2023-09-20 20-53-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/34d22b96-a9a0-4ca8-8a69-8890afe14f12)

similarly,
- Cell rise delay = 50% of output - 50% of input = 0.38ns
- Cell fall delay = 50% of output - 50% of input = 0.45ns

- Get the required files
  ````
  wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
  magic -d XR
  tar xfz drc_tests.tgz
  cd drc_tests
  ````
  -In toplevel open files and open met3.mag
  -In tkcon,
  ````
  drc why
  ````
  ![Screenshot from 2023-09-20 21-34-22](https://github.com/lalithlochanr/pes_pd/assets/108328466/b904e05b-e680-4155-b351-303227f3469a)

  - To see contacts
    ````
    cif see VIA2
    ````
    ![Screenshot from 2023-09-20 21-50-45](https://github.com/lalithlochanr/pes_pd/assets/108328466/e5b07250-7170-4711-b33d-8cee07cb0d9e)

  - to checck for dimensions of area- select area & type box in tkcon and ```` drc check````
  - There are DRC errors so to fix them
  - open sky130A.tech file using an editor and search for poly.9 and make the changes
    ![Screenshot from 2023-09-20 22-12-08](https://github.com/lalithlochanr/pes_pd/assets/108328466/b860880a-27f2-44bd-90a9-65fb2628dbf8)
    ![Screenshot from 2023-09-20 22-16-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/74079b08-2d67-4fab-9b0b-0a310f5559af)
    ![Screenshot from 2023-09-20 22-25-05](https://github.com/lalithlochanr/pes_pd/assets/108328466/2e3fcef6-da2c-49ae-8f17-96291d304f34)
    ![Screenshot from 2023-09-20 23-10-44](https://github.com/lalithlochanr/pes_pd/assets/108328466/6f61b884-c303-4f99-8c4c-ea56eff0cd23)
    ![Screenshot from 2023-09-20 23-17-50](https://github.com/lalithlochanr/pes_pd/assets/108328466/8a9ffb1c-458e-4ac5-8e94-fab317e24c3a)
    ![Screenshot from 2023-09-20 22-59-50](https://github.com/lalithlochanr/pes_pd/assets/108328466/e43edbe5-83d1-4940-92e7-73ecfbc9c619)
    
</details>

# Day 4 - Pre-layout timing analysis and importance of good clock tree
  
<details>
    <summary> Timing modelling using delay tables</summary>
    * Convert grid info into track info
    - Magic Layout into a std cell LEF
  
    ````   
      less tracks.info   
    ````
    
  ![Screenshot from 2023-09-21 00-57-57](https://github.com/lalithlochanr/pes_pd/assets/108328466/1d4ff8b6-4b9b-426f-9e6e-92fb7d998aff)

   ![Screenshot from 2023-09-21 00-57-39](https://github.com/lalithlochanr/pes_pd/assets/108328466/ae025ebb-21c2-43d0-b879-d839e93caf39)
    
 - 1st value indicates the offset and 2nd value indicates the pitch along provided direction
 - press g in layout to get grid
  ![Screenshot from 2023-09-21 01-10-01](https://github.com/lalithlochanr/pes_pd/assets/108328466/d170ec0b-f47e-4312-842c-f506bc94a863)


  ```` grid 0.46um 0.34um 0.23um 0.17um````
  - the width of the standard cell must be in odd multiples of x pitch
![Screenshot from 2023-09-21 01-13-48](https://github.com/lalithlochanr/pes_pd/assets/108328466/ba28cccb-ffbd-4706-b255-d8a52d5420cf)

  - To generate the cell LEF file from Magic Layout
    - we save the modified layout
    - we open the file and extract LEF, type the command in the tkcon window
      
  ````
save sky130_vsdinv.mag
magic -T sky130A.tech sky130_vsdinv.mag
lef write
````
  ![Screenshot from 2023-09-21 01-32-38](https://github.com/lalithlochanr/pes_pd/assets/108328466/a9e9c489-4d15-4a89-b7fb-b3b55f7c2965)

- Generate LEF file
```` lef write```
- terminal - ````less sky130_vsdinv.lef````
![Screenshot from 2023-09-21 01-57-30](https://github.com/lalithlochanr/pes_pd/assets/108328466/e0cbf973-8eff-42d7-9459-448c25aa3fa3)

````
cp sky130_vsdinv.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src

cp sky130_fd_sc_hd__* //home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
````
![Screenshot from 2023-09-21 02-49-43](https://github.com/lalithlochanr/pes_pd/assets/108328466/993a5f1e-06e7-4783-ba81-f18471f0d0a7)

![Screenshot from 2023-09-21 02-49-59](https://github.com/lalithlochanr/pes_pd/assets/108328466/47834e30-76f8-4b00-b059-32ba8596fa0f)


````gedit config.tcl````
![Screenshot from 2023-09-21 03-01-20](https://github.com/lalithlochanr/pes_pd/assets/108328466/221b6cad-01fc-4fd8-adc9-76ff114b33f3)
![Screenshot from 2023-09-21 04-00-57](https://github.com/lalithlochanr/pes_pd/assets/108328466/3e63e5d9-b73d-410b-a807-b28844101ea7)


- Now in openlane
   ````
  docker
  ./flow.tcl -interactive
  package require openlane 0.9
  prep -design picorv32a -tag 18-09_12-32 -overwrite
  set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
  add_lefs -src $lefs
  run_synthesis
  ````

![Screenshot from 2023-09-21 03-55-15](https://github.com/lalithlochanr/pes_pd/assets/108328466/19798cf9-11bf-45c5-a046-72aa1cc89af6)
![Screenshot from 2023-09-21 03-55-39](https://github.com/lalithlochanr/pes_pd/assets/108328466/abb488b6-12df-4fb2-9e06-bc523f88b4a0)
![Screenshot from 2023-09-21 04-05-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/b0471618-6112-44df-864c-3cd5e7564aa6)

* Introduction to Delay Tables
- Delay tables are indispensable components. Their primary function is to provide a structured framework for modeling and comprehending the intricacies of signal propagation delays inherent to logic gates and interconnections within a digital integrated circuit (IC). These tables assume a pivotal role in ensuring that the circuit operates within its prescribed timing specifications, such as meeting setup and hold time requirements. As a cornerstone of synchronous digital system design, delay tables are fundamental in achieving reliable and predictable circuit behavior. 
- Primary purpose of the delay table for performing of timing analysis,synchronization,etc.

![Screenshot from 2023-09-21 04-06-35](https://github.com/lalithlochanr/pes_pd/assets/108328466/f16cb2f0-2d01-45a0-bf72-4745096e63b1)
![Screenshot from 2023-09-21 04-07-00](https://github.com/lalithlochanr/pes_pd/assets/108328466/57ef3a32-17de-4602-a1ff-e46206d185ae)
![Screenshot from 2023-09-21 04-07-17](https://github.com/lalithlochanr/pes_pd/assets/108328466/00f1af5c-3553-4844-970e-a698bf7c1d6f)


![Screenshot from 2023-09-21 04-18-55](https://github.com/lalithlochanr/pes_pd/assets/108328466/dce08360-2da2-4214-97ca-9dca661c4e73)

````
init_floorplan
run_placement
````
-In terminal
````
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/18-09_12-32/results/placement
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
````
![Screenshot from 2023-09-21 04-30-37](https://github.com/lalithlochanr/pes_pd/assets/108328466/8afb6e5d-c2d4-4063-b6cf-3ad75f295071)
![Screenshot from 2023-09-21 04-23-02](https://github.com/lalithlochanr/pes_pd/assets/108328466/a85fcb40-9ad7-4dd0-beb5-7b75ab2ac6f8)
![Screenshot from 2023-09-21 04-25-04](https://github.com/lalithlochanr/pes_pd/assets/108328466/797a770d-d487-4e25-a7ad-d6e41c3dba49)
  
</details>

<details>
  <summary> Timing analysis with ideal clocks using openSTA </summary>
- Setup time analysis
  Setup time analysis is a fundamental aspect of digital circuit design and timing analysis. It refers to the assessment and verification of the minimum amount of time that a data input signal must be stable and available before the active edge of a clock signal (typically the rising edge) for proper and reliable operation of a flip-flop or other sequential logic element.  

1. Setup Time: Setup time is the minimum time interval before the clock edge when a data input must be stable and valid to ensure correct data capture by a flip-flop or latch, preventing setup violations and potential data errors.

2. Hold Time: Hold time is the minimum time interval after the clock edge during which a data input must remain stable and unchanged to prevent data corruption or hold-time violations within a flip-flop or latch.

![Screenshot from 2023-09-21 04-40-18](https://github.com/lalithlochanr/pes_pd/assets/108328466/c40d5798-935a-4a03-9467-18a41ee352d3)
![Screenshot from 2023-09-21 04-35-46](https://github.com/lalithlochanr/pes_pd/assets/108328466/e26b48df-fece-434b-b06a-ca449915ce7e)
![Screenshot from 2023-09-21 04-35-58](https://github.com/lalithlochanr/pes_pd/assets/108328466/68d11775-3985-424c-ae16-5552fa6ce1e4)
![Screenshot from 2023-09-21 04-37-00](https://github.com/lalithlochanr/pes_pd/assets/108328466/8607a4cd-5cfe-4f23-b747-6178ba498f15)
![Screenshot from 2023-09-21 04-37-12](https://github.com/lalithlochanr/pes_pd/assets/108328466/f788d439-11aa-47c8-970f-619d67bba1fa)
  
</details>
<details>
  <summary> Clock Tree Synthesis(CTS)</summary>
 - Clock Tree Synthesis (CTS) is a crucial step in digital integrated circuit design. It involves the generation of an optimized and efficient network of clock distribution paths within a chip, ensuring that the clock signal reaches all sequential elements simultaneously and with minimal skew. CTS minimizes clock distribution delays, reduces clock skew, and aligns clock arrival times at flip-flops, enhancing overall chip performance, reliability, and the ability to meet stringent timing requirements. By carefully balancing and buffering the clock signals, CTS plays a vital role in achieving reliable and high-performance digital systems.

![Screenshot from 2023-09-21 04-48-23](https://github.com/lalithlochanr/pes_pd/assets/108328466/44b6788c-d156-48c5-b60b-834def99352b)

- Clock net shielding and buffering are employed in integrated circuit design to mitigate clock skew, reduce signal interference, and ensure consistent clock distribution. Shielding protects the clock signal from external noise, while buffering amplifies the clock to maintain signal integrity and synchronize its arrival at various destinations.
![Screenshot from 2023-09-21 04-48-49](https://github.com/lalithlochanr/pes_pd/assets/108328466/7355c534-f6d7-4cac-9eb4-ce9afd90cec7)
![Screenshot from 2023-09-21 04-49-00](https://github.com/lalithlochanr/pes_pd/assets/108328466/76041a13-1a96-46f2-8dfd-095dc0a73286)

- Cross-talk induced delta delay refers to the additional time delay introduced in digital circuits due to unwanted electromagnetic interference or coupling between adjacent signal lines. This phenomenon can lead to signal integrity issues, where the switching of one signal affects the timing or integrity of another signal, potentially causing errors or performance degradation. Engineers employ various techniques, including shielding, routing separation, and signal isolation, to mitigate cross-talk-induced delta delay and ensure reliable and predictable operation of digital systems.

![Screenshot from 2023-09-21 04-53-35](https://github.com/lalithlochanr/pes_pd/assets/108328466/52a079a2-c018-4b1e-9994-d8f097bd448f)

- create two file one is pre_sra.conf and my_base.sdc
- save pre_sra.conf in loaction ~/Desktop/work/tools/openlane_working_dir/openlane
- save my_base.sdc in location ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/sr

  ![Screenshot from 2023-09-21 18-08-27](https://github.com/lalithlochanr/pes_pd/assets/108328466/cf88995c-d09b-4ba6-862d-67f0c8e22b2d)
  ![Screenshot from 2023-09-21 18-09-17](https://github.com/lalithlochanr/pes_pd/assets/108328466/e1215ed9-b236-47df-9ab8-f02b65855d62)


</details>

<details>
  <summary> Timing analysis with real clocks using openSTA </summary>

![Screenshot from 2023-09-21 04-55-17](https://github.com/lalithlochanr/pes_pd/assets/108328466/7cc24c7d-99f1-42c0-bc59-0c4ea5b5388c)
![Screenshot from 2023-09-21 04-55-28](https://github.com/lalithlochanr/pes_pd/assets/108328466/3bccc554-e77c-4612-98d3-6d677acc7964)
![Screenshot from 2023-09-21 04-56-09](https://github.com/lalithlochanr/pes_pd/assets/108328466/d365a142-cb24-47ad-a382-f263dd2966d3)
![Screenshot from 2023-09-21 04-55-45](https://github.com/lalithlochanr/pes_pd/assets/108328466/606865a3-2f5b-455b-a505-80f43d8ae538)

In openlane,
````
run_cts
openroad
read_lef /openLANE_flow/designs/picorv32a/runs/18-09_12-32/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/18-09_12-32/results/cts/picorv32a.cts.def
write_db pico_cts.db
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/18-09_12-32/results/synthesis/picorv32a.synthesis_cts.v
read_liberty -max $::env(LIB_SLOWEST)
read_liberty -max $::env(LIB_FASTEST)
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -format full_clock_expanded -digits 4
````
![Screenshot from 2023-09-21 18-30-03](https://github.com/lalithlochanr/pes_pd/assets/108328466/5a8ec773-4eed-4707-9edc-056fac41bb31)
![Screenshot from 2023-09-21 18-30-48](https://github.com/lalithlochanr/pes_pd/assets/108328466/c98ff361-38e7-4a63-a329-864443db4aed)
![Screenshot from 2023-09-21 18-37-26](https://github.com/lalithlochanr/pes_pd/assets/108328466/06197329-d69f-44a1-ae64-0c72d0efe315)

</details>

# Day 5- Final steps for RTL2GDS using tritonRoute and openSTA

<details>
  <summary> Introduction to Maze Routing & Design Rule Check</summary>
- Maze Routing:  
     
  Maze routing is a process used in electronic design automation to find optimal paths for interconnections on a printed circuit board or integrated circuit. It navigates through a grid of obstacles, such as existing wiring or components, to establish efficient and interference-free routes for signals, ensuring reliable connectivity and meeting design constraints. Maze routing algorithms aim to minimize wirelength, delay, and congestion while complying with the specified design rules.

![Screenshot from 2023-09-21 05-29-53](https://github.com/lalithlochanr/pes_pd/assets/108328466/75caffb3-90b2-4bd8-b67f-ce565168e951)
![Screenshot from 2023-09-21 05-30-20](https://github.com/lalithlochanr/pes_pd/assets/108328466/b9f8ccaa-d9dc-48c0-9885-fd98cc530a95)
![Screenshot from 2023-09-21 05-30-38](https://github.com/lalithlochanr/pes_pd/assets/108328466/ac2ba1e8-8fcb-45bb-a13a-b747eee5bf76)

- DRC check:
    
  Design Rule Checking (DRC) is a critical step in semiconductor chip design to ensure that the layout adheres to the specified design rules and constraints.
1. Spacing Rules: Ensure minimum and maximum spacing between adjacent features to prevent short circuits and defects.
   
2. Width Rules: Verify feature widths, such as metal traces and gates, fall within acceptable limits to maintain proper dimensions.

3. Enclosure Rules: Confirm that certain features are enclosed correctly to prevent unintended interactions.

4. Area Rules: Ensure specific layout areas adhere to defined constraints, including density rules.

5. Via Rules: Check that vias meet size, placement, and enclosure requirements for vertical connections between metal layers.

and so on.

  
</details>

<details>
  <summary> Power Distribution & Network Routing  </summary>
  
- In openlane,
 

  ````
  echo $::env(CURRENT_DEF)
  gen_pdn
  run_routing
  ````

![Screenshot from 2023-09-21 18-49-14](https://github.com/lalithlochanr/pes_pd/assets/108328466/e7c73026-654b-4d7e-9fc9-b6813add5a95)

![Screenshot from 2023-09-21 05-46-38](https://github.com/lalithlochanr/pes_pd/assets/108328466/296bae45-6f99-4fc7-9cef-d9cb4a9812a0)

  * Triton Routing:
  
    TritonRout is an open-source, multi-objective, detailed router used in the field of electronic design automation (EDA). It is primarily designed for digital integrated circuit (IC) routing and is known for its versatility and efficiency in producing high-quality chip layouts. TritonRoute employs advanced algorithms to tackle complex routing challenges, such as minimizing wirelength, congestion, and achieving optimal performance within specified design constraints. As an open-source tool, TritonRoute has gained popularity in the semiconductor industry, enabling designers to access a powerful routing solution while contributing to its ongoing development and improvement.
    
![Screenshot from 2023-09-21 05-46-23](https://github.com/lalithlochanr/pes_pd/assets/108328466/c6f2096a-58f9-49be-935f-3e40708b6f9d)
![Screenshot from 2023-09-21 05-48-05](https://github.com/lalithlochanr/pes_pd/assets/108328466/9f469b71-f8ee-431e-97a9-4dcc201d64f1)

* SPEF extractor :
  
  An SPEF extractor is a critical tool in semiconductor design that generates Standard Parasitic Exchange Format (SPEF) files from chip layouts. These files capture essential parasitic capacitance and resistance data, crucial for accurate timing analysis and chip performance verification.

````
cd Desktop/work/tools/SPEF_Extractor
python3 /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/18-09_12-32/tmp/merged.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/18-09_12-32/results/routing/picorv32a.def
````
  
</details>
