#Tutorial tracker - PivotalTracker Walkthrough
ACIT2910 - BCIT - Spring 2017

##Goal

This turorial is a walkthrough, using the Party Planner exercise from last week, 
to show you how to use Tracker properly. 


##1. Pivotal Tracker Walkthrough

I have setup a PivotalTracker project for each group. Each of you will receive 
an email inviting you to your project. When you click on the link in that email, 
you will have to choose a password, and you will be given an opportunity to 
watch a short introduction video. Do watch the video – it will provide context for using the Tracker tool.

The faculty have been added to the projects as well, so that we can observe progress and “accept” or “reject” completed work.

Tracker is basically a glorified to-do list manager, but is is an agile project management tool. 
It does not know about task durations, nor about task precedence – 
that is where your conventional project plan fits in. 
The project plan informs the team members, about what should be worked on next 
(the critical path, remember?), and on the duration of a given task.

I have put the party planner tasks from last week into a project plan, shown below.

<img class="scale" src="/pix/tracker/t01.png"/>

The tool I used is not MS-Project, and it doesn't afford a lot of flexibility in 
presentation, but your lab exercise last week will help you make
sense of it. The durations are a bit different than those we worked with last week too.

Note: the project plan shown provides for four people doing the party prep,
one in each "swim lane".

##Data Setup

I have setup a Tracker <a href="/stuff/partyplanner.csv">project data file</a> for you to import.
Only one project member needs to import it – it will be seen by all. 
Do this by using the navbar: PROJECT > Import CSV.

<img class="scale" src="/pix/tracker/t02.png"/>

##Starting project

All four teams on a project should now see their barebones Party Planner project, with eight stories in the icebox. Stories in the icebox should only be moved to the backlog once they can be started, and they should be moved in priority order. The priority implied is top-to-bottom. If you get a story out of order, drag it to the proper place.

<img class="scale" src="/pix/tracker/t03.png"/>

Once you are more comfortable with Tracker, stories can be moved to the backlog if you intend to complete them during the current iteration.

Oh yes – what we called tasks in project planning are going to be called stories here. Agile management :)

In Tracker, “stories” are functional requirements, i.e. things to be completed before the project is deemed complete. Some of those can be involved, so they get broken down internally into “tasks”. On a larger scale, “epics” are meaningful groups of stories.

Let's get underway. Each of the team members should take ownership of one or two of the eight stories,
by setting the "owner" property in the story properties.

##Librarian and Epics

Designate one member of the project to be the librarian. 
They should add two epics, one for indoor stuff and one for outdoor stuff. 
Show the Epics panel by clicking on EPICS in the navbar.

<img class="scale" src="/pix/tracker/t04.png"/><br/>

<img class="scale" src="/pix/tracker/t05a.png"/><br/>

<img class="scale" src="/pix/tracker/t05.png"/>

Now, each member can edit their stories, adding the appropriate epic label for their stories.
Set yourself as the "owner" if you haven't already.

<img class="scale" src="/pix/tracker/t06.png"/>

Once complete, you will see the epics with their own progress bar.

<img class="scale" src="/pix/tracker/t07.png"/>

##Now for some tasks to do

Further edit the stories to add two to four tasks each.

<img class="scale" src="/pix/tracker/t08.png"/><br/>

<img class="scale" src="/pix/tracker/t09.png"/>

The tasks in a story can be shown in a pop window, by hovering over the bubble in a story row.

##Guidelines!

Once the project is “underway”, remember the following guidelines:
- a story is moved from the icebox to the backlog only if it can be completed during the current iteration.
- a story is “started” by the person/team who will be doing the work
- a story is “finished” by the person who started it
- a story is “delivered” when it is deployed for testing (normally), but in this case when it is ready for inspection; you would normally finish several stories then deploy the latest version of a program incorporating these for testing. In our context, the librarian would normally be responsible for this.
- a story is “accepted” or “rejected” only by the client or if their representative says so; accepting your own stories is considered cheating, and you know what happens to cheaters
- a story is “accepted” by the client if all of its tasks have been completed, and if it meets the functional requirements it is supposed to
- a story is “rejected” by the client if it is incomplete, does not meet its functional requirements, or has flaws uncovered during testing. When a story is rejected, a reason is provided – an explanation of the defect(s)
- once a story has been accepted, the next icebox story, according to the original project plan, can be moved to the backlog

Now we are finally ready to “play” the party planning. 
Remember who has to do what. 
Use seconds instead of minutes for elapsed time, so that this exercise doesn't take hours.

##And we're off

