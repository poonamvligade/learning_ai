
An Introduction to Large Language Models


This  chapter provides an introduction to LLMs and their application in the world of language AI. We will learn -

* history and development of llms
* their architecture and training methods,
* their potential uses and limitations

We intend to answer the following questions in this chapter:

* What is Language AI?
* What are large language models?
* What are the common use cases and applications of large language models?
* How can we use large language models ourselves?

### What is AI
a computer system performing tasks  close to human intelligence, such as language translation, voice recognition, and visual perception.

[Artificial intelligence is] the science and engineering of making intelligent machines, especially intelligent computer programs. It is related to the similar task of using computers to understand human intelligence, but AI does not have to confine itself to methods that are biologically observable.

John McCarthy, 20071

Language AI is a subfield of AI that focuses on developing technologies capable of  understanding, processing, and generating human language. Language AI can be interchangeably used with natural language processing (NLP).

We use language AI to encompass technologies that are not only LLMs but also have a significant impact on the field, such as retrieval systems that can give LLMs superpowers.


<img width="927" height="531" alt="Screenshot 2026-05-15 at 10 48 52 PM" src="https://github.com/user-attachments/assets/8c5e2dda-5432-464a-838d-17bcb94dd5e2" />

Language, however, is a tricky concept for computers. Text is unstructured in nature and loses its meaning when represented as zeros and ones (individual characters). As a result, throughout the history of Language AI, there has been a strong focus on representing language in a structured manner so that it can more easily be used by computers. Examples of these Language AI tasks are provided in Figure 1-2.

<img width="672" height="388" alt="Screenshot 2026-05-15 at 11 00 16 PM" src="https://github.com/user-attachments/assets/2d651609-fa3a-46d3-9d73-5e0d01398c62" />

### Representing Language as a Bag-of-Words

Bag-of-words works as follows: let’s assume that we have two sentences for which we want to create numerical representations. The first step of the bag-of-words model is tokenization, the process of splitting up the sentences into individual words or subwords (tokens), as illustrated in Figure 1-3.


<img width="600" height="202" alt="image" src="https://github.com/user-attachments/assets/631745fe-9de0-4b3a-a25c-63c27a677f76" />

Figure 1-3. Each sentence is split into words (tokens) by splitting on a whitespace.

The most common method for tokenization is by splitting on a whitespace to create individual words. However, this has its disadvantages as some languages, like Mandarin, do not have whitespaces around individual words.

<img width="600" height="296" alt="image" src="https://github.com/user-attachments/assets/05c85c47-1799-48be-a099-6bcda6847b0b" />

Figure 1-4. A vocabulary is created by retaining all unique words across both sentences.

After tokenization, we combine all unique words from each sentence to create a vocabulary that we can use to represent the sentences.

Using our vocabulary, we simply count how often a word in each sentence appears, quite literally creating a bag of words. As a result, a bag-of-words model aims to create representations of text in the form of numbers, also called vectors or vector representations.
These kinds of models are called representation models.

<img width="600" height="290" alt="image" src="https://github.com/user-attachments/assets/10b56e0e-7fc9-4a21-b123-fe383ad7bff3" />
