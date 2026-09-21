<div align="center">

<img src="./assets/header.svg" width="100%" alt="Santhosh Kumar R — Medical Bioinformatics, Structural and Genomic Data Science" />

<img src="./assets/typing.svg" width="700" alt="M.Sc. Medical Bioinformatics at Sri Ramachandra · mutation-aware drug prioritization for drug-resistant TB · structural ensembles, ensemble docking, robustness scoring" />

<br><br>

<img src="https://img.shields.io/badge/M.Sc.%20Medical%20Bioinformatics-CGPA%209.1%2F10-17A398?style=flat-square&labelColor=0B1D26" alt="M.Sc. Medical Bioinformatics, CGPA 9.1 out of 10" />
<img src="https://img.shields.io/badge/Sri%20Ramachandra-Chennai-17A398?style=flat-square&labelColor=0B1D26" alt="Sri Ramachandra, Chennai" />
<img src="https://img.shields.io/badge/Published-WJBPHS%202024-17A398?style=flat-square&labelColor=0B1D26" alt="Published in WJBPHS 2024" />

<br>

<a href="mailto:santhoshrkumar16@gmail.com"><img src="https://img.shields.io/badge/Email-17A398?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0B1D26" alt="Email" /></a>
<a href="https://www.linkedin.com/in/santhosh-kumar-5976ba406"><img src="https://img.shields.io/badge/LinkedIn-17A398?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0B1D26" alt="LinkedIn" /></a>
<a href="https://github.com/santhoshrkumar16"><img src="https://img.shields.io/badge/GitHub-17A398?style=for-the-badge&logo=github&logoColor=white&labelColor=0B1D26" alt="GitHub" /></a>

</div>

---

## About

I'm a Physician Assistant turned bioinformatician. I spent four years in clinical settings — cardiology, pulmonology, orthopedics, community medicine, and a year assisting in surgical procedures — before moving into computational biology.

That path shapes how I work: I'm comfortable with the clinical context a dataset came from, and I care about whether an analysis actually answers a biological question rather than just producing output.

Right now I'm in my M.Sc. in Medical Bioinformatics at Sri Ramachandra (CGPA 9.1/10), working on structural modeling, ensemble docking, and NGS and sequence analysis.

<br>

## Research Focus

**A mutation-aware, CPU-friendly framework for prioritizing cross-resistant RpoB inhibitor candidates in *Mycobacterium tuberculosis***
`M.Sc. dissertation · in progress`

Rifampicin resistance in *M. tuberculosis* is driven largely by mutations in *rpoB*, and those mutations don't all break drug binding the same way — some are steric, some electrostatic, some act through changes in protein dynamics. Most virtual screening ignores this and docks against a single wild-type structure.

This project asks a different question: **which compounds hold up across a clinically realistic panel of resistance backgrounds, not just against the wild type?** The whole workflow is designed to run on a laptop — CPU only, no long molecular dynamics, no GPU cluster.

<details open>
<summary><b>How it works</b></summary>

<br>

| Stage | What happens |
| :--- | :--- |
| **Mutation panel** | Tiered, versioned *rpoB* panel built from the WHO mutation catalogue and primary literature — high-confidence, less-frequent, disputed, and outside-RRDR variants, with alignment-verified Mtb↔*E. coli* numbering |
| **Structural models** | QC'd models of wild-type RpoB, each panel mutant, and selected compensatory *rpoA*/*rpoC* backgrounds — built via two independent protocols and diffed to confirm only the intended residue changed |
| **Flexibility ensembles** | Normal mode analysis (ANM) to capture mutation-induced changes in low-frequency collective motion near the rifampicin pocket, yielding a small conformational ensemble per model |
| **Two-track docking** | Calibrated ensemble docking of a chemically diverse library against the canonical rifampicin pocket (Track A) and a literature-supported alternative site (Track B), with redocking and active-vs-decoy calibration |
| **Interaction fingerprints** | Residue-level fingerprinting of every pose to measure retention of *a priori* key contacts across the ensemble |
| **Robustness score** | A decomposed, transparent score — rank, contact retention, pose consistency, site coverage, chemical quality — kept visible rather than collapsed into one docking number |
| **Stress testing** | Weight-sensitivity analysis, leave-one-mutation-out analysis, and chemical-diversity clustering to check whether rankings actually survive perturbation |

