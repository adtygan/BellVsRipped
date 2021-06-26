# BellVsRippped

***Site Live On =>*** https://calm-desert-07b80cc1e.azurestaticapps.net/

This a fun little web app to classify between **Bell Bottoms** and **Ripped Jeans**. 

## **Table of Contents**

### **1. [Usage](#usage)**

### **2. [Machine Learning Process](#machine-learning-process)** 

### **3. [Performing Grad-CAM](#performing-grad-cam)**
---

### Usage <a name= 'usage'></a>

1. Clone the repository
```
git clone https://github.com/AdityaG09/Bell-Vs-Rippped.git
```
2. Enter the directory
```
cd BellVsRipped
```
3. Install required packages and start the app on localhost
```
npm install
npm run start
```
---

### Machine Learning Process <a name= 'machine-learning-process'></a>
- **DATA PREPARATION** - Training data was scraped using [Bing Image Search API](https://azure.microsoft.com/en-in/try/cognitive-services/?api=search-api-v7). Dataset contains 150 images per class.
- **MODELING** - ResNet-34 architecture on Pytorch(fastai) was used for training the model. 
- **EVALUATION** - Transfer Learning enabled achieving accuracy of **98.2%** while using very little images per class for training. 
- **DEPLOYMENT** - Converted the PyTorch model into an ONNX runtime for faster inference. Deployed the ONNX runtime as an API using [Azure Functions](https://azure.microsoft.com/en-in/services/functions/).

`BellVsRipped.ipynb` explains the steps and process in detail, so that it is easy to follow along. 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AdityaG09/Bell-bottoms-or-Ripped-jeans/blob/main/bell_bottom_or_ripped.ipynb)  

---

### Performing Grad-CAM <a name='performing-grad-cam'></a>
Additionally, Using the ***hooks*** functionality of PyTorch, Grad-CAM heatmaps were generated. This helps us understand why the model labels the given image as a particular class. 

| Grad-CAM on Bell bottoms | Grad-CAM on Ripped jeans |
| ----------- | ----------- |
| <img width="100%" src="https://github.com/AdityaG09/Bell-Vs-Rippped/blob/main/ML/HeatmapImages/bell_bottom_sartorial.png"> | <img width="100%" src="https://github.com/AdityaG09/Bell-Vs-Rippped/blob/main/ML/HeatmapImages/best_ripped_jean_casual.png"> |
| <img width="100%" src="https://github.com/AdityaG09/Bell-Vs-Rippped/blob/main/ML/HeatmapImages/bell_bottom_women.png"> | <img width="100%" src="https://github.com/AdityaG09/Bell-Vs-Rippped/blob/main/ML/HeatmapImages/ripped_jeans_rough.png"> 


