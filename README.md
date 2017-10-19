# tensorflow-tweet-generator

## Tech Design

**Objective:**

An AI that generates Halloween inspired tweets.

Mostly reused code from https://github.com/sherjilozair/char-rnn-tensorflow which was inspired from Andrej Karpathy's [char-rnn](https://github.com/karpathy/char-rnn).

## Requirements
- [Tensorflow 1.0](http://www.tensorflow.org)


**Implementation summary:**

Multi-layer Recurrent Neural Networks (LSTM, RNN) for word-level language models in Python using TensorFlow.

1.  Show a computer some sample text (for example scary, fictional short stories and/or books).The computer identifies all the unique words in the sample text.
2.  The computer groups words based on how often they appear together in the sample text (using a particular mathematical model). This is the "learning" portion of "Deep Learning"
3.  A human picks a starting word (for example, "The").
4.  Using what it learned in Step 3, we ask the computer to guess the word most likely to come after the starting word "The," this is recorded as the second word
5.  Then, based on the first two words, we ask the computer to guess the third word. And so on.

Eventually, we tell the computer to stop guessing after many words, and we'll have successfully created a tweet inspired by fictional, halloween-esque literature.


**Design:**

1.  Obtain/create sample text (halloween-esque/fictional/classic or not, ideally 500,000 words or less
2.  Install TensorFlow
3.  Train the model (e.g. "group" words based on patterns)
4.  Create the "Tale from the Chip" - python example: parser.add_argument('-n', type=int, default=300, help='number of words to sample')
5.  Social team moderates the generated tweet, create/pick the associated image and publish as desired


**Technologies used:**

MacOS

TensorFlow binaries (not Google ML Engine)

Python


**Local setup:**

1.  install pip:\
    sudo easy_install pip\
    sudo easy_install --upgrade six
2.  install TensorFlow:\
    sudo pip install --upgrade $TF_BINARY_URL\
    ...or install version 1.0:\
    pip install tensorflow==1.0\
    ...to check which version of TensorFlow is installed:\
    python -c 'import tensorflow as tf; print(tf.__version__)'  # for Python 2\
    python3 -c 'import tensorflow as tf; print(tf.__version__)'  # for Python 3
3.  ...if you run into issues its likely due to numpy, if so install pip and ignore numpy version:\
    sudo pip install --ignore-installed numpy\
    ...then rerun step 3


**Train the model and generate:**

1.  let your computer know we want to use TensorFlow:\
    source ~/tensorflow/bin/activate
2.  CD into project:\
    cd ~/Documents/_Development/Intel-Tales-from-the-Chip/word-rnn-tensorflow-master
3.  train with default parameters set in "train.py" - this could take a while (e.g. 200,000 words took my 2013 MBP about 7 hours):\
    python train.py
4.  generate sample from the trained models, which only takes a few seconds:\
    python sample.py
5.  thats it! ....and you can modify parameters like number of words generated in the "train.py" file


**Tools:**

<https://www.creepypasta.com/>

<http://www.countofwords.com/>

<http://shakespeare.mit.edu/coriolanus/coriolanus.1.1.html>