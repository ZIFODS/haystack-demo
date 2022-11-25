# Haystack Experiment

---

In this repository, I will experiment with the Haystack (https://haystack.deepset.ai/) NLP framework to perform the following a number of NLP tasks using data from the ArXiv repository (https://www.kaggle.com/datasets/Cornell-University/arxiv).

## Data

### ArXiv dataset

arXiv dataset and metadata of 1.7M+ scholarly papers across STEM. PDF documents downloaded from a publically accessible S3 bucket.

You can download the data, a single JSON file, from here: https://www.kaggle.com/datasets/Cornell-University/arxiv. Once downloaded, the data should be placed in `/data/arxiv/arxiv-metadata-oai-snapshot.json` within this repository.

Documents are generated using a combination of the title and abstract.

## NLP Tasks

Within the Notebooks directory, you will find three examples:

* Document retrieval - semantic search with a single query and retrieval of documents
* Document matching - semantic search using a document and retrieving similar documents
* Question Answer - extractive question answer pipeline that searches the ArXiv document library for a span of text that answers a question


## Development

The work in this repository is exploratory and was performed using Jupyter Lab. The models require a GPU, for this work I used an Nvidia Geforce RTX 3060 and CUDA Version 11.6. Haystack was installed in a conda environment using:

```console
pip install farm-haystack[all-gpu]
```

Some modifications were required post install:

* `faiss-cpu` has to be downgraded to version 1.7.2
* PyTorch had to be manually updated to work with my GPU

