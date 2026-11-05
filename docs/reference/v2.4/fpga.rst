FPGA
####

LimeSDR Mini board features a Lattice ECP5 FPGA LFE5U-45F-xxMG285 (IC7). The board is also footprint and pin compatible with LFE5U-25F and LFE5U-85F FPGAs. The FPGA connects the host (via the USB 3.0 controller) to the LMS7002M RF transceiver, and also controls the RF network, clock network, fan and peripheral devices. FPGA interfaces are listed in Table 2.

.. list-table:: Table 2. FPGA interfaces
   :header-rows: 1

   * - Interface
     - Connected to
     - Details
   * - 32-bit FIFO
     - USB 3.0 controller (IC8)
     - :doc:`usb`
   * - LimeLight, SPI
     - LMS7002M RF transceiver (IC1)
     - :doc:`digital`
   * - Configuration SPI
     - Configuration flash (IC15)
     - `Configuration`_
   * - SPI
     - VCTCXO DAC (IC11)
     - :doc:`peripheralinterfaces`
   * - I\ :sup:`2`\ C
     - Temperature sensor (IC10), EEPROM (IC12, not fitted)
     - :doc:`peripheralinterfaces`
   * - RF control
     - RF switches (IC3, IC4), loopback attenuator
     - :doc:`rfcontrol`
   * - Clock
     - Clock buffer (IC9), analogue switch (IC20)
     - :doc:`clock`
   * - GPIO, LEDs
     - J3, J4 (not fitted), LED1–LED3
     - :doc:`gpio`, :doc:`leds`
   * - Fan control
     - Fan connector (J9, not fitted)
     - :doc:`tempsensor`
   * - JTAG
     - J5 (not fitted)
     - :doc:`jtag`

FPGA I/O banks 0, 1, 6, 7 and 8 are powered from VCC3P3 (3.3 V). Banks 2 and 3, which connect to the LMS7002M RF transceiver, are powered from VDIO_LMS_FPGA. By default VDIO_LMS_FPGA is 2.5 V (R98 fitted), and it can be changed to 3.3 V by fitting R101 instead.

Configuration
=============

The FPGA is configured in SPI master mode (CFG[2:0] = 010) from the 128 Mb SPI configuration flash IC15 (W25Q128JVSIQ). Its interface pins are listed in :doc:`peripheralinterfaces`. For flash programming, see :doc:`/user/flashing`.

Configuration control signals:

* PROGRAMN (T15) – pulled up to VCC3P3 by R48 (4.7 k\ |Omega|).
* INITN (V16) – pulled up to VCC3P3 by R47 (4.7 k\ |Omega|).
* DONE (U15) – not connected.

The FPGA can also be configured and debugged via JTAG connector J5 (not fitted by default), see :doc:`jtag`.

Version Straps
==============

Board hardware and BOM versions are set by straps connected to FPGA inputs, so they can be read by the gateware. Unconnected inputs are read as 1 using the FPGA internal pull-up. Version straps are listed in Table 3.

.. list-table:: Table 3. FPGA version straps
   :header-rows: 1

   * - Schematic signal name
     - FPGA pin
     - Connection
     - Value
   * - HW_VER0
     - D4
     - Not connected
     - 1
   * - HW_VER1
     - M2
     - Not connected
     - 1
   * - HW_VER2
     - N4
     - Not connected
     - 1
   * - HW_VER3
     - J3
     - GND
     - 0
   * - BOM_VER0
     - N1
     - GND via R44 (0 |Omega|)
     - 0
   * - BOM_VER1
     - M1
     - GND via R45 (0 |Omega|)
     - 0
   * - BOM_VER2
     - N2
     - GND via R46 (0 |Omega|)
     - 0

On LimeSDR Mini v2.4, HW_VER = 7 (0111) and BOM_VER = 0 (000).
