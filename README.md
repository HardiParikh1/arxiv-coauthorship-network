# arXiv Co-Authorship Network Analysis
 
Models arXiv co-authorship as a graph for each year from 2000 to 2024, to study how collaboration grows, forms communities and crosses fields, and whether future co-authorships can be predicted. Built for Network Science (CSE655) at IIIT Delhi.
 
**Data:** [arXiv metadata snapshot](https://www.kaggle.com/datasets/Cornell-University/arxiv) (Kaggle). The yearly graphs use 1M records, excluding papers with more than 30 authors.
 
## What it does
 
- **Temporal evolution:** 25 yearly graphs (up to 328K authors and 1.9M edges) tracking degree, clustering, density and degree distributions
- **Communities:** Louvain community detection and modularity for each year
- **Interdisciplinarity:** field diversity per author, a field co-occurrence heatmap and "bridge" authors
- **Link prediction:** trains on 2010–2015 (3.1M edges) and tests on links formed in 2016–2018, using Jaccard, Adamic–Adar and Preferential Attachment
- **Case study:** cs.LG (machine learning) on its own
## Key results
 
- Strong community structure: modularity of 0.97–0.99 in most years, dipping to 0.86 in 2015
- Heavy-tailed degree distributions: a few hub authors, most authors with few co-authors
- cs.LG grew from a niche category into one of arXiv's largest, tightly clustered fields
- Link prediction Precision@100: 0.11 for Adamic–Adar, 0.05 for Jaccard, 0.00 for Preferential Attachment. Shared co-authors predict future collaboration better than popularity does
## Limitations
 
Authors are matched by name, so common names merge different people. Each author's main field is picked arbitrarily when they publish in several fields, and years come from `update_date`. Next steps: author disambiguation and learned link-prediction models (for example graph neural networks).
 
## Run
 
Open [`arxiv_coauthorship.ipynb`](arxiv_coauthorship.ipynb) in Kaggle or Colab, add the dataset, set `file_path`, then `pip install python-louvain` and run all cells.
 
**Stack:** Python, NetworkX, python-louvain, Pandas, NumPy, Matplotlib, Seaborn
 
