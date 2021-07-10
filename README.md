# Tensorflow Specialization on Coursera 

Programming assignments, high level learning ideas from all courses in the Coursera [TensorFlow specilization ](https://www.coursera.org/professional-certificates/tensorflow-in-practice) .

## Credits
This repo contains my work for this specialization. The code base, quiz questions and diagrams are taken from the [TensorFlow specilization ](https://www.coursera.org/professional-certificates/tensorflow-in-practice), unless specified otherwise.

## Programming Assignments
This page will describe in short about each project, the core learning and some tips.

### [Course 1: Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning](https://www.coursera.org/learn/introduction-tensorflow/home/welcome)
  This course mainly talk about the how to implement some of the classification task in tensorflow using deep neural network and CNN. Here is the week wise summary of the course.
  -  Week 1: Talks mainly about a very basic model (sort of hello world of tensorflow). It is illustrated by fitting a model in hourse price data (just few x(bedrooms),y (price) examples). 
  -  Week 2: Introduces to deep neural network (2 layer) as well as idea of callback to stop training when the desired accuracy is achieved.The labs uses training on fashion MNIST (10 labels) and digit MNIST dataset (10 labels). Both of these dataset have small (28x28) images centred around objects. This make achieving high accuracy feasible. With little effort on these task we can achieve >90% training accuracy. Digit MNIST is easier to train and even a 2 layer deep network can achieve 99% accuracy. Fashion MNIST (2 layerdeep ) is able to achieve ~90% accuracy.
  -  Week 3: Introduces to the idea of CNN which is then applied to fashion MNIST. Also by choosing the runtime environment to GPU (in Colab) we can observe 25X improvement in training speed. The genaral idea is to use few repetition of CONV --> MAX_POOL layers before feeding the output to dense layer.
  -  Week 4: Introduces the idea of ImageGenerator object which is really cool as it can read, label (based on directory name) and resize images on the runtime. The ImageGenerator object (training and validation) can then be passed to model.fit(). The programming assigment takes on real horse and human images to make a horseVshuman classifier. The project takes ~1000 images for the classification task.
  - High level ideas are capured in [Summary of Tensorflow course #1](https://github.com/dpant/TensorFlow/blob/main/Course_1_full_summary.ipynb) 
  - Individual weeks labs are captured at [course 1 labs](https://github.com/dpant/TensorFlow/tree/main/Course1)
  
### [Course 2: Convolutional Neural Networks in TensorFlow](https://www.coursera.org/learn/convolutional-neural-networks-tensorflow/home/welcome)
  This course mainly teach about the how to implement CNN's and associated tips.
  -  Week 1: Talks about taking real world images and do a classification task. The data in this project is not very clean and images are not fixed size or centered around the object. There are multiple objects in some of the images. The main idea is to use ImageDataGenerator class to read the data, prepare its labels, resize it appropriately.
      -  [Project #1: Cats and dogs classificaiton using 3K images.](https://github.com/dpant/TensorFlow/blob/main/Course2/catVsDogs3KDataPoint%20%20-%20Notebook.ipynb)
          - This project shows how to do data preprocessing and generating labels using ImageDataGenerator objects. These objects can be training_generator and validation_generator which can be directly fed into the model.fit().This project is overfitting. Training accuracy is >98% while validation test is ~70%. Its a huge gap! and this is partly because we don't have sufficient data for this task (~2K traiing images) 
       - [Project #2 Cats vs Dogs Classification using 25K images](https://github.com/dpant/TensorFlow/blob/main/Course2/catVsDogs3KDataPoint%20%20-%20Notebook.ipynb). 
          - This project have 25K images in total. Generated training accuracy of 87% while test accuracy is 85%. So there is no overfitting. Since the dataset is large it is best to use GPU to train it. Took around 25 mins to train for 15 epochs in a GPU (Colab Pro plan). This again highlights the fact that having bigger dataset help in reducing the overfitting.
 
 -  Week 2: This week is all about data agumentation. Data agumentation can be really useful tool if one have limited data to do the training. For example if in cats and dogs classification we have 3K images, we will overfit the data as shown in project #1 about. Data agumentation can help in avoiding this. The most common data agumentation techniques available in tf.keras.preprocessing.image.ImageDataGenerator are, shear,zoom,rotation,horizontal_filp,vertical_flip, shifting(width_shift_range,height_shift_range). All of these transformation radomly choosen to be applied during training time for each epoch. Hence ImageDataGenerator() is not creating new images , instead it is modifying the existing images by doing these transformation (choosen randomly). Epoch to epoch accuracy/loss will vary more if we apply these transformations (due to to random transformation applied).
For the validation set the transformations are not applied. [Keras ImageDataGenerator](https://keras.io/preprocessing/image/)

     - [Project #3: Cats vs dogs classificaiton using 3K images + data agumentation.](https://github.com/dpant/TensorFlow/blob/main/Course2/CatsVsDogsWithDataAgumentation.ipynb)
        - Data agumentation helped a lot here in the original training we had 100% accuracy in training vs 75% in validation set which is clearly a sign of overfitting. With data agumentation we have 84% accuracy in training and 79% in validation set. Thus the gap in accuracy is narrowed (overfitting is reduced)
        
     - [Project #4: Horse vs human classificaiton using 1K images + data agumentation.](https://github.com/dpant/TensorFlow/blob/main/Course2/HorseVsHumanDataAgumentation.ipy    
          - Notice that Data Agumentation does not always help in reducing the overfitting (gap between accuracy of training,validation). For example the horse vs human applying data agumentation did not yeild good result.So data agumentation is not a substitute of good quality diverse image data. In this particular project both train and validation set have similar type of data (images) so doing data agumentation did not helped (In fact added random noise in training and validation accuracy). Validating accuracy fluctuate widely here as we are chainging the training set in every epoch by adding random transformations.
      
