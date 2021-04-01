# AI Orientation for JavaScript developers

### What are the most popular open source AI frameworks? 
TensorFlow (by Google), Apache [MxNet](https://mxnet.apache.org/versions/1.7.0/api/faq/why_mxnet), PyTorch (by Facebook and used by Tesla for self-driving), Keras, etc.

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

[Face matching, liveness detection](https://github.com/tradle/cloudpal/blob/main/face-ai.md) are ok on CPU, but Voice to Text needs GPU, and requires gigantic models (gigabytes) that take time (a dozen seconds) to load to the GPU.

### How to use GPU in the browser and react native?

TBD 

### What pre-trained modes exist already?
Unlike human beings, AI does not yet learn continuously. You need to train it and the datasets need to be huge and with good variability or you will not get good accuracy (see video at [18:35](https://youtu.be/Vs730jsRgO8?t=1115)) or will get a [bias and a blowback](https://www.aclu.org/blog/privacy-technology/surveillance-technologies/amazons-face-recognition-falsely-matched-28).

Training is the most difficult part of AI, using AI (inference) is quite simple really. Luckily some pre-trained models exist, in ONNX and elsewhere (see [facematching article](https://github.com/tradle/cloudpal/blob/main/face-ai.md)).

### How we we ensure privacy? 
  - Ideally we should do inference on the client side. 
    This also saves money that otherwise are spent on server CPU, ram, GPU and videoram usage.
  - If using GPU on the server that is used by many other clients - this becomes tricky
  - AI models need to be able to visit the data, which will avoid sending data to the center, where AI is usually trained. Accuracy of AI is highly dependent on the data. Who owns the data - wins in AI.

The Model needs to be able to visit million edge computers (CloudPal instances, mobiles) and train on each. The technique is called federated AI, and was first developed by Google. This is a breakthrough in AI and now TensorFlow Federated and PyTorch federated versions exist to help coordinate the process. But federated AI still coordinates from the center, and centralizes the learnings (model) at the center. This is bad as the center maintains control, and may withold the model from some nodes, and perform other shenanigans, such as deplatforming, which happened many times recently (AWS, app stores, Twitter) and in the past (Facebook and Twitter killed their developer ecosystem). There are new approaches to address this problem. They leverage decentralized (P2P) federated learning.

### What types of deep learning networks exist?
Convolutional are traditional now and Transformers have recently made a huge splash.

### What is each type good at?
Convolutional networks are good for image classification (e.g. face matching). 
Transformers are good for NLP (natural language processing), the best example is [GPT3](https://www.theverge.com/2021/3/29/22356180/openai-gpt-3-text-generation-words-day) - you must watch [this demo](https://www.youtube.com/watch?v=PqbB07n_uQ4).


