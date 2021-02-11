# docker-compose test

New command for the docker-compose executable which is targeted at executing tests against a set of docker containers.

## Use cases
* run single container tests
* run integration tests between multiple containers

## Idea
Simple definition of a services setup (identical to docker-compose) with additional configuration for test execution against that setup.
Focus is simplicitly, readability and stability.

## Core features
* simple:       single command to execute
* reproducible: wrapper for proper workflow
* scalable:     allow parallel execution on the same host (unique project-id)
* performant:   test runner termination initiates tear down 
* clean:        clean and reliable tear down (containers, network, volumes)
* reliable:     health checks for individual service readiness
* smart:        ideal time of test runner execution (tests don't need to check service health)

## Core constraints
* the additional configuration does not affect a productive docker-compose.yml
  * --> the same docker-compose.yml could be used for production
* the testrunner image itself is out of scope
* the integration test framework which resolves service addresses dynamically (to run identical tests from the testruner image and from the IDE) is out of scope

## Counter arguments
* "Why not put all of that responsibility in the testrunner image?"
  * Based on this idea, all of the generic test run functionality is in the test runner image:
    * it is a service like the others and starts up with them
    * it is responsible for polling health checks of all the services in the setup (which services exactly needs to be provided somehow)
  * (-) no clean wrapper around the whole workflow
  * (-) pipeline integration is more complex
  * (-) unique identifier has to be handled explicitly
  * (-) tear down has to be triggered by recognizing test runner termination 

## Future
* integration into docker swarm
* integration into kubernetes


## Bachelor/Master Thesis
In the context of a bachelor thesis, the following points need to be worked out. Depending on how many of the points are already established beforehand, this topic might be too extensive for a bachelor thesis.
##### docker basics
the student needs to understand containers, their core differences to virtualization and their impact on modern software development.
##### docker compose basics
the student has to know the functional space of docker compose and how its orchestration capabilities differ from other tools (especially docker swarm & kubernetes).
##### python development
the student needs to be able to write python code, work with an IDE, use git, structure their process in logical commits, write unit and integration tests for their code.
##### open source concepts
the student needs to understand the concept of open source development and contribution.
##### test automation basics
the student needs to grasp the importance of service integration tests within the context of SoA (eg microservice) development. they need to be know differences to other layers of automated testing.
##### docker compose codebase
the student needs to become acquainted with the docker compose codebase and understand how a new feature is properly introduced.