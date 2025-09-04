# panGPSR-reconstruction
large scale reconstruction of pan gene-to-protein-to-structure-to-reaction for prokaryotes


## Method Overview (Figure)

<p align="center">
  <img src="docs/assets/method_overview.png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure.* High-level workflow for automated pangenome and metabolic modeling.


### Key Result
![Accuracy vs. Dataset Size](docs/assets/accuracy_vs_size.png)

> Caption: Accuracy improves with dataset size across three models (error bars: 95% CI).

[View full-res](docs/assets/accuracy_vs_size_full.png)
