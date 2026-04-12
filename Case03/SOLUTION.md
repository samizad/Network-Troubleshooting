# Troubleshooting Resolution Report

## Phase 1: Endpoint Discovery
- **PC-01 Error:** Found IP misconfigured as `172.168.1.3` (Wrong subnet).
- **PC-02 Error:** Default Gateway was missing or incorrect, preventing traffic from leaving the 172.16.1.0/24 network.

## Phase 2: Gateway Analysis (R1)
Upon remoting into R1, we checked the interface status:
`show ip interface brief`

**Observation:** G0/1 was set to `172.16.3.1`.
**Correction:** ```config
interface g0/1
 ip address 172.16.2.1 255.255.255.0
