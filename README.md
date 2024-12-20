# Computer Vision Hackathon NLP Part

## Persian to English Vector Database Search

This Jupyter notebook demonstrates how to create and use a vector database for searching English text content using Persian queries. The system uses LanceDB for vector storage and includes a translation pipeline to convert Persian queries to English before searching.

### Features

- Vector database creation with LanceDB
- Persian to English query translation
- Full-text search capabilities
- Sample dataset of 30 English sentences across various topics

### Requirements

The following packages are required:
```bash
pip install lancedb
pip install tantivy
pip install transformers
```

### Components

#### 1. Database Creation
- Uses LanceDB to store vector embeddings and text data
- Creates a table called 'news' with vector embeddings and text content
- Implements full-text search indexing on the text field

#### 2. Translation System
- Utilizes the Hugging Face transformers library
- Uses the "barghavani/Farsi-to-English" translation model
- Translates Persian queries to English before searching

#### 3. Sample Dataset
The database includes 30 sample sentences covering various topics:
- Technology and Computing
- Business and Work
- Education and Learning
- Health and Wellness
- Environment
- Entertainment and Culture

### Usage

1. Run the installation cells to set up required packages
2. Execute the database creation function:
```python
tbl = create_database()
```

3. Search using Persian queries:
```python
results = search('مهارت', tbl)  # Searches for "skill" in English
```

### Output Format
The search results are returned as a pandas DataFrame containing:
- vector: The embedding vector
- text: The matched English text
- _score: The relevance score of the match

### Notes
- The vector values in the sample data are simplified (1-30) for demonstration purposes
- In a production environment, these should be replaced with actual embeddings
- The full-text search index is created automatically on the 'text' field

### Example
```python
# Create database
tbl = create_database()

# Search in Persian
result = search('فرهنگ', tbl)
# Returns matches related to "skill" in the English dataset
```
