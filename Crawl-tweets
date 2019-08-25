#!/usr/bin/env python
# -*- coding: utf-8 -*-
from __future__ import unicode_literals
from tweepy import Stream
from tweepy import OAuthHandler
from tweepy.streaming import StreamListener
import tweepy
import csv
import pandas as pd
#consumer key, consumer secret, access token, access secret.
ckey = "consumer key"
csecret = "consumer secret"
atoken = "access token"
asecret = "access secret"
auth = OAuthHandler(ckey, csecret)
auth.set_access_token(atoken, asecret)
api = tweepy.API(auth,wait_on_rate_limit=True)
# Open/Create a file to append data
csvFile = open('Dataset1.csv', 'a')
#Use csv Writer
csvWriter = csv.writer(csvFile)

for tweet in tweepy.Cursor(api.search,q="key-word or emoticon",count=10000,lang="ar",since="DATE").items():
    print (tweet.created_at, tweet.text)
    csvWriter.writerow([tweet.text.encode('utf-8')])
