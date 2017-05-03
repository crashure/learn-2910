#Tutorial gitflow03b - Gitflow Walkthrough with NetBeans
ACIT2910 - BCIT - Spring 2017

##Introduction

Feedback from the session 5 lab suggested that you would appreciate a walkthrough
of the gitflow techniques. Some of you asked for a walkthrough using an IDE.
This walkthrough will use NetBeans, which is my "normal" development editor.

I will use the session 5 lab as the basis for the walkthrough, showing
how I would do it, with commentary. I will add a story segment to 
one of the sad stories that you have been working on :)

The account that follows looks long, but there are bunches of screenshots, and I have
been excessive, chronicling eavh action along the way. You asked for it, after all :-/

## <a name="account"></a>Account Setup

This has already been done.
We can verify it from the command line.

    >git config --list
    user.name=Master Yoda
    user.email=jim_parry@bcit.ca
    user.signingkey=12345678
    credential.helper=cache --timeout=3600
    commit.gpgsign=true

No, that is not my real signing key for GPG :P

## <a name="repo"></a>Repository & Fork Setup

We still have these from before, and nothing new needs to be done.

If we didn't have these, they would be setup the same as before, using github.

## <a name="local"></a>Local Project Setup

Here is where things deviate from the command line approach.

We still have the team repo, and I still have my repo, but I deleted
my local clone so we could use NetBeans for this version of the
walkthrough.

In NetBeans, select Team > Git > Remote > Clone...

The same cloning URL that we used from the command line would be used.

<img class="scale" src="/pix/gitflow/Screenshot-25.png"/>

We can select the branches we want cloned locally. All we need id `develop`.

<img class="scale" src="/pix/gitflow/Screenshot-26.png"/>

I am going to clone this into the same parent folder as my other apps.

<img class="scale" src="/pix/gitflow/Screenshot-27.png"/>

NetBeans has discovered the IDE metadata (`.nbproject` folder) that
I mistakenly added to the team repo when I created it.

<img class="scale" src="/pix/gitflow/Screenshot-29.png"/>

I will exploit that and click "Open project". The result is our
project, with all of the stories in it.

<img class="scale" src="/pix/gitflow/Screenshot-30.png"/>

## <a name="work"></a>Work Away

After cloning, my repository's `develop` branch is "even" with the team
repository's `develop` branch.

NetBeans has a Git toolbar, making it easy to invoke the git commands:

<img class="scale" src="/pix/gitflow/Screenshot-34.png"/>

One awkward aspect with NetBeans git support, is that they insist on
calling the `origin` branch "Upstream", contrary to every other
git support tool I have seen, which calls that branch "origin".
You need to recognize this, and take some of the NetBeans button labels
with a grain of salt.

We can create a new branch for the current work by clicking on
"Create Branch" in the Git toolbar, and...

<img class="scale" src="/pix/gitflow/Screenshot-31.png"/>

There is a NetBeans plugin available, to show the name of the current
branch in the lower right of the program's status line...

<img class="scale" src="/pix/gitflow/Screenshot-31b.png"/>

Now that we are working on our topic branch, we can make
the source code changes we want to. Notice that they
show up with a green bar to the left, clearly indicating
what differs from the saved state of that source file.

<img class="scale" src="/pix/gitflow/Screenshot-34.png"/>

Once you have saved the file, you can commit the changes. Click on the
"Commit" button in the Git toolbar...

<img class="scale" src="/pix/gitflow/Screenshot-30.png"/>

You will be prompted for a commit message.

<img class="scale" src="/pix/gitflow/Screenshot-33.png"/>

You don't get the choice to sign your message here - that is done in
NetBeans configuration, which I will address later.

## <a name="pr"></a>Contribute 

Initiate a "push" by clicking on the "Push..." button in the
Git toolbar.

<img class="scale" src="/pix/gitflow/Screenshot-35.png"/>

You will be prompted for the repo that tou wish to push to...

<img class="scale" src="/pix/gitflow/Screenshot-36.png"/>

You can choose which branch(es) to push, the default being the one you are working on.

<img class="scale" src="/pix/gitflow/Screenshot-37.png"/>

You can also select the remote branch to update or create.

<img class="scale" src="/pix/gitflow/Screenshot-38.png"/>

Once pushed, you will see the same "Compare & pull request" button, in
your repository, that was there when the same action was done using
the bash shell.

My PR, if accepted, will be merged. There is no difference or advantage to using
a GUI IDE here.

## <a name="synch"></a>Synchronize 

I need to synchronize my repository with the team one again, so that they are "even".

Switch back to our `develop` branch.

<img class="scale" src="/pix/gitflow/Screenshot-42.png"/>


Initiate a pull request, to be from the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-44.png"/>

We didn't add a git remote alias for our team repo earlier.
We can do that here. Specify both the remote name and the cirrect cloning URL.

<img class="scale" src="/pix/gitflow/Screenshot-45.png"/>

