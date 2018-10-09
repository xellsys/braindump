Monitoring should cover the what and the why: what's broken and give an indication as to why
--------

MDD
Metric Driven Development

Acceptance Criteria
-> Acceptance Tests
-> Acceptance Metrics, Alerts, Monitoring?
Define Metrics or Alerts which cover your acceptance criteria before hand. Implement the feature and the metric as well as the graph and the alert!


"We don't have to be as cautious as before if we can rely on our system to be transparent regarding its success."

- as cautious
Meaning we don't need as many preventive measures as before
- as before
Meaning the time before transparent production systems
- systems success
The systems success is our business success if we built the right system (that is also a field where monitoring is aiding). Meaning our monitoring must indicate if our business success is at risk or failing.

Why is that the case?
Before we had to invest heavily into preventive measures as every failure to production could have had devastating effects since we might not have noticed fast or might not have boiled it down to the "root cause" fast. In the meantime we were effectively losing money.

preventive testing:
- everything you do, before a change is impacting your end users
- what do you do here?
  - risk analysis, trying to predict your users actions AND expectations
  - happy case -> must definitely work exemplarily
  - negative case -> should also work exemplarily
  - exception cases -> too many to cover and/or predict
reactive testing:
- everything you do, after a change is impacting your end users
- watch your users
- monitor your system
- react accordingly

Move tests from preventive to reactive:
- all exception cases
- corner cases, if they are not super business critical
- performance testing by leveraging advanced deployment strategies
- future acceptance tests
What should you not move to reactive?
- unit tests, since they are cheap, fast and IMO their main benefit is supporting development in that codebase
- business critical use cases, should be verified with every commit
- heavily used happy cases, try to cover >90% of your productively executed use cases (a value which you can find out through monitoring)
- technical integration tests, they are not as cheap as unit tests but still fairly cheap and in the time of microservices and distributed systems very critical


What do you achieve?
Speed: because on the testing timeline you shift your release to the left


