# Kvaser ROS Interface API
The Kvaser ROS Interface API is based on the Autonomous Stuff Code (https://github.com/astuff/kvaser_interface). Kvser_interface is modified to enable CANFD communication.

## The `kvaser_can_bridge` Node

**TOPICS**

*can_tx* [can_msgs::Frame]
*can_tx* [can_msgs::FrameFd]

This topic is published by the node. It expects to have other nodes subscribe to it to receive data which are *sent by the CAN device*.

*can_rx* [can_msgs::Frame]
*can_rx* [can_msgs::FrameFd]

This topic is subscribed to by the node. It expects to have data published to it which are intended to be *received by the CAN device*.

**PARAMETERS**

*~can_hardware_id*

This is the Kvaser Hardware ID (serial number) of the connected device.

*~can_circuit_id*

This is the 0-based index of the channel number *on the specific hardware device* designated by the *~can_hardware_id*.

*~can_bit_rate*

This is the communication rate to be used on the CAN channel in bits per second (default: 500000).

*~canfd*

This is the canfd flag (0 : not canfd, 1 : canfd).

*~canfd_tseg1*

Time segment 1, that is, the number of quanta from (but not including) the Sync Segment to the sampling point (default: 15).

*~canfd_tseg2*

Time segment 2, that is, the number of quanta from the sampling point to the end of the bit (default: 4).

*~canfd_sjw*

The Synchronization Jump Width (default: 4).

*~canfd_data_rate*

The canfd data rate (defalut : 2000000)

