# [Title: the clinical question and how you answered it]

**Biomedical Image Analysis · M.Sc. Applied Data Science and AI · SRH University Munich · Winter semester 2026/27**
**Author(s):** Mrudul Tarade · **Repository:** https://github.com/MrudulTarade/Disease-Prediction-using-Image-Analysis.git · **Date:** 17-11-2026

> How to use this template: copy it into your repository as `report.md` (or into LaTeX or Word with the same sections).
> Replace everything in [square brackets]. The section titles follow the eight grading criteria of Session 1 (weights in brackets).
> The remaining criterion, code understanding and technical defense (15 %), is graded in the exam conversation, not in the report.
> Same structure as the Deep Learning report, plus the biomedical parts: modality, labels, patient-level split, clinical meaning.
> Shared data or paper with Deep Learning? Allowed (decided 15.10.): different questions; data preparation is graded here only; name the shared work in both reports.

---

## Abstract

[Four or five sentences: the clinical question, the data, your classical baseline, your deep-learning model, the result with its spread, what it means and what it does not.]

## 1 · The biomedical problem (15 %, with section 2)

- **Clinical question:** Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as "urgent referrals"?
- **Task type:** The task includes classification of OCT scans, where an image/scan of a patient is sent to the neural network to classify it in 4 classes.
- **Why it is hard:** [small lesions, class imbalance, variation between scanners or sites, unclear borders …]

## 2 · The data (15 %, with section 1)

| | |
|---|---|
| Source, version, download date | Data Source: https://data.mendeley.com/datasets/rscbjbr9sj/2 ; Paper: https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0092867418301545%3Fshowall%3Dtrue#fig2 ; version 2 ; downloaded on 18-11-2026 ; DOI : 10.17632/rscbjbr9sj.2  |
| Licence | CC BY 4.0 ; The files associated with this dataset are licensed under a Creative Commons Attribution 4.0 International licence. You can share, copy and modify this dataset so long as you give appropriate credit, provide a link to the CC BY license, and indicate if changes were made, but you may not do so in a way that suggests the rights holder has endorsed you or your use of the dataset. Note that further permission may be required for any content within the dataset that is identified as belonging to a third party. |
| Modality | Optical Coherence Tomography (OCT) images of the retina |
| Size | 31971 images, used at 128 × 128 pixels |
| Labels: who made them | [one expert, several, a lab test, follow-up, an algorithm (Session 11)] |
| Labels: agreement | [inter-observer agreement if reported; otherwise "not reported"] |
| Classes or targets | [counts per class, or share of foreground pixels] |
| Splits | [training / validation / test; **by patient** if patient numbers exist (Session 7); otherwise say so] |
| Preprocessing | [resizing, resampling, intensity windows or normalisation (statistics from the training set only)] |
| Quality checks | [duplicates, broken files, wrong masks you found (look at 20 by eye)] |
| Shared with Deep Learning? | NO |

Refer to A1_examples.png in the results folder for example images.

## 3 · Experimental design (15 %)

- **The floor:** [the trivial answer: largest class, or "always background" (Dice 0)]
- **Classical baseline:** [threshold, features + random forest, … (Sessions 5–6)]
- **Deep-learning model:** [architecture, pretrained or not, 2D/2.5D/3D, loss (Dice + cross-entropy?), why]
- **Augmentation:** [which changes, and why each one is plausible for this modality (Session 8)]
- **Comparisons:** [one change at a time; same splits and budget; at least three seeds]

## 4 · Implementation and reproducibility (25 %)

- **Run it:** [commands or notebook order; environment, for example `requirements.txt`]
- **Seeds, hardware, training time:** […]
- **Where the results come from:** [which notebook or script makes which table and figure]

## 5 · Evaluation, validation and critical analysis (15 %)

| Setting | [metric] mean | ± spread | seeds |
|---|---|---|---|
| floor | | | |
| classical baseline | | | |
| deep-learning model | | | |
| + [change] | | | |

- **Metrics that fit the task:** [Dice and IoU for masks; sensitivity and specificity, AUC for classes; volumes in mL …]
- **Worst cases:** [the images where the model fails most, and why (Session 9)]
- **Ceiling:** [what a second annotator would score, if known (Session 11)]
- **Test set:** used **once**, for the final models only. External data, if any: [which].
- **Limitations:** [what the results do **not** show: other scanners, other hospitals, other populations]

## 6 · Explainability, ethics and clinical responsibility (5 %)

- [Saliency maps or other explanations (Session 14), and what they can and cannot show]
- [Who could be harmed by a wrong answer; what a doctor would still have to check; privacy of the data]

## 7 · Use of AI tools (5 %)

[Which tools you used, for what (code, text, debugging), and how you **checked** their output. Be specific.]

## 8 · Conclusion (documentation and communication, 5 %)

[What you found, how sure you are, what you would do next.]

## References

[All papers, data sets, code and websites you used.]
