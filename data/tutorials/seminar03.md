#Tutorial seminar03 - Project Plan  
ACIT2910 - BCIT - Spring 2017

##Goal

The objective of this seminar is to produce a workable project plan for your
fast food webapp. Rather than being super formal, the artifacts from this
seminar will be two diagrams: one depicting the work breakdown structure
(WBS) and related tasks for your project, and one depicting those
tasks in sequence, with calculated completion data.

We are going to call the latter diagram the "project diagram". 
It might be given a number of different names when discussed in
different contexts, such as project network diagram, precedence diagram,
project activity diagram, or arrow diagram; but we will keep things simple.

## 1 - CPM Exercise

### 1.1 Background

The intent here is to plan preparations for a celebration party, or a 
drowning your sorrows party, as appropriate, for your favorite sports team. 
I am picking on the Canucks :-/

It is 5pm. The Canucks game is on at 7pm.  
You have chores to do first.  
You are on your own.  
_Will you be ready in time???  
If not, when will you be ready?_

Work Breakdown:
- Take the garbage out (10 minutes)
- libations store run (30 minutes)
- convenience store run for munchies (20 minutes)
- vacuum the living room (15 minutes)
- clean the bathroom (30 minutes)
- clean out the fridge (15 minutes)
- hide the dirty laundry (10 minutes)
- put up party decorations (20 minutes)

There are precedences, i.e. necessary orderings:
- you can't do the libations run until the fridge is cleaned
- it makes no sense to clean the bathroom until the laundry is hidden
- take out the garbage only after vacuuming the living room and cleaning the bathroom
- don't put up decorations until the living room has been cleaned

### 1.2 Create activities

Create a postit note activity "card" for each activity.

Plan for each postit note containing 
- an identifier ... top or top left (empty for now)
- the team member assigned to this task (could be empty for now) ... initials, lower left
- the estimated time this task will take (small, medium or large) ... letter, lower right
- the task name or description ... in the center

This is not the only way to portray these activities, and probably not the best
there could be, but it will suit our purposes. You or your organization
will evolve the most appropriate format over time.

### 1.3 Arrange the activities

Place the activities into a diagram, with time flowing
left to right. 

### 1.4 Connect the activities

Draw lines clearing communicating the precedences.

### 1.5 CPM Calculations

Demo provided :)

Will you be done on time?

### 1.6 Enlist a helper

Enlist a friend to help, and split the tasks so that
you can finish on time.

If you are working on different tasks at the same time, 
those tasks can be shown vertically aligned.

### 1.7 Redo CPM calculations

Are we done yet?

## 2 - WBS diagram

Create a work breakdown structure for your project.
The goal is to capture all the tasks you **think**
will be needed to complete your project.

Don't stress over the completeness of your set of tasks -
as you get more experience, you will get better at
determining these for future projects.

In the real world, you would not be expected to do this
until after a reasonable discovery phase (think UX!).
We are pushing things because of the compressed timeframe for
the project course.

### 2.1 Categories (5-10 mins)

The work categories can be whatever you think will work best for
your team. Achieve consensus for them before proceeding!

Some possible categories:
- use the workload from your team agreement
- identify broad activity groups (backend, frontend, etc)
- identify expected feature groups (ordering, kitchen, admin, etc)
- use software development activities (design, code, test, integrate, etc)

The categories are the first broad level in your WBS diagram.
They will have single digit IDs.

Suggestion: if not sure about your categories, consult a mentor.

### 2.2 Tasks (15-30 mins)

Everyone: create postit note descriptions for all of the tasks
you expect in your project, and place them in the proper
column of your WBS diagram.

Arrange postit note contents per #1 above.



**Duration:**  
How are you supposed to come up with estimates for stuff you have never done?
Use coarse granularity and "best efforts" - these are not engraved in stone,
and the planning tools you will use will adjust automatically!

Use the following durations:
- "small" for a task that can be completed by one person/pair in a "half day" (2-4 hours)
- "medium" for a task that can be completed by one person/pair in a "day" (4-8 hours)
- "large" for a task that can be completed by a person/pair in "two days" (8-16 hours)

If a task is trivial or too small for "small", your granularity is too fine - lump
it in with another.

If a task is too large to envision completing in two days, your granularity is too
coarse - split it into multiple tasks.

If a task is super important, but won't take much if any time, record its duration as 0 - 
this would be a "milestone".

