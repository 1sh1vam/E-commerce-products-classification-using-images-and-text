# E-commerce-products-classification-using-images-and-text
# Multi-modal deep learning Method:

This problem comes under the category of multi-label classification and product retrieval. Sometimes product's textual data (product title & description) is helpful for this task, and sometimes product's images help. Hence, we need a Deep learning model which takes into account both the products image and text. This is why a multi-modal deep-learning method is required, with its help we can generates such embeddings that comprises of both the product's text and image representation which can help in further downstream tasks for classification and product retrieval.

# We have taken the reference from HUSE paper :
A lot of ideas implemented here are taken from this paper. I have mentioned in the notebook where I have taken refernce from this paper. You can go and read that section for better understanding.
# Paper overview
﻿HUSE: Hierarchical Universal Semantic Embeddings (https://arxiv.org/pdf/1911.05978.pdf)
This paper proposes a novel method, HUSE, to learn cross-modal representation with semantic information. HUSE learns a shared latent space where the distance between any two universal embeddings is similar to the distance between their corresponding class embeddings in the semantic embedding space. HUSE also uses a classification objective with a shared classification layer to make sure that the image and text embeddings are in the same shared latent space.
![HUSE overview](https://github.com/1sh1vam/E-commerce-products-classification-using-images-and-text/blob/master/HUSE.png)

As you can see the image HUSE model is divided into three parts.


### PART1: CREATING TEXT AND IMAGE EMBEDDINGS INPUTS:
HUSE being a Multimodal Model takes in two input, image and text. The Image is passed onto a pre-trained VGG16 Image Model which produces an embedding for an individual images and trained a small model which are used to obtain a representation of the Text.
  
### PART2: MODEL IMPLEMENTATION FOR CREATING FINAL EMBEDDINGS:
The output from VGG16 is passed onto an Image Tower in parallel to output from text model which is passed onto the Text Tower. The L2 normalized output from both the towers are further passed onto a shared fully connected layer. The output of the shared fully connected layer is further used to calculate different losses.
﻿
### PART3: INCORPORATING THREE  LOSSES INTO THE ARCHITECTURE:
The paper incorporates three losses, for Class Level Similarity, Semantic Similarity, Cross Modal Gap. All three losses are explained in detail in the paper.

### Results:
We have been able to achieve an accuracy of 98.21% on test dataset whereas we got an accuracy of 98.69% on train dataset.

### Note:
If you are getting any difficulties you can reach to me here at github or on linkedin(https://www.linkedin.com/in/1sh1vam/).
