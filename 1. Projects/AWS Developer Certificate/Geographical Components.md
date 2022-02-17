#aws #development_career 
To deliver content in a global scale with high availability, AWS has developed a infrastructure composed of three geographical components: Regions, Availability Zones and Edge Locations.

## Region
When architecting an infrastructure, you need to know where your servers will physically be. That is mandatory, at least country-wise, because you should be able to evaluate your latency and any data laws that may apply to your system. 
A AWS Region is basically a geographic location that Amazon provides. Currently, there are 12 different regions. Some are located in the USA (4), Brazil (1), EU (2) and Asia (5).
Each one of these Regions have al least 2 Availability Zones (AZ).

## Availability Zone 
Unexpected issues may occur even for the giant Amazon. To ensure your product doesn't go down when a Data Center experiences some turbulence, the AZ's come in use. An Availability Zone is effectively a Data Center located within a Region. Each one is independent of others. Since every Region has at least 2 of them, you won't (shouldn't*) have any sleepless nights because your whole Region is down.