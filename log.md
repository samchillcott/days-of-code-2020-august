### #daysofcode 1/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Day off outside the house. Definitely feel better being away from devices and code. Fresh air also helps. Been minimally active this month. Still trying to find the balance but getting there.

### #daysofcode 2/8/20 

**Today's Progress**
- Updated readme for Gulp project. Now all repos have detailed notes.

**Thoughts** 
- Day off.
- Taking time out to do Sunday morning routine of coffee, jazz and reading. 
- Read up on blockchain and its potential. Really intrigued and plan to look into both the core tech and where I could potentially utilise it.

### #daysofcode 3/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣
- Prepping Coaching Question App for testing by refactoring some of the functions to pure functions (no side effects) to be able to unit test. ⁣
- Optimised and condensed code to less lines and fewer functions.⁣
- Added hover state to button and fixed width so now the button is mobile responsive (was breaking out of container previously on some models).⁣
- Removed official twitter styling so functionality and hide on start now both work.⁣
⁣
**Thoughts** ⁣
- Caught myself spending time fixing other things on the app (not what I should be doing atm).⁣
- I'm struggling to understand the code for 2 reasons: I wrote this ages ago and didn't really use explanatory function and variable names and I modelled the code on a SO suggestion and still don't fully understand one aspect of it (I got it working and that's all that mattered at the time). One of things on my todo list was to look at an alternative/more efficient way of writing the logic in this app and I can see why now.⁣
- My top value is Discomfort at the moment. I'm really feeling it looking at this code but leaning into it as I know this is where I shall grow/improve.⁣
- My code is bloated and I am struggling to figure out what I can remove/refactor.⁣
- The fear of breaking stuff kicked in again. Reminded myself I'm on a new branch, chill out, go play.⁣
- I've figured how to make the app way simpler, just having scope issues on one of the variables. Fixed.⁣
- Not actually done the pure function but have improved other areas of app (which I guess does actually go some way to prepping for testing (and testing for performance)).⁣
- Quick chat with mentor getting head around pure functions and testing philosophy. Will attack tomorrow.⁣
- Official twitter button was injecting an iframe which caused issues with styling/hiding and carrying state to tweet. Did it my way instead.

