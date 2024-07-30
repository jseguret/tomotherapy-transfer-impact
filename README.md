# Tomotherapy transfer impact

This python script assesses the supplementary dose induced by short Leaf Closing Times (LCTs) created during a plan transfer. This phenomenon only affects a few locations, but the dose error can be up to 2.5-3% if the initial distribution has a high percentage of Leaf Opening Times (LOTs) stricly equal to Projection Time (PT). Accuray is working on a patch to discard short LCTs during transfer (as it is already done during End Of Planning process when optimizing a plan). This script can be used until the patch is released. It calculates the amount of undiscarded short LCTs, and sums their supplementary opening times, to get the relative value of additional dose. It supposes a homogeneous distribution of short LCTs through the plan, which is not the case for complex PTV locations (e.g. breast, H&N...), but which is a valid approximation for simple PTV locations (e.g. pelvis, bone metastasis...). This code only works with RT-PLAN files generated by Accuray Precision (Accuray Inc., Madison, Wisconsin, USA).  
 


## Installation

You can directly clone the whole repository to your computer. It contains: 

	- the python project file "Transfer_impact.py" (all functions and main in a unique .py file)
	- a "setup.py" file which was used to compile the project and create an executable, using the cx_Freeze lib (https://github.com/marcelotduarte/cx_Freeze)
	- a "build\exe.win-amd64-3.12" directory containing all the files created during compilation with cx_Freeze. This folder includes the final standalone "Transfer_impact.exe", which you can launch without having to install python on your computer. 

## Usage

To use the script and estimate dose errors due to short LCTs, follow this steps : 

### Step 1
Export RT-PLAN files from Precision and store them in a folder. This folder must not contain any subfolder or non RT-PLAN files. 

### Step 2 
Launch the python project: 

	- either by directly lauching the executable file 
	- either by lauching the Transfer_impact.py file if you have python installed with pydicom, openpyxl, tkinter, numpy, os, and sys. 

### Step 3 
Fill in the input folder path as asked by user interface. The scripts plots the supplementary dose estimations and asks for an output folder path and a file name. This output file is a .xlsx which contains the same data as the plot. 


## Contributing and Information

Feel free to contact me (seguret.julien@iuct_oncopole.fr) for further information. Feel free to contribute to the project if you find any improvable points. 

