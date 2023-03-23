
# PMTU Check

Mismatch in tunnel PMTU may lead to forwarding problems. This tool let's you collect the PMTU statistics from all SD-WAN tunnels and compare them to make sure PMTU and TCP MSS value matches on both ends of the tunnel.

Usage: mtu-check vmanage_ip vmanage_user vmanage_password customer-name

Script is using Python3 are requires some additional packages. All are listed in requirements.txt. You can install them manually or via pip tool using: python3 -m pip install -r requirements.txt

Output of the script is displayed in console. Each row is formatted as described below:
```
(status), peer1 (peer1 system-up) tunnel-mtu (peer1 tunnel-mtu to peer2) and peer2 (peer2 system-ip) tunnel-mtu (peer2 tunnel-mtu to peer1)
```
where status is:
- OK if tunnel-mtu matches on both ends
- NOK if tunnel-mtu doesn't match on both ends

Example:
```
NOK, peer1 (213.140.6.4) tunnel-mtu: 1438 and peer2  (213.140.5.61) tunnel mtu: 1370
OK, peer1 (213.140.6.4) tunnel-mtu: 1438 and peer2  (213.140.6.3) tunnel mtu: 1438
```