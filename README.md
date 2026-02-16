# scRNAseq_pancreas_applying_deep_learning_methods
Deep generative modeling (SCVI) vs Classical Clustering vs CellTypist.
This notebook highlights three complementary approaches for single-cell analysis.

1) Classical clustering.

Workflow: normalize → log-transform → PCA/UMAP → Leiden clustering.
Purpose: Identify groups of transcriptionally similar cells.
Pros: Simple, interpretable, widely used.
Cons: Sensitive to batch effects, may miss rare cell populations, cluster labels are arbitrary until annotated.

2) CellTypist annotation.
   
Workflow: Use a reference-trained classifier to assign cell type labels directly to each cell based on expression profiles.
Purpose: Map clusters or individual cells to known biological cell types.
Pros: Fast, interpretable, uses curated reference datasets.
Cons: Cannot discover novel cell types; quality depends on reference coverage.

4) SCVI (deep generative modeling).
   
Workflow: Train a variational autoencoder on raw counts → learn latent embeddings → use embeddings for clustering, and visualization.
Purpose: Capture underlying structure of high-dimensional gene expression data robustly, including batch-corrected and subtle variation.
Pros: Handles batch effects automatically, identifies rare or subtle populations, probabilistic embeddings.
Cons: Less immediately interpretable than classical clustering, requires more computation.
