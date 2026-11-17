# Decoding Placental Signaling in Early-Onset Preeclampsia

**A study of placental gene activity found hundreds of differences in early-onset preeclampsia, but identifying which cells drive them remains a challenge.**

By Aditi Chaudhari, Christine Yao, Jason Liu, and Ruchika Mudraganam | Team Brownian Huskey

![Headline figure showing the main finding in placental gene expression](../figures/headline.png)

*Figure 1. **Placental gene activity differs in early-onset preeclampsia.** In the primary comparison, 258 genes showed higher activity, and 90 showed lower activity in preeclampsia placentas, after adjustment for gestational age at delivery and fetal growth restriction.*

## Introduction

The placenta does more than deliver oxygen and nutrients during pregnancy. Its cells also produce and respond to molecular signals that help coordinate pregnancy development. In preeclampsia, a pregnancy complication involving high blood pressure and potential injury to maternal organs, this communication may be disrupted. Early-onset preeclampsia is particularly concerning because it develops before 34 weeks of pregnancy.

Scientists have already linked preeclampsia to changes in proteins involved in blood vessel function. But a major question remains: **are the differences seen in whole placentas caused by changes within particular cells, or by changes in the mixture of cells that make up the tissue?** Our team examined both possibilities, focusing on genes that may participate in signaling between placental cells.

## The Data and Our Methods

