# Monolith first?

Martin Fowler presents four popular approaches to this strategy:
> Source: https://martinfowler.com/bliki/MonolithFirst.html

#### Modular Monolith:
* carefully design the monolith upfront to be modular
* implement predetermined breaking points
* separate data structures similarly careful

#### Monolith and breaking off Microservices:
* start with a "regular" monolith
* shift functionality from the monolith as a microservice when required

#### Monolith and replacing by Microservices:
* start with a "regular" monolith
* build it as a "sacrificial architecture"
* replace the monolith with a microservice architecture as a whole

#### "Macroservices" first:
* start off with very few large services
* split them up into finer granularity (microservices) when required

## Inquiry:
In my opinion there are quite a few considerations to make beforehand. 
Depending on a well informed summary regarding the questions below you can answer: 
whether a microservice architecture is a valid target architecture at all,
whether you should to apply one of the monolith first approaches or
whether you want to go straight for microservices.

**what to inquire "beforehand"?**

1. how much experience does your team have in designing, implementing and operating microservices?
1. how well do you know the business domain?
1. how well do you know the functional requirements?
1. how well do you know the non-functional requirements?
1. what general architecture will your application have?
1. how high is the pressure of time to market for your business cases?
1. how large is your team to start off?
1. how much will your team grow?
 

**effect of inquiry**

1. This one is fairly easy. if your team has no or little experience with microservices, you should definitely avoid going straight for a microservice architecture.
1. The better you know the domain, the better your design decisions will be. This is heavily affecting your architecture.
1. If your future functional requirements are supposedly well known, you will still run into many unknowns. the more you are sure you know about this the better you can design your architecture.
1. Non functional requirements are often even less considered upfront unless there is some core requirement often in the center of design. This is also heavily affecting your architecture decisions.
1. This is not to be misunderstood. If you claim you know what your architecture is going to look like in a later state you are not doing a great job. Although this is often something management likes to hear, in reality you cannot and must not present a target architecture in advance. However, you can very often tell whether the system is going to be CRUD, streaming/pipelining, event based or follow another large operational pattern.
1. The higher the pressure for time to market, the more realistic is to start off with a monlith first.
1. When starting off with a small team (<6 pax) it is most often not ideal to set up multiple services from the get go. On the other hand, once you can split up teams into 3+ people you might want to consider assigning each of those teams a service.
1. If you known from the business perspective that the number of team members will not grow, microservices can be an expensive investment overall. Only a highly qualified team of less than 10 people will successfully handle a larger (15+) microservice architecture.

**bottom line**

Based on the previous inquiry it might appear that microservices are rarely a good fit.
And as a matter of fact, you should not go for microservices if you don't have some very good reasons to do so (hype is not one of those).
