Aerial Cactus Identification
The objective of this project is to identify whether aerial images contain columnar cacti, as part of the Aerial Cactus Identification competition. This competition is based on resesearch previously hosted on kaggle - original dataset can be found here.

Sample images for classification:
The training dateset includes 17,500 32x32 jpeg aerial images images. Each training image is labeled as whether or not it columnar cactus are present in the image. Test predictions are generated for submission on 4000 32x32 pixel jpeg aerial images.

![Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/000c8a36845c0208e833c79c1bffedd1.jpg)


![No Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/00ba3da3fe6d600703e28dece68fbb12.jpg)


Data Augmentation
Keras' ImageDataGenerator class allows the augmentation of input image to artificially expand the total size of the input training dataset:

train_datagen = ImageDataGenerator(rescale=1./255,
                                   validation_split=0.1,
                                   rotation_range=40,
                                   shear_range=0.2,
                                   width_shift_range=0.2,
                                   height_shift_range=0.2,
                                   horizontal_flip=True,
                                   zoom_range=0.2,
                                   fill_mode='nearest')
Transfer Learning - VGG16 Base Layers
For an initial attempt, I explored using a frozen VGG16 base model pretrained on the ImageNet dataset. I did not retrain these layer given the similarity of cacti to other objects in the imagenet dataset.

Model Parameters:


Evaluation
After 100 training epochs, the model settled at a validation loss of ~0.20 and a validation accuracy of ~0.97



Submission Score
Submission with this model scores an area under the ROC curve of 0.87 on the test dataset.
