Divide and conquer
Limit test scope 
Ease analysis
Ease debugging 
Enable local execution
Reduce setup complexity
Reduce start up time

Maximize dev prod parity
Find production bugs earlier / before release

Consumer driven contract testing
Focus on integration and contract

Mocking and test doubles
Highly important
Know the different options

Layers
Unit, component, service, service integration, cabinet, system
Always introduce a test on the lowest level possible

Generally keep the number of system tests low
High complexity of system makes them extremely hard to analyze
Very costly to maintain
High runtime
Relatively slow feedback
Increases time to market
Highest occurrence of flakiness

Responsibility in the whole development team
Not only testers

Know your setup
Know your technologies
Know your infrastructure
Know your operations

Extremely important to know how the system is being operated

Take scaling into consideration 
Take asynchronous communication into consideration
Take different protocols into consideration
Take load balancing into consideration
Take circuit breaker into consideration

Handle a service as a black box
Often different teams develop different services
Do not make assumptions regarding implementations

Handle test data smartly
Generate test data according to the layer
Use static data only when necessary
Write every test independent from others
Every test sets up its own prerequisites
A test run has a setup and a cleanup phase
If you can create your test setup from scratch with every run and destroy it afterwards
Abstract test data creation
Reduce definition of test data to what is required for that particular test

Parallelize tests in the pipeline
Provide fast feedback
Trust your pipeline and tests
Reduce manual tests to exploratory tests and those which are economically unfeasible to automate

Monitoring is key
It is an extremely useful testing tool
Learn to understand your monitoring output and metrics
Get a feel for how the system behaves in certain situations and under certain load
Tracing is the next step
 
Logging is important for testing
Differentiate between technical and business logs
Avoid testing soley against log statements
Do test your log output though

Test your infrastructure
Automate it
Add it to your pipeline
Dev prod parity covers a lot of this implicitly
However, be aware of the overlap

Know the difference between a business focused test and a technical focused test
Apply the knowledge accordingly
Test different focus on different levels

Try to ignore the fact that it's a MS infrastructure in the background when testing the whole system
This does not apply to all tests but it allows for a different ankle towards test specification
Effectively handle the system as a black box - as if it could also be a monolith or anything else
Focus on the business value which is to be acclaimed

Take leverage of the domain focused architecture
Write your tests in bounded context of the domain
Focus on business value for those tests

Implement performance tests
Run them regularly, ideally on every change
Sync them with your monitoring output
they don't have to be super sophisticated
Simple load tests will provide value by offering a performance graph over time
Monitoring adds to this

Beware of typical microservice pitfalls
Asynchronous calls
Payload size
Memory consumption
Distributed hosts
Multi instances
Multiple services on one machine affecting each other's performance
Concurrency issues
Protocol diversity
Implementation diversity
Technology diversity
Language diversity
Separate responsibilities across different teams
Configuration complexity and impact
Separate state, no central DB, no central truth
Statelessness

use this to your advantage in testing:
MS isolate responsibilities
MS are independently deployable
MS have one or reduced functionalities