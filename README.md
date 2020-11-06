## Premise
_The world seems to swing back and forth between personal and shared economy. We are entering into another cycle of Perso
nal, Personal Cloud._ 

1. **What makes it possible**. Linux evolved in the last 5-10 years to let us create a beautful and powerful Cloud, dedicated to a personal use. We believe this is the next evolutionary cycle of Personal Computing, after PCs and Mobiles.

1. **Spinging from the shadow of Big Tech**. Despite the dominance of Megascaler / Hyperscalers, the inovation did not stop. Cloud industry is surging with the new entrants in Edge Cloud like Fly.io and with the signifant evolution among the existing ones, like Cloudflare and Fastly.com.

1. **Different from VPS** There is one area though that neither Hyperscalers nor others are working on today, a Personal Cloud. This market segment does not exist yet, with the closest to it being the VPS market. Although VPS business exists since the 1990s, its target audience has always been the techical crowd. Personal Cloud is the VPS for the mass market.

## Goals of the Personal Cloud
1. People became not just users but the product to get monetized by Facebook, Google and other SaaS app providers. Our goal is to restore the Internet to the conditions when app companies did not own our data and did not know how we chose to use their apps.
2. We live in an increasingly multi-device world, with mobile, tablets, PCs, vehicle and home automation computing devices coming online at a rapid pace. We need a personal operating system to manage those devices. To make things easier for us this personal OS can create one virtual secure network, with all devices logging into it from many places. This allows to exchange data securely between our devices. Cloud is one of such devices, with specific capabilities that enahnce operations of other personal devices. Cloud 

Personal Cloud comes with 3 major components: network, compute and data virtualization

## 1. Network (your personal VPN)

### Advantages of Personal over traditional VPN
Traditional VPN offers protection of connecting you to the Internet securely. Personal VPN does that beter and paves the road for Cloud apps that VPNs does not offer today.

| Traditional (shared) VPN | Personal VPN |
| --- | --- |
| Provider has a way to record data decrypted by the VPN | Impossibility of that |
| No logging of your browsing history promise  | Logging impossibility |
| Limited number of devices | Unlimited devices |
| Not possible | Virtual network for all your devices. Think Airdrop between any of your devices, no matter where they are |

### Common features of a VPN

- **Secure your line** on public WiFi (cafe, airport, etc.). Those are the feeding grounds even for kids learning to be hackers.
- **No snooping by your internet provider (ISP)**. They see and may record all your browsing history. Yikes!

### Premium features

- **No snooping by the websites**. By default, the websites you visit will see the same IP address that they would see when you are not using our solution. We offer an option of a temporary IP address that they will see instead. Gives you that extra protection.
- **Block ads in apps and browser**. We are all well aware now that Google, Facebook and other ad-based businesses have created a system of total surveilance on us. This option will block many of the ads for all of your devices, without you needeing to do anything. No more installing browser extensions, ad blockers, etc. We feel bad about advertisement supported services, but perhaps their time is coming to a close. Personal Cloud offers alternative apps that never take your data.
- **Pay with cryptocurrnecy** to avoid giving us your name and card when signing up.
- **Firewall** your devices may already have some protection from hackers. But you may want more control and this will give you that extra peace of mind, protecting all your connected devices at once.
- IPv6 vs IPv4

### Not supported
This solution is built for privacy. If you're doing it to mask potentially illegal activity, don't - you will get in trouble. This may include:

- This is not for torrenting of movies and other copyrighted materials
- This is not for location switching to watch Netflix shows not available in your home country

It is also important to understand the limitations on our ability to protect your privacy:

- **Defence from us**. We do not have an ability to access your data, secret keys or network activity. But as we accept payments from you, we may know who you are, if you use the credit card payment mechanism. If you do not want that, pay us please with cryptocurrency if your jurisdiction allows it.
- **Defence from the landlord**. There are two companies you need to watch out for. Your VPN provider, that is us, and the Data Center. We can't know what you are doing, as you operate your own Virtual PC, and only you have access to it. As to the Data Center, you are fairly well isolated by running in your own VM. But this is not an absolute protection. What remains is:
    - The Data Center can take your VM's operating memory snapshotand try to deduce some information from it. Note that all cloud providers have this capability. Yet, the solution for this is coming - encrypted memory for virtual machines will be possible in about a year. Note that this relates only to data in RAM, while the data kept in storage are always encrypted.
    - you will have an ability to choose the Data Center in which your Virtual PC will run.
    - your home router or your mobile on a cell phone network will reveal their network IP address to the Data Center's network. This is standard with the IP protocol used by the Internet. This does not reveal any transmitted data, just the source IP address (e.g. router) and the destination IP which is the address of your virtual machine. You can't hide the destination, but if you want to hide your source IP address, your need to look for Tor or other similar solutions. 
- **Government agency** may compel the Data Center to perform the above actions, using the due process or covertly.


