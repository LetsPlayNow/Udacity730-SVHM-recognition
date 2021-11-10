# House numbers recognition using CNN and Tensorflow
![][svhn image]

It is a final project for [Udacity 730 course (Deep Learning)][udacity course].  
I was aiming to create a real-time app that can recognize numbers in real-world photos of home numbers.  

I used [suggested approach][recognizer publication] from the Udacity course creators.   
Its idea is to build a bunch of simple digit classifiers on top of CNN. 

Each of these classifiers should recognize a digit for its position or digit absence.   
There is also an additional classifier for the length of the digits sequence.

I used 5 classifiers for digits and 1 for sequence length  
and borrowed some ideas about network structure for digit classifiers from [there][mnist].

## Work consists of 4 notebooks:
### 1 - MNIST CNN vs LReg.ipynb
Analysis of Tensorflow tutorial and warm-up:  
* https://www.tensorflow.org/get_started/mnist/beginners
* https://www.tensorflow.org/get_started/mnist/pros

### 2 - MNIST numbers recognizer.ipynb
Create a synthetic house numbers dataset from MNIST and train the model with it.  
I got medium quality during this experiment. 

### 3 - SVHN dataset cracking.ipynb
Official SVHN dataset stores information and labels in mat files,    
which can be opened only with h5py library.  
Retrieving information from them is a tricky thing.    
And there is not much documentation about how to work with this library  
or what the structure of our file is.

### 4 - SVHN digit recognizer.ipynb
- Load and prepare images (resize, crop) and labels.  
- Train model from the 2nd notebook and ... get poor quality and very long training duration.  
This part is uncompleted yet.

Some ideas are:
* To look more accurately into the last FC layer. Maybe reduce the size of a vector more gradually.  
Otherwise, we're losing a lot of information.
* In many cases, numbers are in the center of an image and take only a small area.  
We should think about how to adapt Convolutions and Poolings for it.

[svhn image]: http://ufldl.stanford.edu/housenumbers/examples_new.png
[udacity course]: https://classroom.udacity.com/courses/ud730/
[recognizer publication]: http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42241.pdf
[mnist pros]: https://www.tensorflow.org/get_started/mnist/pros

