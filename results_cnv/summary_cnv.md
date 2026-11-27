Question: Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as 'urgent referrals'?
On 1000 test images, the frozen ResNet-18 (balanced) found 241 of 250 cnv images (96.4%; 95 % bootstrap interval 93.9% to 98.5%).
Accuracy 93.3% (interval 91.7% to 94.8%); floor 25.0%; random-forest baseline 58.9%.
Three training seeds: cnv found 95.3% ± 1.0%. Calibration error for cnv: 0.039.
Limits: one data set, test images from the same source (internal validation only); 697 near-twins between training and test; 4416 training / 633 test patients; 561 in both.
