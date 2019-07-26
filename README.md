<h2>Aerial Cactus Identification</h2>

The objective of this project is to identify whether aerial images contain columnar cacti, as part of the Aerial Cactus Identification competition. This [competition](https://www.kaggle.com/c/aerial-cactus-identification) is based on resesearch previously hosted on kaggle - original [dataset](https://www.kaggle.com/c/aerial-cactus-identification/data) can be found here.

<h4>Sample images for classification:</h4>

The training dateset includes 17,500 32x32 jpeg aerial images images. Each training image is labeled as whether or not it columnar cactus are present in the image. Test predictions are generated for submission on 4000 32x32 pixel jpeg aerial images.

Cacti:

![Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/000c8a36845c0208e833c79c1bffedd1.jpg)

No Cacti:

![No Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/00ba3da3fe6d600703e28dece68fbb12.jpg)


Data Augmentation:

Keras' ImageDataGenerator class allows the augmentation of input image to artificially expand the total size of the input training dataset:

train_datagen = ImageDataGenerator(rotation_range=40,
        width_shift_range=0.2,
        height_shift_range=0.2,
        shear_range=0.2,
        zoom_range=0.2,
        horizontal_flip=True,
        fill_mode='nearest')
        
Transfer Learning - VGG16 Base Layers
I explored frozen VGG16 base model pretrained on the ImageNet dataset. I did not retrain these layer given the similarity of cacti to other objects in the imagenet dataset.

Model Parameters:


Evaluation
After 100 training epochs, the model settled at a validation loss of ~0.20 and a validation accuracy of ~0.97



Submission Score
Submission with this model scores an area under the ROC curve of 0.87 on the test dataset.
