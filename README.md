# Day 2 -> RAG Systems (Retrieval-Augmented Generation)

- Thanks to @https://github.com/Jaskirat-singh04 for the session on RAG systems and the hands on coding for the Winter School Python with Gen AI_Day-2_Rag-agent Colab notebook.

## RAG is a framework and not an architecutre

- Framework that combines the question and the relevant chunks to obtain the answer.
- The asked question by the user is checked by retriever that retrieves that fixed data from the knowledge base (which is separated and broken down into chunks and embedded into numerical values, each numerical value of a word is mapped to the word itself, which finally passes the word chunks) to the LLM instead of the complete knowledge base at once. Only the relevant chunk of the knowledge base is passed (Context Window Problem - fixed LLM memory causes LLM's to forget crucial details in long chats/conversations leading to errors, hallucinations, and decreased accuracy)
- There is a slight overlapping between chunks to build a better connection between them and the selected chunk provides slight context about its previous and next chunks.
- In the retriever, the number of chunks to retrieve is determined by the top-k parameter, a value that is set by the system designer, not determined automatically by the system itself. A small k risks missing crucial info, while a large k adds computational cost and noise.
- User query, relevant chunks, system instruction are the 3 most important parts of the context builder (prompt assembly).
- RAG's take multiple types of data - text, images (text extracted by OCR), videos (text extracted from audio transcripts) and many other types of data.

## Notion document - https://www.notion.so/RAG-Pipeline-with-LangChain-Google-Gemini-and-Agents-2e514dc3f1ec8051835cfb236da43fa9

## Colab Notebook Copy created and added to drive

# Day 3 -> AI Agents and Automation

- Thanks to @https://github.com/Tush-hub for the session on AI agents and Automation and the hands on coding session.

## Basics of AI Infrastructure -

- GPU (Graphic Processing Unit) is a specialized processor designed for parallel processing (Key task in AI). It is excellent for tasks that require massive data calculations.
- TPU's (Tensor Processing Unit) AND NPU's (Neural Processing Unit) exist beyond GPU's offering even higher computation power.

## How AI thinks -

- Tokens - Breaking down the key query/sentence into key words that are tokens, excluding words like is/and/are/or etc.
- Embeddings - The created tokens are converted into high-dimensional vectors (list of numbers)
- Self-Attention - The model weighs the importance of all other tokens in the context of each new token it predicts
- Probability - The model calculates the most probable next token in the answer sentence that the AI returns.

## Art of Prompt Writing

- Include details like persona, task, context and a proper format.
- Types of prompts include -
  - Zero-Shot - Ask directly.
  - Few-Shot - Provide some examples.
  - Structured - Define output format (mostly done in JSON), forcing the AI to be precise.

## We can create AI songs on suno.ai

## Threats to AI Agents

- Prompt Injection - Replacing key information of the prompt with personal information that sends data to others or causes tool to misbehave.
- Tool Misuse - Misuse of the created tool by users to create content that might be offensive or obscene.
- Data Leakage - Data getting leaked from the tool causing users to lose crucial personal information.
- Unauthorized Actions - The tool performs actions that it is not meant to do or authorized to do, saying or doing the wrong stuff.

### AI Agents are hence more riskier than normal chatbot agents as they can act and trigger systems that cause a real-world impact.

### Guardrails must be designed to control tool behaviour by permission scoping and auditing tool outputs.
