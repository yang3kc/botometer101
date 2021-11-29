# Introduction

This repository contains the code for the paper "Botometer 101: a practical guide for researchers."

To demonstrate how to use [Botometer](botometer.osome.iu.edu) for bot detection in research, we provide a simple case study and share the source code here.

# How to

## Data collection

Please refer to the scripts under folder [/scripts](/scripts) for code and instructions to fetch data from Twitter and run bot detection.

## Data analysis

Please refer to the jupyter notebook under folder [/exps](/exps) for code to analyze the collected data and visualize the results.

# Dependency

This demonstration use Python3.7 and the following packages:

- [`botometer-python`](https://github.com/IUNetSci/botometer-python): query the Botometer Pro API
- [`tweepy`](https://www.tweepy.org/): access Twitter API; please use versions >= 3.5.0,<4 that `botomeer-python` depends on as well
- [`requests`](https://docs.python-requests.org/en/latest/): make HTTPS requests

If you also want to replicate the analysis, you will also need

- [`matplotlib`](https://matplotlib.org/)
- [`scipy`](https://scipy.org/)

# Community Guidelines

If you have questions about this project, please create.
You are also welcome to fork the project, modifying the code, and creating pull requests.
Please use clear and organized descriptions when creating issues and pull requests.

# Cite the paper

Please cite the paper as:

```
To be filled
```
