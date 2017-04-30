#Lesson agile01 - Agile Project Management
ACIT2910 - BCIT - Spring 2017

##Project Management

Traditional tools can be very helpful coming up with a viable
project plan, most specifically a list of tasks that need to
be assigned and completed in order to deem the project complete.

Traditional project planning is relatively rigid, however, and
doesn't adapt well to many of the problems that arise in the
execution of a project plan, like scope creep, unreliable
estimates, and flawed design or implementation.

### $64 Questions

At any point in time, developers are likely to have two burning questions:

- When will we be done?
- What do we do next?

The "agile approach" is a software development methodology which 
addresses these issues and questions. It is considered an
"industry-accepted best practice" for small and medium projects.

##Manifesto for Agile Software Development

Agile development is more of a philosophy rather than a rigid
set of rules and practices. It values:

- **Individuals and interactions** over processes and tools
- **Working software** over comprehensive documentation
- **Customer collaboration** over contract negotiation
- **Responding to change** over following a plan

In case you haven't gathered, the practices that are considered
less worthy for agile development are those held in high regard
by traditional development or project management methodologies.

##Agile Development Disciplines

Agile development typically organizes needed skill sets into seven disciplines:

- Modeling (data, process, UX)
- Implementation (coding & documentation)
- Testing (unit testing, TDD)
- Deployment (business process pipeline)
- Configuration Management (development, staging, production)
- Project Management 
- Environment (tool set)

You have learned about some of these already, in earlier courses,
while the discovery of others awaits you :)

Each team member doesn't need to be expert in all of these,
but they need to understand and leverage them.

##Agile Project Management

What, then, is agile project management?

It involves four things:

- Iteration driven
- Customer prioritizes
- Wall tells the story
- Scrums help the team manage

<img class="scale" src="/pix/agile/process.png"/>

The project unfolds in a series of fixed length iterations, sized
appropriately to the project. At the beginning of each iteration,
the customer prioritizes the backlog of tasks. The highest priority tasks
are selected to be the sprint backlog, i.e. a set of tasks to allocate
and complete during the current iteration.
At the end of each iteration, you should have a working (but feature incomplete)
version of the software being built.

The team holds daily scrums (stand-up meetings) to keep everyone in the loop,
and for early warning of issues.

At the end of an iteration, the team would review progress, allow the customer
to re-prioritize tasks, and then plan the work for the next iteration.

##Agile Artifacts

Agile methodology still has deliverables, but not as many or as formal
as traditional development:

- Release plan - vision
- Iteration plan – what next?
- Design – as needed

##Agile Granularity

Agile planning has different levels of granularity.

At the coarsest (top level), we talk about **epics**.
Each might be a planned "release" or version of a larger
product under development.

Each epic contains a number of features, which we might refer to
as **user stories** (or just "stories").

Each feature/story contains a number of **tasks**, smaller units of work
that would be assigned to a developer (or two), and which can be completed
during an iteration.

Epics → User Stories → Tasks

##The Story Board, a.k.a. The Wall

Key information about what is happening in an agile project is
depicted on the **Story Board**. It is as large as needed,
and often posted (literally) on a wall in the project
work area.

<img class="scale" src="/pix/agile/wall.png"/>

##Agile Metrics

Progress in an agile project is measured several different ways:

We keep track of "burndown", namely units of work planned
and completed. This is both for the current epic/release,
as well as for the current iteration.

<img class="scale" src="/pix/agile/metrics01.png"/>

We track "velocity", namely the number of units of work that have
been completed during an interval, and which would be expected
for upcoming intervals.

<img class="scale" src="/pix/agile/metrics02.png"/>

##Blending Agile & Traditional

It is possible to blend other software development methodologies
with agile.

Epics, for instance, are often the result of object-oriented
use case realization.

Features could be developed using more of a traditional "waterfall"
methodology.

User stories or tasks (depending on the size of the project)
would be developed using agile, focusing on the current iteration.
A larger project would have stories made up of tasks, while a smaller project would just have tasks.

Put this all together, and you get a perspective called "Kanban + Scrum".

<img class="scale" src="/pix/agile/kanban.png"/>
 
##Agile in Action

The following three images depict an agile project's storyboard
over time. You can see "jobs" moving from left to right as work
is completed.

We choose an epic to work on (move it one column right), and its features.
The highest priority features start their way across the board, with
as much design as is needed so that we can specify the stories or tasks
that need to be scheduled.

<img class="scale" src="/pix/agile/action01.png"/>

Work is done; tasks are moved to the right; and features are moved to the
right as they progress.

<img class="scale" src="/pix/agile/action02.png"/>

You might be working on tasks for multiple features, and on features for
different epics. Multiple epics could be in progress at the same time,
in different stages of completion.

<img class="scale" src="/pix/agile/action03.png"/>

When all of the features in a planned release reach the rightmost column,
then their epic would be put in its rightmost column, and it would be
deemed ready for release.

##Agile Elaboration

At the start of a larger project, you would probably identify all of the epics,
or planned releases. You would identify the major stories in each, and all of the
high priority stories that the customer expects to see first.
Finally, you would identify the tasks for the highest priority stories,
at least to the point of having enough work for an iteration or two.

<img class="scale" src="/pix/agile/elaboration01.png"/>

As the project unfolds, additional stories are uncovered, and more tasks are
uncovered or specified.

<img class="scale" src="/pix/agile/elaboration02.png"/>

By the end of the project, you have substantially more tasks than when you started out!

<img class="scale" src="/pix/agile/elaboration03.png"/>


##The Evolution of Agile

Agile development isn't perfect, and continues to improve.

One favored perspective is [Modern agile](https://www.industriallogic.com/blog/modern-agile/):

<img class="scale" src="/pix/agile/modernAgile.png"/>


##Wrapup

There you have the basics of agile project management!

Would you like to learn more?

- The original [Manifesto for Agile Software Development](http://agilemanifesto.org/)
- Martin Fowler talks about [The New Methodology](https://martinfowler.com/articles/newMethodology.html) amonst other things
- Craig Larmann wrote a [book](http://www.craiglarman.com/wiki/index.php?title=Book_Applying_UML_and_Patterns)
still in widespread use today, and contributed to the [Scrum Primer](https://less.works/less/scrum/index.html); 
he used to teach at BCIT too
- The team behind "modern agile" [blog](https://www.industriallogic.com/blog/) about many interesting things
