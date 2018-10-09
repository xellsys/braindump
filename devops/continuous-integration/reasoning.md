From reading different blogs and articles and from impressions when talking to colleagues and others in similar positions regarding CI, I get the impression that all arguments against the good practices for CI out there result from a core misconception/misinterpretation or unrealized fact:

"Every change a developer makes is inherently good!"

Why is this the case?
- Intention of the developer is good
- That is their job: to provide value to the codebase
- It provides other developers to benefit from that change
- If it was not good, we would not be spending money on it!!!

After having accepted / realised this fact, the rest falls into place.

On that basis, all the other concepts of CI can be derived:
- integrate as soon and as often as possible
- do not use preflight builds
- highest priority is always: fixing the broken build
- reduce time to market to provide value to the customer as soon as possible
- always focus on the oldest change in the pipeline which is not yet live
- before implementing new changes on a broken build, fix the change which is current ahead in the CI/CD pipeline

ToDo:
- manifest that understanding in your team

Follow Up: "why is the cd the logical next step?"
- under the premise of every change providing value -> your business wants to benefit from that value ASAP
- it only does so if the customer is presented with that value
- so reducing time to market is key
- also it helps the developer in being more productive if something needs to be fixed regarding that change: the change is not long ago, still in memory, the code did not change much since that one change, it is easier to be associated with that one change, the same developer is probably still part of the team, ...
- automated cd pipelines do not increase in costs when the number of changes increases

Try to make the smallest changes possible:
- the smallest change does provide value
 - if it does not, the change is not needed at all
- the smaller the change the sooner it integrates
- the smaller the change the easier it integrates
- the smaller the change the easier it is understood
- the smaller the change the easier it is rolled back
- the smaller the change the easier it is fixed in case of an issue
- the smaller the change the easier it can be assigned to a single task/feature