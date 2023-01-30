# Brain-Tumor-Segmentation-with-UNet-using-AI

Manual segmentation of a brain tumor from MRI images is a very time consuming method and performance is highly dependent on the experience of the physician. Therefore, automatic brain tumor segmentation from MRI images using deep learning methods enables efficient tumor detection. In this study, a CNN-based U-Net model was used for brain tumor segmentation.

#### In the first phase of the project, a model that performs full tumor segmentation, and in the second phase, another model that segments different areas of the tumor was successfully created. Finally, the prediction images were combined and the results were compared. <br /><br />
Different areas of the tumor in the segmentation images in the training data were observed by separating them from the segmentation image. These different areas of the tumor have numerical values ​​on the segmentation images. These numerical values ​​are 1 for Edema, 2 for Expanding Tumor, and 4 for Necrosis: <br /><br />

![206866820-5f2ca28d-fa2c-4af6-ae20-e07099e971fe](https://user-images.githubusercontent.com/120099096/215535247-9af3de53-c808-4e85-8d3a-ecaa4d5e2a7f.png)


<br /><br />
### DATA SET (BraTS 2019)

The data set contains 462 data, 335 of which are training and 127 are validation. Each data consists of four different types of images for the same image as **Flair**, **T1**, **T1c** and **T2**. In addition, there is an original **segmentation image**. 

A total of **three models** with segmentation for each were used: **complete tumor, enhancing tumor area, and non-edema tumor area.** Each model study was carried out with 7770 pieces of data with a specific cross-section range of the images. The result image was obtained by combining the predictions of these models.

Sections of the files in each data in the data set: <br /> <br />

![data_set](https://user-images.githubusercontent.com/120099096/206864407-ca65e05b-06b2-48e1-8076-78ad18dec599.png) <br /><br />
![data_set2](https://user-images.githubusercontent.com/120099096/206864409-8c3fd7f3-406f-4be5-8fa0-7266b00c31d4.png) <br /><br /> <br /><br />

### U-NET

To talk about the U-Net model; The created U-Net model consists of two parts: Compression and Expansion. Size reduction operation is performed on the compression path, and the size increase operation is performed on the expansion path. Each layer in these two paths consists of more than one Convolution layer and one Pooling layer. Maximum Pooling method is applied in the Pooling layer. In the second half of the model, there are Reverse Convolution layers as the size increase process will be performed. An activation function called ReLU activates the Convolution layers in the model. This function prevents the model from learning negative values. 

The difference and advantage of the U-Net model from other CNN (Convolutional Neural Network) architectures is that feature maps are transferred from each layer in the compression path to each layer in the expansion path by establishing a horizontal connection. This process is called Copy and Corp. With this process, features lost by the size reduction process are regained on the Expansion path. In the U-Net architecture, features are not lost through linked copying of feature maps.


![206864660-8602de60-5f69-4ea8-8673-3921dd82a544](https://user-images.githubusercontent.com/120099096/215529763-a05b7a79-3198-44ff-b33e-3c11591f0a98.png)
<br /><br />
![206866267-d3500599-80b6-47db-9668-bf13cc30745c](https://user-images.githubusercontent.com/120099096/215529935-abe286a5-d2be-41ec-a17c-5a41e855032e.png)
<br /><br />
![206866319-29a4ddf0-30dc-42ab-bba1-15410fe4cbc7](https://user-images.githubusercontent.com/120099096/215529999-4345f2a9-5c49-4cff-a58d-e29917017b82.png)
<br /><br />


### RESULTS <br /><br /> 

#### First Step - Tumor Area Segmentation Prediction <br /><br /> <br /><br />

![1](https://user-images.githubusercontent.com/120099096/206865925-4fb76413-acd4-427d-8486-f27df6375cbe.png) <br /><br />

![2](https://user-images.githubusercontent.com/120099096/206866032-d2c7a156-84e2-45af-a7f5-1ec63ddbfbee.png) <br /><br />

![4](https://user-images.githubusercontent.com/120099096/206866037-e02e3b05-db26-40e8-b687-7b318f914143.png) <br /><br />

![1000_Inferno](https://user-images.githubusercontent.com/120099096/206866041-91e8af00-e833-444a-b428-06e33d3500d4.png) <br /><br /><br /><br /> 

#### Second Step - Tumor Segmentation Of Different Areas Prediction <br /><br /> <br /><br />

Upon examination of the results, very similar results have been obtained to the original segmentation images. The segmentation of images segmented by a radiologist can be performed automatically within seconds. A success rate of 96% was achieved for the training data and 82% for the validation data. <br /><br />
<br /><br />
 
![Results](https://user-images.githubusercontent.com/120099096/206864960-0b4503ad-65f4-46f3-a70f-852eaf9a87bd.png)  <br /><br /> <br /><br />

![Results2](https://user-images.githubusercontent.com/120099096/206865220-81f9e9a0-e616-40aa-9438-0375a4e18679.png) <br /><br /> <br /><br />

![1772_test](https://user-images.githubusercontent.com/120099096/206865363-c1be903c-c719-48cd-a5f7-46402b8c71c4.png) <br /><br /> <br /><br /><br /><br />

Examining the results, a success rate of 95.8% for full tumor and 85.7% for validation data was reached using the Dice Coef metric. For the tumor-free area, success rates of 96.9% for training and 80.22% for validation data were achieved. For the expanding tumor area, success rates of 93.2% for training and 78.4% for validation data were reached.<br /><br />

![AccuracyTable](https://user-images.githubusercontent.com/120099096/206866196-4b5068d1-47e8-4309-85de-ff124c34f446.png)

