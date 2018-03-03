# Bitcoin Time Series Prediction with LSTM

## Context
Bitcoin is the longest running and most well known cryptocurrency, first released as open source in 2009 by the anonymous Satoshi Nakamoto.
Bitcoin serves as a decentralized medium of digital exchange, with transactions verified and recorded in a public distributed ledger 
(the blockchain) without the need for a trusted record keeping authority or central intermediary. Transaction blocks contain a SHA-256 
cryptographic hash of previous transaction blocks, and are thus "chained" together, serving as an immutable record of all transactions
that have ever occurred. As with any currency/commodity on the market, bitcoin trading and financial instruments soon followed public
adoption of bitcoin and continue to grow. The data is available at the link below:

https://www.kaggle.com/mczielinski/bitcoin-historical-data/data


## Method - LSTM (Works great for series data)

Long Short-Term Memory Network
The Long Short-Term Memory network, or LSTM network, is a recurrent neural network that is trained using Backpropagation Through 
Time and overcomes the vanishing gradient problem.
As such, it can be used to create large recurrent networks that in turn can be used to address difficult sequence problems in machine
learning and achieve state-of-the-art results. Instead of neurons, LSTM networks have memory blocks that are connected through layers.
A block has components that make it smarter than a classical neuron and a memory for recent sequences. A block contains gates that manage
the block’s state and output. A block operates upon an input sequence and each gate within a block uses the sigmoid activation units to 
control whether they are triggered or not, making the change of state and addition of information flowing through the block conditional.

## Library: Keras

![Keras logo](https://s3.amazonaws.com/keras.io/img/keras-logo-2018-large-1200.png)


Keras is a high-level neural networks API, written in Python and capable of running on top of TensorFlow, CNTK, or Theano. 
It was developed with a focus on enabling fast experimentation. Being able to go from idea to result with the least possible delay 
is key to doing good research.

Use Keras if you need a deep learning library that:

* Allows for easy and fast prototyping (through user friendliness, modularity, and extensibility).
* Supports both convolutional networks and recurrent networks, as well as combinations of the two.
* Runs seamlessly on CPU and GPU.

----------------


## Getting started: 30 seconds to Keras

The core data structure of Keras is a __model__, a way to organize layers. The simplest type of model is the [`Sequential`](https://keras.io/getting-started/sequential-model-guide) model, a linear stack of layers. For more complex architectures, you should use the [Keras functional API](https://keras.io/getting-started/functional-api-guide), which allows to build arbitrary graphs of layers.

Here is the `Sequential` model:

```python
from keras.models import Sequential

model = Sequential()
```

Stacking layers is as easy as `.add()`:

```python
from keras.layers import Dense

model.add(Dense(units=64, activation='relu', input_dim=100))
model.add(Dense(units=10, activation='softmax'))
```

Once your model looks good, configure its learning process with `.compile()`:

```python
model.compile(loss='categorical_crossentropy',
              optimizer='sgd',
              metrics=['accuracy'])
```

If you need to, you can further configure your optimizer. A core principle of Keras is to make things reasonably simple, while allowing the user to be fully in control when they need to (the ultimate control being the easy extensibility of the source code).
```python
model.compile(loss=keras.losses.categorical_crossentropy,
              optimizer=keras.optimizers.SGD(lr=0.01, momentum=0.9, nesterov=True))
```

You can now iterate on your training data in batches:

```python
# x_train and y_train are Numpy arrays --just like in the Scikit-Learn API.
model.fit(x_train, y_train, epochs=5, batch_size=32)
```

Alternatively, you can feed batches to your model manually:

```python
model.train_on_batch(x_batch, y_batch)
```

Evaluate your performance in one line:

```python
loss_and_metrics = model.evaluate(x_test, y_test, batch_size=128)
```

Or generate predictions on new data:

```python
classes = model.predict(x_test, batch_size=128)
```

Building a question answering system, an image classification model, a Neural Turing Machine, or any other model is just as fast. The ideas behind deep learning are simple, so why should their implementation be painful?

For a more in-depth tutorial about Keras, you can check out:

- [Getting started with the Sequential model](https://keras.io/getting-started/sequential-model-guide)
- [Getting started with the functional API](https://keras.io/getting-started/functional-api-guide)

In the [examples folder](https://github.com/keras-team/keras/tree/master/examples) of the repository, you will find more advanced models: question-answering with memory networks, text generation with stacked LSTMs, etc.


------------------



## Installation

Before installing Keras, please install one of its backend engines: TensorFlow, Theano, or CNTK. We recommend the TensorFlow backend.

- [TensorFlow installation instructions](https://www.tensorflow.org/install/).
- [Theano installation instructions](http://deeplearning.net/software/theano/install.html#install).
- [CNTK installation instructions](https://docs.microsoft.com/en-us/cognitive-toolkit/setup-cntk-on-your-machine).

You may also consider installing the following **optional dependencies**:

- cuDNN (recommended if you plan on running Keras on GPU).
- HDF5 and h5py (required if you plan on saving Keras models to disk).
- graphviz and pydot (used by [visualization utilities](https://keras.io/visualization/) to plot model graphs).

Then, you can install Keras itself. There are two ways to install Keras:

- **Install Keras from PyPI (recommended):**

```sh
sudo pip install keras
```

If you are using a virtualenv, you may want to avoid using sudo:

```sh
pip install keras
```

- **Alternatively: install Keras from the GitHub source:**

First, clone Keras using `git`:

```sh
git clone https://github.com/keras-team/keras.git
```

 Then, `cd` to the Keras folder and run the install command:
```sh
cd keras
sudo python setup.py install
```

------------------


## Using a different backend than TensorFlow

By default, Keras will use TensorFlow as its tensor manipulation library. [Follow these instructions](https://keras.io/backend/) to configure the Keras backend.




