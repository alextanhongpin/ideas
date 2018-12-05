# Testing

## Test cases should be independent

Don't group test mockups together - when one things break, it will all break. Previously we had a design where we group the initialization of all mock dependencies in golang in a folder called `testdata/factories`. There was a sudden change in one of the implementation of the interface, and all the test stops working because they shared the same mock factory. 

We initially thought separating the dependency into a folder would keep things DRY, but it ends up becoming a SPOF (single point of failure.

The solution we came up with is by creating new initialization for different environment (e.g. `NewProduction`, `NewDevelopment`, `NewTesting`). Also, if the components do not need to be mocked, we can just create a new **no-op** struct, e.g. `pkg.Nop()` instead of `pkg.NewNop()`. This makes it easier, as we do not need to mock our dependencies elsewhere then - it lives with the package.

TL;DR:
- setup a `Nop` struct for dependencies (such as logger, requestIDGenerator etc) that just fulfils the interface
- if the dependency needs to be reused in multiple places, place it in a package mock
- if the interface is too huge, it's a problem, break it down

## Other principles for testing

- test cases should be easy to understand
- test cases should have a specific objective
- test cases should describe the why, not what
- test cases should cover different scenarios

What is testing? It is basically a process of identifying input and outputs of a function. The problems comes when we can have multiple input parameters and pipeline to achieve the results.
Assuming we have 4 inputs, we will have 2^4 combinations that needs to be tested.

## What to test

- at a higher picture, the user story
- at a lower level, validation and scenarios
- test behaviours, not implementations
- implementations makes tests brittle
- prepare setups for tests (such as logged in users etc) once at the beginning of the test
- clear the database for each tests

## Int scenario

- boundary(min, max), none provided, -tive value
- empty string, zero space