As long as you are consistent with your granularity, everything will fall into place!

Suggestion: if not sure about your granularity or completeness,
consult a mentor.

**How many tasks?**  
Don't under-do it, yet don't over-do it.  
You have 5 team members, and three full weeks (for planning).  
If you assume that each member will contribute 3 "days" of work,
after allowing for seminars, mentoring, and unanticipated
events, that gives you 5 x 3 x 3 = 45 "days" of available effort.

That translates into ~45 "medium" tasks, or ~90 "small" ones
or ~25 "large" ones.

### 2.3 Re-arrange (15 mins)

If a WBS category looks too "busy", add sub-categories as needed.

Arrange or re-arrange the tasks, so that each category
column reflects the expected order that the tasks need to be done in.
Earlier tasks would go towards the top, and later ones towards the
bottom.

If you can't agree on which of two should come first, put them side by side.

Suggestion: if you get stuck or cannot agree, consult a mentor.

### 2.4 Number your tasks (10 mins)

You are now in a position to assign IDs to each task, per the category or sub-category
each is in.

### 2.5 Approval

Run your diagram by one of the instructors.

Heed their feedback.

Once "approved", take a picture of the diagram. Don't lose it.

## 3 - Project diagram

Your WBS diagram identified all the tasks you think you need.
The project diagram is going to arrange them to reflect
a work plan - what has to be done in what order.

### 3.1 Start

If you don't have these already, add a milestone tasks for the
project "start" (it will preceed **any** of the other tasks),
and one for the project "end" (it will succeed **all** of the other
tasks).

These will be the endpoints for your project diagram, the "start"
on the far left, and the "end" on the far right.

You might be more comfortable with some general column labels
to help organize your tasks in the upcoming steps. These could be
week 1, 2 & 3, for instance. Keep week 4 in reserve for everything
that will go wrong!

### 3.2 Arrange your activities (15-30 mins)

Stick your postit notes so that they read left to right (earlier to later).

You might find it helpful to have rows or "streams" to group them,
perhaps per the work categories.

If two activities would be done by different team members/pairs,
indicate so by "assigning" them on the postit note, and they
can go in the same vertical "column".

### 3.3 Connect the activities (15 mins)

Draw connecting lines between the activities, clearly
showing the precedences needed.

Re-arrange as necessary.

### 3.4 Calculate CPM (15 mins)

Complete the critical path calculations.

If you show completion by the target (end of week 4), you just might
be "good to go".

If you show completion well before the target, you have probably missed
some activities.

If you show completion after the target, you need to juggle
workload assignments to improve parallelism and tighten
you planned schedule.

### 3.5 Approval

Run your diagram by one of the instructors.

Heed their feedback.

Once "approved", take a picture of the diagram. Don't lose it.

## 4 - Process Review

Perform a process review when done. This is for your benefit.

## 5 - Trello board

Setup a [Trello](https://trello.com/) board for your project. You will use this for
brainstorming and sharing ideas or documentation - pretty much 
the non-code artifacts for your project.

Each team member will need to signup (no cost) for Trello.
If you have any privacy concerns, with data stored in the US,
create and use a bogus email account and/or name for this.

The team leader should create your board, and invite each of the team
members, as well as Pope & myself.

Create 3 lists to start: Planning, Design and Tools. You can add
any others that you find useful.

In your Planning list, add a card for your WBS diagram, and
another for your project diagram. Each of these should have the
pictures you took, as attachments.
You might have occasion to refer to these again!

##Dropbox Submission

A "readme" which summarizes what you have learned doing these exercises,
and any intended teamwork change(s) resulting from the process review

We will have access to your diagrams through your Trello board :)

By 17:30 Friday

##References / Resources / Inspiration

The course organizer has a couple of sample project plans, written up in a more
formal style.

Here are some additional links you might enjoy:
- https://www.tutorialspoint.com/management_concepts/project_activity_diagram.htm  
- http://www.dummies.com/careers/project-management/how-to-create-a-network-diagram/  
- http://www.dummies.com/careers/project-management/theme-based-product-road-maps-2/  
- http://www.dummies.com/careers/project-management/timed-release-product-road-maps/  
- http://www.dummies.com/careers/project-management/how-to-prepare-your-project-plan/  
- http://www.dummies.com/careers/project-management/4-ways-to-display-your-projects-schedule/#slide-1  
