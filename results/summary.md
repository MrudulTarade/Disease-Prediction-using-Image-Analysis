Question: Can a neural network, pre-trained on ImageNet images, identify choroidal neovascularisation and diabetic macular edema to classify the patients as 'urgent referrals'?
On 1000 test images, the frozen ResNet-18 (balanced) found 239 of 250 cnv images (95.6%; 95 % bootstrap interval 92.8% to 98.0%).
Accuracy 93.9% (interval 92.4% to 95.4%); floor 25.0%; random-forest baseline 59.5%.
Three training seeds: cnv found 95.9% ± 0.2%. Calibration error for cnv: 0.036.
Limits: one data set, test images from the same source (internal validation only); 675 near-twins between training and test; 4487 training / 633 test patients; 557 in both.
