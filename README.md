# Bell-Vs-Rippped

This a fun little web app to classify between **Bell Bottoms** and **Ripped Jeans**. 


### Machine Learning Process
- **DATA PREPARATION** - Training data was scraped using [Bing Image Search API](https://azure.microsoft.com/en-in/try/cognitive-services/?api=search-api-v7). Dataset contains 150 images per class.
- **MODELING** - ResNet-34 architecture on Pytorch(fastai) was used for training the model. 
- **EVALUATION** - Transfer Learning enabled achieving accuracy of **98.2%** while using very little images per class for training. 
- **DEPLOYMENT** - Converted the PyTorch model into an ONNX runtime for faster inference. Deployed the ONNX runtime as an API using [Azure Functions](https://azure.microsoft.com/en-in/services/functions/).

Additionally, I used the ***hooks*** functionality of PyTorch to generate Grad-CAM heatmaps and overlaid it on top of the original image. This helps us understand why the model labels the given image as a particular class. The notebook explains the steps and process in detail, so that it is easy to follow along.  
### Grad-CAM on Bell bottoms
<p align="left" width="100%">
    <img width="33%" src="https://github.com/AdityaG09/Bell-bottoms-or-Ripped-jeans/blob/main/heatmap_images/bell_bottom_sartorial.png"> 
    <img width="33%" src="https://github.com/AdityaG09/Bell-bottoms-or-Ripped-jeans/blob/main/heatmap_images/bell_bottom_women.png"> 
</p>

### Grad-CAM on Ripped jeans
<p align="left" width="100%">
    <img width="33%" src="https://github.com/AdityaG09/Bell-bottoms-or-Ripped-jeans/blob/main/heatmap_images/best_ripped_jean_casual.png"> 
    <img width="33%" src="https://github.com/AdityaG09/Bell-bottoms-or-Ripped-jeans/blob/main/heatmap_images/ripped_jeans_rough.png"> 
</p>  

We see how when making the prediction, the model focuses on the knees and the trouser leg area. This is pretty intuitive since bell bottoms have their signature bell shape in the trouser leg area, and jeans are mostly ripped near the knee region.