The first four stories (clean fridge, convenience store run, clean bathroom and hide dirty laundry) 
can be moved to the backlog, as they are ready to start, 
according to the project plan. Note that they all end up in the “current” folder, 
as they can theoretically all be started now.

<img class="scale" src="/pix/tracker/t10.png"/>

###Time 0

The time is zero. The stories in the current panel can be started, 
but a member should only be working on one at a time. 
If one of the members has two stories in the current panel, they can only 
start on one of them. Let's assume that one person has been given the jobs 
of cleaning the bathroom and hiding the laundry, and that they will 
start with the first. There are then 3 stories started.

<img class="scale" src="/pix/tracker/t11.png"/>

###Time 5

5 minutes later (5 seconds in our time-space continuum), some of the tasks have been completed, 
but none of the stories has finished. Record 1 or 2 tasks for your story as being completed.

<img class="scale" src="/pix/tracker/t12.png"/>

###Time 20

15 minutes later (15 seconds for us),  the first two stories (cleaning the bathroom and cleaning the fridge) 
should be completed. Complete the tasks for those stories, and then “finish” the stories.

<img class="scale" src="/pix/tracker/t13.png"/>

Two stories can now move to the backlog, from the icebox, per our project plan.

<img class="scale" src="/pix/tracker/t14.png"/>

###Time 25

5 minutes later, “Deliver” the two completed stories, and start the garbage 
and store runs if the teams assigned to them are available.

<img class="scale" src="/pix/tracker/t15.png"/>

###Here comes the boss

The “client” can now inspect the bathroom and the fridge. 
Let's assume the bathroom is ok, but the fridge needs to be wiped down.

<img class="scale" src="/pix/tracker/t16.png"/>

The fridge cleaning will need to be restarted once its team is free.

<img class="scale" src="/pix/tracker/t17.png"/>

###Time 30

5 minutes later, complete the convenience store run and garbage takeout. 
Also restart the fridge cleaning.

<img class="scale" src="/pix/tracker/t18.png"/>

###Time 35

5 minutes later, deliver the store run, and the garbage. Those are acceptable, so the client will accept them.

###Time 40

5 minutes later, move the last two stories to the backlog, and finish the fridge.

<img class="scale" src="/pix/tracker/t19.png"/>

###Time 45

5 minutes later, start the laundry hiding and deliver the fridge cleaning.

<img class="scale" src="/pix/tracker/t20.png"/>

###Time up to 60

5 minutes later, accept the fridge cleaning and finish the libations run. 
Neither of the two remaining stories can be started, because they depend on 
hiding the laundry, according to the story plan.

5 minutes later, deliver the libations run for inspection.

5 minutes later, if you reject the libations run (they forgot the rum), 
that story will need to be rejected, and restarted, and then not finished again 
for another 20 minutes. I hope you get the picture, and that we can just accept what they delivered.

<img class="scale" src="/pix/tracker/t21.png"/>

###Time 65

5 minutes later, the laundry is finally hidden. Finish and deliver it.

<img class="scale" src="/pix/tracker/t22.png"/>

###Time 70

5 minutes later, accept the laundry hiding and start the vacuuming.

<img class="scale" src="/pix/tracker/t23.png"/>

###Time 85

15 minutes later, finish and deliver the vacuuming.

<img class="scale" src="/pix/tracker/t24.png"/>

If the vacuuming job is acceptable to the client, accept it and start the decorating.

<img class="scale" src="/pix/tracker/t25.png"/>

###Time 90

15 minutes later, finish & deliver the decorating.

<img class="scale" src="/pix/tracker/t26.png"/>

If the client is happy, we are ready to party. If not, the decorating story will need to be rejected and restarted.

###Are We Done Yet?

Finally done!

<img class="scale" src="/pix/tracker/t27.png"/>

Notice that all stories have moved to the current panel, all are completed (green), 
and that the epics' progress bars are now all green too. 

###Put away the ice

The icebox panel can be closed as soon as there is now longer anything in it, to make the display easier to read.

<img class="scale" src="/pix/tracker/t28.png"/>

I would not suggest closing the backlog panel – it is used to show what has to be completed during the current iteration.

##Wrapup

You probably noticed that not all members were working all the time during this project plan. 
That is a sign of poor planning or poor workload assignment. 
The actual “execution” of the plan did not exactly follow the project plan, 
and that is normal too. The project plan, however, should have informed 
the project team members, as the work progressed.

##Submission ?
Nothing has to be submitted for this walkthrough

##References / Resources / Inspiration

- [Pivotal Tracker](https://www.pivotaltracker.com)