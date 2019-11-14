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

## Chapter 5. Evolutionary Data
