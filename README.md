FinPay needs to segment its network because different departments have different access requirements and security risks. A flat network would place Finance, Operations, IT, Guests and Servers in the same broadcast domain, making unauthorised access and lateral movement easier.

I created a separate VLAN for each department. This logically separates the departments at Layer 2, even when they use the same physical switches. Each VLAN also receives a separate IP subnet, creating a matching Layer 3 network boundary and making devices easier to identify, route and control.

Because devices in separate VLANs cannot communicate directly through a Layer 2 switch, I used router-on-a-stick for inter-VLAN routing. A single physical connection between the switch and router operates as a trunk, while router subinterfaces provide a separate default gateway for each VLAN.

This design is affordable and appropriate for a small FinPay office. Its limitation is that the single router connection can become a bottleneck and single point of failure. A larger production environment would likely use redundant multilayer switches.
