# Introduction

This repository contains the code for the paper "Botometer 101: a practical guide for researchers."

To demonstrate how to use [Botometer](botometer.osome.iu.edu) to perform bot detection for research, we provide a simple case study and share the source code here.

# Dependency

This demonstration use Python3.7 and the following packages:

- [`botometer-python`](https://github.com/IUNetSci/botometer-python): query the Botometer Pro API
- [`tweepy`](https://www.tweepy.org/): access Twitter API; please use versions >= 3.5.0,<4 that `botomeer-python` depends on as well
- [`requests`](https://docs.python-requests.org/en/latest/): make HTTPS requests

If you also want to replicate the analysis, you will also need

- [`matplotlib`](https://matplotlib.org/)
- [`scipy`](https://scipy.org/)
