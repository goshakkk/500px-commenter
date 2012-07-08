# 500px comment poster

Posts comments and likes on "fresh today" photos from your name.
(Primarily used to enlarge "affection".)

### Requirements

* Ruby 1.9

### Required configuration

The following environment variables are required for app to work
properly:

* `CONSUMER_KEY` & `CONSUMER_SECRET` for your app (need to register an
  app on [500px dev center](http://500px.com/settings/applications?from=developers)
* `USERNAME` & `PASSWORD` of the account you want comments to be posted
  from.

### How to run

Once env vars are set, you can just run

    rake

### Heroku deployment

Instead of running locally, you can deploy the app to heroku and set
commenting to be triggered once a hour/day/etc. 

First, add env vars to heroku:

    heroku config:add CONSUMER_KEY=consumer_key
CONSUMER_SECRET=consumer_secret USERNAME=username PASSWORD=password

Then, setup a scheduled task: add "Scheduler" heroku addon for the app,
and create a job with task being `rake` and needed requency.