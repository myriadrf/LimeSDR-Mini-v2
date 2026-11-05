RF Transceiver Digital
######################

The `LMS7002M`_ digital interface and control signals are described below.

Digital Interface
*****************

LMS7002 is using data bus LMS_DIQ1_D[11:0] and LMS_DIQ2_D[11:0], LMS_EN_IQSEL1 and LMS_EN_IQSEL2, LMS_FCLK1 and LMS_FCLK2, LMS_MCLK1 and LMS_MCLK2 signals to transfer data to/from the FPGA. Indices 1 and 2 indicate transceiver digital data PORT-1 or PORT-2. Any of these ports can be used to transmit or receive digital IQ data. 

By default PORT-1 is selected as transmitter port and PORT-2 is selected as receiver port. The FCLK# is input clock and MCLK# is output clock for the LMS7002M transceiver. TXNRX signals are used to indicate ports direction. Please refer to `LMS7002M transceiver datasheet`_ page 12-13 for the LMS7002M interface timing.

Control
*******

These signals are used for the following functions within the LMS7002 RFIC:

* LMS_RXEN, LMS_TXEN – receiver and transmitter enable/disable signals connected to FPGA Bank 14 (3.3V).
* LMS_RESET – LMS7002M reset is connected to FPGA Bank 14 (3.3V).
* SPI Interface: LMS7002M transceiver is configured via 4-wire SPI interface: FPGA_SPI_SCLK, FPGA_SPI_MOSI, FPGA_SPI_MISO, FPGA_SPI_LMS_SS. The SPI interface controlled from FPGA Bank 3 (VDIO_LMS_FPGA; 2.5V).
* LMS I2C Interface: can be used for LMS EEPROM content modification or debug purposes. The signals LMS_I2C_SCL and LMS_I2C_DATA are connected to EEPROM.

LMS7002M Pins
*************

