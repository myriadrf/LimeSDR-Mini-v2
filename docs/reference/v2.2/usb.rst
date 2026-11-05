USB 3.0 Controller
##################

Software controls LimeSDR Mini board via the USB 3.0 controller (`FTDI USB 3.0 to FIFO interface bridge chip FT601 <https://ftdichip.com/products/ft600q-b/>`_). The controller signals description showed below:

* FT_D[31:0] – FTDI 32-bit data interface is connected to FPGA.
* FT_TXEn, FT_RXFn, FT_SIWUn, FT_WRn, FT_RDn, FT_OEn, FT_BE[3:0] – FTDI interface control signals.
* FT_CLK – FTDI interface clock. Clock from FTDI is fed to FPGA.

More information about USB 3.0 controller (FTDI) pins, schematic signal names, FPGA interconnections and I/O standards is given in Table 7.

.. list-table:: Table 7. USB 3.0 controller interface
   :header-rows: 1
   :stub-columns: 1

   * - Chip pin (IC6)
     - Chip reference (IC6)
     - Schematic signal name
     - FPGA pin
     - I/O standard
     - Comment
   * - 40
     - DATA_0
     - FT_D0
     - A13
     - 3.3V
     -
   * - 41
     - DATA_1
     - FT_D1
     - B12
     - 3.3V
     -
   * - 42
     - DATA_2
     - FT_D2
     - B15
     - 3.3V
     -
   * - 43
     - DATA_3
     - FT_D3
     - C12
     - 3.3V
     -
   * - 44
     - DATA_4
     - FT_D4
     - A16
     - 3.3V
     -
   * - 45
     - DATA_5
     - FT_D5
     - A12
     - 3.3V
     -
   * - 46
     - DATA_6
     - FT_D6
     - D18
     - 3.3V
     -
   * - 47
     - DATA_7
     - FT_D7
     - B17
     - 3.3V
     -
   * - 50
     - DATA_8
     - FT_D8
     - F15
     - 3.3V
     -
   * - 51
     - DATA_9
     - FT_D9
     - D16
     - 3.3V
     -
   * - 52
     - DATA_10
     - FT_D10
     - D15
     - 3.3V
     -
   * - 53
     - DATA_11
     - FT_D11
     - C13
     - 3.3V
     -
   * - 54
     - DATA_12
     - FT_D12
     - H18
     - 3.3V
     -
   * - 55
     - DATA_13
     - FT_D13
     - B13
     - 3.3V
     -
   * - 56
     - DATA_14
     - FT_D14
     - J18
     - 3.3V
     -
   * - 57
     - DATA_15
     - FT_D15
     - A15
     - 3.3V
     -
   * - 60
     - DATA_16
     - FT_D16
     - B18
     - 3.3V
     -
   * - 61
     - DATA_17
     - FT_D17
     - C18
     - 3.3V
     -
   * - 62
     - DATA_18
     - FT_D18
     - A17
     - 3.3V
     -
   * - 63
     - DATA_19
     - FT_D19
     - K18
     - 3.3V
     -
   * - 64
     - DATA_20
     - FT_D20
     - C15
     - 3.3V
     -
   * - 65
     - DATA_21
     - FT_D21
     - L18
     - 3.3V
     -
   * - 66
     - DATA_22
     - FT_D22
     - F18
     - 3.3V
     -
   * - 67
     - DATA_23
     - FT_D23
     - C16
     - 3.3V
     -
   * - 69
     - DATA_24
     - FT_D24
     - G16
     - 3.3V
     -
   * - 70
     - DATA_25
     - FT_D25
     - D13
     - 3.3V
     -
   * - 71
     - DATA_26
     - FT_D26
     - G18
     - 3.3V
     -
   * - 72
     - DATA_27
     - FT_D27
     - F16
     - 3.3V
     -
   * - 73
     - DATA_28
     - FT_D28
     - C17
     - 3.3V
     -
   * - 74
     - DATA_29
     - FT_D29
     - F17
     - 3.3V
     -
   * - 75
     - DATA_30
     - FT_D30
     - K15
     - 3.3V
     -
   * - 76
     - DATA_31
     - FT_D31
     - K17
     - 3.3V
     -
   * - 58
     - CLK
     - FT_CLK
     - D17
     - 3.3V
     -
   * - 4
     - BE_0
     - FT_BE0
     - L15
     - 3.3V
     -
   * - 5
     - BE_1
     - FT_BE1
     - J17
     - 3.3V
     -
   * - 6
     - BE_2
     - FT_BE2
     - K16
     - 3.3V
     -
   * - 7
     - BE_3
     - FT_BE3
     - H17
     - 3.3V
     -
   * - 8
     - TXE_N
     - FT_TXEn
     - M16
     - 3.3V
     -
   * - 9
     - RXF_N
     - FT_RXFn
     - H16
     - 3.3V
     -
   * - 10
     - SIWU_N
     - FT_SIWUn
     -
     - 3.3V
     - 10k pull up
   * - 11
     - WR_N
     - FT_WRn
     - J16
     - 3.3V
     -
   * - 12
     - RD_N
     - FT_RDn
     - H15
     - 3.3V
     -
   * - 13
     - OE_N
     - FT_OEn
     - L16
     - 3.3V
     -
   * - 15
     - RESET_N
     - FT_RESETn
     - M17
     - 3.3V
     -
   * - 16
     - WAKEP_N
     - FT_WAKEUPn
     - G15
     - 3.3V
     -