### 3 steps are needed:
- [Twitter Developer Account](#)
- [Configuration](#prerequisites)
- [Set Welcome Message](#setup)

## Create Twitter Developer Account & Apply for Elevated Access Levels

NB: Make sure to log out of all twitter accounts except for the account in question.

1) Go to: https://developer.twitter.com/en/portal/petition/essential/basic-info
Follow the prompts, it will send an OTP to your email and may ask to verify your phone number if not already done.

2) Make an app - it should prompt you this immediately after authenticating. Call it anything - it doesn't matter.

3) Make a note of the Bearer Token for later.

4) In the developer portal, navigate to Projects & Apps > Project 1 > Your App
4.1) Scroll down to "User authentication settings" > click "Edit"
4.2) Enable OAuth 1.0a, scroll down further
4.3) OAUTH 1.0A SETTINGS > enable "Read and write and Direct message"
(the next 2 steps are mandatory even though we don't need it)
4.4) Callback URI / Redirect URL > set to http(s)://<yourdomain>:<port>/login/callback
e.g. mine was http://jasbanza.dedicated.co.za:8080/login/callback
4.5) Website URL > set to "https://example.com"
4.6) Save

5) Left navigation pane again > Projects & Apps > Project 1
5.1) Below access section, scroll down to "Do you need Elevated access for your Project?" > Apply
5.2) What's your current coding skill level? > you can decide (lol)
5.3) Next

6) How will you use the Twitter API or Twitter Data?
6.1) In English, please describe how you plan to use Twitter data and/or APIs:
- We would like to set a default welcome message in our DMs since our official Twitter account's inbox is unmanned, and we would like to direct our users to our official support website, which is manned 24/7.
6.2) Are you planning to analyze Twitter data? - NO
6.3) Will your App use Tweet, Retweet, Like, Follow, or Direct Message functionality? - YES
6.4) Please describe your planned use of these features. 
- We want to set a default welcome message in our DMs in order to direct users to our official support website.
6.5) Do you plan to display Tweets or aggregate data about Twitter content outside Twitter? - NO
6.6) Will your product, service, or analysis make Twitter content or derived information available to a government entity? - NO

7) Next 
8) Ts&Cs Checkbox & Submit

===============================

SETTING THE WELCOME MESSAGE IN DMs

In your terminal:

1) execute this, replacing with your <BEARER_TOKEN> 
... command 1 here
2) Copy the returned message id
... command 2 here 

done!




==============================

WELCOME MESSAGES:

Welcome to Osmosis Support!

For assistance, please visit:
https://support.osmosis.zone/
