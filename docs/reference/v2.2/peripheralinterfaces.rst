Peripheral Interfaces
#####################

FPGA_SPI pins, schematic signal names, FPGA interconnections and I/O standards/levels are shown in Table 11.

.. list-table:: Table 11. FPGA_SPI interface pins
  :header-rows: 1

  * - Schematic signal name
    - FPGA pin
    - I/O standard
    - Comment
  * - FPGA_SPI_SCLK
    - M3
    - 2.5 V/3.3 V
    - Serial Clock (FPGA output)
  * - FPGA_SPI_MOSI
    - L3
    - 2.5 V/3.3 V
    - Data (FPGA output)
  * - FPGA_SPI_MISO
    - K3
    - 2.5 V/3.3 V
    - Data (FPGA input)
  * - FPGA_SPI_LMS_SS
    - N3
    - 2.5 V/3.3 V
    - LMS7002M (IC1) SPI slave select (FPGA output)
  * - FPGA_SPI_DAC_SS
    - L4
    - 2.5 V/3.3 V
    - IC11 SPI slave select (FPGA output)

FPGA_CFG_SPI pins, schematic signal names, FPGA interconnections and I/O standards are shown in Table 12.

.. list-table:: Table 12. FPGA_CFG_SPI interface pins
  :header-rows: 1

  * - Schematic signal name
    - FPGA pin
    - I/O standard
    - Comment
  * - FPGA_CFG_SPI_SCLK
    - U16
    - 3.3 V
    - Serial Clock (FPGA output)
  * - FPGA_CFG_SPI_MOSI
    - U18
    - 3.3 V
    -
  * - FPGA_CFG_SPI_MISO
    - T18
    - 3.3 V
    -
  * - FPGA_CFG_SPI_SS
    - U17
    - 3.3 V
    - IC15 SPI slave select (FPGA output)

FPGA_I2C (temperature sensor and EEPROM) interface slave devices and related information are given in Table 13.

.. list-table:: Table 13. FPGA_I2C interface pins
  :header-rows: 1
  
  * - I\ :sup:`2`\ C slave device
    - Slave device
    - I\ :sup:`2`\ C address
    - I/O standard
    - Comment
  * - IC10
    - Temperature sensor
    - 1 0 0 1 0 0 0 RW
    - 3.3 V
    - LM75
  * - IC12
    - EEPROM
    - 1 0 1 0 0 0 0 RW
    - 3.3 V
    - M24128