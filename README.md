# This is the primer on CloudPal

Tracking is evil, and with CloudPal we are changing this.

CloudPal is where your data is processed by *their* apps, providing you the utility and insights, but without letting app giving app developer access to your data, a total opposite of Gmail, Facebook, Quickbooks, etc.

We live in a multi-device world which is rapidly expanding. The computing devices we use are mobiles, tablets, laptops / desktops, wearables (watches, fitness trackers), AirPods and other earphones, home storage (NAS), smart TVs, home automation, and the rapidly evolving health measuring devices for weight, blood pressure, skin temperature, oxygenation, EKG, sleep, etc.

We are missing one personal device to re-own all the data we produce and stop the surveilance we agreed to today. That device is the personal Cloud device. We called it CloudPal. CloudPal syncs all your devices, stores all your data, and runs cloud apps on your data, all under your own control and no-one else's.

Without a such personal Cloud device we will always be dependent on and beholden to the Big Tech in the middle. This personal Cloud device needs to be consumer-friendly, always-on and require zero-maintenance. 

CloudPal is your assistant in the Cloud, trully personal, no compromises, no backdoors.

CloudPal is not another cloud storage, like Dropbox, CloudPal gives consumers what AWS gives to businesses, elastic on-demand compute, storage and networking.

## Goals
1. We are not app owners, we are a product monetized by Facebook, Google and other SaaS companies (SaaS stands for Software as a Service). We give all our private emails to Gmail, our most precious ideas and private data to Google Drive, we are being watched and tracked by SaaS apps wherever we go and whatever we do. Companies that make those SaaS apps are listening to our bedroom conversations, recording inside our homes, etc. etc. It is insane but there is no other way to get the conveniences we are all used to. This is about to change.
CloudPal will restore the Internet to the prior conditions when app companies did not own our data and did not know how we chose to use their apps.

2. We live in an increasingly multi-device world, with mobiles, tablets, PCs, vehicle and home automation computing devices coming online at a rapid pace. We need a personal system to manage those devices and help them exchange data securely. Consider CloudPal as one of such devices, a linchpin in such a system, helping connect, sync, coordinate, recover and transition all other devices. CloudPal is the most reliable of our devices, the most adaptive to our network, storage and processing needs. CloudPal is also the one that evolves the fastest of them all.

## Business model
Data Centers will operate CloudPal, not us, to create full decentralization and full separation of roles. 
In this sense from a business model point of view we are more like Microsoft MS DOS for cloud than a VPS vendor or AWS. 
But probably a better analogy is the Red Hat. 
They proved Open Source is Big Business and since Cloud is soon to be a trillion dollar market, CloudPal will be a Big Business, 
because Cloud does not have today a Personal Computing segment yet (VPS is not a consumer offering).

## Technical design
Key CloudPal OS components are Software-Defined Network, Data and Compute:

