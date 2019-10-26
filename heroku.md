Simple instruction to participate to ROAR with `heroku`:

These steps will package and deploy your local setup on the `heroku` platform (by way a Docker image).

## Create a `heroku` account:

Follow the instructions from this link:

[https://signup.heroku.com](https://signup.heroku.com)

The free tier give you 550 hours a month, extended to 1000 hours if you enter your credit card information -- but won't be charged if you don't go over the free tier --.

It's enough to run a your BOT for free!

And install the `heroku` cli:

On macOS:

```sh
brew tap heroku/brew && brew install heroku
```

For other platforms, follow instructions from [https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)

And create an application with a unique name (for example, `joe-awesome-bot`) and set the environment variable `APP_NAME` to it -- or replace `$APP_NAME` in the next lines with your application name:

```sh
heroku login
heroku create $APP_NAME
```

Your application will be running a Jupyter Lab instance that you will use to connect to the ROAR platform.

## Push your Bot to heroku

From within the ROAR directory (`bot-tutorial-master` if you followed the instructions from *TODO*)

```sh
heroku container:login
heroku container:push web -a $APP_NAME 
```

## Deploy your application to the Cloud

```sh
heroku container:release web -a $APP_NAME
```

## To get the URL to access your Jupyter Lab, in `heroku`, run:

```sh
heroku info -a $APP_NAME
```

You can also get the status of your application (up, crashed, iddle):

```sh
heroku ps -a
```

## Log in into Jupyter with your password

Hopefully you followed the instructions in the Welcome notebook to reset your password. Enter it to get access to your ROAR Notebooks.

## Connect your bot!

The steps to participate from the Cloud are the same as from your laptop!

