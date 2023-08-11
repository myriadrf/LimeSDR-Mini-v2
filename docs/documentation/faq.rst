FAQ
================

In this section you can find frequently asked questions related to LimeSDR-Mini v2.2 board

It is not working, please help.
--------------------------------------

Avoid vague explanation of encountered issues. Try to provide as many relevant information as you can, for e.g:

* What hardware are you using? Write exact board name and version as you see on silkscreen. 
* What software and version are you using?
* What gateware version are you using? 
* Was it working before? 
* Did you modified hardware, software or gateware? If so explain your modifications. 
* Provide steps to reproduce the issue. 


Where can I ask for help or report issues?
------------------------------------------

* First read this FAQ and go trough available documents in `https://limesdr-mini.myriadrf.org/ <https://limesdr-mini.myriadrf.org/>`__
* Try to search `https://discourse.myriadrf.org/ <https://discourse.myriadrf.org/>`__ maybe someone already had similar issue, if not - post your question there.
* For HW related issues check `LimeSDR-Mini-v2 <https://github.com/myriadrf/LimeSDR-Mini-v2/issues>`__ GitHub repository. 
* For GW related issues check `LimeSDR-Mini-v2_GW <https://github.com/myriadrf/LimeSDR-Mini-v2_GW/issues>`__ GitHub repository. 
* For SW related issues check `LimeSuite <https://github.com/myriadrf/LimeSuite/issues>`__ GitHub repository

How to configure FT601 USB3.0 chip?
-----------------------------------
* Download `FT600ChipConfigurationProgUtility_v1.3.0.2.zip <https://www.ftdichip.com/old2020/Support/Utilities/FT600ChipConfigurationProgUtility_v1.3.0.2.zip>`__ , connect board and hit "Read Configuration" (make sure that any other software is closed and is not using the board). You should see following settings:

    .. figure:: images/LimeSDR-Mini_v2.2_FAQ_FTDI_Config.png
        :width: 600
  
    Figure 1: FTDI configuration

    Ignore "Serial number" field. If any other setting are incorrect fix them and hit "Write Configuration". Close utility and try to connect board to LimeSuite GUI. 

I cannot connect board to LimeSuite GUI, no LEDs are blinking how can I recover my board?  
----------------------------------------------------------------------------------------- 

* Try different USB3.0 cable, if possible connect it directly to USB3.0 port.

* Check FT601 chip configuration, see `How to configure FT601 USB3.0 chip?`_ .

* Reprogram FPGA FLASH memory using JTAG with latest GW `lms7_trx_impl1_dualboot.mcs <https://github.com/myriadrf/LimeSDR-Mini-v2_GW/blob/main/LimeSDR-Mini_bitstreams/lms7_trx_impl1_dualboot.mcs>`__ file. Check `JTAG programming <https://limesdr-mini.myriadrf.org/documentation/jtag-programming#>`__ page and  follow `FPGA FLASH programming <https://limesdr-mini.myriadrf.org/documentation/jtag-programming#fpga-programming-using-lattice-diamond-software>`__ procedure.

* If FLASH programming was successful you should see blinking LED1 after reapplying power to board. 

* If after fixing FTDI configuration and reprogramming FPGA FLASH you still cannot connect to LimeSuite GUI this would indicate problems with software setup that you are using or board is damaged. 

