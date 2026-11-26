Question: Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as 'urgent referrals'?
On 1000 test images, the frozen ResNet-18 (balanced) found 241 of 250 cnv images (96.4%; 95 % bootstrap interval 93.9% to 98.5%).
Accuracy 93.8% (interval 92.3% to 95.2%); floor 25.0%; random-forest baseline 87.1%.
Three training seeds: cnv found 96.3% ± 0.2%. Calibration error for cnv: 0.030.
Limits: one data set, test images from the same source (internal validation only); 556 near-twins between training and test; 2495 training / 633 test patients; 444 in both.
