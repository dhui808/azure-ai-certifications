# Computer vision workloads on Azure
**Foundry Tools**: Azure Cognitive Services (also known as Azure AI Services)  

**Azure AI Face**: detailed facial analysis information. a specialized, deeper service  
**Azure AI Vision**: only returns boundbox coordinates. general image/video analysis. Can detect both landmarks  
and celebrities. Object detection.  

OCR: for checks and non-document images  
**Document Intelligence** for reading images of documents and forms  
Both Azure AI Vision and Azure AI Document Intelligence include OCR  

**Azure AI Vision**: pre-trained models for general image tasks (analyze, read text, detect faces)  
**Azure AI Custom Vision**:  create/train a custom model using your own images for image classification and object 
detection     

**Face Verification**: 1:1 process, answering the question: Is this person who they claim to be?  
**Face Identification**: 1:N process, answering: who is this person?
**Facial landmarks** are key points (like eye corners, nose tip, mouth edges) identified on a face  
**PersonGroup** is the correct data structure face identification  

## Image classification solutions
### 1. Classification Types

The primary output of **image classification** model is a class label for the main subject.  
**Image captioning** is more complex than classification.

Solutions are often categorized by how they handle labels:

* **Binary Classification:** The simplest form, sorting images into two distinct groups (e.g., "Defective" vs.  
  "Non-defective").
* **Multi-class Classification:** Assigning an image to one of several exclusive categories (e.g., identifying  
  a specific animal species from a list of 50).
* **Multi-label Classification:** Allowing a single image to have multiple tags (e.g., a photo tagged as both  
  "Sunset," "Beach," and "Summer").

## Object detection solutions
Object detection solutions in AI focus on identifying, classifying, and locating objects within images or video.  

### Key features
- **Detects multiple objects** in an image and returns:
  - Object name
  - Confidence score
  - Bounding box coordinates in pixels
- **Understands object relationships**, such as multiple instances of the same object in an image.

## Azure AI Vision
[Azure AI Vision](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/overview-image-analysis?tabs=4-0)  

| Feature Area       | Key Capabilities |
|--------------------|------------------|
| **Image Analysis** | Tagging, classification, captioning, object detection, smart crop, people detection, Multimodal embedding |
| **OCR**            | Printed + handwritten text extraction, multi‑language support |
| **Face**           | Detection, recognition, identification, returns Face bounding boxes, landmarks, pose |
| **Video Analysis** | Spatial analysis, movement tracking, video search |

## Azure AI Face
[Azure Face Detection](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/concept-face-detection)  

### 1. **Face Detection**
Detects one or more human faces in an image and returns:
- Bounding box coordinates  
- A unique face ID  
- Facial landmarks (eyes, nose, mouth, etc.)  
- Attributes such as:
  - Head pose: Yaw, Roll, Pitch  
  - Glasses  
  - Mask detection  
  - Blur, exposure, noise  
  - Occlusion  
  - Accessories  
  - Quality for recognition  

### 2. **Face Analysis**
Provides deeper insights into detected faces, including:
- Pose orientation (pitch, roll, yaw)  
- Presence of masks or accessories  
- Image quality indicators  

### 3. **Face Recognition**
Supports two major recognition tasks:
- **Verification** — Is this the same person?  
- **Identification** — Who is this person among a known group?  
Used for identity verification, authentication, and access control.  

### 4. **Liveness Detection**
Ensures the face in front of the camera is **real and present**, not a photo or spoof.  
Useful for secure onboarding and fraud prevention.  

### 5. **Portrait Processing**
Enhances portrait images with:
- Face beautification  
- Hair color adjustments  
- Other aesthetic improvements  
  
### Face redaction
Redact or blur detected faces of people recorded in a video to protect their privacy  

## Azure AI Video Indexer
Out-of-scope for AI-900  
[Azure AI Video Indexer](https://learn.microsoft.com/en-us/azure/azure-video-indexer/)  

### Video Indexer Enabled by Azure Arc
* Transcription	
* Translation	
* Captioning
* Key frame detection	
* Object detection	
* Scene detection	
* Shot detection	
* Summarization

### Cloud-based Video Indexer
Video models  
* Face detection
* Celebrity identification
* Account-based face identification
* OCR
* etc.

Audio models  
* Audio transcription
* Closed captioning
* etc

Audio and video models (multichannels)  
* Keywords extraction
* Named entities extraction
* Topic inference
* Artifacts
* Sentiment analysis





