JAVASCRIPT TESTING CURRICULUM
#. Fundamental of Testing in JavaScript
Do you know what a testing framework does? Do you know what makes a testing framework different from a testing or assertion library? The best way to use a tool effectively is to understand how it works. And the best way to understand how a tool works is by making it yourself! In this short course, we’ll learn how testing frameworks and assertion libraries work by building our own, simple version of each.
1. Intro to Fundamentals of Testing in JavaScript
2. Throw an Error with a Simple Test in JavaScript
In this lesson, we'l get the most fundamental understanding of what an automated test is in Javascript. A test is code that throws an error when the actual result of something does not match the expected output. Tests can get more complicated when you're dealing with code that depends on some sate to be set up first (like a component needs to be rendered to the document before you can fire browser events, or there needs to be users in the database). However, it is relatively easy to test pure functions (functions which will always return the same output for a given input and not change the state of the world around them).
3. Abstract Test Assertions inot a JavaScript Assertion Library
Let's add a simple layer of abstraction in our simple test to make writing tests easier. The assertion library will help our test assertions read more like a phrase you might say which will help people understand our intentions better. It wil also help us avoid unnecessary duplication.
4. Encapsulate and Isolate Tests by building a JavaScript testing Framework
One of the limitations of the way that this test is writtent is that as soon as one of these assertions experiences an error, the other test are not run. It can realy help developers identify what the problem is if they can see the results of all of the tests. Let's create our own `test` function to allow us to encapsulate our automated tests, isolate them from other tests in the filem, and ensure we run all the tests in the file with more helpful error messages. 
5. Support Async Tests with JavaScritps Promises through async await
Our testing framework works great for our syncrhonous test. What if we had some asynchronous functions that we wanted to test? We could make our callback functions `async`, and then use the await keyword to wait for that to resolve, then we can make our assertion on the result and the expcted. Let's make our testing framework support promises so users can use async/await.
6. Provide Testing Helper Functions as Globals in JavaScript
These testing utilities that we built are pretty useful. We want to be able to use them throughout our application in every single one of our test files. Some testing frameworks provide their helpers as global variables. Let's implement this functionality to make it easier to use our testing framework and assertion library. We can do this by exposing our `test` and `expect` functions on the global object available throughout the application.
7. Verify Custom JavaScript Tests with Jest
Up to this point we’ve created all our own utilities. As it turns out, the utilities we’ve created mirror the utilities provided by Jest perfectly! Let’s install Jest and use it to run our test!
---

#. JavaScript Mocking Fundamentals
When running unit tests, you don’t want to actually make network requests or charge real credit cards. That could… get expensive… and also very, very slow. So instead of running your code exactly as it would run in production, you can modify how some of your JavaScript modules and functions work during tests to avoid test unreliability (flakiness) and improve the speed of your tests. This kind of modification can come in the form of stubs, mocks, or generally: “test doubles.” There are some great libraries and abstractions for mocking your JavaScript modules during tests. The Jest testing framework has great mocking capabilities built-in for functions as well as entire modules. To really understand how things are working though, let’s implement some of these features ourselves.
---

#. Static Analysis Testing JavaScript Applications
There are a ton of ways your application can break. One of the most commont sources of bugs is related to typos and incorrect types. Passing a string to a function that expects a number, or falling prey to a common typo in a logical statement are silly mistakes that should never be made, but this happens all the time. We could write a comprehensive suite of automated tests for our entire codebase to make certain mistakes like this never happen, but what would liley be too much work and slow development down to be worth the benefit. Luckily for use, there are tools like ESLint, TypeScript, Prettier, and more which we can use to satisfy a whole category of testing with a  gret developer experience.
1. Intro to Static Analysis Testing JavaScript Applications
2. Lint JavaScript by Configuring and Running ESLint
3. Use the ESLint Extension for VSCode
4. Use pre-bult ESLint Configuration using extends
5. Run ESLint with npm Scripts
6. Format Code by Installing and Running Prettier
7. Configure Prettier
8. Use the Prettier Extension for VSCode
9. Disable Unnecessary ESLint Stylistic Rules with eslint-config-prettier
10. Validate All Files are Properly Formatted with Prettier
11. Avoid Common Errors by Instaling and Configuring Typescript.
12. Make ESLin Support Typescript Files
13. Validate Code in a pre-commit git Hook with husky
14. Auto-format All Files and Validate Relevant Files in a precommit Script with lint-staged
15. Run multiple npm Scripts in Parallel with npm-run-all
---

