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
- **Why it is hard:** 
    - The dataset doesn't have a validation set.
    - 556 images are present in the training dataset which are identical to the test dataset. 
    - 444 patients are present in both training and testing data when verified using patient ID.

## 2 · The data (15 %, with section 1)

| | |
|---|---|
| Source, version, download date | Data Source: https://data.mendeley.com/datasets/rscbjbr9sj/2 ; Paper: https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0092867418301545%3Fshowall%3Dtrue#fig2 ; version 2 ; downloaded on 18-11-2026 ; DOI : 10.17632/rscbjbr9sj.2  |
| Licence | CC BY 4.0 ; The files associated with this dataset are licensed under a Creative Commons Attribution 4.0 International licence. You can share, copy and modify this dataset so long as you give appropriate credit, provide a link to the CC BY license, and indicate if changes were made, but you may not do so in a way that suggests the rights holder has endorsed you or your use of the dataset. Note that further permission may be required for any content within the dataset that is identified as belonging to a third party. |
| Modality | Optical Coherence Tomography (OCT) images of the retina |
| Size | 31971 images, used at 128 × 128 pixels |
| Labels: who made them | First labelled by recent diagnosis, then labelled in 4 tiers. |
| Labels: agreement | Labels that passed through tiers, with final TRUE LABEL from 2 retinal specialists |
| Classes or targets | `cnv 25.4% of training`, `dme 26.1% of training`, `drusen 22.2% of training`, `normal 26.3% of training` |
| Splits | training / validation(created) / testing ; randomized patient IDs exist |
| Preprocessing | Converting to RGB, Resizing to 128 x 128, Pixel normalization |
| Quality checks | Duplicates found and removed from training datasets, Patient IDs found identical between sets and classes |
| Shared with Deep Learning? | NO |

Refer to examples.png in the results folder for example images.

## 3 · Experimental design (15 %)

- **The floor:** [the trivial answer: largest class, or "always background" (Dice 0)]
- **Classical baseline:** [threshold, features + random forest, … (Sessions 5–6)]
- **Deep-learning model:** [architecture, pretrained or not, 2D/2.5D/3D, loss (Dice + cross-entropy?), why]
- **Augmentation:** [which changes, and why each one is plausible for this modality (Session 8)]
- **Comparisons:** [one change at a time; same splits and budget; at least three seeds]

## 4 · Implementation and reproducibility (25 %)

- **Run it:** Clone the repository and download the data from the data source mentioned in Section 2 of this report. Download is exactly 5.39GB, refer to data folder for further info.
`DiseaseReferral_new.ipynb` notebook runs data loading, model training and evaluating. Run the first cell, with `requirements.txt`, which installs the packages required for the whole experiment.
- **Seeds, hardware, training time:** 3 Seeds, NVIDIA 48GB GPU, around 20 - 30 minutes.
- **Where the results come from:** `DiseaseReferral_new.ipynb` creates the results folder, where certain cells save respective results generated.

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
ChatGPT:
- To modify the load folder function (classes), to exclude files (`.ipynb_checkpoints` / `__pycache__` ) as they do not contain any image. It was verified by checking the image count, which stayed the same before and after for the respective classes.
- To handle duplicates that existed in both the training and testing data, generated the code that removes the identical images only from the training data, that have a Euclidean distance of ~0.0001. It was verified by comparing the count of images present before and after removing duplicates.
- To perform checks on patient ID distribution between training, validation and testing datasets and also among the classes. It was verified by comparing it with the research paper numbers. 

## 8 · Conclusion (documentation and communication, 5 %)

[What you found, how sure you are, what you would do next.]

## References
Kermany D, Goldbaum M, Cai W ...
Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning
Cell, 172, 1122-1131.e9

Data Source: https://data.mendeley.com/datasets/rscbjbr9sj/2 

Initial Code Template provided by : Prof. Dr. Judith Cerit (github: @profdrjcerit )

chatgpt.com