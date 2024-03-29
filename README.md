![image](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/91909939/f3a72c5b-86f6-46b8-a78c-7e3353a6c4f8)
    ![made-with-jupyter-notebook](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/91909939/006282ec-3abd-4c9f-905a-b96c70e10bfb)
          ![migrated-to-oneapi](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/91909939/8de93f8a-389c-4a25-a66f-e6acb6073b54)
<img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/Altaf-01/Sexual-Harassment-Detection-In-Workplace"> <img alt="GitHub watchers" src="https://img.shields.io/github/watchers/Altaf-01/Sexual-Harassment-Detection-In-Workplace?style=social">
<hr/>


# Inspiration  <img src="https://user-images.githubusercontent.com/130077430/230579469-c1263cef-784e-4845-93fb-2f73544e49e1.png" width="90" height="80"> 
Throughout our lives, we've been exposed to countless reports and stories in newspapers and online platforms, underscoring the distressing prevalence of sexual harassment incidents. What strikes me even more profoundly is the significant reluctance victims often experience when reporting such incidents due to fears of retaliation or social stigma. This reporting hesitancy and the lack of practical technological solutions have intensified my resolve to address this critical issue. The absence of practical tools and measures to combat such behaviour compelled me to develop the "Sexual Harassment Detection at Workplace" project. The driving force behind this endeavour is not only to close the gap between the gravity of the problem and the available solutions but also to contribute to a safer and more inclusive work environment by harnessing the potential of innovative technological advancements.


<hr/>

# Problem Statement <img src="https://user-images.githubusercontent.com/130077430/230730194-a7389fed-f5fd-48d3-856a-0212057f2500.png" width="90" height="80">

Our main goal is to build an innovative technological solution that could detect sexual harassment in real-time, which is much needed to fill in the gap left void by traditional methods,  by which I aim to create a safer work environment, overcome reporting hesitancy, support HR and legal management, reduce psychological and physical stress and do early detection and prevention.

<hr/>

# Introduction <img src="https://user-images.githubusercontent.com/72274851/152814876-73362bcc-bde6-411f-ba80-235e911f276f.gif" width="90" height="90">

Recognizing and tackling harassment instances can be complex due to victim hesitation prompted by fear or stigma. We aim to develop a CNN-based model to detect workplace harassment, differentiating it accurately from normal behavior's in videos. Our solution leverages a CNN-based model to effectively detect harassment in videos, contributing to a safer workplace and fostering a culture of inclusivity.
 

<hr/>

# Approach <img src="https://cdn0.iconfinder.com/data/icons/data-science-2-1/66/119-512.png" width="90" height="80"> 

Our model uses a CNN(Convolutional Neural Network) for detection since the dataset uses images using a Deep Learning model to make better detection. A dataset containing images will be used, out of which half will have harassment images, and the other half will show a normal work environment. We will follow an 80:20 split, where 80% of the images will be used for training our model, and the remaining 20% will be reserved for testing the model. To further enhance the accuracy of the detection system, we have 
implemented Transfer Learning techniques by leveraging pre-trained models such as VGG16, Xception, and others. These models have been trained on large-scale datasets and come with high accuracy levels.

![image](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/116085472/4869db22-eb39-401e-8d1e-38458b2b1d3f)

<hr/>

# Procedure <img src="https://th.bing.com/th/id/R.02832177b40b49d50674126476f980c3?rik=aXibwvpQe645bg&riu=http%3a%2f%2fwww.clipartbest.com%2fcliparts%2fjcx%2f6rb%2fjcx6rbngi.png&ehk=xllVkMLnEE%2fEXx%2fnWbpceiVVfvTNGJmODcZ9fEBJVGA%3d&risl=&pid=ImgRaw&r=0" width="120" height="100"> 

## 1️⃣ Pre-install all the required libraries
       1) OpenCV
       2) Keras
       3) Numpy
       4) Pandas
       5) OS
## 2️⃣ Understand the dataset
       As no solution was available to this problem before, this project had no existing dataset online.
       So, we had to create the dataset ourselves, which was a tedious process.
       it has 2 folder which are :
       1) yes - having 1000 pictures(Harassment)
       2) no - having 1000 pictures(Healthy work environment)
 
## 3️⃣ Data preprocessing
1. preprocess the images from the yes and no folder.

2. Resizing all the images to the same dimension (224,224,3)
  
3. Convert the images into numpy arrays.
   
4. The dataset will be split into training, validation, and testing sets.

## 4️⃣ Build and train the VGG16 model
The VGG16 model is designed and trained to classify images as either Harassment or Healthy.


## 5️⃣ Training the model using Intel OneAPI to get better results

<img src="https://user-images.githubusercontent.com/72274851/218504609-585bcebe-5101-4477-bdd2-3a1ba13a64a8.png" width="190" height="100"><img src="https://aditech.in/wp-content/uploads/2020/07/image_2020_07_17T06_08_48_297Z.png" width="800" height="100">

**How does OneApi provide better performance :**
    
