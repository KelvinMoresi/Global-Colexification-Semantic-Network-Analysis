# Global Colexification Semantic Network Analysis

This repository contains an advanced network science and computational linguistics pipeline that models cross-linguistic semantic structures. By evaluating global **colexification patterns**—phenomena where a single word form expresses multiple distinct concepts across different languages (e.g., a single word meaning both "SPIDER WEB" and "SLEEP")—this project maps the structural topology of human meaning. 

The primary research objective is an algorithmic investigation into the **Universality Gradient** and the **Structural Bridge Hypothesis** of parts of speech, proving via Monte Carlo permutation testing that action and existence verbs act as crucial global semantic bridges across distinct cultural domains.

## Core Analytical Pipeline

The Python engine handles complex graph structures using `networkx` and runs statistical verification models across several key stages:

1. **Topological Filtering & Giant Component Extraction:** Cleans raw multi-language colexification data (`colexifications.csv`), keeping only semantic edges that appear in at least 3 distinct language families to ensure cross-cultural universality. It isolates the giant connected component to discard isolated topological islands.
2. **Network Topology & Scale-Free Verification:** Computes the network's degree distribution on a log-log scale to evaluate heavy-tailed power-law behaviors, and calculates the Global Clustering Coefficient and Average Shortest Path Length.
3. **Macro-Structural Louvain Modularity Clustering:** Utilizes the Louvain community detection algorithm to partition the semantic graph into discrete thematic neighborhoods. Communities are automatically labeled by identifying the local bottleneck node possessing the highest local Betweenness Centrality.
4. **Grammatical Part-of-Speech (POS) Tagging:** Implements an automated linguistic tagger combining a contextual manual override dictionary with hierarchical algorithmic lookups across the WordNet lexical database via NLTK.
5. **Monte Carlo Permutation Tests:** Runs non-parametric statistical simulations (1,000 iterations) shuffling global betweenness centrality metrics to generate a null model distribution, quantitatively validating the significance (Z-score) of structural bridging properties across verbs, nouns, and adjectives.
6. **Ego-Network & Bridge Visualization:** Generates topological map snapshots tracking the universality gradient across filtering thresholds (at least 3, 5, 10, and 20 language families) and produces publication-ready graphics mapping the localized structural reach of hub concepts like `"SAY"`.

---

## Tech Stack & Library Dependencies

The environment relies on scientific computing and graphing libraries:
* **Data Engineering & Scripting:** `python`, `pandas`, `numpy`
* **Graph & Network Topology Engineering:** `networkx`, `python-louvain`
* **Statistical Computation & NLP:** `scipy`, `nltk` (WordNet lexical corpus)
* **High-Fidelity Visualization:** `matplotlib`, `seaborn`, `adjustText`

---

## Visualizing Key Insights

The scripts output data visualizations detailing the structural properties of language:

### 1. Universality Gradient
As the threshold for cross-cultural stringency increases from 3 families up to 20, the global network undergoes a clear phase transition. The core structural modularity score shifts dynamically before collapsing into a tight, universal core of 13 primary multi-cultural nodes.

### 2. Semantic Node Roles by Part of Speech
By mapping nodes across Eigenvector Centrality (local "echo chambers" or dense thematic domains) versus Betweenness Centrality (global "bridges" crossing macro-clusters), the pipeline visually separates grammatical categories by structural utility:
* **Nouns** pack tightly inside high-eigenvector clusters.
* **Verbs** scale steeply along the high-betweenness axis, acting as systemic informational bottlenecks.

---

## How to Run the Infrastructure

### 1. Clone the Environment
```bash
git clone [https://github.com/KelvinMoresi/sunspot-topology-analysis.git](https://github.com/KelvinMoresi/sunspot-topology-analysis.git)
cd sunspot-topology-analysis
