# panGPSR-reconstruction
large scale reconstruction of pan gene-to-protein-to-structure-to-reaction for prokaryotes


## Method Overview (Figure)

<p align="center">
  <img src="/documents/Lacto-panGPSRs.jpg" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 1.* High-level workflow for automated pangenome and metabolic modeling.


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

*Figure 2.* A) Genomes distribution across genera, B) species and C) geographical locations.   

4. **Annotation (BAKTA)**  
   Generate consistent, evidence-backed functional annotations at the protein level to support pangenome and metabolic reconstruction.

5. **Pangenome (CD-HIT)**  
   Cluster proteins to form non-redundant ortholog groups; build a pangenome graph that captures core, accessory, and rare gene families.

   <p align="center">
  <img src="/documents/Lacto-panGPSRs (2).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 3.* Pangenome analysis, D) family-level . E) species level



   <p align="center">
  <img src="/documents/Lacto-panGPSRs (3).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure.* Pangenome analysis, F) Cross-genera . G) Genus level





 <p align="center">
  <img src="/documents/Lacto-panGPSRs (4).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 4.* Pangenome analysis, H) Comulative pangenome - defining stabel core, accessory and rare (CAR) genes across the family




7. **GEM Reconstruction (CarveMe)**  
   Construct draft, strain-resolved GEMs from annotated proteomes; harmonize model identifiers and media definitions for comparative analysis.

9. **panGPRs**  
   Derive gene–protein–reaction (GPR) rules across strains; quantify the diversity of genetic implementations for each metabolic reaction at pangenome scale.



<p align="center">
  <img src="/documents/Lacto-panGPSRs (5).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 5.* PanGEM and PanGPR reconstruction, I) Reactome presence absence matrix - J) PanGPRs' genetic diversity




<p align="center">
  <img src="/documents/Lacto-panGPSRs (6).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 6.* PanGEM and PanGPR reconstruction, K) Genera-exclusive metabolic reactions



12. **Protein Stoichiometry (SWISS-MODEL)**  
   Obtain or estimate subunit stoichiometries and complex composition to refine GPRs and reaction assignments.

13. **3D Modeling**  
   Generate or retrieve structural models for selected proteins/complexes to enable structure-informed curation and downstream predictions.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (7).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 7.* PanGPSR reconstruction, L) Prptein sequence clusters of LR2T pangpr across the family M)  Prptein structure clusters of LR2T pangpr across the family



15. **Structural Analysis**  
    Analyze model quality and interfaces; link structural features to function, kinetics, or variant effects when relevant.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (9).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 8.* PanGPSR analysis, N) Structutal variation against sequence divergence by RMSD O)  Structutal variation against sequence divergence by Tm Align




<p align="center">
  <img src="/documents/Lacto-panGPSRs (10).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

*Figure 9.* PanGPSR analysis, P) Structural evolution across Family



17. **Neighborhood Analysis & Pangenome Graph**  
   Map gene neighborhoods and co-occurrence patterns; integrate with the pangenome graph to study genomic context and mobility.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (8).png" width="900" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

 *Figure 5.* Pan-neighborhood, Q) Genome neighborhood analysis at pangenome scale 
 
-------------------------------------------

  





# Implementation.


## Run the full pipeline.

This repository provides a sequential pipeline for ESKAPE taxa. The runner below executes your scripts **in order** and handles env activation for Bakta. It assumes the directory layout:


### Prerequisites.
### Python packages.
-pandas.
-numpy.
-scipy (for optimize, clustering).
-matplotlib.
-seaborn.
-biopython (Entrez, SeqIO, AlignIO).
-tqdm.
-requests.
-certifi.
-cobra (COBRApy).
-scikit-learn.

#### External tools (CLI).
-CD-HIT (pangenome clustering).
-Mash (distance / clustering).
-CarveMe (draft GEMs) — also needs a MILP solver; we install swiglpk via conda.
-MAFFT (for the MSA step; adjust if you use MUSCLE/Clustal instead).
-USalign and TMalign (structural alignment) — install manually and point the runner to the binaries.
-Bakta (annotation) — in its own conda env per your workflow.

- A SWISS-MODEL **access token** available as an environment variable:



#### Quick start (single taxon).
bash scripts/panGPSR_pipeline \
  --root /path/to/dir/ESKAPE \
  --taxon Enterococcus_faecium

#### Run all ESKAPE taxa.
bash scripts/panGPSR_pipeline --root /path/to/dir/ESKAPE --all