Today’s computer systems are heterogeneous and include CPUs, GPUs, FPGAs, and other accelerators. The different architectures exhibit varied                   characteristics that can be matched to specific workloads for the best performance.
Having multiple types of compute architectures leads to different programming and optimization needs. oneAPI and SYCL provide a programming model, whether through direct programming or libraries, that can be utilized to develop software tailored to each of the architectures.
    
**Advantages of using OneAPI :**

1) We can use Single code for both CPU and GPU (heterogeneous computing)
2) To implement machine learning based IoT projects easily with less hardwares as the machine learning part happens in cloud
3) To process files faster ie. it takes less time to run the epochs
4) OneAPI allows users to transcend Hardware restrictions and provide better performance for low powered computers
5) Accuracy will improve while using OneAPI

**We used the following Intel® oneAPI libraries and frameworks to increase our performance and efficiency :**

* <b>Intel® oneAPI Data Analytics Library (oneDAL)</b>

we used Intel® Extension for Scikit-learn*, a key component of oneDAL to enhance our existing scikit code by patching it.

Installation:
<code>pip install scikit-learn-intelex</code> 

Usage:<br>
<code>from sklearnex import patch_sklearn
patch_sklearn()</code>

By using this library we were able to see a 2x difference in the perfomance

* <b>Intel® oneAPI Deep Neural Network Library (oneDNN)</b>

To optimize deep learning applications on Intel® CPUs and GPUs, We integrated the oneAPI Deep Neural Network Library (oneDNN). To enable oneDNN optimizations for TensorFlow* running on Intel® hardware, We used the following code:

<code>os.environ['TF_ENABLE_ONEDNN_OPTS'] = '1'
os.environ['DNNL_ENGINE_LIMIT_CPU_CAPABILITIES'] = '0'</code> 

* <b>Intel® oneAPI DPC++ Library (oneDPL)</b>

The Intel® oneAPI DPC++ Library (oneDPL) aims to simplify SYCL* programming efforts across devices for high-performance parallel applications. We harnessed the power of oneDPL using specific environment variables to optimize performance and memory utilization.

<code>os.environ['ONEAPI_DEVICE_SELECTOR'] = 'opencl:*'
os.environ['SYCL_ENABLE_DEFAULT_CONTEXTS'] = '1'
os.environ['SYCL_ENABLE_FUSION_CACHING'] = '1'</code>

* <b>Intel® oneAPI AI Analytics Toolkit (AI Kit)</b>

The Intel® oneAPI AI Analytics Toolkit (AI Kit) offers an integrated solution for preprocessing, machine learning, and model development. To optimize deep learning training on Intel® XPUs and streamline inference, We utilized the toolkit's Intel®-optimized deep-learning frameworks for TensorFlow*.

<code>pip install --upgrade intel-extension-for-tensorflow[cpu]</code>

We set the backend type to CPU for Intel® Tensorflow Operator Optimization:

<code>os.environ['ITEX_XPU_BACKEND'] = 'CPU'</code>

And enabled Advanced Automatic Mixed Precision for improved inference speed and reduced memory consumption:

<code>os.environ['ITEX_AUTO_MIXED_PRECISION'] = '1'</code>

### Performance Comparison
The following graphs illustrate the substantial performance improvements achieved by integrating Intel® oneAPI libraries and frameworks into our models:

1. Comparing the time taken to complete one epoch in various development Environments<br><br>
<img src="https://user-images.githubusercontent.com/130077430/230733189-78e03097-7c88-4f42-9c0e-159e58aa7972.jpg" width="495" height="400">

By leveraging the power of Intel® oneAPI libraries and frameworks, our models achieves remarkable performance enhancements and optimized memory utilization . The seamless integration of oneDAL, oneDNN, oneDPL, and AI Kit contributes to faster training, efficient inference, and improved overall user experience.

To migrate your project to OneAPI : 
[click here!](https://devcloud.intel.com/oneapi/get_started/) to get started

For reference : [click here!](https://www.youtube.com/watch?v=NkJXCalgmeU)
    
    
## 6️⃣ Save the model
       save the model to calculate the accuracy and loss
    
<hr/>

# Accuracy and Loss      <img src="https://user-images.githubusercontent.com/130077430/230577475-9af43d03-1a50-41c2-99b2-e1a28b69c84e.png" width="90" height="80">

We did 250 epochs, to get a good accuracy from the model i.e. 94% for training accuracy and 92% for validation accuracy.


<hr/>


    

    
<hr/>

# Learnings <img src="https://user-images.githubusercontent.com/130077430/230583675-33ad7480-857b-451f-a64b-3c45f21d390a.png" width="90" height="80">

<img src="https://user-images.githubusercontent.com/72274851/218504609-585bcebe-5101-4477-bdd2-3a1ba13a64a8.png" width="190" height="100"><img src="https://user-images.githubusercontent.com/72274851/220130227-3c48e87b-3e68-4f1c-b0e4-8e3ad9a4805a.png" width="800" height="100">

1) **Building a CNN model using Intel oneDNN :**
    OneAPI is an open-source software toolkit developed by Intel that simplifies the development of high-performance, heterogeneous applications. It allows       developers to write code that can run efficiently on a variety of architectures, including CPUs, GPUs, and FPGAs. oneDNN (Deep Neural Network) is a part     of oneAPI and is an optimized library for deep learning. It provides highly optimized building blocks for neural network models that run efficiently on a variety of hardware platforms.
   
2) **Machine Learning :**
    _How to use machine learning for identifiying the facial features from a drivers face to detect drowsiness._
   
