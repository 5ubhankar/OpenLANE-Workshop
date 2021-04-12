# OpenLANE-Workshop
![advanced_physical_design](https://user-images.githubusercontent.com/82052594/114381521-d4af4780-9ba8-11eb-8ab5-f9009734f23a.png)

**Advanced Physical Design - OpenLANE Workshop**
## Table of Contents
* [**Day-1 [Inception of open-source EDA, OpenLANE and Sky130 PDK]**](https://github.com/5ubhankar/OpenLANE-Workshop#day-1-inception-of-open-source-eda-openlane-and-sky130-pdk)
* [**Day-2 [Good floorplan vs bad floorplan and introduction to library cells]**](https://github.com/5ubhankar/OpenLANE-Workshop#day-2-inception-of-open-source-eda-openlane-and-sky130-pdk)
* [**Day-3 [Design library cell using Magic Layout and ngspice characterization]**](https://github.com/5ubhankar/OpenLANE-Workshop#day-3-inception-of-open-source-eda-openlane-and-sky130-pdk)
* [**Day-4 [Pre-layout timing analysis and importance of good clock tree]**](https://github.com/5ubhankar/OpenLANE-Workshop#day-4-inception-of-open-source-eda-openlane-and-sky130-pdk)
* [**Day-5 [Final steps for RTL2GDS using tritonRoute and openSTA]**](https://github.com/5ubhankar/OpenLANE-Workshop#day-5-inception-of-open-source-eda-openlane-and-sky130-pdk)



## Day-1 [Inception of open-source EDA, OpenLANE and Sky130 PDK]

## Day-2 [Good floorplan vs bad floorplan and introduction to library cells]

## Day-3 [Design library cell using Magic Layout and ngspice characterization]

## Day-4 [Pre-layout timing analysis and importance of good clock tree]

## Day-5 [Final steps for RTL2GDS using tritonRoute and openSTA]



Working directory of Openlane




 
 
  
  
  
  
  
  
  
  
  
  
  
  
 
 
 

 




 



pdks – process design kit; information related to PDK; 




 




Skywater-pdk – has all the timing libraries, cell lef, tech
lef, all files. Made to work with commercial tools.



Open_pdk – make compatible to open surce tools.



Sky130A – made compatible to 
work on open source environment. PDK variant.




 




Libs.ref – process files – time, 



Libs.tech – technology files




 




Will be working on sky130_fd_sc_hd – >
precess.name_foundry.name_std.cell_high.density(variant)




 




Techlef contains files woth layer info



Lib – all timing files



Lef – just  cel lef




 




Working directory for open lane




 




Start to use open lane with interactive option



Step 1> package require opwnlane 0.9 - Import all package
required to run open lane



Step 2> prep –design picorv32a - Setup file inside design
folder




 




Files inside the design folder – many design



Config.tcl – bypasses default values (override settings)



Default > Config.tcl>sky130_config.tcl(highest
priority)



We work on picorv32a design




 




SRC – has picorv32a.v RTL file and SDC information




 




Setup file created inside design folder “../openLANE_flow/designs/picorv32a”
to after running the preparation step.



This config.tcl get all the default parameter taken by the
run. Can make changes on the fly make change on the config file – run floorplan
the default will change.



Cmd.log – record of all the records applied



Step 3> run_synthesis – runs yosys and abc



After synthesis completes will get all reports and results
populated inside runs folder.



 



DAY 2



1.     
Utilisation factor – =area occupied by netlist/
total area of the core. Aspect ratio – height / width. If aspect ratio is 1
core is  square shape. Other wise
rectangle



2.     
Pre-placed cells – are cell designed once and
can be reused. There placement is fixed.



3.     
Decoupling capacitors – use to decouple the main
circuit from the source. So that is does 
not have to depend on soure to get adequate voltage. And keep the
voltage logic out of the undefined region.



4.     
Power planning – discharge all capacitor at same
time > (cause Ground bounce || cause voltage droop) >  may cause logic errors if outside the noise
margin level. 



5.     
Pin placement and logical cell placement
blockage – setup the pins in logical places (after backend and front
consultation). Block the boundary for pin connections. So that the automatic
placement tool don’t use the area for placing ips.



 



Die area>core area>aspect ratio>utilisation factor>place i/o
cells>power distribution n/w (pg creation power grid)>macroplacement>



Standard cells are placed in placement stage



 



1.     
To  make
folder with a custom name




 




2.     
Used to remove the existing folder and create a
new folder 




 




3.     
Change the clock period in the working design
folder itself 
 




 



Readme file contains all info about the flags of all stages




 




Used to execute floorplan -> %run_floorplan



After running floorplan we can see the .def(design exchange
format) file to calculate the die area




 




Command - $ magic –T/home/subha/Desktop/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech
lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &




 




Tapcells, decap cells



 



After running floorplan using magic



S-mouse pointer hover and select



v-center



z-zoom shift + z to zoom out



left and right click to select



use the command "what" in the "tkcon 2.3
main" xterm for viewing detials of any selected




 




 



Netlist binding and initial place design



1.     
Bind netlist with physical cells-Library
consists of cell, varios shapes and sizes of same cells, timing info, delay
info, 



2.     
Placement – best placement possible. Closer to
i/o



3.     
Optimize placement – estimate wire length and
capacitance and based on that insert repeaters. Add buffers to optimise the
wire lengths.



Library characterization and
modelling – 



Part1 – concepts and theory –
NLDM, ccs timing, power and noise characterization



Logic sysnthisis >
floorplanning > placement > CTS > routing > STA



 



Atomic Command used to do the
placement - > %run_placement 



Then do this Command from the placement result folder > -
$ magic –T/home/subha/Desktop/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech
lef read ../../tmp/merged.lef def read picorv32a.placement.def &




 




 




 




 



Cell design flow – 



Inputs (PDKs: DRC&LVS, SPICE,
Library & user defined specs)



Design steps (circuit design,
latout design, characterisations[timing, power, noise])



Outputs – CDL (circuit description
language), GDSII, LEF, extracted spice netlist(.cir), timing, noise, power,
.libs, function



 



GUNA software for characterisation
–



Timing characterisation,
propagation delay, 




 




 



 



 



Day 3



Setting the IO pin mode in run
time




 




Result after running
floorplan(Hungarian IO pin placement algorithm)




 




 



VTC spice simulation



SPICE deck-Component connectivity,
component values, 



M1 Drain gate source substrate
pmos  W=0.375u L=0.5u



CMOS inv spice simulation



Switching threshold Vm



Static and Dynamic simulation of
CMOS inv



 



Take inverter design from git by git clone
-https://github.com/nickson-jose/vsdstdcelldesign.git



Do spice extraction and post layout spice simulations



 



 



Copy sky130a tech file to the git folder




 





 





 





 




 



Create Active regions – 16-mask
CMOS process



1.selecting a substrate > 2.creating
active region for transistors > 3.N-well and p-well formation > 4.formation
of gate > 5.lightly doped drain (LDD) formation > 6.source and drain
formation > 7.steps to form contacts and interconnects(local) > 8.Higher
level metal formation > 



 



Convert inverter to spice file
 




Files inside the inverter folder




 




Edit spice file




 




 




 





 




 



 



 



rise




 




Fall-




 




Rise delay-




 




Fall delay-




 




 



DRC-



http://opencircuitdesign.com/magic/



https://skywater-pdk.readthedocs.io/en/latest/



https://skywater-pdk--136.org.readthedocs.build/en/136/



https://github.com/google/skywater-pdk



http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz



…



…



…



CIF-caltech intermediate
format   || common output format-human
readable asci format



Magic –o gl || magic –d XR



: || ; used to move from layout to
console window in magic until hit return or enter



drc why  - know the drc violations



paint command | | P key || middle mouse
button on the side bar



cif see VIA2 – to see contact
cuts  || feed clear – to clear cif



box – calc dimentions ; snap int ;
tech loadsky130A.tech ; drc check ;



select cell
<instance_name> ; findbox zoom.



8:35



command to find a
particular cell using its instance name in MAGIC



 



Day 4




 




1.     
Input and output port must lie on the horizontal
tracts



2.     
Width of the standard cell must be in the odd
multiples of the track pitch



3.     
Height must be of odd multiple of track vertical
pitch



Press g to activate grids



help grid command 




 




Then create grids as per the tracks file




 




 



port defining-




 




Define port class and port use in magic:




 




Lef writing command-




 




Bring lef file to picorv32a src
folder



Bring all types of library file to
src




 




Modify config.tcl file for synthesis




 




Commands run during openlane flow
to include the inverter in the picorv32a




 




Info about offset and pitch > What is the default pitch
and offset (respectively) of metal2 layer defined in tech LEF




 




Delay tables



Power aware CTS



Delay table beome the timing model
of buffer




 




 



Settings changed to improve the
slack




 




 




 




Inverter inside the merged.lef
file



 




 




Placement of inverter inside
picorv32a after placement




 




 



Base.sdc file inside src




 




 



Pre_sta.conf file in the openlane
folder 




 




 



First run opensta > command > sta pre_sta.conf




 




 




 




Report generation for opensta




 




Change a buffer size from 1 to 4 to improve slack in openSTA



Upsizing the buffer with more slack




 




Slack decreased




 





 




After further resizing




 




Overwrite the Verilog file




 





 




Atomic command > procs > inside the
openlan/scripts> all tcl scripts/tcl_commands for procs > 




 





 




 



echo $::env(CURRENT_DEF)



read_lef /openlane/../merged.lef




 





 





 





 





 





 





 





 




Above analysis is wrong as use typical Verilog for min and
max corners



For correct analysis




 




 




 




 




 




After gen_pdn




 




 



run_routing



TritonRoute- MILP-mixed integer linear programing



Globalroute-fastroute > detailed route- tritonrout



Violations after routing




 




Fastrouting




 




SPEF extraction outside of openlane




 




 Results file
generated




 




Post synthesis new netlist is created



Pre routing antennae diode insertion happens




 




Post sta analysis use picorv32a.synthesis_preroute.v Verilog
netlist



Use same sdc file as reference



read_spef for reading parasitics in openlane for post route
STA analysis



***CTS_tolerance – QoR – quality of result : trade off b/w
runtime and Qor:lower Qor Degraded the results



***



(* improved netlist -> Netlist with post synthesis setup
slack = -0.12 ./vsdstdcelldesign/extras)



For the improved netlist*, what’s the setup clock skew with
default buffer list?



For the improved netlist*, what’s the setup slack with
default buffer list?



For the improved netlist*, what’s the hold clock skew with
default buffer list? 



For the improved netlist*, what’s the hold slack with
default buffer list?



Removing element from the list




 




 



Clock skew should be max 10% of clock period



 
 




Insert buf 1 again




 




Kill task




 





 





 




When running cts 2nd time error occur as current
become cts def file. But we need the previous step def file of placement.



The current def file was wrong so run cts got stuck. Replace
the file. Then run cts



Even if the cts flow run successfully there will be error
later in timing analysis (clock buf 1 included but it was removed)




 




 



 



 



 



 



