# panGPSR-reconstruction
large scale reconstruction of pan gene-to-protein-to-structure-to-reaction for prokaryotes


## Method Overview (Figure)

<p align="center">
  <img src="/documents/Lacto-panGPSRs.jpg" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure.* High-level workflow for automated pangenome and metabolic modeling.


## Methods Overview

**Summary.** Automated, end-to-end workflow for large-scale microbial genomics and metabolic modeling. The pipeline ingests genomes, performs rigorous QA/QC, annotates proteins, builds a non-redundant pangenome, reconstructs strain-resolved GEMs, derives panGPRs, analyzes genomic neighborhoods, and integrates structure-aware refinement.

### Pipeline Stages

1. **Obtain Genomes**  
   Retrieve assemblies and metadata; standardize file formats and identifiers for downstream steps.

2. **QA/QC**  
   Assess contamination and taxonomic assignment; cluster genomes (Mash) and evaluate completeness and contiguity; exclude or flag low-quality genomes.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (1).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure.* Genomes distribution across genera, species and geographical locations.   

4. **Annotation (BAKTA)**  
   Generate consistent, evidence-backed functional annotations at the protein level to support pangenome and metabolic reconstruction.

5. **Pangenome (CD-HIT)**  
   Cluster proteins to form non-redundant ortholog groups; build a pangenome graph that captures core, accessory, and rare gene families.

6. **GEM Reconstruction (CarveMe)**  
   Construct draft, strain-resolved GEMs from annotated proteomes; harmonize model identifiers and media definitions for comparative analysis.

7. **panGPRs**  
   Derive gene–protein–reaction (GPR) rules across strains; quantify the diversity of genetic implementations for each metabolic reaction at pangenome scale.

8. **Neighborhood Analysis & Pangenome Graph**  
   Map gene neighborhoods and co-occurrence patterns; integrate with the pangenome graph to study genomic context and mobility.

9. **Protein Stoichiometry (SWISS-MODEL)**  
   Obtain or estimate subunit stoichiometries and complex composition to refine GPRs and reaction assignments.

10. **3D Modeling**  
   Generate or retrieve structural models for selected proteins/complexes to enable structure-informed curation and downstream predictions.

11. **Structural Analysis**  
    Analyze model quality and interfaces; link structural features to function, kinetics, or variant effects when relevant.

---

  





### Key Result
![Accuracy vs. Dataset Size](docs/assets/accuracy_vs_size.png)

> Caption: Accuracy improves with dataset size across three models (error bars: 95% CI).

[View full-res](docs/assets/accuracy_vs_size_full.png)
