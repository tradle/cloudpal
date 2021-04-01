# Faces 
## Face matching pipeline 
Face matching is an ability to recognize faces and identify them.
It can be used to match a photo ID to a selfie. 
This is so colled 1:1 matching or sometimes called face verification. 

## Face recognition 
This is a 1:N matching which is used to recognize a person's face to their face in a photo or a video. 
It is very useful for personal photo albums, and using this capability in CloudPal would insure its absolute privacy.
In KYC and fraud-prevention scenarios, this is useful to detect synthetic identities, e.g. when a person is registering for a service under a fake name. 
In this case a search against the database of all users faces is needed, which might be quite expensive.
The more extreme version is to recognize person's face on a surveilance camera on a video doorbell or inside a home. 
Corporates applications of this is in screening people at the entrance into the building / office 
and of course the most hated one, a government surveilance via CCTV cameras.

### Face detection
Detect a face in the image (bounding box). There could be multiple faces. 
Align the face compensating (math not deep learning) 

## Pipeline for face matching (also called face verification)

### Face Embeddings 
has the standard emerged on face embeddings? the reason I ask is that we would like to avoid storing images of the faces, and instead store only the embeddings. But if later we need to switch to another framework that uses different embeddings, it will be impossible.if we do not have original images
First of all, there is no standard. And each embeddings is generated specifically from a trained model. 
We can not recover the information from one model to another with the same embedding.  
And also, the one you mentioned to just stored the embeddings and convert it back to original images is called autoencoder or transformer in another form.  
It is only used to compress the information of an image and could not be used to identify features

## Deep fakes 
https://www.x-mol.com/paper/1376603357762269184
Detecting fake images of deepfake video streams that people might use to break the face recognitoin system. 
There is at least one one scenario where detecting deepfakes ia importanrt. 
When analyzing social media profile of the person to confirm their identity.

## Liveness detection
Looking into deep fakes is important in other contexts but in the context of ID matching to a selfie, it is not critical.
What is critical is to detect if the image of the ID and selfie image are original and live. So called liveness detection.
In the US the NIST defined a term for this PAD - presentation attack detection, 
and defined the standard for testing PAD products. 
Although they do not test for PAD themselves like they do with face verification and face recognition.
A couple of vendors got certified to be able to detect with 100% probability that a selfie is live and 
soon the sane will ne availble for photo IDs.
The rest we can guarantee with app using a live camera and not allowing to upload pictures from the photo album.
This is both for selfies and IDs.
