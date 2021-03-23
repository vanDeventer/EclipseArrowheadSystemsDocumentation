# OPC UA System HTTP/TLS/JSON System Description

## Abstract
This document describes the Arrowhead Client system integrated with OPC UA server. This core system takes responsibility for managing the offered services of all systems.

## Overview
This document describes the Eclipse Arrowhead client system integrated with OPC UA server. To demonstrate this integration, a Siemens PLC with an integrated OPC UA server is connected to a model assembly with two machining stations and four conveyor belts. The model assembly consists of total 9 sensors and 10 actuators and each sensor and actuator is linked to an individual node in the OPC UA server. The PLC is then connected to an Arrowhead local cloud through an Ethernet cable and let the Arrowhead OPC UA client system integrate with the OPC UA server. 

The purpose of this System are:
- connect to any OPC-UA server.
- Browse through the available nodes of the OPC UA server and register individual service instances for each node.

Once the services are available for each node in the service registry, any authorized consumer can read the status of all sensors and actuators through orchestrating for the registered service instances. The integration of OPC-UA with the Arrowhead Framework is smooth and complete. All that is needed is the URL of the OPC-UA and its root node.

## System Role
This System provides one service the Signal Status. The applications.properties file is configured with the OPC UA server address and the root node id. Prior to registering the service, the OPC UA System connects to the OPC UA server and scans all the nodes present under the root node and then registers all the nodes as individual service instances with same service definition but different service URI and metadata. Hence, in the case of this demonstrator there are 19 service instances registered in the service registry. 
Once the services are available, the consumer can orchestrate the service and gets the endpoints for all 19 service instances. Now the consumer can get the status of each signal individually by connecting to each endpoint. A sequence diagram of the service registration and consumption process is depicted in figure 1. 

### Sequence Diagram of OPC UA System Interaction in the Arrowhead Local Cloud
![] (Images/OPCUA Flow.jpg)

## Services
### Consumed Services
#### Service Discovery
This service provided by the Service Registry allow the OPC UA System to Register and to Unregister their services.

### Provided Services
#### Signal Status
This service is provided to read the value of all the nodes under the root node of the connected OPC UA server, which means the status of all sensors and actuators.

## Security
This System can be secured via the HTTPS protocol. If it is started in secure mode, it verifies whether the Application System possesses a proper X.509 identity certificate and whether that certificate is Arrowhead compliant in its’ making. This certificate structure and creation guidelines ensure:
- Application System is properly bootstrapped into the Local Cloud
- The Application System indeed belongs to this Local Cloud
- The Application System then automatically has the right to register its Services in the Registry.
