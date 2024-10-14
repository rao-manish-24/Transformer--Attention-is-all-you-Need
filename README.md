Transformer Model with PyTorch
Overview

This project implements a Transformer model in PyTorch, which is widely used for tasks like machine translation, text generation, and various other natural language processing (NLP) applications. The transformer architecture, introduced in the paper "Attention is All You Need", eliminates recurrence and convolutions entirely, relying solely on the self-attention mechanism to draw global dependencies between inputs and outputs.

This repository includes key functionalities like data loading, model training, beam search for inference, and visualization of attention mechanisms. It also provides different training configurations for both local and cloud environments (such as Google Colab).

Features
Transformer Architecture: Implements the full transformer model architecture, including multi-head self-attention layers, positional encodings, and feed-forward networks.

Training Configurations: Includes notebooks and scripts for training the transformer model both locally and in Google Colab.

Inference & Beam Search: Implements an inference pipeline with optional beam search to improve translation accuracy.

Attention Visualization: Contains a notebook for visualizing attention weights in the transformer, allowing for interpretability of the attention mechanism.

Configurable Parameters: Supports hyperparameter configuration through a configuration file (config.py), making it easy to customize the model.

Dataset Management: Provides utilities for loading and processing datasets for training and evaluation.

WandB Integration: The project supports Weights & Biases for tracking experiment metrics during training.


Prerequisites=
To run the project locally, ensure that the following are installed:

Python 3.8 or higher
PyTorch (version 1.7+)
CUDA (optional, for GPU acceleration)
Other required Python packages listed in requirements.txt or conda.txt

Set up the environment:

Using pip:

pip install -r requirements.txt
Using Conda:

conda create --name transformer --file conda.txt
conda activate transformer
Prepare the dataset:

Modify the dataset.py file to load the dataset of your choice (e.g., WMT or any other translation dataset). Ensure the dataset is correctly processed into tokenized inputs and targets.

Model Training=
There are two main ways to train the model: locally and on Google Colab.

Local Training
Open the Local_Train.ipynb notebook and configure the paths and parameters as per your dataset.
Run the notebook step-by-step to train the transformer on your local machine.
Alternatively, you can run the train.py script directly from the command line:

python train.py --config config.py
Google Colab Training=
If you want to train using Google Colab, open the Colab_Train.ipynb notebook and run it in Colab after uploading your dataset or linking it to Google Drive.

Inference=
For running inference and evaluating the model's translation performance, use the Inference.ipynb notebook or execute the translate.py script:


python translate.py --config config.py --input "Translate this sentence."
The inference pipeline also supports beam search for improved translation accuracy, as demonstrated in the Beam_Search.ipynb notebook.

Attention Visualization=
The attention_visual.ipynb notebook allows you to visualize the attention mechanisms at work during inference. By inspecting the attention weights, you can gain insights into how the transformer model is making its predictions.

Configuration=
The configuration for the transformer model is defined in the config.py file. This file allows you to easily customize the model's architecture and training hyperparameters, such as:

Number of layers
Number of attention heads
Hidden dimension sizes
Dropout rates
Learning rate
Batch size
