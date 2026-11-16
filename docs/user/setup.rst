Hardware Setup
##############

Host Interface
**************

LimeSDR Mini should be plugged into a USB Type-A socket on the host device.

The host must provide a USB 3.0 interface, which supplies up to 900 mA at 5 V. A USB 2.0 port can also be used, but it only guarantees 500 mA, which may not be enough in some configurations and limits the data transfer rate.

Cooling
*******

Depending on the application, host system and ambient temperature, additional cooling may be required to ensure reliable operation of the LimeSDR Mini board. This may be in the form of airflow through the host system, or a dedicated heatsink fitted to the board.

.. note::
   In the event of errors, instability or reduced performance, check the board temperature to ensure that it is within the specified operating range.

Fan Mounting
============

The LimeSDR Mini board features three holes, which may be used to secure the board in a case or to mount a fan, as shown in Figure 4. Two holes are placed at the sides of the USB connector and one hole is between the SMA connectors. 

.. figure:: /images/LimeSDR-Mini_v2.2_fan_mounting_1.png
  :width: 600

  Figure 4. LimeSDR Mini v2.x fan mounting

.. warning::
  Take care not to damage resistor R72 and capacitor C186 when using the mounting holes, as there is little clearance, as shown in Figure 5.

.. figure:: /images/LimeSDR-Mini_v2.2_fan_mounting_2.png
  :width: 600

  Figure 5. LimeSDR Mini v2.x mounting hole clearance

The recommended fan mounting solution is shown in Figure 6.

.. figure:: /images/LimeSDR-Mini_v2.2_fan_mounting_3.png
  :width: 600

  Figure 6. FIX-TP2-5 fan mounting components

.. figure:: /images/LimeSDR-Mini_v2.2_fan_mounting_4.png
  :width: 600

  Figure 7. FIX-HP2-5 fan mounting components

Use two FIX-TP2-5 stands with internal and external thread (4 mm width, M2 thread) as spacers to mount the fan on top of LimeSDR Mini v2.x. Put FIX-TP2-5 stands from the top through LimeSDR Mini v2.x slot mounting holes around USB connector as shown in Figure 6. Secure the stands to the fan using two M2 thread screws (e.g. P/N 1219480, Phillips head screw, M2x10). Secure two FIX-TP2-5 stands using two FIX-HP2-5 spacers as nuts from the bottom of the PCB as shown in Figure 7. This is enough to hold the fan but one may use additional FIX-HP2-5 (4 mm width, M2 thread) stand with internal thread as an additional fan rest point which rests on PCB over the unpopulated J3 connector as shown in Figures 6 and 7. Secure FIX-HP2-5 spacer to the fan using the same screw (P/N 1219480).

The fan is powered from connector J9 (0.1” pitch), which is not fitted by default, so a header must be soldered to the board to connect the fan. J9 supplies 5 V by default, and 3.3 V can be selected by resistors (R94, R96). The fan is controlled by the FPGA according to the board temperature, see :doc:`/reference/v2.4/tempsensor`.

Total required mechanical components per LimeSDR Mini v2.x:

* 2x `FIX-TP2-5 <https://www.tme.eu/en/details/fix-tp2-5/plastic-standoffs/fix-fasten/>`_ stands with internal and external M2 thread;
* 3x `FIX-HP2-5 <https://www.tme.eu/en/details/fix-hp2-5/plastic-standoffs/fix-fasten/>`_ stands with internal M2 threads;
* 3x `1219480 <https://www.tme.eu/en/details/b2x10_bn1435/bolts/bossard/1219480/>`_ screws, M2x10, 10 mm length;
* 1x `4127/MF30060V1-1000U-A99 <https://www.digikey.com/en/products/detail/sunon-fans/4127-MF30060V1-1000U-A99/9838567>`_ 30 mm fan.



RF Connections
**************

.. figure:: /images/LimeSDR-Mini_v2.4_RFCON.png
  :width: 600
  
  Figure 8. LimeSDR Mini v2.x board top with RF connector positions

.. table:: Table 2. RF connectors

  +---------------+----------+--------------+----------+-----------------------+
  | **Connector** | **Type** | **Function** | **Band** | **Recommended range** |
  +===============+==========+==============+==========+=======================+
  | J1            | SMA      | TX output    | TX low   | Below 2 GHz           |
  |               |          |              +----------+-----------------------+
  |               |          |              | TX high  | 2 GHz and above       |
  +---------------+----------+--------------+----------+-----------------------+
  | J2            | SMA      | RX input     | RX wide  | Below 2 GHz           |
  |               |          |              +----------+-----------------------+
  |               |          |              | RX high  | 2 GHz and above       |
  +---------------+----------+--------------+----------+-----------------------+

.. note::
   The recommended frequency ranges are approximate values that cover most use cases, not hard limits of the RF paths. The optimum path may vary depending on other factors, such as the antenna and RF front-end parameters.

.. warning::
   Care should be taken when connecting external RF signals to the RX inputs, to ensure that the maximum safe input power of +10 dBm is not exceeded, as this may cause permanent damage to the device.

