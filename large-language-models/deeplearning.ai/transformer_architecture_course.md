How Transformer LLMs Work?

Instructors: Jay Alammar, Maarten Grootendorst

Co-authors of "Hands-On Large Language Models"

# Intro
Transformer Architecture was introduced in the 2017 paper "Attention is all you need" by Ashish Vaswani and others for the machine translation task.
The idea was to input an English sentence and have the network output a German sentence.
The same architecture is good at inputting, say, a prompt and outputting a response to that prompt. So the prompt can be a question, and the response can be an answer to the question.


## original transformer arch: 
1. consists of 2 parts - an encoder and a decoder
2. In a machine translation scenario, the encoder pre-processes the entire English sentence to extract a context from it, which might be helpful for translation; then the decoder uses the context to generate a German sentence.

3. The encoder and decoder form the basis for the models used in many language models today.

4. The encoder model provides a rich, context-sensitive representation for the input text and is the basis for BERT models and most of the embedding models used in RAG applications.
5. The decoder model performs text generation tasks such as summarizing text, writing code, and answering questions and is the basis for most LLMs such as those from OpenAI, Cohere, and Anthropic.

<img width="1428" height="771" alt="Screenshot 2026-08-07 at 1 09 23 PM" src="https://github.com/user-attachments/assets/24ed7154-d293-4fcb-8198-a8edd23e144b" />
<img width="1428" height="357" alt="Screenshot 2026-08-07 at 1 11 41 PM" src="https://github.com/user-attachments/assets/504a76ee-cbf3-41cc-97c0-7b1be8366be4" />


What will you learn:

1. Advancements in LLMs
2. Tokenization, where input text is broken down into tokens, which can be words/word fragments, which will then be fed into LLMs.
3. Gain intuition about how the transformer network works, focusing on decoder-only models.


## Decoder-only model - a generative model

A generative model takes in a text prompt and generates a text in response by generating one token at a time.
Here is how the generation process works -

1. The model starts by mapping each input token into an embedding vector that captures the meaning of that token.
2. After that, the model passes these token embeddings through a stack of transformer blocks, where each block is a specific neural network architecture that is designed to learn flexibly from data and also scale well on GPUs.
3. So you will learn how each block is made up of an attention layer and a feed-forward network.
4. The model then uses the output vectors of a transformer block and passes them to the last component, the language modelling head, which finally generates the output token.
  
   <img width="838" height="597" alt="Screenshot 2026-08-07 at 5 06 17 PM" src="https://github.com/user-attachments/assets/8a85d0a1-a34b-43a8-9d93-e7d3bb572267" />


   #### The magic of LLLMs comes  not only the transformer architecture but also from the incredibly rich data the models learn from.
