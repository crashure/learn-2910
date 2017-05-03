#Tutorial gitflow03 - Gitflow Walkthrough
ACIT2910 - BCIT - Spring 2017

##Introduction

Feedback from the session 5 lab suggested that you would appreciate a walkthrough
of the gitflow techniques. Here you go, using the images I presented at the beginning 
of session 5.

I will use the session 5 lab as the basis for the walkthrough, showing
how I would do it, with commentary.

I will add some story segments to the sad stories that you have been working on :)

This walkthrough will use the command line, which would be the bash shell on Windows.
Everything I type will have lines starting with the greater than sign, ">".
Any other lines are responses from the commands I use.

## <a name="account"></a>Account Setup

Before doing anything, I want to make sure that my name and email have been setup for git.

    >git config --global user.name "Master Yoda"
    >git config --global user.email jim_parry@bcit.ca

## <a name="repo"></a>Repository Setup

The starting point is a team repository that we wish to join.

<img class="scale" src="/pix/gitflow/01.png"/>

We are given a team repository to work with, `sad-story` in the `jedi-academy` organization
on github.com. As you can see, 41 people have forked it already.

<img class="scale" src="/pix/gitflow/Screenshot-9.png"/>

I can see that the repository has two branches, `master` and `develop`, and that `develop`
is the default one. So far, so good.

<img class="scale" src="/pix/gitflow/Screenshot-10.png"/>

I also notice that the repository has an `nbproject` folder in it.
Oops - the yoyo who setup the respository initially goofed,
by not git ignoring that folder, which contains IDE metadata.

<img class="scale" src="/pix/gitflow/Screenshot-11.png"/>

## <a name="fork"></a>Fork Setup

I need to fork the team repository, into my own account, in
order to work with it properly.

<img class="scale" src="/pix/gitflow/02.png"/>

On github.com, I click the "Fork" button...

<img class="scale" src="/pix/gitflow/Screenshot-12.png"/>

... and I choose choose my personal github account as the destination.

<img class="scale" src="/pix/gitflow/Screenshot-13.png"/>

The repository in my personal account shows that it came from
the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-14.png"/>

## <a name="local"></a>Local Project Setup

The next step is to clone my fork of the project, so that I can
collaborate on it.

<img class="scale" src="/pix/gitflow/03.png"/>

I need the cloning URL for my repo...

<img class="scale" src="/pix/gitflow/Screenshot-15.png"/>

And I can then clone the repository locally, inside the folder
I use for my web projects. 

    >cd /pub7/htdocs
    >git clone https://github.com/jim-parry/sad-story.git
    Cloning into 'sad-story'...
    remote: Counting objects: 345, done.
    remote: Compressing objects: 100% (28/28), done.
    remote: Total 345 (delta 10), reused 0 (delta 0), pack-reused 317
    Receiving objects: 100% (345/345), 49.13 KiB | 0 bytes/s, done.
    Resolving deltas: 100% (171/171), done.
    Checking connectivity... done.

When I change into that directory, I can see what appears to be all the files from the repo,
as well as `.git`, which is the literal copy of the repo.

    >cd sad-story/
    >ls -la
    total 60
    drwxrwxr-x.  4 jim jim 4096 May  3 01:39 .
    drwxr-xr-x. 88 jim jim 4096 May  3 01:39 ..
    -rw-rw-r--.  1 jim jim  830 May  3 01:39 dagobah.txt
    -rw-rw-r--.  1 jim jim  735 May  3 01:39 endor.txt
    drwxrwxr-x.  7 jim jim 4096 May  3 01:39 .git
    -rw-rw-r--.  1 jim jim  125 May  3 01:39 .gitignore
    -rw-rw-r--.  1 jim jim  898 May  3 01:39 hoth.txt
    -rw-rw-r--.  1 jim jim  312 May  3 01:39 jakku.txt
    -rw-rw-r--.  1 jim jim  354 May  3 01:39 kamino.txt
    -rw-rw-r--.  1 jim jim 1057 May  3 01:39 LICENSE
    -rw-rw-r--.  1 jim jim  911 May  3 01:39 mustafar.txt
    -rw-rw-r--.  1 jim jim  674 May  3 01:39 naboo.txt
    drwxrwxr-x.  2 jim jim 4096 May  3 01:39 nbproject
    -rw-rw-r--.  1 jim jim   56 May  3 01:39 README.md
    -rw-rw-r--.  1 jim jim 2601 May  3 01:39 tatooine.txt

