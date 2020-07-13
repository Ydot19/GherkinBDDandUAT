# Gherkin for BDD and ATDD

** Table of Contents **

# Background

## Business/Product Owners

Software development ultimately falls on the product vision and clarity from the business, product owner, and/or product manager. It is imperative that clear product expectations are communicated. Once this communication is  brought forth it is important to use a common language (gherkin in this instance) to drive development.

For more: see [Gherkin in Development](https://www.youtube.com/watch?v=KP0vpVLatMc)

Without product clarity, development will almost always build un-intended features or will be put on pause until there is clearity on product features. 

## For Developers

Before getting started there are design consideration you must implement to utilize cucumber. All these design considerations are centered around building a form of test-able architecture.

## Test-ability

- Application is modular.
  - Product and Service features are 
    - loosely coupled
    - component based
    
### Testable Architectures

#### Build Application Components Using Hexagonal Architecture

- Isolate the I/O based functionality at the edges of your design
- In this way, central logic of the application is decoupled from outside concerns
- Architecture makes testing easier
  - [x] Easily plug in stubs/fakes as needed

![Hexagonal Architecture](https://alistair.cockburn.us/wp-content/uploads/2018/02/Hexagonal-architecture-with-adapters.gif)

This is where most of the business application behavior is tested. *Component Wise* functional should occur throughout the development lifecycle.

For more: see the first 3 minutes of [BDD and ATDD/UAT](https://www.youtube.com/watch?v=lC0jzd8sGIA)


#### Full Stack UAT Tests

- These tests go through your entire application stack
- This tests are meant to get you complete confidence of your application as a whole
- These tests should be utilized as part of the UAT tests
  - Other user acceptance tests include 
    - *Performance Testing*
    - *Stress Testing*
    - *System Testing*

- These tests should be utilized during QA to assessed whether the application ready for release
  - Minimize stubs/fakes in this stage so that you can properly assess product readiness.
