# OPC UA System HTTP/TLS/JSON System Description

## Abstract
This document describes an [Arrowhead framework compliant system](https://arrowhead.eu/eclipse-arrowhead) that integrates an OPC UA client. 
The systems scans an OPC UA server's nodes and offers these services as Arrowhead framework compliant services with fine grained authorization.
The OPC UA systems registers these services with the ServiceRegistry system<sup>[[1]](#footnote-1)</sup>. 
The system can additionally consume services from a DataManager system to log signal states.
It does so by requesting the URL of the DataManager from the Orchestrator system.
This core system takes responsibility for managing the offered services of all systems.

## Overview
This Eclipse Arrowhead compliant OPC UA system is composed of an [Arrowhead provider](https://github.com/arrowhead-f/client-skeleton-java-spring) with an [Eclipse Milo](https://github.com/arrowhead-f/client-skeleton-java-spring) client.

To develop and demonstrate this system within a local cloud, it is interfaced to a [Siemens PLC](https://new.siemens.com/global/en/products/automation/systems/industrial/plc/simatic-s7-1500.html) with an integrated OPC UA server.
A system of systems description [SoSD](OPCUA_SoSD.md) describes this demonstrator.

The purpose of this system is to:
- connect to any OPC-UA server.
- Browse at run time through the available nodes of the OPC UA server and register the individual service instances for each node.
- Register these services with their associated metadata (automatically without configuration).
- Provide these services to respectively authorized systems.
- Consume data logging services from data logging system (e.g., [DataManager](https://github.com/jenseliasson/DataManager) or [Jotne logger](https://conwik.jotne.com/display/EDM/On-boarding+Document+Arrowhead+Framework+Integration-EDMtruePLM+%28ISO10303%29+repository)) if available via the mandatory core systems.

Once the services are available for each node in the service registry, any authorized consumer can read the status of all sensors and actuators through orchestrating for the registered service instances. 
The integration of OPC UA with the Arrowhead Framework is smooth and complete. 
All that is needed is the URL of the OPC-UA and its root node.

## System Role
This System provides one service the Signal Status. The *applications.properties* file is configured with the OPC UA server address and the root node id. Prior to registering the service, the OPC UA System connects to the OPC UA server and scans all the nodes present under the root node and then registers all the nodes as individual service instances with same service definition but different service URI and metadata. Hence, in the case of this demonstrator there are 19 service instances registered in the service registry. 
Once the services are available, the consumer can orchestrate the service and gets the endpoints for all 19 service instances. Now the consumer can get the status of each signal individually by connecting to each endpoint. A sequence diagram of the service registration and consumption process is depicted in figure 1. 

### Figure 1: Sequence Diagram of OPC UA System Interaction in the Arrowhead Local Cloud
![](Images/OPCUA%20Flow.jpg)

## Services
### Consumed Services
- ServiceRegistry
- Orchestrator
- Data logger
#### Service Discovery
This service provided by the Service Registry allow the OPC UA System to Register and to Unregister their services.

### Provided Services
#### Signal Status
This service is provided to read the value of all the nodes under the root node of the connected OPC UA server, which means the status of all sensors and actuators.

## Security
Within its local cloud, this system can be secured via the HTTPS protocol. 
If it is started in secure mode, it verifies whether the application system possesses a proper X.509 identity certificate and whether that certificate is Arrowhead compliant in its making. This certificate structure and creation guidelines ensure:
- Application System is properly bootstrapped into the Local Cloud
- The Application System indeed belongs to this Local Cloud
- The Application System then automatically has the right to register its Services in the Registry.

The X.509 standard can also be used [between](https://github.com/eclipse/milo/blob/master/opc-ua-stack/stack-core/src/main/java/org/eclipse/milo/opcua/stack/core/util/CertificateUtil.java) the Milo client and OPC UA server to enforce cybersecurity on that side for the system.

<a name="footnote-1">[1]</a>:The OPC UA consumes services from the ServiceRegistry system.