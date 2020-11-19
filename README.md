CloudPal comes with 3 major components: personal and private Network, Compute and Data. Here we focus on the Network, See separate articles on [personal Data](https://github.com/tradle/why-hypercore) and, later on, on personal Compute.

## Your Network
Today we rely on Google and other Big Tech companies to connect our devices in order to sync photos, email, and documents. In fact most of our apps today go via some form of a central player. We pay the price for this convenience with lost privacy as we put ourselves under non-stop corporate surveillance. 

Peer-to-Peer (P2P) apps today lack the convenience of cloud-based apps. The judo move it to leverage Cloud's strength for P2P.
Enter CloudPal.

CloudPal sits on a fast and reliable network and is always on, and thus it can help connect your many devices and apps. CloudPal is your device in the cloud, it belongs to you, controlled by you, and defends your data from intrusion on your behalf.

### A private network that you operate
You are familiar with the local network today, sitting behind your home router. But when you travel, when you go to work, when you want to add other machines, at a different location, or even your car, how do you do that? CloudPal creates an encrypted distributed network so that devices at your different locations, on different cell / WiFi networks, appear to be on one local network and can communicate without Big Tech at the center. 

### Adding devices to the network
How will the devices find each other without a central server? How will we add new devices and remove them when they get stolen or replaced? Apparently the P2P tech has recently evolved to help us achieve just that. Keep reading.

### VPN, securing your privacy
Each device on your private network will still talk to the Internet directly, and are more identifiable. To give you more privacy, we can route all traffic through your CloudPC. Then CloudPC becomes your **Personal VPN**, a VPN with a number of advantages and no downsides.

## Personal vs traditional VPN
Traditional VPN offers protection of connecting you to the Internet securely. Personal VPN does that better and paves the road for Cloud apps, which VPNs do not offer today. 

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

## Background
_The world seems to swing back and forth between personal and shared computing models. We are about to enter into another cycle of Personal computing, CloudPal._ 

1. **What makes this possible**. Linux evolved in the last 5-10 years to let us create a beautful and powerful Cloud, dedicated to a personal use. We believe this is the next evolutionary cycle of Personal Computing, after PCs and Mobiles.

1. **Cloud commoditization**. Despite the dominance of Megascaler / Hyperscalers, the innovation on the Edge did not stop, with Cloudflare and Fastly.com adding serverless compute, Virtual Private Server (VPS) providers like Linode, Digital Ocean, Vultr etc. adding AWS S3-compatible Object Storage and other services, popularized by AWS. 

1. **Get ready for VPS++** There is one area though that neither Hyperscalers nor others are offering today, a CloudPal for consumers. Although VPS business has existed since the 1990s, its target audience has always been the technical crowd. 

## Goals of CloudPal
1. We all now understand that we became not just the beneficiaries of the Internet, but the product monetized by Facebook, Google and other SaaS companies (SaaS stands for Software as a Service). We give our all private emails to Gmail, our most precious ideas and private data to Google Drive, we are being watched and tracked by SaaS apps whereever we go and whatever we. Companies that make those SaaS apps are listening to our bedroom conversations, recording inside our homes, etc. etc. It is insane but there is no other way to get the conveniences we are all used to. This is about to change.
CloudPal will restore the Internet to the prior conditions when app companies did not own our data and did not know how we chose to use their apps.

2. We live in an increasingly multi-device world, with mobiles, tablets, PCs, vehicle and home automation computing devices coming online at a rapid pace. We need a personal system to manage those devices and help them exchange data securely. Consider CloudPal as one of such devices, a linchpin in such a system, helping connect, sync, coordinate, recover and transition all other devices. CloudPal is the most reliable of our devices, the most adaptive to our network, storage and processing needs. CloudPal is also the one that evolves the fastest of them all.

## FAQ
### How can I trust what you claim here? 
We are 100% open source, so every claim can be verified by experts. We will provide official security audits in due course.

### What is a private virtual network? 
A number of open source offerings exist for this. Take a look at Tinc, Wormhole, Zerotier. Here is a technical video for [Zerotier](https://www.youtube.com/watch?v=Bl_Vau8wtgc) that does a good job explaining Software Defined Network (SDN) and Software-Defined Wide Area Network (SD-WAN) and how they relate to VPN.

### CloudPal vs Virtual Private Server in the cloud (VPS)
VPS is what existed even before Cloud, they are being sold by Linode, DigitalOcean, OVH and a dozens of others
How is CloudPal different?

|Function|CloudPal|Typical VPS|
| -- | -- | -- |
|**Target audience**| Normal people | Techies |
|**Isolation**| Townhouse-style. You have your own roof - it is a full Virtual Machine (VM), not a leaky container, like some VPSes are. | Apartment-style, expect the need to talk to superintedant |
|**Privacy**| Service provider (Data Center) does not know who you are. You buy a ticket from Tradle and pay with it to the Data Center | VPS provider got your name and credit card |
|**Checks and balances**| We, your product developer are not your service provider. This gives you proivacy and leverage over both of us. Move any time to another Data Center for whatever reason, no need to lose remaining monthly payment and setup a new account. | You are at the mercy of your VPS provider |
|**Moving target for hackers**| We make it hard for hackers, like skeet shooting, no like shooting stars. CloudPal activates and de-activates as you need it, this is how we keep our prices low, and make it harder for hackers to hit you. | Sitting ducks |
|**Open Source**| Yes, we do not know any other provider that is Open Source (tell us if we missed another brave soul). Does it make it hard for us to make money? You bet, but we figure this is the only way you can trust us. | Any hidden surveilance cameras in your appartment? Who knows. No way to verify their claims. They likely also use open source software, and also the prorietary one ... | 
|**Apps**| Consumer apps. So far we have a Private network for all your devices (which includes VPN), document Vault. | Apps for techies | 
|**Snooping by Data Center** | Data Center does not know who you are. Your payment ticket did not carry any idetifiable data. The only way Data Center can snoop on you with CloudPal is by takeing a snapshot of operating memory on your CloudPal. If your VPS provider did not tell you that, this is the truth and we must say it as it is. Your data in storage is encrypted, your data on the wire is encrypted, your data in the Vault is never ever exposed, but not when data is being processed in any way (and Vault data is not), then it theretically can be taken a picture of. But don't despair. Encrypted memory upcoming. This will give you even more protection from the landlord, the Data Center.| |

| **No snooping by us**. | We do not have an ability to access your data, secret keys or network activity. But as we accept payments from you, we may know who you are, if you use the credit card payment mechanism. If you do not want that, pay us please with cryptocurrency if your jurisdiction allows it. ||

- **Limiting Data Center's powers of snooping**. There are two companies you need to watch out for. Your VPN provider, that is us, and the Data Center. We can't know what you are doing, as you operate your own CloudPal, and only you have access to it. As to the Data Center, you are fairly well isolated by running in your own VM. But this is not an absolute protection. What remains is:
    - The Data Center can take your VM's operating memory snapshot and try to deduce some information from it. Note that all cloud providers have this capability. Yet, the solution for this is coming - encrypted memory for virtual machines will be possible in about a year. Note that this relates only to data in RAM, while the data kept in storage are always encrypted.
    - you will have an ability to choose the Data Center in which your CloudPal will run.
    - your home router or your mobile on a cell phone network will reveal their network IP address to the Data Center's network. This is standard with the IP protocol used by the Internet. This does not reveal any transmitted data, just the source IP address (e.g. router) and the destination IP which is the address of your virtual machine. You can't hide the destination, but if you want to hide your source IP address, your need to look for Tor or other similar solutions. 
- **Government agency**. CloudPal drastically increases your privacy, but the government agency may come knocking. We can't help such an agency, as we have no access to your CloudPal. The government can and will be able to compel the Data Center to perform the above actions, using the due process or covertly. You need to obey the law of your jurisdiction.
