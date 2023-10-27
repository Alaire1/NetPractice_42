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
<br>

### IPv4 and IPv6 differences
  
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
<br>


## TCP
**T**ransmission **C**ontrol **P**rotocol

- connection-oriented communication protocol in computer networking. It ensures reliable and ordered data transmission between devices by establishing and managing connections, performing error-checking, and retransmitting lost data when necessary. TCP is part of the Internet Protocol suite and is widely used for applications like web browsing, email, and file transfers.

## 3 steps of connection process
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
<br>

## SUBNETTING

### IP Subnet Masks (IPv4)
- Subnet masks are used in IPv4 to define network boundaries by indicating how many bits in an IP address represent the network portion and how many bits represent the host portion. Subnet masks are essential for routing and segmenting IP networks, allowing devices to communicate within the same network and routing data between different networks.<br>

Masks can be written in two ways:
- Dot-decimal notation: `255.255.255.0`
- **C**lass **I**nter-**D**omain **R**outing" or CIDR: `/24`<br>

| Subnet Mask       | CIDR  | IP Addresses count / (usable)|
|-------------------|---------------|----------------------|
| 255.255.255.255   | /32    | 1 (0)               |
| 255.255.255.254   | /31     | 2 (0)                  |
| 255.255.255.252   | /30     | 4 (2)                 |
| 255.255.255.248   | /29    | 8 (6)                |
| 255.255.255.240   | /28    | 16 (14)                |
| 255.255.255.224   | /27    | 32 (30)              |
| 255.255.255.192   | /26    | 64 (62)              |
| 255.255.255.128   | /25    | 128 (126)                  |
| 255.255.255.0     | /24     | 256 (254)                 |
| 255.255.254.0     | /23    | 512 (510)              |
| 255.255.252.0     | /22    | 1024 (1022)               |
| 255.255.248.0     | /21    | 2048 (2046)              |
| 255.255.240.0     | /20    | 4096 (4094)              |
| 255.255.224.0     | /19    | 8190 (8188)              |
| 255.255.192.0     | /18     | 16382 (16380)               |
| 255.255.128.0     | /17    | 32768 (32766)              |
| 255.255.0.0       | /16    | 65536 (65534)              |
| 255.254.0.0       | /15    | 131072 (131070)             |
------------------------------------------------------------
<br>

## LEVELS

<details>
  <summary>Level 1</summary>

  ![Level 1](https://raw.githubusercontent.com/Alaire1/netPractice/main/images/level1.png)<br>
  **1.** Mask here is given, so three first numbers will stay the same as the Interface B1 has `104.98.23.12` all we can do is to chanage the last one to the number between 1-254, except 12 as it is already used.<br>
  **2.** Situation is similar, but mask `255.255.0.0` indicates we can change the third number to any between 0-255 and the last one to any between 1-254, except 17. Why we have 2 numbers more to choose for the third number? Beacuse the last 
</details>

<details>
  <summary>Level 2</summary>

  ![Level 1](img link)<br>
  **1.** We have to copy the mask of the connected device which is `255.255.255.224` or `/27` in CIDR notation. That means we have 30 usable last numbers to choose. What are the ranges, I will show it with a table:<br>
| Network Address | Broadcast Address | Usable Host Addresses |
|---|---|---|
| 192.168.0.0 | 192.168.0.31 | 192.168.0.1 - 192.168.0.30 |
| 192.168.0.32 | 192.168.0.63 | 192.168.0.33 - 192.168.0.62 |
| 192.168.0.64 | 192.168.0.95 | 192.168.0.65 - 192.168.0.94 |
| 192.168.0.96 | 192.168.0.127 | 192.168.0.97 - 192.168.0.126 |
| 192.168.0.128 | 192.168.0.159 | 192.168.0.129 - 192.168.0.158 |
| 192.168.0.160 | 192.168.0.191 | 192.168.0.161 - 192.168.0.190 |
| 192.168.0.192 | 192.168.0.223 | 192.168.0.193 - 192.168.0.222 |
| 192.168.0.224 | 192.168.0.255 | 192.168.0.225 - 192.168.0.254 |

<br>

The other adress on the same subnetwork of IP `192.168.150.222` has `222` at the end, so in order to fit in the range we are taking `255` and substracting `32`, which is giving us number `223`(the broadcast number of rage below) we see the number `222` from IP is less so we know it belong to that range, so for the second IP we can choose as the last number any number between `222-193` , but as we see `222` is taken so we cannot use that one

</details>

<details>
  <summary>Level 3</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 4</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 5</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 6</summary>

  ![Level 1](img link)<br>
  
 
</details>

<details>
  <summary>Level 7</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 8</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 9</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>

<details>
  <summary>Level 10</summary>

  ![Level 1](img link)<br>
  hghghh
 
</details>
