# Transformer from Scratch

A character/byte-level language model implemented directly, following the
structure of Andrej Karpathy's `llm.c`-style walkthrough.

## Layout

```
config.py        hyperparameters
dataset.py       corpus loading
model.py         transformer: attention, FFN, blocks
train.py         training loop
karpathy_attention.py   attention implemented in the walkthrough style
input.txt        training corpus
tokenizer_en.json        English vocabulary
tokenizer_it.json        Italian vocabulary
```

Two tokenizers are included so the same architecture can be trained on either
language - the English and Italian corpora produce noticeably different output.

## Setup

```bash
pip install torch numpy
```

Edit `config.py`, then:

```bash
python train.py
```

## Notes

- Attention is implemented twice: once in `model.py` as used for training, and
  once in `karpathy_attention.py` kept as a readable reference. They should
  agree; if they diverge, the reference version is the one to check.
- `input.txt` is the training corpus and is committed deliberately - it is the
  data the repo exists to demonstrate. Swap it for your own text to change what
  the model learns.
- No tests and no packaging; this is a learning repository.