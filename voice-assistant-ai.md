# Voice assistant 
We had decades of sci-fi books and movies in which people talk to computers. 
Finally voice is here and in mass. But Houston, we have a problem! 
All those utterances from our our bedrooms and living rooms are going to BigTech.

I grew up in the former Soviet Union, and we wispered at home, 
as we knew then that the walls were listening. Now they are listening to us in the US and everywhere in the world and we gladly put ourselves
under this total surveilance.

Well we can do better. We must do better.

## Voice Assistant market
Voice Assistants have grown into a [big market in the last 10 years](https://www.t4.ai/industry/voice-assistant-market-share) since Apple introduced Siri. Amazon Alexa is a leader today with Google, Apple and Microsoft sharing the rest of the market. 

Voice Assistants are an especially privacy-sensitive piece of technology. They are always on, listening for the wake word (Hey Siri, Ok Google, etc.). They are like the search engine, they know all our questions and what results were useful for us.
We give them access to many pieces of private information, like our contacts, calendar, location, and practically everything else, as this is the only way they can be trully of help to us.

As most applications on the market today, Voice Assitants ship our private information to their systems, make it available to their staff, and even share with their contractors.

## Voice Assistant privacy requirements
CloudPal is a way for you to run Voice Assistant privately. Its design is based on all processing of your data happing on the cloud device that you own, and no one else has access to. In addition it includes a number of components that protect your security like no other Voice Assistant on the market.

- CloudPal Voice, which like the CloudPal itself, is an open source system, and thus allows any security researcher verify its operations
- CloudPal firewall that creates the network enclosure so that no data can leave the CloudPal
- CloudPal Voice apps (equivalent to Alexa Skills) are developed by any enterprising developers outside of CloudPal core team and thus require isolation. They are executed in a secure virtual machine, that they can't escape
- A secure way to open a door in the firewall for the Voice app to communicate to a specific site on the internet, e.g. to a hotel system to order room service. This door has security measures:
    - Connecttion to 3rd party site (e.g. Hotel) is encrypted
    - The 3rd party site must be authenticated
    - The door is opened for the command to go through and closes right away
    - The door allows to pass only a small amount of data
- The connection to 3rd party site is anonymized, e.g. if you stay in the same hotel 2 times, the hotel will not know it is you.
- Access to GPU is secure and private, see issue #3

## Voice asisstant pipeline
Assistant today typically goes through 4 stages: listening for the wake word, voice to text (also called automatice speech recongnition / ASR, or speech to text / STT), intent extraction, voice response. Each stage uses its own AI model, so they are quite independent. By pipeline we mean stages are executed one after another.

### Wake word listening
Alexa on a smart speaker, a Siri on iPhone or a Google Assistant on Android must always be listening to hear your call, such as "Alexa", "Hey Siri", "Ok Google", etc.
Listening requires a special AI that operates on low power to avoid draining battery. The ideal scenario is for this AI to work on the edge device and to never ship voice samples to the server.
Yet all of the current major assitants do send samples to their servers, if only for quality assurance and improvements. If CloudPal Voice is not possibble yet on the device, we will at least send it to your server, but not to ours unlike Alexa and others.

### Transcription of Voice to text
This is the stage when you issue a command or ask a question and AI needs to transcribe your voice into text. This is the heaviest of all the voice operations in Assitant and requires GPU, see issue #3.

### Understanding your intent
After that assistant needs to understand what you wanted,
and for that it uses the AI to map the transcribed text into one of the so called intents. 
Intent could be - reserve a seat in the restaurant. 
As command can be said in a variaty of ways, when intent is configured by the Voice app developer, they would provide a list of possible uterances in the textual form. This list does not need to cover all variants, usually a dozen variants are sufficient for AI to understand the intent.

### Voice response
To give a response to the user in a natural voice the predefined responses in textual form need to be rendered in audio. For that special AI networks exist that take voice artist's voice samples and use it as a basis of rendering text response as speech.

This stage is simpler as it does not need to operate in real time, as all predefined text can be rendered to voice ahead of the game and stored.

## Parameters / variables / slots
When do you want to schedule your spa visit? How many people will be coming? What procedures do you want to book at the spa?

These are variables or slots as Alexa Skills call them.
Developer needs to define them upfront. 
And STT needs to understand spoken dates, time, duration, numbers and lists of possible values (e.g. SPA procedures).