I can find out the git aliases, which would be used for pushing and pulling...

    >git remote -v
    origin	https://github.com/jim-parry/sad-story.git (fetch)
    origin	https://github.com/jim-parry/sad-story.git (push)

I have `origin`, which is an alias for my repository.
I need to add an alias for the team repository too.

    >git remote add upstream https://github.com/jedi-academy/sad-story.git
    >git remote -v
    origin	https://github.com/jim-parry/sad-story.git (fetch)
    origin	https://github.com/jim-parry/sad-story.git (push)
    upstream	https://github.com/jedi-academy/sad-story.git (fetch)
    upstream	https://github.com/jedi-academy/sad-story.git (push)

Now I am ready to get down to work.


## <a name="work"></a>Work Away - Round 1

Note: at this point, my repository's `develop` branch is "even" with the team
repository's `develop` branch, i.e. they are the same.

For round 1 of the lab, I will edit one of the stories, save it,
commit it, and then push it to my repository.

<img class="scale" src="/pix/gitflow/04.png"/>

This will all be done in a topic/feature branch (actually shown in the previous
presentation picture), suitably named. This keeps my `develop` branch as close
to the team one as possible.

I first check to make sure that I am on my `develop` branch, then create
my new branch for this job based on it. Note that my branch name is helpful.

    >git status
    On branch develop
    Your branch is up-to-date with 'origin/develop'.
    nothing to commit, working directory clean
    >git checkout -b lab/round1
    Switched to a new branch 'lab/round1'
    >git status
    On branch lab/round1
    nothing to commit, working directory clean

I will edit the first story, `dagobah.txt`

<img class="scale" src="/pix/gitflow/Screenshot-16.png"/>

If I check my git status now, it shows that I have a changed file.

    >git status
    On branch lab/round1
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git checkout -- <file>..." to discard changes in working directory)

            modified:   dagobah.txt

    no changes added to commit (use "git add" and/or "git commit -a")

I need to stage changed files, so they will be included in my next commit...

    >git add .

And, since this is the only change I plan to make, I can commit
the changes, using an approprite commit message.

    >git commit -m "Added segment to dagobah.txt"

    You need a passphrase to unlock the secret key for
    user: "Jim Parry (aka Master Yoda) <jim_parry@bcit.ca>"
    4096-bit RSA key, ID 0775AD5B, created 2016-06-07

    [lab/round1 3a86033] Added segment to dagobah.txt
     1 file changed, 5 insertions(+)

Unfortunately, my account is setup for automatic GPG signing.
I was hoping to lead up to that over the three rounds.
Your commit response won't be quite as involved as mine.


## <a name="pr"></a>Contribute 

I am now ready to contribute my proud story enhancement.

<img class="scale" src="/pix/gitflow/05.png"/>

I have committed all my changes, and need
to push my feature branch to my repository.

    >git push origin lab/round1
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 1.06 KiB | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To https://github.com/jim-parry/sad-story.git
     * [new branch]      lab/round1 -> lab/round1

I was prompted for my github username and password, which I am not going
to share with you :-/

I am ready to propose my changes.

<img class="scale" src="/pix/gitflow/06.png"/>

When I go to my repository, I see a "Compare & pull request" button.

<img class="scale" src="/pix/gitflow/Screenshot-17.png"/>

I can create a pull request now, proposing my changes to the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-18.png"/>

The pull request title comes from my last commit message.
It is a good idea to have a description, explaining the purpose of the PR.

Note that my PR proposes to my **my** `lab/round1` branch
into the team's `develop` branch. This is correct.

Note also that is says "Able to merge." At the time this PR was created, there
were no conflicts.

My PR, if accepted, will be merged.

<img class="scale" src="/pix/gitflow/07.png"/>

After creating it, the team repo maintainer sees a PR merge request...

<img class="scale" src="/pix/gitflow/Screenshot-19.png"/>

You would not see this as a contributor.

Notice the "Verified" badge on the right side, on the line with
the commit message. That says that my commit was GPG-signed.

The team repo maintainer would check the changes, by examining changed files,
and by pulling the PR to his/her machine for more extensive testing (if warranted).
Once satisfied, they would "Merge pull request".

Once the PR has been merged, my `develop` branch is no longer "even" with the team's.

<img class="scale" src="/pix/gitflow/Screenshot-20.png"/>

