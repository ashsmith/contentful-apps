# Contentful Backend Demo APP

A demo App that will prefill certain values when an entry is created.

The purpose of this demo is to show how backend Apps can be setup and used.


## Prerequisites
This demo requires node.js, yarn, and some way of making the running server
available to contentful. For local development it is easiest to use
[ngrok](https://ngrok.com/)

## Setup instructions

1. Run
shell```
ngrok http 3543
```

Take note of the url provided by NGROK

2. Update `.env` with
shell```
ORG_ID= # Your contentful organisation id
SPACE_ID= # Your contentful spaece id
ENVIRONMENT_ID= # Your contentul enviornment name
APP_LOCATION=the ngrok URL from step 1
```

### Warning!
The setup for this demo will make install an app, and create a content type in
whatever orgnization/space/environment you use. We highly recommend that you do
not use your production environment for testing this App.

3. Add a valid CMA token to the environment variables, you can obtain this token
   from the contentful web app

```shell
export CMA_TOKEN=${a valid CMA token}
```

4. create key pair
```shell
# Creates a local key pair
./tools/makekeys
```

5. Run the app's setup script

```shell
yarn setup
```
This step will 
* Create an app definition in your contentful organization
* Install the app to the space and enviornment you specified
* Setup a webhook that listens for new entries


6. Run the backend App!
```shell
yarn start
```

7. Test it by going to the contentful web app and creating a new entry of the
   `Example` content type. You should see a prefilled title field!



## TODOS

put the api path in config