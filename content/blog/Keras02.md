---
title: "Loading Keras into R, Part 2"
date: 2018-03-16T18:13:37-07:00
draft: true
---

So I learned [in the previous post][1] that if an *R* user wants to load the Python *keras* library into *R* to run neural net models, it is necessary to load Python first. The *keras* package in *R* is an interface with Python, not a standalone package.

That's fine, but it would have been nice to know beforehand. So I thought I should write it down for others.

> Loaded Anaconda 3 Earlier

Fortunately, I loaded Anaconda 3 into my system earlier this year in preparation for a program at UCLA on data science. We have been using Jupyter Notebooks and, lately, Jupyter Lab to run both *R* and Python code, so I have much of the Python infrastructure set up. Anaconda 3 is a pretty easy installation, though it does take some time due to its size. It is a good place to start if you need a Python environment.

Anaconda Navigator is the main package in the Anaconda 3 suite, and it comes with a version of *R Studio*. I can't say anything about that, but some users might find it convenient to have both Python and *R Studio* in the same software suite.

If you are working in Notebook or Lab, Docker is another useful program to have running on your system. You have to access and operate it through the shell. A thorough treatment of Docker and all its intricacies can be found in Joshua Cook's book, *Docker for Data Science: Building Scalable and Extensible Data Infrastructure Around the Jupyter Notebook Server*, [available from Apress][2].

One way or another, however you work with Python, setting it up is necessary for loading the *keras* package into *R*. And since *keras* works with TensorFlow you will need to load the *R* library *tensorflow*, as well, but that should not be too demanding.

> Easiest to Work with Python in the Command Window

Once you have set up Anaconda 3, it is probably easiest to work with Python through the command window, Anaconda Prompt. The *keras* package does not come preloaded in Anaconda, so you have to install it. I found [on Git the code][3] making this possible, and if you are not familiar with Python it might be easiest just to follow this approach.

At the command line in Anaconda Prompt, you need to enter:

`pip install keras`.

Then `import keras`.

That's it.

Though I don't have personal experience using it, another method I understand works, which you should try only if the previous command does not help, is to enter:

`sudo pip3 install keras`.

A common mistake is to enter instead:

`conda install keras`

So try to avoid that.

It takes a while to load *keras* into Python, so be patient and enjoy watching the forward slash spin around while the program does its thing.

> Good to Go

Once you have *keras* loaded, go back to your *R* environment and install and load the CRAN version of the library.

You should be good to go.

The Pyimagesearch blog [has a good post][4] on the *keras* installation in much more detail if you are interested. I didn't find it necessary to carry out the steps described there for editing the *keras.json* config file, setting up GPU support, or accessing *OpenCV* bindings, but if you do this is a good reference.

We can talk about the *R* interface with TensorFlow some other time.

 [1]: https://www.finex.co/loading-keras-into-r/
 [2]: https://www.apress.com/us/book/9781484230114
 [3]: https://github.com/keras-team/keras/issues/4889
 [4]: https://www.pyimagesearch.com/2016/07/18/installing-keras-for-deep-learning/