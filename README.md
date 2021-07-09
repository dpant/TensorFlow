# Tensorflow Specialization on Coursera 

Programming assignments, high level learning ideas from all courses in the Coursera [TensorFlow specilization ](https://www.coursera.org/professional-certificates/tensorflow-in-practice) .

## Credits
This repo contains my work for this specialization. The code base, quiz questions and diagrams are taken from the [TensorFlow specilization ](https://www.coursera.org/professional-certificates/tensorflow-in-practice), unless specified otherwise.

## Programming Assignments
This page will describe in short about each project, the core learning and some tips.

### [Course 1: Introduction to TensorFlow for Artificial Intelligence, Machine Learning, and Deep Learning](https://www.coursera.org/learn/introduction-tensorflow/home/welcome)
  This course mainly talk about the how to implement some of the classification task in tensorflow using (deep neural network and CNN). Here is the week wise summary of the course.
  -  Week 1: Talks mainly about a very basic model (sort of hello world of tensorflow) for fitting a model in hourse price data. 
  -  Week 2: Introduce to deep neural network (2 layer) as well as idea of callback to stop training when the desired accuracy is achieved.The labs uses training on fashion MNIST (10 labels) and digit MNIST dataset (10 labels). Both of these dataset have small (28x28) images centred around objects. This make achieving high accuracy feasible. With little effort on these task we can achieve >90% training accuracy. Digit MNIST is easier to train and even a 2 layer deep network can achieve 99% accuracy. Fashion MNIST (2 layerdeep ) is able to achieve ~90% accuracy.
  -  Week 3: Introduces to the idea of CNN which is then applied to fashion MNIST. Also by choosing the runtime environment to GPU (in Colab) we can observe 25X improvement in training speed. The genaral idea is to use few repetition of CONV --> MAX_POOL layers before feeding the output to desnse layers.
  -  Week 4: Introduces the idea of ImageGenerator object which is really cool as it can read, label (based on directory name) and resize images on the runtime. The ImageGenerator object (training and validation) can then be passed to model.fit(). The programming assigment takes on real horse and human images to make a horseVshuman classifier. The project takes ~1000 images for the classification task.
  - High level ideas are capured in [Summary of Tensorflow course #1](https://github.com/dpant/TensorFlow/blob/main/Course_1_full_summary.ipynb) 
  - Individual weeks labs are captured at [course 1 labs](https://github.com/dpant/TensorFlow/tree/main/Course1)
  
