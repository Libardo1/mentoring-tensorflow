# Tensorflow tutorials for internship mentoring

## Contents

1. Week 1
    - [Basic Python](notebooks/basic_python.ipynb)
    - [Basic Tensorflow](notebooks/basic_tf.ipynb)
    - [Logistic Regression](notebooks/logistic_regression.ipynb)
    - [Linear Regression](notebooks/linear_regression.ipynb)
    - [Multilayer Perceptron](notebooks/mlp.ipynb)
    - [Convolutional Neural Network](notebooks/cnn.ipynb)
    - [Tensorboard](notebooks/tensorboard.ipynb)
    - [Image Processing](notebooks/image_processing.ipynb)
    - [Exercise](notebooks/exercise.ipynb)

2. Week 2

    - [Exercise](notebooks/flowers.ipynb)
    - RNN Reading list - [[1](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)] [[2](https://medium.com/@erikhallstrm/hello-world-rnn-83cd7105b767#.1d68gqvcf)]
    - RNN tutorial - [sjchoi86/char_rnn_train_tutorial.ipynb](https://github.com/sjchoi86/tensorflow-101/blob/master/notebooks/char_rnn_train_tutorial.ipynb)

## Installation guide

First, you need to set python virtual environment.<br>
(Or you could use Anaconda or system python etc.., but I prefer virtualenv)

```shell
$ cd location_you_want
# .venv3 can be changeable (whatever you want)
$ virtualenv .venv3 -p python3

# to activate virtual env
# .venv3 can be changeable
$ source .venv3/bin/activate
```

And then, you must install python libraries using pip. See `requirements.txt` for more info.

```shell
$ pip3 install -r requirements.txt
```

All done? Let's install tensorflow.

Tensorflow provide `.whl` file in github page, so we download and just install using pip. Note that if system setting is different from default tensorflow required system (e.g. CUDA v8.0, cudnn v5 etc..), you must compile tensorflow using Bazel (it's realllly boaring work), but in my machine you don't have to. :) 

```shell
# download tf .whl file
$ cd ~/Downloads
$ wget https://ci.tensorflow.org/view/Nightly/job/nightly-matrix-linux-gpu/TF_BUILD_IS_OPT=OPT,TF_BUILD_IS_PIP=PIP,TF_BUILD_PYTHON_VERSION=PYTHON3,label=gpu-linux/lastSuccessfulBuild/artifact/pip_test/whl/tensorflow-0.11.0-cp34-cp34m-linux_x86_64.whl

# .whl file you've downloaded
$ pip3 install tensorflow_blabla.whl
```

Then open (or create) `bash_profile` file in your home directory.

```shell
$ vim ~/.bash_profile
```

And write code below in `bash_profile`.

```shell
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64"
export CUDA_HOME=/usr/local/cuda
export CUDA_ROOT=/usr/local/cuda

export PATH=/usr/local/cuda/bin:$PATH
export PATH=/home/nmhkahn/Library/torch/install/bin:$PATH
```

Check everything is fine.

```shell
$ python3
```

```python
>>> import tensorflow as tf
>>> tf.__version__
'0.11.head'
>>> hello = tf.constant("hello, tensorflow!")
>>> sess = tf.Session()
>>> sess.run(hello)
hello, tensorflow!
>>> a = tf.constant(10)
>>> b = tf.constant(32)
>>> sess.run(a+b)
42
>>>
```

If you follow all step above, every system setting step is done. It's time to programming.<br>
One more notable thing is I provide code as IPython style. So to read and code, you must run Jupyter (IPython)

```shell
$ cd somewhere_code_is
# will give my ip address
$ jupyter notebook --ip=.... --port=....
```

## Note

Most codes are from Tensorflow-101 by sjchoi86. Thanks!
