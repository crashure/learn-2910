#Mini-Project - Fast Food Outlet
ACIT2910 - BCIT - Spring 2017

##Project Overview

The purpose of the project is to let you apply the techniques 
and skills from earlier courses, using agile development and
collaborative workflow.

In teams of four or five, you will be building a small but complete webapp, 
in this case to support a fast food outlet on a distant planet. 

This will be done in four or five iterations, with specific expectations for 
the deliverables and the process used for each stage. 
There will be one or more graded deliverables for each stage.

Week 1 is spent team building and planning, which leaves us four "real" 1 week iterations
to build the webapp.

##The Business

The fast-food outlet you are building a website for will need a planet-appropriate
menu, with 12-24 items.

The website will include a public-facing component (for ordering), an operational component 
(to help the kitchen), and an admin component (for management).

##Ordering

Ordering is to be handled with a hierarchical kiosk-style tool (think McDonald's
or A&W). Items should be priced reasonably, using [Imperial Credits](http://starwars.wikia.com/wiki/Galactic_Credit_Standard) for currency.
Star Wars, the Old Republic has a [lengthy article](http://www.swtor.com/community/showthread.php?t=442915) 
to help determine the value of
an Imperial Credit on Planet Earth ... to make a long story short, it is about $0.62USD or $0.50CDN.

Your app does not need to collect payment - we will be using the new Extra
Special Payment (ESP) merchant system for that. You do need to track sales,
however, for management.

When a customer places an order, it should be assigned a unique and ascending order number.
The unfilled orders should be displayed onpage, similar to what you see at McDonalds.

##The Kitchen

The kitchen should be able to prepare food items, one kind at a time, in quantities of 1, 2 or 6.
Each "preparation" should have an artificial delay, initially set at 5 seconds.
Only one kitchen is in operation, with one thing cooking at a time,
so the chef needs to plan production carefully.

Your app should show the outstanding orders, the same way that earth-bound fast food
outlets do. You can limit the number of outstanding orders to six, if it makes life easier.

You are allowed to cook more than one of something at a time, for instance planning
to handle the burgers for several orders at a time.

Keep track of what is cooked and ready to be bagged, but watch the time - any prepared food
that has been sitting under the heat lamps for more than 5 minutes needs to be
discarded, and the cost of wasted food is considered for management reporting.

##Admin

Management wants to know how much money they have made, broken down by order or by menu item.

Provide CRUD for the menu, so they can add or remove items, and adjust pricing.

Provide store closing and opening buttons: after closing, no further orders 
should be accepted; on opening, all transaction data should be reset.

##Security

Access to the back-end should be restricted. Provide for cook and boss accounts, 
the details of which will need to be part of your dropbox submission when the time is right.

##Deliverables

Documents:
- team agreement (session 2)
- project plan (session 3)
- webapp design (week 2) ... research during weeks 1 & 2, based on above
- project presentation (week 5)

Repositories:
- project tracker (session 4) ... we'll pick one in week 2
- project codebase (weeks 2-5) ... can include docs

##Technology constraints

The resulting webapp needs to be deployable on Linux.
A standard AMP stack is available. I have a deployment testing
script can you will configure as a webhook in your project
codebase repository.

Anything beyond this will need to be explored!

##Programming Targets

Code like you are getting paid for it - comments, structured,
sensible.

Code like you need to prove your results - unit testing, possibly continuous integration.
There will be beta testing, with multiple customers, during week 5.

Code for your portfolio - you want to be proud to show the webapp
to a prospective employer.
