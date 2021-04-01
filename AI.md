# AI Orientation for JavaScript developers

### What are the most popular frameworks? 
TensorFlow (developed by Google), MxNet, PyTorch (used by Tesla), Keras, etc.

### Is there interoperability between frameworks? 
Surprisingly yes, it is called ONNX, it is built and maintained by Microsoft. ONNX supports conversion from and to [17 different frameworks](https://onnx.ai/supported-tools.html#buildModel) (with various limitations). ONNX is like a .docx format, which was originally created by Microsoft Word, but now supported by Libre, Pages, Google Docs and others. So you can save PyTorch model to ONNX format. But ONNX is also a runtine for executing models. 

### Is it possible to run in nodeJS? 
Yep, with [ONNX.js](https://github.com/microsoft/onnxjs) runtine, which is awesome, it runs in Node, browsers, mobile browsers, and likely in webview in React Native (need to check). ONNX has CPU, WebAssembly (wasm) and WebGL (for GPU) backends. ONNX.js currently supports most operators in ai.onnx operator set v7 ([opset v7](https://github.com/onnx/onnx/blob/master/docs/Operators.md)). Support for [ai.onnx.ml operators](https://github.com/onnx/onnx/blob/master/docs/Operators-ml.md)) is coming soon. 
Your milage may vary though, e.g. Keras.js and TensorFlow.js don't support wasm in browsers yet. 
Also, when you convert a model, you might need to make some adjustments, like happened during this demo at [17:31](https://youtu.be/Vs730jsRgO8?t=1051)), which otherwise was a very smooth process.

### On mobile, really? What works on mobiles and what does not?
Well, ONNX only does not do inference in browsers, but it is crazy fast. 
And it has a special runtime [optimized for smartphones](https://cloudblogs.microsoft.com/opensource/2020/10/12/introducing-onnx-runtime-mobile-reduced-size-high-performance-package-edge-devices/), which claims to be as lite as Tensoflow-Lite, but faster. Note that Tensoflow-Lite supports training on mobiles.

### Do you need CPU or GPU?
And when you can get away with CPU as GPU is not always available, e.g. low end mobiles) or too expensive in the cloud.

TBD. So far I see that Facematching, liveness detection are ok on CPU, but Voice to Text needs GPU, and requires gigantic models (gigabytes) that take time (a dozen seconds) to load to the GPU.

### How to use GPU in the browser and react native?

TBD 

### What pre-trained modes exist already?
Unlike human beings, AI does not yet learn continuously. You need to train it and the datasets need to be huge and with good variability or you will not get good accuracy (see video at [18:35](https://youtu.be/Vs730jsRgO8?t=1115)) or will get a [bias and a blowback](https://www.aclu.org/blog/privacy-technology/surveillance-technologies/amazons-face-recognition-falsely-matched-28).

Training is the most difficult part of AI, using AI (inference) is quite simple really. Luckily some pre-trained models exist, in ONNX and elsewhere (see [facematching article](https://github.com/tradle/cloudpal/blob/main/face-ai.md)).

### How we we ensure privacy? 
  - Ideally we should do inference on the client side. 
    This also saves money that otherwise are spent on server CPU, ram, GPU and videoram usage.
  - If using GPU on the server that is used by many other clients - this becomes tricky

# How AI model can be trained by bringing it to data, not data to AI (which is a bad norm now)? 
Model needs to be able to visit a million CloudPal instances, and train on each. The technique is called federated AI. But this still centralizes the model at the center. This is bad as it maintains control at the center, e.g center may withold the model from some nodes, and perform other shenanigans. There are new approaches for decentralized (P2P) federated learning.

### What types of deep learning networks exist?
TBD
Convolutional and newer, Transformer networks

### What is each type good at?
TBD
Convolutional networks are good for image classification (e.g. face matching). 
Transformers are good for NLP (natural language processing).


