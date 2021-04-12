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

    #### Skywater PDK Files ####

    * Invoking OpenLANE

    * Package Importing

    * Design Folder

    * Design Folder Hierarchy

    * Configuration Files

    * Prepare Design

    * Synthesis





## Day-2 Good floorplan vs bad floorplan and introduction to library cells

## Day-3 Design library cell using Magic Layout and ngspice characterization

## Day-4 Pre-layout timing analysis and importance of good clock tree

## Day-5 Final steps for RTL2GDS using tritonRoute and openSTA