**Core hypotheses:** resistance mutations cluster into distinct mechanistic classes rather than one uniform mechanism; ensemble docking across mutant and compensatory backgrounds surfaces cross-variant robust compounds that single wild-type docking misses; and the top compounds by raw docking score are generally *not* the top compounds by robustness.

</details>

<details>
<summary><b>Toolchain — dual implementation</b></summary>

<br>

The methodology is implemented twice, so the workflow is reproducible whether or not the user can script.

**Scripted pipeline (CLI)** — reproducible, version-controlled, identical parameters across every model
`ProDy` · `Biopython` · `RDKit` · `Open Babel` · `MODELLER` · `AutoDock Vina` · `Meeko` · `ProLIF` · `PyMOL` · `pandas` · `NumPy` · `scikit-learn` · `conda` · `git`

**No-code equivalent (GUI/web)** — same ten phases at pilot scale
`UCSF ChimeraX` · `PyRx` · `SWISS-MODEL` · `MolProbity` · `PDB2PQR/PROPKA` · `iMODS` · `CABS-flex` · `CASTp` · `PrankWeb` · `Clustal Omega` · `PLIP` · `SwissADME` · `ProTox-3.0` · `DataWarrior`

</details>

> **Scope, stated plainly:** this is a computational prioritization and hypothesis-generation framework. It does not claim enzymatic inhibition, whole-cell activity, pharmacokinetics, or clinical efficacy. The dissertation includes an explicit staged roadmap separating what was computationally established from what would require experimental follow-up.

**Repository:** private during evaluation · the pipeline is intended for open release so others can point it at new mutation panels or compound libraries.

<br>

## Technical Skills

### Core toolkit

| Area | Level | Detail |
| :--- | :---: | :--- |
| **Python for bioinformatics** | ●●●●○ | Biopython, NumPy, Pandas — sequence parsing, annotation, pipeline scripting |
| **R & Bioconductor** | ●●●○○ | Genomic data analysis, statistical analysis of study data |
| **NGS data analysis** | ●●●○○ | Galaxy platform pipeline execution, read processing, gene annotation |
| **Sequence analysis** | ●●●●○ | BLAST, multiple sequence alignment, phylogenetics, algorithm implementation |
| **Transcriptomics & genomics** | ●●●○○ | Coursework-level differential expression and annotation workflows |
| **Linux / command line** | ●●●○○ | Bash, CLI genomic tooling (Johns Hopkins certified) |
| **SQL & DBMS** | ●●●○○ | Query writing, schema basics, web-backed data handling |
| **Structural visualization** | ●●●○○ | PyMOL, protein structure inspection and figure generation |
| **Clinical domain knowledge** | ●●●●● | 4 years hands-on: patient assessment, lab test interpretation, medical documentation |

<div align="center">

<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white" alt="R" />
<img src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black" alt="C" />
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="SQL" />
<img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white" alt="Bash" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux" />
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
<br>
<img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy" />
<img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas" />
<img src="https://img.shields.io/badge/Biopython-17A398?style=flat-square&labelColor=0B1D26" alt="Biopython" />
<img src="https://img.shields.io/badge/Bioconductor-17A398?style=flat-square&labelColor=0B1D26" alt="Bioconductor" />
<img src="https://img.shields.io/badge/Galaxy-17A398?style=flat-square&labelColor=0B1D26" alt="Galaxy platform" />
<img src="https://img.shields.io/badge/NCBI%20%2F%20BLAST-17A398?style=flat-square&labelColor=0B1D26" alt="NCBI and BLAST" />
<img src="https://img.shields.io/badge/PyMOL-17A398?style=flat-square&labelColor=0B1D26" alt="PyMOL" />
<br>
<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white" alt="HTML5" />
<img src="https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=css&logoColor=white" alt="CSS" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />

