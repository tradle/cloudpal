# AI Orientation for JavaScript developers

- What are the most popular frameworks? TensorFlow (developed by Google), MxNet, PyTorch (used by Tesla), Keras, etc.
- Is there interoperability between frameworks? 
  Surprisingly yes, it is called ONNX, it is built and maintained by Microsoft. ONNX supports conversion from and to [17 different frameworks](https://onnx.ai/supported-tools.html#buildModel) (with various limitations). ONNX is like a .docx format, which was originally created by Microsoft Word, but now supported by Libre, Pages, Google Docs and others. So you can save PyTorch model to ONNX format. But ONNX is also a runtine for executing models. 
- Is it possible to run in nodeJS? ONNX.js is awesome, it runs in Node, browser, and in mobile browsers, and viw webview in React Native. It has CPU, WebAssembly (wasm) and WebGL (for GPU) backends. ONNX.js currently supports most operators in ai.onnx operator set v7 ([opset v7](https://github.com/onnx/onnx/blob/master/docs/Operators.md)). Support for [ai.onnx.ml operators](https://github.com/onnx/onnx/blob/master/docs/Operators-ml.md)) is coming soon. 
Your milage may vary though, e.g. Keras.js and TensorFlow.js don't support wasm in browsers yet. 
Also, when you convert a model, you might need to make some adjustments, like happened during this demo at [17:31](https://youtu.be/Vs730jsRgO8?t=1051)), which otherwise was a very smooth process.
- On mobile, really? What works on mobiles and what does not?
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


