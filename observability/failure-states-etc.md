Observability and failure states

Hypothesis:

Observability has two major goals:
1. Allow us to immediately realize failure states
2. Help us easily analyze such failure states 

The first is deeper in the realm of testing
Whereas the second is further in debugging

Are those two strictly separated though?
Definitely not! Here comes cause and effect into play. For failure discovery you rely on effect. For debugging you look for cause. Cause and effect are by definition strongly coupled. 

However you often do not have a single cause for a certain effect. 
Also you often don’t have a single effect following one cause. 
So n causes can have n effects. 

You might not always be able to measure the effect of a failure. Especially since you don’t know all possible failure states. We could turn this around and argue: you don’t need to know all failure states, you just need to know all success states and check on those existing. Which does not help much as it is basically checking (as a subset of testing). 

So there is two approaches to the first goal of observability:
1. Check on something working
2. Check on something not working
does this really mean something different?
Check on something working is a test. 
Check on something not working is probably also a test. Its a negative or exception case. 


What is a failure state?
Is it anything not working as expected?
Or is it anything not working as specified?
Or is it anything not working as needed by the user?
Is it equal to a bug?
Is it just a symptom of a bug?
Does a failure state require there to be a bug to exist in the first place?
How does failure state relate to bugs?
A failure state can definitely derive from a bug. But a bug cannot derive from a failure state, as a bug is existent in the system until it is effective. And one way it can be effective is by resulting in a failure state. Could a bug ever be effective without resulting in a failure state though? I cannot think of an example for that. 
So failure states can have two origins: from a bug and from not a bug (lets call it that for now). 
That is a good thing to keep in mind when analyzing a failure state. You don’t know yet if you are looking for a bug or for an incident (is that a good term?).
To follow that train of thought further we have to clearly define what a bug is. A bug is a false implementation in our system, whereas false applies to the weakly defined space between specified, needed and implemented. Because, you see it’s not necessarily a bug if the software does more than specified and needed. 
What is the other thing though?
The important part from our bug definition is the implementation part. There could be failure states that do not result from a false implementation (whatever that may be). So even with the hypothetically most perfectly implemented software we could still result in failure states.
Why is that? Because everything around us changes: neighbors, hardware, expectations (needed), network, certain states (db or otherwise), etc
Sounds a little bit like infrastructure is the common denominator. But it’s more like surrounding. 
Another ankle that helps nailing this down is thinking about we fix those issues. We usually don’t want to fix them by changing our software. But often that is exactly what we need to do, as we need to adapt to new surroundings, changed infrastructure or expectations. Actually that should be the only way of how we fix those as well. If our software as it exists is defined in code, as a whole. We can change it to adapt to that outside change to then prevent that particular failure state from happening again. 