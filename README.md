# [Twitter Watch](https://equatorial-sternum-35b.notion.site/Twitter-Watch-052f5ae4fd1d440ba7a590af040065e4)
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
    
    
    ---------------------------------------------------------------------------------------------

To track tweets and replies from specific Twitter accounts, you can use the Twitter API along with the Tweepy library in Python. Here's an overview of the process:

1. Set up a Twitter Developer account: First, you'll need to create a Twitter Developer account and create an application to obtain API keys and access tokens. You can sign up for a developer account at https://developer.twitter.com/.

2. Install Tweepy library: Use pip, the package installer for Python, to install the Tweepy library. You can execute the following command in your terminal or command prompt:
   ```
   pip install tweepy
   ```

3. Authenticate with Twitter API: Use the API keys and access tokens obtained from your Twitter Developer account to authenticate with the Twitter API using Tweepy. Here's an example of how to authenticate:
   ```python
   import tweepy

   consumer_key = 'YOUR_CONSUMER_KEY'
   consumer_secret = 'YOUR_CONSUMER_SECRET'
   access_token = 'YOUR_ACCESS_TOKEN'
   access_token_secret = 'YOUR_ACCESS_TOKEN_SECRET'

   auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
   auth.set_access_token(access_token, access_token_secret)

   api = tweepy.API(auth)
   ```

4. Track tweets and replies: Once authenticated, you can use the `api` object to track tweets and replies from specific accounts. Tweepy provides a `StreamListener` class that allows you to define custom behavior for handling incoming tweets. Here's an example of how to track tweets and replies from three accounts:
   ```python
   class MyStreamListener(tweepy.StreamListener):
       def on_status(self, status):
           # Process the incoming tweet
           print(status.text)

   # Create an instance of the StreamListener
   stream_listener = MyStreamListener()

   # Start tracking tweets and replies
   stream = tweepy.Stream(auth=api.auth, listener=stream_listener)
   accounts = ['account1', 'account2', 'account3']  # Replace with the desired account usernames
   stream.filter(follow=[api.get_user(screen_name).id_str for screen_name in accounts], is_async=True)
   ```

   In the `on_status` method of the `StreamListener`, you can define your custom logic to extract the desired information from the incoming tweets. You can access various attributes of the `status` object, such as `status.text`, `status.user.screen_name`, `status.created_at`, etc., to extract relevant information.

Remember to replace the placeholder values for the API keys, access tokens, and account usernames with your own information.

Please note that building a complete system with data storage, analysis, and a web interface goes beyond the scope of a simple guide. You would need to set up a database to store the extracted information, design data models, and develop a web application to display the tracked data. For a full-fledged system, you may consider using frameworks like Django or Flask for web development.

Additionally, Twitter has rate limits on API calls, so make sure to review their API documentation and handle rate limit restrictions accordingly.

If you have any specific questions or need further assistance, feel free to ask.
