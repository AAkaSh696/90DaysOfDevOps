## Day 14 – Networking Fundamentals & Hands-on Checks

## OSI vs TCP/IP Models
OSI(Open System Interconnection Model ) : 7 Layers 
- Application (Layer 7): Interacts with software applications to provide network services (e.g., HTTP, FTP).
- Presentation (Layer 6): Translates, encrypts, and compresses data for the application layer.
- Session (Layer 5): Manages sessions (connections) between computers.
- Transport (Layer 4): Handles host-to-host communication, flow control, and error correction (TCP/UDP).
- Network (Layer 3): Determines data paths and manages logical addressing (IP addresses, routers).
- Data Link (Layer 2): Defines physical addressing (MAC addresses) and handles frame synchronization.
- Physical (Layer 1): Transmits raw, unstructured bitstreams over physical media (cables, electricity, radio). 

TCP/IP(Transmission Control Protocol/Internet Protocol) : 4 layers
- Application Layer: Handles high-level protocols (HTTP, FTP, SMTP, DNS), providing user interface and network services.
- Transport Layer: Manages end-to-end communication, flow control, and error correction using TCP (reliable) and UDP (fast).
- Internet Layer: Handles routing and logical addressing (IP) to ensure data reaches the correct destination.
- Network Access Layer: Manages physical transmission, addressing, and hardware (Ethernet, WiFi).

## Where Protocols Sit
- IP → Internet Layer
- TCP/UDP → Transport Layer
- HTTP/HTTPS → Application Layer
- DNS → Application Layer

One real example : curl http://www.example.com
= Application (HTTP) over TCP (Transport) over IP(Internet).

## Hands-on Checks
- identity:
  - hostname -I
  - Observation: shows my local IP address(172.31.14.114).
- Reachability:
  - ping google.com
  - Observation: 0% packet loss ,confirms host is reachable.
- Path:
  - traceroute google.com
  - Observation: Multiple hops, some intermediate routers show timeout (*).
- Ports:
  - ss -tulpn
  - Observation: tcp service listens on port 22
- Name resolution:
  - dig google.com
  - Observation: Domain resolves to multiple IP addresses, confirms DNS working correctly.
- HTTP check:
  - curl -I http://www,google.com
  -  Observation: HTTP/1.1 200 OK
- Connections snapshot:
  - netstat -an | head
  - Observation: 2 listens and 1 established connections

## Mini Port Probe
- Test SSH port locally:
- curl -I http://localhost:22

- Result: Connection successful.

- Next check if failed:
  - systemctl status ssh
  - Check firewall rules(sudo iptables -L)
 
## Reflection
- Fastest signal command: ping (quick connectivity check).
- If DNS fails: Check Application layer (DNS service) ,use dig or nslookup.
- If HTTP 500: Check application layer ,logs and service status.

## Two Follow-up Checks in Real Incident
- ss -tulpn → Verify service is listening.
- journalctl -xe → Check for runtime errors.
  
