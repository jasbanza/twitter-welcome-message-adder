# twitter-welcome-message-adder

Since Twitter killed business.twitter.com, this is a way to set a welcome message for your Business Twitter account using their API with OAuth.
> If you want to use CLI instead, your best option is to use [TWURL](https://developer.twitter.com/en/docs/tutorials/using-twurl), twitter's cURL wrapper which handles OAuth, but I don't want to be forced to install Ruby just for this...


#### Prerequisites:
   - Install Node.js: [Download here](https://nodejs.dev/en/download/)
   - Guide: [Create Twitter Developer Account & Apply for Elevated Access Levels](#create-twitter-developer-account--apply-for-elevated-access-levels)

#### Installation:
   - git clone this repo
   - install dependencies:
      ```bash
      npm install
      ```
   - Guide: [Environment Configuration](#environment-configuration)

### Usage
   - Start the server:
      ```bash
      node index
      ```
      - Open the webpage & OAuth your Twitter account. 
         > This will ONLY work for the account you have set up (consumer key)!
      - Enter a welcome message & hit save.
      - Click remove to remove it.
         > if you try remove without having one saved, the app will crash. Just start again with "node index"


## Create Twitter Developer Account & Apply for Elevated Access Levels

> ***NB: Make sure to log out of all twitter accounts except for the account in question.***

1) Go to: https://developer.twitter.com/en/portal/petition/essential/basic-info
   * Follow the prompts, it will send an OTP to your email and may ask to verify your phone number if not already done.

2) Make an app - it should prompt you this immediately after authenticating. Call it anything - it doesn't matter.
   > Don't worry about saving the bearer token or API keys, we don't need this!
3) In the developer portal, navigate to Projects & Apps > Your Project > Your App
<img width="1349" alt="image" src="https://user-images.githubusercontent.com/1925470/190052242-f4d749fd-1700-4d15-8dfd-56b671431146.png">

   - Scroll down to **"User authentication settings"** > click ***"Edit"***
   - Enable OAuth 1.0a, scroll down further
   - **OAUTH 1.0A SETTINGS** 
      > enable *"Read and write and Direct message"*
   - **Type of App**
      > set to  *Web App, Automated App or Bot (Confidential client)*
   - **Callback URI / Redirect URL** > set to http(s)://server:port/login/callback
      > e.g. http://mysite.com:3000/login/callback
      > 
      > or http://127.0.0.1:3000/login/callback (if you want to run locally)
   - **Website URL** 
      > just set to *"https://example.com"*
   - ***Save***
Yours should look like this:
<img width="333" alt="image" src="https://user-images.githubusercontent.com/1925470/190052499-f2c98b82-a60c-4c1e-ba1f-8419d5ce4531.png">


4) Left navigation pane again > Projects & Apps > Project 1
   - Below access section, scroll down to "Do you need Elevated access for your Project?" > Apply
   - What's your current coding skill level? > you can decide (lol)
   - ***Next***

5) Complete form: "How will you use the Twitter API or Twitter Data?"
   - *In English, please describe how you plan to use Twitter data and/or APIs:*
      > We would like to set a default welcome message in our DMs since our official Twitter account's inbox is unmanned, and we would like to direct our users to our official support website, which is manned 24/7.
   - *Are you planning to analyze Twitter data?*
      > NO
   - *Will your App use Tweet, Retweet, Like, Follow, or Direct Message functionality?*
      > YES
   - *Please describe your planned use of these features.*
      > We want to set a default welcome message in our DMs in order to direct users to our official support website.
   - *Do you plan to display Tweets or aggregate data about Twitter content outside Twitter?*
      > NO
   - *Will your product, service, or analysis make Twitter content or derived information available to a government entity?*
      > NO
   - Click ***Next***
6) Check the Ts&Cs Checkbox & ***Submit***

***NB: It's important to follow up on any emails, they will most likely ask the same questions, just reiterate that we will only be requiring these permissions in order to set the welcome message***

## Environment Configuration
- copy the config.json.template > config.json and edit accordingly:
```json
{
  "PORT": 3000,
  "BASE_URL": "http://127.0.0.1:3000/login/callback",
  "TWITTER_CONSUMER_KEY": "your-consumer-api-key",
  "TWITTER_CONSUMER_SECRET": "your-consumer-secret"
}
```
- If you run this locally, you don't need to change anything except the key and secret.
- You can get the Key and Secret here:
<img width="1566" alt="image" src="https://user-images.githubusercontent.com/1925470/190053552-22b9a5ce-3e53-4451-a7c8-daa77a15b9c1.png">
