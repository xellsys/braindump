# Just in time Microservices?

Serverless Applications are Event based. The upside is that they only take up resources (cost money) when they are required.

Microservices always run in a specific scaling by default although there might be no need for a particular functionality for hours or even days.

A hybrid could be an extremely responsive Microservice architecture which allows (most of) its services to be instantiated to zero. Whenever their functionality is required they will be started up just in time. 
The cold start is a big downside for this approach. 
Depending on the use case this might not be an issue though. 

If you have a cabinet (bounded context of multiple Microservices) which’s functionality is only required rarely and when it is, not necessarily immediately, you can have great gains here. 
Set up a gatekeeper service (adapter) that is up all the time and only accepts external events. Those events could be migrated or simply put into a message queue (a broker is up anyway). Based on your business case you could spin up the rest of the cabinet whenever there is at least a number of events in the message queue (could be one) or in a regular interval or based on a different rule set. 
By setting up metrics for incoming external events, spin up time and duration of working off the queued events you can optimize your rule set for the just in time orchestration. 

However to really benefit from this approach you should have an elastic kubernetes environment in place.

To find out if this is a promising option for your own case you could instrument each Microservice with the event received metric. Monitoring and analyzing those time series will give you a good indication whether you can optimize. 

_Does that behavior exist in serverless architectures? To allow a build up of a queue before spinning up an instance of a function?_