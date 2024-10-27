# RAGNovel: Retrieval Augmented Summarization and Question Answering of Literary Texts

CIS530 - Project Work for Spring 2024: Comparative analysis of NLP techniques, including TextRank and Retrieval Augmented Generation (RAG), for summarizing and Question-Answering

### Description
This project draws comparison between natural language processing (NLP) techniques like TextRank and Retrieval Augmented Generation (RAG) for text summarization and question answering of a literary novel - Alice in a Wonderland. It is tailored for processing large literary texts and to return relevant summaries and answers, utilizing embeddings and similarity computations for improved accuracy.

### Project Structure

```bash
root/
├── code_and_data/                  # Directory containing notebooks and data files
│   ├── Data/                       # Data subdirectory for text or PDF files
│   ├── Q_and_A.ipynb               # Notebook for question answering
│   ├── Text_summarization.ipynb    # Notebook for text summarization
│   └── localllm.ipynb              # Notebook for experimenting with local LLMs
│
├── requirements.txt                # Project dependencies
├── README.md                       # Project information and setup instructions
└── report.pdf                      # Project report with methodology and results
```

**Key Files**

1. **Q_and_A.ipynb:** Notebook that allows users to query text files, returning the most relevant sentences based on TF-IDF and GloVe embeddings.
2. **Text_summarization.ipynb:** Notebook for summarizing lengthy texts into concise versions, using RAG, TextRank, and similarity-based (SimHash, MinHash) techniques.
3. **localllm.ipynb:** Notebook for setting up and experimenting with local Large Language Models (LLMs), such as LLaMa.

### SetUp Instructions

1. Install Dependencies: Ensure Python 3.8+ is installed, then install required packages with:
```bash
pip install -r requirements.txt
```

2. Download GloVe embeddings (e.g., glove.42B.300d.txt) from the official GloVe website and place them in the Code&Data directory.

3. Prepare Data: Place text files in Code&Data/Data/. Ensure paths are correctly referenced in notebooks (e.g., Data/alice_wonderland_chapter1.txt).

### Usage

**Running Text Summarization**
Open `Text_summarization.ipynb` in Jupyter Notebook or JupyterLab.

**Loading Files**
Ensure `file_path` and `embedding_file_path` are set to valid paths, such as:

```python
file_path = "Data/alice_wonderland_chapter1.txt"
embedding_file_path = "glove.42B.300d.txt"
```

### Summarization Techniques
The notebook offers summarization with both RAG and TextRank:

- **RAG (Retrieval Augmented Generation):** Utilizes the LangChain library to generate summaries directly from the context in documents.
- **TextRank:** Uses cosine similarity with TF-IDF and GloVe embeddings to rank sentences, applying MinHash and SimHash to assess performance differences.

### Example Code Snippet
Run the following in the notebook to obtain a summary:

```python
questions = [
    "Summarize this book. Use only the text within this book for generating the summary. Write the summary in 1000 words."
]

for question in questions:
    print(f"Question: {question}")
    print(f"Answer: {chain.invoke({'question': question})}")
```

### Evaluating Summarization

The notebook evaluates summaries using ROUGE scores. ROUGE-1 and ROUGE-L scores are computed to compare generated summaries against reference summaries.






