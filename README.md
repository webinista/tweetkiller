# tweetkiller

Python script that deletes your tweets &#8212; either all of them, or only ones before a particular date.

Install and use [`virtualenv`](https://pypi.python.org/pypi/virtualenv) to run this script.

```bash
pip install virtualenv
virtualenv tweetkiller
cd tweetkiller
source bin/activate
```
After creating your virtual environment, install `python-twitter` and its dependencies using **pip** and the requirements.txt file from within your virtual environment.

```bash
pip install -r requirements.txt
```

## How to use

1. **Download your [Twitter Archive](https://support.twitter.com/articles/20170160?lang=en).** This will provide a series of JSON-formatted text files. `tweet.js` contains all of your tweets, with a unique identifer for each one.

1. Edit `tweet.js` to remove `window.YTD.tweet.part0` from the beginning of the file. (Note: I've only tested this with ≈6000 or so tweets. You may need to do more cleanup than this if you have thousands more tweets.)

1. **Create a [Twitter app](https://apps.twitter.com/)**. This is how you get your Consumer Key, Consumer Secret, Access Token, and Access Token Secret.

1. **Clone this repo.**

1. **Rename `tweetkillerconf.sample.py` to `tweetkillerconf.py` and update it** with the path to `tweet.js` file, and the keys and secrets provided by Twitter in Step 2.

1. **Set the `BEFORE_DATE`** to delete only those tweets  posted before a certain date. Set to `False` _if you want to delete **all** of your tweets_. 

  I can't stress this enough: **If you do not set a date, you will delete ALL of your tweets**

1. **Run this script** using the command `python tweetkiller/tweetkiller.py`.

## What this does

It does exactly what [Twitter](https://support.twitter.com/articles/18906) says happens when you delete a tweet.

- Removes tweets from your public timeline.
- Removes retweets of your tweet.

Be aware that:

- Twitter may still retain copies of your Tweet in its database.
- Third parties, such as [the Wayback Machine](https://archive.org/web/) may still have archives of your tweets.


## Disclaimer, no warranties, no support

This is a hastily-written-in-an-afternoon project by a Python n00b. There is no test suite. There are probably bugs. It will delete things. It might delete things you didn't want it to delete. Test yourself with a small batch of tweets. It comes with no promises or warranties about its fitness for a particular purpose. _I also do not provide technical support._


 
