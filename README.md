# panGPSR-reconstruction
Large-scale reconstruction of pan gene → protein → structure → reaction (panGPSR) for prokaryotes. A big data analysis

> Automated, end-to-end workflow for large-scale microbial genomics and metabolic modeling. The pipeline ingests genomes, performs rigorous QA/QC, annotates proteins, builds a non-redundant pangenome, reconstructs strain-resolved GEMs, derives panGPRs, analyzes genomic neighborhoods, and integrates structure-aware refinement.

---

## Table of Contents
- [Method Overview (Figure)](#method-overview-figure)
- [Methods Overview](#methods-overview)
  - [Pipeline Stages](#pipeline-stages)
  - [Pangenome Analysis (Panel)](#pangenome-analysis-panel)
  - [PanGEM and panGPR Reconstruction](#pangem-and-pangpr-reconstruction)
  - [Structural Modeling](#structural-modeling)
  - [PanGPSR Analysis](#pangpsr-analysis)
  - [Neighborhood Analysis](#neighborhood-analysis)
- [Implementation](#implementation)
  - [Dependencies](#dependencies)
  - [Quick Start](#quick-start)
  - [Run All ESKAPE Taxa](#run-all-eskape-taxa)
  - [Reproducibility (Capture Versions)](#reproducibility-capture-versions)
- [Citation](#citation)
- [License](#license)

---

## Method Overview (Figure)

<p align="center">
  <img src="/documents/Lacto-panGPSRs.jpg" width="450" alt="Automated pipeline: genomes → QA/QC → annotation (BAKTA) → pangenome (CD-HIT) → GEM reconstruction (CarveMe) → panGPRs → neighborhood analysis; with protein stoichiometry, 3D modeling, and structural analysis integration.">
</p>

<p align="center"><em>Figure 1. High-level workflow for automated pangenome and metabolic modeling.</em></p>

---

## Methods Overview

### Pipeline Stages

1. **Obtain Genomes**  
   Retrieve assemblies and metadata; standardize file formats and identifiers for downstream steps.

2. **QA/QC**  
   Assess contamination and taxonomic assignment; cluster genomes (Mash) and evaluate completeness and contiguity; exclude or flag low-quality genomes.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (1).png" width="450" alt="Genomes distribution across genera, species, and geography.">
</p>
<p align="center"><em>Figure 2. Genomes distribution: A) by genera; B) by species; C) by geography.</em></p>

3. **Annotation (BAKTA)**  
   Generate consistent, evidence-backed functional annotations at the protein level to support pangenome and metabolic reconstruction.

4. **Pangenome (CD-HIT)**  
   Cluster proteins to form non-redundant ortholog groups; build a pangenome graph that captures core, accessory, and rare gene families.

### Pangenome Analysis (Panel)

<table>
  <tr>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (2).png" width="100%" alt="Family-level and species-level analysis">
      <p align="center"><em>Figure 3. Pangenome analysis — D) family-level; E) species-level.</em></p>
    </td>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (3).png" width="100%" alt="Cross-genera and genus-level analysis">
      <p align="center"><em>Figure 4. Pangenome analysis — F) cross-genera; G) genus-level.</em></p>
    </td>
  </tr>
</table>

<p align="center">
  <img src="/documents/Lacto-panGPSRs (4).png" width="50%" alt="Extended pangenome analysis.">
  <br>
  <em>Figure 5. Extended pangenome analysis.</em>
</p>

5. **GEM Reconstruction (CarveMe)**  
   Construct draft, strain-resolved GEMs from annotated proteomes; harmonize model identifiers and media definitions for comparative analysis.

6. **panGPRs**  
   Derive gene–protein–reaction (GPR) rules across strains; quantify the diversity of genetic implementations for each metabolic reaction at pangenome scale.

### PanGEM and panGPR Reconstruction

<table>
  <tr>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (5).png" width="100%" alt="Reactome presence/absence and panGPRs' diversity">
      <p align="center"><em>Figure 6. PanGEM & panGPR — I) reactome presence–absence matrix; J) panGPRs’ genetic diversity.</em></p>
    </td>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (6).png" width="100%" alt="Genera-exclusive metabolic reactions">
      <p align="center"><em>Figure 7. PanGEM & panGPR — K) genera-exclusive metabolic reactions.</em></p>
    </td>
  </tr>
</table>

### Structural Modeling

7. **Protein Stoichiometry (SWISS-MODEL)**  
   Obtain or estimate subunit stoichiometries and complex composition to refine GPRs and reaction assignments.

8. **3D Modeling**  
   Generate or retrieve structural models for selected proteins/complexes to enable structure-informed curation and downstream predictions.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (7).png" width="450" alt="Protein sequence vs structure clusters across the family.">
</p>
<p align="center"><em>Figure 8. PanGPSR reconstruction — L) protein sequence clusters of LR2T panGPR across the family; M) protein structure clusters of LR2T panGPR across the family.</em></p>

### PanGPSR Analysis

<table>
  <tr>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (9).png" width="100%" alt="Structural variation vs sequence divergence">
      <p align="center"><em>Figure 9. PanGPSR analysis — N) structural variation vs. sequence divergence (RMSD); O) structural variation vs. sequence divergence (TM-align).</em></p>
    </td>
    <td width="50%">
      <img src="/documents/Lacto-panGPSRs (10).png" width="100%" alt="Structural evolution across family">
      <p align="center"><em>Figure 10. PanGPSR analysis — P) structural evolution across family.</em></p>
    </td>
  </tr>
</table>

### Neighborhood Analysis

9. **Neighborhood Analysis & Pangenome Graph**  
   Map gene neighborhoods and co-occurrence patterns; integrate with the pangenome graph to study genomic context and mobility.

<p align="center">
  <img src="/documents/Lacto-panGPSRs (8).png" width="459" alt="Genome neighborhood analysis at pangenome scale.">
</p>
<p align="center"><em>Figure 11. Pan-neighborhood — Q) genome neighborhood analysis at pangenome scale.</em></p>

---

## Implementation

### Dependencies
**Python packages**
- pandas · numpy · scipy · matplotlib · seaborn · biopython · tqdm · requests · certifi · cobra (COBRApy) · scikit-learn

**External tools (CLI)**
- CD-HIT (pangenome clustering)  
- Mash (distance / clustering)  
- CarveMe (draft GEMs; requires a MILP solver — we use `swiglpk`)  
- MAFFT (MSA; substitute MUSCLE/Clustal if preferred)  
- USalign & TMalign (structural alignment)  
- Bakta (annotation) — in its own conda env

> **SWISS-MODEL token:** export at runtime; never commit secrets.  
> `export SWISSMODEL_TOKEN="YOUR_TOKEN_HERE"`

We recommend keeping two conda envs: `pangem` (main pipeline) and `bakta_env` (annotation). Environment files can live under `envs/`.

### Quick Start
```bash
# Run a single taxon
bash scripts/panGPSR_pipeline \
  --root /path/to/ESKAPE \
  --taxon Enterococcus_faecium
