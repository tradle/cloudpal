# Why CloudPal must have a native app?
As we are designing the first cut of the CloudPal, a friend asked me this important question:
Why should CloudPal app be a native app on mobile and desktop and not a normal web app on any device?

I wish it could actually, as the world was better when Web apps reined. We did not have to go through the walled gardens of the App Stores, wait for days for Apple and Google to approve our apps, subject ourselves to miriad of their rules, [be forced to use their payment systems and pay the huge tax on that](https://variety.com/2020/digital/news/apple-app-store-fee-cut-developers-spotify-epic-1234834668/), risk of being deplatformed, like [Parler](https://www.theverge.com/22224860/parler-trump-deplatformed-capitol-raid-moderation-censorship-facebook-amazon-twitter), and so on.

But the reality is that the world has shifted to mobile-first 8 years ago and until something changes drastically, this is how it will stay for some time.

In this reality, the CloudPal app must be native. Here are the facts why it is what it is:

## Google and Apple do not want us to have good web apps
They make billions on app stores and jealously guard this revenue. Therefore they intentionally make Web apps second-rate citizens on mobile. Mobile web will always be slower than the native app and have limited capabilities.

## P2P
CloudPal has a P2P design at its core, and CloudPal peer is just one of the peers in a P2P network of your personal devices. 
These devices are rapidly expanding, including smartphones, watches and fitness trackers, blutooth devices like earphones, 
and health and wellness devices like scales, sleep monitors, etc., home automation (smart rings, smart locks, smart TVs, thermostats, lights, solar roof, powerwalls, Sattelite Internet, internet routers, and the surveillance devices like burglar alarms, nanny cams, [video doorbells](https://www.tomsguide.com/news/video-doorbell-horizontal-feature)), smart cars, etc.

CloudPal's mission is to connect all those devices without a central player, like Google in teh middle.
Unfortunately P2P will always be second rate in Web browsers due to the lack of storage, connectivity (no UDP and no TCP), secure keys storage, etc. 

## Key management 
Key management is almost impossible on the Web as Web browsers lack data store reliability and sophisticated encryption. 
Web browser also does not have access to secure element / enclave for generating and keeping keys 
on a tamper-resistant separate chip, that is hardware isolated from the access by other apps.
This functionality is important for Digital Identity and Crypto, which includes normal tokens and NFTs.

## Native networking
Some apps need to be native as the Web does not offer UDP and TCP/IP. And no, WebRTC, although very cool, is not a good substitute 
(unlike TCP/IP it requires a signaling server and it also leaks your private IP address). 
For example, DHT protocol that is used heavily in P2P does not work on the Web. 
Bottorrent uses uTP protocol on top of UDP, which is really good at bandwidth sharing with other apps, but not possible on the Web.

## Low-level access to OS
- VPN app needs to be native, as it requires access to OS capabilities to intercept all (or part of) network traffic. Both on mobile and desktop this is possible in native but not in Web apps.
- Bluetooth apps talking to devices needs to be native, e.g. for talking to wearables
- Apps that work in the background need to be native
- Launch screen is not truly available for Web apps on mobile
- Push notifications are not working well for Web apps on mobile
- Background operations are not possible in Web app on mobile, and this is needed for content syncing, for VPN, etc.
- Integration with PhotoID and TouchID is not available for Web apps or is very limited
- Access to other device's sensors requires a native app. The list is long: ambient light sensor, network status (am I online? am I on WiFi or Cell network), power status (how much juice is left? Am I plugged into a wall?), gyroscope, geo-fencing, etc. 
- Access to other apps, like contacts, Phone App, ability to add yourself to "Share to" and other native menus
- Camera on mobile is much better and it is handheld so allows operations not possible with the webcam. To be honest, Web app has access to camera and microphone, but the level of control is absent, or always lagging (think zoom control, HDR, choice of front or back, etc.)
- Web apps are limited in size as everything needs to be downloaded while the user is waiting. Thus native app can include heavy code, like a [new faster JavaScript engine](https://reactnative.dev/blog/2021/03/12/version-0.64).
- Native desktop app can register a new filesystem, using FUSE interface, Web app can't (mobile app can't either).
- And the list goes on and on ...

## Content creation
- Audio/visual content creation is better in a native app, and it is also depesdent on a good data object store, which is not available in Web browsers.
- Native apps have better control of the touch screen, which is critical for content creation (think slides, scrapbooks, drawing, etc.), so such apps need to be native as it heavily relies on the 
 
