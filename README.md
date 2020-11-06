# Personal Cloud Premise
Linux evolved in the last 5-10 years to let us create a beaitful and powerful Cloud, which in the past required significant investments, as those that were made by the Megascalers (AWS, Azure and GCP).

Despite the dominance of megascaler / Hyperscalers, Cloud industry is surging with new entrants like Fly.io and wuth the signifant evolution among the existing ones, like Cloudflare, Fastly.com.

There is one area that Hyperscalers are not addressing today, a Personal Cloud. 
This segment of the market does not exist today, closest to it being the VPS. VPS business existed since 1990s but its target audience was always the techically savvy. Personal Cloud is for the mass consumer.

# Goals of Personal Cloud
Restore the Internet to the condition of  

# Components of the Personal Cloud
3 major components: network, compute and data virtualization

## Network
Why VPN?
- Secure line on public Wifi and even at home? - warp
    - wireguard on LAN
- No snooping of browsing history by ISP - warp
- No snooping by websites (via IP + cookies) - no-warp
    - $ premium  - egress NAT. Need reputation system to avoid dirty IPs
- Service mesh: VLAN for Airdrop and P2P apps
    - why do u need one? - no warp
    - maybe just VLAN, and not even VPN? 
    - teams 
- Firewall
- IPv6 vs IPv4
- PiHole to block ads in apps and browser
    - $ premium 
- keychain / passwords backup
- pay with crypto first 
- QUESTION - No logs? if I save browsing history there, can someone snoop? Must be encrypted …
- 

### Not aimed for and not supported
- Torrenting of movies and other copyrighted materials
- Geolocation switching to watch Netflix shows not available in your home country
- Anonymity of your home IP address



