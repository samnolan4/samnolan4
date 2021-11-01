# Instructions for running code:

## Getting Started

This solution takes advantage of the bert-as-service architecture:

	https://bert-as-service.readthedocs.io/en/latest/

Running the code requires running two programmes in two seperate virtual environments. 
Note that both programmes are computationally expensive. To run in a reasonable amount
of time, we used the UQ GPU-labs available at 78-226.

We used Anaconda Environment manager to set up and run the environments:
	
	https://www.anaconda.com/products/individual

Next, the pre-trained bert server must be downloaded from:

	https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip

This file is 420MB and needs to be moved to the submission directory and unzipped.

Once downloaded and installed, run Anaconda Prompt.

## Setting up server

To create and run the bert server, run the following commands:

1. cd path/to/s4432976  *#substitute in path of unzipped submission*

2. conda create -n server python=3.7.6

2. conda activate server

2. pip install tensorflow==1.13.0rc1

2. pip install bert-serving-server

2. bert-serving-start -model_dir uncased_L-12_H-768_A-12\ -num_worker=1 -max_seq_len=75

*Note that the server needs tensorflow 1.13.0 and python 3.7.6 to run.*

## Setting up the client

With the server running, open another Anaconda Prompt window.

To create and run the bert client, run the folowing commands:

1. cd path/to/s4432976 *#substitute in path of unzipped submission*

1. conda create --name client

1. conda activate client

1. conda install tensorflow-gpu

1. conda install pandas

1. pip install bert-serving-client

1. conda install scikit-learn

1. pip install jupyter

1. conda install keras

1. jupyter notebook

## Running the code

This should open a jupyter notebook in the submission directory. From here, open main.ipynb and run the cells in the notebook.
This will create a submission document call submission.csv which is in the format required for the Kaggle competition.

Note, the method bertClient.encode() can take up to 5-10 minutes even on high-powered computers, so allow time to run.

<!---
samnolan4/samnolan4 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
