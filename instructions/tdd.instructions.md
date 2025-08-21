---
applyTo: "**"
---
# Test-Driven Development (TDD) Guidelines

This document contains critical information about working with this codebase. Follow these guidelines precisely.

## What TDD ensures
- Everything that was working before continues to work.
- The new behavior works as expected.
- The system is ready for further changes.
- The programmer is confident about the above points.

## TDD Steps
1. Comprehensively list the expected behaviors for the target functionality, and based on that, create a list of test scenarios.
  <test-scenario-example>
    Feature: The `truncate()` method that truncates strings exceeding the specified maximum length and appends "..."

    Scenario-01: When the string is shorter than the maximum length
      Given: There is a string "hello"
      When: truncate("hello", 10) is called
      Then: "hello" is returned

    Scenario-02: When the string length is equal to the maximum length
      Given: There is a string "hello world"
      When: truncate("hello world", 11) is called
      Then: "hello world" is returned

    Scenario-03: When the string is longer than the maximum length
      Given: There is a string "hello world"
      When: truncate("hello world", 5) is called
      Then: "he..." is returned
  </test-scenario-example>
2. Select "only one" from the test list, create and execute a concrete and executable test code, and confirm that the test fails.
3. Change the product code to make the test you just wrote and all the tests you have written so far pass.
4. Refactor as necessary to improve the design of the implementation.
5. Commit the code in meaningful units.
6. If you notice the need for a new test scenario in the process up to step 4, add the scenario to the test list.
7. Return to step 2 and repeat until the test list is empty.

<instructions>
- Create tests only for public methods and functions.
- Start with the simplest and most minimal implementation possible.
- When implementing, first choose the **easiest way to pass the test**.
- Clearly separate the work of Step 3 and Step 5.
- When refactoring, **make sure to pass all existing tests**.
- When common parts become visible in multiple test cases, abstract them by refactoring.
- Don't get obsessed with creating a large number of test scenarios; create only the essential ones.
- **Do not tamper with the test results**.
- Output the status each time each step shown in 'TDD Steps' is completed.
  <status-output>
    Scenario-01: red...
    Scenario-01: green...
    Scenario-01: blue...
    Scenario-01: committed!
  </status-output>
</instructions>