3) **Convolutional Neural Network(CNN) :**
    _How to build, train and fine-tune convolutional neural networks for image and video classification._
   
4) **Preprocessinig the datasets :**
    _How to preprocess the data dowloaded from kaggle so that the machine learning could happen in a much better and efficient way._

    
5) **Team work :**
    _Collaborating and communicating effectively in a team to deliver a project._
   
6) **Understanding the need for a sexual harassment detection system**
_These are just a few examples of the knowledge and skills that i likely gained while building this project. Overall, building a sexual harasssment detection model  is a challenging and rewarding experience that requires a combination of technical expertise and knowledge ._

<hr/>

# Project Deployment <img src="https://user-images.githubusercontent.com/130077430/230725195-2f024fca-9cae-4e91-85dc-4c12e0e1fcb0.png" width="90" height="80">

# Harassment Detection Model with Streamlit

## Overview
This project implements a harassment detection model using Streamlit, capable of processing both images and videos to detect signs of sexual harassment. The model is built to analyze the content of the provided source and provide insights regarding potential harassment. 

## Features
- Processes both images and videos for harassment detection.
- Detects signs of sexual harassment within the provided source.
- Provides a user-friendly interface for easy interaction.

## Usage
To use the harassment detection model, follow these steps:
1. Access the Streamlit application using the following link: [Harassment Detection Streamlit App](https://harassment-detection.streamlit.app/)
2. Upload the image or video you want to analyze.
3. Wait for the model to process the content.
4. View the results indicating whether signs of sexual harassment are detected.

## Streamlit Application
Access the Streamlit application [here](https://harassment-detection.streamlit.app/).
## Sample Output
**Safe Working Environment:**
![Screenshot (94)](https://github.com/Altaf-01/Sexual-Harassment-Detection/assets/91909939/fc79f9c7-529d-4b8f-a3c6-6773b2889be3)
**Sexual Harassment Detected:**
![image](https://github.com/Altaf-01/Sexual-Harassment-Detection/assets/91909939/512e20d4-3203-4a58-bc35-38ee21f50827)
**Live demo**
<br/>
![live_demo](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/116085472/b3b47795-0b11-4bc8-bda2-fc48aa1c6c8c)



# Harassment Detection App as a POC

![image](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/116085472/a36353fd-4907-4f0a-9145-eafd01e9543f) ![image](https://github.com/Altaf-01/Sexual-Harassment-Detection-In-Workplace/assets/116085472/8042317e-e4e4-4f01-8b42-0f3edfaf4b4c)



We have built an app using Flutter. Flutter helps Build, test, and deploy beautiful mobile, web, desktop, and embedded apps from a single codebase. It is a cross-platform app development framework by Google 



# One more thing <img src="https://cdn.freebiesupply.com/logos/large/2x/apple1-logo-png-transparent.png" width="60" height="60">

<p align="middle"><img src="https://th.bing.com/th/id/R.cfabfe3a83a918b326ede9efb1d7ee8b?rik=sxInqysclnUS1A&riu=http%3a%2f%2fmedia.idownloadblog.com%2fwp-content%2fuploads%2f2015%2f08%2fSteve-Jobs-One-More-Thing.jpg&ehk=VbXo3DNGszgubtTtwYXhvwQyxwDKVJ%2bW7%2b0%2bproDQ%2fM%3d&risl=&pid=ImgRaw&r=0" width="800" height="300">
    
1) **EARLY WARNING SYSTEM :**

    Through behavioural analysis it predicts non-desirable behavioural patterns and warns potential threats.

   
2) **EMOTION AND INTENT ANALYSIS :**
   
    Analyzes emotions and intentions in conversations, identifying subtle signs of manipulation, gaslighting, and emotional abuse.
   
3) **CULTURAL NORMALISATION :**

   Adapt the model to different cultural contexts for multinational organizations.

4) **REALTIME ADAPTIVE LEARNING :**

   Periodically re-train the model with new data to adapt to evolving and emerging harassment tactics.

5) **ENHANCING SOCIETAL IMPACT :**

   Integrating advanced predictive machine learning models with a focus on addressing and resolving societal challenges.

6) **CONTEXTUAL DOMAIN EXPANSION AND ADAPTION :**

   Expanding a model's capabilities to detect sexual harassment in various places and environments.

   
<hr/>

# Conclusion <img src="https://user-images.githubusercontent.com/130077430/230730394-3dfbc977-435b-4a6f-bfa3-fc193606f0e0.png" width="90" height="80">

Through this project we can create a safer work environment, Support HR and Legal management, Reduce psychological and physical stress, early detection and prevention and overcome reporting hesitancy. If this project is used efficiently it may also lead to huge decrease in percentage of sexual harassment cases .

To view this project on Intel DevMesh : [click here!](https://devmesh.intel.com/projects/sexual-harassment-detection-in-workplace-559ed4)
<hr/>
