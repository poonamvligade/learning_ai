Sequence-to-sequence models ahve achieved success in machine translation, image captioning, text summarization, etc.

It's a model that takes a sequence of items, which can be simple words, letters, features of images, and outputs another sequence of items.

Under the hood, the model is composed of an encoder and a decoder.

encoder processes a sequence of items in the input and stores the information into a vector called context.
After processing the entire sequence, it passes the context to the decoder and the decoder then starts producing a sequence of output items.

In the case of machine translation, the encoder and decoder are both RNNs (Recurrent Neural Networks)
