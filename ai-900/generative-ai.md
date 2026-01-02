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
  * Decoder block - generates answers and predications. uses the embeddings calculated by the encoder to
    determine the next most probable token in a sequence started by a prompt.  

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

---
# Microsoft Foundry (Azure AI Foundry)
* Model catalog
* AI Agent Service
* Development and Deployment
* Goverance,Security and Compliance
  - Content Safety
* Observability & Monitoring

## Foundry Agent Service
**Foundry Agent Service** connects the core pieces of Foundry (such as models, tools, and frameworks) 
into a single runtime. It manages conversations, orchestrates tool calls, enforces content safety, and 
integrates with identity, networking, and observability systems.  

### AI Agents
Agents make decisions, invoke tools, and participate in workflows.  
An agent has three core components:  
* Model (LLM): Powers reasoning and language understanding.
* Instructions: Define the agent's goals, behavior, and constraints. 
* Tools

Types of agents:  
* Prompt-based
* Workflow
* Hosted

Agent components  
1. Create an agent: Define an agent to start sending messages and receiving responses.
2. Create a conversation (optional): Use a conversation to maintain history across turns.
3. Generate a response
4. Check response status
5. Retrieve the response

### Retrieval Augmented Generation (RAG)
RAG is a pattern that uses your data with an LLM to generate answers specific to your data.  

### Azure AI Search
Azure AI Search tool connects an agent to a new or existing search index. Use this tool to retrieve 
and summarize your indexed documents, grounding the agent's responses in your proprietary content.  

## Customizing models
* Using grounding data
* Implementing RAG	
* Fine-tuning
* Managing security and governance controls
  
## Observability
Evaluators are specialized tools that measure the quality, safety, and reliability of AI responses.  
* Groundedness: measures how consistent the response is with respect to the retrieved context.
* Relevance: measures how relevant the response is with respect to the query.
* Fluency: measures natural language quality and readability.
* Coherence: measures logical consistency and flow of responses.
* Content safety: comprehensive assessment of various safety concerns.

