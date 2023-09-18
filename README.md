# pes_pd

# Day 1 - Inception of Open-Source EDA, OpenLANE & Sky130 PDK

<details>
  <summary>How to talk to computers </summary>

<details>
  <summary>Introduction to QFN-48 Package, chip, pads, core, die and IPs</summary>

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
  
</details>

<details>
  <summary>RISC-V flow</summar>
* Flow:
    
  ![Screenshot 2023-09-18 103611](https://github.com/lalithlochanr/pes_pd/assets/108328466/a0323dbe-8072-4dcf-9f5d-f7dda3059180)  

  ![Screenshot 2023-09-18 103930](https://github.com/lalithlochanr/pes_pd/assets/108328466/0989080d-23bd-413c-9ab4-ea5ed9cea589)  

  ![Screenshot 2023-09-18 104105](https://github.com/lalithlochanr/pes_pd/assets/108328466/7a500dd6-61c5-4314-9bda-4d4ff797c7ad)  

</details>

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


    











    
</details>


