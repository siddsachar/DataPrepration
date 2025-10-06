# Data Preparation for Language Model Training

This repository provides a complete workflow for preparing text data for training large language models (LLMs) using PyTorch and the `tiktoken` tokenizer. It includes scripts and Jupyter notebooks for data aggregation, tokenization, dataset creation, and batching, following best practices for modern NLP pipelines.

## Features
- Combine multiple raw text files into a single training corpus
- Tokenize text using OpenAI's `tiktoken` (e.g., `cl100k_base`)
- Analyze vocabulary size and token statistics
- Create PyTorch-compatible datasets for next-token prediction
- Efficient batching with DataLoader and custom collate logic
- Example code for embedding layers and positional encodings
- Modular, well-documented notebook cells for easy customization

## Folder Structure
```
├── books/                # Raw text files (input)
├── all_books.txt         # Combined corpus (auto-generated)
├── dataPrepration.ipynb  # Main Jupyter notebook
├── .gitignore            # Git ignore rules
└── README.md             # Project documentation
```

## Quick Start
1. **Clone the repository**
   ```sh
   git clone <repo-url>
   cd DataPrepration
   ```
2. **Install dependencies**
   - Python 3.8+
   - Install required packages:
     ```sh
     pip install torch tiktoken
     ```
3. **Add your data**
   - Place your `.txt` files in the `books/` directory.
4. **Run the notebook**
   - Open `dataPrepration.ipynb` in Jupyter or VS Code.
   - Execute cells step by step to:
     - Combine text files
     - Tokenize the corpus
     - Analyze tokens
     - Prepare PyTorch datasets and DataLoaders
     - Inspect embeddings and batches

## Notebooks Overview
- **Data Aggregation**: Merges all `.txt` files into a single corpus with `<EOS>` tokens for document boundaries.
- **Tokenization**: Uses `tiktoken` to encode and decode text, and reports vocabulary size.
- **Dataset Creation**: Defines a custom PyTorch `Dataset` for next-token prediction, with adjustable sequence length and stride.
- **Batching**: Demonstrates DataLoader usage and batch inspection.
- **Embeddings**: Shows how to create and combine token and positional embeddings for transformer models.

## Customization
- Change `max_length`, `step_size`, and `batch_size` in the notebook to suit your model and hardware.
- Replace or extend the `BooksDataset` class for different modeling tasks.
- Add preprocessing or filtering steps as needed for your data.

## Best Practices
- Use `<EOS>` tokens to mark document boundaries for LLM training.
- Inspect token and batch shapes before starting long training runs.
- Keep raw data and generated files (like `all_books.txt`) out of version control (see `.gitignore`).

## License
This project is provided for educational and research purposes. Please check the licenses of any third-party datasets or models you use.

## Acknowledgments
- [tiktoken](https://github.com/openai/tiktoken) by OpenAI
- [PyTorch](https://pytorch.org/)
- Hugging Face Datasets (optional, for advanced workflows)

---

For questions or contributions, please open an issue or submit a pull request.
