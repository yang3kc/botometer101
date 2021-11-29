# Introduction

In this case study, we aims to estimate which cashtag of `$SHIB`, `$FLOKI`, and `$AAPL` is more amplified by bot-like accounts.

We will first query tweets mentioning these cashtags from Twitter, then query Botometer for bot detection.

# Instructions

## Set keys

Before collecting the data, you need to set your Twitter developer app key and RapidAPI key.
Make a copy of [`keys_template.json`](/scripts/keys_template.json) using the following command:

```bash
cp keys_template.json keys.json
```

Put your keys in the corresponding locations in `keys.json`.

## Collect tweets

First, we need to collect the tweets mentioning these cashtags.
This can be achieved by the script [`collect_tweets.py`](/scripts/collect_tweets.py).
We need to pass three parameters to it: the cashtag, number of tweets needed, and the path to the file where we want to store the tweets.

We can use the following commands:

```bash
python collect_tweets.py '$floki' 2000 ../data/floki_tweets.jsons
python collect_tweets.py '$shib' 2000 ../data/shib_tweets.jsons
python collect_tweets.py '$aapl' 2000 ../data/aapl_tweets.jsons
```

## Extract user ids

Second, we need to extract the unique user ids so that we can perform bot detection later.
This can be achieved by the script [`extract_user_ids.py`](/scripts/extract_user_ids.py).
It takes two parameters: the input file that contains the tweets we just collected and the output file that contains the unique user ids.

We can use the following commands:

```bash
python extract_user_ids.py ../data/floki_tweets.jsons ../data/floki_user_id.csv
python extract_user_ids.py ../data/shib_tweets.jsons ../data/shib_user_id.csv
python extract_user_ids.py ../data/aapl_tweets.jsons ../data/aapl_user_id.csv
```

## Bot detection

Third, we can perform bot detection.
This can be done by the script [`bot_detection.py`](/scripts/bot_detection.py).
It needs two parameters: the input file that contains the user ids to check and the output file where that we want to store the results.

We can use the following commands:

```bash
python bot_detection.py ../data/floki_user_ids.csv ../data/floki_bot_scores.jsons
python bot_detection.py ../data/shib_user_ids.csv ../data/shib_bot_scores.jsons
python bot_detection.py ../data/aapl_user_ids.csv ../data/aapl_bot_scores.jsons
```

Note that bot detection might take longer than the previous steps.

## Data analysis

For data analysis, please refer to the jupyter notebook under folder [`/exps`](/exps).
