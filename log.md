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

### #daysofcode 8/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Reading about what areas of tech I would like to explore more. Currently drawn toward Blockchain, HCI & Cognitive Science, I-apps (intelligent apps) & AR.

### #daysofcode 9/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Further reading on the bottlenecks for Blockchain adoption.
- Planned my strategy for job-hunting which starts next week.

### #daysofcode 10/8/20 ⁣
⁣
**Today's Progress**⁣
- Project 2 Tidy:⁣
- Sorted styling for CTC and Tweet buttons.⁣
- Add animations and pointers to buttons. ⁣
- Mobile responsive on iPhone 5 using aspect ratio.⁣
- Added testing reflections to readme.⁣
- Redeployed all updates to Netlify.⁣
- Added Jest & Puppeteer icons to Portfolio.⁣
- Updated resume to include testing.⁣
⁣
**Thoughts** ⁣
- Ready for the next phase.

### #daysofcode 11/8/20 ⁣
⁣
**Today's Progress**⁣
- GH Pull Requests & Issues - Understanding the difference and workflow.⁣
- Weather App issue - My friend Wissam @designingforscale noticed my weather app shows the sunrise/set times in GMT (local time for me) irrespective of what city is returned. This obviously means non GMT-based cities have incorrect times. Created fix branch for the issue and linked to a new (draft) PR.⁣

**Thoughts** ⁣
- Been good to get some experience with working on a "shared repo"/with others in GH. All my work up to this date has just been me, my code, my repos.⁣
- I shall also have a play with some open source at some point.⁣
- Noticed even my GMT times are 1 hour off. Strangely the sunset is 1 hour earlier than expected and sunset is 1 hour later?! Something funky going on here could be daylight savings/BST causing an inconsistency. It is the convert to UTC which is causing it. I don't actually need this conversion (think I initially did because I wanted to convert to GMT for some reason).⁣
- Got UK/GMT cities working fine and updated the display format by removing the seconds.⁣
- Montreal (my test case) still not working as desired. This is because the Unix timestamp is based off UTC so will have to make a function that does some sort of conversion based on the timezone (timezone Shift in seconds from UTC) value available in the retried data object.⁣
- sunrise conversion using timezone is now knocking the GMT sunrise times off by an hour for some reason. The sunrise conversion timestamp is correct so my date obj is wrong/adding an hour.⁣
- Leaving this for the day as I have a call with my mentor. Sometimes it's a good thing to leave things hanging = more excitement and momentum to attack in the next coding session.

### #daysofcode 12/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Day off having fun with the fam in the sun. 
- Been pondering the date/times in weather app - I shall try and do it myself but I'll also have a go with date-fns library which was recommended to me. Would be further practice using libraries and docs.

### #daysofcode 13/8/20 

**Today's Progress**
- Weather App Times Issue:
- Date Object reading.
- date-fns utility library installation and doc reading.
- momentjs installation, doc reading and sunrise/set attempt - All working but sunset misses a digit on minutes in some cases.  

**Thoughts** 
- Starting to see I could code this myself but it is the date object that is causing the issue and as there are so many variations and timezones I would need to code in, I'm thinking a library (which was recommended to me by a few friends) is actually the best way forward to cover all "gotchas".
- I'm collecting and converting the correct sunrise time in UNIX but struggling to convert that into the correct time.
- Having the same issue of my Unix being correct but converting it to an object using date-fns is converting to GMT (great for Leeds, not for Montreal). It is converting my unix back into GMT which I don't want. Seems this is built in to momentjs (the other recommended library) but I need a helper function date-fns-tz. Had a quick read but don't think this will do what I need to.
- Installed momentjs which acts as a wrapper so have to use a different getter approach to draw the hours and mins from the result.
- Now getting a crazy/incorrect date object. The getters are working but because the object is wrong, it is still displaying incorrect times. Needed moment.unix().
- Really starting to see how dates, times and timezones are a pain in the backside in JS! All good practice though.
- Both Leeds and Montreal (date objects) are an hour out, so I'm almost there. Turns out I need .unix().utc().format(). So the object is now correct but the getters are off. So close lol.
- Think the .format() was confusing the getters so removed that and looks like it finally works.
- Montreal sunset minutes is only showing 1 digit. Most other cities seem fine.
- Another session should sort this. Finally.