### #daysofcode 4/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣
- Pure Functions - A pure function is a function where the return value is only determined by its input values, without observable side effects. Benefits: no side-effects, easier testing, easier debugging.⁣
- Referential Transparency = your function can be substituted with its output and not affect your program’s behaviour. If your function has side effects, swapping it out can break the program.⁣
- You can’t write bad code and good unit tests. If your unit tests are bad, it might be a symptom of bad code. Go back to the design and figure out how it needs to change to allow writing good unit tests.⁣
- Moved my pure function to util.js file and linked back to app.js (didn't need to but good practice for modular code). The util. js file contains a set of JavaScript utility functions that are used across multiple components.⁣
- Wrote first unit test to check selectRandomItemFromArray should select an item from an array at random.⁣
- Installed Jest-extended to have access to toBeOneOf. toBe only takes a single match.⁣
- Added exception testing - if the function is going to be invoked it has to be wrapped in another function call, otherwise the error will be thrown unexpectedly.⁣
⁣
**Thoughts** ⁣
- Pure functions can help me write better more testable code that is optimised. Have heard about functional programming so cool to check it out somewhat.⁣
- Caught myself going too deep into pure functions, back to actually writing some tests.⁣
- Realised my selectRandomItemFromArray function isn't technically a pure function because it outputs different results each time.⁣
- npm test in React actually uses Jest. Create React App uses Jest as its test runner.⁣
- Noticed I have 2 test suites because I still have the App.test.js file from CRA. And that's the test that is failing! My test looks like it is working. Deleted App.test.js.⁣
- Refactored test following the Jest docs, no longer works.⁣
- Choosing to write my first unit test on a function whose sole purpose is to deliberately give a different output each time probably wasn't the best idea lol.⁣
- Got unit test working with 3 variations of input including an empty array. Not quite sure how I am supposed to test for incorrect usage.

### #daysofcode 5/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣⁣
- Reading on how to do unit tests. When you’re writing tests, always try to be an evil genius. Think deeply about what can go wrong and add “unhappy path” test scenarios to keep your code honest.⁣
- Refactored original function to throw bespoke errors (not just generic ones) - based on what I expected in the test scenarios = using my tests to better my original code.⁣
- One Concern in One Test - Each test should evaluate one and only issue. Refactored test code into separate tests and added describe code block to house them.⁣
- Integration test on my Randomize function.⁣
- Renamed test to it - line of code/sentence makes more sense this way imo.⁣
⁣
**Thoughts** ⁣
- I do get the concept of why we do unit tests and I have done a few already but I want to check I am testing for the right things and in the right way. I want to get clearer on HOW to actually write the tests - less so the syntax, more the concept.⁣
- I had the Q; If you are expecting certain errors to be thrown, do you have to have written them into the source code first? OR will the test throw that error? I now see the point is to write the expected errors in the test then go back and add that code to your source and therefore pass the test!⁣
- I'm not convinced my test should be passing. I'm deliberately writing incorrect expected throw messages. Hmm. Spent an hour testing my tests. Wonder if it is timing out - I can see some test have the time in ms next to them and some don't? Spent a while googling this forgetting to check the Jest docs. Still seem to pass even when I feed inputs that should fail the test.⁣
- I'm thinking integration testing in React could be more complicated due to state being involved. Will be worth knowing how to do the testing though.⁣
⁣
**Questions**⁣
- Do all my functions have to be re-written to take arguments for them to be tested? Aka reusable. Yes function needs to take an input.

### #daysofcode 6/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣⁣
- Integration Tests reading - Pros and cons of Big Bang and the various Incremental strategies.⁣
- Integration test attempt - refactored main randomise function to accept arguments (2x arrays and 3 state setters). Test code fail.⁣
- e2e Test attempt - Also fail. ⁣
⁣
**Thoughts** ⁣
- I've been putting this off because I was/am still unsure on how to execute these, especially if they deal with state and was scared of having to rewrite my function to take arguments = I'm acknowledging some resistance.⁣
- I'm thinking I'm going to have to separate my concerns on my randomise function as it does 3 things.⁣
- Realizing the checks I wrote into yesterday's function are breaking when using the real-world data rather than the test data upon feeding (testing the array for non-integers = my questions array is all strings). Commented out the non integer check => react render infinite loop. Wrapped the onClick/JSX function in an arrow function - Fixed.⁣
- Seems the error checks I wrote in my source code yesterday are causing most of my issues today. Guess the plan is to find the balance of only checking certain things that COULD actually happen in the app rather than everything that COULD happen outside the context of the app.⁣
- I'm sure some of my tests should be failing. Not 100% sure why but as my foray is only meant to be an introduction I shan't worry about it too much at this stage.⁣
- Cannot read property 'constructor' of undefined - can't work out why feeding my test a legit variable is causing this.⁣
- Not had a day of being stumped in a while. Moving on to e2e for a dabble.⁣
- e2e test showing blank screen in puppeteer and passing test even with no expect code, wtf?!⁣
- Calling it for the day.⁣
- Think I should be using React testing library, will attack tomorrow.

### #daysofcode 6/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣⁣
- Integration Tests reading - Pros and cons of Big Bang and the various Incremental strategies.⁣
- Integration test attempt - refactored main randomise function to accept arguments (2x arrays and 3 state setters). Test code fail.⁣
- e2e Test attempt - Also fail. ⁣
⁣
**Thoughts** ⁣
- I've been putting this off because I was/am still unsure on how to execute these, especially if they deal with state and was scared of having to rewrite my function to take arguments = I'm acknowledging some resistance.⁣
- I'm thinking I'm going to have to separate my concerns on my randomise function as it does 3 things.⁣
- Realizing the checks I wrote into yesterday's function are breaking when using the real world data rather than the test data upon feeding (testing the array for non-integers = my questions array is all strings). Commented out the non integer check => react render infinite loop. Wrapped the onClick/JSX function in an arrow function - Fixed.⁣
- Seems the error checks I wrote in my source code yesterday are causing most of my issues today. Guess the plan is to find the balance of only checking certain things that COULD actually happen in the app rather than everything that COULD happen outside the context of the app.⁣
- I'm sure some of my tests should be failing. Not 100% sure why but as my foray is only meant to be an introduction I shan't worry about it too much at this stage.⁣
- Cannot read property 'constructor' of undefined - can't work out why feeding my test a legit variable is causing this.⁣
- Not had a day of being stumped in a while. Moving on to e2e for a dabble.⁣
- e2e test showing blank screen in puppeteer and passing test even with no expect code, wtf?!⁣
- Calling it for the day.⁣
- Think I should be using React testing library, will attack tomorrow.⁣
⁣
**Questions**⁣
- Is it best practice to always write functions as reusable (take arguments rather than hardcoded for specific use)?

### #daysofcode 7/8/20 ⁣
⁣
**Today's Progress**⁣
- Challenge 7 - Tests:⁣⁣
- e2e in React using Puppeteer headless browser.⁣
- Debugging tests using VSCode debugger. ⁣
- All tests (unit x 4, integration and end 2 end) pass.⁣
⁣
**Thoughts** ⁣
- Moved int and e2e test to app.test.js, still same issue of one of the variables being undefined so the inner function can't run.⁣
- Changed page.goto from a file(index.html) to the localhost - app now showing in chromium.⁣
- My main two fails are now due to 'undefined' issues. There must be something (possibly obvious) I am missing here but the testing environment is slightly different because I don't yet know how to debug the tests (as opposed to just the app code). I'm pretty sure I'm close on both my int and e2e tests but something isn't being passed as I expect.⁣
- What is undefined? OR is that the point/answer? The test don't have the variable they need to test? Noticed these errors are coming from the expect lines of my int and e2e which are both checking to see if the question displayed is one of the questions array. ⁣
= it has the variable but it has no data/value attached - why? And what exactly is undefined? Which variable? And where is it being used?⁣
- Medium's paywall is starting to annoy me.⁣
- Using the debugger is still a weak point of mine and is on my list of areas to improve. Those skills would come in handy now.⁣
- Had a play in VSCode debugger and looks like my questions variable (my array of questions saved as an array) is undefined - not sure why. I don't know how to use debugger, yet! Did some recon on how to use debugger. Don't think I can sort my tests out without this knowledge so detour it is.⁣
- questions variable is undefined at import stage. Changed export to exports. syntax and is now available in test file. This means my choice variable now gets defined too.⁣
- toBeOneOf is also undefined which leads me to believe it also isn't being imported correctly. Actually, the test is failing because once the question is selected and matched against the array it isn't in there because the function removed it!⁣
- Getting the hang of debugger and breakpoints - cool!⁣
- Both suites (all tests in unit/int/e2e) pass.⁣
⁣
**Questions**⁣
- Is the debugger changing my original files? Look like it's adding a load of stuff? Or at least in a copy of the file in the next tab over.
