# What is Domain Driven Design?
DDD is less about software design patterns and more about problem solving through collaboration.

## How does DDD manage complexity?
DDD deals with both the challenge of understanding a problem domain and creating a maintainable solution 
that is useful to solve problems within it.  
It achieves this by utilizing a number of strategic and tactical patterns.

### Strategic pattern
By using this, we can distill the problem domain and shape the architecture of an application.

#### Distill problem domain to reveal what is important
Discovering the core domain helps teams understand why they’re producing the software 
and what it means for the software to be successful to the business.

#### Create a model to solve domain problems
This model is not a model of real life
but more an abstraction built to satisfy the requirements of business use cases 
while still retaining the rules and logic of the business domain. 

#### Use a shared language to enable modeling collaboration
Use the ubiquitous language(UL) to describe how to solve the problem. Do not include any tool, pattern, etc.  
Make sure everybody on the same page and understand:
1. What is the problem
2. How to solve the problem

#### Isolate models from ambiguity and corruption
Models are isolated from infrastructure code to avoid the accidental complexity of merging technical and business concepts.

#### Understand the relationships between contexts

## The practices and principles of DDD
They are:
1. focus on core domain.
> It’s the product’s unique selling point, the reason it is being built rather than bought.
2. learn through collaboration, from business experts.
3. create models through exploration and experimentation
> Eric Evans suggests that for every good design there must be at least three bad ones, 
> this will prevent teams stopping at the first useful model.
