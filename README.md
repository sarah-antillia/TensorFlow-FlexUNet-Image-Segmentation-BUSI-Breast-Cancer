<h2>TensorFlow-FlexUNet-Image-Segmentation-BUSI-Breast-Cancer (2026/03/12)</h2>
Sarah T.  Arai<br>
Software Laboratory antillia.com<br><br>
This is the second experiment of Image Segmentation for <b>BUSI-Breast-Cancer</b> based on our <a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet</a> 
(TensorFlow Flexible UNet Image Segmentation Model for Multiclass), 
and 
<a href="https://drive.google.com/file/d/1n3UziRhHAPThXBYqa5vkNRGZXPQjvceU/view?usp=sharing">
<b>Augmented-BUSI-Breast-Cancer-ImageMask-Dataset.zip</b></a> which was derived by us from <br><br>
<a href="https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset">
<b>Breast Ultrasound Images Dataset</b> </a> on the kaggle.com.
<br><br>
On the first experiment, please refer to <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Breast-Ultrasound-Images">
TensorFlow-FlexUNet-Image-Segmentation-Breast-Ultrasound-Images</a>
<br><br>
In this experiment, we updated some hyper-parameters in <a href="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/train_eval_infer.config">
train_eval_infer.config
</a> to improve segmentation performance of our FlexUNetModel from the first one.
<br><br>
<b>Data Augmentation Strategy</b><br>
To address the limited size of images and masks of the original <b>brain tissue segmentation dataset</b>, 
we used our offline augmentation tool <a href="./generator/ImageMaskDatasetGenerator.py">ImageMaskDatasetGenerator.py</a> 
 to generate the augmented dataset. Please see also <a href="https://github.com/sarah-antillia/Image-Deformation-Tool">Image-Deformation-Tool</a>. 
<br><br> 
<hr>
<b>Actual Image Segmentation for BUSI-Breast-Cancer Images</b><br>
As shown below, the inferred masks predicted by our segmentation model trained by the dataset appear similar to the ground truth masks.
<br><br>
<b>rgb_map = {benign:green, malignant:red}</b>
<br><br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10018.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10018.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10018.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10535.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10535.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10535.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10550.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10550.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10550.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1  Dataset Citation</h3>
The dataset used was taken from the following kaggle web site:<br> 
<a href="https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset">
<b>Breast Ultrasound Images Dataset </b>
</a>
<br><br>
<b>About Dataset</b><br>
Breast cancer is one of the most common causes of death among women worldwide. 
Early detection helps in reducing the number of early deaths. 
The data reviews the medical images of breast cancer using ultrasound scan. 
Breast Ultrasound Dataset is categorized into three classes: normal, benign, and malignant images. 
Breast ultrasound images can produce great results in classification, detection, 
and segmentation of breast cancer when combined with machine learning.
<br><br>
<b>Data</b><br>
The data collected at baseline include breast ultrasound images among women in ages between 25 and 75 years old. 
This data was collected in 2018. The number of patients is 600 female patients. 
The dataset consists of 780 images with an average image size of 500*500 pixels. 
The images are in PNG format. The ground truth images are presented with original images. 
The images are categorized into three classes, which are normal, benign, and malignant.
<br>
<br>
<b>Citation</b><br>
Al-Dhabyani W, Gomaa M, Khaled H, Fahmy A.<br> 
Dataset of breast ultrasound images. Data in Brief.<br> 
2020 Feb;28:104863. <br>
DOI: 10.1016/j.dib.2019.104863.<br>
<br>
<b>License</b><br>
<a href="https://creativecommons.org/publicdomain/zero/1.0/">CC0: Public Domain</a>
<br>
<h3>
2 BUSI-Breast-Cancer ImageMask Dataset
</h3>
 If you would like to train this BUSI-Breast-Cancer Segmentation model by yourself,
please down load our dataset 
 <a href="https://drive.google.com/file/d/1n3UziRhHAPThXBYqa5vkNRGZXPQjvceU/view?usp=sharing">
<b>Augmented-BUSI-Breast-Cancer-ImageMask-Dataset.zip</b></a>
 (CC0: Public Domain), expand the downloaded, and put it under <b>./dataset/</b> to be:
<pre>
./dataset
└─BUSI-Breast-Cancer
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
        ├─images
        └─masks
</pre>
<b>BUSI-Breast-Cancer Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/BUSI-Breast-Cancer_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images of train and valid datasets is large enough to use for a training set of our segmentation model.
<br><br>

<b>Train_images_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_masks_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<h3>
3 Train TensorflowFlexUNet Model
</h3>
 We trained BUSI-Breast-Cancer TensorflowFlexUNet Model by using the following
