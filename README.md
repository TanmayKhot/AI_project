# AI_project

## Team Members
1. Tanmay Khot - tsk9863@nyu.edu
2. Akshita Lakkad - acl10003@nyu.edu (AWS contact)
3. Sirus Baladi - Sb8389@nyu.edu

## Reverse Image Search - Project Details

In this project we aim to build a reverse image search mechanism where the query images are faces. The project is divided into two tasks :
1. Creating a baseline model
2. Performing improvements on the baseline model

Dataset used: **Labeled Faces in Wild (LFW)** is the dataset we use for the project. LFW contains face photographs where each face has been labeled with the name of the person pictured. The data set contains more than 13,000 images of faces collected from the web. There are 4 different sets of LFW images. For our project, we work with the 'Deep Funneled' images. Deep funneled LFW dataset is formed by a combination of unsupervised joint alignment with unsupervised feature learning. 

We incorporate the deep funneled LFW dataset as it produces superior results over the original dataset.

Task 1: 

Refer the following notebooks:

1_Baseline_Embeddings - The baseline model we have considered is ResNet50. In this task, we locally compute embeddings for the LFW deep funneled dataset using pretrained ResNet50 convolutional neural network model. We create a pickle dump of the extracted features and save it to EC2 as 'features-lfw-deepfunneled-resnet50.pickle'

3_Indexing_and_Similarity_Search - This notebook contains steps to run Jupyter notebook in Deep Learning AMI. We also run OpenSearch which we access using the docker image as shown in the notebook. Once we have jupyter running, we connect to OpenSearch. In this notebook, upon loading the embeddings we have implemented kNN using cosine similarity measure to find out images similar to the query image. 

Task 2:

Refer the following notebooks:

2_Facenet_Embeddings - Similar to baseline task, we generate embeddings but this time for a more advanced network, FaceNet. The feature embeddings generated using FaceNet have 128 dimensions. We create a pickle dump of these emebeddings and upload it to EC2.

3_Indexing_and_Similarity_Search - In this notebook, we load the FaceNet embeddings, create a new kNN index with OpenSearch. The '.search' function returns all the images similar to the query image and is displayed in the notebook. 

The output_images folder contains all the results from both ResNet50 and FaceNet model.

The embeddings are here 'https://drive.google.com/drive/folders/1Xhv_OJukG_z39LXYPX15zp9-AMQbxd4u?usp=sharing'
