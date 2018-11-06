# Microservice architectures have many properties of complex systems:
## Systems Theory
-> it contains of elements (services, load balancer, proxy, message broker, database, ..) and its relations (HTTP calls, messages, persistence, ..)
### 1.) Numerosity
-> different levels and hierachy: hardware, os, platform, application, binary, network, ...
### 2.) Nonlinearity
- non linearity would mean the same input does not necessarily guarantee the same output or even in the same scale
-> classical testing (I->O?) on the system level is not ideal. this presents to us as flakiness, long runtimes, costly reproducibility, apparently non deterministic outcomes
### 3.) Connectivity
-> high connectivity appears as networks: highly interconnected services, distributed
### 4.) Adaptation
-> autonomy + adaptation shapes macro scale: an individual service can have a major effect on the whole business outcome





## statistical correctness:
statistically a feature is behaving as intended
statistically the test is green
when monitoring you can give a statistical statement whether a feature is working

this is in contrast to the classical test, where you perform the actual execution of the feature and verify its intended behaviour at that particular setting/time.

which one is better? -> the statistical verification is better as it is a generic check on the functionality
because...
• there is no guarantee that the system will behave the same way again as it did in that one particular case
  • this is regarding change in configuration, data, time, resources, application
• it is only a snapshot and relies on the missinterpretation that the system is static and behaves deterministically at all times (complicated vs complex system)

---

### pets vs cattle

what are pets (as in pets vs cattle) and why do they exist?
pets are systems that permanently being adapted for stability, functionality, requirements reasons. it is the natural reaction to a complex systems behaviour. if something is not working properly, you adapt it to fulfil your needs: monitoring, responding, adapting, learning. this is the definition of resilience.

---

### black box system testing

viewing the system as a black box is not reasonable anymore. we have to know of and understand the inner workings to understand what the system does.
-> the practice of black box system testing is not valid anymore

---

### cynefin

often we are dealing with a system being on the edge of a complicated to a complex system. the more moving and adaptive and layered parts there are, the more we shift towards a complex system. (cynefin)

---

### questions

_Does continuous deployment count as an adaptive system?_

_What does the looming fact that microservices are a complex system entail?_