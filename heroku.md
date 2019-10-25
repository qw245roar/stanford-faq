Simple instruction to participate to ROAR with `heroku`:

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

## TODO: Make it easier: setup password for your Jupyter Notebook

```python
In [1]: from notebook.auth import passwd
In [2]: passwd()
```
and update your `notebook_config.py` with the password hash.

TODO: only one Dockerfile, but for now, make sure your CMD is:
```docker
CMD [ "jupyter-lab", "--config=notebook_config.py"]
```

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
