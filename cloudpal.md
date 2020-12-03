This is the primer on CloudPal

CloudPal as one of the personal devices in a person's multi-device setup, which includes mobiles, tablets, laptops, desktops, home NAS and home automation, wearables like watches, etc. 
Without a personal Cloud component, which is consumer-friendly, always-on and zero-maintenance, we will always be dependent on Big Tech in the middle. 

## Business model
Data Centers will operate CloudPal, not us, to create full decentralization and full separation of roles. 
In this sense from a business model point of view we are more like Microsoft MS DOS for cloud than a VPS vendor or AWS. 
But probably a better analogy is the Red Hat. 
They proved Open Source is Big Business and since Cloud is soon to be a trillion dollar market, CloudPal will be a Big Business, 
because Cloud does not have today a Personal Computing segment yet (VPS is not a consumer offering).

## Technical design
Key CloudPal OS components are Software-Defined Network, Data and Compute:
Network. [Single tenant Network](https://github.com/tradle/simplecloud) is our first commercial product, 
a personal VPN with a private overlay network for all of the person's devices. 
Such network is the prerequisite for P2P apps down the line, and a good market entry as VPN is becoming a mass market product, but all VPNs today are SaaS products (shared VPN) and therefore can't ever be trusted. 

Our Single tenant Data stack is based on Hypercore, see the post on [why we chose it](https://github.com/tradle/why-hypercore). 
We joined this Hypercore community 4 months ago and produced so far a component they have been missing - a multi-master replicated LevelDB compatible P2P DB, see https://github.com/tradle/multi-hyperbee. This DB is the cornerstone of our platform to build CloudPal apps. We also produced a piece of documentation that they have been badly missing the FAQ. Hyperore also produced a set of other data structures that are exceptional for P2P apps - append only log which is good for audit purposes and as a message bus, the Hypertrie, the Key-Value store, that is simpler than the DB, and the Hyperdrive, which is the basis for P2P Dropbox, for personal storage.

Compute will be based on FireCracker and vmm-rust project's with single-container per MicroVM. To maximize security we will run each CloudPal app in its own MicroVM, much like Qubes OS. For ease of distribution, convenience and deployment determinism, we plan to allow app developers to package their apps as OCI containers (standardized by Docker) to run inside FireCracker MicroVM, but as one container per VM (btw lead developer for FireCracker is the lady from Romania https://github.com/aghecenco).

Performance of MicroVM is critical for the freemium business model to work. So MicroVM will not be running all the time. FireCracker boots KVM guest VM in 125ms. VM will need to be metered and the runaway processes that mine bitcoin or something ugly like that will be killed. Fast boot and VM snapshotting are critical features. VMM-Rust project recently delivered the first preview of FireCracker snapshotting that restores guest VM in 5ms.

To minimize the costs, we will need to implement the wake-on-LAN equivalent, so full integration with WireGuard and Linux routing is critical and the top priority project.

To further increase the performance we will probably also use microkernels, like OSv (see blog on this project by the Polish developer). Microkernel will speed up the MicroVM significantly by removing the unneeded barrier between OS and Userland. OSv guys are saying their boot time for the userland part is 5ms!
Hope this gives you the context to understand what role Qubes could play and what expertise you could bring to this, should you be interested in collaboration.
