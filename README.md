# sbe_ctdproc
A set of scripts to setup directories and scripts to do some basic CTD processing under Windows or *nix systems using wine.
This has successfully been tested on Windows linux and OSX.

Contents
========
Included are two scripts to initialize a ctd processing environment and a folder with<br>
raw data files for station 004 of a Western Boundry Time Series(WBTS) cruise<br>
carried out in May of 2017.<br>

-init_ctd_proc       A BASH script.<br>
-init_ctd_proc.bat   A BATCH script<br>


raw_data<br>

-ab1705_004.bl         Bottle trip file<br>
-ab1705_004.hdr        Header file<br>
-ab1705_004.hex        Raw hex data file<br>
-ab1705_004.mrk        Markscan file<br>
-AB1705_004.XMLCON     Configuration file<br>



Requirements
============

The SeaBird processing software installed in one of the default locations.<br>


If using wine.<br>
$HOME/.wine/drive_c/Program Files (x86)/Sea-Bird<br>
$HOME/user/.wine/drive_c/Program Files/Sea-Bird<br>

If using Windows<br>
C:\Program Files (x86)\Sea-Bird<br>
C:\Program Files\Sea-Bird<br>

These scripts were written to process files that were created with the version of SeaSave that creates<br>
configuration files with the XMLCON extension. I think SeaBird Began using the XMLCON file with version 7.<br>
The scripts also require that the raw data files be created with the following file naming convention.<br>

CRUISE_ID_nnn<br>

CRUISE_ID is the cruise designation and nnn is the three digit station number. The two must be seperated by an underscore.<br> 

Obviously all this can be modified to suite your needs, so please do so.<br>
You can  modify the actual initilization script so that all cruises you initialize have your modified parameters or you<r>
can modify the config and process_ctd files after initializing a cruise.<br>
   




Example
=======

In this example we'll prepare an environment to process CTD station 004 from cruise AB1705.<br>

1) Open a terminal and navigate to the install scripts.<br>
You should see two files.<br>
-init_ctd_proc<br>
-init_ctd_proc.bat<br>
   
On linux/OSX<br>
chmod +x ./init_ctd_proc<br>
./init_ctd_proc AB1705 $HOME/data<br>
   
This will install the processing script with it's configuration file and PSA files.<br>
Copy the included raw data files to $HOME/data/ctd_proc/raw_data and navigate to <br>
   
$HOME/data/ctd_proc/batch_files using the terminal.<br>
   
to process station 004 type<br>
./process_ctd 004<br>
   
The SBEBatch should run and deposit the processed files in<br>
   
$HOME/data/ctd_proc/1db/proc_data<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.cnv<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.ros<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-dAB1705_004.cnv<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-uAB1705_004.cnv<br>
   
$HOME/data/ctd_proc/1hz/proc_data<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.cnv<br>
  
On Windows<br>

1) Open a terminal and navigate to the install scripts.<br>
You should see two files.<br>
-init_ctd_proc<br>
-init_ctd_proc.bat<br>

init_ctd_proc AB1705 %ALLUSERSPROFILE%\Documents\data

This will install the processing script with it's configuration file and PSA files.<br>
Copy the included raw data files to %ALLUSERSPROFILE%\Documents\data\ctd_proc\raw_data and navigate to <br>

%ALLUSERSPROFILE%\Documents\data\ctd_proc\batch_files using the terminal.<br>
   
to process station 004 type<br>
process_ctd 004<br>

The SBEBatch should run and deposit the processed files in<br>
   
%ALLUSERSPROFILE%\Documents\data\ctd_proc\1db\proc_data<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.cnv<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.ros<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-dAB1705_004.cnv<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-uAB1705_004.cnv<br>
   
%ALLUSERSPROFILE%\Documents\data\ctd_proc\1hz\proc_data<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-AB1705_004.cnv<br>


