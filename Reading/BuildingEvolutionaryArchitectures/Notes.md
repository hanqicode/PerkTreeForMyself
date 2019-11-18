# Notes

## Chapter 3. Engineering Incremental Change

There are two aspects of incremental change: development(build), operational(deploy).

> If the new version requires a different contract for callers, it is typical to handle that within the service rather than burden callers with resolving which version to call. - Page 41

> Once the hypothesis is in place, run experiments via A/B testing and tally the result...Using hypothesis-driven development, we can incorporate users in an unprecedented way, learning from behavior and buiding what users really find valuable. - Page 57

## Chapter 4. Architectural Coupling
There are 3 criteria for a good evolutionary architecture:
1. Incremental change  
Making any change should not be difficult.

2. Guided change with fitness functions  
Architecure should be clearly defined and have protective tests.

3. Appropriate coupling  
Should have lowly coupled components inside the system.

Prevent cycle between couples. We could leverage *JDepend* open source tool to test.

## Chapter 6. Building Evolvable Architectures
Three steps:
1. Identify which dimensions of the architecture we want to protect as it evolves.
2. Define fitness functions for each dimension, such as preventing component dependency cycles, make a wiki for dimensinos deserve ongoing attention.
3. Use pipeline to automate fitness functions. 

> Understand the business problem before choosing an architecture...While this advice seems obvious, we constantly see teams that have chosen the shiniest new architectural pattern rather than the most appropriate one suffer.  - Page 112. (Similar to Domain Driven Design)

> Don’t build an architecture just because it will be fun meta-work. - Page 115

> Identify and remove needless variability. - Page 123

> Make as many decisions as possible reversible (without over- engineering). - Page 124

> While architects can’t predict the future, we can at least lower the cost of change so that it doesn’t impact us so nega‐ tively. - Page 126

## Chapter 7. Evolutionary Architecture Pitfalls and Antipatterns

Do not be a vendor king.
> To escape this antipattern, treat all software as just another integration point, even if it initially has broad responsibilities. - Page 138

Code reuse antipattern.
> Clearly, the ability to reuse code is good. However, like all good ideas, many companies abuse this idea and create problems for themselves. - Page 142

> Making code reusable involves adding additional options and decision points to accommodate the different uses. The more developers add hooks to enable reusability the more they harm the basic usability of the code. - Page 143

