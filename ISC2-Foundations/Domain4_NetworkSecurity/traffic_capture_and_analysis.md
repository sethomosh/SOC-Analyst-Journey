# Traffic Capture & Analysis

## Tools
- tcpdump (capture)
- tshark (command-line analyze)
- Wireshark (GUI for screenshots)

## Capture example
# capture all host traffic for 60s:
sudo timeout 60 tcpdump -i any -w artifacts/network_capture.pcap

## Basic tshark parses
# top talkers:
tshark -r artifacts/network_capture.pcap -q -z conv,ip

# show HTTP requests (if any):
tshark -r artifacts/network_capture.pcap -Y http -T fields -e ip.src -e http.request.method -e http.host -e http.request.uri

## Notes
- Always include timestamps and interface in screenshots.
- Save markup of packet bytes for suspicious packets (use Wireshark export).

