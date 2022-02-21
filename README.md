# restarter for DiscordSpeechToText Bot

## Due to the limitations of the Heroku API, a deployed app cannot interact with it's own hosting or deployment through the API. To include a way for a command to trigger a redeployment on a deployed Heroku app, this web service will trigger the reset of a different deployed app.


Deploy your code to Heroku
If you don't have a linux server/machine then you can use Heroku for hosting your bot 24/7 and it's free. Under "Resources" tab, use the "web" dyno type, and not the "worker" one. You will need to configure the "Config Vars" under "Settings" tab, these are the environment variables from the settings section below.

Create and login to your Heroku account (https://heroku.com/). It is free and no credit card required.
Make a new app, give it some name and set your region:
The easiest way to deploy the code is by forking the Github repository, a copy of the repo will be added to your Github account which you can use. Alternatively you can use Heroku CLI tools, but that's beyond our scope and for advanced users only.
Once forked, select GitHub as deployment method and connect the DiscordEarsBot repository.
Scroll down and click on "deploy branch". It might take a minute or two until it's done.
Now we need to provide the config vars, under the "Settings" menu. Here you have to provide the necessary key-value pairs.
Enter the TARGETPATH variable with a value of "/apps/{deployed-app-name}/dynos"
Go to the Resources tab and you should see two Free Dynos: a web and worker type. Enable the web dyno.
Now you're ready and set. You can see the output logs from the bot by clicking on "more" and then "view logs".

To test this, send a !restart command in discord, and you should see the events occur on the logs of both the transcriber bot, and this restarter.