<a href="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer, and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
, which simply runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>
<b>Model parameters</b><br>
Defined a small <b>base_filters=16</b> and a large <b>base_kernels=(11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large num_layers (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
image_width    = 512
image_height   = 512
image_channels = 3
input_normalize = True
normalization  = False
num_classes    = 3
base_filters   = 16
base_kernels  = (11,11)
num_layers    = 8
dropout_rate   = 0.05
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_crossentropy" and "dice_coef_multiclass".<br>
<pre>
[model]
loss           = "categorical_crossentropy"
metrics        = ["dice_coef_multiclass"]
</pre>
<b >Learning rate reducer callback</b><br>
Enabled learing_rate_reducer callback, and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.5
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b></b><br>
<b>RGB color map</b><br>
rgb color map dict for BUSI-Breast-Cancer 1+2 classes.<br>
<pre>
[mask]
mask_file_format = ".png"
;BUSI-Breast-Cancer 1+2
rgb_map = {(0,0,0):0,(0,255,0):1,(255,0,0):2,}
</pre>
<b>Epoch change inference callbacks</b><br>
Enabled epoch_change_infer callback.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
epoch_changeinfer        = False
epoch_changeinfer_dir    = "./epoch_changeinfer"
num_infer_images         = 6
</pre>
By using this epoch_change_infer callback, on every epoch_change, the inference procedure can be called
 for 6 images in <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> <br> 
<b>Epoch_change_inference output at starting (1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middle-point (23,24,25)</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/epoch_change_infer_at_middlepoint.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (48,49,50)</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>
In this experiment, the training process was terminated at epoch 50.<br><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/train_console_output_at_epoch50.png" width="880" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/eval/train_metrics.png" width="520" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4 Evaluation
</h3>
Please move to a <b>./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer</b> folder, and run the following bat file to evaluate TensorflowFlexUNet model for BUSI-Breast-Cancer.<br>
<pre>
>./2.evaluate.bat
</pre>
This bat file simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetEvaluator.py  ./train_eval_infer.config
</pre>
Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/evaluate_console_output_at_epoch50.png" width="880" height="auto">
<br><br>Image-Segmentation-BUSI-Breast-Cancer
<a href="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_crossentropy) to this BUSI-Breast-Cancer/test was low, and dice_coef_multiclass high as shown below.
<br>
<pre>
categorical_crossentropy,0.0218
dice_coef_multiclass,0.9887
</pre>
<br>
These values are better than those of the first experiment <a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Breast-Ultrasound-Images">
TensorFlow-FlexUNet-Image-Segmentation-Breast-Ultrasound-Images</a>
<pre>
categorical_crossentropy,0.1161
dice_coef_multiclass,0.9463
</pre>
<br>
<h3>
5 Inference
</h3>
Please move to a <b>./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer</b> folder, and run the following bat file to infer segmentation regions for images by the Trained-TensorflowFlexUNet model for BUSI-Breast-Cancer.<br>
<pre>
>./3.infer.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/mini_test_masks.png" width="1024" height="auto"><br>
<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for  BUSI-Breast-Cancer Images</b><br>
As shown below, the inferred masks predicted by our segmentation model trained by the dataset appear similar to the ground truth masks.
<br><br>
<b>rgb_map = {benign:green, malignant:red}</b>
<br>
<br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10080.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10080.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10080.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10217.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10303.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10303.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10303.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10523.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10523.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10523.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10535.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10535.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10535.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/images/10598.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test/masks/10598.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/BUSI-Breast-Cancer/mini_test_output/10598.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>
References
</h3>
<b>1. Breast lesion detection using an anchor-free network from ultrasound images with segmentation-based enhancement</b><br>
Yu Wang & Yudong Yao<br>
<a href="https://www.nature.com/articles/s41598-022-18747-y">
https://www.nature.com/articles/s41598-022-18747-y
</a>
<br>
<br>
<b>2. Classification of Breast Cancer Ultrasound Images with Deep Learning-Based Models </b><br>
Fatih Uysa,and Mehmet Murat Köse<br>
<a href="https://www.mdpi.com/2673-4591/31/1/8/html">
https://www.mdpi.com/2673-4591/31/1/8/html
</a>
<br>
<br>
<b>3. A CNN Deep Learning Technique for Prediction of Breast Cancer using Ultrasound Image
</b><br>
Atisham Khan and Silky Pareyani<br>
<a href="https://www.jetir.org/papers/JETIR2303813.pdf">
https://www.jetir.org/papers/JETIR2303813.pdf
</a>
<br>
<br>
<b>4. TensorFlow-FlexUNet-Image-Segmentation-BUS-BRA</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-BUS-BRA">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-BUS-BRA
</a>
<br><br>

<b>5. TensorFlow-FlexUNet-Image-Segmentation-BUS-UC</b><br>
Toshiyuki Arai @antillia.com<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-BUS-UC">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-BUS-UC</a>
<br>
<br>
<b>6. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br>
<br>
