# **MetaNest: AI-Driven Research Intelligence Platform**

**MetaNest** is an AI-powered research paper management and discovery platform that goes beyond traditional keyword-based search. It enables researchers to upload academic PDFs, automatically extract structured metadata, and discover relevant papers using a **hybrid search system** that combines database filtering with semantic understanding powered by machine learning.

---

## 🚀 Vision

Conventional research search systems depend heavily on exact keywords. This often fails when users are unaware of the precise terminology used in a paper. For example, searching for *“Artificial Intelligence”* may miss highly relevant work titled *“Deep Neural Architectures”*.

MetaNest addresses this limitation by converting research papers into **vector embeddings**, allowing the system to understand conceptual similarity rather than relying solely on exact word matches.

---

## 🔍 Core Features

### 🔹 Hybrid Search Engine

* Combines **MongoDB keyword filtering** (author, year, category)
* With **semantic vector similarity search** over abstracts and full text
* Produces ranked results based on both relevance and meaning

### 🔹 Automated Paper Ingestion

* Upload a research PDF
* Automatically extracts text and metadata
* Generates AI embeddings in real time
* Indexes documents instantly for search

### 🔹 Role-Based Access Control (RBAC)

* **Researchers**: Upload papers and perform searches
* **Admins**: Moderate content and remove papers
* All permissions are enforced securely at the server level

### 🔹 Analytics Dashboard

* Visualizes publication trends
* Category-wise paper distribution
* Time-based insights for stored research

---

## 🛠️ Engineering Challenges & Solutions

### **1️⃣ Hybrid Search Data Conflict**

**Problem:**
Keyword-based queries returned structured dictionaries, while semantic search produced similarity-score tuples. Merging these incompatible formats caused runtime failures.

**Solution:**
A custom **standardization layer** was introduced to normalize results from both search engines into a unified JSON-compatible schema. This allowed the frontend to remain completely agnostic to the search source.

---

### **2️⃣ Modern Python Compatibility Issues**

**Problem:**
Integrating Hugging Face Transformers caused runtime failures due to incompatibilities with newer Python environments during model initialization.

**Solution:**
Instead of downgrading the environment, the dependency stack was carefully reconfigured using stable, compatible versions of `torch` and `transformers`, preserving performance while restoring AI functionality.

---

### **3️⃣ Securing Admin-Only Operations**

**Problem:**
Early implementations exposed destructive admin actions (such as deleting papers) to all users at the UI level, creating a severe security risk.

**Solution:**
Strict **server-side role validation** was implemented. Sensitive operations are conditionally rendered and executed only when a verified admin session exists, eliminating the possibility of unauthorized access—even through client-side manipulation.

---

## 🧰 Tech Stack

* **Frontend:** Streamlit (Python)
* **Backend Logic:** Python
* **Database:** MongoDB Atlas (Vector Search)
* **AI / NLP:** Hugging Face Transformers (`all-MiniLM-L6-v2`)
* **Authentication:** Session-based Role Management
* **Visualization:** Pandas, Altair

---

## 📦 Installation & Setup

Clone the repository:

```bash
git clone https://github.com/Harshsalunke100/MetaNest.git
cd MetaNest
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
streamlit run app.py
```

---

## 🌐 Deployment

MetaNest is designed to be deployed on **Streamlit Community Cloud** with MongoDB Atlas for scalable vector search.

---

## 🎯 Why This Project Matters

MetaNest demonstrates:

* Real-world **AI + database hybrid search**
* Practical use of **semantic embeddings**
* Secure role-based system design
* Debugging and productionizing a complex ML application

This project reflects **industry-level problem solving**, not just model usage.






