How language has beeen represented numerically. 
we'll start with algorithm that represents words as large sparse vectors or array of numbers whcih simply records the presence of teh words.
then word-to0vec whose word represenattioncapture the meaning of words in context withof a few neighbouring words. 
finally trnasformers whoseense vectors captured the emaning of words in context of the full sentenceora paragraph.


Recent history of language ai-
though we are going to explore more recent history of langfuage AI and language models it s 
important to know where we started.
1. Non transformer models - BAg-of words, word=-to-vec and attention models
   Earliers techniques such as bag 0f wordsd word to vec has been the foundation of what we are using today
  although they lack contexual representations they are ofetn a good baseline to start with.
  these are cllaed non-transofmer model sisnce today;s models are soly powdered by a transformer architecture. in contrast to these stong baselines.

3.  Encoder only models -BERT, distillBert, RoBerta
   these are great at representing language a sa numerical representations.

4.  Decoder only models - are generative in nature their main goal is to generate text
5.  encoder-decoder models -that attempt to get best of both the worlds

<img width="1427" height="763" alt="Screenshot 2026-08-09 at 10 26 21 AM" src="https://github.com/user-attachments/assets/e15dfe9a-e636-47cb-b932-76d8844cbc2b" />

We will learn non-transformer models, encoders, decoders, and how they relate to each other.

## Typical tasks
<img width="1427" height="763" alt="Screenshot 2026-08-09 at 10 31 14 AM" src="https://github.com/user-attachments/assets/7e207d5d-97e6-479b-8eaf-277e5967b05a" />

Language AI is, however, a tricky concept for computers.
text in nature is unstructured and loses its meaning when represented by zeros and ones or individuel characters.
As a result throughout the history of language AI, there has been a large focus on representing a language in a structured manner, so that it can be more easily be used by computers.
from generating text to creating numerical representations and classifying textual inputs

<img width="1061" height="419" alt="Screenshot 2026-08-09 at 10 33 07 AM" src="https://github.com/user-attachments/assets/e3a10367-0595-487a-b20b-e01c585c57b6" />




At the start of this language AI field, the focus was mainly on representing language to analyse unstructured data.
A first and very relevant method is representing language as a bag of words.
1. Imagine you have some input text.
2. That is a cute dog"
3. To represent this sentence, you can break it up into smaller pieces. To do so, you split the text into words by separating them througha  white space this  process of converting text into pieces called tokenizations and each individuel word is called a token
4. Note a token can be even smaller than an entire word eg. forming can become "form" , "ing".
you can perform the same tokenization method with another document
