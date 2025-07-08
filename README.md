# 🧬 MirBERT Pipeline

**MirBERT** is a biomedical text-mining pipeline that extracts and predicts functional relationships between **miRNAs** and **target genes** from PubMed abstracts. It combines Named Entity Recognition (NER), lexicon-based annotation, and an ensemble of BERT models to detect validated miRNA–gene interactions.

---

## 🚀 Features

- ✅ Input: list of PubMed IDs (PMIDs)
- 🔍 Identifies miRNA and gene mentions using a custom lexicon and Stanza NER
- 🤖 Predicts validated interactions with an ensemble BERT classifier
- 📤 Outputs a `.tsv` file with structured results

---

## 🐳 Usage with Docker
