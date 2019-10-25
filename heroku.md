Simple instruction to participate to ROAR with `heroku`:

These steps will package and deploy your local setup on the `heroku` platform (by way a Docker image).

## Create a `heroku` account:

Follow the instructions from this link:

[https://signup.heroku.com](https://signup.heroku.com)

The free tier give you 550 hours a month, extended to 1000 hours if you enter your credit card information: enough to run a your BOT for free.

And install the `heroku` cli:

On macOS:

```sh
brew tap heroku/brew && brew install heroku
```

And create your app with name referred as `APP_NAME` in the rest of the instructions:

```sh
heroku login
heroku create $APP_NAME
```

## Push your Bot to heroku

Obtain the SDK and `cd` into it.

```sh
heroku container:login
heroku container:push web -a $APP_NAME 
```

## Deploy your app

```sh
heroku container:release web -a $APP_NAME
```

## To get the URL to access your Jupyter Lab in `heroku`, run:

```sh
heroku info -a $APP_NAME
```

## Log in into Jupyter with your password

Hopefully you followed the instructions in the Welcome notebook to reset your password.

## Connect your bot!

The steps to participate from the Cloud are the same as from your laptop!

