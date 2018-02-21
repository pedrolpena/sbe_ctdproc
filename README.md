# sbe_ctdproc
A set of scripts to setup directories and scripts to do some basic CTD processing under Windows or *nix systems using wine.
This has successfully been tested on Windows linux and OSX.

Requirements
============

The SeaBird processing software installed in one of the default locations.<br>

If using wine.<br>
$HOME/.wine/drive_c/Program Files (x86)/Sea-Bird<br>
$HOME/user/.wine/drive_c/Program Files/Sea-Bird<br>

If using Windows<br>
C:\Program Files (x86)\Sea-Bird<br>
C:\Program Files\Sea-Bird<br>

In this example we'll prepare an environment to process CTD station 004 from cruise AB1705.<br>

1) Open a terminal and navigate to the install scripts.<br>
You should see two files.<br>
-init_ctd_proc<br>
-init_ctd_proc.bat<br>
   
On Linux/OSX<br>
chmod +x ./init_ctd_proc<br>
./init_ctd_proc AB1705 $HOME/data<br>
   
This will install the processing script with it's configuration file and PSA files.<br>
Copy the included raw data files to $HOME/data/ctd_proc/raw_data and navigate to <br>
   
$HOME/data/ctd_proc/batch_files using the terminal.<br>
   
to process station 004 type<br>
./process_ctd 004<br>
   
The SBEBatch should run and deposit the processed files in<br>
   
$HOME/data/ctd_proc/1db/proc_data<br>
-AB1705_004.cnv<br                  />
-AB1705_004.ros<br                  />
-dAB1705_004.cnv<br                 />
-uAB1705_004.cnv<br                 />
   
$HOME/data/ctd_proc/1hz/proc_data<br>
-AB1705_004.cnv<br>
  

