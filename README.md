# Lecture notes, End-to-End Testing

## Overview of End-to-End Testing
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - End-to-End (E2E) testing is the broadest category of testing that checks user stories.
  - The goal is to see if the entire workflow works as expected, such as logging in and being directed to the correct page.
  - Instead of hiring user testers, which can be expensive, E2E tests can help catch many bugs, though it’s still worth considering user testing for complete flow validation.
  - E2E tests are useful after completing other tests, like unit or integration testing, before pushing the application live.
  - You can run E2E tests on all pages, including those you may not have direct access to.
  - **E2E chain testing** is often synonymous with end-to-end testing.
  
</details>

## Why Use End-to-End Testing?
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - E2E testing helps ensure nothing is overlooked—checking if menus, buttons, login functionality, and other components work as expected.
  - Once set up, tests automatically detect issues after changes are made, making them efficient for future updates.
  - More complex tests provide more insights, but the best approach is to have a mix of unit tests, workflow tests, and smaller tests to cover various aspects of the app.
  
</details>

## User Stories
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - E2E testing fits well with **user stories**, which are a great way to define features.
  - User stories describe, in simple terms, what should happen based on who the user is. 
  - Example: "As a user, I should be able to see a list of 12 posts." / "As an admin, I should be able to edit posts."
  - User stories should be easy to understand and readable by everyone. One common mistake is forgetting to define what constitutes completion.
  - Avoid writing user stories that are too broad or general; complex stories can be split into smaller ones (e.g., a, b, c).
  - Always seek feedback, as something working on your machine may still have issues elsewhere.
  - Typical user story format: "As a (user role), I want to (action) so that (reason)."
  
</details>

## How to Create End-to-End Test Cases
<details>
  <summary><strong>Click to read more</strong></summary>
  
  ### Step 1: Define Functions
  - What functionalities do you want to test? Identify the input data and the expected output data.
  - Listing expected input data is essential to know what kind of data you’ll get back. Apps can crash if this isn't well thought out.
  - Understand relationships: what is required to move from point A to B or C? Can the functions be reused, or are they for specific use cases only?
  - It's always good to aim for DRY (Don't Repeat Yourself) code, but not all code can be fully reusable.

  ### Step 2: Build Conditions
  - Think about how these functions are built. Do you need to do A before B? Do you need to wait for something, like an API response?
  - If async conditions aren’t handled properly, the test might fail because the data isn’t returned in time.
  - Timing is crucial when checking APIs, such as when logging in (e.g., handling wrong username or password).
  - E2E tests focus on: did I click on the wrong thing and get the correct error message? Did I click on the right thing and get the expected result?
  
  ### Step 3: Build Test Cases
  - Create multiple test cases: login, balance check, etc.
  - Most workflows will have more than one test case—try logging in with correct and incorrect data and verify that the responses are as expected.
  - Consider what is being tested, how it was built, and how to best test it.
  
</details>

## Tools for End-to-End Testing
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - **Cypress** is an open-source system designed for frontend and end-to-end testing.
  - It can be set up entirely within Cypress, running tests in either a browser window or headless mode.
  - Cypress automates actions like typing in an email and clicking submit, and it can run tests every time a pull request is made back to the main branch.
  - It can take screenshots and record videos during the test, which is useful for debugging.
  - Cypress runs tests over the network and works on any webpage without the need for external waits or sleeps.
  - Unlike Selenium, Cypress is built on the machine itself, and if not specified otherwise, it runs tests on Electron (which also powers VS Code).
  - The language in Cypress resembles Jest, and it has a test runner to select which tests to run in which browser.
  - Errors and success messages are displayed within the test runner.
  - As projects grow, Cypress provides a dashboard to view test cases individually.
  
</details>

## Advantages of Cypress
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - Cypress can automatically manipulate the DOM, type into input fields, and click buttons.
  - Once installed, no additional software is needed—all actions happen within the test runner.
  - It’s written in JavaScript and integrates well with JavaScript frameworks.
  - Works well with GitHub Actions and other CI tools.
  - While Cypress can be used for any testing type, it's best suited for end-to-end tests.
  
</details>

## Disadvantages of Cypress
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - Doesn’t support Safari, so it can’t automate testing in that browser.
  - Cypress cannot switch between multiple browser tabs.
  - Other tools may be needed if your project uses other languages or requires support for Safari.
  
</details>

## Use Cases Beyond E2E Testing
<details>
  <summary><strong>Click to read more</strong></summary>
  
  - While Cypress can be used for unit testing and integration testing, it can be more difficult in those contexts.
  - Developers often switch between different tools based on the type of testing needed.
  
</details>
