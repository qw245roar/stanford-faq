Simple instruction to participate to ROAR with `heroku`:

These steps will package and deploy your local setup on the `heroku` platform (by way a Docker image).

## Create a `heroku` account:

https://signup.heroku.com

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

## To get your URL

```sh
heroku info -a $APP_NAME
```
