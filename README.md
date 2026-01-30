Here is the English version of the README. You can place this content in a file named `README_EN.md` or append it to your current document.

To enable **one-click switching**, add these buttons to the very top of both your Chinese and English README files:

```markdown
[**English Version**](README.md) | [**中文版**](README_zh.md) 

```

---

# Acidithiobacillus Ameehan AME_WP1377 Genome Annotation & Supplementary Data

This repository contains the complete genome annotation data, metabolic model evaluation reports, and supplementary materials for the research paper published in *Frontiers in Microbiology* regarding **Acidithiobacillus Ameehan AME_WP1377** (a model strain of acidophilic sulfur-oxidizing bacteria). These datasets support functional genomic analysis, metabolic mechanism studies, and environmental adaptation research for this strain.

**Associated Publication**: Wu, P., et al. (2023). Genome Annotation and Metabolic Analysis of Acidithiobacillus Ameehan AME_WP1377 Reveals Its Adaptive Mechanisms to Extreme Acidic Environments. *Frontiers in Microbiology*, 14, 1277847.

**DOI**: [10.3389/fmicb.2023.1277847](https://www.frontiersin.org/journals/microbiology/articles/10.3389/fmicb.2023.1277847/full)

---

## 1. Repository Structure

The repository is organized into three core directories: **Strain Metadata**, **RASTtk Annotation**, and **classicRAST Annotation + Supplementary Data**.

```
├── AME_WP1377/          # Core strain metadata and basic info
├── RASTtk/              # Full genome annotation results based on RASTtk
└── classicRAST/         # Annotation results based on classicRAST + Paper supplements

```

### 1.1 AME_WP1377/ (Strain Metadata)

Contains fundamental information about the strain to support experimental design and genomic context:
| File | Format | Key Usage |
| :--- | :--- | :--- |
| `AME_WP1377.xlsx` | Excel | Core info: taxonomy, isolation source, culture conditions, and genome traits (GC content, contigs, etc.). |
| `AME_WP1377.xml` | XML | Structured metadata compatible with bioinformatics databases (NCBI, ENA). |
| `media.txt` | TXT | Medium recipe: pH conditions, temperature, and chemical composition for growth. |

### 1.2 RASTtk/ (RASTtk Annotation Results)

Comprehensive annotation using **RASTtk** (the next-generation RAST toolset) for precise functional and metabolic pathway analysis:
| File | Format | Key Usage |
| :--- | :--- | :--- |
| `RASTtk.contigs.fa` | FASTA | Raw genomic contig sequences used as the basis for annotation. |
| `RASTtk.ec-stripped.*` | GBK/GFF/GTF | De-duplicated EC number annotations; standard formats for IGV, SnapGene, or RNA-seq pipelines. |
| `RASTtk.faa` / `.fna` | FASTA | Predicted amino acid (protein) and nucleotide (DNA) sequences of all genes. |
| `RASTtk.gto` | GTO | RAST Genome Object for secondary editing or batch analysis. |
| `RASTtk.xls` | Excel | Statistical summary of functional classifications (COG, KEGG, GO). |

### 1.3 classicRAST/ (classicRAST Results & Supplementary Data)

Traditional RAST results for cross-validation and all supplementary materials for the paper:

* **Core Annotation**: Includes `.gbk`, `.gff`, and `.faa` files identical in format to the RASTtk directory for comparative analysis.
* **Supplementary Materials**:
* `MemoteReportApp.html`: Quality assessment report for the Genome-scale Metabolic Model (GEM).
* `S1.xlsx - S8.xlsx`: Supplementary Tables 1–8 (comparative genomics, adaptive gene screening, etc.).
* `Supplementary Figure.docx`: Captions and descriptions for all supplementary figures.



---

## 2. Methods and Data Sources

### 2.1 Annotation Pipeline

* **Input**: High-quality contigs assembled from Illumina (high-throughput) and PacBio (long-read) sequencing.
* **Tools**: Both **RASTtk** (integrated with latest UniProt/KEGG databases) and **classicRAST** (for validation) were utilized.

### 2.2 Metabolic Modeling

The **Memote** tool was used to evaluate the Genome-scale Metabolic Model (GEM). Key metrics in the `MemoteReportApp.html` include:

* **Model Consistency**: Charge balance and thermodynamic feasibility.
* **GPR Associations**: Coverage of Gene-Protein-Reaction relationships.
* **Pathways**: Analysis of sulfur oxidation, carbon fixation, and energy metabolism.

---

## 3. Usage Guide

1. **Sequence Analysis**: Use `.faa` and `.fna` files for BLAST searches, phylogenetic tree construction (e.g., MEGA/IQ-TREE), or protein structure prediction.
2. **Visualization**: Import `.gbk` or `.gff` files into **SnapGene**, **IGV**, or **Artemis** to browse gene locations and functions interactively.
3. **Metabolic Insights**: Open `MemoteReportApp.html` in any modern web browser (Chrome/Firefox) to explore the metabolic network's completeness.

---

## 4. Citation

If you use the data in this repository, please cite:

> Wu, P. (2023). Genome Annotation and Metabolic Analysis of Acidithiobacillus Ameehan AME_WP1377 Reveals Its Adaptive Mechanisms to Extreme Acidic Environments. *Frontiers in Microbiology*, 14, 1277847. [https://doi.org/10.3389/fmicb.2023.1277847](https://doi.org/10.3389/fmicb.2023.1277847)

---

## 5. Contact

For questions or collaborations:

* **Email**: wupengflipped@163.com

---
