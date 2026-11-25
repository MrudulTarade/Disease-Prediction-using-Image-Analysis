Question: Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as 'urgent referrals'?
On 1000 test images, the frozen ResNet-18 (balanced) found 240 of 250 cnv images (96.0%; 95 % bootstrap interval 93.5% to 98.1%).
Accuracy 93.1% (interval 91.4% to 94.6%); floor 25.0%; random-forest baseline 76.4%.
Three training seeds: cnv found 93.9% ± 2.0%. Calibration error for cnv: 0.028.
Limits: one data set, test images from the same source (internal validation only); 363 near-twins between training and test; patient not known from the files: cannot check (say so in the report).
