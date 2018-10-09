Monitoring in production can replace your regression testing as a whole. 
When regression testing a feature you are covering one sample whereas a strong monitoring on the production environment will give you feedback on all and exclusive relevant samples. 
On the left the regression test on the right one or multiple metrics indicating success of the same feature. 

Why risk one error in prod?
Distributed systems are inherently brittle and never 100% healthy. Therefore relying on one sample to give green light for the whole feature is misleading. Also it slows down your response Time: Time to fix the error in production. 

Statistically: Chance of uncovering a bug with one sample vs chance of uncovering a bug in production: 
x% vs 100%
User impact:
y% vs z%
Both are unknown: the regression sample set is most definitely incomplete. The user impact on production we can strive to reduce. 
