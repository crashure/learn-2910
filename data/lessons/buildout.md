#Lesson buildout - Project Build Out
ACIT2910 - BCIT - Spring 2017

##Introduction

How **DO** we actually build out a project?

There is no single "recipe" for all projects, and a back-end heavy project
is likely to be built a bit differently than a front-end heavy project.

My strategy revolves around four phases:
- Database
- Webpage Template
- Starter Components
- Elaborate Usecases

The project is built out iteratively, one phase at a time. The general "recipe"
for a phase:

<img class="scale" src="/pix/build/build01.png"/>

##Some truths about this "recipe":

- Assumed: some design!  
You have to have some clue about where you are heading, so you can
recognize when you get there. This could be some design for the
project as a whole, or for the phase you are working on.

- No single best way  
There is no single best key to build a phase.
If you seek it, you will spend your time in the search rather than in construction.
Instead, do it an arbitraty way the first time, and improve on your
process with each successive project. You will find "your path".

- Agile: client picks next usecase  
If you are following an agile process, the client determines what should
go into the next phase, not you. The next phase should build the next
part of a project that is critical, or for which you or your client need feedback.
Be wary of choosing the easiest stuff to handle in the next phase.

- All methodologies: need a starter  
It doesn't matter which methodology you plan to use to build a project, or
even a phase of it - you need some form of a starter.
This could be a standard set of components or supporting frameworks
that you want to reuse, or simply that you are comfortable with.  
The idea is, if possible, to choose existing stuff to handle a bunch (80%?)
of the functionality, so that you can concentrate on the unique requirements
of the project at hand. Yes, this is another example of the 80/20 rule.

- Need a methodology & tool set!  
You need to choose a methodology and a tool set before embarking on the project.
If you haven't picked one, then phase zero should be investing enough time to
investigate the candidates and choose those that you will use.
This keeps your focus on the project, not the tools, as much as possible.

###Agile?

Wait a minute - this sounds like agile, doesn't it?

Sort of.

With a small project, each phase will take considerably less than
the normal iteration using agile.

With a larger project, each of "my phases" would take one or more iterations.

<img class="scale" src="/pix/build/build02.jpg"/>

##Database Phase

I start with the "database", because not too much will happen without it.

The term "database" is used loosely, as there could be any number of
choices for data persistence: relational database, document database, XML 
documents, and so on.

The driving force here is performing sufficient data analysis to make
sure that I understand what data the client needs to make the decisions
they are relying on a project for, and which of the data needs to be
persisted for later reporting or analysis.

There is no single tool for this.
You might use a data modeling program, or a UML diagramming program.

With a complex project, the visual artifacts for this phase might include
entity-relationship diagrams, workflow diagrams, and possible generic
class diagrams (not programming language specific).

I usually try to come up with a data definition to suit the data model(s),
for instance DDL for an RDB, or DTDs or schemas for data to be
persisted in XML.

Coming up with the data definitions is a way of uncovering missing visual
components, and vice-versa. If I can't define it, I don't understand it.

With a simple project, the data definitions might be all you need :-/

A sample ERD:

<img class="scale" src="/pix/build/build06.png"/>

In addition to suitable DDL script, I will try to come up with
a DML script to populate the datastores I envision, with test or starter
data. Again, this help me make sure I have thought of everything.

This could be part of an iterative cycle during the database phase.
Basically, repeat all of the above until I have a pass through the steps
without anything new or changed.

A sample DDL script, for Postgres:

    -- Create table:
    CREATE TABLE land_registry_price_paid_uk(
      transaction uuid,
      price numeric,
      transfer_date date,
      postcode text,
      property_type char(1),
      newly_built boolean,
      duration char(1),
      paon text,
      saon text,
      street text,
      locality text,
      city text,
      district text,
      county text,
      ppd_category_type char(1),
      record_status char(1));

Note: it is entirely possible that the client has an existing database
prescribed for use with a project. In such a case, I make sure that
I have the DDL for it, and a representative data sample to use for testing.

##Template Phase

Phase two, for my projects, is to build a webpage template.

I usually try to start with a single layout for every page, and wireframe it.

The boxes that result from this end up guiding the implementation to come:
they are placeholders for content, and I can name them here and plan
methods later to fill each panel with "real" data.

Note: this isn't the only way to do this, just how I go about it.

With a larger project, there could be several templates or layouts, for instance 
one for a landing page,
one for for a product list, and one for individual items (eg for ordering).

A sample wireframe:

<img class="scale" src="/pix/build/build07.jpg"/>

I use a CSS framework, typically Bootstrap, to mock up representative pages.
If I am worried about layout intricacies, I will set arbitrary bold colours
for each panel, so I can see how the webpage looks, in context. 
The result is ugly, but effective.

Larger projects typically have larger budgets, and it is common for the client
to hire a graphic designer to come up with wireframes, colour palettes,
and page mockups. In such a case, designer and developer work together,
and the designer may even have final approval over the look & feel of the site.

The design and mockups usually go through several iterations, with small and
large suggestions from the client at each, before being approved, concluding
this phase.

##Starter Components Phase

Given data to work with, and intended presentation, phase three sees support components
built for everything so far.

I usually build the pieces in the order shown below.

First up is the template logic, which I use a "base controller" for.
It provides for menus, and assembly of a finished page.

Second up are the models - O-O classes used to manipulate the data, either at
the collection level (customers) or at the entity level (one customer), or both.
Classes would usually correspond to database tables, but don't have to.

Third up are controllers - incoming request handlers. I usually have one for
each page in the site, each having methods appropriate to the panels that
the page's template/layout provides.

Fourth up are the views - HTML fragments corresponding to the template panels.

All of this follows the "model-view-adapter" pattern. Models have no HTML code,
views have no PHP or Java logic, and the
controllers access model data and pass substitution parameters to their views.

This is typical of a server-side app, and very different from one that you build
with much of the business logic implemnented in Javascript in the browser!

I do use Javascript, but try to do at a "widget" level. Think Bootstrap components,
some of which might be complicated. They can still be rich, and use AJAX, but
they don't define the apps that I build.

An architecture diagram of the framework I use:

<img class="scale" src="/pix/build/appflowchart.png"/>

###Support Components

The tail end of phase three often involves creating the support
components that will be needed during phase four.

- Business delegates - classes that implement or connect to business logic
- Helper classes/functions - stuff I know I will need
- Third party libraries - useful stuff I plan to incorporate
- Services - adapters for services I know will be needed

These are often just empty shells at this point, but making
them helps define the interfaces, i.e. how they will each be
used in phase four.

An example, showing some expected components on the right side:

<img class="scale" src="/pix/build/build03.png"/>


##Elaboration Phase

The fourth phase is where things get "completed", following my "recipe".

I do this one usecase at a time. For each:
- flesh out controller methods (subusecases)
- complete or enhance view(s)
- enhance model(s) as needed, eg searching
- flesh out or enhanced support component(s)

This is standard O-O usecase realization.

It is done using agile, choosing usecases to elaborate according to
the iteration length and the planned work effort (think back to the 
project plan!).

An example showing four usecases to elaborate, with a shared 'validate user' subusecase:

<img class="scale" src="/pix/build/build04.png"/>

If any of the top three usecases were selected for the current iteration,
that iteration would also have to include fleshing out the 'validate user'
subusecase.

Repeat until no usecases remain.

##Wrapup

I have to stress that the above is only *my* "recipe".
Every project is different. The tool set chosen and the experience that
the developer team brings to the project will affect the "recipe"
steps and completion time.

_Your mileage may vary. Results not guaranteed. Some lottery prizes may
have already been won. _

