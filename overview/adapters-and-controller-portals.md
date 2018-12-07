# Adapters and Controller Portals

Enbala of course needs to talk to devices that exist in the real world in order to receive real-time telemetry, and control their operation. In practical terms that means we can only work with devices that are networked and have an API. We call these devices **Smart Devices** and the box on the device that we talk to we call the **Controller**. In all of the cases that we have seen so far, we don't communicate with any smart devices directly but rather we use an API endpoint provided by the manufacturer of the controller. We call this endpoint the **Controller Portal**. The portion of our application that we use to abstract away the details of, and talk to the controller portal we call the **Adapters.**

The flow of information looks like:

```text

+-------------------------------+              +------------------------------------------------------+
|    Things we do not own       |              |    Things we own                                     |
+----------+--------------------+   Internet   +------------------------------+-----------------------+
|  Assets  | Controller Portals |              |    Adapters                  |  VPP                  |
+----------+--------------------+              +------------------------------+-----------------------+
| +-----+                       |              |                                                      |
| |     |    Skycentrics API <---------+       |    Skycentrics Adapter +---+                         |
| +-----+                       |      |       |                            |                         |
| |     +---> Collect Telemetry |      +--------->  Ask for telemery        |                         |
| +-----+                       |      |       |                            |                         |
| |     <---+ Send Control      |      +----------  Schedule Control        |                         |
| +-----+                       |              |                            |                         |
| |     |                       |              |                            +--> Receive Telemetry    |
| +-----+                       |              |                            |                         |
| |     |                       |              |                            <--+ Send Control Records |
| +-----+                       |              |                            |                         |
|                               |              |                            |                         |
|                               |              |                            |                         |
| +-----+                       |              |                            |                         |
| |     |    Aquanta API <-------------+       |    Aquanta Adapter     +---+                         |
| +-----+                       |      |       |                                                      |
| |     +---->Collect Telemetry |      +--------->  Ask for telemery                                  |
| +-----+                       |      |       |                                                      |
| |     <----+Send Control      |      +----------  Schedule Control                                  |
| +-----+                       |              |                                                      |
| |     |                       |              |                                                      |
| +-----+                       |              |                                                      |
| |     |                       |              |                                                      |
| +-----+                       |              |                                                      |
|                               |              |                                                      |
+-------------------------------+              +------------------------------------------------------+

```

