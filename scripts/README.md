# Introduction

In this case study, we aims to estimate which cashtag of `$SHIB`, `$FLOKI`, and `$AAPL` is more amplified by bot-like accounts.

# Commands to collect the data

First, we need to collect the tweets mentioning these cashtags.
This can be achieved by the script [`collect_tweets.py`](/collect_tweets.py).
We need to pass three parameters to it: the cashtag, number of tweets needed, and the path to the file where we want to store the tweets.

We can use the following commands:

```bash
python collect_tweets.py '$floki' 2000 ../data/floki_tweets.jsons
python collect_tweets.py '$shib' 2000 ../data/shib_tweets.jsons
python collect_tweets.py '$aapl' 2000 ../data/aapl_tweets.jsons
```

Second, we need to extract the unique user ids so that we can perform bot detection later.
This can be achieved by the script [`extract_user_ids.py`](/extract_user_ids.py).
It takes two parameters: the input file that contains the tweets we just collected and the output file that contains the unique user ids.

We can use the following commands:

```bash
python extract_user_ids.py ../data/floki_tweets.jsons ../data/floki_user_id.csv
python extract_user_ids.py ../data/shib_tweets.jsons ../data/shib_user_id.csv
python extract_user_ids.py ../data/aapl_tweets.jsons ../data/aapl_user_id.csv
```

Finally, we can perform bot detection.
This can be done by the script [`bot_detection.py`](/bot_detection.py).
It needs two parameters: the input file that contains the user ids to check and the output file where that we want to store the results.

We can use the following commands:

```bash
python bot_detection.py ../data/floki_user_ids.csv ../data/floki_bot_scores.jsons
python bot_detection.py ../data/shib_user_ids.csv ../data/shib_bot_scores.jsons
python bot_detection.py ../data/aapl_user_ids.csv ../data/aapl_bot_scores.jsons
```
