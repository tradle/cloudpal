# Faces 
_For the purposes of this and other articles, we use an AI team for deep learning AI. 
In contrast to that we use the ML term for statistical and other traditional mathematical methods for visual, audio and other types of signal processing_.

## Face matching pipeline 
Face matching is an ability to find faces in larger images or videos and identify them.
It can be used to match a photo ID to a selfie. 
This is so called 1:1 matching or sometimes called face verification. 

## Face recognition 
This is a 1:N matching which is used to recognize a person's face in a photo or a video. 
It is very useful for personal photo albums, and using this capability in CloudPal would insure its absolute privacy.
In KYC and fraud-prevention scenarios, this is useful to detect synthetic identities, e.g. when a person is registering for a service under a fake name. 
In this case a search against the database of all registered faces is needed, which might be quite expensive. For that various 2-step techniques are used for finding initially a subset of potential matches (usually about 100) and then doing face matching on each of the candidates individually. 

The more extreme version of face recognition is to recognize a face as viewed via video doorbell or on a nanny camera or security camera inside a home. This one is a super privacy senstite application, great for CloudPal.
Corporates applications of this are screening people at the entrance into the building / office, 
and of course the universally hated one - government surveillance via CCTV cameras and such.

### Face detection
Face recognition starts with face detection in the image or video stream (and placing a bounding box around it). In 1:N scenarios there could be multiple faces in the stream. 

_This is done with AI._

### Face Landmarks (creating an embedding)
Facial landmarks are salient regions of the face, such as:

    Eyes
    Eyebrows
    Nose
    Mouth
    Jawline

After identifying landmarks, the face embedding is created. It is a mathematical representation of the face.
No standard has yet emerged for face embeddings. Some algorithms use 6 points, others use dozens and even hundreds of points on the face. 
_There are [ML algorithms](https://www.pyimagesearch.com/2017/04/03/facial-landmarks-dlib-opencv-python/) and AI algorithms for embeddings._

Then embeddings can be compared with each other and the resulting score indicates whether 2 images match.

In KYC settings, for privacy it is very important to avoid storing registered faces and instead to store only the embeddings. The problem is that when later we need to switch to another framework, you will need the original images. It is because we can not recover the information from the embedding from one algorithm to use in another algorithm because they use different number of landmark points, different math or different AI to produce the embeddings. And asking millions of users to upload their selfie again is practically impossible. 

### Face alignment
Today's face matching AI is still not capable of matching faces as they were presented. Faces need to be normalized to the frontal view. Facial landmarks are used for face alignment, but also for head pose estimation, blink detection and more.

Note that this step must be skipped for photo IDs to avoid unnecessary distortion and to save resources.
_This is done with ML_

## Deep fakes 
https://www.x-mol.com/paper/1376603357762269184
Detecting deepfakes in images and video streams is a hot topic today. 
Some use cases:
- User agent (browser, voice assistant) can pre-read the article of pre-watch the video to detect deepfakes
- KYC - when analyzing social media profile of the person to confirm their identity

## Liveness detection
Looking into deep fakes is important in other contexts but in the context of ID matching to a selfie, it is not critical.
What is critical is to detect if the image of the ID and selfie image are original and live. This is called liveness detection.
In the US, NIST defined a term for this PAD - presentation attack detection,
and defined the standard for testing PAD products. 
NIST does not test for PAD themselves, like they do with face verification and face recognition.
A couple of vendors got certified with the NIST with PAD-certified lab and can detect liveness with 100% probability. Soon liveness detection will be possible for photo IDs as well.
Liveness detection is used in combination with an app that only uses a live camera, not allowing the user to upload pictures from a photo album.

## Performance 
A lot of AI requires a GPU, which is a more limited and expensive resource. 
Forunately inference for face matching can work reasonably well on the CPU, and even on mobiles. Liveness detection does not yet work on mobile.

## Training AI and accuracy testing
Fortunately for face matching and recognition tasks there are pre-trained models, released to open source:
- 360K people 1.5 images [Glint360K](https://github.com/deepinsight/insightface/tree/master/recognition/partial_fc)

Testing can be done on the forllowing test datasets:
- [Labeled Faces in the Wild (LFW)](http://vis-www.cs.umass.edu/lfw/index.html)

