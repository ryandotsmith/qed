# Timecards

The timecard highlights how time is allocated across your app's HTTP requests. Using this information, you can quickly determine if you app is correctly provisioned and/or if your app's performance is degrading customer experience.

There are 3 stages of an HTTP request on Heroku:

1. Wait
2. Connect
3. Service

With 2 possible outcomes:

1. Good response (e.g. 200)
2. Bad response (e.g. 404, 500)

Timecards give you an immediate understanding of how customers experience your app. For example, say that you have an endpoint in your application that returns an error. Furthermore, say that the error is caused by a slow database query. In this scenario, you are clogging up your capacity with a worthless request. This means that customers have to wait a long time to receive a bad experience, and customers who can potentially have a good experience are stuck behind the bad requests.
