## Your Network
Cloud PC connects all your devices in a private network. 

You have a local private network today behind your home router. CloudPC creates an encrypted network so that devices at different locations and on different cell / WiFi networks appear to be on one local network. Why do I need it, you ask? Today we rely on Google and other Big Tech to connect us and sync photos, notes, email etc. bewteen our divices. We pay the price of lost privacy for that. To rebuild the Internet that does not rely on Big Tech, we need several things. Virtual network is the first step, it allows apps to connect peer-to-peer, without a central server, the way Internet was originally built.

Each device on your private network still talks to the Internet directly. But you can instead switch them to go to the Internet via your CloudPC. Then it becomes a **Personal VPN**.

### Personal vs traditional VPN
Traditional VPN offers protection of connecting you to the Internet securely. Personal VPN does that beter and paves the road for Cloud apps, which VPNs do not offer today. 

| Function | Traditional (shared) VPN | Personal VPN | Notes | 
| --- | --- | --- | --- |
| All devices hide bihind the VPN | Yes | Yes |
| 'No recording' of decrypted data | Impossible to verify | Yes | We do not run own VPN server, you do - on your own Cloud PC|
| 'No logging' for your browsing clicks | Impossible to verify | Yes | You run your own VPN. You choose to log or not to log. By default - no logging|
| Unlimited number of devices | No | Yes | Use it on your phone, tablet, laptop, desktop. Use it yourself, give to your kids |
| Virtual network for all your devices| No | Yes | Think Airdrop between any of your devices, no matter where they are. Apps that use this, feel magical. Stay tuned... |

