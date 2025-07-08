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

### 1. Build the Docker image

```bash
docker build -t mirbert .

### 2. Prepare your data/ directory

On your local machine, create a folder named data/ that contains:

data/
├── config.yml              # Path configuration
├── list_of_PMIDs.txt       # Input PMIDs (one per line)
└── models/
    └── stanza/             # BioNLP13CG NER model files

Example config.yml:

input_file: /data/list_of_PMIDs.txt
output_file: /data/output.tsv
stanza_model_dir: /data/models/stanza/

    All paths should start with /data/, which maps to the local data/ folder when mounted inside the container.

### 3. Run the pipeline

docker run \
  -v /absolute/path/to/your/data:/data \
  mirbert \
  --config /data/config.yml

The output.tsv file will be saved inside your local data/ directory.
