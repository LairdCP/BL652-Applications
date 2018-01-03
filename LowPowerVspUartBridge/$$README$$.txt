********************
May 2017
********************
v1.10
The smartBASIC application in "$autorun$.low.power.vsp.uart.bridge.sb" implements
the state machine depicted in "LowPowerVspUartBridge.flo" and provides a bridge
between the uart and Laird's VSP profile.
In addition it is designed for low power operation in that when there is no
activity, the uart is closed so that power consumption is even lower and 
if there is any airside or uart activity it is reopened.

  Note: the state machine diagram can be viewed using the free viewer 
        that can be downloaded from https://www.rff.com/viewer.php

The user is free to fine tune the application by changing any of the #defines
in the the application.

In addition, the behaviour can be customised by providing the content
of various callbacks that are provied in "file custom.low.power.vsp.uart.bridge.sb"
which is #included in the main file

MECHANISM TO REOPEN THE UART
--------
Option 1
--------
By default using the #defines UART_REOPEN_SIONUM and UART_REOPEN_STATE_CHANGE
the mechanism to reopen the uart is for the uart host to either send a sacrificial
character or a uart_break.
               ^^^^^^^^^^
It is recommended that if a sacrificial character is sent then it be one of the
following values :- 
  0x00, 0x80, 0xC0, 0xE0, 0xF0, 0xF8, 0xFC, 0xFE
Because it will result in a single low to high transition and so NOT result
in any extraneous random data from being received.

--------
Option 2
--------
Change UART_REOPEN_SIONUM to the pin number for the UART_CTS line and the 
value for UART_REOPEN_STATE_CHANGE to UART_REOPEN_TRANSITION_HI_to_LO.
Then the uart host can deassert and reassert its RTS output line to force
the module to open the uart.
