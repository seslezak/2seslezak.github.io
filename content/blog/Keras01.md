---
title: "Loading Keras into R, Part 1"
date: 2018-03-14T18:12:29-07:00
draft: true
---

Late last year, Matt Dancho had [a post on deep learning][1] celebrating the arrival of the Python *keras* package for *R*. It is a very good tutorial on using artificial neural networks (ANN) to solve complicated business problems, well worth checking out.

> Took More Doing Than I Thought

I started working with neural networks over a decade ago with Palisade Decision Tree software, which includes [NeuralTools][2], a neural network add-in for Excel. It's a quality program that works well, but it is subject to constraints imposed by Excel. So I looked forward to playing around with *keras* and getting a sense of how *R* works with neural nets.

What I didn't know is that in order to use *keras* in *R* it is necessary to have the *keras* Python library loaded and ready to go. This took more doing than I thought it would.

Of course, *R* has native neural network and deep learning packages, such as *nnet* and *RSNNS*, [among others][3]. But the idea of *R* joining forces with Python to implement a *keras* package is a welcome addition and one I wanted to try. I went through [the *R-Studio* cheat sheet][4] on *keras* and decided to make a go.

> Straight to GTS Mode

Things went smoothly until I got to actually building and running the *keras* model. I was immediately faced with a long list of warnings followed by the failure of the model to run. I ran the code a couple more times to see if I could figure out what was going on. Each time, the same warnings popped up.

In looking closely at the warnings I finally noticed, buried among them towards the bottom, this error message:

`ModuleNotFoundError: No module named 'keras'`

I checked to make sure the *keras* library was loaded in my environment and running. It was. A lesson from a long ago data science class came to mind and I went straight to GTS mode. All I could find were references to *keras* in Python. There was nothing about this error message in *R*.

GitHub was the most help. There I [found a thread][5] on "No module named keras: #4889". But it was short and was closed down due to lack of use in late 2017.

That thread contained a few snippets of Python code that helped me figure out the problem. For *keras* to run in *R* you need to have *keras* loaded in Python. Which means you need to have Anaconda Prompt or JupyterLab loaded in your system, as well as *R*.

> Lesson Learned

This was news to me. It's not mentioned in the *keras* cheat sheet or in Matt's blog post.

In fact, the *keras* cheat sheet mentions in the "Installation" section that "the *keras R* package uses the Python *keras* library. You can install all the prerequisites directly from *R*."

That wasn't the case for me. There's a note that says "See *?keras_install* for GPU instructions," but when I run the command I get "No results found."

I guess it is common knowledge, but somehow I did not get the memo. Many others are probably unaware. Hence, this post.

The lesson here is [read the documentation][6]. *Keras* in *R* is the interface to Python's *keras*. No Python, no *keras* in *R*.

More on this is the next post.

 [1]: http://www.business-science.io/business/2017/11/28/customer_churn_analysis_keras.html
 [2]: http://www.palisade.com/neuraltools/
 [3]: https://cran.r-project.org/web/views/MachineLearning.html
 [4]: https://github.com/rstudio/cheatsheets/raw/master/keras.pdf
 [5]: https://github.com/keras-team/keras/issues/4889
 [6]: https://keras.rstudio.com/