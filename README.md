# ELD

The implementation of CVPR 2020 (Oral) paper "[A Physics-based Noise Formation Model for Extreme Low-light Raw Denoising](https://openaccess.thecvf.com/content_CVPR_2020/papers/Wei_A_Physics-Based_Noise_Formation_Model_for_Extreme_Low-Light_Raw_Denoising_CVPR_2020_paper.pdf)"

***News*** (16/07/2020): Release the ELD dataset and our pretrained models at [GoogleDrive](https://drive.google.com/drive/folders/1CT2Ny9W9ArdSQaHNxC5hGwav9lZHoqJa?usp=sharing) and [Baidudisk](https://pan.baidu.com/s/11ksugpPH5uyDL-Z6S71Q5g ) (0lby)


## Highlights

* We present a highly accurate noise formation model based on the characteristics of CMOS photosensors, thereby enabling us to synthesize realistic samples that better match the physics of image formation process. 

<img src="imgs/pipeline.png" height="140px"/> 

* To study the generalizability of a neural network trained with existing schemes, we introduce a new Extreme Low-light Denoising (ELD) dataset that covers four representative modern camera devices for *evaluation* purposes only. The image capture setup and example images are shown as below:

<img src="imgs/capture_setup.jpg" height="140px"/> <img src="imgs/example_images.png" height="140px"/> 


* By training only with our synthetic data, we demonstrate a convolutional neural network can compete with or sometimes even outperform the network trained with paired real data under extreme low-light settings. The denoising results of networks trained with multiple schemes, i.e. 1) synthetic data generated by the poissonian-gaussian noise model, 2) paired read data of [SID dataset](https://github.com/cchen156/Learning-to-See-in-the-Dark) and 3) synthetic data generated by our proposed noise model, are displayed as follows:

<img src="imgs/results.png" height="140px"/> 


## Prerequisites
* Python >=3.5, PyTorch >= 1.0.1
* Requirements: opencv-python, tensorboardX
* Platforms: Ubuntu 16.04, cuda-8.0


## Quick Start
Due to the business license, we are unable to to provide the noise model as well as the calibration method. 
Instead, we release our collected ELD dataset and our pretrained models to facilitate future research.

To reproduce our results presented in the paper (Table 1 and 2), please run ```ELD_preprocess.py``` first to standardize the file names of the ELD dataset
and then take a look at ```scripts/test_SID.sh``` and ```scripts/test_ELD.sh``` 

More surprising results will be revealed in our journal version of this work in future.   

## ELD Dataset
The dataset capture protocol is shown as follow:

 <img src="imgs/dataset.png" height="250px"/> 

We choose three ISO settings (800, 1600, 3200) and four low light factors (x1, x10, x100, x200) to capture the dataset (x1/x10 is not used in our paper). Image ids 1, 6, 11, 16 represent the long-exposure reference images. Please refer to ```ELDEvalDataset``` class in ```data/sid_dataset.py``` for more details. 

## Citation

If you find our code helpful in your research or work please cite our paper.

```
 @inproceedings{wei2020physics,
   title={A Physics-based Noise Formation Model for Extreme Low-light Raw Denoising},
   author={Wei, Kaixuan and Fu, Ying and Yang, Jiaolong and Huang, Hua},
   booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
   year={2020},
 }
```

## Contact
If you find any problem, please feel free to contact me (kaixuan_wei at bit.edu.cn).
A brief self-introduction is required, if you would like to get an in-depth help from me. 
