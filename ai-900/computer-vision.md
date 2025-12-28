# Computer vision workloads on Azure
**Foundry Tools**: Azure Cognitive Services (also known as Azure AI Services)  

**Azure AI Face**: detailed facial analysis information. a specialized, deeper service  
**Azure AI Vision**: only returns boundbox coordinates. general image/video analysis. Can detect both landmarks  
and celebrities. Object detection.  

OCR: for non-document images  
**Document Intelligence** for reading images of documents and forms  
Both Azure AI Vision and Azure AI Document Intelligence include OCR  

**Azure AI Vision**: pre-trained models for general image tasks (analyze, read text, detect faces)  
**Azure AI Custom Vision**:  create/train a custom model using your own images for image classification and object 
detection     

## Image classification solutions
### 1. Classification Types

Solutions are often categorized by how they handle labels:

* **Binary Classification:** The simplest form, sorting images into two distinct groups (e.g., "Defective" vs.  
  "Non-defective").
* **Multi-class Classification:** Assigning an image to one of several exclusive categories (e.g., identifying  
  a specific animal species from a list of 50).
* **Multi-label Classification:** Allowing a single image to have multiple tags (e.g., a photo tagged as both  
  "Sunset," "Beach," and "Summer").

### 2. Core Functional Features

* **Confidence Scoring:** Instead of a simple "yes/no," the system provides a probability score (e.g., "98% Dog,
  2% Cat"). This allows businesses to set "human-in-the-loop" thresholds for low-confidence results.
* **Automated Feature Extraction:** Unlike older methods, modern solutions use **Convolutional Neural Networks
  (CNNs)** to automatically learn which visual patterns (edges, textures, shapes) are important for the
  classification task.
* **Data Augmentation:** To improve accuracy, solutions "create" more training data by taking existing images and
  applying random rotations, flips, or color shifts, making the model more robust to different lighting and angles.
* **Transfer Learning:** This allows a model to use "knowledge" from a massive general dataset (like ImageNet) and
  fine-tune it for a specific niche task, significantly reducing the amount of data and time needed for training.

### 3. Integrated Tooling & Metrics

| Feature                    | Description |
| -------------------------- | --- |
| **Preprocessing Pipeline** | Automatically resizes, crops, and normalizes images to fit model requirements. |
| **Inference API**          | A gateway that allows other software to send an image to the model and receive a label in real-time. |
| **Confusion Matrix**       | A diagnostic tool that shows exactly which classes the model is confusing (e.g., mistaking "Wolf" for "Husky"). |
| **Precision & Recall**     | Specific metrics that measure how reliable the model is for a particular label versus how many it missed. |

### 4. Advanced Features

* **Explainable AI (XAI):** Uses "heatmaps" (like Grad-CAM) to show which specific pixels in the image led
  the model to its conclusion.
* **Region of Interest (ROI):** Focuses the classification on a specific part of the image rather than the
  entire background.
* **Multimodal Search:** Allowing users to find images using text descriptions (e.g., "Find all photos of
  red trucks in the rain").

## Object detection solutions
Object detection solutions in AI focus on identifying, classifying, and locating objects within images or video.  

## Video features - Azure AI Video Indexer
* Face Detection
* OCR
* Content Moderation
* Scene Changes
* People Tracking
  
## Audio features
* Speech-to-Text (STT)
* Text-to-Speech (TTS)
* Emotion detection
* Speaker Recognition & Diarization
* Translation
* Automatic Language Detection
* Keyword and Named Entity Extraction
  
