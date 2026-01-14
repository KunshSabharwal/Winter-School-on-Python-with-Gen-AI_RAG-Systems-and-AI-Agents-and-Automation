## RAG Systems (Retrieval-Augmented Generation)

- Thanks to @https://github.com/Jaskirat-singh04 for the session on RAG systems and the hands on coding for the Winter School Python with Gen AI_Day-2_Rag-agent Colab notebook.

### RAG is a framework and not an architecutre

- Framework that combines the question and the relevant chunks to obtain the answer.
- The asked question by the user is checked by retriever that retrieves that fixed data from the knowledge base (which is separated and broken down into chunks and embedded into numerical values, each numerical value of a word is mapped to the word itself, which finally passes the word chunks) to the LLM instead of the complete knowledge base at once. Only the relevant chunk of the knowledge base is passed (Context Window Problem - fixed LLM memory causes LLM's to forget crucial details in long chats/conversations leading to errors, hallucinations, and decreased accuracy)
- There is a slight ovelapping between chunks to build a better connection between them and the selected chunk provides slight context about its previous and next chunks.
- In the retriever, the number of chunks to retrieve is determined by the top-k parameter, a value that is set by the system designer, not determined automatically by the system itself. A small k risks missing crucial info, while a large k adds computational cost and noise.
- User query, relevant chunks, system instruction are the 3 most important parts of the context builder (prompt assembly).
- RAG's take multiple types of data - text, images (text extracted by OCR), videos (text extracted from audio transcripts) and many other types of data.

### Notion document - https://www.notion.so/RAG-Pipeline-with-LangChain-Google-Gemini-and-Agents-2e514dc3f1ec8051835cfb236da43fa9

### Colab Notebook Copy created and added to drive
