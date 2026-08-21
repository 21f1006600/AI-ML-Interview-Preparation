# RAG (Retrieval Augmented Generation) Interview Questions

## Q1. What is RAG?

Ans. RAG (Retrieval-Augmented Generation) is a technique where we retrieve relevant information from an external knowledge source and provide it to an LLM as context so it can generate a more grounded answer.

## Q2. Why do we need RAG?

Ans. LLM has its own limitations.

- Its knowledge is outdated.
- It may not know private/company specific information.
- It can hallucinate.
- RAG lets the model **retrieve the required information at query time** instead of relying only on what it learned during training.

## Q3 Explain RAG Pipeline?

Ans. Documents → Chunking → Embeddings → Convert those embeddings into vector database → User Query → Query Embedding → Retrieval → Relevant Chunks → Prompt + Context → give it to LLM → Output

1. **Data Ingestion**– collect and preprocess documents
2. **Chunking** – split content into manageable segments
3. **Embedding generation** – convert text into vector representations
4. **Vector storage** – store embeddings in a vector database
5. **Retrieval** – find relevant chunks based on queries
6. **Augmented prompt** – supply retrieved context to LLM
7. **Generation** – LLM produces grounded response

## Q4 What is vector databases?

Ans. Its is use to store and retrieve vector embeddings efficiently.

Examples are: Pinecone, ChromaDb

## Q5. Explain chunking strategies for RAG. How do chunk size and overlap affect retrieval?

Ans. Chunking divides documents into smaller pieces or sections for efficient retrieval. Proper chunking balances context richness and accuracy.

- Smaller Chunks improve precision
- larger chunks preserve context
- overlap prevents context loss

## Q6. What is Semantic and Keyword search?

Ans. Keyword search matches the exact words or terms. (SQL) TF-IDF

- Semantic Search: matches the meaning using representations such as embeddings. Semantic search is useful when the user query and the relevant document use different words but express the same idea.
    
            Query
                ↓
    Embedding model
                ↓
    Vector representation
                ↓
    Similarity search
                ↓
    Relevant documents
    
    The query and documents are converted into **embeddings**, and the system finds vectors that are semantically similar using the Euclidian or Manhattan Distance.
    
    ## **Q7. What is “Lost in the Middle” problem in RAG? How can you mitigate it?**
    
    Ans. LLMs tend to prioritize information at the beginning and end of long context windows, ignoring middle content.
    
    **Mitigation strategies:**
    
    - reorder retrieved chunks by importance
    - place most relevant content first
    - use summarization before insertion
    - limit context size
    - use hierarchical retrieval
    
    Proper context structuring improves response accuracy.
    
    ## Q8. What is fine-tuning?
    
    > Fine-tuning means continuing to train a pretrained model on a task-specific dataset so that its parameters adapt to the new task.
    > 
    
    ## Q9. What is transfer learning?
    
    > Transfer learning means taking knowledge learned from one task/domain and adapting it to another related task.
    > 
    
    Example: CNN trained on million images has already learned about:
    
    - edges, textures, shapes.
    - Instead of starting from zero we fine tune to medical images.

## Q10. Explain the complete training process of neural network.

Ans. 

passing Input through network
↓
using Forward propagation
↓
to generate Prediction
↓
Compare actual with predicted using Loss calculation
↓
Backpropagation
↓
Gradients
↓
Optimizer
↓
Weight update
↓
Next batch
↓
Repeat
↓
Epochs
↓
Validation
↓
Final model