# Twitter Watch
Build a system that tracks tweets and replies of the three of the following accounts (pick whichever three you like) from February 1st, 2023 onwards and extracts some information, explained in the Basics section, based on the tracked data.


The list of accounts:

- @alikarimi_ak8
- @elonmusk
- @BarackObama
- @taylorlorenz
- @cathiedwood
- @ylecun


## Requirements

### Basics

- For each account extract all the conversation threads. Data for each tweet
should at least include name of the author, time of the tweet and
text of the tweet. Feel free to include anything else you think is useful.
- For each account figure out a set of active audiences. A good heuristic for an active
audience is the set of accounts which reply to tweets of a given account.
- Sentiment:
Use any method you think best to assign sentiment scores to each of the following:
    - figure out how positive or negative each thread is.
    - figure out how positive or negative audience of (e.g. replies to) each thread is.

**Important:** The system should keep running and the information should remain up to date even after you have submitted your entry.

## Delivery

The delivery has two parts:

**API Endpoints:**

- Make a REST API with the following endpoints:
    - /accounts: return a json list of all tracked accounts.
    - /tweets/<twitter-handle> : return a json of the user's conversation threads since start.
    - /audience/<twitter-handle> : return a json of information about the audience for a user's account.
    - /sentiment/<twitter-handle> : return a json about the sentiment information of an account (e.g. thread level, audience level)

**Source Code:**

The source code behind the endpoints should be posted on Github or another code hosting website so we could review it.

To submit send an email to **competition@310.ai** before **March 11th**. The email should contain:

- a link to your API endpoint.
- a link to you source code.
- a link to the website if have made it for the extra score

    
### Extra Score

- Figure out a sentiment metric that measures how positive or negative each account is.
- Use AI to come up with a two paragraph summary description of the account.
- Make a website that presents the data extracted in a simple and clean way.

### Followup & Questions in Discord

[https://discord.gg/2Kf9h9JA](https://discord.gg/2Kf9h9JA)
