# Investigating Differential Gene Expression, Cell-Type-Specific Signaling and Potential Intercellular Communication in Early-Onset Preeclampsia

OpenBio 2026 Datathon, Track 1: Maternal-Fetal Cell Communication in Preeclampsia

## Team
- Aditi Chaudhari
- Christine Yao
- Jason Liu
- Ruchika Mudraganam

## Research Question
**Starter Question 8:** What might gene activity reveal about communication between placental cells in preeclampsia?

- Which genes encoding signaling ligands or receptors differ between PE and control placentas?
- In which placental cell types do these differences occur?
- Exploratory: which ligand–receptor pairs between cell types change in PE?

## Data Used
- GSE203507 bulk RNA-seq (required)
- Zeisel/Admati gene browser, for at least three genes (required): FLT1, ENG, LEP, INHBA and CADM3
- Admati/Skarbianskis single-cell pseudobulk files (optional)
- LIANA consensus ligand–receptor resource (LIANA 1.10.0)

## How to Run
1. Clone the datathon repository; the data package is in `track-01/data`. On Colab, the first notebook cell clones it automatically.
2. Install packages by following Track 1 Setup, plus LIANA (installed in Section 7.2a of the notebook).
3. Place the notebook in `track-01/notebooks/` and run `Brownian_Huskey.ipynb` from top to bottom.

**Reproducibility details**
- Notebook: `Brownian_Huskey.ipynb`
- Where we ran it: our own computer (macOS, Python 3.11.15, conda environment); the notebook also runs on Google Colab
- Package versions: PyDESeq2 0.5.4, LIANA 1.10.0
- Random seeds: seed 0 for jitter in the per-placenta figure (Section 10.5c)

## Files
| Path | Contents |
|---|---|
| `notebooks/` | The analysis notebook |
| `figures/` | Figures (PNG): volcano plot, pseudobulk heatmap, cell proportions, gene browser screenshots and `headline.png` |
| `results/` | Main result tables (CSV) produced by the notebook |
| `docs/analysis-plan.md` | The comparison, model and thresholds we chose |
| `docs/hypothesis-card.md` | Our hypothesis and how to test it |
| `docs/article.md` | Science communication article, following the HUDP article guide |

## Key Findings
- **Differential expression:** after adjusting for gestational age and FGR, 348 genes pass padj < 0.05 and |log2 fold change| ≥ 1 (258 higher in PE, 90 lower). ENG is the most significant (padj 2.1 × 10⁻¹⁶). Directions are unchanged in five sensitivity analyses.
- **Signaling genes:** 65 of the 348 genes encode ligands or receptors, more than expected (18.7% vs 7.7%; odds ratio 2.86). All 11 that pass every robustness check, including ENG, FLT1, LEP and INHBA, are higher in PE.
- **Cell types:** in single-cell pseudobulk data, these genes change in the same direction as in bulk in syncytiotrophoblast, but none is significant within any cell class. Deconvolution estimates a lower Hofbauer cell proportion in PE; the data cannot separate a change in cell behavior from a change in cell mix.
- **Ligand–receptor pairs:** no pair has both partners significantly changed, so no specific cell-to-cell interaction is supported.
- **Hypothesis:** in early-onset PE, syncytiotrophoblast expresses more ENG, FLT1, LEP and INHBA per cell than in gestational-age-matched controls.

## Limitations
- Small sample size (30 placentas) and early-onset PE only.
- No control was delivered before 29.9 weeks, so for the earliest PE samples the gestational-age adjustment relies on the model.
- Fetal sex is unbalanced between groups in the bulk data, and batch information is not available.
- In the single-cell data, FGR occurs only in PE donors and magnesium sulfate mostly in PE donors, so neither could be adjusted for; the cohort also includes late-onset PE.
- All cell-level evidence (pseudobulk, gene browser, deconvolution reference) comes from one single-cell dataset, and within-cell-type comparisons have limited power.
- RNA levels do not show protein levels or signaling activity.

## Presentation
Video link: https://youtu.be/4_kQrlhvYTM?is=xe4HESwivoMBIkH8
