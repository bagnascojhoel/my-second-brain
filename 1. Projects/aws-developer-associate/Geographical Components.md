#aws #development_career 
To deliver content in a global scale with high availability, AWS has developed a infrastructure composed of three geographical components: Regions, Availability Zones and Edge Locations.

## Region
When architecting an infrastructure, you need to know where your servers will physically be. That is mandatory, at least country-wise, because you should be able to evaluate your latency and any data laws that may apply to your system. 
A AWS Region is basically a geographic location that Amazon provides. Currently, there are 12 different regions. Some are located in the USA (4), Brazil (1), EU (2) and Asia (5). These regions don't always have all AWS Services. Some Regions, like `us-east` receive new features faster. That means that if you wish to use the lattest AWS feature, you may endup having to go for farther Regions and have high-latency.

## Availability Zone 
Unexpected issues may occur even for the giant Amazon. To ensure your product doesn't go down when a Data Center experiences some turbulence, the AZ's come in use. An Availability Zone is effectively a Data Center located within a Region. Each one is independent of others. Since every AWS Region has at least 2 of them, you won't (shouldn't*) have any sleepless nights because your whole Region is down.
Every AZ within the same Region are connected via extremely low latency infrastructure. That allows for AWS services to provide features that ensure you have multiple sources in different AZ's. 

## Edge Location
To deliver content at a low latency everywhere in the globe, AWS CloudFront provides a global Content Delivery Network (CDN). This CDN uses Edge POP's. They are infrastructure needed to deliver content, located at highly populated areas. They don't necessarily need to be inside an Infrastructure Region.
![AWS Edge Location Distribution](https://filedb.experts-exchange.com/incoming/2015/07_w29/923433/homepage-global-infrastructure-map.png)