</div>

### Building up through the dissertation

Actively learning these on the RpoB project — not yet production experience.

<div align="center">

<img src="https://img.shields.io/badge/AutoDock%20Vina-0F6E64?style=flat-square&labelColor=0B1D26" alt="AutoDock Vina" />
<img src="https://img.shields.io/badge/ProDy%20%2F%20NMA-0F6E64?style=flat-square&labelColor=0B1D26" alt="ProDy and normal mode analysis" />
<img src="https://img.shields.io/badge/ProLIF-0F6E64?style=flat-square&labelColor=0B1D26" alt="ProLIF" />
<img src="https://img.shields.io/badge/RDKit-0F6E64?style=flat-square&labelColor=0B1D26" alt="RDKit" />
<img src="https://img.shields.io/badge/MODELLER-0F6E64?style=flat-square&labelColor=0B1D26" alt="MODELLER" />
<img src="https://img.shields.io/badge/ChimeraX-0F6E64?style=flat-square&labelColor=0B1D26" alt="UCSF ChimeraX" />
<img src="https://img.shields.io/badge/scikit--learn-0F6E64?style=flat-square&labelColor=0B1D26" alt="scikit-learn" />
<img src="https://img.shields.io/badge/Reproducible%20Pipelines-0F6E64?style=flat-square&labelColor=0B1D26" alt="Reproducible pipelines" />

</div>

<br>

## Publication

**A Cross-sectional Study Assessing Digital Addiction among Young Adults using the Digital Addiction Scale**
*World Journal of Biology Pharmacy and Health Sciences* (WJBPHS), Aug 2024 · Vol. 19, Issue 02

<details>
<summary><b>Study details</b></summary>

<br>

Cross-sectional epidemiological study on digital addiction prevalence among 500+ young adults, run as a B.Sc. academic research project with a team of 3 (Oct 2023 – Jul 2024).

| | |
| :--- | :--- |
| **My role** | Study lead — survey instrument design using the Digital Addiction Scale, sampling and data collection, statistical analysis in R, interpretation and write-up |
| **Motivation** | Rising concern over technology-driven mental health impacts, with limited regional data available |
| **Outcome** | Published in WJBPHS; findings adopted by the university psychology department for student wellness programming |
| **Presented to** | Cohort and faculty at Dr. M.G.R. Educational and Research Institute |

</details>

<br>

## Education

**M.Sc. Medical Bioinformatics** — Sri Ramachandra Institute of Higher Education and Research, Chennai
`Aug 2025 – Present` · CGPA **9.1/10** · Semester 2 completed

<sub>Coursework: Cell &amp; Molecular Biology · Biochemistry &amp; Immunology · Mathematics &amp; Statistics · Fundamentals of Programming · Biophysics &amp; Proteomics · Sequence Analysis &amp; Algorithms · Genomics &amp; Transcriptomics · Programming with Python · DBMS &amp; Web Technology</sub>

**B.Sc. Physician Assistant** — Dr. M.G.R. Educational and Research Institute, Chennai
`Dec 2020 – Sep 2024` · CGPA **9.0/10**

<br>

## Experience

**Hair Transplant Assistant** — Kolors Healthcare Pvt. Ltd., Chennai
`Oct 2024 – Jul 2025`

Assisted in hair transplant surgeries and post-operative care in a clinical OT setting, handling roughly 13 patients a month. Performed pre-procedure counselling, test dose and local anaesthesia administration, and PRP injections on a case-by-case basis. Maintained OT standards working alongside the Chief Cosmetologist.

<br>

**Physician Assistant** — Primary care / clinic practice

Supported daily clinic operations at roughly 12 patients a day: IV line setup, wound dressing, catheter flushing, IM injections, plus pharmacy assistance and medication counselling.

