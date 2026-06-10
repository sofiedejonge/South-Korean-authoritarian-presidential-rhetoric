# Software Requirements & Environment Dependencies  
  
This document outlines the software versions, language environments, and non-default libraries required to fully replicate the text preprocessing, LDA topic modeling, sentiment analysis.  
  
  
 1. Orange Data Mining Environment  
The primary natural language processing (NLP) pipeline, dictionary mapping, and topic extractions were executed inside the graphical Orange environment.  
  
* **Orange Version:** `v3.35.0` (or higher)  
* **Required Add-ons (Non-Default):**  
  * **Orange-Text:** `v1.10.0` (Provides widgets for *Import Documents*, *Preprocess Text*, *Topic Modeling*, and *Sentiment Analysis*).  
  
  
2. Python Interoperability (Optional Backup)  
*If you used Python script widgets directly inside Orange or executed standalone scripts for the data preprocessing phase (e.g., tokenization or character normalization):*  
  
* **Python Version:** `v3.9.x` or `v3.10.x`  
* **Non-Default Python Packages:**  
  * `Orange3-Text` (v1.10.0)  
  * `KoNLPy` (v0.6.0) – Specifically utilizing the `Okt` (Open Korean Text) module for morphological analysis and tokenization of the Korean corpus.  
  
  
  
 Replication Notes  
1. **Orange Reproducibility:** To replicate the workflow visually, open Orange, ensure the `Text` add-on is installed, and load the provided `.ows` workflow file.  
