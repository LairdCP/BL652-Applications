BL652 smartBASIC-Applications
=============================

A repository for smartBASIC applications that run on the Laird BL652 (Released under the ISC License).

BL652 Overview
------------
Laird’s BL652 contains the latest generation silicon with Bluetooth Smart v4.2 capabilities and groundbreaking ultra-low power performance. Building on the expertise of the BL600 Series, the BL652’s smaller form factor, class-leading Nordic nRF52 silicon, optimized low power schemes and smartBASIC programming language provide a secure, stable, hostless Bluetooth environment. The BL652 introduces Bluetooth v4.2 and NFC, bringing industrial security and feature expansion to Laird’s proven Bluetooth Low Energy modules. In addition, the BL652 contains Bluetooth 5 ready hardware, pending the release of the Bluetooth 5 specification. Let Laird’s innovative BL652 series and decades of expertise in Bluetooth module design speed your product to market. For more information, visit the [`BL652 product page`](https://www.lairdconnect.com/wireless-modules/bluetooth-modules/bluetooth-5-modules/bl652-series-bluetooth-v5-nfc).

UwTerminalX
-----------
UwTerminalX is a cross-platform utility for communicating and downloading applications onto the BL652. The latest releases are available at https://github.com/LairdCP/UwTerminalX/releases

BL652 Quick Start Demonstration
-------------------------------
Get started in minutes with the [`DVK-BL652 Quick Start`](https://www.lairdconnect.com/bl652-quick-start) Guide!

Older firmwares
-------------------------------
The files in this repository are designed for use with the latest BL652 firmware, which at the time of writing is 28.7.3.0. For applications targeting older firmware, please check the [Releases tab](https://github.com/LairdCP/BL652-Applications/releases)

Best Practices for Writing smartBASIC Applications
-------------------------------
1. Always check the resultcode returned from an API function. Non-zero result codes usually indicate that the operation has not been successful.
2. smartBASIC is event driven; ensure that the application is written in an event-driven manner. Starting with a state-machine or a flowchart is highly recommended.
3. Minimize the use of WAITEVENTs; ideally, WAITEVENT should be used only once at the end of the program to ensure the app is simple and robust.
4. Minimize radio usage when possible to save power.
5. Use comments wherever possible to ensure that the appliaction can be read and understood.
6. Only hard-code when necessary. When hard-coding, use #defines to give meaning to the constants used.
7. Follow the smartBASIC app  template found [here](https://github.com/LairdCP/BL652-Applications/blob/master/Applications/ttt.template.sb).

Notes
-------------------------------
Please note that for simplicity reasons, some sample apps have been written without important features such as error handling or result code checking. However, when writing your applications, please ensure that result codes returned from the API functions are always checked to ensure that your applications are robust and bug-free.
