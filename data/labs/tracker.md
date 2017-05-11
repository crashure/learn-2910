#Lab tracker - Two-way Integration
ACIT2910 - BCIT - Spring 2017

##Previously, on ...

You have a PivotalTracker project, and you have a Github repository.

You created a "zap" to create a new Github issue whenever you added a story
to Tracker.

We want to complete the circle, with closed issues on github changing story status
in our Tracker.

Pivotal Tracker has a brief tutorial for 
[setting up a Github integration](https://www.pivotaltracker.com/help/articles/githubs_service_hook_for_tracker/).
This lab will walk you through the process.

##Plan on Tracker

With your "zap" setup, whenever you create a new Tracker story, that
results in a new Github issue.

When you story is saved, Tracker assigns a unique ID to id. This is shown
in the top left of the story editing dialog, shown below.
<img class="scale" src="/pix/tracked/track08.png"/>

Any applicable zaps are run every 5 minutes, but the Github issue
corresponding to your story will show up in Github.
<img class="scale" src="/pix/tracked/track02.png"/>

Notice that Github assigns an issue # to each issue. The screenshot above shows issues
13 and 14.

##Setup the Github integration

On your Github repo page, you need to an an integration, through the
"Settings" tag...

<img class="scale" src="/pix/tracked/track03.png"/>

<img class="scale" src="/pix/tracked/track04.png"/>

The integration service wants your Tracker **token**,
which comes from the bottom area on your Tracker profile page.
<img class="scale" src="/pix/tracked/track05.png"/>

**Note:** I experimented with the integration settings, and found
that not specifying a branch worked better :-/

Once setup, you should see the new integration in your
"Integrations & services" settings page.
<img class="scale" src="/pix/tracked/track06.png"/>

##Work

The Github->Tracker integration does not affect the
work that you do. Continue to use gitflow to complete the work
assigned to a team member.

##Commit your work

Once you have completed all or a substantial portion of a story,
you will want to "commit" that to your repository.

This could be a commit that you do locally, or it could be a change
made directly on the repository (dangerous practice).

Either way, you want to tag the Tracker story in your commit message,
if it is substantially completed. This is done with a comment inside
square brackets, which uses an appropriate keyword and references the 
_Tracker_ story ID, as shown here. Choose the verb carefully :)
<img class="scale" src="/pix/tracked/track07.png"/>

Even if making a change directly on the repository, when you save
that change, you are prompted to "commit" it, and have the opportunity
to have your Tracker story reference.
<img class="scale" src="/pix/tracked/track09.png"/>

Note that you can commit directly to the repo, but the online editing can
trigger a pull request instead, which is more consistent with gitflow.

##Merge your contribution

When you create a pull request, it will include one or more commits.
Commits can mention Tracker stories (as above), and different commits
included in a PR can mention different Tracker stories.

In the PR description, however, you might want to mention the _Github_
issue, for instance `Closes #13`. This Github "tag" is not inside
square brackets. If you do this, the Github issue will
be automatically closed once the PR is merged.

When the PR is merged, any PR or commit messages containing a Tracker story
reference will trigger an update sent to Tracker.
<img class="scale" src="/pix/tracked/track12.png"/>

##And voila

If you use a "finishes" tag in your Github commit, the Tracker story
should now show with an "accept/reject" control in your story list.

If you used a "delivers" tag in the commit, the story should show as
"done".

Easy, peasy, right? Except that you have to remember to add the
Tracker tag in your commit message. If you forget to do that,
Tracker is not notified of the story state change :(

If you somehow messed up the integration, you will have to manually close the
Github issues that are now completed, and to adjust story statuses
in Tracker.

##Your job

What we want you to do is setup the Github -> Tracker integration,
and use it for a couple of stories.

You should already have Tracker stories and associated Github issues
for some of the work planned for today. Make sure you tag the commits
for them appropriately.

##Your submission

Put a text file into the session 9 dropbox, with a link to your team repo.

We will check the Github commit history for today, looking for integration
triggers, and we will check the Tracker board for those stories,
making sure that the integration went all the way through.

If you have problems with some of the early commits today, indicate in your dropbox note
which issues/stories show that you have succeeded with the Github->Tracker
integration.

##Conclusions

Having new tracker stories show up as Github issues is a good thing :)

Having new Github issues show up as Tracker stories is not as valuable,
because many issues are bugs to fix (part of dealing with an existing 
Tracker story in many cases), and also because we want to avoid circular
links, where a Tracker story creates a Github issue which creates a Tracker story which...

Is the two-way integration worth it?
That is up to you. For a large project, I can definitely see its worth, but for a small
project (like our current ones), it feels like more overhead than simply
updating Tracker story status on their website.
