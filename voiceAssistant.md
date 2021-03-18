# Voice Assistant and Privacy

Voice Assistants have grown into a [big market in the last 10 years](https://www.t4.ai/industry/voice-assistant-market-share) since Apple introduced Siri. Amazon Alexa is a leader today with Google, Apple and Microsoft sharing the rest of the market. 

Voice Assistants are an especially privacy-sensitive piece of technology. They are always on, listening for the wake word (Hey Siri, Ok Google, etc.). They are like the search engine, they know all our questions and what results were useful for us.
We give them access to many pieces of private information, like our contacts, calendar, location, and practically everything else, as this is the only way they can be trully of help to us.

As most applications on the market today, Voice Assitants ship our private information to their systems, make it available to their staff, and even share with their contractors.

CloudPal is a way for you to run Voice Assistant privately. Its design is based on all processing of your data happing on the cloiud device that you own, and no one else has access to. In addition it includes a number of components that protect your security like no other Voice Assistant on the market.

- CloudPal Voice, which like CloudPal itself, is an open source system, and thus allows any security researcher verify its operations
- CloudPal firewall that creates the network enclosure so that no data can leave the CloudPal
- CloudPal Voice apps (equivalent to Alexa Skills) are developed by 3rd parties and thus require isolation. They are executed in a secure virtual machine, that they can't escape
- A secure way to open a door in the firewall for the Voce app to communicate to a specific site on the internet, e.g. to a hotel system to order room service. This door has security measures:
    - Connecttion to 3rd party site (e.g. Hotel) is encrypted
    - The 3rd party site must be authenticated
    - The door is opened for the command to go through and closes right away
    - The door allows to pass only a small amount of data
- The connection to 3rd party site is anonymized, e.g. if you stay in the same hotel 2 times, the hotel will not know it is you.

