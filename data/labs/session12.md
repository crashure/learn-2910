#Lab session12 - Loose Ends
ACIT2910 - BCIT - Spring 2017

##Goal

We want to help you with suitable unit & functional testing.

You should have learned how to do a simple unit test and integrate with
travis-ci, but you need to do this for your app!

You should have learned how to create and run a simple functional test,
but you need to have a suite of these for your app!

We will help you to set these up.

## Unit Testing - Too Late!

I checked all of the team repositories, trying to install and run each one,
as well as taking a look at your code.

ONE of the eight teams has models, and unit testing for them.
Good job :D

The other seven teams do not appear to have anything close to models,
hence no chance of performing any unit testing. 
At this stage of the project, you do not have time to re-architect
your app and complete meaningful unit testing.
Take the hit and worry about functional testing - it will be enough of a
challenge!

The travis-ci for trivial only unit testing is kind of pointless, and should probably be removed.

## Functional Testing

Most of the teams have at least one functional test in their repo.
One team gave the notion lip service, but there is a "functional
test" in their repo. Some of the teams didn't complete this :(

From looking at your code, I am convinced that you **NEED** functional
testing, if you are have reasonable odds of completing the app!

Session 11 suggested six functional tests for you to consider.

Seriously, you need to make sure that those testcases work with your app.

There are probably a dozen others that you can think of, and having those
in your test suite is a good idea.

Have someone not working on the order page script the tests. 
They should determine if the app is working the way it **should** work,
not it if behaves the way it does, good or bad.

##Submission

One member of each team should add a readme note in the session 12 dropbox,
so that we can provide feedback on your testing.

Make sure that your dropbox note, *or* the readme in your repo, *or* some
other directions file clearly named and easily found (i.e. in the root of your repo), 
tells us how to install and run your
app, and how to run the functional testing for it.

Each of the teams should see a HELP card on their Trello board, with some
feedback from me about my testing experience mentioned above.
