## Context Awareness

The more I have been talking to people and thinking about it and engaging deeper into the "three pillars (or pipes what I recently heard) of Observability", I feel like the most important thing is context.
What is the simplest way to describe context of any of those pipes? It's key value pairs, fields, tags, labels, cardinalities, dimensions, attributes or any other name.

With prometheus, dimensional metrics really took off: https://prometheus.io/docs/concepts/data_model/
Also compare open census: https://opencensus.io/tag/
```
[metric_name: [key1: value1, key2: value2, ..], metric_value: value, timestamp: ...]
```

With logs, structure and fields is a good practice for a long time: https://stackify.com/what-is-structured-logging-and-why-developers-need-it/
```
{
    "message" : "UserA logged in",
    "user" : "user_a",
    "timestamp" : "...",
    "node" : "node-1a",
    ...
}
```

With traces, this is also possible: https://opencensus.io/tracing/span/time_events/annotation/
```
[traceId: <traceId>,
spanId: <spanId>,
attributes: [
    node: node-1a,
    ...
    ]
]
```

Basically, we do the same thing in three areas to describe the context of the "thing" (metric, log, trace) we write.
It allows us to aggregate, associate, correlate and perform other powerful data analysis on it.

#### Idea

Within an application, any of the above pipes should always receive the current context. 
We should not have to set MDC every time we want to write a log and then set the same (or probably rather something different, as humans are bad at doing the same thing identically multiple times) labels for our metric and then again the same annotations for our traces.
Ideally we would define context _once_ and have all three pillars receive and integrate that context.
This will simplify consistency across the pillars and allow cross pillar association.

#### Caveats
We are not able to cover all relevant context keys within our application (language, productive code).
Especially with containerization and missing node awareness etc some keys can simply not be resolved within our application (eg the node it's running on).
Most (especially domain specific) context info is only available to the app (language specific) though.
So for now it looks impossible have one place where we define our context fully.


#### Inside the service
We need to be able to enrich context information within the service centrally (across the pipes). 
-> this could result in language specific libraries following open census principles as well as enriching logging fields.
 
#### Outside the service
Service meshes promise "observability", but that is a promise they cannot keep.
O11y is so much more than what a service mesh can access.
A lot of domain specific context information is only available to the thread within our service.
Analysing packages (HTTP or others) is not enough - and probably not effective anyway.
-> service meshes are already powerful when it comes to this context info (infrastructure etc)

#### Combination
Service meshes could intercept all the pipes, pick up all the context information from within the service and enrich it with the information from outside the service.
