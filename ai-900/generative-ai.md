# Generative AI workloads on Azure
## Generative AI creates original content based on patterns from training data
Grounding: The process of porviding additional context and real-world information to the model  

Azure OpenAI Service: Access to OpenAI's large language models and embedding models.  
Azure AI Search: A managed search service that indexes and searches large volumes of your enterprise data  

Parameters: internal variables  
Hyperparameters: User-configuratable settings  

## Key Services & Capabilities
* Azure OpenAI Service: Provides access to OpenAI's models  
* Azure AI Foundry: A platform for building, testing, and deploying custom AI agents for content understanding,  
translation, and speech, accelerating innovation.  
* Azure Machine Learning (Azure ML): For building, training, and deploying custom models  
* Azure AI Services: Pre-built APIs for Vision, Speech, Language, and Cognitive Services that integrate with
  generative AI  

## Language models
* Tokennization
* Embedding: creating vectors of the tokens  
  
Transformer model represents relationships between words.  
  * Encoder block - breaks down text and converts it into converts it into a numerical representation,
    or **embedding**  
  * Decoder block - generates answers and predications.

## Responsible AI
* Identifying Harms
* Measuring Harms
* Mitigating Harms
* Following an operation and readiness plan
  
### Mitigating Harms
* Model layer: select a different model or fine-tune a model
* System layer: content filters
* Metaprompt and grounding layer: prompt engineering and grounding
* User experience layer:

## Top-P vs Top-K
**Top-P**, or nucleus sampling, is a key AI text generation setting that controls output creativity by  
selecting the smallest set of most probable next words whose cumulative probability exceeds a threshold  
'P' (e.g., 0.9 for 90%), offering a dynamic balance between focused, predictable text (low P) and  
diverse, creative responses (high P)  

**Top-K** sampling is a text generation technique that limits the model's next word choices to the k  
most probable options, introducing controlled randomness for diverse yet coherent outputs, preventing  
bizarre choices while balancing creativity with focus.  