We analyzed [publicly available placental RNA-sequencing data (GSE203507)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE203507) from **15 early-onset preeclampsia placentas and 15 non-preeclampsia placentas**. RNA sequencing measures gene activity by counting RNA molecules, which cells produce when using genes. We compared the groups using a statistical model that accounted for gestational age at delivery and fetal growth restriction, a condition in which a fetus does not grow as expected. We also examined a separate [single-cell-derived dataset](https://doi.org/10.6084/m9.figshare.23264102.v1) covering **26 donors (17 with preeclampsia and nine controls)** across **14 placental cell classes**. Because these were different patient groups, and the second included both early- and late-onset disease, it could provide context but not direct confirmation.

## What We Found

### Hundreds of genes differed between the two groups

We identified **348 genes** with statistically supported differences in activity: **258 were higher** in preeclampsia placentas, and **90 were lower**. To qualify, a gene had to meet both a multiple-testing-adjusted statistical threshold (adjusted *p* below 0.05) and at least a twofold estimated difference between groups. The adjustment helps reduce false discoveries when thousands of genes are tested at once. A twofold change means that estimated activity is approximately doubled or halved, depending on direction.

![Volcano plot showing the strength and size of gene activity differences in preeclampsia.](../figures/volcano.png)

*Figure 2. **Hundreds of placental genes differ in early-onset preeclampsia.** A volcano plot shows estimated changes in gene activity (horizontal axis, log2 fold change) versus statistical evidence (vertical axis, negative log10 adjusted p-value). Genes to the right are higher in preeclampsia. Genes to the left are lower. Highlight the five focus genes in the final exported plot.*

### Signaling-related genes were unusually common among the differences

Of the 348 differentially expressed genes, **65 were annotated as ligands or receptors**, molecules involved in sending or receiving cellular signals. That was **18.7%** of the differentially expressed genes, compared with **7.7%** of the tested background. A statistical enrichment test suggested this concentration was unlikely to occur by chance alone (odds ratio **2.86**; Fisher's exact *p* = **1.3 × 10⁻¹¹**). This does **not** mean we observed cells communicating differently. It means genes associated with communication were overrepresented among the tissue-level differences.

![Chart comparing the proportion of ligand or receptor genes among differentially expressed genes and all tested genes.](../figures/fig_cell_proportions.png)

*Figure 3. **Signaling-related genes are enriched among the placental differences.** Ligand- or receptor-annotated genes accounted for 18.7% of differentially expressed genes versus 7.7% of the tested background. The chart should label both groups and show the percentages clearly.*

### Five genes stood out, but their cellular sources were harder to identify

We examined **FLT1, ENG, LEP, INHBA, and CADM3** more closely. The first four showed **higher** activity in preeclampsia placentas and retained the result across **all five** additional checks that changed the statistical assumptions or sample selection. **CADM3**, a gene associated with cell adhesion, showed **lower** activity and met the criteria in **four of five** checks. Its direction remained lower in the fifth. These checks make the overall tissue-level patterns more credible, although they cannot rule out every source of bias.

The next question was which placental cells might account for those differences. In the separate cell-resolved dataset, all five genes changed in the **same direction** within **syncytiotrophoblasts**, cells forming the outer layer of placental villi in contact with maternal blood. However, **none of the five reached statistical significance within any individual cell class**. Agreement in direction is a clue, not proof that a particular cell type is responsible.

![Comparison of the five selected genes in whole placentas and syncytiotrophoblast-derived pseudobulk samples.](../figures/fig_pseudobulk_heatmap.png)

*Figure 4. **Five candidate genes show matching directions, but cell-specific changes are not confirmed.** Plot the bulk-tissue and syncytiotrophoblast pseudobulk log2 fold changes for FLT1, ENG, LEP, INHBA, and CADM3. Positive values indicate higher activity in preeclampsia. Negative values indicate lower activity. State in the figure that the within-cell-class results were not statistically significant.*

### Could changes in cell mixtures explain the results?

A whole placenta contains many cell types. A gene can appear more active in a tissue sample either because individual cells produce more RNA or because the sample contains more cells that normally express that gene. We used an exploratory computational method called **deconvolution** to estimate the relative RNA contributions of different cell populations. The estimated syncytiotrophoblast contribution was higher in preeclampsia, but the main comparison was **not statistically significant**. These estimates reflect RNA contributions, **not direct cell counts**.

We also explored potential ligand–receptor pairings between cell populations. **No change involving the five selected genes was statistically supported.** One candidate pairing, CADM3–CADM1 between stromal and natural killer cell populations, had a lower exploratory score in preeclampsia. This finding was not statistically supported and should not be interpreted as a demonstrated communication defect.

## Unanswered Questions

Our results leave two explanations open. The selected genes may change activity **within** syncytiotrophoblasts, or the overall tissue differences may partly reflect **changes in the cell mixture**. Both could also contribute. Our single-cell comparisons were not strong enough to distinguish them. We also cannot infer that a ligand binds its receptor, that a signal was transmitted, or that gene changes caused preeclampsia from RNA measurements alone.

## Conclusions, Limitations and Next Steps

The clearest result is that **early-onset preeclampsia placentas show widespread differences in gene activity, with an unusually high representation of signaling-related genes**. FLT1, ENG, LEP, INHBA, and CADM3 are useful candidates for follow-up. We hypothesize that higher tissue-level expression of FLT1, ENG, LEP, and INHBA reflects changes within syncytiotrophoblasts, while lower CADM3 may indicate a separate adhesion-related change. These are **testable explanations**, not established mechanisms.

There are important limitations. The bulk study had only 30 placentas, and the groups differed in delivery timing. No control placenta was delivered before 29.9 weeks, limiting how well gestational age could be separated from disease status. **Sequencing batch information was not provided**. The [original study preprint](https://doi.org/10.1101/2023.03.08.23286998) reports that control samples were sequenced with only four early-onset preeclampsia samples (S16, S20, S21, and S22). Technical batch differences may overlap with group membership. This is a possible confounder, not proof of a batch effect. The cell-resolved data came from a different cohort and included later-onset disease. Finally, all samples were collected at delivery, so the analysis cannot show what happened at the start of the condition.

A stronger next study would compare early-onset preeclampsia with gestational-age-matched controls, distribute samples across sequencing batches, and measure the five genes within identified cell types. Imaging-based RNA measurements and protein experiments could then test whether the suspected changes actually occur in syncytiotrophoblasts and affect neighboring cells.



## Data and Code

* **Repository:** [Brownian Huskey GitHub repository](https://github.com/chaudhariaditi96/brownian-huskies_datathon.git)
* **Bulk placental RNA sequencing:** [GSE203507](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE203507)
* **Cell-resolved dataset:** [Admati and colleagues' placental dataset](https://doi.org/10.6084/m9.figshare.23264102.v1)
* **Placental gene browser:** [Zeisel Lab browser](https://storage.googleapis.com/www_zeisellab/PE_web/pe_web_test_v1.html)
* **Sequencing-batch information:** [Ackerman et al., 2023 preprint](https://doi.org/10.1101/2023.03.08.23286998)

## Acknowledgements

We thank the Harvard Undergraduate OpenBio Datathon organizers and the researchers who made these placental datasets publicly available.

