# OCT Disease Classification for Referral Support

> **Project status:** Experimental image-classification study. This notebook is not a clinically validated referral system and must not be used to make patient-care decisions.

## 1. Project overview

This project investigates whether a neural network pretrained on ImageNet can classify Optical Coherence Tomography (OCT) images into four retinal-image categories:

- Choroidal neovascularisation (CNV)
- Diabetic macular oedema (DME)
- Drusen
- Normal

The research question currently configured in the notebook is:

> Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as “urgent referrals”?

## 2. Repository structure

```text
.
├── DiseaseReferral_cnv.ipynb
├── DiseaseReferral_dme.ipynb
├── requirements.txt
├── data/
│   └── OCT2017/
│       ├── train/
│       │   ├── CNV/
│       │   ├── DME/
│       │   ├── DRUSEN/
│       │   └── NORMAL/
│       ├── val/
│       └── test/
│
├── results_cnv/
│   ├── examples_cnv.png
│   ├── counts_cnv.csv
│   ├── twins_cnv.png
│   ├── numbers_cnv.md
│   ├── confusion_cnv.png
│   ├── gradcam_cnv.png
│   ├── sanity_cnv.png
│   ├── seeds_cnv.json
│   ├── bootstrap_cnv.png
│   ├── calibration_cnv.png
│   ├── worst_cnv.png
│   ├── data_table_cnv.md
│   └── summary_cnv.md
│
└── results_dme/
    ├── examples_dme.png
    ├── counts_dme.csv
    ├── twins_dme.png
    ├── numbers_dme.md
    ├── confusion_dme.png
    ├── gradcam_dme.png
    ├── sanity_dme.png
    ├── seeds_dme.json
    ├── bootstrap_dme.png
    ├── calibration_dme.png
    ├── worst_dme.png
    ├── data_table_dme.md
    └── summary_dme.md
```

The exact folder names and generated result files may vary depending on the dataset and notebook run.

## 3. Installation and execution

### Requirements

The notebook writes a `requirements.txt` containing the installed versions of NumPy, PyTorch, and torchvision, plus scikit-learn, Matplotlib, Pillow, and Requests.

Install dependencies:

```bash
pip install -r requirements.txt
```

### Run in Google Colab

1. Open `DiseaseReferral_{focus}.ipynb` in Google Colab.
2. Make the dataset available at the configured path (exact size 5.39GB), or update the `YOUR DATA` configuration cell.
3. Set `DATA`, `SIZE`, `FOLDER`, `FOCUS`, and `PATIENT_ID` as appropriate.
4. Select a runtime with a GPU (T4 recommended) if available.
5. Run all cells.
6. Review the generated files in `results_{focus}/`.

*focus = "cnv","dme"

The notebook prints an approximate runtime of three minutes on a Colab T4 GPU; actual runtime depends on the environment, data, and download time.


