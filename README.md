# Mistral Fine-Tuning for Indian Agriculture Dataset

This repository contains the code and resources for fine-tuning the open-source **Mistral** large language model using an Indian agriculture dataset sourced from [Kaggle](https://www.kaggle.com). The project aims to adapt the capabilities of Mistral to address tasks related to the agriculture domain in the Indian context.

## Project Overview

Fine-tuning a large language model like Mistral with a domain-specific dataset enhances its ability to generate relevant and accurate responses. This repository includes:
- The fine-tuning script in a Jupyter Notebook (`AGmistralfinetuning.ipynb`)
- Guidance for setting up the environment
- Instructions for running the fine-tuning process

## Dataset

The [dataset](https://www.kaggle.com/datasets/vineetkukreti/indian-agriculture-dataset) used for fine-tuning is from Kaggle and is focused on Indian agriculture. It includes information of dstrict-wise yearly area, yield and production.


### Prerequisites

Ensure the following tools and dependencies are installed:

- Python 3.8 or higher
- PyTorch (for model training)
- Hugging Face Transformers library
- Jupyter Notebook

## Current Status

This project is still a work in progress. The training of the Mistral model has not yet been successfully completed. Currently, there is an issue during the training phase that needs resolution. Specifically, the following error is encountered:  


### Explanation of the Error

This error occurs when using the `Trainer` class from Hugging Face Transformers and the model is managed by Accelerate for memory optimization. If parts of the model are offloaded to CPU or disk for memory efficiency, you cannot move the entire model or certain components of it during training. This situation arises because Accelerate hooks handle the model’s placement dynamically, and any manual attempts to move the model cause a conflict.

### Suggested Fixes

To address this issue:
1. Ensure that your model and datasets fit in the available GPU memory. If not, consider optimizing batch size, sequence length, or using gradient accumulation.
2. Disable or adjust the Accelerate configuration if you do not need dynamic memory optimization.
3. Check for any incompatibilities in the versions of Hugging Face Transformers, Accelerate, or PyTorch.

---

This issue is under investigation,contribution and your help is highly appreciated in resolving this issue. Feel free to submit a pull request with a fix or workaround and
share resources or experiences related to this error. Updates will be provided as the problem is resolved. Work Around Update Pendind
