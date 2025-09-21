# VPN Lab — WireGuard (quick demo)

## Objective
Demonstrate encrypted traffic across an interface and prove confidentiality on the wire (pcap shows encrypted payloads).

## Quick WireGuard steps (local two-endpoint demo)
- install wireguard (Ubuntu: sudo apt install wireguard)
- create keys, config wg0 for a peer on the same machine or another VM
- start wg, transfer a file or ping across wg interface
- capture traffic on host interface (not the wg interface) to show encrypted packets:
  sudo tcpdump -i eth0 -w artifacts/vpn_traffic_before_after.pcap

## Evidence
- artifacts/wg_show_output.txt (wg show)
- artifacts/vpn_traffic_before_after.pcap (pcap of encrypted traffic)
- screenshot of Wireshark showing encrypted packets (no cleartext HTTP)

