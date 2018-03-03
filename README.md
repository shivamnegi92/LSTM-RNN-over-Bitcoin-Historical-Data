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

Keras is a high-level neural networks API, written in Python and capable of running on top of TensorFlow, CNTK, or Theano. 
It was developed with a focus on enabling fast experimentation. Being able to go from idea to result with the least possible delay 
is key to doing good research.

Use Keras if you need a deep learning library that:

* Allows for easy and fast prototyping (through user friendliness, modularity, and extensibility).
* Supports both convolutional networks and recurrent networks, as well as combinations of the two.
* Runs seamlessly on CPU and GPU.





