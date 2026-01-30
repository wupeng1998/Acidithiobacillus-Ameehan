# Acidithiobacillus Ameehan AME_WP1377 Genome Annotation & Supplementary Data
[**English Version**](README.md) | [**中文版**](README_zh.md) 

本仓库存储**Acidithiobacillus Ameehan AME_WP1377**（嗜酸硫氧化细菌模式菌株）的全基因组注释数据、代谢模型评估报告及发表于*Frontiers in Microbiology*的研究论文补充材料，为该菌株的基因组功能解析、代谢机制研究及极端环境适应机制分析提供核心数据支撑。

**关联论文**：Wu, P., et al. (2023). Genome Annotation and Metabolic Analysis of Acidithiobacillus Ameehan AME_WP1377 Reveals Its Adaptive Mechanisms to Extreme Acidic Environments. *Frontiers in Microbiology*, 14, 1277847.
**DOI**：[10.3389/fmicb.2023.1277847](https://www.frontiersin.org/journals/microbiology/articles/10.3389/fmicb.2023.1277847/full)

---

## 一、仓库文件结构
本仓库按**菌株元数据**、**RASTtk注释结果**、**classicRAST注释结果+补充数据**分为3个核心目录，文件格式覆盖基因组序列、注释文件、代谢模型报告及论文补充材料，具体结构如下：

```
├── AME_WP1377/          # 菌株核心元数据与基础信息文件
├── RASTtk/              # 基于RASTtk的基因组注释全结果
└── classicRAST/         # 基于classicRAST的注释结果 + 论文补充数据
```

### 1.1 AME_WP1377/ 目录（菌株核心元数据）
存储Acidithiobacillus Ameehan AME_WP1377菌株的基础信息，为基因组分析与实验设计提供背景支撑：
| 文件名 | 格式 | 核心用途 |
|--------|------|----------|
| `AME_WP1377.xlsx` | Excel | 菌株核心信息表：含菌株编号、分类学地位（门/纲/目/科/属/种）、分离源、培养条件、基因组基本特征（GC含量、contig数、基因组大小等） |
| `AME_WP1377.xml` | XML | 结构化菌株元数据：兼容生物信息学数据库（如NCBI、ENA）的结构化存储格式，便于数据共享与二次整合 |
| `media.txt` | TXT | 菌株培养培养基配方：详细记录该菌株生长所需的酸性培养基成分、pH条件、培养温度等，支撑生理生化实验 |

### 1.2 RASTtk/ 目录（RASTtk基因组注释结果）
采用**RASTtk**（RAST工具新一代版本，支持精准功能注释与代谢途径分析）对AME_WP1377基因组完成注释，生成多格式注释文件，满足不同下游分析需求：
| 文件名 | 格式 | 核心用途 |
|--------|------|----------|
| `RASTtk.contigs.fa` | FASTA | 基因组拼接contig序列：注释流程的原始序列输入，为所有注释文件的序列基础 |
| `RASTtk.ec-stripped.embl` | EMBL | 去冗余EC编号的EMBL注释：含基因、CDS、tRNA/rRNA、功能注释等信息，去除重复EC编号便于分析 |
| `RASTtk.ec-stripped.gbk` | GenBank | 去冗余EC编号的GenBank注释：标准基因组注释格式，兼容NCBI、SnapGene等工具，可直接查看基因结构与功能 |
| `RASTtk.ec-stripped.gff` | GFF3 | 去冗余EC编号的GFF注释：基因特征通用格式，用于基因组可视化（IGV、GBrowse）与下游功能富集分析 |
| `RASTtk.ec-stripped.gtf` | GTF | 去冗余EC编号的GTF注释：基因转录本特征格式，适配转录组分析（如STAR、HISAT2）与可变剪接分析 |
| `RASTtk.embl` | EMBL | 完整EMBL注释：含全部EC编号的原始注释结果，保留完整注释信息用于深度分析 |
| `RASTtk.faa` | FASTA | 注释基因蛋白序列：所有编码基因的氨基酸序列，用于蛋白结构预测（SWISS-MODEL）、系统发育分析（IQ-TREE） |
| `RASTtk.fna` | FASTA | 注释基因核酸序列：所有编码基因的DNA序列，用于基因克隆、引物设计、同源序列比对 |
| `RASTtk.gbk` | GenBank | 完整GenBank注释：原始RASTtk注释结果，含完整功能注释、基因位置、产物信息等 |
| `RASTtk.gto` | GTO | RAST专用基因组对象格式：用于注释结果的二次编辑、功能修正与批量注释分析 |
| `RASTtk.tgz` | TGZ | 注释结果压缩包：完整RASTtk注释文件集合，便于批量下载与离线分析 |
| `RASTtk.txt` | TXT | 注释统计摘要：核心注释指标（基因总数、CDS数、tRNA/rRNA数、功能分类占比等） |
| `RASTtk.xls` | Excel | 注释统计表格：功能注释分类（如COG、KEGG、GO）的详细统计，便于图表绘制与数据整理 |

### 1.3 classicRAST/ 目录（classicRAST注释结果+论文补充数据）
采用**classicRAST**（传统RAST注释流程，用于注释结果交叉验证）完成基因组注释，同时存储论文全部补充材料，支撑研究结论验证：
#### 1.3.1 classicRAST注释核心文件
| 文件名 | 格式 | 核心用途 |
|--------|------|----------|
| `classicRAST.contigs.fa` | FASTA | 基因组contig序列：与RASTtk注释使用**同一序列**，保证两种注释流程的序列一致性 |
| `classicRAST.ec-stripped.embl/gbk/gff/gtf` | EMBL/GenBank/GFF3/GTF | 去冗余EC编号的classicRAST注释：格式同RASTtk，便于两种注释结果的对比分析 |
| `classicRAST.embl/gbk` | EMBL/GenBank | 完整classicRAST注释：原始传统RAST注释结果，用于与RASTtk注释的交叉验证 |
| `classicRAST.faa/fna` | FASTA | classicRAST注释的蛋白/核酸序列：用于两种注释流程的基因序列一致性比对 |
| `classicRAST.gto` | GTO | classicRAST专用基因组对象格式：用于传统注释结果的二次编辑与分析 |
| `classicRAST.merged.gbk` | GenBank | 合并后GenBank注释：整合所有contig的注释信息，便于全基因组范围的功能分析 |

#### 1.3.2 代谢模型与论文补充数据
| 文件名 | 格式 | 核心用途 |
|--------|------|----------|
| `MemoteReportApp.html` | HTML | 代谢模型质量评估报告：基于Memote工具构建AME_WP1377基因组尺度代谢模型（GEMs），可视化展示模型完整性、GPR关联、途径覆盖度等核心指标 |
| `S1.xlsx-S8.xlsx` | Excel | 论文补充表格1-8：对应文章Supplementary Tables 1-8，含注释统计、比较基因组学、代谢途径分析、极端环境适应基因筛选等核心数据 |
| `Supplementary Figure.docx` | Word | 论文补充图说明：含补充图的绘制方法、数据来源、图例解释、结果解读，对应文章Supplementary Figures |

---

## 二、数据来源与分析方法
### 2.1 基因组注释方法
1. **序列基础**：以Acidithiobacillus Ameehan AME_WP1377的全基因组拼接contig序列（`RASTtk.contigs.fa`/`classicRAST.contigs.fa`）为输入，采用Illumina高通量测序+PacBio三代测序拼接的高质量基因组序列。
2. **注释工具**：
   - **RASTtk**：新一代RAST注释工具，整合了最新的蛋白数据库（如UniProt、KEGG）与注释算法，实现更精准的基因功能注释、代谢途径预测与非编码RNA识别；
   - **classicRAST**：传统RAST注释流程，作为对照验证RASTtk注释结果的可靠性，确保注释的准确性与完整性。
3. **注释流程**：遵循RAST工具标准参数，完成基因预测、功能注释、EC编号分配、代谢途径映射等核心步骤，生成多格式注释文件。

### 2.2 代谢模型构建
基于RASTtk注释结果，采用**Memote**工具构建AME_WP1377的基因组尺度代谢模型（GEMs），通过`MemoteReportApp.html`完成模型质量评估，核心评估维度包括：
- 模型完整性：反应数、代谢物数、基因-蛋白-反应（GPR）关联覆盖率；
- 模型一致性：代谢物电荷平衡、反应热力学可行性；
- 功能覆盖度：核心代谢途径（如硫氧化、碳固定、能量代谢）的基因覆盖情况。

### 2.3 补充数据说明
`S1.xlsx-S8.xlsx`与`Supplementary Figure.docx`为论文核心补充材料，直接支撑正文研究结论，包括：
- 菌株基因组基本特征统计；
- RASTtk与classicRAST注释结果对比；
- 极端酸性环境适应相关基因（如质子泵、抗氧化基因、硫代谢基因）的筛选与功能注释；
- 与近缘Acidithiobacillus菌株的比较基因组学分析；
- 代谢模型核心途径的可视化与分析结果。

---

## 三、使用说明
### 3.1 基因组序列与注释文件使用
1. **序列分析**：`*.contigs.fa`（FASTA格式）可用于BLAST比对（NCBI BLAST、Local BLAST）、基因组可视化（IGV、Artemis）、系统发育分析（将16S rRNA序列提取后用MEGA/IQ-TREE构建进化树）。
2. **注释查看**：
   - GenBank/EMBL格式（`*.gbk`/`*.embl`）：可直接用SnapGene、Geneious、NCBI Genome Data Viewer打开，查看基因位置、结构、功能注释；
   - GFF3/GTF格式（`*.gff`/`*.gtf`）：导入IGV、GBrowse等可视化工具，实现基因组特征的交互式查看；
   - FAA/FNA格式（`*.faa`/`*.fna`）：用于蛋白结构预测（SWISS-MODEL）、功能富集分析（DAVID、ClusterProfiler）、同源基因克隆。
3. **注释对比**：将RASTtk与classicRAST的`*.gff`/`*.gbk`文件导入注释对比工具（如GFFCompare、GBKDiff），分析两种注释流程的基因差异与功能一致性。

### 3.2 代谢模型报告使用
`MemoteReportApp.html`可**直接在浏览器（Chrome/Firefox）打开**，无需额外安装软件，核心查看内容：
- 模型统计面板：快速获取模型的反应数、代谢物数、GPR关联数等核心指标；
- 途径覆盖面板：查看核心代谢途径（如硫代谢、能量代谢）的基因与反应覆盖情况；
- 质量评估面板：检查模型的电荷平衡、热力学可行性等问题，为模型优化提供依据。

### 3.3 补充数据使用
1. **补充表格**：`S1-S8.xlsx`用Excel/WPS直接打开，可提取统计数据用于图表绘制（如Origin、GraphPad Prism）、数据二次分析；
2. **补充图说明**：`Supplementary Figure.docx`结合论文正文，理解补充图的实验设计、数据来源与结果解读，支撑研究结论的验证。

---

## 四、引用信息
若使用本仓库数据开展研究，请引用以下论文：
> Wu, P. (2023). Genome Annotation and Metabolic Analysis of Acidithiobacillus Ameehan AME_WP1377 Reveals Its Adaptive Mechanisms to Extreme Acidic Environments. *Frontiers in Microbiology*, 14, 1277847. https://doi.org/10.3389/fmicb.2023.1277847

**BibTeX格式**：
```bibtex
@article{wu2023genome,
  title={Genome Annotation and Metabolic Analysis of Acidithiobacillus Ameehan AME_WP1377 Reveals Its Adaptive Mechanisms to Extreme Acidic Environments},
  author={Wu, Peng and [其他作者]},
  journal={Frontiers in Microbiology},
  volume={14},
  pages={1277847},
  year={2023},
  publisher={Frontiers Media SA},
  doi={10.3389/fmicb.2023.1277847},
  url={https://www.frontiersin.org/journals/microbiology/articles/10.3389/fmicb.2023.1277847/full}
}
```

---

## 五、联系方式
若对本仓库数据有疑问或需进一步合作，可通过以下方式联系：
- 邮箱：wupengflipped@163.com

---
