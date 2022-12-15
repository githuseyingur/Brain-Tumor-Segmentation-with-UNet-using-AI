# README IN ENGLİSH

Manual segmentation of a brain tumor from MRI images is a very time consuming method and performance is highly dependent on the experience of the physician. Therefore, automatic brain tumor segmentation from MRI images using deep learning methods enables efficient tumor detection. In this study, a CNN-based U-Net model was used for brain tumor segmentation.

#### In the first phase of the project, a model that performs full tumor segmentation, and in the second phase, another model that segments different areas of the tumor was successfully created. Finally, the prediction images were combined and the results were compared. <br /><br />
Different areas of the tumor in the segmentation images in the training data were observed by separating them from the segmentation image. These different areas of the tumor have numerical values ​​on the segmentation images. These numerical values ​​are 1 for Edema, 2 for Expanding Tumor, and 4 for Necrosis: <br /><br />

![Segmentasyon(Ödem,genişleyen,nekroz)](https://user-images.githubusercontent.com/120099096/206866820-5f2ca28d-fa2c-4af6-ae20-e07099e971fe.png)

<br /><br />
### DATA SET (BraTS 2019)

The data set contains 462 data, 335 of which are training and 127 are validation. Each data consists of four different types of images for the same image as **Flair**, **T1**, **T1c** and **T2**. In addition, there is an original **segmentation image**. 

A total of **three models** with segmentation for each were used: **complete tumor, enhancing tumor area, and non-edema tumor area.** Each model study was carried out with 7770 pieces of data with a specific cross-section range of the images. The result image was obtained by combining the predictions of these models.

Sections of the files in each data in the data set: <br /> <br />

![data_set](https://user-images.githubusercontent.com/120099096/206864407-ca65e05b-06b2-48e1-8076-78ad18dec599.png) <br /><br />
![data_set2](https://user-images.githubusercontent.com/120099096/206864409-8c3fd7f3-406f-4be5-8fa0-7266b00c31d4.png) <br /><br /> <br /><br />

### U-NET

To talk about the U-Net model; The created U-Net model consists of two parts: Compression and Expansion. Size reduction operation is performed on the compression path, and the size increase operation is performed on the expansion path. Each layer in these two paths consists of more than one Convolution layer and one Pooling layer. Maximum Pooling method is applied in the Pooling layer. In the second half of the model, there are Reverse Convolution layers as the size increase process will be performed. An activation function called ReLU activates the Convolution layers in the model. This function prevents the model from learning negative values. The difference and advantage of the U-Net model from other CNN (Convolutional Neural Network) architectures is that feature maps are transferred from each layer in the compression path to each layer in the expansion path by establishing a horizontal connection. This process is called Copy and Corp. With this process, features lost by the size reduction process are regained on the Expansion path. In the U-Net architecture, features are not lost through linked copying of feature maps.



### To Be Continued...

