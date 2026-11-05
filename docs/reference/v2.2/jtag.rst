JTAG
####

To debug FPGA design, flash bitstream to FPGA and/or Flash memory JTAG J5 connector is used. It is located on the PCB top side and attaches to the programmer using 7-pin, 0.1” spaced JTAG connector. JTAG connector pins, schematic signal names, FPGA interconnections and I/O standards are listed in Table 12.

.. list-table:: Table 12. JTAG connector X9 pins
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
    - 3.3V
    - Test Clock
  * - 3
    - TDO
    - V14
    - 3.3V
    - Test Data Out
  * - 4
    - TMS
    - V13
    - 3.3V
    - Test Mode Select
  * - 5
    - TDI
    - T13
    - 3.3V
    - Test Data In
  * - 6
    - VCC3P3
    -
    -
    - Power (3.3V)
  * - 7
    - VCC5P0
    -
    -
    - Power (5.0V)