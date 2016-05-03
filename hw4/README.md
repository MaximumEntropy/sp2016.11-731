For this homework, I implemented a simple sequence to sequence model with attention. I implemented my attention in 2 different ways. The first was using the dot product between the hidden state representation of the decoder and encoder that gives me a matrix of size n_target x n_source. I then computed a weighted average of the encoder hidden states and concatenated it to the decoder hidden states before predicting the the words in the decoder. I connect the encoder and the decoder by setting the first hidden state of the decoder to be the last hidden state of the encoder. The other attention mechanism that I used was to provide the encoder represntation at each step while decoding (I did this by concatenating it with the decoder input at each step).

Finally, I used a regularization method for RNNs that penalizing the L2 norm between successive hidden states in the RNN. This gave + 2 BLEU points on the validation set.

I used a Bidirectional LSTM as my encoder and an LSTM for my decoder.


There are two Python programs here:

- `python bleu.py your-output.txt ref.txt` to compute the BLEU score of your output against the reference translation.
 - `python rnnlm.py ref.txt` trains an LSTM language model, just for your reference if you want to use pyCNN to perform this assignment.

The `data/` directory contains the files needed to develop the MT system:

 - `data/train.*` the source and target training files.

 - `data/dev.*` the source and target development files.

 - `data/test.src` the source side of the blind test set.
