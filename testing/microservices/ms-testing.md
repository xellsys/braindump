We don’t test for the testings sake!
We Test because we gain a benefit from it. If we don’t then we don’t test. If something else does the job better, we do that!

Low coupling high cohesion in testing Microservices. Don’t build the test monolith. 

I view pre-production testing as a best effort verification of the correctness of a system as well as a best effort simulation of the known failure modes.
The goal of pre-production testing, as such, isn’t to prove there aren’t any bugs (except perhaps in parsers and any application that deals with money or safety), but to assure that the known-knowns are well covered and the known-unknowns have instrumentation in place for.


--------------------
24.06.18
1. seperate microservice integration testing between sociable and solitary
2. focus on unit/component/service tests -> should cover >80% of business functionality (cross check with domain driven architecture if that seems unreasonable for you)
3. integration testing of multiple services should mainly be technical, focusing on the contracts (narrow integration tests)
4. exceptions are: business interdependencies of microservices (should be very rare). in that case a sociable integration test is appropriate (wide integration tests)