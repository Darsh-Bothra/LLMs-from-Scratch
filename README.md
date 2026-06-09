# LLMs from Scratch

Personal notes and Jupyter notebooks for building a GPT-style large language model from the ground up, following [Build a Large Language Model (From Scratch)](https://www.manning.com/books/build-a-large-language-model-from-scratch) by Sebastian Raschka.

## Topics Covered

- **Text tokenization** — splitting raw text into tokens with regular expressions
- **Vocabulary & token IDs** — mapping tokens to integer labels for model input
- **Custom tokenizer classes** — `encode` / `decode` with special tokens (`<|unk|>`, `<|endoftext|>`)
- **Byte Pair Encoding (BPE)** — subword tokenization via OpenAI's `tiktoken` library
- **Input–target pairs** — sliding-window next-token prediction
- **PyTorch data loading** — `GPTDatasetV1` and `DataLoader` for batched training

## Notebooks

| Notebook | Description |
| --- | --- |
| [LLM_From_Scratch_Tokenization.ipynb](notebooks/single/LLM_From_Scratch_Tokenization.ipynb) | Regex-based tokenization, vocabulary creation, and a tokenizer with unknown-word handling |
| [LLM_from_Scratch_BPE.ipynb](notebooks/single/LLM_from_Scratch_BPE.ipynb) | BPE tokenization using `tiktoken` (GPT-2 encoding) |
| [Data_Loader_Input_Output_Pairs.ipynb](notebooks/single/Data_Loader_Input_Output_Pairs.ipynb) | Full Chapter 2 walkthrough — tokenization through BPE, input–target pairs, and a PyTorch `DataLoader` |

## Getting Started

### Prerequisites

- Python 3.10+
- [Jupyter](https://jupyter.org/) or [Google Colab](https://colab.research.google.com/)

### Install dependencies

```bash
pip install torch tiktoken jupyter
```

### Download the sample text

The notebooks use Edith Wharton's public-domain short story *The Verdict* as training data. Download it into the same directory as the notebook you are running:

```bash
curl -o the-verdict.txt \
  https://raw.githubusercontent.com/rasbt/LLMs-from-scratch/main/ch02/01_main-chapter-code/the-verdict.txt
```

## Project Structure

```
LLMs-from-Scratch/
├── notebooks/
│   └── single/
│       ├── LLM_From_Scratch_Tokenization.ipynb
│       ├── LLM_from_Scratch_BPE.ipynb
│       └── Data_Loader_Input_Output_Pairs.ipynb
└── README.md
```

## References

- [Build a Large Language Model (From Scratch)](https://www.manning.com/books/build-a-large-language-model-from-scratch) — Sebastian Raschka (Manning, 2024)
- [Official companion repository](https://github.com/rasbt/LLMs-from-scratch) — `rasbt/LLMs-from-scratch`

## License

This repository contains personal learning notes. The accompanying book and its official code repository have their own licenses.