### Network
[Single tenant Network](https://github.com/tradle/simplecloud) is our first commercial product, 
in a form of a personal VPN with a private overlay network for all of the person's devices. 
Such network is the prerequisite for P2P apps down the line, and a good market entry as VPN is becoming a mass market product, but all VPNs today are SaaS products (shared VPN) and therefore can't ever be trusted. 

### Data
Our [single-tenant Data](https://github.com/tradle/cloudpal/blob/main/data.md) stack is based on Hypercore, see the post on [why we chose it](https://github.com/tradle/why-hypercore). Our team joined Hypercore community in September 2020 and has produced so far a component the community badly needed - a multi-master leaderless LevelDB-compatible and DynamoDB-compatible [P2P Database](https://github.com/tradle/multi-hyperbee). This DB is the cornerstone of the platform for people to build CloudPal apps. We have also produced a piece of documentation that Hypercore comunity has been badly missing, the [FAQ](https://github.com/tradle/why-hypercore/blob/master/FAQ.md). We think of it as a start of CloudPal documentation.

Hypercore project has produced a set of data structures that are exceptional for P2P apps - append-only log which is good for audit purposes and as a messaging bus, the Hypertrie - a Key-Value store, that is simpler than the DB, and the Hyperdrive, which is the basis for the P2P Dropbox replacement, a personal file and media storage.

### Compute 
CloudPal Compute is a serverless system, based on [FireCracker](https://firecracker-microvm.github.io/) and [rust-vmm](https://github.com/rust-vmm) projects. To maximize security each CloudPal app runs in its own MicroVM, much like [Qubes OS](https://www.qubes-os.org/) does it. For ease of distribution, convenience and deployment determinism, we will let app developers package their apps as OCI containers (standardized by Docker), but we will not use Docker runtime, and will execute the app directly in a single FireCracker MicroVM.

Performance of MicroVM is critical for the consumer friendly freemium business model to work. So MicroVM will not be running all the time, which is possible because FireCracker boots KVM guest VM in 125ms and [VM snapshots](https://github.com/firecracker-microvm/firecracker/blob/v0.23.0/docs/snapshotting/snapshot-support.md) boot in 5-8ms. VM will need to be metered and the runaway processes that mine bitcoin or something ugly like that will be killed. 

To minimize the costs, we will need to implement the wake-on-LAN equivalent, so a full integration with WireGuard and Linux routing is critical and is our top priority project.

To further increase the performance we will probably also [use microkernels, like OSv](http://blog.osv.io/blog/2019/04/19/making-OSv-run-on-firecraker/). Microkernel will speed up the MicroVM significantly by removing the unneeded barrier between OS and Userland. OSv guys are saying their boot time for the userland part is 5ms! 

## CloudPal vs VPS (Virtual Private Server)
VPS is what existed even before Cloud, they are being sold by Linode, DigitalOcean, OVH and a dozens of others
How is CloudPal different?

|Function|CloudPal|Typical VPS|
| -- | -- | -- |
|**Target audience**| Normal people | Techies |
|**Isolation**| Townhouse-style. You have your own roof - it is a full Virtual Machine (VM), not a leaky container, like some VPSes are. | Apartment-style, expect the need to talk to superintedant |
|**Privacy**| Service provider (Data Center) does not know who you are. You buy a ticket from Tradle and pay with it to the Data Center. At the same time Tradle is not a service provider, which means we do not know what and where you run. | VPS provider got your name and credit card *and* also launches the VM, so they have full power to do surveilance on you|
|**Checks and balances**| We, your product developer are not your service provider. This gives you proivacy and leverage over both of us. Move any time to another Data Center for whatever reason, no need to lose remaining monthly payment and setup a new account. | You are at the mercy of your VPS provider |
|**Moving target for hackers**| CloudPal VM activates and de-activates as needed, this is how we keep our prices low, and it also makes it much harder for hackers to hit it. | Sitting ducks |
|**Open Source**| Yes, we do not know any other provider that is Open Source (tell us if we missed another brave soul). Does it make it hard for us to make money? You bet, but we figure this is the only way you can trust us. | Any hidden surveilance cameras in your appartment? Who knows. No way to verify their claims. They likely also use open source software, and also the prorietary one ... | 
|**Apps**| Consumer apps. At this point we offer a Private network app for all your devices (which includes VPN capability), and are planning to release a document Vault, collaborating on documents with friends and family, media sharing and many other apps from P2P software developers. Many of them will be open source so you can trust them more. | Apps for techies | 
| **No snooping by us**. | We do not have an ability to access your data, secret keys or network activity. The way we implemneted the payment system, we can't connect your name and the CloudPal you are running |VPS provider knows who you are |
|**Limiting Data Center's powers of snooping**| With CloudPal, the Data Center does not know who you are, since your payment ticket did not carry any identifiable data. The only way Data Center can snoop on you with CloudPal is by takeing a snapshot of operating memory on your CloudPal and try to deduce some information from it. Note that all cloud providers have this capability. Yet, the solution for this is coming - encrypted memory for virtual machines will be possible soon. Note that this relates only to data in RAM. Your data in storage and on the wire are always encrypted. | They know your name and all payment details |Worse, as VPS provider knows who you are |
|**Network sooping**| Data Center can trace source address of the traffic and the address where it is heading out. Your home router or your mobile on a cell phone network will reveal their source address to the Data Center's network. This is standard for any VPS provider. To hide your IP address you need to use I2P, Tor or other similar solutions. You need to understand the law of your jurisdiction, and that the government can compel the Data Center with the due process or covertly. | Worse, as VPS provider knows who you are |

## Background
_The world seems to swing back and forth between personal and shared computing models. We are about to enter into another cycle of Personal computing._ 

1. **What makes this possible**. Linux evolved in the last 5-10 years, opening proprietary solutions used by Cloud vendors so that we can now create a beautful, powerful and open Cloud, dedicated to the personal use. 

1. **Cloud commoditization**. Despite the dominance of Megascalers / Hyperscalers, the innovation on the Edge did not stop. CDN vendors like Cloudflare, Fastly abd Fly.io have added serverless compute. VPS providers like Linode, Digital Ocean, Vultr have added AWS S3-compatible Object Storage.

1. **Get ready for VPS++** There is one area though that neither Hyperscalers nor others are offering today, a Cloud,  sold directly to consumers. Although VPS business has existed since the 1990s, its target audience has always been the technical crowd. 

## CloudPal vs SOLID
[SOLID (Social Linked Data)](https://en.wikipedia.org/wiki/Solid_(web_decentralization_project)) is a web decentralization project led by Tim Berners-Lee, the inventor of the World Wide Web, developed collaboratively at the Massachusetts Institute of Technology (MIT). Like SOLID, Tradle aims for web decentralization. Unlike SOLID, Tradle creates a complete new Cloud stack, designed for personal use.

|Function|CloudPal|SOLID|
| -- | -- | -- |
|**Target audience**| Normal people | Techies |
|**Decentralized**| Yes | Yes |
|**Open source**| Yes | No |
|**Data self-sovereignty**| Yes | Yes |
|**Data interlinking**| Yes | Yes |
|**Language for Semantics**| Yes | Yes? |
|**Data streaming**| Yes | No |
|**Bandwidth sharing**| Yes | No |
|**Messaging**| Yes | No |
|**File Systen**| Yes | No |
|**Database**| Yes | No |
|**Object store base**| Yes | Yes |
|**Data Integrity**| Yes | No? |
|**Blockchain audit**| Yes | No |
|**AI**| Yes | No? |
|**Local first offline first**| Yes | No |
|**Compute**| Yes | No |
|**Virtual networking**| Yes | No |
|**App Store**| Yes | No |
|**Universal a  front-end**| Yes | No |
|**Digital identity**| Yes | No |

## Community - call for action
Hope this gives an Open Source developer the context to understand what role you can play in this project and what expertise you could bring to this, should you be interested in a collaboration with us.

Please reach out to us at info at tradle dot io.
