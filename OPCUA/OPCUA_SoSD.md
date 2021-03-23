# Local Cloud with OPC UA System
To develop and demonstrate this system within a local cloud, it is interfaced to a [Siemens PLC](https://new.siemens.com/global/en/products/automation/systems/industrial/plc/simatic-s7-1500.html) with an integrated OPC UA server.
The PLC's digital input and outputs (I/O) are connected to a model indexed line with two machining stations and four conveyor belts. 
The model line consists of total 9 sensors and 10 actuators and each sensor and actuator is linked to an individual node in the OPC UA server. 
The PLC is then connected to an Arrowhead local cloud through an Ethernet cable. 
