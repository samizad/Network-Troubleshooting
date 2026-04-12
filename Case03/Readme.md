# Network Troubleshooting: DNS & Inter-VLAN Connectivity

## Scenario
Users on the local network are unable to access the web server `www.cisco.pka` following a network upgrade. Your goal is to identify why PC-01 and PC-02 cannot reach the server via URL and why cross-network communication to PC-A and PC-B is failing.

## Topology
![Network Topology](./evidence/topology.png)

## Addressing Table
| Device | Interface | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **R1** | G0/0 | 172.16.1.1 | 255.255.255.0 | N/A |
| **R1** | G0/1 | 172.16.2.1 | 255.255.255.0 | N/A |
| **PC-01** | NIC | 172.16.1.3 | 255.255.255.0 | 172.16.1.1 |
| **PC-A** | NIC | 172.16.2.3 | 255.255.255.0 | 172.16.2.1 |
| **Web** | NIC | 209.165.201.2 | 255.255.255.224 | 209.165.201.1 |

## Access Credentials
- **SSH to R1:** `ssh -l Admin01 172.16.1.1`
- **Password:** `cisco12345`
