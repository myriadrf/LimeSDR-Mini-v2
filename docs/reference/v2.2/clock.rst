Clock Distribution
##################

The LimeSDR Mini board clock distribution block diagram is shown in Figure 7.

.. figure:: /images/LimeSDR-Mini_v2.2_diagrams_clock.png
  :width: 600

  Figure 7. LimeSDR Mini v2.2 board clock distribution block diagram

The LimeSDR Mini board features an onboard 40.00 MHz VCTCXO as the reference clock for the LMS7002M RF transceiver and FPGA PLLs.

Rakon E7355LF 40 MHz voltage controlled temperature compensated crystal oscillator (VCTCXO) is the clock source for the board. VCTCXO frequency can be tuned using a 10-bit (IC11) or 16-bit (IC16, unpopulated) DAC. Main VCTCXO parameters are listed in Table 7.

.. list-table:: Table 7. Rakon E7355LF VCTCXO main parameters
   :header-rows: 1

   * - Frequency parameter
     - Value
   * - Calibration (25 °C ± 1 °C)
     - ± 1 ppm max
   * - Stability (-40 to 85 °C)
     - ± 0.5 ppm max
   * - Long-term stability (1 year, 10 years)
     - ± 2 ppm max, ± 4 ppm max
   * - Control voltage range
     - 0.5 V – 2.5 V
   * - Frequency tuning
     - ± 7 ppm min, ± 15 ppm max
   * - Slope
     - +9 ppm/V

The reference clock source is selected by resistors: the onboard VCTCXO (XO1) via R63 (fitted by default) or the external U.FL connector (J8) via R66 (not fitted). Only one of R63 and R66 should be fitted. The selected clock is distributed to the RF transceiver and FPGA by clock buffer IC9 (LMK00105). Buffered clock output (REF_CLK_OUT) is also available using U.FL (J7) connector.

The board clock lines and other related signals/information are listed in Table 8.

.. table:: Table 8. LimeSDR Mini main clock lines

  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  | **Source**               | **Schematic signal name** | **I/O standard** | **FPGA pin** | **Description**                            |
  +==========================+===========================+==================+==============+============================================+
  | External                 | REF_CLK_IN                | 2.5 V/3.3 V      |              | External reference clock input             |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  | Clock buffer (IC9)       | REF_CLK_OUT               | 3.3 V            |              | Reference clock output                     |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  | Clock buffer (IC9)       | LMK_CLK                   | 3.3 V            | A9           | Reference clock connected to FPGA          |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  | RF transceiver (IC1)     | RxPLL_CLK                 | 1.8 V            |              | Reference clock input                      |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  |                          | TxPLL_CLK                 | 1.8 V            |              | Reference clock input                      |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  |                          | LMS_MCLK1                 | 2.5 V/3.3 V      | H4           |                                            |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  |                          | LMS_FCLK1                 | 2.5 V/3.3 V      | H3           |                                            |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  |                          | LMS_MCLK2                 | 2.5 V/3.3 V      | D2           |                                            |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  |                          | LMS_FCLK2                 | 2.5 V/3.3 V      | D1           |                                            |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+
  | USB 3.0 controller (IC8) | FT_CLK                    | 3.3 V            | D17          | Clock output (100 MHz) from USB controller |
  +--------------------------+---------------------------+------------------+--------------+--------------------------------------------+