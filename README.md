# Gherkin for BDD and UAT

** Table of Contents **

## Background

### For Developers

Before getting started there are design consideration you must implement to utilize cucumber. All these design considerations are centered around building a form of test-able architecture.

#### Test-ability

- Application is modular.
  - Product and Service features are 
    > - loosely coupled
    > - component based
    
#### Testable Architectures

##### Build Application Components Using Hexagonal Architecture

- Isolate the I/O based functionality at the edges of your design
- In this way, central logic of the application is decoupled from outside concerns
- Architecture makes testing easier
  - [x] Easily plug in stubs/fakes as needed

![Hexagonal Architecture](https://alistair.cockburn.us/wp-content/uploads/2018/02/Hexagonal-architecture-with-adapters.gif)

