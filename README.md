<div align="center">
  <h2>Hands-on LLMs Course - My Experience</h2>
  <h1>Building a Real-Time Financial Advisor System</h1>
  <i>by Idir HAREB</i>
</div>

## Introduction

In this project, I explored the world of Large Language Models (LLMs) and built a real-time financial advisor system using a 3-pipeline architecture. This project was inspired by the original Hands-on LLMs Course created by Paul Iusztin, Pau Labarta Bajo, and Alexandru Razvant.

## Technologies Used

* **Large Language Models (LLMs)**: Used a financial Q&A datasetto fine-tune and deployan open-source LLM.
* **QLoRA**: Employed QLoRA to fine-tune the LLMs and adapt them to the financial domain.
* **Beam**: Utilized Beam as a serverless GPU infrastructure to deploy the training and inference pipelines.
* **Qdrant**: Chose Qdrant as a serverless vector database to store and query the financial news embeddings.
* **Comet ML**: Used Comet ML as a serverless ML platform to track experiments, log results, and deploy the inference pipeline.
* **Poetry**: Managed project dependencies using Poetry.
* **Ruff**: Employed Ruff for linting the code.
* **Black**: Used Black for code formatting.
* **CI/CD**: Set up continuous integration and continuous deployment pipelines.
* **Alpaca API**: Fetched financial news from Alpaca API.
* **SentenceTransformers**: Transformed news documents into embeddings.
* **Bytewax**: Cleaned and transformed data in real-time.
* **LangChain**: Created chains for enhanced prompt querying and response generation.

## Why these technologies?

I chose these technologies because they offered a scalable, flexible, and cost-effective way to build and deploy a real-time financial advisor system. LLMs provided a powerful foundation for natural language understanding, while QLoRA enabled me to adapt the models to the financial domain. Beam and Qdrant offered a serverless infrastructure for deploying and querying the models, and Comet ML provided a unified platform for tracking experiments and deploying the inference pipeline. Poetry, Ruff, and Black helped ensure code quality and maintainability.

## Project Steps

### Training Pipeline: Fine-tuning an LLM on Financial Q&A Dataset

1. **Load Dataset**: Loads a proprietary Q&A dataset.
2. **Fine-tune Model**: Fine-tunes an open-source LLM using QLoRA.
3. **Track Experiments**: Logs the training experiments on Comet ML's experiment tracker & the inference results on Comet ML's LLMOps dashboard.
4. **Store Model**: Stores the best model on Comet ML's model registry.
5. **Deploy Pipeline**: The training pipeline is deployed using Beam as a serverless GPU infrastructure.

### Streaming Pipeline: Fetch Data from Alpaca Financial News API

1. **Ingest News**: Ingests financial news from Alpaca.
2. **Transform Data**: Cleans & transforms the news documents into embeddings (using SentenceTransformers) in real-time using Bytewax.
3. **Store Embeddings**: Stores the embeddings into the Qdrant Vector DB.

### Inference Pipeline: Real-Time Financial Advice System

1. **Load Model**: Downloads the fine-tuned model from Comet's model registry.
2. **User Input**: Takes user questions as input.
3. **Query Database**: Queries the Qdrant Vector DB and enhances the prompt with related financial news.
4. **Generate Response**: Calls the fine-tuned LLM for financial advice using the initial query, the context from the vector DB, and the chat history.
5. **Persist Chat History**: Persists the chat history into memory.
6. **Log Results**: Logs the prompt & answer into Comet ML's LLMOps monitoring feature.
7. **Deploy Pipeline**: The inference pipeline is deployed using Beam as a serverless GPU infrastructure, as a RESTful API.

## What I learned

Through this project, I gained hands-on experience with LLMs, fine-tuning, and deploying AI models. I learned how to design and implement a 3-pipeline architecture, leveraging the strengths of each technology to build a robust and scalable system. I also developed a deeper understanding of the importance of data preprocessing, model selection, and hyperparameter tuning in achieving optimal results. Additionally, I learned:

* How to structure an MLOps project for scalability and maintainability.
* The process of creating a domain-specific Q&A dataset by prompting an LLM.
* Fine-tuning Falcon-7B with the created dataset.
* Using Poetry for dependency management.
* Implementing code linting and formatting with Ruff and Black.
* Setting up CI/CD pipelines to automate testing and deployment. (Optional)

## Future Work

In the future, I plan to continue exploring the applications of LLMs in finance and expand this project to incorporate additional features and capabilities.

## Acknowledgments

I would like to thank Paul Iusztin, Pau Labarta Bajo, and Alexandru Razvant for creating the original Hands-on LLMs Course, which inspired this project. Their work has been instrumental in helping me learn and grow as a machine learning engineer.

