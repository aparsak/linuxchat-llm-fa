# 🤖 Persian QA Chatbot on Linux & Free Software Philosophy

This project builds a **conversational QA chatbot** that answers user questions based on data gathered from various sources such as PDF/Epub files, Wikipedia pages, websites, and more. The content revolves around the **philosophy of Linux**, **free software**, and the **key figures** who have shaped these movements.

---

## 📘 Project Overview

This project demonstrates how to build a Persian-language **Question Answering (QA)** system using [LangChain](https://www.langchain.com/), Cohere multilingual embeddings, and a FAISS vectorstore.

It integrates information from **PDFs, websites, Wikipedia pages, and HTML documents**, preprocesses them, generates embeddings, and enables natural language querying in Persian.

---

## Features

- Load and clean PDF content (e.g., _Just for Fun_ in Persian)
- Scrape and load a Persian Linux blog (`https://linuxbook.ir`)
- Extract Farsi articles from Wikipedia
- Load local HTML files
- Clean and preprocess Persian text
- Chunk documents with overlap using LangChain
- Embed using Cohere's `embed-multilingual-light-v3.0`
- Store embeddings using FAISS vectorstore (locally)
- Perform retrieval-based question answering with `command-r-plus` model
- Apply MMR (Maximal Marginal Relevance) for diverse document retrieval

---

## 📁 Data Sources

| Type      | Source                                                                 |
|-----------|------------------------------------------------------------------------|
| PDF       | `justforfun_persian.pdf` — Biography of Richard Stallman              |
| Website   | [`https://linuxbook.ir/all.html`](https://linuxbook.ir/all.html)      |
| Wikipedia | Articles on Stallman, Linus Torvalds, GNU Project, Free Software, etc.|
| HTML      | Local files inside `data/html`                                         |

---

## ⚙️ Pipeline Overview

1. **Document Loading**: Load PDFs, web pages, Wikipedia, and HTML using LangChain community loaders.
2. **Text Cleaning**: Normalize and clean Persian text to remove invisible and redundant characters.
3. **Chunking**: Split documents into overlapping chunks (500 chars, 50 overlap) using recursive splitter.
4. **Embedding**: Use Cohere’s multilingual embedding model to convert chunks into dense vectors.
5. **Vectorstore**: Store chunks and their embeddings in a FAISS index with metadata.
6. **Retrieval QA**: Use an LLM (`command-r-plus`) to answer user questions based on top-k retrieved chunks.

---

## 🛠 Requirements & Setup

- Python 3.9
- Install dependencies via:
  
  ```bash
  pip install -r requirements.txt
  ```

- Make sure to set your Cohere API key in the script before running.
- Data files (PDFs, HTML, etc.) should be placed in the appropriate data/ directories.

---
## 🙏 Acknowledgments

This project is developed as part of the **Quera LLM Course**.  

