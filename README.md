# DNS Spoofing Tool

## Description

This Python script is a DNS spoofing tool that intercepts DNS requests and modifies the DNS response to redirect the target to a specified IP address. The script uses `netfilterqueue` to interact with the network packets and `scapy` to analyze and manipulate the packets.

**Note:** This tool is intended for educational purposes and ethical hacking only. Unauthorized use of this tool on networks without permission is illegal and unethical.

## How It Works

1. The script captures network packets using `netfilterqueue`.
2. It checks if the packet contains a DNS request (`DNSQR`).
3. If the request is for `www.bing.com`, the script modifies the DNS response (`DNSRR`) to redirect the request to a specific IP address.
4. The packet is then forwarded to its destination.

## Prerequisites

- Python 3.x
- `netfilterqueue` Python library
- `scapy` Python library
- Root privileges (required to manipulate network packets)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Abhay-Mahanta/DNS-Spoofer
   cd DNS-Spoofer
   ```

2. Install the required Python libraries:
   ```bash
   pip install netfilterqueue scapy
   ```

3. Ensure that you have root privileges to run the script:
   ```bash
   sudo python3 dns_spoofer.py
   ```

## Usage

1. Set up your IP tables to forward DNS packets to the netfilter queue:
   ```bash
   sudo iptables -I FORWARD -j NFQUEUE --queue-num 0
   ```

2. Run the script with root privileges:
   ```bash
   sudo python3 dns_spoofer.py
   ```

3. When a DNS request for `www.bing.com` is made, the tool will spoof the response, redirecting the target to the IP address `192.168.92.133`.

## Warning

This tool should only be used in a controlled environment or on networks where you have explicit permission to perform testing. Unauthorized use is illegal and can result in severe penalties.



## License

This project is licensed under the MIT License.

---

