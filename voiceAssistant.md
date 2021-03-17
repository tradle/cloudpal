# Voice Assistant and Privacy

Voice Assistants are an especially privacy-sensitive piece of technology. They are alsways on, listening to the audio, 
waiting for the wake word (Hey Siri). They are like the search engine, they know all our questions and what results were useful for us.
They are given access to many pieces of information about us and our life so that they can be trully of help, like our contacts, 
calendar, location, etc. 

We can't have all this information be known to anyone, yet, all Voice Assitant vendors do have that access, 
and even share that data with their contractors.

The alternative design include a number of components that protect your security like no other Voice Assistant on the market:

- CloudPal, which makes it possible for your data to be 100% private 
- CloudPal Voice, which like CloudPal itself is an open source system, and thus allows any security researcher verify its operations
- CloudPal firewall that creates the network enclosure so that no data can leave the CloudPal
- CloudPal Voice apps (equivalent to Alexa Skills) are developed by 3rd parties and thus require isolation. They are executed in a secure virtual machine, that they can't escape
- A secure way to open a door in the firewall for the Voce app to communicate to a specific site on the internet, e.g. to a hotel system to order room service. This door has security measures:
    - Connecttion to 3rd party site (e.g. Hotel) is encrypted
    - The 3rd party site must be authenticated
    - The door is opened for the command to go through and closes right away
    - The door allows to pass only a small amount of data
- The connection to 3rd party site is anonymized, e.g. if you stay in the same hotel 2 times, the hotel will not know it is you.