.. list-table:: Table 2. LMS7002M RF transceiver digital interface pins
   :header-rows: 1
   :stub-columns: 1

   * - Chip pin (IC1)
     - Chip reference (IC1)
     - Schematic signal name
     - FPGA pin
     - FPGA I/O standard
     - Notes
   * - E5
     - xoscin_tx
     - TxPLL_CLK
     - 
     - 
     - Connected to 40.00 MHz clock
   * - AB34
     - MCLK1
     - LMS_MCLK1
     - H4
     - 2.5V/3.3V
     - 
   * - AA33
     - FCLK1
     - LMS_FCLK1
     - H3
     - 2.5V/3.3V
     - 
   * - V32
     - TXNRX1
     - LMS_TXNRX1
     - F1
     - 2.5V/3.3V
     - 
   * - U29
     - TXEN
     - LMS_TXEN
     - B7
     - 2.5V/3.3V
     - 
   * - 1Y32
     - ENABLE_IQSEL1
     - LMS_EN_IQSEL1
     - F3
     - 2.5V/3.3V
     - 
   * - AG31
     - DIQ1_D0
     - LMS_DIQ1_D0
     - J2
     - 2.5V/3.3V
     - 
   * - AF30
     - DIQ1_D1
     - LMS_DIQ1_D1
     - L1
     - 2.5V/3.3V
     - 
   * - AF34
     - DIQ1_D2
     - LMS_DIQ1_D2
     - K1
     - 2.5V/3.3V
     - 
   * - AE31
     - DIQ1_D3
     - LMS_DIQ1_D3
     - K4
     - 2.5V/3.3V
     - 
   * - AD30
     - DIQ1_D4
     - LMS_DIQ1_D4
     - G3
     - 2.5V/3.3V
     - 
   * - AC29
     - DIQ1_D5
     - LMS_DIQ1_D5
     - F4
     - 2.5V/3.3V
     - 
   * - AE33
     - DIQ1_D6
     - LMS_DIQ1_D6
     - J1
     - 2.5V/3.3V
     - 
   * - AD32
     - DIQ1_D7
     - LMS_DIQ1_D7
     - H1
     - 2.5V/3.3V
     - 
   * - AC31
     - DIQ1_D8
     - LMS_DIQ1_D8
     - G4
     - 2.5V/3.3V
     - 
   * - AC33
     - DIQ1_D9
     - LMS_DIQ1_D9
     - F2
     - 2.5V/3.3V
     - 
   * - AB30
     - DIQ1_D10
     - LMS_DIQ1_D10
     - G1
     - 2.5V/3.3V
     - 
   * - AB32
     - DIQ1_D11
     - LMS_DIQ1_D11
     - H2
     - 2.5V/3.3V
     - 
   * - AM24
     - xoscin_rx
     - RxPLL_CLK
     - 
     - 
     - Connected to 40.00 MHz clock
   * - P34
     - MCLK2
     - LMS_MCLK2
     - D2
     - 2.5V/3.3V
     - 
   * - R29
     - FCLK2
     - LMS_FCLK2
     - D1
     - 2.5V/3.3V
     - 
   * - U31
     - TXNRX2
     - LMS_TXNRX2
     - B6
     - 2.5V/3.3V
     - 
   * - V34
     - RXEN
     - LMS_RXEN
     - D6
     - 2.5V/3.3V
     - 
   * - R33
     - ENABLE_IQSEL2
     - LMS_EN_IQSEL2
     - C4
     - 2.5V/3.3V
     - 
   * - H30
     - DIQ2_D0
     - LMS_DIQ2_D0
     - A3
     - 2.5V/3.3V
     - 
   * - J31
     - DIQ2_D1
     - LMS_DIQ2_D1
     - C2
     - 2.5V/3.3V
     - 
   * - K30
     - DIQ2_D2
     - LMS_DIQ2_D2
     - A2
     - 2.5V/3.3V
     - 
   * - K32
     - DIQ2_D3
     - LMS_DIQ2_D3
     - B4
     - 2.5V/3.3V
     - 
   * - L31
     - DIQ2_D4
     - LMS_DIQ2_D4
     - C3
     - 2.5V/3.3V
     - 
   * - K34
     - DIQ2_D5
     - LMS_DIQ2_D5
     - B2
     - 2.5V/3.3V
     - 
   * - M30
     - DIQ2_D6
     - LMS_DIQ2_D6
     - D3
     - 2.5V/3.3V
     - 
   * - M32
     - DIQ2_D7
     - LMS_DIQ2_D7
     - B1
     - 2.5V/3.3V
     - 
   * - N31
     - DIQ2_D8
     - LMS_DIQ2_D8
     - A4
     - 2.5V/3.3V
     - 
   * - N33
     - DIQ2_D9
     - LMS_DIQ2_D9
     - C1
     - 2.5V/3.3V
     - 
   * - P30
     - DIQ2_D10
     - LMS_DIQ2_D10
     - C7
     - 2.5V/3.3V
     - 
   * - P32
     - DIQ2_D11
     - LMS_DIQ2_D11
     - A6
     - 2.5V/3.3V
     - 
   * - U33
     - CORE_LDO_EN
     - LMS_CORE_LDO_EN
     - C6
     - 2.5V/3.3V
     - 
   * - E27
     - RESET
     - LMS_RESET
     - A7
     - 2.5V/3.3V
     - 
   * - D28
     - SEN
     - FPGA_SPI_LMS_SS
     - N3
     - 2.5V/3.3V
     - SPI interface
   * - C29
     - SCLK
     - FPGA_SPI_SCLK
     - M3
     - 2.5V/3.3V
     - SPI interface
   * - F30
     - SDIO
     - FPGA_SPI_MOSI
     - L3
     - 2.5V/3.3V
     - SPI interface
   * - F28
     - SDO
     - FPGA_SPI_MISO
     - K3
     - 2.5V/3.3V
     - SPI interface
   * - D26
     - SDA
     - LMS_I2C_SDA
     - 
     - 
     - Connected to EEPROM
   * - C27
     - SCL
     - LMS_I2C_SCL
     - 
     - 
     - Connected to EEPROM