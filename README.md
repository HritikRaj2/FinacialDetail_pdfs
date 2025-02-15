# Financial Data Extraction Using Open-Source LLMs

## 📌 Overview
T*local embeddings and regex-based extraction techniques**. The extracted data includes:
- 📌 **Company Name**  
- 📅 **Report Date**  
- 💰 **Profit Before Tax**  
- 📊 **Revenue from Operations**  
- 📈 **Total Income**  
- 📉 **Total Expenses**  
- 🏦 **Net Profit After Tax**  

The processed data is stored in **Astra DB (Cassandra)** for efficient retrieval.

---

## 📂 Files and Structure
```
📁 project-folder/
│── 📜 financial_extraction.py    # Main Python script for extraction
│── 📜 extracted_data.json        # Output file with structured financial data
│── 📜 requirements.txt           # Dependencies
│── 📜 README.md                  # Project documentation (this file)
│── 📁 pdfs/                      # Folder containing input financial reports
```

---

## 🛠 Technical Stack
- **Python Libraries:** `cassio`, `langchain`, `sentence-transformers`, `PyPDF2`, `regex`
- **Vector Storage:** `AstraDB (Cassandra)`
- **Financial Data Extraction:** **Regex-based entity extraction**
- **Embeddings Model:** `all-MiniLM-L6-v2` (Local)

---

## 🚀 Installation and Setup
### 1️⃣ Install Required Dependencies
Run the following command to install necessary libraries:
```bash
pip install -q cassio datasets langchain tiktoken PyPDF2 sentence-transformers langchain-community
```

### 2️⃣ Set Up Astra DB Credentials
Ensure you have your **Astra DB application token** and database ID.
```python
ASTRA_DB_APPLICATION_TOKEN = "your_astra_token"
ASTRA_DB_ID = "your_database_id"
cassio.init(token=ASTRA_DB_APPLICATION_TOKEN, database_id=ASTRA_DB_ID)
```

### 3️⃣ Run the Extraction Script
Execute the Python script to process the PDFs and extract data:
```bash
python financial_extraction.py
```
The results will be stored in `extracted_data.json`.

---

## 🔍 Methodology
### ✅ **Text Extraction**
- **Reads PDFs** using `PyPDF2`
- **Splits text into chunks** for vector storage

### ✅ **Vector Storage in AstraDB**
- **Embeds text** using `sentence-transformers`
- **Stores document chunks** in AstraDB for retrieval

### ✅ **Financial Data Extraction**
- **Uses regex patterns** to extract key financial details
- **Backup line-by-line search** if regex fails

---

## 📈 Example Output (JSON Format)
```json
{
  "Company Name": "ABC Pvt Ltd",
  "Report Date": "05 Feb 2025",
  "Profit Before Tax": "₹120 crores",
  "Revenue from Operations": "₹500 crores",
  "Total Income": "₹550 crores",
  "Total Expenses": "₹430 crores",
  "Net Profit After Tax": "₹90 crores"
}
```

---

## 🔹 Future Enhancements
✔ **Improve accuracy with fine-tuned NLP models**
✔ **Implement LLM-based entity extraction for better precision**
✔ **Enhance scalability using cloud-based vector stores**

---

## 📧 Contact
For any queries, feel free to reach out:
- **Name:** Hritik Raj
- **Email:** hritikraj723@gmail.com
- **GitHub:** https://github.com/HritikRaj2

🚀 **Thank you for reviewing my submission!**

