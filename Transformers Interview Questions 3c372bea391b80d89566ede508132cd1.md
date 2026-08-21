# Transformers Interview Questions

## Q1. What is transformer?

Ans. A transformer architecture is the foundation of modern LLMs. Introduced in the paper “Attention is all you need” and replaces the recurrence with attention mechanisms to process text parallelly.

Key components

1. Input Embeddings: Convert tokens into numerical vectors. (tokenisation)
2. Positional Encoding: tells the model where each token occurs in sequence.
    - Example: Dog bites man. |  Man bites dog. → same words completely different meaning.
    - It is like giving the positions to the encodings.
3. Self Attention Mechanism:
4. Multi Head Attention:
5. Feed Forward Neural Network
6. Output

## Q2. What is Attention?

Ans. Attention lets model decide which parts of the inputs are important when processing a particular element.

- "The animal didn't cross the road because **it** was tired."
- When interpreting **"it"**, attention can assign more importance to **animal** than **road**.

## Q3 What is Self Attention?

Ans. Self attention means the model calculates the attention between elements within the same sequence. 

Example: "The bank raised interest rates.”

The meaning of **bank** can be understood by looking at other words in the sentence. It means that it is a financial institution not a river bank.

## Q4 What is Multi Head Attention?

Ans. Instead of having one attention mechanism, Transformers use multiple attention heads.

- Imagine eight people reading the same sentence:
    - Person 1 focuses on grammar
    - Person 2 focuses on relationships
    - Person 3 focuses on nearby words
    - Person 4 focuses on long-distance relationships

Then their information is combined.

## Q5 Why do Transformers need positional encoding?

Ans. Attention doesn’t inherently know whether the word came first or second or tenth. So positional encoding tells the model that where each token occurs in the sequence. Its like seating system in IRCTC. Everyone is assigned a seat.

## Q6 What is Query, Key, Value in transformers?

Ans. 

- **Query:** What am I looking for? → what a token is looking for?
    - Your query is “cats”
- **Key:** What does each item represent? → key represents what each token can be matched on
    - Book 1 → Key: Dogs
    - Book 2 → Key: Cats
    - Book 3 → Key: Cars
    - The query is compared with keys which are relevant to the question/query?
- **Value:** What information do I actually get? → value contains the actual information that is retrieved.
    - Once the model decides that the **Cats** book is highly relevant, it retrieves the actual information from that book.
    
    ![image.png](image.png)
    

## Q7. Why do we divide by √dk in attention?

Ans.  I guess it is for the scalability purpose. When the dimensions of keys become large the dot product becomes large and larger values going to softmax can make the distribution sharp which can lead to very small gradients.

## Q8. What is an embedding?

Ans. An embedding is a numerical vector representation of objects such as words, sentences, images or document where semantically similar objects have similar representations.

| Word Embeddings  | Contextual Embeddings |
| --- | --- |
| Each word has fixed vector regardless of context. | Vectors change depending on context |
| Ex.  | Ex. “bank” in river vs finance |

## Q9 What is Vocabulary?

Ans. Set of unique tokens that a model knows or uses.

## Q10 What is Token?

Ans. A small piece of text that the model processes. It can be a word, part of word, punctuations or symbols.

## Q11 What is context window?

Ans. Context window is the maximum amount of information an LLM can consider at one time when generating a response.

Why it Matters? 

→ Analysing long documents. A larger context window allows more of the documents to be available simultaneously.

→ Long conversations: larger context window more prev conv to remain available.

→ RAG Systems: 

→ Context window is not equal to memory.

- **Context window:**

> Information the model can process during the current request.
> 
- **Long-term memory:**

> Information stored externally and retrieved later.
> 

## Q12 What is Encoder, Decoder and Encoder-Decoder transformer models with examples.

| **Encoder-only** | **Decoder-only** | **Encoder-Decoder** |
| --- | --- | --- |
| Understand text | Generate text | Convert input to output |
| Used for classification, search, sentiment analysis. | Used in chatbots, content generation | Used in translation and summary |
| Ex. BERT | GPT models | Ex. BART |

## Q13 How is LLM better than NLP?

Ans. LLM is trained on massive datasets to understand, generate and reason with human language. Modern LLMs use transformer architecture and billions of parameters to perform tasks like summary, translation, QnA and code generation.

While NLP is relied on RNNs and LSTMs which require task based training and feature engineering manually.

## Q14 What is Hallucination in LLMs?

Ans. Hallucination can occur when an LLM generates incorrect, fabricated or misleading information presented as factual.

Causes:

1. Incomplete training
2. lack of factual grounding
3. ambiguous prompts

Mitigations:

1. RAG for factual grounding
2. human in-the-loop validation
3. fine tuning with domain data