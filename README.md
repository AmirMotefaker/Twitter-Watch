# Twitter-Watch
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
