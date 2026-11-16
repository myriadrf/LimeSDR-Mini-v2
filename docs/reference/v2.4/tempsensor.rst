Board Temperature Control
#########################

LimeSDR Mini has an integrated temperature sensor, which is used to control the fan to keep the board within its operating temperature range. The fan must be connected to connector J9 (0.1” pitch). The fan supply voltage is 5 V by default, but it can be changed to 3.3 V by resistors.

The fan is turned on when the board heats up to 55 °C and turned off when the board cools down to 45 °C.

.. figure:: /images/LimeSDR-Mini_v2.2_temp_hysteresis.png
  :width: 600
  
  Figure 9. Fan control temperature hysteresis 




