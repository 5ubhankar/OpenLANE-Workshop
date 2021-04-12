# Advanced Physical Design - OpenLANE Workshop
![advanced_physical_design](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/advanced_physical_design.png)



## Table of Contents
1. [**About the project**](https://github.com/5ubhankar/OpenLANE-Workshop#about-the-project)
2. [**OpenLANE Architecture**](https://github.com/5ubhankar/OpenLANE-Workshop#openlane-architecture)
3. [**Day-1 Inception of open-source EDA, OpenLANE and Sky130 PDK**](https://github.com/5ubhankar/OpenLANE-Workshop#day-1-inception-of-open-source-eda-openlane-and-sky130-pdk)
    * Skywater PDK Files
    * Invoking OpenLANE
    * Package Importing
    * Design Folder
    * Design Folder Hierarchy
    * Configuration Files
    * Prepare Design
    * Synthesis
5. [**Day-2 Good floorplan vs bad floorplan and introduction to library cells**](https://github.com/5ubhankar/OpenLANE-Workshop#day-2-good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)
6. [**Day-3 Design library cell using Magic Layout and ngspice characterization**](https://github.com/5ubhankar/OpenLANE-Workshop#day-3-design-library-cell-using-magic-layout-and-ngspice-characterization)
7. [**Day-4 Pre-layout timing analysis and importance of good clock tree**](https://github.com/5ubhankar/OpenLANE-Workshop#day-4-pre-layout-timing-analysis-and-importance-of-good-clock-tree)
8. [**Day-5 Final steps for RTL2GDS using tritonRoute and openSTA**](https://github.com/5ubhankar/OpenLANE-Workshop#day-5-final-steps-for-rtl2gds-using-tritonroute-and-opensta)


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

## Day-1 Inception of open-source EDA, OpenLANE and Sky130 PDK
#### Openlane working directory ####
![1.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.1%20openlane%20directory.jpg)

![1.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.2%20pdks.jpg)

![1.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.3%20inside%20sky130a.jpg)

#### Invoking OpenLANE and Package Importing ####
![1.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.4%20invoke%20openlane.jpg)

#### Design Folder ####
![1.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.6%20design%20folder.jpg)
![1.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.7%20inside%20src.jpg)

#### Synthesis ####
![1.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/1.8%20inside%20runs.jpg)

## Day-2 Good floorplan vs bad floorplan and introduction to library cells
![2.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.1%20folder%20-tag.jpg)

![2.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.2%20folder%20-overwrite.jpg)

![2.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.3%20chg%20clk%20period.jpg)

![2.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.4%20config%20all%20flags.jpg)

![2.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.5%20floorplan%20def.jpg)

![2.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.6%20Floorplan%20magic%20run.jpg)

![2.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.7%20floorplan%20magic%20result.jpg)

![2.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.8%20placement%20magic%20run.jpg)

![2.9](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/2.9%20placement%20magic%20result.jpg)

## Day-3 Design library cell using Magic Layout and ngspice characterization
![3.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.1%20floorplan%20mode%20chg.jpg)

![3.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.2%20floorplan%20mode%20chg%20op.jpg)

![3.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.3%20cp%20tech%20file%20to%20inv%20folder.png)

![3.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.4%20magic%20inv.png)

![3.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.5%20inv%20spice%20create.png)

![3.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.6%20inv%20spice%20file%20location.png)

![3.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.7%20edit%20spice%20file.png)

![3.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.8%20spice%20results.png)

![3.9](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.9%20spice%20plot.png)

![3.10](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.10%20rise%20transition%20delay.png)

![3.11](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.11%20fall%20transition%20delay.png)

![3.12](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.12%20cell%20rise%20delay.png)

![3.13](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/3.13%20cell%20fall%20delay.png)

## Day-4 Pre-layout timing analysis and importance of good clock tree
![4.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.1%20tracks%20file.png)

![4.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.2%20magic%20grid%20cmd.png)

![4.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.3%20port%20def%20of%20layout.png)

![4.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.4%20def%20port%20class%20and%20use.png)

![4.5](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.5%20lef%20write.png)

![4.6](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.6%20modify%20picorv32a%20config%20file.png)

![4.7](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7%20add%20inv%20to%20picorv32a%20cmd.png)

![4.7.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7.1%20inv%20included%20in%20the%20merged%20lef%20file.png)

![4.7.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.7.2%20inv%20inside%20picorv32s.png)

![4.8](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8%20cmd%20to%20improve%20slack%201.png)

![4.8.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.1%20slack%20improved%201.png)

![4.8.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.2%20cmd%20to%20improve%20slack%202.png)

![4.8.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.8.3%20slack%20improved%202.png)

![4.10](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.10%20base%20sdc%20file%20in%20src.png)

![4.11](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.11%20pre_sta%20conf%20file%20in%20openlane.png)

![4.12](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.12%20buf%201%20to%204%20improve%20slack%203.png)

![4.12.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.12.1%20slack%20improved%203.png)

![4.13](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.13%20overwrite%20verilog%20file.png)

![4.14](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.14%20run_cts.png)

![4.15](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15%20openroad%20read%20def.png)

![4.15.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.1%20openroad%20read%20lef.png)

![4.15.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.2%20write%20db%20and%20read%20liberty%20max.png)

![4.15.3](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.3%20read%20liberty%20min%20and%20sdc.png)

![4.15.4](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.15.4%20report%20checks.png)

![4.16](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/4.16%20slack%20improved%204%20typical.png)


## Day-5 Final steps for RTL2GDS using tritonRoute and openSTA
![5.1](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/5.1%20pdn%20results.png)

![5.2](https://github.com/5ubhankar/OpenLANE-Workshop/blob/main/Screenshots/5.2%20run_routing.png)


## Acknowledgments

1. [Kunal Ghosh](https://github.com/kunalg123) - Co-founder (VSD Corp. Pvt. Ltd)
2. [Nickson Jose](https://github.com/nickson-jose/) - Teaching Assistant (VSD Corp. Pvt. Ltd)







