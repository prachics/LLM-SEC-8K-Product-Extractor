# LLM-Based SEC 8-K Product Extraction

This project analyzes **SEC Form 8-K** filings to extract new product announcements using **Large Language Models (LLMs)** and **Named Entity Recognition (NER)**. The structured output is stored in a CSV format for further analysis.

---

## 📌 Objective

The goal is to identify and extract:
- Company Name
- Stock Ticker
- Filing Time
- New Product Name
- Product Description (≤180 characters)

From the 8-K filings published by public companies using SEC-provided data.

---

## 🧠 Methodology

1. **CIK Mapping**:  
   - `https://www.sec.gov/files/company_tickers.json` is used to map stock tickers to CIK codes.

2. **Filing Retrieval**:  
   - `https://www.sec.gov/cgi-bin/browse-edgar` is used to fetch recent 8-K filings for each company.

3. **Text Extraction**:  
   - BeautifulSoup parses the "Complete submission text file" from each filing.

4. **NER + LLM Processing**:  
   - spaCy performs Named Entity Recognition.
   - OpenAI GPT-3.5-turbo model extracts:
     - Product Name
     - Product Description

5. **Output Generation**:
   - Valid outputs are saved to `Filtered_SP500_8K_Filings.csv` in the following format:
     ```
     Company Name | Stock Name | Filing Time | New Product | Product Description
     ```



---

## 📂 Files

| File                            | Description                             |
|---------------------------------|-----------------------------------------|
| `LLM_Document_Analysis.ipynb`               | Jupyter Notebook with full implementation |
| `Filtered_SP500_8K_Filings.csv` | Final structured output in CSV format   |
| `README.md`                    | Project documentation                   |

---

## 🔧 Technologies Used

- `Python`
- `BeautifulSoup`
- `spaCy`
- `OpenAI API (GPT-3.5-turbo)`
- `pandas`
- `requests`

---

## 📌 Note

This project is part of a single-student academic assignment for analyzing SEC filings. You can scale this up to process filings from all S&P 500 companies or as permitted by rate limits.

---

## 🚀 Author

Prachi Saibewar  
GitHub: [github.com/prachics](https://github.com/prachics)
