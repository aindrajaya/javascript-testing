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

# Test NodeJS Backends
Backends hold so much of our application's business logic that is often used to support multiple clients (web, mobile, and other native platforms). This logic is critical to get right and deploying a breaking change to this can be devastating to your company's goals (not to mention the bottom-line). Increasing your "deployment confidence" is crucial and automated testing is the best way to do that. As NodeJS continues to grow in usage around the world, learning how to test this mission-critical code in a way that increases developer velocity as well as confidence becomes increasingly important. In this workshop we use an Express.js example and focus on the patterns and practices that you need to learn so you can apply what you learn to test your code written in any NodeJS web framework.
You'll learn:
- Testing Pure Functions
- Testing Middleware
- Testing Controllers
- Testing API routes
- Mocking third party dependencies
- Testing authenticated code
1. Intro to Test NodeJS Backends
2. Test Pure Functions overview
## Background
Here's what a Jest test looks like:
```js
//add.js
export default (a, b) => a + b

// __test__/add.js
import add from '../add'

test('add returns the sum of the two given numbers', () => {
  const result = add(1,2);
  expect(result).toBe(3)
})
```
The `test` and `expect` functions are global variables provided to us from Jest. `expect` is an assertion library that's built into Jest and has a lot of assertions you can use: you may want to keep that page open for reference. A "pure function" is a function with the following properties:
--> it's return value is the same for the same arguments (no variation with local static variables, non-local variables, mutable reference arguments or input streams from I/O devices)
--> Its evaluation has no side effects (no mutation of local static variables, non-local variables, mutable reference arguments or I/O streams)
Thanks to these properties, pure functions are typically the easiest thing to test. And because of this, it's often advisable to place as much of your complex logic in pure functions as possible. That way you can write tests for that logic very easily, giving you confidence that it continues to work as intended over time. 
## Exercise
In this exercise, we have a `isPasswordAllowed` function we can call with a string and it returns `true` or `false` based on whether that password is strong enough. The implementation of `isPasswordAllowed` enforces that the password is at leas 6 characters long and has at least one of the following characters:
--> non-alphanumeric
--> digit
--> uppercase letter
--> lowercase
For us to be confident that `isPasswordAllowed` will continue to function as expected, we should have a test case of these (as well as one which does pass the requirements). Your job to completely test the `isPasswordAllowed` function in `src/utils/__tests__/auth.exercise.js`.
## Extra Credit
### reduce duplication
Depending on how this is solved we could have one of two problems:
--> We have an individual test for every assertion: This results in a lot of duplication, which can lead to typo mistakes
--> We have one giant test: This results in less helpful error messages.
See if you can figure out a way to programmatically generate the tests (using array/loops) so we get both good error messages as well as avoiding duplication.
```auth.exercise.js -> reduce duplication
import {isPasswordAllowed} from '../auth'

describe('isPasswordAllowed only ')

```
### jest-in-case
Unfortunately for these generated tests, the error messages may still not be quite what we're looking for. In addition, we may actually be writing more code for this abstraction than before. So instead, let's use a module called `jest-in-case` to test this. If I were to use `jest-in-use` for the `add` function as above, it would look like this:
```js
import cases from 'jest-in-case';

cases(
  'add',
  opts => {
    const result = add(opts.a, opts.b)
    expect(result).toBe(opts.result)
  },
  {
    'Sum of the two given numbers': {
      a: 1,
      b: 2,
      result: 3,
    },
  },
)
```
Clearly using `jest-in-case` for this simple function is going a bit overboard, but doing this kind of thing for more complex pure functions with lost of cases can simplify maintenance big time. Here's an example of an open source project where I applied this similar kind of pattern (before `jest-in-case` was a thing): `rtf-css-js` tests. And here's another: `match-sorter` tests(also wrote this before `jest-in-case` was a thing).
I've been the maintainer of these projects for years and people have commented on how easily it is to contribute to because the tests are so easy to add to, and once you've added a test case, you can go implement that feature easily. This is a perfect tool for Test-Drive Development. [NOTE: as mentioned, both of these were written before `jest-in-case` was created and I haven't taken the time to upgrade them. If I were actively working on these projects then I would definitely migrate them. I have definitely used `jest-in-case` in products I've worked on and I love it]
### Improved titles for jest-in-case
The naive implementation of `jest-in-case` here may result in good, but still imperfect test names which has an impact on the error messages you'll get. Try to make it so the test name includes not only the reason a given password is valid/invalid, but also what the password is.
---
3. Write Unit Tests for a Simple Pure Function
```auth.exercise.js
//Import the function that we wanna test
import {isPasswordAllowed} from '../auth';

//first use case
test('isPasswordAllowd returns true for valid passwords', () => {
  expect(isPasswordAllowed('!aBc123')).toBe(true)
})

//second use case
test('isPasswordAllowed returns false for Invalid passwords', () => {
  expect(isPasswordAllowed('a2c!')).toBe(false)
  expect(isPasswordAllowed('123456!')).toBe(false)
  expect(isPasswordAllowed('ABCdef!')).toBe(false)
  expect(isPasswordAllowed('abc123!')).toBe(false)
  expect(isPasswordAllowed('ABC123!')).toBe(false)
  expect(isPasswordAllowed('ABCdef123 ')).toBe(false)
})
```
```auth.js
function isPasswordAllowed(password){
  return (
    password.length > 6 &&
    // non-alphanumeric
    /\W/.test(password) &&
    // digit
    /\d/.test(password) &&
    // capital letter
    /[A-Z]/.test(password) &&
    // lowercase letter
    /[a-z]/.test(password)
  )
}
```
4. Improve Error Messages by Generating Test Titles
5. Use jest-in-case to Reduce Duplication and Improve Test Titles
6. Create a Casify Function to Generate Cases for jest-in-case
7. Test Node Middleware Overview
8. Write a Unit Test for Handling an UnauthorizedError
9. Write a Unit Test for Handling headerSent in an Error Middleware
10. Write a Unit Test for Status 500 Error Middleware Fallback
11. Improve Test Maintainability using the Test Object Factory Pattern
12. Use a Test Object Factory utils/generate
13. Test Node Controllers Overview'
14. Write a Unit Test for a Controller by Mocking the Database
15. Simplify Assertions on Error Messages with toMatchInlineSnapshot
16. Unit Test Business Logic of a Controller's Middleware
17. Test Controller 404 Edge Case where Resource is Not Found
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
