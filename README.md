#ChatGroq Demo Project

Overview

This project is a demonstration of a chatbot using Retrieval-Augmented Generation (RAG) with OpenAI's GPT-3.5 and Streamlit. The chatbot leverages the ChatGroq model to provide contextually accurate responses based on documents retrieved from a specified web source.

Features

Streamlit Interface: A user-friendly web interface for interacting with the chatbot.
Retrieval-Augmented Generation (RAG): Combines document retrieval with language generation to provide more accurate and contextually relevant responses.
Document Retrieval: Utilizes FAISS for efficient document retrieval.
Text Splitting: Implements a recursive character text splitter to handle large documents.
API Integration: Integrates with the ChatGroq API for natural language processing.

Code Explanation

Load Environment Variables: The dotenv library is used to load the Groq API key from the .env file.
Document Loading: Documents are loaded from a specified URL using the WebBaseLoader.
Text Splitting: Documents are split into chunks of 1000 characters with an overlap of 200 characters using RecursiveCharacterTextSplitter.
Vector Store with FAISS: FAISS (Facebook AI Similarity Search) is used to create and store document vectors, enabling efficient similarity searches to find relevant document chunks based on the query.
Chat Interface: The main interface is created using Streamlit, with a text input for user queries.
Model Initialization: The ChatGroq model is initialized with the API key and specified model name.
Custom Prompt Template: A template for generating responses based on the retrieved document context is created using ChatPromptTemplate.
Retrieval Chain: A retrieval chain is created to handle document retrieval and response generation.
Response Time Measurement: The response time for the chatbot is measured and printed.

Key Differences from a Usual Chatbot

Retrieval-Augmented Generation (RAG): Combines document retrieval with language generation for more accurate and contextually relevant responses.
Document Loading and Splitting: Uses WebBaseLoader to load documents and RecursiveCharacterTextSplitter to split them into manageable chunks.
Vector Store with FAISS: Utilizes FAISS for efficient similarity searches to retrieve relevant document chunks.
Integration with LangChain Components: Employs various LangChain components for embeddings, vector storage, and document retrieval.
Custom Prompt Template: Ensures responses are based on the provided document context, enhancing relevance and accuracy.
Streamlit Interface: Provides a user-friendly web interface with an expander to display relevant document chunks.

Models Tested

Gemma 7b: Response time: 0.3556 seconds
Mixtral 8x7b: Response time: 0.4536 seconds (best performance)
LLaMA3 8b: Response time: 0.3092 seconds

Results

The Mixtral 8x7b model provided the best answers, being elaborate and contextually accurate compared to other models tested.
