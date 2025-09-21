# IDS Lab (Lightweight with Suricata in Docker)

## Objective
Run Suricata in docker to detect simple network scans and suspicious traffic, then collect the alert log.

## Quick Docker Suricata example
# run suricata container mounted to artifacts:
docker run --rm --net host -v $(pwd)/artifacts:/var/log/suricata jasonish/suricata:latest -c /etc/suricata/suricata.yaml -i any

# generate suspicious scan from another terminal:
nmap -sS -p 1-1024 127.0.0.1

# alerts will appear in artifacts/eve.json or fast.log (depending on container config)

## Output
- artifacts/suricata_eve.json
- artifacts/ids_alerts.txt

