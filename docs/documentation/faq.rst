FAQ
================

In this section you can find frequently asked questions related to LimeSDR-Mini v2.2 board

I cannot connect board to LimeSuite GUI. 
---------------------------------------- 

* Try different USB3.0 cable, if possible connect it directly to USB3.0 port.

* Check FTDI configuration. Download `FT600ChipConfigurationProgUtility_v1.3.0.2.zip <https://www.ftdichip.com/old2020/Support/Utilities/FT600ChipConfigurationProgUtility_v1.3.0.2.zip>`__ , connect board and hit "Read Configuration" (make sure that LimeSuite GUI is closed and is not using the board). You should see following settings:

    .. figure:: images/LimeSDR-Mini_v2.2_FAQ_FTDI_Config.png
        :width: 600
  
    Figure 1: FTDI configuration

    Ignore "Serial number" field. If any other setting are incorrect fix them and hit "Write Configuration". Close utility and try to connect board to LimeSuite GUI. 

* Reprogram FPGA FLASH memory using JTAG with latest GW `lms7_trx_impl1_dualboot.mcs <https://github.com/myriadrf/LimeSDR-Mini-v2_GW/blob/main/LimeSDR-Mini_bitstreams/lms7_trx_impl1_dualboot.mcs>`__. Follow `FPGA FLASH programming <https://limesdr-mini.myriadrf.org/documentation/jtag-programming#fpga-programming-using-lattice-diamond-software>`__ procedure.

* If FLASH programming was successful you should see blinking LED1 after reapplying power to board. 

* If after fixing FTDI configuration and reprogramming FPGA FLASH you still cannot connect to LimeSuite GUI this would indicate problems with software setup that you are using or board is damaged. 