### Beauty of the modern design
- **Stay connected with network interruptions** Hop in the car while on WhatsApp call and the handoff from WiFi to Cell network will be semaless. Close the lid of your laptop, open it and you are online almost instantly. Feels so nice compared to leading VPN services on the market!
- **VPN usually makes your network slower** Here you will not notice it! (we use WireGuard which is [58% faster than OpenVPN](https://restoreprivacy.com/vpn/wireguard-vs-openvpn/), commonly used by the VPNs).
- **VPN usually transfers more data hurting your data plan**. Here the overhead is minimal!

### Common VPN features
- **Secure your line on public WiFi** (cafe, airport, etc). Public WiFi is the feeding ground for hackers-in-training, it is that easy to spy on you there. Use VPN. Stay safe!
- **No more snooping by your internet provider (ISP)**. This includes your mobile operator too! They see all your browsing and may record your browsing history. Yikes!

### Unique Privacy features
- **You run VPN in the privacy of your own Cloud PC**, and the only thing better than that is to run a dedicated machine on a reliable broadband network, but how many of us can be bothered doing that?
- **Cloud PC is yours, with amazing privacy apps upcoming, get a discount for them now**. 
- **Pay with the cryptocurrency** if you like to avoid giving us your name and the payment card when signing up.
- **Magical private network for all your devices**. Yes, it sounds like Apple-speak, but seriosly, it feels magical to have all your devices across the globe, including your Cloud PC, on one virtual network chatting securely. Seriosly, this was what Enterprises are still paying big bucks for. And without Google or anyone else in the middle! Is that even possible? Now those among you that are techies, think of the Peer to Peer apps which you can make from this! [Give us a shout on the support forum](https://discord.gg/343jUAKP) - we have a dozen ideas for you and will even help you build them!

### Premium features
- **No snooping by the websites**. By default, the websites you visit will see the same IP address that they would see when you are not using our solution. We offer an option of a temporary IP address that they will see instead. Gives you that extra protection.

### Planned features
- **Nat traversal**. We currently relay all traffic between devices via your Cloud PC. But it is sometimes possible to establish a direct connection between devices. This is not easy as all devices nowadays work behind the firewalls that hide device's direct IP addresses (NAT). We will likely use [Hypercore's Hyperswarm](https://github.com/hyperswarm/hyperswarm) for this. 
- **Extend the private network to your distributed team or just your friends**. This capability has been offered to the Enterprise users by Cisco and others for awhile and now it is simplified and made availabe for you.
- **Block ads in all apps and all browsers on all devices**. We are all well aware now that Google, Facebook and other ad-based businesses have created a system of total surveilance on us. This option will block many of the ads for all of your devices, without you needeing to do anything. No more installing browser extensions, ad blockers, etc. We feel bad about advertisement supported services, but perhaps their time is coming to a close. Cloud PC offers alternative apps that never take your data.
- **Bypass restrictive firewalls** You may be on campus and the only traffic that is allowed to the Internet is HTTPS (while we use UDP). 
- **Add a Firewall** your devices may already have some additional protection from hackers. This is a must in addition to securing the line to Internet. But you may want more control and this option will give you that extra peace of mind, protecting all your connected devices at once. For example:
    - Do not allow outbound traffic to the internet from the Cloud PC. This removes the VPN capability leaving you with a virtual network for your devices
    - Whitelist sites on the internet that are allowed
    - Blacklist sites on the internet that are not allowed
- **Securing DNS**. DNS is the address book of the Internet. It is quite old and insecure. A lot of hacks on the Internet today are based on intercepting the DNS requests and giving you the wrong address. You think to go to the bank, but you come to hacker's home. Surveilance states like to outlaw securing the DNS, as this is how they spy on their population.
- **IPv6 vs IPv4**. Internet is running out of addresses and older IPv4 addresses often get an extra surcharge now. IPv6 addresses are more abundant than the stars in the Universe, they are usually free, but not all apps support them. So we will help bridging them.

### Not supported
This solution is built for privacy. If you're want to use it to mask potentially illegal activity, don't - you will get in trouble. These activities may include:

- Torrenting the movies and other copyrighted materials
- Location switching to watch Netflix shows, that may not be available in your home country

We help you increase your privacy. But no privacy is absolute, even on the device you hold in your hand. So it is important for you to understand the limitations on our ability to protect you, and how we will continue to improve our solution:

- **Your defence from us**. We do not have an ability to access your data, secret keys or network activity. But as we accept payments from you, we may know who you are, if you use the credit card payment mechanism. If you do not want that, pay us please with cryptocurrency if your jurisdiction allows it.
- **Your defence from the landlord**. There are two companies you need to watch out for. Your VPN provider, that is us, and the Data Center. We can't know what you are doing, as you operate your own Virtual PC, and only you have access to it. As to the Data Center, you are fairly well isolated by running in your own VM. But this is not an absolute protection. What remains is:
    - The Data Center can take your VM's operating memory snapshotand try to deduce some information from it. Note that all cloud providers have this capability. Yet, the solution for this is coming - encrypted memory for virtual machines will be possible in about a year. Note that this relates only to data in RAM, while the data kept in storage are always encrypted.
    - you will have an ability to choose the Data Center in which your Virtual PC will run.
    - your home router or your mobile on a cell phone network will reveal their network IP address to the Data Center's network. This is standard with the IP protocol used by the Internet. This does not reveal any transmitted data, just the source IP address (e.g. router) and the destination IP which is the address of your virtual machine. You can't hide the destination, but if you want to hide your source IP address, your need to look for Tor or other similar solutions. 
- **Government agency**. Cloud PC drastically increases your privacy, but the government agency may come knocking. We can't help such an agency, as we have no access to your Cloud PC. The government can and will be able to compel the Data Center to perform the above actions, using the due process or covertly. You need to obey the law of your jurisdiction.

## Background
_The world seems to swing back and forth between personal and shared computing models. We are about to enter into another cycle of Personal computing, Cloud PC._ 

1. **What makes this possible**. Linux evolved in the last 5-10 years to let us create a beautful and powerful Cloud, dedicated to a personal use. We believe this is the next evolutionary cycle of Personal Computing, after PCs and Mobiles.

1. **Cloud commoditization**. Despite the dominance of Megascaler / Hyperscalers, the inovation on the Edge did not stop, with Cloudflare and Fastly.com adding serverless compute, Virtual Private Server (VPS) providers like Linode, Digital Ocean, Vultr etc. adding AWS S3-compatible Object Storage and other services, popularized by AWS. 

1. **Get ready for VPS++** There is one area though that neither Hyperscalers nor others are offering today, a Cloud PC for consumers. Although VPS business has existed since the 1990s, its target audience has always been the techical crowd. 

## Goals of Cloud PC
1. We all now understand that we became not just the beneficiaries of the Internet, but the product monetized by Facebook, Google and other SaaS companies (SaaS stands for Software as a Service). We give our all private emails to Gmail, our most precious ideas and private data to Google Drive, we are being watched and tracked by SaaS apps whereever we go and whatever we. Companies that make those SaaS apps are listening to our bedroom conversations, recording inside our homes, etc. etc. It is insane but there is no other way to get the conveniences we are all used to. This is about to change.
Cloud PC will restore the Internet to the prior conditions when app companies did not own our data and did not know how we chose to use their apps.

2. We live in an increasingly multi-device world, with mobiles, tablets, PCs, vehicle and home automation computing devices coming online at a rapid pace. We need a personal system to manage those devices and help them exchange data securely. Consider Cloud PC as one of such devices, a linch pin in such a system, helping connect, sync, coordinate, recover and transition all other devices. Cloud PC is the most he reliable of our devices, the most adaptive to our network, storage and processing needs. Cloud PC is also the the one that evolves the fastest of them all.

Cloud PC comes with 3 major components: network, compute and data virtualization. Here we focus on the Software Defined Network designed for personal use. See separate articles on [single-tenant Personal Data system](https://github.com/tradle/why-hypercore) and on Virtual Compute (to be posted later).

## FAQ
**How can I trust what you claim here?** We are 100% open source, so every claim can be verified by experts. We will provide official security audits in due course.

**What is a private virtual network?** A number of open source offerings exist for this. Take a look at Tinc, Wormhole, Zerotier. Here is a technical video for [Zerotier](https://www.youtube.com/watch?v=Bl_Vau8wtgc) that does a good job explaining SDN and SD-WAN terms are and how they relate to VPN.

