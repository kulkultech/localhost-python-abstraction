# Bot chat

This application demonstrates the use of Markov Chains [theory](https://en.wikipedia.org/wiki/Markov_chain) by building a chat-bot based on tweets.

## Requirements and dependencies

- [Python3](https://www.python.org/) - We recommend using virtual environments. They will help on the creation of isolated environments so different python versions can run on the same machine. Check more about virtual environments [here](https://docs.python.org/3/library/venv.html). (Needs to be installed manually)
- [Pip](https://pip.pypa.io/en/latest/installing/) - The python package manager. (Needs to be installed manually)
- [Flask](http://flask.pocoo.org/) - A simple and flexible Python Web Framework that provides with tools, libraries and technologies to build a web application. (Installed by pip)
- [Flask-SocketIO](https://flask-socketio.readthedocs.io) - Flask-SocketIO gives Flask applications access to low latency bi-directional communications between the clients and the server. (Installed by pip)
- [Markovify](https://github.com/jsvine/markovify) -A simple, extensible Markov chain generator. (Installed by pip)
- [Tweepy](http://www.tweepy.org/) - Twitter for Python! (Installed by pip)
- [dotenv](https://github.com/theskumar/python-dotenv) - Get and set values in your .env file in local and production servers. (Installed by pip)
- [Microsoft Content Moderator](https://azure.microsoft.com/en-us/services/cognitive-services/content-moderator/) - Machine-assisted content moderation APIs and human review tool for images, text, and videos


## Clone the project

Use the command below:

```sh
git clone https://github.com/MLH/localhost-python-ii.git
```


## Set Up Environment variables

To quickly set up environment variables, make a copy of the `.env.example` and rename it to `.env`. Then make sure to modify it following the instructions below.

### Tweets Source

There are two different fetchers for tweets. One of them is based on Tweepy and uses the Twitter API. To use it set this env var:

```TWITTER_FETCHER=tweepy```

The second one is a web scrapper and fetches tweets through twitter html pages. To usee it set this env var:

```TWITTER_FETCHER=scraper```


### Microsoft Content Moderator API Keys
We need an API key to use this content moderator. Just click on get started and create your free account [here](https://contentmoderator.cognitive.microsoft.com/). You will then have access to a key that you can use in the variable:

```
OCP_APIM_SUBSCRIPTION_KEY=
```

### Twitter API Keys
We need to setup the twitter API keys to be able to fetch data from Twitter's API. Follow [this guide](https://developer.twitter.com/en/docs/basics/authentication/guides/access-tokens.html) to get your keys.

After going through the tutorial, you should have the following information:

```
CONSUMER_KEY= 
CONSUMER_SECRET= 
ACCESS_TOKEN=
ACCESS_TOKEN_SECRET=
```

You can also tweak `NUM_TWEETS_TO_GRAB` to get more or less data to feed the markov chain.


## Install dependencies

The next step is to install the dependencies used by the project. Run the following command:

```sh
pip install -r requirements.txt
```

## Executing the application

After having all the dependencies installed, you only need to execute the main application file. In this case it will be the file "main.py"

```
FLASK_APP=main.py FLASK_DEBUG=1 flask run
```

Then open [http://localhost:5000/](http://localhost:5000/) to see the application.
