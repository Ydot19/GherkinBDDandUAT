# Gherkin for BDD and UAT

** Table of Contents **

## Background

### For Developers

Before getting started there are design consideration you must implement to utilize cucumber. All these design considerations are centered around building a form of test-able architecture.

#### Test-ability

- Application is modular.
  - Product and Service features are 
    - loosely coupled
    - component based
    
#### Testable Architectures

##### Build Application Components Using Hexagonal Architecture

- Isolate the I/O based functionality at the edges of your design
- In this way, central logic of the application is decoupled from outside concerns
- Architecture makes testing easier
  - [x] Easily plug in stubs/fakes as needed

![Hexagonal Architecture](https://alistair.cockburn.us/wp-content/uploads/2018/02/Hexagonal-architecture-with-adapters.gif)

This is where most of the business application behavior is tested. *Component Wise* functional should occur throughout the development lifecycle.
- When doing component tests utilize fakes/stubs

#### Full Stack UAT Tests

- These tests go through your entire application stack
- There should only be a few of these tests
- This tests are meant to get you complete confidence of your application
- These tests should be utilized as part of the UAT tests
  - Other user acceptance tests include 
    - *Performance Testing*
    - *Stress Testing*
    - *System Testing*

- These tests should be utilized during QA to assessed whether the application ready for release
