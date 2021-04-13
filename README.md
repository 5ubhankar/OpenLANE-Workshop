# Advanced Physical Design - OpenLANE Workshop
![advanced_physical_design](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/advanced_physical_design.png)



## Table of Contents
1. [**About the project**](https://github.com/5ubhankar/OpenLANE-Workshop#about-the-project)
    * Openlane working directory
    * Invoking OpenLANE and Package Importing
    * Design Folder
    * Synthesis
3. [**OpenLANE Architecture**](https://github.com/5ubhankar/OpenLANE-Workshop#openlane-architecture)
4. [**Day-1 Inception of open-source EDA, OpenLANE and Sky130 PDK**](https://github.com/5ubhankar/OpenLANE-Workshop#day-1-inception-of-open-source-eda-openlane-and-sky130-pdk)   
5. [**Day-2 Good floorplan vs bad floorplan and introduction to library cells**](https://github.com/5ubhankar/OpenLANE-Workshop#day-2-good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)
6. [**Day-3 Design library cell using Magic Layout and ngspice characterization**](https://github.com/5ubhankar/OpenLANE-Workshop#day-3-design-library-cell-using-magic-layout-and-ngspice-characterization)
7. [**Day-4 Pre-layout timing analysis and importance of good clock tree**](https://github.com/5ubhankar/OpenLANE-Workshop#day-4-pre-layout-timing-analysis-and-importance-of-good-clock-tree)
8. [**Day-5 Final steps for RTL2GDS using tritonRoute and openSTA**](https://github.com/5ubhankar/OpenLANE-Workshop#day-5-final-steps-for-rtl2gds-using-tritonroute-and-opensta)
9. [**Acknowledgments**](https://github.com/5ubhankar/OpenLANE-Workshop#acknowledgments)


## About the project ##
This project gives an interactive tutorial experied during the VSD Advanced Physical Design workshop using OpenLANE.

OpenLANE is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, Fault, OpenPhySyn, SPEF-Extractor and custom methodology scripts for design exploration and optimization. It is a tool started for true open source tape-out experience and comes with APACHE version 2.0 licence. The goal of OpenLANE is to produce clean GDSII without any human intervention. OpenLANE is tuned for Skywater 130nm open-source PDK and can be used to produce hard macros and chips.

## OpenLANE Architecture ##
Process Design Kit (PDK) is the interface between the CAD designers and the foundry. The PDK is a collection of files used to model a 
fabrication process for the EDA tools used in designing an IC. PDK’s are traditionally closed-source and hence are the limiting factor to 
open-source Digital ASIC Design. Google and Skywater have broken this stigma and published the world’s first open-source PDK on June 30th, 
2020. This breakthrough has been a catalyst for open-source EDA tools. This workshop focuses on using the open-source RTL2GDS EDA tool, 
OpenLANE, in conjunction with the Skywater 130nm PDK to perform the full  RTL2GDS flow as shown below:

![OpenLANE_flow](https://github.com/efabless/openlane/blob/master/docs/_static/openlane.flow.1.png)

---
## Day-1 Inception of open-source EDA, OpenLANE and Sky130 PDK
#### Openlane working directory ####
![1.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.1%20openlane%20directory.jpg)

OpenLANE PDK - sky130A was used here.
![1.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.2%20pdks.jpg)

the tech and ref file location.
![1.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.3%20inside%20sky130a.jpg)

#### Invoking OpenLANE and Package Importing ####
![1.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.4%20invoke%20openlane.jpg)

#### Design Folder ####

![1.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.6%20design%20folder.jpg)

Verilog and sdc file inside src
![1.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.7%20inside%20src.jpg)

#### Synthesis ####
After synthesis these folders gets generated with a time stamp
![1.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.8%20inside%20runs.jpg)

---
## Day-2 Good floorplan vs bad floorplan and introduction to library cells

Floorplanning includes:
* Define the size of your chip/block and Aspect ratio
* Defining the core area and IO core spacing
* Defining ports specified by top level engineer.
* Design a Floor Plan and Power Network with horizontal metal layer such that the total IR Drop must be less than 5% (VDD+VSS) of VDD to operate within the power budget.
* IO Placement/Pin placement
* Allocates power routing resources
* Place the hard macros (fly-line analysis) and reserve space for standard cells.
* Defining Placement and Routing blockages blockages
* If we have multi height cells in the reference library separate placement rows have to be provided for two different unit tiles.
* Creating I/O Rings
* Creating the Pad Ring for the Chip
* Creating I/O Pin Rings for Blocks

Switch -tag load a the design in openLANE
![2.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.1%20folder%20-tag.jpg)

Switch -overwrite to overwrite the design in openLane
![2.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.2%20folder%20-overwrite.jpg)

Change the clock period in the working design folder itself without change it in the config file.
![2.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.3%20chg%20clk%20period.jpg)

Location of the configuration files. Readme file contains all information about the flags of all stages.
![2.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.4%20config%20all%20flags.jpg)

The def file location of the floorplan
![2.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.5%20floorplan%20def.jpg)

Command to run the magic tool with the floorplan result and the sky130 techfile
![2.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.6%20Floorplan%20magic%20run.jpg)

The floorplan in the magic window.
![2.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.7%20floorplan%20magic%20result.jpg)

Command to run the magic tool with the placement result and the sky130 techfile
![2.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.8%20placement%20magic%20run.jpg)

The placement in the magic window.
![2.9](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.9%20placement%20magic%20result.jpg)

---
## Day-3 Design library cell using Magic Layout and ngspice characterization
Setting the IO pin mode in run time.
![3.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.1%20floorplan%20mode%20chg.jpg)

Result after changing the IO pin mode.
![3.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.2%20floorplan%20mode%20chg%20op.jpg)

Clone the inverter design from git loaction -> https://github.com/nickson-jose/vsdstdcelldesign.git
Folder location inside the openLANE to be placed.
![3.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.3%20cp%20tech%20file%20to%20inv%20folder.png)

Inverter layout in magic.
![3.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.4%20magic%20inv.png)

Create spice file for the inverter.
![3.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.5%20inv%20spice%20create.png)

Spice file created location.
![3.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.6%20inv%20spice%20file%20location.png)

Add VDD and VSS in Spice file and also add a pulse to plot a respone.
![3.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.7%20edit%20spice%20file.png)

Runing ngspice and then plotting the output to time.
Run spice file -> `$ ngspice sky130a_inv.spice`
![3.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.8%20spice%20results.png)

ngSpice output plot.
![3.9](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.9%20spice%20plot.png)

Rise transition delay = Time taken for the output signal to reach from 20% of max value to 80% of max value.

![3.10](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.10%20rise%20transition%20delay.png)
`Value = 0.06397ns`

Fall transition delay = Time taken for the output signal to reach from 80% of max value to 20% of max value.

![3.11](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.11%20fall%20transition%20delay.png)
`Value = 0.04283ns`

Cell rise delay = Time difference between 50% of rising output and 50% of falling input.

![3.12](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.12%20cell%20rise%20delay.png)
`Value = 0.0595ns`

Cell fall delay = Time difference between 50% of falling output and 50% of rising input.

![3.13](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.13%20cell%20fall%20delay.png)
`Value = 0.02761ns`

---
## Day-4 Pre-layout timing analysis and importance of good clock tree





Tracks file is used during the routing stage. These control the routes, that specification is given by tarcks.
![4.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.1%20tracks%20file.png)

Run grid command in the magic console to draw grid on the laout as per requirement.
![4.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.2%20magic%20grid%20cmd.png)

Needed to define ports to the layout before converting to lef.
![4.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.3%20port%20def%20of%20layout.png)

Define port class and port use in magic:
![4.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.4%20def%20port%20class%20and%20use.png)

Command to make the lef file from magic console.
![4.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.5%20lef%20write.png)

Modify config.tcl file for synthesis.
![4.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.6%20modify%20picorv32a%20config%20file.png)

Commands run during openlane flow to include the inverter in the picorv32a
![4.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7%20add%20inv%20to%20picorv32a%20cmd.png)

Custom inverter inside the merged.lef file
![4.7.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7.1%20inv%20included%20in%20the%20merged%20lef%20file.png)

Placement of the custom inverter inside the picorv32a layout.
![4.7.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7.2%20inv%20inside%20picorv32s.png)

Slack optimisations by setting synthesing strategy and sizing.
![4.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8%20cmd%20to%20improve%20slack%201.png)

Slack improvement 1
![4.8.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.1%20slack%20improved%201.png)

Setting max fanout to 4 
![4.8.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.2%20cmd%20to%20improve%20slack%202.png)

Slack improvement 2
![4.8.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.3%20slack%20improved%202.png)

Editing the base.sdc file inside src folder. 
![4.10](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.10%20base%20sdc%20file%20in%20src.png)

pre_sta.conf file inside the openlane working folder. Set of command to run in openSTA timing analysis.
![4.11](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.11%20pre_sta%20conf%20file%20in%20openlane.png)

After running the openSTA separately, slack improved by replacing buffer 1 with buffer 4 to increase speed. But this will reduce area.
![4.12](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.12%20buf%201%20to%204%20improve%20slack%203.png)

Slack improved 3
![4.12.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.12.1%20slack%20improved%203.png)

The improved netlist is replaced with the exiting synthesis verilog file inside the results folder.
![4.13](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.13%20overwrite%20verilog%20file.png)

Run clock tree synthesis

![4.14](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.14%20run_cts.png)

In OpenROAD the timing analysis is done by creating a .db database file. This database file is created from the post-cts LEF and DEF files. To generate the .db files within OpenROAD. Whenever the DEF file changes we need to recreate this .db file.

Reading def file
![4.15](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15%20openroad%20read%20def.png)

Reading lef file
![4.15.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.1%20openroad%20read%20lef.png)

Writing the db file, reading the verilog file and lib files.
![4.15.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.2%20write%20db%20and%20read%20liberty%20max.png)
![4.15.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.3%20read%20liberty%20min%20and%20sdc.png)

Running the report 
![4.15.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.4%20report%20checks.png)

Final slack report
![4.16](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.16%20slack%20improved%204%20typical.png)

---
## Day-5 Final steps for RTL2GDS using tritonRoute and openSTA

After generating clock tree network and verifying post routing STA checks next step is power distribution network generation in OpenLANE.
Command -> `% gen_pdn`

Report generated after running pdn
![5.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/5.1%20pdn%20results.png)

Comand to run routing.

![5.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/5.2%20run_routing.png)

If there are DRC errors after routing two ways to fix them - re-run routing with higher QoR settings or manually fix DRC errors specific in tritonRoute.drc file.

After routing has been completed interconnect parasitics can be extracted to perform sign-off post-route STA analysis. The parasitics are extracted into a SPEF file. The SPEF extractor is not included within OpenLANE as of now.

DRC and LVS verifiaction can be done in magic and netgen respectively. GDSII file can be obtained from magic.

---
## Acknowledgments

1. [Kunal Ghosh](https://github.com/kunalg123) - Co-founder (VSD Corp. Pvt. Ltd)
2. [Nickson Jose](https://github.com/nickson-jose/) - Teaching Assistant (VSD Corp. Pvt. Ltd)