### #daysofcode 14/8/20 

**Today's Progress**
- Weather App Times Issue:
- Sort formatting and display of Unix timestamps after timezone conversion.
- Reviewed and merged PR back into master branch.
- GitHub Pages deployment update.
- Mobile responsive issue - create PR for responsive styling.

**Thoughts** 
- I think when the minutes is a single digit it displays as a single digit but I want it to be double ie 03 instead of 3. It is my formatting that needs sorting because this is happening in hours as well (6:5 instead of 06:05). Ideally I want single digit format for hours and double for minutes.
- Converted timestamp to correctly formatted string and displays perfectly but do now have a "value provided is not in a recognised RFC2822 or ISO format" deprecation warning.
- Removed above formatting and used a quick function to add a zero to single digit minutes when using an accepted format.
- Added same function to sunrise minutes.
- Normally I would merge this back into dev branch and then merge dev branch into master but am doing this via a PR on GH so will be interesting to see what happens. Think it merged into dev and then into master. Looks like it put the commits directly onto the dev branch, my previous way would have displayed the commits on the fix branch then 1 commit to show the merge. Sure it all does the same. Think my way was the long-winded way come to think of it.
- GitHub Pages (which is running off a GitHub pages branch (the only way I could get it working a while back) so it is now behind the master and therefore not showing the latest merge. I want to be able to sync my ghp and master branches. Reverted to master branch and now GHP just shows the readme.
- Tried to checkout the GHP branch locally and created a new branch - VSCode going mental with 40k uncommitted changes. Unsure what is happening.
- Think I might need to run a build and just get this app running off the master. Run the build and changed GHP to run from master - not quite displaying correctly. Npm run deploy got it working - I remember this from a few weeks back.
- Creating the mobile-responsive branch off the dev means it is now 12 commits behind due to the last PR. Not used to this way of doing things. Created draft PR and linked to issue.

### #daysofcode 15/8/20 

**Today's Progress**
- Weather App - mobile responsive:
- Common breakpoints reading - Bootstrap and @thecodercoder suggestions.
- Fixed containers and text for S/M/L Mobiles, Tablets and Desktops using chrome dev tools responsive. Started with mobile-first approach.
- Merged PR back in, closed issue and updated GHP deployment.

**Thoughts** 
- Not played with CSS and media queries in detail in a while as I've been concentrating on JS. I still have a few grey areas so spending some time learning the most up to date methods and tools for making a site mobile ready/responsive.
- Most of my mobile design has been done by just shrinking the width of my browser (to around 500px). I realise now this is insufficient and could go into more detail and use smaller breakpoints.
- I made the new branch off the dev but it was before the sunrise/set commits. This could cause an issue when I merge back in. Will it keep the new branch time setup or the current dev branch. All a bit confusing/worrying. Turned out ok as only merges the files I changed (2 x css files) back into master. Just looks different in GitGraph.
- Stoked I feel way more comfortable with mobile first and responsive design now. 
- Must remember to run build before run deploy for GitHub Pages.

### #daysofcode 16/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Planning week ahead - mainly based around finishing off CV and looking to approach some companies for jnr positions. 
- Super tired today and checking my Youper app, I see I have on aver 1 or 2 bad nights of sleep a week which really lowers my productivity. Annoyingly, I can't always control the variables and it seems to be hit or miss.

### #daysofcode 17/8/20 

**Today's Progress**
- Portfolio Responsive Design - Updated so now all pages are responsive.
- Portfolio Issue - Mentor logged an issue where the tech icons don't reload upon page refresh. Created draft PR and linked issue. Changed icons from relative to absolute path.
- Portfolio icons text - I want to display some short text explaining the name of each tech icon and what it does for those who aren't familiar with the logos (potentially recruiters/HR). Set up branch ready for tomorrow.

**Thoughts** 
- After realising my weather app wasn't actually responsive and fixing that, I am now going through the same process on the portfolio site. Yet again, working with another person's Sass is a pain. I think there are some elements of Gatsby at play too.
- Figured it was the padding on the page links that was causing the overflow. Tidied up lander.
- Tidied About Page.
- Added actual text email address to contact section for extra UX. Envelope icon sends them to an auto compose - but user may not have it setup for the right client.
- The reload issue doesn't happen on the dev server. I need to remove the . to change the path.

**Questions**
- Is the norm to merge a fix/feature branch into the dev THEN into the master, or merge the fix/feature branch straight into the master? Both work but option 1 leaves the dev branch behind meaning when I create a new branch off the dev it is also then behind.

### #daysofcode 18/8/20 

**Today's Progress**
- Portfolio Enhancements:
- Centered page links.
- Added title text to tech icons - hover state now shows name of technology and a brief description for those who don't know the logos by name (recruiters/HR).
- Hover state fix - now return to normal after links have been visited.
- Active page - Current page now indicated.
- Weather App Responsive update - taking average screen height into consideration.

**Thoughts** 
- Added some &nbsp; to align the page link to the centre and adjusted a mobile-s media query to ensure it works across all device widths.
- title text seems slow to load (2 seconds for the first one, pretty quick once you mouse over the rest) so people might not realise that feature exists. Suffices for now, will maybe add some animation in the future.
- Active page not being indicated so checked the Gatsby docs and added an activeStyle attribute.
- Active page styling stops after page reload? Leaving for now but made a note to fix later.
- Noticed my weather app MQs were off. When in dev tools they worked fine in terms of width but my height setting was random and although it looked fine in dev tools, it didn't in reality. I'd love to know that I have my height set appropriately in dev tools responsive so I know my design works when it comes to height as well as width. Looks like 768px is the smallest on average. Adjusted accordingly.

**Questions**
- (How) do you take screen height into consideration when making a responsive design?

### #daysofcode 19/8/20 

**Today's Progress**
- CV/Resume updates - Ensuring all technologies and project info is up to date.
- Typography - limit the number of font families to a minimum (two is plenty, one is often sufficient). Reduced the number of fonts on CV. Matched headings on Portfolio to CV.
- webpack - Docs reading to understand the basics and differences from other tools.

**Thoughts** 
- Minimal code today but still part of the journey to junior. I've been consuming a lot of content (and making lots of notes) over the last few months in relation to the job side (learning roadmaps, resume tips, portfolio reviews, interview experiences and so on) so I already have a CV created. It has been reviewed by a recruiter already and now my mentor will do a review soon. As he knows me and my journey more, he may be able to think of extra things to add/change.
- I'm aiming for some consistency between my portfolio and CV so did some reading on typography and basic (web) design concepts. At the moment I have a few different fonts and weights across the 2 documents.
- webpack differs to gulp (which I have used) and is used in React so taking a look in more depth.

**Questions**
- Does a different weight of the same font count as a different font? Eg Roboto and Roboto Mono Thin.

### #daysofcode 20/8/20 ⁣

**Today's Progress**⁣
- webpack:⁣
- Basic tut understanding manual setup and configuration.⁣
- web pack is a devDependency - devDependencies are modules which are only required during development, while dependencies are modules which are also required at runtime.⁣
- __ - The __dirname in a node script returns the path of the folder where the current JavaScript file resides. __filename and __dirname are used to get the filename and directory name of the currently executing file.⁣
- mode - can be production or development environment. If not set, will default to production.⁣
- Tree shaking - a method of optimising code bundles by eliminating any code from the final file that isn’t actually being used.⁣

**Thoughts** ⁣
- Love how you can publish to GH directly and easily from VSCode (think that is a new feature or at least the GUI/process has a better UX).⁣
- Starting to understand the npm ecosystem a little more. ⁣
- Because I did some work in Gulp/build systems, the concept and process of webpack (at least on a basic level) makes sense. ⁣
- From the YT comments: "Why not Gulp?" > Chris Hawkes: "Nobody uses it anymore. Webpack killed it".

### #daysofcode 21/8/20 

**Today's Progress**
- Resume updates:
- Increase readability - removing ambiguous words, increasing font size, shifting layout
- Add photo.
- Embellish the languages & frameworks with more detail. - Highlight the coaching, team and self-management skills more.

**Thoughts** 
- Mentor CV review yesterday gave some great tips on both content and design. Always great to get extra eyes/thoughts. Some things were obvious that I didn't pick up on myself.
- I've been tracking my coding hours each day since December 2019. Recently I have been spending time on non-code/job-related tasks and the job application process in general. As my objective is to land a position, I have decided to count the non-code hours because they still count toward my Objective (I use OKRs - Objective Key Results for my tracking system).
- CV looks better already. Note to self: don't be afraid to edit existing "designs" made by designers.
- Chat with a former employee of a potential target company. Realising team skills and self-management are strengths I have that aren't highlighted on my CV.

### #daysofcode 22/8/20 

**Today's Progress**
- Job Prep List - Going through a few company sites to pick out keywords and technologies to at least get myself familiar with.
- Updated LinkedIn with my new languages and frameworks.
- CRUD v REST - REST is an architectural system centered around resources and hypermedia, via HTTP protocols. CRUD is a cycle meant for maintaining permanent records in a database setting. CRUD principles are mapped to REST commands to comply with the goals of RESTful architecture.

**Thoughts** 
- Mentor and I will be doing this process in more detail next week but this is good practice to pick out what potential employers may be looking for. 
- For the last 9 months I have been slouched on a sofa/chair whilst working with the laptop on my lap. I feel fine at the moment but mentor mentioned to think about posture now (before its too late). Today I am using a @nexstand_eu stand (keeping my MBA at eye level), wired keyboard and a Magic Mouse sat up at a desk. My neck isn't used to this angle yet but I want to strengthen myself in this more ergonomic position going forward.
- Agile keeps popping up. I did actually teach myself PRINCE2 project management back in 2015 (I looked at project management as a potential career path - wish I would have done the qualification at the time) and did cover a bit of Agile so will check out my notes and ensure they are up to date.
- Doing the same thing with another company to see if any patterns emerge in terms of work approaches/peripheral philosophies etc.
- Already seeing the second company is too advanced for me at this level so checking the culture side.
- Nice to get back into listening to dnb while working. Can be done when I'm doing less focused/taxing work. I missed the energy.
- Sat a dining table and already remembering the importance of a decent chair! Will be investing once I settle.

### #daysofcode 23/8/20 

**Today's Progress**
- N/A.

**Thoughts** 
- Day off with family.
- Caught live stream by ritagirl. Asked for junior dev advice: "don't underestimate yourself and your talent".

### #daysofcode 24/8/20 

**Today's Progress**
- Coding interview prep - (Technical) Interviews can cover theory as well as coding questions/challenges.
- Created a doc for the common JS theory and coding challenge interview Qs.
- Data Structures - Initial look at the common ones.
- Drafted a cover letter template (which will eventually be tailored to specific job listings).
- Had a look at a few companies using Glassdoor.

**Thoughts** 
- I've had an "Interview skills" section on my to do list for a while. This is less on the soft skills and more on the technical side. I played with edabit a while back and plan to look into data structures and algorithms too. @dev.jeanrauwers also suggested getting some practice coding under pressure. I'm not aiming for FAANG so won't be going too deep into the technical interview but having some skills in that area will def help not just my interview process but also the rest of my career. I guess the only way to find out what I'l need to know for interviews is to start doing interviews.
- Bits and bobs kinda day. Don't feel like I have learned too much but definitely laid out and prepared a few paths/documents for future learning. 
- Feeling slightly lost/unfocused due to multiple potential routes of things to do and learn. Referred back to my main objective for focus.

### #daysofcode 25/8/20 

**Today's Progress**
- Data Structures & Algorithms:
- To truly master Algorithms is to understand them in relationship to Data Structures. Data structures and algorithms go hand-in-hand like Yin and Yang.
- An algorithm is just a function that transforms a certain input data structure into a certain output data structure.
- DS/A/DP - All of three of these basically compile to this: knowledge of efficient code placement and efficient execution of code to achieve the best possible result in the shortest amount of time. Algorithms can propel you forward and give you better insight as to what kind of function to use to sort more efficiently, or how to use it correctly. Data Structures and how they work also help you pick what’s best. You learn what operations are expensive in terms of processing and memory. Design Patterns help you set up your structure in conventional, tested, and proven ways. 
- Collating common algorithm challenges.
- Data Structures basics - looking a the most common types and their pros and cons.  Linked lists, Arrays, Hash tables (objects in JS), Stacks and queues, Graphs and trees.
- Code Kata - an exercise in programming which helps software developers improve their skills through practice and repetition.
- Pair programming - an agile software development technique in which two programmers work together at one workstation. One, the driver, writes code while the other, the observer or navigator, reviews each line of code as it is typed in.

**Thoughts** 
- Spent the start of the session getting head around what data structures, algorithms and design patterns actually are (with examples), how they all sit together and why they are worth learning.
- General consensus of which to learn first seems to be data structures although you kinda need to do both at the same time.
- I'm starting to see that I was doing this kind of problem solving when I was using @edabit a few months back. I can also see how having a better knowledge of DS&A can give you more options to solve problems and the ability to select more performant options.
- Look into Katas as suggested by @dev.jeanrauwers. UK interviews in his experience were more around katas and pair programming rather than data structures and algo (more common in the US).
- Brief overview of pair programming and some tips.
- Another day of no code but definitely got my head around a few concepts and will dive in to some Katas for practice.
- Tried to change the scaling on my mouse in terminal to reduce wrist movement. Mac doesn't seem to want to go as high as I'd like.

### #daysofcode 26/8/20 

**Today's Progress**
- Coding challenges - Having a go at some of the classics using Codewars:
- Fizzbuzz (multi-line) kata - basic test passed in under 5 mins. 
- Traversy JS Cardio YT:
- String reverse - under 1 min, using 1 line.
- String reverse (without using reverse()) - 25 mins. Lol.

**Thoughts** 
- Complied a lot of theory qs and coding challenges, now time to answer them and build that interview muscle up. 
- I was told a while back that the whole interview side was a different skill in itself which needed some time to spend on. I was secretly hoping that wasn't the case and a decent portfolio would do the trick. I now see that a lot of time is needed for this area of learning and deserves as much time as a new framework at least. Worth putting the time in though, it will lonely serve me going forward.
- Cool to see in CW you are encouraged to write your own tests as you try to complete the kata, as you would if you were writing production code.
- Full test suite "ATTEMPT" is a cool option to get used to optimising the code. I passed the sample test but not the full test according to the requirement "Every line should have less than 4 characters". How tf do I do that? And WHY? Guessing this is an advanced version of fb, will come back.
- CW seems to have slightly more advanced variations of the classics. Can't seem to find the basic versions on here (annoyingly).
- Highly irritable today for some reason. Switched to edabit to try and find equivalents of the classics.
- Be great if there was a playlist of the classics - made a note for feature request to CW.
- Quick refresher on one liners / arrow syntax. Am proper rusty on the basics! Could do with a debugger refresher too.
- Desk and mouse is starting to strain my neck - defeats the point in me moving from a sofa/slouch combo.
- Good to be back in the JS gym.

### #daysofcode 27/8/20 

**Today's Progress**
- Coding Challenges:
- Reverse string - not using reverse(), using a string, an array, incrementing and decrementing for loop variations, for of, for each and reduce().
- Palindrome validation - easy.
- Reverse integer - Return as an integer not a string (parseInt()), include negative numbers.
- Capitalize letters - Return a string with the first letter of every word capitalized. 

**Thoughts** 
- The constraints and variations are really making me think, I like it.
- Tried sleeping with mouth tape to improve nasal breathing last night. My deviated septum meant that I woke up probably because I couldn't breathe so not feeling too energetic this morning.
- I'm embarrassed by how much I have forgotten but I guess that is what happens when you learn so much stuff. Also glad that there isn't the expectation to remember everything (a belief I had before I started coding). I may not remember much, but bottom line, give me a few mins and google (or my own notes) and I can get sh*t working.
- I don't think I've ever written a forEach. Higher order functions have been on my list for ages, maybe its time to dive in.
- Just googled the capitalisation one. Not used substring before and had no idea where to start.

### #daysofcode 28/8/20 

**Today's Progress**
- Job Prep List Updates - Brief overviews (shallow learning) of:
- React v Angular - React is a library, Angular is a framework.
- Angular.
- BitBucket - Alternative to GitHub.
- TypeScript - Why use it and weak v strong type systems.
- React Native.
- Cloud computing - Created new doc and covered general concept, services, benefits, cloud types (public/private/hybrid), types of services (IaaS/PaaS/Serverless/SaaS) common uses and providers (AWS/Azure/Google).
- Lazy Loading - a design pattern commonly used in computer programming to defer initialisation of an object until the point at which it is needed (usually images/vide/iframes below the fold). It can contribute to efficiency in the program's operation.
- SOLID - Main principles: Single responsibility, open closed, Liskov substitution, interface segregation and dependency inversion. The intention of these principles is to make software designs more understandable, easier to maintain and easier to extend.
- Node.js.
- MongoDB - a document database, which means it stores data in JSON-like documents.

**Thoughts** 
- Slight pivot and few things added to list after mentor chat yesterday. Working way through them this/next week. 
- Upping the hours the next few days so working more on pomodoros and pace to improve work rate sustainability. I work most days with a virtual coworker so we are now encouraging and reminding each other to take proper breaks (get up, fresh air, stretch, no devices etc).
- Cool to learn a bit more about cloud. Can see me getting more into it in the future.
- Super passive day of "shallow" learning but great to know what some more terms and concepts are that I always see in job listings (and company sites) but hadn't got round to looking at and getting a grasp of yet.
- My curated collection of deep house mixes (which I eventually want to build an app around) has really got me in the zone today.
- Guess one of the main benefits of today's learning is a further understanding of what tools are available when it comes to development.

### #daysofcode 29/8/20 

**Today's Progress**
- Redux.js:
- DevEd tut - refresher on application level state management.
- Store - globalised state.
- Action - describes what you are going to do (think Event).
- Reducer - describes how your actions transform your state into your next state. Action called, reducer checks which action then modifies store (think Event Handler).
- Dispatch - execute the action to the reducer, store gets updated.
- combineReducers - groups all your reducers.
- Redux DevTools - Chrome extension for debugging application's state changes.
- Provider - via react-redux, connects global state/store to entire app (by wrapping the App component).
- useSelector - via redux, allows you to extract data from the Redux store state, using a selector function.
- useDispatch - hook returns a reference to the dispatch function from the Redux store. You may use it to dispatch actions as needed.
- Payload - the part of transmitted data that is the actual intended message.
- Mosh tut - Pros and Cons of Redux, Functional Programming (inc Function Composition, Lodash, Currying, pure functions, immutability), Redux fundamentals & Bug Tracker App.

**Thoughts** 
- As @developedbyed says, you can get by with passing props or useContext with your own/smaller projects but larger scale apps (read: actual jobs) may use it hence why I am having a look.
- Can already see why you wouldn't need Redux for small apps = so much to set up to get going! But, can also already see how that setup is beneficial when you are dealing with multiple files and state etc.
- I actually prefer working on my own projects rather than tuts nowadays = I can listen to my music and time flies.
- Love how the RDT GUI visualises the actions and the state in the form of a chart(showing connections) as well as a classic tree. Also shows the Diff(erence) = the previous state. Some other cool features like playback and skip/jump.
- Not sure why we now have 3 index.js files (albeit in 3 different locations). Surely that can lead to some confusion?
- My eyes are feeling dry - must remember to blink more. May check out some glasses.
- Mosh tut seems to be going into a lot of foundational theory. Little irked as I want to learn Redux but all useful stuff no doubt (vid is part of a bigger course tbf). Skipped the last few sections to get to Redux. Probably could have chosen a more specific tut, my bad.
- Like how Mosh has an exercise so you have to go think for yourself.
