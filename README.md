# Probing Transformer Layers for Syntactic Structure

# Project goal
Investigate how syntactic information is represented across layers of a pretrained Transformer using supervised probing experiments.

# Research Questions

1. How well can syntactic properties be predicted from different Transformer layers?
2. Which layers provide the most useful syntactic representations?
3. How do probing results change across experimental conditions?


# Planned workflow
1. Select a pretrained Transfoermer and a syntactic dataset.
2. Extract hidden representations from each layer.
3. Train simple probes on the extracted representations.
4. Evaluate and compare layer-wise performance.
5. Analyze results and document limitations.

# Project structure

- `src/` : experiment code
- `data/` : dataset instructions and local data
- `results/` : evaluation outputs
- `figures/` : plots and visualizations
