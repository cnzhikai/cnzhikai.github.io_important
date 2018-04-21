---
title: Installation of TensorFlow on Windows
audience: 
tags: [soft-coding,neural-network]
keywords: neural-network
summary: "This article mainly describes the TensorFlow installation procedure on Windows system, including installation of CUDA and CUDNN."
last_updated: Oct 10, 2017
sidebar: mydoc_sidebar
permalink: soft_coding_installation_of_tensorflow_on_windows.html
folder: project
---


## Step 1 Installation of CUDA ##

##### What is CUDA, and why do we use it?
　　CUDA is short for Compute Unified Device, and it is a production of NVIDIA corporation that aims to solve the complicated computing problems with GPU within a parallel computing architecture. Developers can process programming with C, C++ or FORTRAN under a standard, mature environment (CUDA environment) to control GPU to solve problems.

##### Installation Procedures
  
1. If your computer is equipped with a NVIDIA graphics card that is not too *old*, it is almost sure for running CUDA. To double check whether your GPU satisfies the CUDA running condition, visit this site [https://developer.nvidia.com/cuda-gpus](https://developer.nvidia.com/cuda-gpus "https://developer.nvidia.com/cuda-gpus").
2. Download CUDA Toolkit from NVIDIA official website (see:[https://developer.nvidia.com/cuda-toolkit](https://developer.nvidia.com/cuda-toolkit "https://developer.nvidia.com/cuda-toolkit")). A reference choice is as follows: 
3. Install the CUDA as instructions.

## Step 2 Installation of CUDNN ##

##### What is CUDNN?
　　CUDNN is a computing package provided by NVIDIA CUDA Toolkit to speed up the computation of convolutional neural network by converting common computation to GPU-friendly one.

##### Installation Procedures
 

1. You can visit the NVIDIA official website to freely download the latest edition of th cuDNN computing package after filling some basic information required, or you can directly search package through search engine and download it to local computer.
2. Install it as instructions.

## Step 3 Installation of Anaconda and TensorFlow package ##

##### Q: What is Anaconda, and why do we use it?

　　Anaconda is an integrated Python environment equipped with Python main programme, IDE, IPython and other third-party packages. And conda is used as a attached tool to manage packages as well as programming environments. You can directly run the conda command in command lines for conda have been defaultly added to system environment varibies during the Anaconda installation process.

##### Installation Procedures

1. Add *CDUA bin* and *NVIDIA Computing Toolkit* to system path.
2. Download the installation package of Anaconda from [https://www.continuum.io/downloads](https://www.continuum.io/downloads "https://www.continuum.io/downloads"). If the downloading process is too slow, you can also download the mirror file from domestic mirror ware, for example: [http://mirrors.ustc.edu.cn/](http://mirrors.ustc.edu.cn/ "http://mirrors.ustc.edu.cn/") .
3. After the Anaconda installation, open the Anaconda Navigator to add a new environment in local computer, note that to choose a python 3.5 version (because some new features are not supported in python 3.6 ).
4. Use the Anaconda to install TensorFlow package. Open Anaconda Prompt and type in *anaconda search -t conda tensorflow* command to check the tensorflow avaliable for current system. Then use command *anaconda show dhirschfeld/tensorflow+'version'* to download and install the package.

##### Well down! Enjoy the convenience from TensorFlow by open Jupyter Notebook.

----------
## References
- http://blog.csdn.net/goodshot/article/details/61926805
- http://blog.sina.com.cn/s/blog_14935c5880102wu86.html




