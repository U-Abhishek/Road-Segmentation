# Road Segmentation
Road surface detection is important for safely driving autonomous vehicles, this is still to be overcome in the field of visual perception for vehicle and robotic navigation on heavily damaged and unpaved roads is the task of reliable path and obstacle detection. This repo present an approach for road detection considering variation in surface types, this repo consists of methods to convert low quality RGB image into segmented road information and that can be a rich source for any autonomus system.
### Image Segmentation
Image segmentation can be formulated as a classification problem of pixels with semantic labels (semantic segmentation) or partitioning of individual objects (instance segmentation). Semantic segmentation performs pixel-level labeling with a set of object categories (e.g., human, car, tree, sky) for all image pixels, thus it is generally a harder undertaking than image classification, which predicts a single label for the entire image.
## Dataset
The dataset used in this project is semantic segmentation GT for road surfaces contains 701 frames from [RTK dataset](http://www.lapix.ufsc.br/pesquisas/projeto-veiculo-autonomo/datasets/?lang=en).

The [RTK dataset](http://www.lapix.ufsc.br/pesquisas/projeto-veiculo-autonomo/datasets/?lang=en) is composed by 77547 images captured by a low-cost camera with low-resolution, which could increase the challenge of our application. All frames were obtained with a lowcost camera mounted on the roof of a vehicle. The dataset is composed of images captured during the daytime, containing lighting variations and plenty of shadows on the road.
It contains images of asphalt roads, unpaved, different paved roads and transitions between surface types. Also contains variations in the quality of these roads, with potholes, waterpuddles, speed-bumps, patches, etc.\
![0](https://user-images.githubusercontent.com/86155658/151662045-ce98657d-4d32-4703-816e-5383c85199f0.png)
![0](https://user-images.githubusercontent.com/86155658/151662051-78672c28-ebca-48ce-8cf6-5edc21d0a61b.png)


## Data Processing
The labels in the above dataset are having multiple classes, The code for converiting all the multy class labels are converted into binary labels is procided in the following  notebook [**********].

## Models:
All the models used are trained form scratch with no pre-trained models. 
## 1)  Fully Convolutional Networks(FCN):
One of the first deep learning works for semantic image segmentation, using a fully convolutional network (FCN). An FCN includes only convolutional layers, which enables it to take an image of arbitrary size and produce a segmentation map of the same size.

#### Code for FCN : [FCN Training.ipynb](https://github.com/U-Abhishek/Road-Segmentation/blob/master/FCN%20Training.ipynb)
### Results of FCN
![image](https://user-images.githubusercontent.com/86155658/151660900-2e7ea6ce-6d83-43ae-9e5e-0727873abcfd.png)

### Limitations of FCN:
It is not fast enough for real-time inference, it does not take into account the global context information in an efficient way.This issue is however addressed in some of the high-resolution networks.

## 2) U-Net:
The U-Net architecture comprises two parts, a contracting path to capture context, and a symmetric expanding path that enables precise localization. The down-sampling or contracting part has a FCN-like architecture that extracts features with 3 × 3 convolutions. The up-sampling or expanding part uses up-convolution (or deconvolution), reducing the number of feature maps while increasing their dimensions.
#### Code for U-Net : [U-Net Training.ipynb](https://github.com/U-Abhishek/Road-Segmentation/blob/master/UNet%20Training.ipynb)
### Results of U-Net 
![image](https://user-images.githubusercontent.com/86155658/151661584-a5d80a39-2bb1-42e0-a54b-16dbc51d2a2a.png)
![image](https://user-images.githubusercontent.com/86155658/151661611-9efc209a-c945-44af-aa74-ca43e9e59513.png)
