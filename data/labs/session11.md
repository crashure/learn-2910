#Lab session11 - Functional testing :)
ACIT2910 - BCIT - Spring 2017

##Goal

You want to test proper functionality of your app, from the user perspective!!

We want you to explore one of the functional testing frameworks below, and
get one sample functional test working.

##Constraints

Per yesterday's discussion at the beginning of class, we can provide
the following constraints to limit the complexity of your apps.

-  maximum orders open at a time: 10 (suitable message displayed asking user to try 
again, without losing their order info)
- maximum items in an order: 10 (don't let them add more)
- maximum quantity for any single item in an order: 6
- delay for cooking a single item: 5 seconds
- how long until prepared food spoils and has to be tossed: 2 minutes

Some of these may change, the most likely being the number of open orders
(for the bug bounty attacks).

## Clarifications

- Consolidate products in an order. If it already contains 1 "fries" and
a second is added to the order, treat that as one line item with an
order quantity of 2

## Behaviour Driven Testing

Functional testing is behaviour driven, i.e. from the perspective of
a user of your app. Our specific concern is with the ordering, as
that part of your app is public-facing, although there is merit to
doing similar testing to make sure that the kitchen aspect of the
app works as intended, for your "cooks".

Functional testing is usecase driven, and is meant to mimic the
UX of a website user. The testing frameworks let you script
the usecase, with assertions about what the result should be.
It does not test the appearance or pleasentness of the app,
but rather the proper functioning of it.

An example of a test script for a login:

    module.exports = {
      'Login test': function (client) {
        client
          .url('http://foobar.qux/login')
          .setValue('input[name="email"]', 'foo@bar.com')
          .setValue('input[name="password]', 'p455w0rdZ')
          .click('button[type="submit"]')
          .assert.containsText('main', 'News feed')
          .end();
      }
    };

Another example, which navigates to google.com and searches for "rembrandt van rijn", 
then verifies if the first result is the Wikipedia page of Rembrandt.

    module.exports = {
      'Demo test Google' : function (client) {
        client
          .url('http://www.google.com')
          .waitForElementVisible('body', 1000)
          .assert.title('Google')
          .assert.visible('input[type=text]')
          .setValue('input[type=text]', 'rembrandt van rijn')
          .waitForElementVisible('button[name=btnG]', 1000)
          .click('button[name=btnG]')
          .pause(1000)
          .assert.containsText('ol#rso li:first-child',
            'Rembrandt - Wikipedia')
          .end();
      }
    };

## Functional Test Cases

Here are some minimal functional test cases:

- John wants to order 1 X
- Paul wants to order 1 X, 1 Y and 1 Z
- George wants to order 1 X, 1 Y and another X
- John, Paul & George want to order as above, but all at the same time
- Ringo wants to order the most amount of food possible (6X, 6Y, 6Z, ...)
- Justin wants to order 1 X and 1 Y, and then cancel the X and substitute 2 Z
instead

You would use functional test cases to ensure proper operation of your app
under all foreseen circumstances.

This beats the heck out of having a manual checklist for testing,
as these functional tests are repeatable!

## Functional Testing Tools

These tools run on your system, either headless (command line)
or inside your browser. Personally, the headless approach
appeals to me, since it shouldn't be messed up by faulty CSS.

The tool that looks most useful is [Nightwatch.js](http://nightwatchjs.org/).
It is the one that the examples above come from.
A complimentary tutorial is available form [Sitepoint](https://www.sitepoint.com/javascript-functional-testing-nightwatch-js/).

If you are using Angular in your project already, [Protractor](https://github.com/angular/protractor)
is meant specifically to provide functional testing for such an app.

If you are using Mocha in your project already, it has builtin provision for
functional testing in addition to unit testing.

If you want to unleash the full power of the force, consider signing up for a
free 30-day trial of [TestCafe](https://testcafe.devexpress.com/),
which has a visual test case builder!

Note: it would be ideal to incorporate functional testing into your continuous
integration, but most are designed to run client-side only.
Some of the headless tools might suit CI, but I haven't ahd a chance
to properly investigate that.

##Your Job

Investigate a tool or two, pick one, and complete one of the above test cases.

This doesn't have to involve the entire team ... I suggest tasking one team
member, or a pair, to pursue this spike.

##Submission

One member of each team should add a readme note in the session 11 dropbox,
with instructions for running your functional test.
