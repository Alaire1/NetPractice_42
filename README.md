# NetPractice

## IP
- **Unique Assignment:** Each device on a network must have a unique IP address to ensure accurate data routing and device identification.
- **Handling Connection:** makes sending data between devices possible. 
- **Two types** currently we have two types of IPs existing, IPv4 and IPv6.
- **Private and Public IPs:** IP addresses can be also categorized as private (used within local networks) or public (used for internet communication).
- **Dynamic and Static IPs:** IP addresses can be dynamic (assigned by a DHCP server and may change over time) or static (fixed and manually assigned).
- **Network Troubleshooting:** IP addresses are essential for diagnosing network issues through tools like ping and traceroute.
- **IoT and IP:** The Internet of Things (IoT) relies on IP addresses for connected devices and sensors to communicate and share data over the internet.
- **Data Security:** IP addresses play a critical role in network security, helping to identify and control data traffic, including the use of firewalls and intrusion detection systems.


### IPv4 and IPv6 diffenences
  
| Feature                | IPv4                               | IPv6                           |
|------------------------|------------------------------------|-------------------------------|
| Address Format         | Dotted-decimal (e.g., 192.168.1.1) | Hexadecimal, colon-separated  |
| Address Length         | 32 bits (4 bytes)                  | 128 bits (16 bytes)           |
| Address Notation       | Example: 192.168.1.1               | Example: 2001:0db8:85a3:0000: |
| Number of Addresses    | Approximately 4.3 billion          | Approximately 340 undecillion |
| Address Configuration  | Manual or DHCP                     | Stateless Autoconfiguration   |
| Broadcast              | Supported (limited)                | Not supported                 |
| Subnetting             | Used to create smaller networks    | Simplified subnetting         |
| Header Complexity      | Variable header lengths            | Fixed-length headers          |
| Security Features      | IPsec is optional                  | IPsec is integral to the protocol |
| Usage                  | Predominantly used                 | Increasing adoption for new networks |



## TCP
**T**ransmission **C**ontrol **P**rotocol

- connection-oriented communication protocol in computer networking. It ensures reliable and ordered data transmission between devices by establishing and managing connections, performing error-checking, and retransmitting lost data when necessary. TCP is part of the Internet Protocol suite and is widely used for applications like web browsing, email, and file transfers.

## 3 steps of conNection process
1. Connection estabilishment (Three-way handshake)
   - SYN
   - SYN-ACK
   - ACK
2. Data transfer
3. Connection Termination
   - FIN
   - ACK
   - FIN
   - ACK

## Subnetting
### IP Subnet Masks (IPv4)
- Subnet masks are used in IPv4 to define network boundaries by indicating how many bits in an IP address represent the network portion and how many bits represent the host portion. Subnet masks are essential for routing and segmenting IP networks, allowing devices to communicate within the same network and routing data between different networks.
