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

###Network

[Single tenant Network](https://github.com/tradle/simplecloud) is our first commercial product, 
a personal VPN with a private overlay network for all of the person's devices. 
Such network is the prerequisite for P2P apps down the line, and a good market entry as VPN is becoming a mass market product, but all VPNs today are SaaS products (shared VPN) and therefore can't ever be trusted. 

### Data
Our single-tenant Data stack is based on Hypercore, see the post on [why we chose it](https://github.com/tradle/why-hypercore). Our team joined Hypercore community in September 2020 and has produced so far a component the community badly needed - a multi-master replicated LevelDB-compatible [P2P Database](https://github.com/tradle/multi-hyperbee). This DB is the cornerstone of the platform for people to build CloudPal apps. We have also produced a piece of documentation that Hypercore comunity has been badly missing, the [FAQ](https://github.com/tradle/why-hypercore/blob/master/FAQ.md). We think of it as a start of CloudPal documentation.

Hyperore project has produced a set of data structures that are exceptional for P2P apps - append-only log which is good for audit purposes and as a messaging bus, the Hypertrie - a Key-Value store, that is simpler than the DB, and the Hyperdrive, which is the basis for the P2P Dropbox replacement, a personal file and media storage.

### Compute 
CloudPal Compute will be based on FireCracker and the vmm-rust project with a single-container per MicroVM. To maximize security we will run each CloudPal app in its own MicroVM, much like Qubes OS. For ease of distribution, convenience and deployment determinism, we plan to allow app developers to package their apps as OCI containers (standardized by Docker) to run inside FireCracker MicroVM, but as one container per VM.

Performance of MicroVM is critical for the consumer friendly freemium business model to work. So MicroVM will not be running all the time, which is possible because FireCracker boots KVM guest VM in 125ms and [VM snapshots](https://github.com/firecracker-microvm/firecracker/blob/v0.23.0/docs/snapshotting/snapshot-support.md) boot in 5-8ms. VM will need to be metered and the runaway processes that mine bitcoin or something ugly like that will be killed. 

To minimize the costs, we will need to implement the wake-on-LAN equivalent, so a full integration with WireGuard and Linux routing is critical and is our top priority project.

To further increase the performance we will probably also [use microkernels, like OSv](http://blog.osv.io/blog/2019/04/19/making-OSv-run-on-firecraker/). Microkernel will speed up the MicroVM significantly by removing the unneeded barrier between OS and Userland. OSv guys are saying their boot time for the userland part is 5ms! 

Hope this gives any interested Open Source developers the context to understand what role they can play in this project and what expertise you could bring to this, should you be interested in collaboration.

Please reach out to us.
