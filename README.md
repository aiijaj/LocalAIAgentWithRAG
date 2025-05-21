

# 🍕 Pizza Restaurant Review Q\&A Chatbot

This is an AI-powered chatbot that answers user questions about a pizza restaurant using real customer reviews. It combines vector search and LLMs to give relevant, context-aware responses.

## 🧠 Features

* Uses **LangChain** with **Ollama** for LLM and embeddings.
* Embeds and stores real restaurant reviews using **ChromaDB**.
* Retrieves the most relevant reviews based on user questions.
* Generates intelligent answers using the **LLaMA 3** model.
* Simple, interactive CLI to chat with the bot.

## 🚀 How It Works

1. **Data Embedding**
   Loads review data from `realistic_restaurant_reviews.csv`, creates document embeddings using `mxbai-embed-large`, and stores them in Chroma vector DB (on first run).

2. **Retrieval**
   When a user asks a question, the retriever fetches the top 5 relevant reviews from the database.

3. **LLM Response**
   The `llama3.2` model generates a response using both the user question and the retrieved reviews.

## 📁 Project Structure

```
.
├── main.py                  # Main script with LLM chat loop
├── vector.py                # Contains Chroma vector store and retriever
├── realistic_restaurant_reviews.csv
└── README.md
```

## 📦 Requirements

Make sure you have the following Python packages:

```bash
pip install langchain langchain-community langchain-core langchain-chroma pandas
```

Also, ensure **Ollama** is installed and the models (`llama3.2` and `mxbai-embed-large`) are available:

```bash
ollama pull llama3:2
ollama pull mxbai-embed-large
```

## 🛠️ How to Run

```bash
python main.py
```

Then interact via the command line:

```bash
Ask your question (q to quit): What do customers think about the crust?
```

## 📌 Notes

* The Chroma database is persisted locally at `./chrome_langchain_db`.
* The database is only created on the first run.
* Make sure `realistic_restaurant_reviews.csv` exists with at least the columns: `Title`, `Review`, `Rating`, `Date`.



## 👨‍🍳 Made With

* [LangChain](https://www.langchain.com/)
* [Ollama](https://ollama.com/)
* [Chroma](https://www.trychroma.com/)
* [Pandas](https://pandas.pydata.org/)

