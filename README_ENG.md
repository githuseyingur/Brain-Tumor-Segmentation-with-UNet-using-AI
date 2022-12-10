# README IN ENGLİSH

Manual segmentation of a brain tumor from MRI images is a very time consuming method and performance is highly dependent on the experience of the physician. Therefore, automatic brain tumor segmentation from MRI images using deep learning methods enables efficient tumor detection. In this study, a CNN-based U-Net model was used for brain tumor segmentation.

#### In the first phase of the project, a model that performs full tumor segmentation, and in the second phase, another model that segments different areas of the tumor was successfully created. Finally, the prediction images were combined and the results were compared. <br /><br />
Different areas of the tumor in the segmentation images in the training data were observed by separating them from the segmentation image. These different areas of the tumor have numerical values ​​on the segmentation images. These numerical values ​​are 1 for Edema, 2 for Expanding Tumor, and 4 for Necrosis: <br /><br />

![Segmentasyon(Ödem,genişleyen,nekroz)](https://user-images.githubusercontent.com/120099096/206866820-5f2ca28d-fa2c-4af6-ae20-e07099e971fe.png)
