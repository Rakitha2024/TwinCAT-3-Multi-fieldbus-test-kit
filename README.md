# Revision History

  --------------------------------------------------------------------------
  Rev     Description                                 Date         By
  ------- ------------------------------------------- ------------ ---------
  1.0     Initial release                             19/01/2026   RDA

                                                                   

                                                                   
  --------------------------------------------------------------------------

# Contact persons

  -------------------------------------------------------------------------
  Name              Email                               Company
  ----------------- ----------------------------------- -------------------
  Chaminda          <cserasingh@au.pepperl-fuchs.com>   P+F
  Serasinghe                                            

  Rakitha De Alwis  <R.DeAlwis@beckhoff.com>            Beckhoff
  -------------------------------------------------------------------------

# Introduction

This document contains basic configuration instructions. The PLC code
provided are example code.

# Included items

+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
| No. | Part number                                                                                                                          |                                            |
+=====+======================================================================================================================================+============================================+
|     | [CX5340-0195 / 000453021](https://www.beckhoff.com/en-au/products/ipc/embedded-pcs/cx5300-intel-atom-r-x6/cx5340.html)               | DIN rail Embedded PC,                      |
|     |                                                                                                                                      |                                            |
|     |                                                                                                                                      | Intel Atom x6425RE, 1.9 GHz, 4 cores       |
|     |                                                                                                                                      | (TC3:50), 40 GB CFast, 8GB RAM, 2 x GBit   |
|     |                                                                                                                                      | LAN, 1s UPS, Win 10 IoT Ent 2021 LTSC, 64  |
|     |                                                                                                                                      | bit                                        |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [EL1859](https://www.beckhoff.com/en-au/products/i-o/ethercat-terminals/el-ed1xxx-digital-input/el1859.html)                         | HD EtherCAT Terminal, 8-channel digital    |
|     |                                                                                                                                      | input + 8-channel digital output 24 V DC   |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [EL6022](https://www.beckhoff.com/en-au/products/i-o/ethercat-terminals/el-ed6xxx-communication/el6022.html)                         | 2-channel serial interfaces                |
|     |                                                                                                                                      | RS422/RS485,D-sub connection               |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [EL6751](https://www.beckhoff.com/en-au/products/i-o/ethercat-terminals/el-ed6xxx-communication/el6751.html)                         | CANopen Master Terminal                    |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [EK1122](https://www.beckhoff.com/en-au/products/i-o/ethercat-terminals/ek-ec1xxx-bk1xx0-ethercat-coupler/ek1122.html)               | 2-port EtherCAT Junction (RJ45)            |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [EL9011](https://www.beckhoff.com/en-au/products/i-o/ethercat-terminals/el-ed9xxx-system/el9011.html)                                | Bus end cap                                |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [TC1200-0250](https://www.beckhoff.com/en-au/products/automation/twincat/tcxxxx-twincat-3-base/tc1200.html)                          | TC3 PLC                                    |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [TF6250-0250](https://www.beckhoff.com/en-au/products/automation/twincat/tfxxxx-twincat-3-functions/tf6xxx-connectivity/tf6250.html) | TC3 Modbus TCP                             |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
|     | [TF6255-0250](https://www.beckhoff.com/en-au/products/automation/twincat/tfxxxx-twincat-3-functions/tf6xxx-connectivity/tf6255.html) | TC3 Modbus RTU (Communication via RS485)   |
+-----+--------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+

# Licenses / serial numbers

## Embedded PC

![](media/image1.tmp){width="3.082872922134733in"
height="1.8229166666666667in"}

![A screenshot of a computer AI-generated content may be
incorrect.](media/image2.tmp){width="6.396725721784777in"
height="2.135715223097113in"}

![A screenshot of a phone AI-generated content may be
incorrect.](media/image3.tmp){width="6.386307961504812in"
height="1.7085717410323709in"}

## TwinCAT

**System ID** : C1A15913-491B-37A0-08C0-0055FEFA5329

**License ID** : 01679424

**XAR** : v3.1.4026.19

![](media/image4.tmp){width="6.5in" height="3.911111111111111in"}

# Connections

## IP address 

![](media/image5.tmp){width="7.5in" height="1.9006944444444445in"}

## Default login credentials

  -----------------------------------------------------------------------
  Username      Administrator
  ------------- ---------------------------------------------------------
  Password      1

  -----------------------------------------------------------------------

## TwinCAT ADS (AMS NetID)

TwinCAT XAE uses ADS communication to configure the CX5340

![](media/image6.tmp){width="5.042369860017498in"
height="0.4375612423447069in"}

## Windows remote desktop

RDP can be used with the above-mentioned IP address and the login
credentials.

## Beckhoff Device Manager

Using the Beckhoff Device Manager, an industrial PC can be configured by
remote access with the aid of a web browser. This uses HTTPS and Port
443 (TCP).

Use one of these URLs with the default login credentials.

- <https://192.168.1.12/config>

- <https://BTN-000U4KNV/config>

# Preparation

## TwinCAT installation

Install the latest version of TwinCAT Package Manager (TwinCAT 3.1 Build
4026) available on the Beckhoff homepage. Then use the package manager
to install the latest stable version of TwinCAT 3.1.4026 XAE.

TwinCAT 3 XAE is free to download and use.

## Learning the basics

Watch this getting started video:

<https://beckhoff-au.teachable.com/courses/twincat-3-training-getting-started/lectures/38231220>

Read this quick start section in Beckhoff Infosys

<https://infosys.beckhoff.com/content/1033/ethercatsystem/2584719371.html?id=8536364527568983675>

Please contact Beckhoff support if the links have expired.

# Digital IO

## Wiring

![](media/image7.tmp){width="3.2708333333333335in"
height="1.9425262467191602in"}

## PLC code

Here some Boolean variables are created for the digital IO in the GVL
(Global Variable List).

![](media/image8.tmp){width="6.000837707786527in"
height="3.698432852143482in"}

The simple PLC code flashes channle1 output and the input channel1
increments a counter for every rising edge of the input.

![](media/image9.tmp){width="4.844425853018373in"
height="3.448397856517935in"}

# EtherCAT

P+F Ethernet IO-Link ICE11-8IOL-G60L-V1D set in EtherCAT mode was used.

<https://www.pepperl-fuchs.com/en-au/products-gp25581/119992>.

A P+F read head WCS3B-LS810DS was used as the IO link sensor.
<https://www.pepperl-fuchs.com/en-au/products-gp25581/131722>

## Wiring

![A white electronic device with green and red lines AI-generated
content may be incorrect.](media/image10.tmp){width="7.5in"
height="2.7888888888888888in"}

Ensure the protocol is set to EtherCAT (EC) on rotary switch X100.

![](media/image11.tmp){width="2.8645833333333335in"
height="1.6743383639545057in"}

## Procedure

1.  Download EtherCAT ESI file from the PNF website and save it on the
    "***C:\\Program Files
    (x86)\\Beckhoff\\TwinCAT\\3.1\\Config\\Io\\EtherCAT***" directory on
    the engineering PC (4026 TwinCAT build).

2.  Connect the devices as shown above.

3.  In TwinCAT scan the IO.

4.  The P+F IO link device will be added in the IO tree.

![](media/image12.tmp){width="2.502425634295713in"
height="2.5729166666666665in"}

5.  Configure the PDOs for the read head as shown. The read head has 18
    bytes IN and 1 byte OUT.

The closest to this is 32 In and 4 OUT.

IO-Link Ch.2 to Ch.8 is set as "Deactive" since there is nothing
connected on these ports.

![](media/image13.tmp){width="6.854166666666667in"
height="2.7981496062992126in"}

6.  You should see the PDOs added in the IO tree as shown.

![A screenshot of a computer program AI-generated content may be
incorrect.](media/image14.tmp){width="2.59411198600175in"
height="1.7502438757655292in"}

7.  Link the PDOs to the PLC code as needed.

8.  Activate configuration and run the PLC.

# CANopen

P+F inclination sensor INX360D-F99-B16-V15 was used

<https://www.pepperl-fuchs.com/en-au/products-gp25581/41541#tabBarContent-productDetail-3>
+

## Wiring of EL6751 to P+F sensor

The bus must be terminated at each end with a 120 (or 121) Ohm
terminating resistor to prevent

reflections. This is also necessary even if the cable lengths are very
short.

![](media/image15.tmp){width="7.5in" height="2.410416666666667in"}

## Procedure for adding a CANopen slave in TwinCAT

1.  Download EDS file from the PNF website and save it on the
    "***C:\\Program Files
    (x86)\\Beckhoff\\TwinCAT\\3.1\\Config\\Io\\CANopen***" directory on
    the engineering PC (4026 TwinCAT build).

2.  Connect the sensor to the EL6751 as shown above and power on the
    sensor.

3.  In TwinCAT scan the IO.

4.  When TwinCAT is scanning for boxes, you should see this message.
    Click yes

![](media/image16.png){width="3.2604166666666665in" height="2.0625in"}

5.  Select the correct Baud rate here and click ok. Your CAN Open slave
    will not be detected if the baud rate is incorrect.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image17.tmp){width="2.9483278652668417in"
height="1.9690244969378827in"}

6.  TwinCAT will proceed to scan the CANopen Bus for nodes.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image18.png){width="5.073624234470691in"
height="1.3335192475940507in"}

7.  Once the scanning is complete, click yes to "activate free run" if
    you wish to verify the sensor data is coming through.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image19.png){width="2.1041666666666665in"
height="1.5833333333333333in"}

8.  In the I/O tree you should now see the scanned in sensor under the
    CANopen master. Note the EL6751 EtherCAT terminal will be also
    present in the EtherCAT network.

![](media/image20.tmp){width="4.354166666666667in"
height="3.859870953630796in"}

## Read/write CANopen slave object directory

ADS tab on the CANopen sensor can be used to read and write data of the
slave object directory.

**[Note:]{.underline}** TwinCAT must be in either "Free-run" or "Run"
mode. And EL6751 EtherCAT device must be in "OP" status.

Ensure the correct node ID is set

![](media/image21.tmp){width="6.489583333333333in"
height="2.9683836395450567in"}

In the following examples node ID is read and written

**Object index: 2000 hex**

**Subindex (offset): 00 hex**

Check the slave data sheet for high byte and low byte order for read and
write data.

Read-length must be correct as per datasheet too.

Some parameter changes will require a power cycle, check datasheet.

### Example 1: reading node ID

![](media/image22.tmp){width="7.5in" height="3.2291666666666665in"}

### Example 2: writing node ID

![](media/image23.tmp){width="7.5in" height="3.397222222222222in"}

## EL6751 Diagnostics

A description of all diagnostic features are described in the EL6751
datasheet or the Beckhoff
[Infosys](https://infosys.beckhoff.com/content/1033/el6751/12308676875.html?id=2399216633946018809).

### Diagnostic LEDs

![A screenshot of a computer AI-generated content may be
incorrect.](media/image24.tmp){width="7.5in"
height="6.304166666666666in"}

# Modbus TCP

For this test we can use any free Modbus testers. The free tool used in
this example is ClassicDIY ModbusTool available from GitHub.

<https://github.com/ClassicDIY/ModbusTool>

## Wiring

![](media/image25.tmp){width="7.5in" height="2.5506944444444444in"}

## Procedure -- TwinCAT as the Modbus TCP server (Slave)

1.  Turn off firewalls on both engineering PC and the CX5340 temporarily
    for this test.

![](media/image26.tmp){width="5.330918635170604in"
height="2.5208333333333335in"}

2.  Check if TF6250 \| Modbus TCP runtime is installed on the CX5340.

![](media/image27.tmp){width="6.60490813648294in"
height="2.5416666666666665in"}

3.  Check if TcModbusSrv service is running on the CX5340.

![](media/image28.tmp){width="6.895833333333333in"
height="1.8963538932633421in"}

4.  Check if the CX5340 has a valid Modbus TCP license.

![](media/image29.tmp){width="5.177806211723534in"
height="0.28128937007874016in"}

5.  On the CX5340, run the Modbus configurator found in "***C:\\Program
    Files
    (x86)\\Beckhoff\\TwinCAT\\Functions\\TF6250-Modbus-TCP\\Win32\\Server***"

![](media/image30.tmp){width="6.572916666666667in"
height="1.6182764654418198in"}

6.  Set the IP address as desired, default TCP port for Modbus TCP
    is 502. Click "Set configuration" and click "Yes" to stopping
    TwinCAT.

![](media/image31.tmp){width="4.927083333333333in"
height="2.81958552055993in"}

7.  The TcModbusSrv service should be still running. If its not, double
    check the setting in the previous step.

8.  On the TwinCAT project create a global variable list called GVL and
    declare the following global variables.

+--------------------------------------------------------------------+
| VAR_GLOBAL                                                         |
|                                                                    |
| mb_Input_Coils : ARRAY \[0..255\] OF BOOL;                         |
|                                                                    |
| mb_Output_Coils : ARRAY \[0..255\] OF BOOL;                        |
|                                                                    |
| mb_Input_Registers : ARRAY \[0..255\] OF WORD;                     |
|                                                                    |
| mb_Output_Registers : ARRAY \[0..255\] OF WORD;                    |
|                                                                    |
| END_VAR                                                            |
+====================================================================+

9.  Activate the TwinCAT project and run the PLC.

10. Run the Modbus master test tool on the engineering PC.

11. Set the IP address and port number set in the CX5340 and click
    connect.

12. The address range to read/write is dependent on what you have set
    using TwinCAT Modbus configurator. Since we used the default range
    it is 0x8000 to 0x80FF (32768 to 33023)

Note on some Modbus masters you may need to offset the address by 1.

13. Shown below is a result of setting the input registers in TwinCAT
    and reading the data from the test tool.

![](media/image32.tmp){width="6.864583333333333in"
height="2.728672353455818in"}

14. Turn back the firewalls on after the test is complete.

## Procedure - TwinCAT as Modbus TCP Client (Master) 

The following Modbus functions are available in TwinCAT.

  --------------------------------------------------------------------------------------------------------------------------------------------------------
  **Modbus TCP function** **Function code**       **PLC block**
  ----------------------- ----------------------- --------------------------------------------------------------------------------------------------------
  Read Coils              1                       [FB_MBReadCoils](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192752395.html)

  Read Inputs             2                       [FB_MBReadInputs](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192753931.html)

  Read Registers          3                       [FB_MBReadRegs](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192755467.html)

  Read Input Registers    4                       [FB_MBReadInputRegs](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192757003.html)

  Write Single Coil       5                       [FB_MBWriteSingleCoil](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192758539.html)

  Write Single Register   6                       [FB_MBWriteSingleReg](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192760075.html)

  Write Multiple Coils    15                      [FB_MBWriteCoils](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192761611.html)

  Write Multiple          16                      [FB_MBWriteRegs](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192763147.html)
  Registers                                       

  Read/Write Multiple     23                      [FB_MBReadWriteRegs](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192764683.html)
  Registers                                       

  Diagnostic              8                       [FB_MBDiagnose](https://infosys.beckhoff.com/content/1033/tf6250_tc3_modbus_tcp/192766219.html)
  --------------------------------------------------------------------------------------------------------------------------------------------------------

## 

1.  Follow steps 1 to 7 in the Modbus server (slave) setup instructions.
    The modbus GVLs are not required for this test.

2.  In the TwinCAT project add the Tc2_ModbusSrv library to the TwinCAT
    project.

![A screenshot of a computer AI-generated content may be
incorrect.](media/image33.tmp){width="6.96875in"
height="2.0441666666666665in"}

3.  For this test "FB_MBReadRegs" and "FB_MBWriteRegs" are used from the
    PLC library that was just added. Sample is shown below.

![](media/image34.tmp){width="6.084181977252843in"
height="2.0419520997375327in"}

![](media/image35.tmp){width="7.260416666666667in"
height="3.524663167104112in"}

![A screenshot of a computer code AI-generated content may be
incorrect.](media/image36.tmp){width="6.61550634295713in"
height="4.1047397200349955in"}

4.  Run the Modbus Slave tool on the Engineering PC.

5.  Activate the TwinCAT project and run the PLC.

6.  Execute the read and write commands in TwinCAT.

7.  Shown below is the result of writing the data to the Modbus Slave.

![](media/image37.tmp){width="6.912915573053368in" height="3.925in"}

## Default Modbus mapping 

The server maps the individual ADS areas and enables the access to the
physical process image and maps the PLC data area.

The mapping can be adjusted by the TwinCAT Modbus TCP Configurator.

![](media/image38.tmp){width="6.782195975503062in"
height="5.729966097987751in"}
