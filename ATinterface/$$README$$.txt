--------
Jul 2018
--------

This folder contains smartBASIC applications that when loaded in a BL65x 
(BL652 or BL654 series) module will expose an AT interface, that will allow
AT commands to be sent over the uart interface (@ 115200,N,8,1) to make
it do various BLE, NFC or GPIO actions.

The main functionality is being able to create a virtual serial port profile
connection, over BLE, that will allow data to be exchanged with a peer as 
if there was a wired uart connection.

     ==============================================================
     The minimum firmware version that you will need is as follows:
     
                             BL652 : v28.8.4.0
                             BL654 : v29.1.1.0
          
      The command 'AT I 3<cr>' will return the version number from
      the module
     ==============================================================

The folder contains many smartBASIC source code files which end with the
extension ".sb"

For BL652, start testing with file "$autorun$.AT.interface.BL652._.sb"
For BL654, start testing with file "$autorun$.AT.interface.BL654._.sb"

 ------------------------------------------------------------------------
   The application files have filenames with the following pattern ..
   
     $autorun$.AT.interface.PPP.FFF.FFF.sb
     
   Where PPP is the platform and can be one of 'BL652' or 'BL654'
   FFF can be one or more of '_', 'nfc' , 'lpuart'
   
     'nfc'    means AT commands to interface with NFC are exposed
     'lpuart' means the uart can be operated in low power mode

     '_' means core functionality and will always be present even if that
         string is not present in the filename.
 ------------------------------------------------------------------------

An application is downloaded to a module using a free Laird utility called
UwTerminalX. You can download the utility from ...

    https://github.com/LairdCP/UwTerminalX/releases

Only files that start with "$autorun$" are stand alone.
  DO NOT SELECT ANY FILES TO DOWNLOAD THAT DOES NOT START WITH "$autorun$

All other files are library files which are #included in the stand alone
files and if you try to download them to a module you will get one or
more download errors. To make that clear, all library files start with
a filename "$LIB$."

When an app is downloaded it will be saved in the module's file system as 
a file called "$autorun$" which means it will automatically run when the
module is reset or powered up.

QUICK START GUIDE
Once an application is downloaded using UwTerminalX, power cycle the module.
Then send the command ATI0<cr> where <cr> is the enter key and you will 
see the module respond with the name of the module and then an "OK" response.

DOCUMENTATION
There are two main documents that are relevant for this application which
can be found at

  https://www.lairdtech.com/products/bl654-ble-thread-nfc-modules
  or
  https://www.lairdtech.com/products/bl652-ble-module
  
   (1) BL65x AT Interface Application User Guide
   (2) AT Interface Quick Start Guide
   
   
