# Sample GroupMe Python Bot using MeBots
**Python** | [**JavaScript**](https://github.com/ErikBoesen/mebots-example-javascript) | [**Ruby**](https://github.com/ErikBoesen/mebots-example-ruby)

## Introduction

A simple GroupMe bot that reacts to a user saying "ping" in a group. Designed to demonstrate the MeBots API and serve as a template for other bots.

Please see [this tutorial](https://github.com/ErikBoesen/bot-tutorial-python) for to get general intuition on how a Python bot works in GroupMe, but note that the approach for running a MeBots bot will be quite different.

It is recommended to run this example bot, and other bots, on AWS Lambda or a similar serverless host, using the `serverless` package. This approach is convenient for GroupMe bots because they only run to generate a response once in a while, so most bots can be hosted for free.


## Prerequisites
Papaya is meant to run on AWS Lambda using the Serverless framework.

To install serverless on your local machine:
```sh
npm install -g serverless
```

## Deployment
Install `pip` dependencies locally in the `vendor` directory:
```sh
pip install -r requirements.txt -t vendor
```

Deploy using serverless:
```sh
serverless deploy
```

Configure your OpenAI key as an environment variable:
```sh
aws lambda update-function-configuration --function-name papaya-dev-receive --environment "Variables={OPENAI_API_KEY=abcdef1234567890}"
```

The bot should now be ready to receive messages!

## Logs
To view the logs:
```sh
serverless logs -f receive
```

## Author
[Erik Boesen](https://github.com/ErikBoesen)
