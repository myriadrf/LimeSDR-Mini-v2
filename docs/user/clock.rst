Reference Clock
###############

The LimeSDR Mini clock system is based on a high-stability 40 MHz VCTCXO (Voltage Controlled Temperature Compensated Crystal Oscillator) which can be tuned by an onboard 10-bit DAC or 16-bit DAC (unpopulated).

The board provides both reference clock input and output U.FL connectors.

.. list-table:: Table 3. Clock Functions
   :header-rows: 1

   * - Function
     - Specification
     - Notes
   * - Onboard Oscillator
     - 40 MHz VCTCXO
     - Rakon E7355LF, ± 0.5 ppm stability
   * - External Clock Input
     - U.FL (J8)
     - 10–52 MHz, 1.8 V to 3.3 V
   * - Clock Output
     - U.FL (J7)
     - 3.3 V CMOS

.. note::
   On v2.2 boards, the external clock input J8 is not connected by default. To use it, remove R63 and fit R66 (0 |Omega|). On v2.3 and v2.4 boards, the clock source is selected by the FPGA via analogue switch IC20, so no hardware changes are needed.

.. warning::
   When using external clock references, ensure signal levels and frequencies match specifications. 
   
   Improper clock signals may cause unstable operation and potential damage to the device.

