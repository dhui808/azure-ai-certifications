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
| Feature Area       | Key Capabilities |
|--------------------|------------------|
| **Image Analysis** | Tagging, classification, captioning, object detection, smart crop |
| **OCR**            | Printed + handwritten text extraction, multi‑language support |
| **Face**           | Detection, recognition, identification, returns Face bounding boxes, landmarks, pose |
| **Video Analysis** | Spatial analysis, movement tracking, video search |

### Video features - Azure AI Video Indexer
* Face Detection
* OCR: extract account number, routing number and deposit amount from a check.
* Content Moderation
* Scene Changes
* People Tracking
  
### Audio features
* Speech-to-Text (STT)
* Text-to-Speech (TTS)
* Emotion detection
* Speaker Recognition & Diarization
* Translation
* Automatic Language Detection
* Keyword and Named Entity Extraction
  