<br>

**Physician Assistant Intern** — ACS Medical College and Hospitals, Chennai
`Oct 2023 – Sep 2024`

Rotated across Cardiology, Pulmonology, Orthopedics, and Community Medicine with doctors, nurses, and senior physician assistants. Hands-on patient assessment, clinical documentation, lab test interpretation, and multidisciplinary team coordination. Ran the digital addiction research project concurrently.

<br>

## Certifications

| Certification | Issuer | Issued | Credential ID |
| :--- | :--- | :--- | :--- |
| Command Line Tools for Genomic Data Science | Johns Hopkins University (Coursera) | Aug 2026 | `3AGT6D263TFJ` |
| Bioconductor for Genomic Data Science | Johns Hopkins University (Coursera) | Aug 2026 | `P6AXNMJBCWDS` |
| Python for Genomic Data Science | Johns Hopkins University (Coursera) | Aug 2026 | `X5BI7XP0MWC4` |
| Introduction to Genomic Technologies | Johns Hopkins University (Coursera) | Aug 2026 | `WU0EJFDB3C27` |
| Python for Data Science, AI &amp; Development | IBM (Coursera) | Aug 2026 | `BEEMGZNE19E9` |
| AI Tools Workshop | Be10x | May 2026 | `0270772f-3809-4400-b29b-1e1c61cd0997` |

<br>

## Current Focus

```yaml
building:
  - RpoB inhibitor prioritization framework (M.Sc. dissertation)
  - Tiered rpoB mutation panel from the WHO catalogue
  - CPU-only structural ensemble + two-track docking pipeline
  - Decomposed robustness score, stress-tested for rank stability

learning:
  - Mutant modeling and model QC (MODELLER, ChimeraX, MolProbity)
  - Normal mode analysis for CPU-friendly flexibility ensembles
  - Ensemble docking and calibration (AutoDock Vina, Meeko)
  - Interaction fingerprinting (ProLIF, PLIP) and cheminformatics (RDKit)
  - Reproducible pipeline practice: versioned manifests, run logs, checksums

exploring:
  - Antimicrobial resistance mechanisms and resistance-barrier prediction
  - Structure-based drug design beyond single-structure docking
  - Machine learning for biological and chemical data

open_to:
  - Bioinformatics Analyst
  - Computational Biologist
  - Computer-Aided Drug Design / Structural Bioinformatics roles
```

<br>

## GitHub

<div align="center">

<a href="https://github.com/santhoshrkumar16"><img src="https://komarev.com/ghpvc/?username=santhoshrkumar16&color=17A398&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile views" /></a>
<a href="https://github.com/santhoshrkumar16?tab=followers"><img src="https://img.shields.io/github/followers/santhoshrkumar16?style=for-the-badge&color=17A398&labelColor=0B1D26&label=FOLLOWERS" alt="GitHub followers" /></a>
<a href="https://github.com/santhoshrkumar16?tab=repositories"><img src="https://img.shields.io/badge/REPOSITORIES-View-17A398?style=for-the-badge&labelColor=0B1D26" alt="View repositories" /></a>

</div>

<br>

Most of my current work lives in the dissertation repository, which stays private until evaluation. Once the RpoB pipeline is released, it'll be the main thing here — a reproducible, CPU-only workflow others can point at new mutation panels or compound libraries.

<br>

<div align="center">

### Let's connect

<a href="mailto:santhoshrkumar16@gmail.com"><img src="https://img.shields.io/badge/Email-17A398?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0B1D26" alt="Email" /></a>
<a href="https://www.linkedin.com/in/santhosh-kumar-5976ba406"><img src="https://img.shields.io/badge/LinkedIn-17A398?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0B1D26" alt="LinkedIn" /></a>

<br><br>

<i>"Resistance is a moving target — so the model should be too."</i>

<img src="./assets/footer.svg" width="100%" alt="Thanks for visiting" />

</div>
