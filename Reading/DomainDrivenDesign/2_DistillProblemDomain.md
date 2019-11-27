# Distill The Problem Domain

## Knowledge crunching and Collaboration
1. We can start from a use case to understand the business requirements.
2. Need to collaborate with business experts/stakeholders to understand correctly and not overlooked.
3. Simplify the model to satisfy the needs of all use cases.

## Reach a shared understanding through a shared language
The language should also be used in the code implementation of the model, with the same terms and concepts used as class names, properties, and method names.

The shared understanding that a UL prevents the need to constantly translate from a technical model to a business model, thus removing the chance of vital insight being lost.

## An ongoing process
Knowledge crunching is an ongoing process; teams should continually be working toward a simple view of the problem domain that focuses only on the relevant pieces to aid the creation of a useful model. 

The model made is only useful for the problems at hand.

## Domain experts
Stakeholders may just give you the inputs, outputs of the system; Domain experts will give you a useful model to satisfy the needs.

<img src="https://github.com/hanqicode/PerkTreeForMyself/blob/master/Reading/DomainDrivenDesign/Pictures/DomainExpert.png" alt="drawing" width="600"/>

## Sketch
Draw a sketch will help to understand and communicate. 

But, pay attention to keep your diagrams at a consistent level of detail. It’s often better to create multiple diagrams each at a different level of detail.

## Defer naming of concepts in your model
Naming is important when modeling a domain. Defer naming a concept before you fully understand its functions.

The types of names that you want to avoid are `XXXXService` and `XXXXManager`. If you find yourself appending service or manager to a class or concept, think more creatively, strive for real intent behind a name. When you feel you have really understood a part of the model, you will be in a better place to give it a sensible and meaningful name.

## Impact Map
What is impact map? Start from the goal, end to technical solution. 

Here is an example:

<img src="https://github.com/hanqicode/PerkTreeForMyself/blob/master/Reading/DomainDrivenDesign/Pictures/ImpactMap.png" alt="drawing" width="600"/>

Think about the problem from:
1. The final business goal.
2. The actors.
3. Ways that actors can take.
4. Actual tasks that can be carried out.