#. Use DOM Testing Library to test any JS Framework
#. Configure Jest for Testing JavaScript Applications
#. Test React Components with Jest and React Testing Library
#. Install, Configure, and Script Cypress for JavaScript Web Applications
## 

#. Test NodeJS Backends
Backends hold so much of our applications's business logic that is often used to support multiple clients (web, mobile, and other native problems). This logic is critical to get right and deploying a breaking change to this can be devastating to your company's goals (not to mention the bottom-line). Increasing your "deployment confidence" is crucial and automated testing is the best way to do that. As nodejs continues to grow in usage around the world, learning how to test this mission-critical code in a way that increases developer velocity as well as confidence becomes increasingly important. In this workshop we use an Express.js example and focus o the patterns and practices that you need to learn so you can apply what you learn to test your code written in any NodeJS web framework. You'll learn:
- Testing Pure Functions
- Testing Middleware
- Testing Controllers
- Testing API Routes
- Mocking Third party dependencies
- Testing Authenticated Code
1. Intro to Test NodeJS Backends
2. Test Pure Functions Overview
Of all things you can test, the easisest you can test is a pure function because they require no setup or teardown. In this exercise, we'll explore testing a pure function called isPasswordAllowed. 
3. Write Unit Tests for a Simple Pure Function
Let's write the basic tests for our simple isPasswordAllowed functino to ensure that both valid and invalid passwords the correct return value. 
4. Improve Error message by Generating Test Titles
One of the most crucial things you can do when writing tests is ensuring that the error message explains the problem as clearly as possible so it can be addressed quickly. Let's improve our test by generating test titles so error messages are more descriptive.
5. Use jest-in-case to Reduce Duplication and Improve Test Titles
Jest has a test-generation feature built-in called test.each which is great, but I don't particularly like its API. Instead, we're going to use an open source project called jest-in-case which gives us a realy nice API for generated tests and improved error meesages. Let's try that library out for our isPasswordAllowed tests here. 
6. Create a Casify Function to Generate Cases for jest-in-case
Even with jest-in-case there canb e a little boilerplate and you can easily side-step that by creating a simple function that allows you to write test cases that are more suited for your use case. Let's
7. Test Node Middleware Overview
8. Write a Unit Test for Handling an UnauthorizedEror
9. Write a Unit Test for Handling headersSent in an Error Middleware
10. Write a Unit Test for Status 500 Error Middleware Fallback
11. Improve Test Maintainability using the Test Object Factory Pattern
12. Use a Test Object Factory utils/generate
13. Test Node Controllers Overview
14. Write a Unit Test for a Controller by Mocking the Database
15. Simplify Assertions on Error Messages with toMachInlineSnapshot
16. Unit Test Business Logic of a Controller's Middleware
17. Test controller 404 Edge Case where Resource is Not Found
18. Test Controller Unauthorized Case
19. Test getListItems for Getting Multiple Mock Objects
20. Test the Happy Path of a Creation Flow
21. Testing an Error Case for createListItem
22. Testing the Happy Path for updateListItem
23. Testing Resource Deletion
24. Test Authentication API Routes Overview
25. Start a Node Server and Fire a Request to an HTTP API Endpoint
26. Make Assertions on HTTP API Responses for Registration
27. Test the Login Endpoint for a Node Server
28. Test the User's Resource Endpoint
29. Create a Pre-configured axios Client for the baseURL
30. Improve Error Messages with an axios Interceptor
31. Ensure a Unique Server Port
32. Use Snapshots to Assert on Server Eror Responses
33. Interact Directly with the Database
34. Test all the Edge Cases
35. Test CRUD API Routes Overvie
36. Write an Integration Test for a Resource Create Endpoint
37. Write an Integration Test for a Resource Read Endpoint
38. Integration Test a Resource Update Endpoint
39. Integration Test a Resource Delete Endpoint
40. Snapshot the Error Message with Dynamic Data