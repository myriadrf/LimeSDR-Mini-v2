Board Versions
##############

There are currently three versions of the LimeSDR Mini v2 board: v2.2, v2.3 and v2.4. 

v2.2, v2.3 and v2.4 boards should be treated the same in terms of hardware functionality and software support. The main changes in each new board version are listed in Table 1. For a full list of changes, see the :doc:`/reference/changelog`.

.. list-table:: Table 1. Changes in each board version
   :header-rows: 1
   :stub-columns: 1

   * - Version
     - Changes
   * - v2.4
     - Switching regulators (IC14, IC19) changed back to LMZ20501.

       Optional voltage reference (IC17) for the 16-bit VCTCXO DAC changed from MCP1525T to AS431.

       IC17 is not fitted by default.
   * - v2.3
     - Analogue switch (IC20) added to select the reference clock source.

       The FPGA selects the onboard VCTCXO or the external clock input (J8), so no hardware changes are needed.

       Switching regulators (IC14, IC19) changed to LMZ10501.
   * - v2.2
     - Initial version.

       The reference clock source is selected by resistors (R63, R66).

.. figure:: /images/LimeSDR-Mini_v2.4_3D_top.png
  :width: 600

  Figure 1. LimeSDR Mini v2.4 board top view

.. figure:: /images/LimeSDR-Mini_v2.3_3D_top.png
  :width: 600

  Figure 2. LimeSDR Mini v2.3 board top view

.. figure:: /images/LimeSDR-Mini_v2.2_3D_top.png
  :width: 600

  Figure 3. LimeSDR Mini v2.2 board top view