# Why should CloudPal be a netive app?

As we are designing the first cut of CloudPal, a friend asked me this important question:
Why should CloudPal app be a native app on mobile and desktop and not a normal web app on any device?

I wish it could actually, but the world has shifted to mobile-first 8 years ago and until something changes drastically, 
this is how it will stay for some time.

Here is a number of reasons why CloudPall app must be native:

## P2P

CloudPal has a P2P design at its core, and CloudPal peer is just one of the peers in a P2P network of your personal devices. 
These devices are rapidly explanding, including smartphones, watches and fitness trackers, blutooth devices like earphones, 
and health and wellness devices like scales, sleep monitors, etc., home automation (smart ring, smart lock, thermostat, lights, surveilance like burgler alarm, nanny cam, smart TV, etc.)

P2P is second rate in Web browsers due to the lack of storage, connectivity (no UDP and no TCP), and secure keys storage.

## Key management 
Key management is almost impossible on the Web as Web browser lack data store reliability and sohpisticated encryption. 
Web browser also does not have access to secure element / enclave for generating and keeping keys 
on a temper-resistant separate chip, that is hardware isolated from the access by other apps.

## Native networking
Some apps needs to be native as Web does not offer UDP and TCP/IP. And no, WebRTC, although very cool, is not a good substitute 
(unlike TCP/IP it requires a signaling server and it also leaks your private IP address). 
For example, DHT protocol that is used heavily in P2P does not work on the Web. 
Bottorrent uses uTP protocol on top of UDP, which is really good at bandwidth sharing with other apps, but not possible on the Web.

## Low-level access to OS
- VPN app needs to be native, as it require access to OS capabilities to intercept any network traffic, both on mobile and desktop
- Bluetooth apps talking to devices needs to be native
- Apps that work in the background need to be native
- Launch screen is not trully available for Web apps on mobile
- Push notifications are not working well for Web apps on mobile
- Background operations are not possible in Web app on mobile
- Integration with PhotoID and TouchID is not available for Web apps or is very limited
- Access to other sensors, like ambient light, network status, gyro, geo-fencing, etc. requires the app to be native 
- And the list goes on and on ...

## Content creation
Audio/visual content creation is better in a native app, and it is also depedent on a good object store, not available in Web browser.
Native apps have better control of the touch screen which is critical for content creation (slides, scrap book, other documents), 
so such apps need to be native as it heavily relies on the 

- wearables need bluetooth, which is bad in browser
    - mobile native offers sensors that web will always be behind. E.g. Tradle can’t do ID scanning, does not do good selfie, etc, and is thus offers less value on the web
    - mobile web is slower than native app

- 

