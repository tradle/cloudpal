# Decentralizing _Legal_ Identities

👋 Hi! This document looks into the combination of two complex things: _legal identification_ and _decentralized identification_. As there is quite a bit to unpack on each its a good idea to learn about each seperately beforehands.

That being said, here is a short primer for the problem space:

## Overview

Decentralized identity is about signing documents. You can sign documents right now with your name and signature in many countries. Decentralized identities allows for repeat signing of digital documents without talking to a server. There is no de-facto standard solution for decentralized identities at the moment but all given solutions use cryptographic structures such as public-key cryptography, hashes and signing.

There are two tricky parts about decentralized identities:

1) anonymity; in the digital space most things should be treated as eventually public, which means that any identifier may be used by anyone to track you. 

2) continuity; digital devices and setups can break and because we need anonymity it is a problem to figure out if this _new_ digital identity is still _you_ (and that the old identity can be scrapped, thanks).

---

In legal _contracts_, identity is required for regulation _(read: tax evasion)_ and conflict resolution. When banks, lawyers, legal solicitors, etc. setup contracts their manual process to proof your identity is to make sure _(broad generalization)_ to pay your taxes and to be able to reach you if you can't hold up your "end of the deal" for conflict resolution through the legal system.

A digital, legal identity describes the means to sign a document in a way that is legally acceptable to the courts and makes tax evasion less easy. This is relevant for payments in smart contracts on a blockchain, but really in any digital system. (Un)fortunately at the time of writing there is no system for this in place.

_The rest of this document will work out some puzzle pieces on our way to get a solution to decentralized legal identites that is not a compromise of annoynmity, convenience and security. Some parts may still be open questions, others might be workable solutions. It is neither a final nor definite document but rather our current state of understanding._

## Asserting a legal identity

A legal identity is described by regulations. In Japan its the use of an Inkan stamp but in western countries you may use your name, address and signature to sign a document. For some cases you may need things notarized.

The important bit about it is that local regulations specify what is acceptable as a signature in front of the law. And some important parts that all mechanisms have in common is:

- they are not infallible: a bank employee, lawyer or post officer may mistake an identity.
- they are bound to different degrees of effort: faking a school-id is easy; faking a notarized document and beaurocratic trail is harder.

New regulations have been set-up in different countries. They are not just specifying different degrees of e-signatures but also a new mechanism to prove documentat ownership at a given time:

## Proof of identity using ePassports and mobile camera feeds

[Passports](https://en.wikipedia.org/wiki/Biometric_passport) have the possibility to be read by any NFC reader, including mobile devices. The passports also contain the image that shown on the passport itself.

Advanced [Image Error analysis](http://www.errorlevelanalysis.com/) algorithms can guarantee (to a degree accepted by regulators) if an image is faked or not.

Using Visual recognition AI's it is possible to a degree with a lower error rate than humans to detect if the person in the passport is the person from the camera feed.

These three techniques combined make it possible to create a mobile application, running on your device(!) that can **assert** your identity.

## Asserting the assertion

How can we differentiate a honest assertion from a fake assertion? In the analog world we stake the reputation and careers of the officers doing the assertion to it. This is obviously not possible if the device runs on your mobile phone.

For this to work we <abbr title="not 100% certain about this statement">_likely_</abbr> need to use [trusted computing](https://en.wikipedia.org/wiki/Trusted_Computing), more specifically [Direct Anonymous Attestation](https://en.wikipedia.org/wiki/Direct_Anonymous_Attestation) to make sure that the code generating these results is actually of a given signature which has been published by an organization. (more in a follow up post on this)

In short: the combination of the code's signature the created attestation allows to make certain that a given digital assertion is not faked. For that to work a _(by all parties)_ **trusted organization** (TO) needs to publish both the algorithm and the signatures under which they run.

Just by knowing what algorithms a TO has published you can assert someone else is actually the person with a government passport, without needing to look up anything outside of your device or that person needing to lookup anything: making the whole process local first _(decentralized)_.

## Continuous Identification

You can see "the Internet"'s approach to continous identify in "private keys" of an domain identity. It is essentially centralized with the IANA as a tiny top authority and the <abbr title="Certificate Authorities">CA</abbr>s as the second-tier well-known providers of certificates.

In a decentralized context however we need to use different technologies. Currently we have two options:

a. Grouping Identities; By using more than one device that a user has, we can make sure that if the user looses one device they can still remove/add new devices as long as they are in the possession of the majority of their devices.

b. Hashed & Salted passports; The passport's data can be used to create a unique hash with a salt phrase. Multiple assertions would be able to create the same hash. Allowing a "newer" assertion to be used instead of an older one. This means, however that it would be problematic if a user looses both the passport and the (all?) mobile devices at the same time.

## Identifying against the Government

The last question is: How can the tax office identify me as party of a blockchain entry.

We imagine this can be done in a three-step process: (IRS is a stand-in for contract-relevant authorities)

1. The first party of a contract issues their public key.
2. The trusted algorithm running on the second party's device encrypts their tax/passport info with the [IRS public key](https://www.ides-support.com/) AND additionally with the first party's public key.
3. The first party decryts the info. It is still encrypted at this point and only to be read by the IRS. The first party adds the still-encrypted info to their tax returns. Giving a reference to the IRS allowing it to create the connection.

This way the persons know that either of them is a person registered by a government and they have the relevant information for expulge their relationship to the government.

_Note: if the parties wish to know about the "real identity" of each-other it should be possible._
