# Naive RAG Implementation

This project demonstrates a basic Retrieval Augmented Generation (RAG) pipeline using the following components:

* **FAISS:**  Efficient similarity search for finding relevant documents.
* **GCP Generative AI (e.g., Vertex AI):** Powerful language model for generating embeddings and responses.
* **Jupyter Notebook:**  Interactive environment for running the RAG pipeline.

## Getting Started

### Prerequisites

1. **Google Cloud Platform (GCP) Account:** You'll need a GCP account with access to Vertex AI or other suitable generative AI services.
2. **Python 3.x:** Make sure you have Python installed.

### Setup

1. **Create a Virtual Environment:**
   ```bash
   python -m venv rag_env
   source rag_env/bin/activate  # On Windows, use `rag_env\Scripts\activate`
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Prepare your GCP Credentials:**
   * Set up a GCP project and enable the necessary APIs (e.g., Vertex AI).

4. **Run the Jupyter Notebook:**
   ```bash
   jupyter-lab rag_pipeline.ipynb
   ```

## How it Works

1. **Document Loading:** The dataset (`first_five_netflix_titles.csv`) is loaded into memory.
2. **Index Creation:**  A FAISS index is built from the documents embeddings for fast similarity search.
3. **Query Processing:**
   * A user's query is received and embeddings are generated for it.
   * FAISS searches for relevant documents based on similarity.
   * The relevant documents are combined with the LLM prompt.
   * The combined text is sent to the GCP Generative AI model to generate a response.


## Customization

Feel free to modify the following:

* **Dataset:** Replace `first_five_netflix_titles.csv` with your own documents.
* **GCP Model:** Choose the GCP Generative AI model that best suits your needs.
* **Parameters:** Experiment with different FAISS and GCP model parameters for optimal performance.

## Important Notes

* This is a simplified RAG implementation intended for demonstration purposes.
* For production use, consider:
   * Optimizing the FAISS index for larger datasets.
   * Implementing robust error handling and logging.
   * Fine-tuning the GCP Generative AI model on your specific domain or task.
