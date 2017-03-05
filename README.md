Apartment finder
-------------------

This repo contains the code for a bot that will scrape Craigslist for real-time listings matching specific criteria, then alert you in Slack.  This will let you quickly see the best new listings, and contact the owners.  You can adjust the settings to change your price range, what neighborhoods you want to look in, and what transit stations and other points of interest you'd like to be close to.

Heavily inspired (including this Readme file) by the work of [Vik Paruchuri](https://github.com/VikParuchuri/apartment-finder] and a talk by [Ian Whitestone](https://github.com/ian-whitestone/apartment-finder)

Vik wrote a blog about his search.  Read it [here](https://www.dataquest.io/blog/apartment-finding-slackbot/).


Settings
--------------------

Look in `settings.py` for a full list of all the configuration options.  Here's a high level overview:

* `MIN_PRICE` -- the minimum listing price you want to search for.
* `MAX_PRICE` -- the minimum listing price you want to search for.
* `CRAIGSLIST_SITE` -- the regional Craigslist site you want to search in.
* `AREAS` -- a list of areas of the regional Craiglist site that you want to search in.
* `BOXES` -- coordinate boxes of the neighborhoods you want to look in.
* `NEIGHBORHOODS` -- if the listing doesn't have coordinates, a list of neighborhoods to match on.
* `MAX_TRANSIT_DISTANCE` -- the farthest you want to be from a transit station.
* `TRANSIT_STATIONS` -- the coordinates of transit stations.
* `CRAIGSLIST_HOUSING_SECTION` -- the subsection of Craigslist housing that you want to look in.
* `SLACK_CHANNEL` -- the Slack channel you want the bot to post in.

External Setup
--------------------

Before using this bot, you'll need a Slack team, a channel for the bot to post into, and a Slack API key:

* Create a Slack team, which you can do [here](https://slack.com/create#email).  
* Create a channel for the listings to be posted into.  [Here's](https://get.slack.help/hc/en-us/articles/201402297-Creating-a-channel) help on this.  It's suggested to use `#housing` as the name of the channel.
* Get a Slack API token, which you can do [here](https://api.slack.com/docs/oauth-test-tokens).  [Here's](https://get.slack.help/hc/en-us/articles/215770388-Creating-and-regenerating-API-tokens) more information on the process.

Configuration
--------------------

## Manual

* Create a file called `private.py` in this folder.
    * Add a value called `SLACK_TOKEN` that contains your Slack API token.
    * Add any other values you want to `private.py`.

Installation + Usage
--------------------

    
## Manual

* Look in the `Dockerfile`, and make sure you install any of the apt packages listed there.
* Install Python 3 using Anaconda or another method.
* Install the Python requirements with `pip install -r requirements.txt`.
* Run the program with `python main_loop.py`. Results will be posted to your #Housing channel if successful.

Troubleshooting
---------------------


## Manual

* Look at the stdout of the main program.
* Inspect `listings.db` to ensure listings are being added.

