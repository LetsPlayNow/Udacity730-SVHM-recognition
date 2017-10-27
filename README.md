# Udacity730-SVHM-recognition
## Recognize house numbers with tensorflow
![][svhn image]

This is a final project for [Udacity 730 course (Deep Learning)][udacity course].
Aim is to create live app that can interpret number strings in real-world images.

I used [suggested approach][recognizer publication] from course creators.
It's idea in building a bunch of simple digit classifiers on a top of CNN.
Each of these classifiers should predict it's digit or `None`.
Also 1 classifier for a length of digits sequence.

In my work there are 5 classifiers for digits and 1 for sequence length  
based on a top of simple CNN, which structure idea I took from [here][mnist pros].

## Work consists of 4 notebooks:
### 1 - MNIST CNN vs LReg.ipynb
Walkthrough of Tensorflow tutorial which consists in two parts
* https://www.tensorflow.org/get_started/mnist/beginners
* https://www.tensorflow.org/get_started/mnist/pros

This is a kind of warm-up.

### 2 - MNIST numbers recognizer.ipynb
Create synthetic house numbers dataset from MNIST and train model on it.  
I got medium quality on this dataset with my model. 


### 3 - SVHN dataset cracking.ipynb
Official SVHN dataset stores information and labels in mat files,    
which can be opened only with h5py library.  
Retrieving information from them is a tricky thing.    
And there is no much documentation about how to work with this library  
or how structure of our file looks like.  

So it's kind of a hacking.

### 4 - SVHN digit recognizer.ipynb
Load and prepare images (resize, other) and labels.

Train our model from 2-th notebook and ...
get poor quality and very long training duration.
This part isn't fully accomplished yet.

Some ideas are:
* Look more precisely into last FC layer. Reduce size of a vector in more soft manner.  
In other way you loosing a lot of information.

* Numbers in many cases are in the center of image and take small part of it.  
Think how to adapt Convs and Poolings for it.

[svhn image]: http://ufldl.stanford.edu/housenumbers/examples_new.png
[udacity course]: https://classroom.udacity.com/courses/ud730/
[recognizer publication]: http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42241.pdf
[mnist pros]: https://www.tensorflow.org/get_started/mnist/pros

