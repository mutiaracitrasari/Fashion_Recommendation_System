#  Fashion Recommendation with Multimodal RAG

This project is a **fashion product recommendation system** that utilizes a **Retrieval-Augmented Generation (RAG)** approach, combining **semantic text embeddings** with structured product data and style knowledge to deliver personalized fashion suggestions.

## Features

*  Recommends fashion items based on user queries or preferences.
*  Integrates product descriptions with **styling tips** for richer recommendations.
*  Uses `SentenceTransformer` (`all-MiniLM-L6-v2`) to generate semantic embeddings.
*  Fast similarity search powered by **FAISS**.
*  Works with structured CSV fashion datasets.
*  Employs lightweight NLP to make the chatbot context-aware.

---

## Dataset

The system uses two core datasets:

1. **Fashion Product Dataset (`fashion_dataset.csv`)**

   * Fields: `id`, `name`, `description`, `style`, `price`

2. **Styling Tips Dataset**

   * Manually created mapping between style types and expert advice (e.g., "Business", "Casual", "Evening")

---

## Tech Stack

| Tool/Library             | Description                                     |
| ------------------------ | ----------------------------------------------- |
| `pandas`                 | Data manipulation and preprocessing             |
| `sentence-transformers`  | Semantic embedding model for text understanding |
| `faiss-cpu`              | Fast vector similarity search                   |
| `scikit-learn`           | Similarity metrics                              |
| `transformers`           | Optional for additional NLP capabilities        |
| `langchain` & `chromadb` | (Prepared for future multimodal integration)    |

---

## How It Works

1. **Load Data**: Fashion items and tips are read into DataFrames.
2. **Embedding Generation**: Product descriptions and styling advice are embedded into vectors.
3. **Index Building**: Vectors are added to a FAISS index for fast similarity search.
4. **User Query**: A user's fashion preference (e.g., "summer casual") is embedded and matched.
5. **Recommendation**: Top-N similar fashion items are returned with optional styling context.

---

## Installation

To run this notebook on **Google Colab**, ensure you install dependencies:

```bash
!pip install -q sentence-transformers faiss-cpu langchain chromadb
```

---

## Example Query

**Input:**
`"What are some good formal outfits for a gala?"`

**Output:**

* Red Evening Gown
* Sequin Party Dress
* Styling Tip: "Formal occasions require elegant pieces. Choose floor-length gowns or sophisticated cocktail dresses."

---

## Notes

* This system is text-only for now but designed to support **multimodal RAG** in the future by including images.
* Good for building chatbot-style assistants for e-commerce fashion platforms.

---

## File Structure

```
fashion__Recommendation.ipynb   # Main notebook
fashion_dataset.csv             # Dataset with fashion item metadata
README.md                       # This file
```

---


