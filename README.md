# Gherkin for BDD and ATDD

- [Background](#background)
- [Best Practices](#best-practices)

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

This is where most of the business application behavior is tested. *Component Wise* functional tests should occur throughout the development lifecycle.

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

# Best Practices
- Use a feature to describe a modular/encapsulated component of your application
- Use Tags to describe different environments (`@dev`, `@qa`, `@atdd`, `@sandbox`)
- Keep scenarios/examples steps short (under 10 steps if possible)
- Use data tables in step definition to different multiple inputs or more than one expected output
  - See https://www.baeldung.com/cucumber-data-tables
  - See http://www.automationtestinghub.com/cucumber-data-table/
- Use `Background` keyword to give a common context to all scenarios in a feature file
- Using `Scenario` vs `Scenario Outline`
  - Use `Scenario` when you have one single test case
  
  ```
  Scenario: Search button works
    Given: Context info
    When: Action step
    Then: Expected result
  ```
  
  - Use `Scenario Outline` when you have different inputs for the same scenario
    - See the [example](https://www.tutorialspoint.com/cucumber/cucumber_scenario_outline.htm)

- Use a `rule` in a feature when you are trying to

> *represent one business rule that should be implemented. It provides additional information for a feature. A Rule is used to group together several scenarios that belong to this business rule. A Rule should contain one or more scenarios that illustrate the particular rule.* source: https://cucumber.io/docs/gherkin/reference/
  - Use rules to group related scenarios together that don't follow a common `Scenario Outline` format
    - See the following examples:
      - https://cucumber.io/blog/bdd/example-mapping-introduction/
      - https://cucumber.io/docs/gherkin/reference/
      - [Sample Feature](https://github.com/cucumber/cucumber-jvm/blob/main/gherkin-messages/src/test/resources/io/cucumber/core/gherkin/messages/background.feature)
- Utilize `And` to give additional context after a `Given` or follow up on the result following a `Then` step
- Use `But` if you are using repeated `And` steps consecutively
    - See https://www.tutorialspoint.com/cucumber/cucumber_annotations.htm
