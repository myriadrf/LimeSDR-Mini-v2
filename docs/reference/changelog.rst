Changelog
#########

v2.4
****

Changes from v2.3:

* Switching regulators IC14 (1.8 V rail) and IC19 (3.3 V rail) changed from LMZ10501 back to LMZ20501, with the same feedback and compensation components as v2.2.
* Optional voltage reference IC17 for the 16-bit VCTCXO DAC (IC16) changed from MCP1525T to AS431. Both fixed and adjustable voltage references can be used by fitting the appropriate resistors (R63, R66, R102). IC16 and IC17 are not fitted by default.
* Higher voltage rating on several decoupling capacitors.
* Hardware version (HW_VER) increased from 6 to 7. The BOM version (BOM_VER) is 0.

v2.3
****

Changes from v2.2:

* Analogue switch IC20 (74LVC1G3157FZ4) added to select the reference clock source: the onboard VCTCXO (XO1) or the external clock input (J8). The switch is controlled by the FPGA through the CLK_SEL signal (FPGA pin B6), so the clock source can be changed without hardware modifications. On v2.2 boards, the clock source is selected by fitting either R63 (VCTCXO, default) or R66 (external clock).
* FPGA pin B6 is now used for CLK_SEL, so the LMS7002M LMS_TXNRX2 signal is no longer connected to the FPGA.
* Switching regulators IC14 (1.8 V rail) and IC19 (3.3 V rail) changed from LMZ20501 to LMZ10501.
* Hardware version (HW_VER) increased from 5 to 6. The BOM version (BOM_VER) is 0.

RF loopback
***********

On LimeSDR Mini v2.x boards, shunt transistor VT3 in the RF feedback attenuator chain was changed because the original part reached end of life (EOL). The original part BFT92,215 had a small output capacitance of around 1.2 pF, whereas the new RF transistor ZVN4525E6TA has a larger output capacitance of 11 pF. An extract of the schematic is presented in Figure 1.

.. figure:: /images/LimeSDR-Mini_Attenuator_v1_vs_v2.png
  :width: 600
  
  Figure 1. LimeSDR Mini RF loopback attenuator implementation on v1.x and v2.x boards

The increased shunt capacitance affects the frequency response of the attenuator. The attenuation is −46 dB at 1 GHz and −52 dB at 2.1 GHz for the new LimeSDR Mini v2.x board. The frequency response shown in Figure 2 can be used as a reference RF loopback attenuation in the supported frequency range. 

.. figure:: /images/LimeSDR-Mini_v2.2_RF_LB_response.png
  :width: 600
  
  Figure 2. LimeSDR Mini v2.x RF loopback frequency response