From this point on, we have the choice of branch to work with...

<img class="scale" src="/pix/gitflow/Screenshot-47.png"/>

We specifically want the team repo's `develop` branch, one of the only two that should be there.

<img class="scale" src="/pix/gitflow/Screenshot-42.png"/>

We would then push our updated `develop` branch to our own repo, the same way we did earlier.

Looking at the hoth story, we can see that the changes are incorporated, and 
that there is no colour bar down the side.

<img class="scale" src="/pix/gitflow/Screenshot-49.png"/>

## <a name="work"></a>Cleanup

Cleaning up stale or unwanted branches can be done from inside NetBeans too.

Choose Team > Repository > Repository browser from the app menu.

<img class="scale" src="/pix/gitflow/Screenshot-50.png"/>

You can delete both the local and remote branches that concern
the topic branch that was merged.

<img class="scale" src="/pix/gitflow/Screenshot-51.png"/>

## Resolve Merge Conflict

I artifically created a merge conflict, separate from the above
walkthrough. Let's join that thread at the point where we
discover that a PR has a merge conflict...

I have two PRs outstanding, both of which show no conflict, but
both of which change "James T Kirk" to a different name.

<img class="scale" src="/pix/gitflow/Screenshot-54.png"/>

The first of these can be merged the usual way...

<img class="scale" src="/pix/gitflow/Screenshot-55.png"/>

... but the second now shows a merge conflict, because the story that this
PR was based on is now different - in fact, the same line was changed :(

<img class="scale" src="/pix/gitflow/Screenshot-56.png"/>

On github, you can see that our topic branch is 1 commit ahead (our name change) and
2 commits behind (merging the other PR) of the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-57.png"/>

We need to fix this before we can merge our second change!

Back in NetBeans, in our `lab/conflict-picard` branch, we still see our desired change,
but we need to synchronize with the now updated team repo.

<img class="scale" src="/pix/gitflow/Screenshot-58.png"/>

Let's pull the most recent `develop` branch from the team repo...

<img class="scale" src="/pix/gitflow/Screenshot-59.png"/>

... selecting its `develop` branch

<img class="scale" src="/pix/gitflow/Screenshot-60.png"/>

Oh no ... we have a conflict! Oh wait - we knew that. NetBeans can help us resolve it...

<img class="scale" src="/pix/gitflow/Screenshot-61.png"/>

Choose the "merge" option. We will get a warning that the situation needs to
be resolved...

<img class="scale" src="/pix/gitflow/Screenshot-62.png"/>

Choose "Resolve", and we get the merge conflict wizard...

<img class="scale" src="/pix/gitflow/Screenshot-63.png"/>

You can see that we have both versions of the conflicting file, and we need
to choose wisely. Clicking "Accept" for the left panel (what we want)
results in a changed highlight colour...

<img class="scale" src="/pix/gitflow/Screenshot-64.png"/>

If we click "Ok" in the lower right of the conflict resolution wizard,
we get a warning...

<img class="scale" src="/pix/gitflow/Screenshot-65.png"/>

After saving the changed file, the git history for our topic branch is updated locally, but
we still need to commit it. Clicking the commit button in the Git toolbar leads to...

<img class="scale" src="/pix/gitflow/Screenshot-66.png"/>

It doesn't show any files to commit, but our resolved one is really there.
Click "Commit", and make sure we are affecting the correct repository (ours)...

<img class="scale" src="/pix/gitflow/Screenshot-67.png"/>

Ooh - we can update both our `develop` branch and out topic branch, bringing them both in synch with the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-68.png"/>

The push dialog will show both branches...

<img class="scale" src="/pix/gitflow/Screenshot-69.png"/>

Go for it, and when we revisit the PR that was blocked before
we resolved the merge conflict ...

<img class="scale" src="/pix/gitflow/Screenshot-70.png"/>

Yay! It can now be merged, and Jean Luc Picard will star in the newly revised
sad story for Hoth.

## Commit Signing

NetBeans has a configuraiton option to automatically add a "signed-off by" message
to commits, in the description field.

Choose Tools > Options > Team > Versioning > Git to see the relevant options dialog:

<img class="scale" src="/pix/gitflow/Screenshot-52.png"/>

All this does, if you haven't configured secure signing as I have done, is add a
message to your commit:

    Signed-off-by:Master Yoda <jim_parry@bcit.ca>

This is different from a GPG signed commit, which shows the real name of the contributor,
in spite of their user name Git setting.

<img class="scale" src="/pix/gitflow/Screenshot-53.png"/>

NetBeans does not support secure signing directly. You have to do that
by commiting from the bash shell. You can still push, pull, etc from NetBeans.

Note: some other IDEs do support GPG signing, but only in their premium ($)
versions, and not in their free versions.

Note 2: some IDEs have a "Synchronize" button, to do the pull/push dance
automatically, using the proper branching.


##Wrapup

There is your step-by-step walkthrough. I hope it helps!
