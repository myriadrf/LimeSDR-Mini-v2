Peripheral Interfaces
#####################

FPGA_SPI pins, schematic signal names, FPGA interconnections and I/O standards/levels are shown in Table 9.

.. list-table:: Table 9. FPGA_SPI interface pins
  :header-rows: 1

  * - Schematic signal name
    - FPGA pin
    - I/O standard
    - Comment
  * - FPGA_SPI_SCLK
    - M3
    - 2.5V / 3.3V
    - Serial Clock (FPGA output)
  * - FPGA_SPI_MOSI
    - L3
    - 2.5V / 3.3V
    - Data (FPGA output)
  * - FPGA_SPI_MISO
    - K3
    - 2.5V / 3.3V
    - Data (FPGA input)
  * - FPGA_SPI_LMS_SS
    - N3
    - 2.5V / 3.3V
    - IC1 (LMS7002) SPI slave select (FPGA output)
  * - FPGA_SPI_DAC_SS
    - L4
    - 2.5V / 3.3V
    - IC11 SPI slave select (FPGA output)

FPGA_CFG_SPI pins, schematic signal names, FPGA interconnections and I/O standards are shown in Table 10.

.. list-table:: Table 10. FPGA_CFG_SPI interface pins
  :header-rows: 1

  * - Schematic signal name
    - FPGA pin
    - I/O standard
    - Comment
  * - FPGA_CFG_SPI_SCLK
    - U16
    - 3.3V
    - Serial Clock (FPGA output)
  * - FPGA_CFG_SPI_MOSI
    - U18
    - 3.3V
    -
  * - FPGA_CFG_SPI_MISO
    - T18
    - 3.3V
    -
  * - FPGA_CFG_SPI_SS
    - U17
    - 3.3V
    - IC15 SPI slave select (FPGA output)

FPGA_I2C (temperature sensor and EEPROM) interface slave devices and related information are given in Table 11.

.. list-table:: Table 11. FPGA_I2C interface pins
  :header-rows: 1
  
  * - I2C slave device
    - Slave device
    - I2C address
    - I/O standard
    - Comment
  * - IC10
    - Temperature sensor
    - 1 0 0 1 0 0 0 RW
    - 3.3V
    - LM75
  * - IC12
    - EEPROM
    - 1 0 1 0 0 0 0 RW
    - 3.3V
    - M24128