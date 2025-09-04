# panGPSR-reconstruction
large scale reconstruction of pan gene-to-protein-to-structure-to-reaction for prokaryotes


## Method Overview (Figure)

<p align="center">
  <img src="/documents/Lacto-panGPSRs.jpg" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure.* High-level workflow for automated pangenome and metabolic modeling.


flowchart LR
  A[Obtain Genomes]
  B[QA/QC<br/>• contamination • taxonomy • Mash clustering<br/>• completeness • contiguity]
  C[Annotation<br/>(BAKTA)]
  D[Pangenome<br/>(CD-HIT)]
  E[panGPRs]
  F[GEM reconstruction<br/>(CarveMe)]
  G[Neighborhood analysis<br/>& pangenome graph]
  H[Protein stoichiometry<br/>(SWISS-MODEL)]
  I[3D Modeling]
  J[Structural analysis]

  A --> B --> C --> D
  C --> F
  D --> G
  E --> F
  H --> E
  I --> E
  I --> J





### Key Result
![Accuracy vs. Dataset Size](docs/assets/accuracy_vs_size.png)

> Caption: Accuracy improves with dataset size across three models (error bars: 95% CI).

[View full-res](docs/assets/accuracy_vs_size_full.png)
