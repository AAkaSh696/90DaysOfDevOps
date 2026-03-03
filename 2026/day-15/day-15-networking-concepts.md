## Day 15 – Networking Concepts: DNS, IP, Subnets & Ports
## Task 1: DNS – How Names Become IPs

When I type google.com in a browser:
- Browser first checks local DNS cache,if not found, it asks the configured DNS resolver.
- Resolver queries root->TLD(Top Level Domain)->authoritative name server.
- DNS returns an IP address.
- Browser connects to that IP using TCP (usually port 443).

DNS Record Types:
- A → Maps domain name to IPv4 address.
- AAAA → Maps domain name to IPv6 address.
- CNAME → Alias of another domain.
- MX → Mail server record.
- NS → Name server responsible for the domain.

Run dig google.com:
- Observation: identified A record type with public IP and  TTL(Time to Live ) value =18 sec

## Task 2: IP Addressing
1. IPv4 address- 32 bit number written in decimal format , contains 4 octets ranging 0-255.
2. - Public IP- accessible on internet ( e.g. 8.8.8.8)
   - Private IP- not directly accessible on internet ,used inside private network(e.g. 192.168.1.5)
3.  Private IP Ranges:
  - 10.0.0.0 – 10.255.255.255
  - 172.16.0.0 – 172.31.255.255
  - 192.168.0.0 – 192.168.255.255
4. Run ipr addr show
  - Observation: My ip (172.31.x.x) ->private IP

## Task 3: CIDR & Subnetting
1. /24 mean in 192.168.1.0/24- Subnet mask 255.255.255.0 Total IPs: 256 Usable hosts: 254
2.  usable hosts in :
     - /24=>Subnet mask 255.255.255.0 Total IPs: 256 Usable hosts: 254
     - /16=>Subnet mask 255.255.0.0 Total IPs: 65,536 Usable hosts: 65,534
     - /28=>Subnet mask 255.255.255.240 Total IPs: 16 Usable hosts: 14
3. Why Subnet? To divide networks into smaller segments.

## Task 4: Ports – The Doors to Services
1. Port-a logical communication endpoint used by services.
2. Common ports:
  - 22 → SSH
  - 80 → HTTP
  - 443 → HTTPS
  - 53 → DNS
  - 3306 → MySQL
  - 6379 → Redis
  - 27017 → MongoDB
3. Run ss-tulnp
  -Observation: only port 22(SSH) is listening [in my test]

## Task 5: Putting It Together
1. curl http://myapp.com:8080
  Concepts involved:
  - DNS resolves myapp.com → IP
  - TCP connection established to port 8080
  - HTTP request sent over TCP
  - Response returned

  Layers involved:
  - Application → Transport → Internet

2. App can't reach DB 10.0.1.50:3306:
- Check network connectivity (ping)
- Is port 3306 open (nc / telnet)
- Check firewall/security group

## What I learned:
- DNS converts human-readable names into IP addresses.
- CIDR notation manages network sizes.
- Ports allows multiple services to run on same IP.
