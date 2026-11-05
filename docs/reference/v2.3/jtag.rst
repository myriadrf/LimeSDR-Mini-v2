JTAG
####

JTAG connector J5 is used to debug the FPGA design and to load the bitstream into the FPGA and/or flash memory. It is located on the board edge and attaches to the programmer using a 7-pin, 0.1” pitch header. J5 is not fitted by default. JTAG connector pins, schematic signal names, FPGA interconnections and I/O standards are listed in Table 14.

.. list-table:: Table 14. JTAG connector J5 pins
  :header-rows: 1
  :stub-columns: 1

  * - Connector pin
    - Schematic signal name
    - FPGA pin
    - I/O standard
    - Comment
  * - 1
    - GND
    -
    -
    - Ground
  * - 2
    - TCK
    - U13
    - 3.3 V
    - Test Clock
  * - 3
    - TDO
    - V14
    - 3.3 V
    - Test Data Out
  * - 4
    - TMS
    - V13
    - 3.3 V
    - Test Mode Select
  * - 5
    - TDI
    - T13
    - 3.3 V
    - Test Data In
  * - 6
    - VCC3P3
    -
    -
    - Power (3.3 V)
  * - 7
    - VCC5P0
    -
    -
    - Power (5.0 V)