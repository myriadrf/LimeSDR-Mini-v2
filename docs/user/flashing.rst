Flashing
########

From time to time it may be necessary to reprogram the FPGA configuration FLASH memory on the LimeSDR Mini board. This may be required when upgrading to a newer gateware version, or in case of corrupted FLASH memory.

It should usually be possible to program the LimeSDR Mini board using software only, with the device connected via the USB interface. However, in case of corrupted FLASH memory or other issues, JTAG programming may be required. The JTAG connector J5 is not fitted by default, so a header must be soldered to the board to use it, see :doc:`/reference/v2.4/jtag`.

To start, download a `pre-compiled programming file`_ (.bit). Then proceed to use the pure software programming method described below, unless it has been determined that JTAG programming is necessary.

Software Programming
********************

This section describes how to program the FPGA configuration FLASH memory on the LimeSDR Mini v2 board using Lime software.

Software
========

The :external+suiteng:ref:`Lime Suite NG software <index:introduction>` is required for programming the FPGA configuration FLASH memory.

Programming via the GUI
=======================

The programming options can be accessed in the :code:`limeGUI` application under Modules->Programming.

To program:

#. Set Programming mode to FPGA/FLASH.
#. Select the image .bit file you wish to use by pressing Open. 
#. Initiate programming by pressing Program.

.. figure:: /images/LimeSDR-Mini_v2_PROGGUI.png
  :width: 600

  Figure 9. Programming via the GUI

Programming via the CLI
=======================

Programming can also be achieved using the CLI application :code:`limeFLASH` that is built alongside limeGUI.

The relevant options:

* device - to choose LimeSDR Mini v2 type :code:`Mini`.
* target - to set programming mode type :code:`FPGA/FLASH` and add the path to the .bit file. 

..  code-block:: shell
    :caption: Programming via the CLI

    limeFLASH --device Mini --target FPGA/FLASH <path_to>/limesdr_mini_v2.bit

.. note::
  :code:`<path_to>/limesdr_mini_v2.bit` should be replaced by the actual path to your chosen .bit file.

.. _pre-compiled programming file: https://github.com/myriadrf/LimeSDR_GW/blob/master/bitstream/LimeSDR_Mini_V2/limesdr_mini_v2.bit





