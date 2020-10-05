# Key Assurance

Use a neural network algorithm to identify random and non-random sequences to comparable fidelity as the existing tests, and the overhead in implementing onboard as a check during runtime to assure security.

The code will generate train/test samples, perform the benchmark 
standard statistical Diehard tests on those test samples, train 
a machine learning algorithm to distinguish between 
noise and signal+noise and compare the results from both 
approaches.

## Table of contents
- [Installation](#installation)
- [Usage](#usage)

## Installation

The prefered method of installation is via the 
anaconda package manager. An alternative method 
using pip and virtualenv may also be used. Instructions 
using this alternative method will also be given 
below. 

In addition to those python packages included in 
the requirements.txt file, you will also need to 
install the non-python Dieharder package. This will 
require that you have sudo priviledges. Otherwise, 
you will need to install this from source.

`sudo apt-get install dieharder`

### Anaconda Installation Option

Create a virtual environment using 
the anaconda package manager. 

`conda update conda`

`conda create -n myenv python=3.6 anaconda`

Source your environment

`source activate myenv`

Install required packages. Anaconda will also 
handle all non-python packages needed.

`conda install requirements.txt`

### Alternative Installation Option

First, ensure that you have both CUDA and CUDNN 
installed on your machine. This is required 
in order to run tensorflow on a GPU (which 
will speed up training).

Create a virtual 
environment where the required dependency packages 
will be installed.

`virtualenv -p python3.6 myenv`

Source the virtual environment

`source myenv`

Install the required packages via pip.

`pip install requirements.txt`


## Usage

The entirety of the code may be found within the 
ipython notebook titled **nn_for_key_assurance.ipynb**. 
Simply open this notebook in a jupyter notebook server in 
order to get started.

## Getting started

First, execute the cell under the title 
**Import required software packages**.

Next, we need to define some important global variables 
which will be used throughout the code. Under the 
**# Model variables** heading you can find parameters 
which describe things like the total number of training 
samples to be used, bit size of signals and batch size 
... etc. Make sure that you define the **ML_path** variable 
as this will determine where your files containing results 
will be stored.

Under the **# Plotting variables** tag are variables which 
define plotting functions in the results section of the code.

After having defined global variables to your satisfaction, 
simply run the rest of the cells in order. At a minimum, it is 
recommended that you use 100,000 training samples and ~2000 total 
testing samples.