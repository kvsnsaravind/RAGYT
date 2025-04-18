# 🧠 RAG Pipeline using LangChain & Hugging Face

This project implements a Retrieval-Augmented Generation (RAG) pipeline using [LangChain](https://www.langchain.com/), [Hugging Face Transformers](https://huggingface.co/), and the [Chroma vector store](https://www.trychroma.com/). It loads data from a website, splits the content into chunks, creates embeddings, stores them in a vector database, and uses a Language Model to answer questions based on that content.

---

## 📦 Requirements

Install the necessary Python packages:

```bash
pip install langchain langchain-community langchain-core chromadb
pip install huggingface_hub sentence-transformers
```
🔐 Set Up API Keys
You need a Hugging Face API token for accessing hosted models.

Go to https://huggingface.co/settings/tokens

Generate a new token (read access)

Set the token in your environment:

os.environ["HUGGINGFACEHUB_API_TOKEN"] = "your-huggingface-token-here"

---

## 🛠️ How It Works
1. Web Scraping & Chunking
The website content is loaded and split into smaller chunks for embedding.

2. Embeddings & Vector Storage
Each chunk is embedded using all-MiniLM-L6-v2 from Hugging Face.

The embeddings are stored in a Chroma vector store.

3. Retrieval & Answering
A question is asked.

Relevant chunks are retrieved using similarity search.

The LLM generates a response based on the retrieved context.

---

## 💡 Troubleshooting

Issue | Solution

503 Server Error | Try using a different model (e.g. google/flan-t5-base)

AttributeError: 'str' object has no attribute 'page_content' | Ensure you’re formatting LangChain documents, not strings

ValueError: Embeddings must be a non-empty list | Make sure your content is loaded and chunked before embedding

---

## ✨ Credits
Built with:

LangChain

Hugging Face

ChromaDB

## 📜 License
MIT License.
