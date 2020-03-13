# Semantic-Segmentation-using-UNET-architecture-on-VOC2012-dataset
To locate the motorbike in an given image using UNET architecture
Dataset: http://host.robots.ox.ac.uk/pascal/VOC/voc2012/
Methodology Used: 
 	Data Preprocessing:(segmentation.ipyb)
1) The data consist of images with 21 segmented class but we require only single class that is, motorbike to predict.
2) The pixel value of segmented area of motorbike is found ie., (64,128,128,255) 
3) We can use two classes, one for background and other for required segmented area. But, currently I'm  using single class for segmented area only.
4) To extract and store the features and labels of the images the empty list of  image data and segmented image are created.
5) Using the pickle module data is serialized and de-serialized for creation of model.
 	Model Building:(unet_model.ipyb)

1) UNET Model is build on tensorflow environment using keras 
2) The UNET model consists of three major parts:
     a) Down_block consisting of two 3x3 Conv2D layers with 'relu' activation followed by 2x2,     
         MaxPooling layer.
     b) Up_block consisting of Upsampling layer and Concatenating layer followed by two 3x3 
          Conv2D layers.
     c) Bottleneck block consisting of two Conv2D  3x3 layers. 
3) The model is fitted with 20 epochs and model summary is printed. The obtained accuracy for model is around 83%
4) Model is saved as h5 file.

 	Problems in Model:
1) The accuracy is not enough and can be increased by increasing number of epochs.
2) The dataset consists of only 147 images  and to build strong models, data augmentation techniques can be applied.
3) ResUNet model can be build to make more deep models.
