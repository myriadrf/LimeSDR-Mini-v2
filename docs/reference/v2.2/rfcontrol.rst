RF Network
##########

The RF network contains matching networks, RF switches, a loopback variable attenuator and two SMA connectors (J1 - TX and J2 - RX), as shown in Figure 6.

.. figure:: /images/LimeSDR-Mini_v2.2_diagrams_RFFE.png
  :width: 600

  Figure 6. LimeSDR Mini v2.2 RF diagram

Frequency Range
===============

Each LMS7002M RF transceiver TX and RX port is connected to a dedicated RF path, and the appropriate path should be selected according to the operating frequency. On the receive side, the wideband path (RX1_W) is recommended for frequencies below 2 GHz and the high-band path (RX1_H) for frequencies of 2 GHz and above. On the transmit side, the TX1_2 path is recommended for frequencies below 2 GHz and the TX1_1 path for frequencies of 2 GHz and above. The recommended frequency ranges for all ports are summarised in Table 5.

.. note::
   The recommended frequency ranges are approximate values that cover most use cases, not hard limits of the RF paths. The optimum path may vary depending on other factors, such as the antenna and RF front-end parameters.

.. list-table:: Table 5. LMS7002M RF transceiver ports and recommended frequency ranges
   :header-rows: 1

   * - RF transceiver port
     - Recommended frequency range
   * - TX1_1
     - 2 GHz and above
   * - TX1_2
     - Below 2 GHz
   * - RX1_H
     - 2 GHz and above
   * - RX1_W
     - Below 2 GHz

Control
=======

The onboard RF switches and the loopback attenuator are controlled by FPGA 3.3 V outputs. RF network control signals are described in Table 6.

.. table:: Table 6. RF network control signals

  +------------------------+---------------------------+------------------+--------------+----------------------------------------------------+
  | **Component**          | **Schematic signal name** | **I/O standard** | **FPGA pin** | **Description**                                    |
  +========================+===========================+==================+==============+====================================================+
  | RFSW_TX                | RFSW_TX_V1                | 3.3 V            | B10          | V1 high, V2 low: TX1_1 to TX, TX1_2 to ATT.        |
  |                        |                           |                  |              |                                                    |
  | (SKY13411-374LF – IC3) |                           |                  |              | V1 low, V2 high: TX1_1 to ATT, TX1_2 to TX.        |
  |                        +---------------------------+------------------+--------------+                                                    |
  |                        | RFSW_TX_V2                | 3.3 V            | C9           |                                                    |
  +------------------------+---------------------------+------------------+--------------+----------------------------------------------------+
  | RFSW_RX                | RFSW_RX_V1                | 3.3 V            | C11          | V1 high, V2 low: RX1_H to RX, RX1_W to ATT.        |
  |                        |                           |                  |              |                                                    |
  | (SKY13411-374LF – IC4) |                           |                  |              | V1 low, V2 high: RX1_H to ATT, RX1_W to RX.        |
  |                        +---------------------------+------------------+--------------+                                                    |
  |                        | RFSW_RX_V2                | 3.3 V            | B11          |                                                    |
  +------------------------+---------------------------+------------------+--------------+----------------------------------------------------+
  | Variable attenuator    | TX_LB_AT                  | 3.3 V            | C8           | High: -25 dB, low: -40 dB.                         |
  |                        +---------------------------+------------------+--------------+----------------------------------------------------+
  |                        | TX_LB_SH                  | 3.3 V            | B8           | Attenuator shunting.                               |
  +------------------------+---------------------------+------------------+--------------+----------------------------------------------------+
