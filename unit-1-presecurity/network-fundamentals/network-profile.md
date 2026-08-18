# Network Profile — [Christo Topali]

## Identity
- IPv4 address: 172.20.xx.x
- Subnet mask / CIDR: 255.255.255.240
- MAC address: 80-B6-55-CC-xx-xx
- Network address: 172.20.10.0
- Broadcast address: 172.20.10.15

## Gateway and reachability
- Default gateway: 172.20.10.1
- Ping to gateway (avg): 5 ms
- Ping to 1.1.1.1 (avg): 23 ms
- Q6: What was the average round-trip time to your gateway versus to 1.1.1.1? Why is one much faster than the other?

It because default gateway belongs to the local network
## DNS
- Configured DNS server(s): 172.20.10.1
- example.com resolves to: 172.66.147.243
- Q10: A security thought: DNS lookups are usually sent in cleartext. If someone could watch your network traffic, what could they learn about you just from your DNS queries — even if all the websites you visit use HTTPS?

Even when websites use HTTPS, someone monitoring normal DNS traffic may be able to see which domain names my computer is looking up. This can give them information about the websites or online services I am using, even though they cannot normally see the encrypted webpage contents.
## Path to the internet
- Hops to example.com: 8 hops
- First hop: 3 ms     3 ms     2 ms  2001-14bb-c6-4626-f44c-6529-87dc-1469.rev.dnainternet.fi [2001:14bb:c6:4626:f44c:6529:87dc:1469]

## Listening ports
| Port | Protocol | Interface (localhost / all) | Common use |
|------|----------|------------------------------|------------|
| 49670 | TCP | all | Windows RPC / dynamic port |
| 49668 | TCP | all | Windows RPC / dynamic port |
| 49667 | TCP | all | Windows RPC / dynamic port |
| 49666 | TCP | all | Windows RPC / dynamic port |
| 49665 | TCP | all | Windows RPC / dynamic port |
| 49664 | TCP | all | Windows RPC / dynamic port |
| 24830 | TCP | localhost | Application-specific / local service |
| 5040 | TCP | all | Windows/application service |
| 135 | TCP | all | Microsoft RPC Endpoint Mapper |

- Q14: Look up what two of these ports are commonly used for (a quick web search for "port 22" or "port 445" is fine). Why does it matter, from a security standpoint, whether a port is listening on localhost only versus on all interfaces?
  
  Port 135 is used by Windows RPC, and 49664 is a dynamic Windows port.

  A port on 127.0.0.1 is only accessible from my PC, while 0.0.0.0 can be accessed from the network, so it has a bigger security risk.

- Q15: A security thought: an attacker scanning your machine sees only the ports listening on 0.0.0.0 (network-facing), not the localhost-only ones. Based on your output, is your machine exposing more or fewer network-facing services than you expected?
  
  My computer is exposing more network-facing services than I expected, since most of the ports I found are listening on 0.0.0.0.

## Reflection (150–200 words)
- What surprised you about your own network?

  What surprised me most was seeing how many ports and network services are running on my computer. I also found it interesting that my laptop has several network adapters, including virtual adapters, even when I am not actively using them.
  
- Which open port (if any) would you want to investigate or close?

  I would investigate port 135 first because it is listening on all interfaces and is used by Microsoft RPC. I would not close it immediately, because Windows may need it for normal system functions. I would first check which service is using it and whether I actually need it.
  
- Which command do you think you'll use most often, and why?

  I think I will use ipconfig /all most often because it quickly shows important network information like my IP address, MAC address, default gateway, and DNS servers. It is useful for both troubleshooting and understanding how my computer connects to the network.
