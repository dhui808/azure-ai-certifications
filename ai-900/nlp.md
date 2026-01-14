# Natural Language Processing (NLP) workloads on Azure
* Extract information
* Classify text
* Understand questions and conversational language
* Summarize text
* Tanslate text
* Speech Synthesis

## Metrics of evaluating a language model
* Precision:True Positives / (True Positives + False Positives)
* Recall:   True Positives / (True Positives + False Negatives), percentage of actual positives that the model
  correctly identified.
* F1 Score: Single metric that combines percision and recall. Harmony mean of precision and recall
  F1=2*(Precision * Recall) / (Precision + Recall)  
  
 
Aspect-based **sentiment analysis**: identifying sentiment related to specific aspects or topics within the text  
**Sentiment** analysis does not perform the act of categorization.  
**Key phrase extraction** does not perform the act of categorization.  

Speech Synthesis Markup Language (SSML): Giving the speech engine stage directions: pronunciation, pauses, speed, 
pitch, emphasis, voice selection, and more.  

Language modeling: predicts subsequent words based on prior context.  

---
## Azure Language
[Features and Use Cases](https://learn.microsoft.com/en-us/azure/ai-services/language-service/overview#which-language-feature-should-i-use)  

Azure Language is a cloud-based service that provides Natural Language Processing (NLP) features for understanding 
and analyzing text.  Available features:
  * Named Entity Recognition (NER)
  * Personal and health data information detection
  * Language detection
  * Sentiment Analysis and opinion mining: analyze text to identify positive or negative sentiments and can link
    them to specific elements within the text.
  * Summarization
  * Key phrase extraction
  * Entity linking: to be retired
  * Text analytics for health
  * Custom text classification
  * Custom Named Entity Recognition (Custom NER)
  * Conversational language understanding: enables users to build custom natural language understanding models to
    predict the overall intention of an incoming utterance and extract important information from it.  
  * Orchestration workflow
  * Question answering

## Key phrase extraction
Key phrase extraction: the main purpose is to find the main topic of the text  

## Named Entity Recognition (NER)
Entity Recognition or **Named Entity Recognition (NER)**: identifies and  identify and categorize entities in 
unstructured text.  

After entities are detected, each entity receives a semantic label and is organized into predefined categories and types:
  * Entity Categories refer to main classifications of named entities such as Location, Organization, Date, or Quantity.
  * Entity Types: how is it different from categories?

 All entity classifications now use the type field.

 Sample output:  
```
{ 
    "kind": "EntityRecognitionResults", 
    "results": { 
        "documents": [ 
            { 
                "id": "1", 
                "entities": [ 
                    { 
                        "text": "Microsoft", 
                        "category": "Organization", 
                        "type": "Organization", 
                        "offset": 0, 
                        "length": 9, 
                        "confidenceScore": 0.97, 
                        "tags": [ 
                            { 
                                "name": "Organization", 
                                "confidenceScore": 0.97 
                            } 
                        ] 
                    }, 
                    { 
                        "text": "One", 
                        "category": "Quantity", 
                        "type": "Number", 
                        "subcategory": "Number", 
                        "offset": 21, 
                        "length": 3, 
                        "confidenceScore": 0.9, 
                        "tags": [ 
                            { 
                                "name": "Number", 
                                "confidenceScore": 0.8 
                            }, 
                            { 
                                "name": "Quantity", 
                                "confidenceScore": 0.8 
                            }, 
                            { 
                                "name": "Numeric", 
                                "confidenceScore": 0.8 
                            } 
                        ], 
                        "metadata": { 
                            "metadataKind": "NumberMetadata", 
                            "numberKind": "Integer", 
                            "value": 1.0 
                        } 
                    } 
                ], 
                "warnings": [] 
            } 
        ], 
        "errors": [], 
        "modelVersion": "2023-09-01" 
    } 
}
```

---
## Speech service capabilities
[Speech service](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/overview)  

* Speech to text
* Text to speech
  - **Speech Synthesis Markup Language (SSML)** to fine-tune the pitch, pronunciation, speaking rate,
    volume, and more  
  - **Neural voices**, which are human like voices powered by deep neural network
* Speech translation: speech to speech and speech to text translation.
* LLM speech
  - transcribe: Convert pre-recorded audio into text.
  - translate: Convert pre-recorded audio into text in a specified target language.
* Language identification
* Pronunciation assessment

### Speech to text
Also known as speech recognition, enables real-time and batch transcription of audio streams into text.  

**Custom speech** allows you to tailor the speech recognition model to better suit your application's 
specific needs.  

**Whisper model** is a speech to text model from OpenAI that you can use to transcribe or translate 
audio files.  

### Text to speech
Also known as speech synthesis  

* Standard voice (Neural)
* Custom Neural Voice

The patterns of stress and intonation in spoken language are called **prosody**  

Improve text to speech output with **SSML**  

**Visemes**: Visemes are the key poses in observed speech, including the position of the lips, jaw, and 
tongue in producing a particular phoneme.  

Text to speech with the audio content creation tool  

### Speech translation
**Realtime speech translation**  
Speech SDK or Speech CLI, Speech Studio  

* Speech to text translation
* Speech to speech translation
* Multi-lingual speech translation
* Live Interpreter
* Multiple target languages translation  

**Video translation**: translate and generate videos in multiple languages automatically.  
* Dialogue audio extraction and spoken content transcription.
* Translation from language A to B and large language model (LLM) reformulation.
* Automatic translation – voice generation in other language.
* Human in the loop for content editing
* Subtitles generation  

### LLM Speech API
LLM speech API currently supports the following speech tasks:
  * transcribe
  * translate

### Voice live API
Voice live API is a solution enabling low-latency, high-quality speech to speech interactions for voice agents.  
End-to-end solution, integrated speech recognition, generative AI, and text to speech  

### Keyword recognition (keyword spotting)
Keyword recognition detects a word or short phrase within a stream of audio.  
keyword recognition is implemented as a multistage system.
  - On-device keyword recognition (Edge, i.e. local on device)
  - Keyword verification (Cloud)

Metrics for accuracy of keyword recognition
  * Correct accept rate: Measures the system's ability to recognize the keyword spoken by a user. (true positive rate)  
  * False accept rate: Measures the system's ability to filter out audio that isn't the keyword spoken by a user.
    (false positive rate)

Keyword verification
Keyword verification is a cloud service that reduces the effect of false accepts from on-device models with robust 
models running on Azure.  
Keyword verification is always used in combination with speech to text  

###  Speaker Recognition
Speaker Recognition is used to answer the question "who is speaking?"  

### Speaker Verification
For speaker verification, the system needs at least 5 recordings (~30s each) to build a reliable voice vector.  
Speaker verification can be either text-dependent or text-independent.  

### Speaker identification
Speaker identification is the task of determining the identity of an unknown voice among a set of candidate speakers.  
The Speaker Identification API is text-independent as it does not compare what was said at the enrollment and recognition.  


