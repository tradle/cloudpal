# AI Orientation for JavaScript developers

- What tools to use for what? For visual learning for audio for video etc.
- What works on mobiles and what does not?
- Is it possible to run in nodeJS?
- Is it possible to run in browser?
- On mobile?
- In react native?
- Do you need CPU or GPU and when you can get away with CPU as GPU is not always available (low end mobiles) or too expensive in the cloud
- How to use GPU in the browser and react native?
- What pre-trained modes exist already?
- Training vs using AI. Unlike human beings AI does not yet learn continuously. 
  And training is the most difficult part of AI, using AI (inference) is quite simple really. 
  Luckily some pre-trained models exist.
- How to ensure privacy? 
  - Ideally we should do inference on the client side. 
    This also saves money that otherwise are spent on server CPU, ram, GPU and videoram usage.
  - If using GPU on the server that is used by many other clients - this becomes tricky
- How AI model can be trained by bringing it to data? 
  Model needs to visit a million CloudPal instances, and train on each. 
  This is called federated AI. But this still centralizes the model at the center, 
  and center may withold the model from some nodes, and do other shenanigans.
  There are new approaches for decentralized (P2P) federated learning.
- What types of deep learning networks exist?
  Like Convolutional and newer, Transformer networks
- What each type is good at?
  Convolutional is good for image classification (e.g. face matching)
  Transformers are good for NLP (natural language processing)


