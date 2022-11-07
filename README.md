# Face 3D depth reconstruction

<img src="https://github.com/cantonioupao/generate-synthetic-face-data/blob/main/assets/eg3d_training.gif" alt="drawing" width="600" height="300"/>

This is the repository for the face depth regressor implementation. Given a single-view input image, the neural network regressor, predicts dense  depth pixel values, and achieves 3D reconstruction of the entire face. The model is trained on  synthetic EG3D generated data. The model is trained for different neural networkl architectures. The 2 architectures are the [Attention-UNET](https://arxiv.org/pdf/1804.03999.pdf) and the [MiDaS-DPT Vision Transformer](https://github.com/isl-org/MiDaS). The MiDaS architecture recovers mostly coarse face details and focuses on correctly predicting dense depth values that recover the general face structure, rather than fine-grained details of the face region(e.g wrinkles, nose, cheeks, lips). Our best model, is the Attention-UNET, that can reconstruct better high-frequency details around the face region, resulting to better overall 3D reconstruction, from the predicted depthmaps. The code for evaluating our existing models, as well as training/fine-tuning models with custom data, can be found in the following notebooks. 



Below you can find the relavant notebooks:
| Description      | Link |
| ----------- | ----------- |
| Generate EG3D face data (image, depthmap and 3D .obj)| [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cantonioupao/generate-synthetic-face-data/blob/main/colab_notebooks/eg3d.ipynb)|
| Visualize synthetic face mesh | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/cantonioupao/generate-synthetic-face-data/blob/main/colab_notebooks/visualize_mesh.ipynb)|

A good comparison, to our work, is the [UnSup3D](https://elliottwu.com/projects/20_unsup3d/) [paper](https://arxiv.org/pdf/1911.11130.pdf), that leverages depth regression to reconstruct 3D faces in an unsupervised manner. This repository levarages data generated by a model called [EG3D](https://nvlabs.github.io/eg3d/media/eg3d.pdf) and uses the codebase from [EG3D](https://github.com/NVlabs/eg3d). Please refer to the [project's webpage](https://arxiv.org/pdf/2112.07945.pdf) for more information. For more information about our synthetic training dataset, please refer to our detailed repository [here](https://github.com/cantonioupao/generate-synthetic-face-data)






