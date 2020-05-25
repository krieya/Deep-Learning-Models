# Portugese Translation and Paraphrasing


## Description

1. Machine Translation

    The goal of this task is building a machine translation model to translate sentence in Portugese to English. 
    
    Data size:

        - Train: 85918 pairs
        - Validation: 4772 pairs
        - Test: 4738 (source only)
    
    Evaluation Metric: BLEU-4 score

    Strategies and Results:

    | Hyperparameters | Range | Best |
    |-----------------|-------|------|
    | train batch size | 16, 32, 64 | 16 |
    | val/test batch size | 64, 128, 256 | 256 |
    | pre-trained embeddings | None, fasttext, GloVe, Ptwiki, Google | None |
    | embedding dimension | 256, 300, 512 | 256 |
    | encoder dropout | [0.2 0.8] | 0.5 |
    | decoder dropout | [0.2 0.8] | 0.8 |
    | teacher forcing | [0.1 0.9] | 0.6 |
    | encoder hidden dimension | 256, 512 | 512 |
    | optimizer | Adam, SGD | Adam |
    | learning rate | [0.0001 0.0015] | 0.0011 |
    | weight decay | [0.00001 0.0001], None | None |
    | loss function | cross-entropy | cross-entropy |
    
    Best BLEU-4 score in Validation set: 0.2770

2. Paraphrasing

    The goal of this tasks is generating Portugese paraphrases of a given sentence automatically, which is important for many downstream applications. For example, chatbot engines can leverage paraphrases to diversify the responses. Question answering systems can use paraphrases to understand the question better. For more details, look at [this sample paper](http://people.ee.duke.edu/~lcarin/emnlp_gap.pdf).

    Data size:
        - Train: 85171 pairs
        - Validation: 4725 pairs
        - Test: 4724 (source only)

    Evaluation metric: BLEU-4 score

    Strategies and Results

    | Hyperparameters | Range | Best |
    |-----------------|-------|------|
    | Model | `Transformer` `Seq2Seq + dot attn` | `Seq2Seq + dot attn` |
    | train batch size | 16, 32, 64 | 16 |
    | val/test batch size | 64, 128, 256 | 256 |
    | pre-trained embeddings | None, fasttext, Ptwiki | None |
    | embedding dimension | 256, 300, 512 | 256 |
    | encoder dropout | [0.2 0.8] | 0.4 |
    | decoder dropout | [0.2 0.8] | 0.8 |
    | teacher forcing | [0.1 0.9] | 0.7 |
    | encoder hidden dimension | 256, 512 | 512 |
    | optimizer | Adam, SGD | Adam |
    | learning rate | [0.0001 0.0015] | 0.001 |
    | weight decay | [0.00001 0.0001], None | None |
    | loss function | cross-entropy | cross-entropy |
    
    Best BLEU-4 score in Validation set: 0.2530



## Credits

This task is designed and mentored by the instructor team led by [Muhammad Abdul-Mageed](https://mageed.arts.ubc.ca/).
