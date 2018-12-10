---
layout: post
title: Event-Driven Architecture
---
Fun facts
"When anything sounds like it is really nice, there is always a but, isn't it"

### Reference
https://www.youtube.com/watch?v=STKCRSUsyP0

### Four patterns of Event-Driven Architecture
+ Event Notification
+ Event-carried State Transfer
+ Event Sourcing ***
+ CQRS

### Pros and Cons
+ Event Notification  
    Pros:  
    - Decoupling (+)  
    
    Cons:  
    - Can not figure out how it works by just looking at the code base,  
    need to step throught the debugger do thing and see what happens because it is all events.

+ Event-carried State Transfer  
    Pros:  
    - Decoupling
    - Reducing load on supplier  

    Cons:  
    - Replicated data, consistency problem

+ Event Sourcing  
    Pros:  
    - Audit
    - Debugging
    - Historic State
    - Alternative State
    - Memory Image  

    Cons:  
    - Unfamiliar
    - External Systems
    - Event Schema
    - Identifiers
    - Asynchrony?
    - Versioning?

+ CQRS?
