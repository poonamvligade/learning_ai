Tokens and embeddings are 2 central concepts in using LLMs.
They are not only important to understand the history of language AI, but also to have a clear sense of how LLMs work and how they are built, 
and where they will go in the future without having a good sense of LLMs and tokens.

<img width="600" height="384" alt="image" src="https://github.com/user-attachments/assets/8c654064-d69e-4bc7-bd4d-dd5a425fb7e9" />

A language model processes text by breaking it into small units called tokens and then converting them into numeric representations called embeddings.

In this chapter, we will look more closely at tokens and what tokenization methods are used to power LLMs.

We will then dive into the famous word-to-vec embedding method that preceded modern-day LLMs and see how it's extending the concept of token embeddings to build commercial recommendation systems that power a lot of apps that we use.
Finally, we go from token embeddings to sentence or text embeddings, where a whole sentence or text can have an embedding vector  that represents it, enabling applications like semantic search and topic modelling.



## LLM Tokenization

The way that the majority of people interact with LLMs currently is with the help of a web playground that represents a chat interface between the user and the language model. You may notice that the model does not produce its output response all at once; it actually generates one token at a time.
But tokens aren't the only output of a model; they are also the way in which the model sees its inputs.

The text prompt sent to a model is first broken down into tokens.

### How tokenizers prepare input for the language model

If we look from the outside, generative LLMs can take an input prompt and generate a response.

<img width="600" height="236" alt="image" src="https://github.com/user-attachments/assets/9e4a0bed-9af0-4dc5-9155-f2c11bf0417e" />

Figure 2-2. High-level view of a language model and its input prompt.

Before the prompt is presented to the language model, however, it first has to go through a tokenizer that breaks it into pieces.

You can find an example showing the tokenizer of GPT-4 on the [OpenAI Platform](https://platform.openai.com/tokenizer). Check it out so cool.

<img width="600" height="431" alt="image" src="https://github.com/user-attachments/assets/4fa47db3-12fe-4221-945d-60e6b622280e" />

Figure 2-3. A tokenizer breaks down text into words or parts of words before the model processes the text. It does so according to a specific method and training procedure (from https://oreil.ly/ovUWO).

Let's look at the code example and interact with these tokens ourselves.
Here we'll be downloading an LLM and interacting with how to tokenize the input before generating text with the LLM.
