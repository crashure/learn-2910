#Lesson testing - Testing, Seriously
ACIT2910 - BCIT - Spring 2017

##Testing Plan

A testing plan documents the strategies that will be used to verify proper operation
of a software product being built. This includes identifying the features or components
that need to be tested, the testing tasks, and the acceptance criteria.

A testing plan is **not** a statement like "We will test thoroughly".

A really large software project might have a testing plan that would fill a book,
while a small project might have a bullet list of things that need to be
tested in specific ways.
You don't need to get carried away, but you do need to plan
testing quality and quantity to suit the scope and budget of
a development project.

This lesson is not meant to be comprehensive, but attempts to identify a
handful of good testing practices that you should consider, i.e.
a variation of the [80/20 rule](http://www.time-management-success.com/pareto-principle.html).

Specifically, we will talk about four kinds of testing:
- Error handling
- Unit testing
- Functional testing
- Experience testing

##Testing - Who Needs It?

A $1000000 killer product ...
- without code coverage, only $100000
- without unit testing, $10000
- without comments, $1000
- without UX, $100

##Error handling

Error handling refers to "hardening" your code so that it doesn't break
if invoked with other than expected data.

This could include many things:
- providing default values for method or function parameters
- testing value ranges for parameters, rather than assuming they are correct
- double-checkung the "facts", like counting the number of items in an order
to make sure they add up to what an order summary record suggests

Server-side code should assume the worst, namely that any incoming request
might come from a compromised source (eg. javascript exposed client-side
and then altered).

Some of the common things addressed in error handling:
- No response
- Token not valid
- Form validation
- Missing parameter
- Malformed data
- Non sensical data

Error handling should be a standard practice when programming,
not an afterthought or a retro-fit.

Error handling is done both client-side and server-side.

<img class="scale" src="/pix/testing/test01.jpg"/>

##Unit testing

Unit testing is a style of testing where you write test classes using
a test framework, with multiple tests each addressing a single potential
failing in your project.

Tests are usually grouped by the class being tested. For instance, CharlieTest would
be the unit tests for your Charlie class. CharlieTest would :
- extend the appropriate testing framework superclass, eg TestingUnitTest
- have a setup() method, to establish common data for all its tests
- have a teardown() method, to cleanup after a test
- have multiple testX methods, each testing a different condiition, eg.
testMissingName() and testNameTooLong()

The test framework would find all the classes in your testing folder, 
which extend its superclass, and "run" them. Each would be "run" by
instantiating the test class, invoking its setup(), invoking one
of the test methods, and finally invoking its teardown(). This
would be repeated for every testX method in the test class.

A project with 20 classes might have 20 unit test classes, each of
which contained multiple tests. A complete unit test of the project
might then involve dozens or even hundreds of specific tests.

Unit test your models and business logic.
Unit testing is typically server-side.

###Regression Testing
The intent is that unit tests are run as part of [regression testing](https://en.wikipedia.org/wiki/Regression_testing).
Every time you add something to the project, all the unit tests are run again,
to make sure there are no failures, i.e. that you didn't break anything
that was working before.


###Test-Driven Development
[Test-driven development](https://en.wikipedia.org/wiki/Test-driven_development) suggests:
- write a comprehensive set of unit tests before starting main code
- use failures in these to guide remaining code to implement
- if a defect is encountered, "provce it" by writing a test case for it,
and then refactor or fix the code so that all unit tests pass, including
the one evidencing the defect

##Code Coverage

Code coverage is a measure of how much of your code is unit tested.

It is one of the KPIs for the quality of a software project.


<img class="scale" src="/pix/testing/test09.gif"/>

##Functional testing

Functional testing refers to whatever testing you perform to ensure
that your project meets the functional requirements, i.e. that
the usecases are properly realized and implemented.

A clever developer will have expressed their usecases so that they
are measureable, and the success criteria would form the basis
of functional testing :)

Functional tests can be "black-box" or "white-box".

"Black-box" testing is done without any assumptions about the inner
workings of your code. This would typically be done by a tool which
plays the role os a "user agent" (browser), and which tests assertions
about expected webpage contents after specific actions or sets of actions
are performed.

"White-box" testing is done with explicit access to the source code.
It operates similarly to black-box testing, except that the tester
has inside knowledge about scenarios that might break a usecase :-/

The goal of functionality testing is client acceptance - a go/no-go decision.
"If all these functionality tests pass, I will pay you".

Functional testing involves setting up and "playing" a set of automated
scripts, to replicate user actions in the performance of usecases.

Functional testing is typically client-side.

<img class="scale" src="/pix/testing/test04.gif"/>

##Experience testing

Straight out of UX/UI, experience testing is measurement of the user
experience, by the different stakeholders or their representatives, 
and then analysis & summarization of the results.

Some specific things that might come from this:
- ensuring mobile friendliness of the app
- testing browser compatibility of the app

The goal is non-functional requirements acceptance from the client.

Experience testing is typically client-side.

<img class="scale" src="/pix/testing/test05.gif"/>

##Golden Rules

If a server/service falls over – client loses business, you are fired/banished/sued

If a service breaks – you are fired/banished/sued

If a client breaks – you are demoted/shamed/whipped

**Server-side code needs to be bulletproof**

Smooth-talking may save your bacon once.

<img class="scale" src="/pix/testing/test10.gif"/>

##Beyond Mere Testing?

Testing is best integrated into your code repository, as part of a **continuous integration**.
Github supports this through [travis-ci](https://travis-ci.org/), and you will be adding it
to your projects :)

<img class="scale" src="/pix/testing/test03.gif"/>

##Wrapup

Testing is important, but it can be hard. Fortunately, there are some
simple techniques that will improve confidence in a product without
breaking its development budget.

Would you like to learn more?

- Wikipedia has a long, but surprisingly complete article on [software testing](https://en.wikipedia.org/wiki/Software_testing)
- TutorialsPoint has a good but simple article on 
[errors and exceptions handling](https://www.tutorialspoint.com/javascript/javascript_error_handling.htm)
in Javascript
- [Software Testing Fundamentals](http://softwaretestingfundamentals.com/functional-testing/)
- [What users do](https://www.whatusersdo.com/clients/resources/what-is-user-experience)
- Wikipedia has an [introduction to code coverage](https://en.wikipedia.org/wiki/Code_coverage)

Javascript unit testing frameworks:
- https://github.com/facebook/jest
- http://facebook.github.io/jest/
- https://github.com/unitjs/unit.js

Javascript unit testing as part of continuous integration:
- https://github.com/dwyl/learn-travis
- https://gist.github.com/nackjicholson/1cbd083fd74839ed4dfe
- https://docs.travis-ci.com/user/languages/javascript-with-nodejs/#Default-Test-Script
- http://www.codeblocq.com/2016/04/Setup-Travis-CI-with-your-node-project/

Javascript code coverage:
- https://tntim96.github.io/JSCover/
- http://blanketjs.org/

Javascript functional testing:
- https://www.sitepoint.com/javascript-functional-testing-nightwatch-js/
- https://testcafe.devexpress.com/
- https://www.joecolantonio.com/2016/06/14/top-8-essential-javascript-automation-frameworks/

Experience testing:
- http://www.dtelepathy.com/blog/business/14-best-tools-for-evaluating-user-experience

<img class="scale" src="/pix/testing/test07.png"/>

