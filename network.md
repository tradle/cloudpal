CloudPal comes with 3 major components: personal and private Network (described here), personal Compute and [personal Data](https://github.com/tradle/why-hypercore). 

## Your Network
Today we rely on Google and other Big Tech companies to connect our devices in order to sync photos, email, and documents. In fact, most of our apps today go via some form of a central player, putting ourselves under non-stop  surveillance. 

Peer-to-Peer (P2P) decentralized apps attempt to restore the norm, but today they lack the convenience of Cloud-based apps. The judo move is not to fight Cloud, but to leverage Cloud's strength for P2P.

Enter CloudPal.

CloudPal sits on a fast and reliable network and is always on, and in this capcity it can help connect your personal devices and apps. Unlike iCloud, gmail and similar services, CloudPal is your device in the cloud, it belongs to you, controlled by you, and defends your data from intrusion on your behalf.

### A private network that you operate
You are familiar with the local network today, sitting behind your home router. But when you travel, when you go to work, when you want to add other machines, at a different location, or even your car, how do you do that? CloudPal creates an encrypted distributed network so that devices at your different locations, on different cell / WiFi networks, appear to be on one local network and can communicate without Big Tech at the center. This capability is sometimes referred to as an [overlay or a mesh network](https://undisclosed.blog/mesh-vpn/).

### Adding devices to the network
How will the devices find each other without a central server? How will we add new devices and remove them when they get stolen or replaced? Apparently the P2P tech has recently evolved to help us achieve just that. Keep reading.

### VPN, securing your privacy
Without VPN, each device on your private network will still talk to the Internet directly. With VPN all traffic to the Internet from your devices is routed through your CloudPC, and appears to the internet as if they all are sitting behind one router.  CloudPC becomes your **Personal VPN**. Without this, your devices are more easily identifiable, as coming from home, work, cafe, co-working place, hotel, or from a particular cell phone network.

## Personal vs traditional shared VPN
Traditional VPN offers protection of connecting you to the Internet securely. Yet, traditional VPN becomes your ISP, and gains knowledge of your Internet activity. This is so bad that [some experts recommend not to use VPNs at all](https://gist.github.com/joepie91/5a9909939e6ce7d09e29). Personal VPN, implemented with care, fixes does a much better job and protecting your privacy, and paves the road for Cloud apps, which VPNs do not offer today. 

| Function | Traditional (shared) VPN | Personal VPN | Notes | 
| --- | --- | --- | --- |
| All devices hide behind the VPN | Yes | Yes |
| 'No recording' of data | Impossible to verify | Yes | Any VPN decrypts your traffic and can read it in clear text. Some sell it. But here we can't read it, as it is end-to-end encrypted all the way to your own VPN, running in CloudPal.|
| 'No logging' for your browsing clicks | Impossible to verify | Yes | You run your own VPN. You choose to log or not to log. By default - no logging|
| Unlimited number of devices | No | Yes | Use it on your phone, tablet, laptop, desktop. Use it yourself, give to your kids |
| Virtual network for all your devices| No | Yes | That is direct connections betweem your devices, no matter where they are. Apps that use this, feel magical. Stay tuned... |

### Beauty of the modern network design
- **Stay connected**. Hop in the car while on a WhatsApp call and the handoff from WiFi to Cell network will be seamless. Close the lid of your laptop, open it and you are online almost instantly. Feels so nice compared to leading VPN services on the market!
- **Faster connection**. VPNs usually make your connection slower. Here you will not notice it! (we use [WireGuard](https://docs.sweeting.me/s/wireguard#) which is [58% faster than OpenVPN](https://restoreprivacy.com/vpn/wireguard-vs-openvpn/), commonly used by the VPNs).

### Common VPN features
- **Stop password and data theft** by securing your line on public WiFi (cafe, airport, hospital, etc). Public WiFi is the feeding ground for hackers-in-training, it is that easy to spy on you there. Use VPN. Stay safe!
- **Privacy from others on local network**. You may not be on a public WiFi, but a guest in AirBnb, hotel or visiting some company and are connecting to their network. Stay safe!
- **Privacy from ISP**. No more snooping by your internet provider. This includes your mobile operator too! They see all your browsing and may record your browsing history and sell it. Yikes!


### Unique Privacy features
- **You run VPN in the privacy of your own CloudPal**, and the only thing better than that is to run a dedicated machine on a reliable broadband network, but how many of us can be bothered doing that?
- **CloudPal is yours, with amazing privacy apps upcoming, get a discount for them now**. 
- **Pay with the cryptocurrency** if you like to avoid giving us your name and the payment card when signing up.
- **Magical private network for all your devices**. Yes, it sounds like Apple-speak, but seriously, it feels magical to have all your devices across the globe, including your CloudPal, on one virtual network chatting securely. Seriously, this was what Enterprises are still paying big bucks for. And without Google or anyone else in the middle! Is that even possible? Now those among you that are techies, think of the Peer to Peer apps which you can make from this! [Give us a shout on the support forum](https://discord.gg/343jUAKP) - we have a dozen ideas for you and will even help you build them!

### Premium features
- **Privacy from websites**. By default with this service, the websites you visit will see the same IP address that they would, when you are not using this service. We offer an option of assigning you a new temporary IP address for every session to avoid snooping by the websites.

### Planned features
- **Direct connections**. We will currently relay all traffic between devices via your CloudPal. But it is sometimes possible to establish a direct connection between devices. This is not easy as all devices nowadays work behind the firewalls that replace a device's direct IP address with the IP address of the router (NAT). We might use [Hyperswarm](https://github.com/hyperswarm/hyperswarm) for this. But the complexity of NAT is such that a multi-path network might be required for reliability, [falling back seamlessly from the direct connection to the relayed one](https://news.ycombinator.com/item?id=22467879).
- **Extend to friends, family and teams** This capability will extend the private network without compromising your security. This capability has been offered to the Enterprise users by Cisco and others for awhile now. Enjoy a simplified and affordable option made for you.
- **Block ads**. Ad networks of Google, Facebook and others are snooping on our activities online. We are all well aware now that ad-based businesses have created a system of total surveillance on their users. So this option will block ads in all apps and all browsers on all your devices. No more installing browser extensions, ad blockers, etc. Simple, effective, and *constantly evolving* to counteract future surveillance tricks. We feel bad about advertisement supported services, but perhaps it is time for apps to change. CloudPal offers new breed of P2P apps that never spy on you.
- **Bypass restrictive firewalls** You may be on campus and the only traffic that is allowed to the Internet is HTTPS (while we use UDP). 
- **Add a Firewall** your devices may already have some additional protection from hackers. This is a must in addition to securing the line to Internet. But you may want more control and this option will give you that extra peace of mind, protecting all your connected devices at once. For example:
    - Do not allow outbound traffic to the internet from the CloudPal. This removes the VPN capability leaving you with a virtual network for your devices
    - Whitelist sites on the internet that are allowed
    - Blacklist sites on the internet that are not allowed
- **Securing DNS**. DNS is the address book of the Internet. It is quite old and insecure. A lot of hacks on the Internet today are based on intercepting the DNS requests and giving you the wrong address. You think to go to the bank, but you come to hacker's home. Surveillance states like to outlaw securing the DNS, as this is how they spy on their population.
- **IPv6 vs IPv4**. The Internet is running out of addresses and older IPv4 addresses often get an extra surcharge now. IPv6 addresses are more abundant than the stars in the Universe, they are usually free, but not all apps support them. So we will help bridging them.

### Will not be supported
This solution is built for privacy. If you want to use it to mask potentially illegal activity, don't - you will get in trouble. These activities may include, but not limited to:

- Torrenting the movies or other copyrighted materials. Raids on VPN-enabled torrenting happened in the past. This is your CloudPal, use it responsibly.
- Location switching to watch international Netflix shows, this violates Netflix's terms of service, and if you get locked out of Netflix, do not blame us.

We help you increase your privacy. But no privacy is absolute, even on the device you hold in your hand. So it is important for you to understand the limitations on our ability to protect you, and how we will continue to improve our solution. Read on.


## FAQ
### How can I trust what you claim here? 
We are 100% open source, so every claim can be verified by experts. We will provide official security audits in due course.

### What is a private virtual network? 
A number of open source offerings exist for this. Take a look at Tinc, Wormhole, Zerotier. Here is a technical video for [Zerotier](https://www.youtube.com/watch?v=Bl_Vau8wtgc) that does a good job explaining Software Defined Network (SDN) and Software-Defined Wide Area Network (SD-WAN) and how they relate to VPN.


