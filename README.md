# ElecHubWeb
IoT smart metre and electric stations monitor app


## Deploy to Azure web application
Go to [Azure Portal](https://portal.azure.com) to create your own Azure web app service. Then do the following setting:

* Go to `Application settings`, add key/value pairs `ConnectionString` and `ConsumerGroup` to `App settings` slot.
* Go to `Deployment options`, set `Local git repository` to deploy your web app.
* Go to `Deployment credentials`, set your deploy username and password.
* In the `Overview` page, note the `Git clone url`.
* Push the repo's code to the git repo url you note in last step.
* After the push and deploy finished, you can view the page to see the real-time data chart.

*NB : The web application should be created with linux as enviroment*

## Local deploy
* Open a console and set the following environment variable:
  * `export ConnectionString=<your connection string>`
  * `export ConsumerGroup=<your consumer group name>`
* Open ./public/javascripts/index.js, and change the code around line 69

    from
    ```js
    var ws = new WebSocket('wss://' + location.host);
    ```
    to
    ```js
    var ws = new WebSocket('ws://' + location.host);
    ```
* `npm install`
* `npm start`
