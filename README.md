# Face 3D depth reconstruction

<img src="https://github.com/cantonioupao/face-depth-3D-reconstruction/blob/main/assets/depth_regression.png" alt="drawing" />

This is the repository for the face depth regressor implementation. Given a single-view input image, the neural network regressor, predicts dense  depth pixel values, and achieves 3D reconstruction of the entire face. The model is trained on  synthetic EG3D generated data. The model is trained for different neural network architectures. The 2 architectures are the [Attention-UNET](https://arxiv.org/pdf/1804.03999.pdf) and the [MiDaS-DPT Vision Transformer](https://github.com/isl-org/MiDaS). The MiDaS architecture recovers mostly coarse face details and focuses on correctly predicting dense depth values that recover the general face structure, rather than fine-grained details of the face region(e.g wrinkles, nose, cheeks, lips). Our best model, is the Attention-UNET, that can reconstruct better high-frequency details around the face region, resulting to better overall 3D reconstruction, from the predicted depthmaps. Overall, our models, predict dense depth pixels, for a given input image and then using the [depth2mesh algorithm](https://github.com/sfu-gruvi-3dv/deep_human), we recover the 3D face reconstruction as a trianglular mesh (as a .obj file), directly from the predicted depthmap (.png). The code for evaluating our existing models, as well as training/fine-tuning models with custom data, can be found in the following notebooks. 



Below you can find the relavant notebooks:
| Description      | Link |
| ----------- | ----------- |
| :star: Attention-UNET depth regressor *training, testing, evaluation*| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cantonioupao/face-depth-3D-reconstruction/blob/main/colab_notebooks/unet_depthmap_training.ipynb)|
| :2nd_place_medal: MiDaS (DPT Vision Transformer) depth regressor *training, testing, evaluation* | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cantonioupao/face-depth-3D-reconstruction/blob/main/colab_notebooks/midas_depthmap_training.ipynb)|

The notebooks above, include step by step instructions and interactive ways to guide anyone to rapidly set up, train and generally play around with these models.

A good comparison, to our work, is the [UnSup3D](https://elliottwu.com/projects/20_unsup3d/) [paper](https://arxiv.org/pdf/1911.11130.pdf), that leverages depth regression to reconstruct 3D faces in an unsupervised manner. This repository levarages data generated by a model called [EG3D](https://nvlabs.github.io/eg3d/media/eg3d.pdf) and uses the codebase from [EG3D](https://github.com/NVlabs/eg3d). Please refer to the [project's webpage](https://arxiv.org/pdf/2112.07945.pdf) for more information. For more information about our synthetic training dataset, please refer to our detailed repository [here](https://github.com/cantonioupao/generate-synthetic-face-data)






