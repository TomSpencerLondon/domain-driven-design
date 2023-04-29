### Domain Driven Design
- Eric Evans - Domain Driven Design: Tackling Complexity in the Heart of Software
- Pluralsight: https://www.pluralsight.com/courses/domain-driven-design-fundamentals?utm_source=google&utm_medium=paid-search&utm_campaign=upskilling-and-reskilling&utm_term=ssi-emea-uk-dynamic&utm_content=free-trial&gclid=Cj0KCQjw3a2iBhCFARIsAD4jQB06xLQuWUoyixx2mAPIXGn79riA4BOrDxZPkFgPcOCHiBUI3DftK9saAhP1EALw_wcB
  - perhaps watch and then implement on own project rather than trying to code along
- This course looks by Event Sourcery is good on domain driven design:
    https://www.youtube.com/watch?v=aGwZVOsll6Q&list=PLQuwqoolg4aI6v1GvtRg3NgT0PBBHVqii
- It starts with What is a Model and then goes on to talk about aggregates and modelling in general
- This is another course which is quite cool for practical domain driven design:https://www.pluralsight.com/courses/domain-driven-design-in-practice
- I had a go at translating to Java here: https://github.dev/TomSpencerLondon/SnackMachine
  - but next time would use BigDecimal instead of double.
- This video is also quite good on domain driven design with REST  : https://www.youtube.com/watch?v=x3Bf25altb4
  - According to Julien Topcu (I cloned the repo from his talk here: https://github.com/TomSpencerLondon/Columbiad-Express) the
best form of rest is HATEOAS (Hypermedia as the Engine of Application State). This is where the client is given a link to
the next state of the application. This is a good way of doing things because it means that the client does not need to work out the workflow but is presented
with the next logical step as part of the response.
    
### Domain Driven Design Example (Dmitri)
Items aggregates should be saved and updated at the same time. This is to avoid duplication of data.
A good example of domain driven design in action might be the following:

We might have an Order aggregate and a widget aggregate.
We might need the widget types and images for our order.
A bad design would simply put the Widget directly into the Order.
If we put the widget in the order we will have to decide not to save the widget in the order if the widget already exists.
We would then have to duplicate the saving logic and then there are more than one way of getting widgets. There is no 
longer one source of truth for mapping to the persistence store. Here we are talking about avoiding having to save things 
all the time. It is better to have smaller aggregates that are updated at the same time.
