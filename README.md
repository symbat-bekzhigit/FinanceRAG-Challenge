# FinanceRAG-Challenge

## Description: 
The Financial RAG Challenge aims to advance RAG systems that can efficiently handle large-scale financial documents. Participants are tasked with building a system that can retrieve relevant contexts from extensive financial datasets. In doing so, they must demonstrate the ability to handle real-world challenges, including financial terminology, industry-specific language, and numerical data. 

The task is to retrieve the most relevant document corpus for a given query from a large document database. This process can be done by converting the query into an embedding and searching through a pre-indexed database of document embedding vectors. An effective search and reordering system that can prioritize documents similar to the query must be implemented.
* Goal : The goal of the task is to maximize the retrieval accuracy (nDCG@10) by accurately ranking the top relevant contexts for each query. The evaluation criterion is determined by how well the system ranks the retrieved contexts compared to the actual correct answers.


## Dataset: 
The competition provides an integrated dataset of text and table-formatted financial information, designed to test the system's ability to retrieve and reason with financial data. 

### Passage Retrieval:
* **FinDER:** This task involves retrieving relevant sections from 10-K reports and financial disclosures based on search queries that mimic real questions posed by financial experts. It incorporates domain-specific terms and abbreviations.
* **FinQABench:** This benchmark tests the performance of AI models in answering queries about 10-K reports, evaluating their ability to detect misinformation and maintain factual accuracy.
* **FinanceBench:** This task involves using natural language queries to retrieve relevant information from publicly available documents, such as 10-K and annual reports, assessing how well systems handle realistic financial questions.

### Tabular and Text Retrieval:
* **TATQA:** This task requires answering natural language queries that demand numerical reasoning based on data combined from tables and text in financial reports. It includes basic arithmetic, comparisons, and logical reasoning.
* **FinQA:** This challenge involves answering complex natural language queries in financial reports through multi-step numerical reasoning, requiring precise extraction and calculation from both text and table data.
* **ConvFinQA:** This task involves responding to queries through multiple conversational turns in financial reports, maintaining accurate context across turns to provide precise answers.
* **MultiHiertt:** This task requires multi-step query resolution based on hierarchical tables and unstructured.

### Example:
Example document: Description of MSFT services and products.<br /> 
Example query: "What are Microsoft's revenue streams?"<br /> 


## Our Approach:
#### Step 0: Preprocessing
Cleaned and validated the dataset for consistent and efficient retrieval.
#### Step 1: Data Chunking
Splitted the large corpus of documents into manageable chunks (e.g., 512 characters) to facilitate efficient retrieval and processing.
#### Step 2: Chunk Embedding
Generated vector embedding for each chunk using a pre-trained large model Stella EN 400M V5, converting text into a numeric format for similarity-based search.
#### Step 3: Query Expansion
Rewrote queries using OpenAI API to provide additional context and improve retrieval scores.
#### Step 4: Chunk Retrieval
Retrieved the most relevant (i.e., top-10 similar chunks) from the database based on the similarity between the chunk embeddings and the question embedding.

***

_Detailed report about our approach can be found in the **"Project Details.pptx"** file of this repository._

_This project was done as a submission for the 4th UNIST-KAIST-POSTECH AI & Data Science Competition in a team of two_

_Kaggle Website for the competition: https://www.kaggle.com/competitions/4-ai-and-datascience-competition/overview_
