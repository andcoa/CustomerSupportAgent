# AI Agent for Service Policy Inquiries

## Objective  
Build a retrieval-augmented AI agent in n8n that reads service-related documents from Google Drive, embeds them into Supabase for vector search, and answers customer inquiries about services, terms, and conditions of a body shop via chat.

## Skills Learned  
- **Retrieval-Augmented Generation (RAG)**: Combined LLM reasoning with vector search to enable answers from policy documents.  
- **Embedding and Vector Storage**: Used OpenAI embeddings with Supabase to store and query documents semantically.  
- **Persistent Chat Memory**: Implemented PostgreSQL memory to preserve user interaction history across sessions.  
- **Document Pipeline Automation**: Automated ingestion, chunking, and embedding of Drive documents for dynamic knowledge base updates.  
- **Conversational Agent Design**: Built an interactive AI agent capable of responding accurately to customer queries using internal document knowledge.

## Tools Used  
- **n8n**: Orchestration layer used to design and deploy the AI agent workflow.  
- **AI Agent (n8n built-in)**: Managed chat interactions and invoked tools (e.g., vector search).  
- **OpenAI Chat Model**: Provided language understanding and response generation capabilities.  
- **Postgres Chat Memory**: Stored multi-turn chat history for contextual continuity.  
- **Google Drive**: Source for uploading and accessing service-related documents.  
- **Supabase Vector Store**: Stored vectorized document chunks for semantic retrieval.  
- **OpenAI Embeddings**: Transformed text chunks into embeddings suitable for vector storage and retrieval.  
- **Recursive Character Text Splitter**: Split documents into manageable chunks to improve embedding.  
- **Default Data Loader**: Ingested and formatted documents for embedding.  

## Steps  

![image](https://github.com/user-attachments/assets/a27e4da2-824b-45cc-ad6b-45c83850546a)

1. **Chat Trigger**: Workflow starts when a chat message is received by the AI agent.

![image](https://github.com/user-attachments/assets/0e09d049-05a4-4f40-8bc9-1235f9a4ffa7)

3. **Contextual AI Setup**: The agent uses the OpenAI chat model with Postgres Chat Memory for interaction continuity.
   
4. **Vector Tool Invocation**: The AI agent uses Supabase Vector Store as a tool to retrieve relevant document chunks based on the user query.

![image](https://github.com/user-attachments/assets/aef93652-812b-4d93-b961-d089351f6413)
  
4. **Document Embedding Pipeline**:  
   - A document is uploaded via Google Drive.  
   - The document is parsed by the Default Data Loader.  
   - It is split using the Recursive Character Text Splitter.  
   - Chunks are embedded with OpenAI Embeddings.  
   - Embedded chunks are stored in Supabase Vector Store.  

![image](https://github.com/user-attachments/assets/5431589e-07e4-4a7e-ab07-62a0461ba662)

5. **Answer Generation**: Based on retrieved context, the AI agent answers user queries accurately using information from the uploaded documents.

![image](https://github.com/user-attachments/assets/36e8ca0b-c33d-433b-abda-5813b046bdd4)



