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
