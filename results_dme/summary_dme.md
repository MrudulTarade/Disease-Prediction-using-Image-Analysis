Question: Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as 'urgent referrals'?
On 1000 test images, the frozen ResNet-18 (balanced) found 231 of 250 dme images (92.4%; 95 % bootstrap interval 88.8% to 95.5%).
Accuracy 93.3% (interval 91.7% to 94.8%); floor 25.0%; random-forest baseline 58.9%.
Three training seeds: dme found 93.5% ± 0.9%. Calibration error for dme: 0.014.
Limits: one data set, test images from the same source (internal validation only); 697 near-twins between training and test; 4416 training / 633 test patients; 561 in both.
