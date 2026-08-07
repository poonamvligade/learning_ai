How Transformer LLMs Work
Instructors: Jay Alammar, Maarten Grootendorst
Co-authors of "Hands-On Large Language Models"

# Intro
Transformer Architecture was introduced in the 2017 paper "Attention is all you need" by Ashish Vaswani and others for the machine translation task.
The idea was to input an English sentence and have the network output a German sentence.
The same architecture is good at inputting, say, a prompt and outputting a response to that prompt. So the prompt can be a question, and the response can be an answer to the question.


## original transformer arch: 
1. consists of 2 parts - an encoder and a decoder
2. In a machine translation scenario, the encoder pre-processes the entire English sentence to extract a context from it, which might be helpful for translation then the decoder uses the context to generate a German sentence.

3. The encoder and decoder form the basis for the models used in many language models today.

4. The encoder model provides a rich, context-sensitive representation for the input text and is the basis for BERT models and most of the embedding models used in RAG applications.
5. The decoder model performs text generation tasks such as summarizing text, writing code, and answering questions and is the basis for most LLMs such as those from OpenAI, Cohere, anthropic

<img width="1428" height="771" alt="Screenshot 2026-08-07 at 1 09 23 PM" src="https://github.com/user-attachments/assets/24ed7154-d293-4fcb-8198-a8edd23e144b" />
<img width="1428" height="357" alt="Screenshot 2026-08-07 at 1 11 41 PM" src="https://github.com/user-attachments/assets/504a76ee-cbf3-41cc-97c0-7b1be8366be4" />
