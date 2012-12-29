# Service Efficiency Chart

The service efficiency chart highlights how time is allocated across your app's HTTP requests. Using this information, you can quickly determine if you app is correctly provisioned or if your app's performance is degrading customer experience.

There are 3 stages of an HTTP request on Heroku:

1. Wait
2. Connect
3. Service

With 2 possible outcomes:

1. Good response (e.g. 20x, 30x)
2. Bad response (e.g. 40x, 50x)

Service efficiency charts give you an immediate understanding of how customers experience your app. For example, say that you have an endpoint in your application that returns an error; furthermore, say that the error is caused by a slow database query. In this scenario, you are clogging up your capacity with a worthless request. This means that customers have to wait a long time to receive a bad experience, and customers who can potentially have a good experience are stuck behind the bad requests.

Here is an example:

![img](http://f.cl.ly/items/0E361Z3L0V0o340n300F/service-efficiency-page.png)


There are a couple of things to point out:

* Each bucket in the chart contains throughput with relative slope.
* We can see that errors increase with throughput until 21:03.
* The current minute, 21:03 contains more throughput and less errors.
