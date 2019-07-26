<h2>Aerial Cactus Identification</h2>

The objective of this project is to identify whether aerial images contain columnar cacti, as part of the Aerial Cactus Identification competition. This [competition](https://www.kaggle.com/c/aerial-cactus-identification) is based on resesearch previously hosted on kaggle - original dataset can be found [here](https://www.kaggle.com/c/aerial-cactus-identification/data).

<h4>Sample images for classification:</h4>

The training dateset includes 17,500 32x32 jpeg aerial images images. Each training image is labeled as whether or not it columnar cactus are present in the image. Test predictions are generated for submission on 4000 32x32 pixel jpeg aerial images.

<h4>Cacti:</h4>

![Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/000c8a36845c0208e833c79c1bffedd1.jpg)

<h4>No Cacti:</h4>

![No Cacti:](https://github.com/Deepthi-cloud/Machine-Learning-Capstone-Project-/blob/master/Images/00ba3da3fe6d600703e28dece68fbb12.jpg)


<h4>Data Augmentation:</h4>

Keras' ImageDataGenerator class allows the augmentation of input image to artificially expand the total size of the input training dataset:

train_datagen = ImageDataGenerator(rescale=1/.255,
        rotation_range=40,
        width_shift_range=0.2,
        height_shift_range=0.2,
        shear_range=0.2,
        zoom_range=0.2,
        horizontal_flip=True,
        fill_mode='nearest')
        
<h4>Transfer Learning</h4> 

Keras [VGG16 application](https://keras.io/applications/#vgg16) trained on [Imagenet](http://image-net.org/explore) data has been implemented. 

<h4>Model Parameters:</h4>

<h5>1.Evaluation</h5>
After 100 training epochs, the model settled at a validation loss of ~0.20 and a validation accuracy of ~0.97

<h5>2.Submission Score</h5>
Submission with this model scores an area under the ROC curve of 0.87 on the test dataset.