Also, my repo still has the now useless `lab/round1` branch, which is 1 commit
"ahead" of my `develop branch.


## <a name="synch"></a>Synchronize 

I need to synchronize my repository with the team one, so that they are "even".

<img class="scale" src="/pix/gitflow/08.png"/>

<img class="scale" src="/pix/gitflow/09.png"/>

    >git pull upstream develop
    remote: Counting objects: 1, done.
    remote: Total 1 (delta 0), reused 1 (delta 0), pack-reused 0
    Unpacking objects: 100% (1/1), done.
    From https://github.com/jedi-academy/sad-story
     * branch            develop    -> FETCH_HEAD
     * [new branch]      develop    -> upstream/develop
    Updating 617141b..a856567
    Fast-forward
     dagobah.txt | 5 +++++
     1 file changed, 5 insertions(+)
    >git push origin develop
    Counting objects: 1, done.
    Writing objects: 100% (1/1), 304 bytes | 0 bytes/s, done.
    Total 1 (delta 0), reused 0 (delta 0)
    To https://github.com/jim-parry/sad-story.git
       617141b..a856567  develop -> develop

And boom - my repo is in synch with the team repo.

<img class="scale" src="/pix/gitflow/10.png"/>

I can delete the `lab/round1` through the browser, and my local branch
from my bash shell ...

    >git branch -d lab/round1
    Deleted branch lab/round1 (was 3a86033).

## <a name="work"></a>Work Away - Round 2

I am going to edit a different story now, for round 2.
This will be done on a new feature branch.
I will take this all the way to creating the PR, but will
not merge it.

The highlights...

    >git status
    On branch develop
    Your branch is up-to-date with 'origin/develop'.
    nothing to commit, working directory clean
    >git checkout -b lab/round2
    Switched to a new branch 'lab/round2'
    bash-4.1$ gedit hoth.txt
    bash-4.1$ git add .
    bash-4.1$ git commit -s -m "Edited the hoth story"

    You need a passphrase to unlock the secret key for
    user: "Jim Parry (aka Master Yoda) <jim_parry@bcit.ca>"
    4096-bit RSA key, ID 0775AD5B, created 2016-06-07

    [lab/round2 b1db49e] Edited the hoth story
     1 file changed, 7 insertions(+), 6 deletions(-)
    >git push origin lab/round2
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 1.15 KiB | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To https://github.com/jim-parry/sad-story.git
     * [new branch]      lab/round2 -> lab/round2

I created the pull request (#77), but did not accept it into the
team repo yet.

Another change for round 3. It's a good thing I used feature branches, or this would
get tangled up with the round 2 change!

    >git status
    On branch develop
    Your branch is up-to-date with 'origin/develop'.
    nothing to commit, working directory clean
    >git checkout -b lab/round2
    Switched to a new branch 'lab/round2'
    >gedit hoth.txt
    >git add .
    >git commit -s -m "Edited the hoth story"

    You need a passphrase to unlock the secret key for
    user: "Jim Parry (aka Master Yoda) <jim_parry@bcit.ca>"
    4096-bit RSA key, ID 0775AD5B, created 2016-06-07

    [lab/round2 b1db49e] Edited the hoth story
     1 file changed, 7 insertions(+), 6 deletions(-)
    >git push origin lab/round2
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 1.15 KiB | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To https://github.com/jim-parry/sad-story.git
     * [new branch]      lab/round2 -> lab/round2
    >git status
    On branch lab/round2
    nothing to commit, working directory clean
    >git checkout develop
    Switched to branch 'develop'
    Your branch is up-to-date with 'origin/develop'.
    >git checkout -b lab/round3
    Switched to a new branch 'lab/round3'
    >gedit tatooine.txt 
    >git add .
    >git commit -S -m "Edited tatooine.txt"

    You need a passphrase to unlock the secret key for
    user: "Jim Parry (aka Master Yoda) <jim_parry@bcit.ca>"
    4096-bit RSA key, ID 0775AD5B, created 2016-06-07

    [lab/round3 cffdf0a] Edited tatooine.txt
     1 file changed, 5 insertions(+)
    >git push origin lab/round3
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 1.08 KiB | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To https://github.com/jim-parry/sad-story.git
     * [new branch]      lab/round3 -> lab/round3

I created a pull request for `lab/round3`, and both now show in the list
of PRs on the team repo.

<img class="scale" src="/pix/gitflow/Screenshot-22.png"/>

Both of my PRs show on the list, and both are mergeable.

## Resolve Merge Conflict

Oh no! Another PR was accepted, for the same file that our
original one changed, and we now have a conflict!!

<img class="scale" src="/pix/gitflow/Screenshot-23.png"/>

Let's try to fix this by re-synching our repo.

    >git checkout develop
    Switched to branch 'develop'
    Your branch is up-to-date with 'origin/develop'.
    >git pull upstream develop
    remote: Counting objects: 5, done.
    remote: Compressing objects: 100% (5/5), done.
    remote: Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (5/5), done.
    From https://github.com/jedi-academy/sad-story
     * branch            develop    -> FETCH_HEAD
       a856567..8d4bb4e  develop    -> upstream/develop
    Updating a856567..8d4bb4e
    Fast-forward
     hoth.txt     | 13 +++++++------
     tatooine.txt |  7 ++++++-
     2 files changed, 13 insertions(+), 7 deletions(-)
    >git push origin develop
    Counting objects: 5, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (5/5), done.
    Writing objects: 100% (5/5), 965 bytes | 0 bytes/s, done.
    Total 5 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 1 local object.
    To https://github.com/jim-parry/sad-story.git
       a856567..8d4bb4e  develop -> develop
    >git checkout lab/round3
    Switched to branch 'lab/round3'
    >git merge develop
    Auto-merging tatooine.txt
    CONFLICT (content): Merge conflict in tatooine.txt
    Automatic merge failed; fix conflicts and then commit the result.

Oh oh - the conflicting changes are now recorded in our story,
and we need to change them. This is what the conflicted part of our story looks like

    <<<<<<< HEAD
    Unfortunately, someone didn't follow lab directions, and Jill is going to be horribly
    confused by the two fortunatelys in a row.

    Fortunately, she can take good luck in stride, so she seemed ok.
    =======
    Unfortunately, James T Kirk materialized onto the slope beside them, and he was no help.
    He kept muttering "Beam me up, Scotty - we need Bones here, not me."

    Fortunately, Jill's sister was strong in the ways of the force, and could
    resist the pull of the USS Enterprise's transporter beam.
    >>>>>>> develop

There are two conflicting sections. We can choose to keep one, or the other, or both.
Either way, we decide, and we need to remove the conflict markers before
continuing.

I chose to keep both, leaving...

    Unfortunately, someone didn't follow lab directions, and Jill is going to be horribly
    confused by the two fortunatelys in a row.

    Fortunately, she can take good luck in stride, so she seemed ok.

    Unfortunately, James T Kirk materialized onto the slope beside them, and he was no help.
    He kept muttering "Beam me up, Scotty - we need Bones here, not me."

    Fortunately, Jill's sister was strong in the ways of the force, and could
    resist the pull of the USS Enterprise's transporter beam.

So, save & re-commit this, and re-push it to my repo.

    >git add .
    >git commit -m "Fix conflict in tatooine"

    You need a passphrase to unlock the secret key for
    user: "Jim Parry (aka Master Yoda) <jim_parry@bcit.ca>"
    4096-bit RSA key, ID 0775AD5B, created 2016-06-07

    [lab/round3 a8f460f] Fix conflict in tatooine
    >git push origin lab/round3
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 1.13 KiB | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    To https://github.com/jim-parry/sad-story.git
       cffdf0a..a8f460f  lab/round3 -> lab/round3

Now, when we check our PR again, on the team repo, ...

<img class="scale" src="/pix/gitflow/Screenshot-24.png"/>

It is mergeable again, yay!

Merge it and we are good to go!

Don't forget to resynch your repository, so it is even with the team one!

    >git checkout develop
    Switched to branch 'develop'
    Your branch is up-to-date with 'origin/develop'.
    >git pull upstream develop
    remote: Counting objects: 1, done.
    remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (1/1), done.
    From https://github.com/jedi-academy/sad-story
     * branch            develop    -> FETCH_HEAD
       8d4bb4e..07666b9  develop    -> upstream/develop
    Updating 8d4bb4e..07666b9
    Fast-forward
     tatooine.txt | 7 +++++++
     1 file changed, 7 insertions(+)
    >git push origin develop
    Counting objects: 1, done.
    Writing objects: 100% (1/1), 298 bytes | 0 bytes/s, done.
    Total 1 (delta 0), reused 0 (delta 0)
    To https://github.com/jim-parry/sad-story.git
       8d4bb4e..07666b9  develop -> develop

##Wrapup

There is your step-by-step walkthrough. I hope it helps!
