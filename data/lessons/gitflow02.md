#Lesson gitflow02 - Gitflow Techniques
ACIT2910 - BCIT - Spring 2017

##Introduction

There are a number of standard tasks when using gitflow workflow.
These are grouped together below.

- [Account Setup](#account)
- [Repository Setup](#repo)
- [Fork Setup](#fork)
- [Local Project Setup](#local)
- [Work Away](#work)
- [Contribute](#pr)
- [Synchronize](#synch)
- [Release](#release)
- [Cleanup](#cleanup)

The sample code shown is intended for use in your git bash shell,
with some of the examples showing the equivalent NetBeans commands.

**Note:** Treat this as a work-in-progress document. I will add
to it as problems arise.

## <a name="account"></a>Account Setup

Many projects insist that submitted code be "signed", so they can be assured of the identity of the contributer.

The first part of this is making sure that Git is configured with your name and email.

    git config --global user.name "John Doe"
    git config --global user.email johndoe@example.com

These settings will be available to all of the github projects you work on.

If you want to work on different projects using a different github account,
then inside any non-normal ones...

    git config user.name "John Doe"
    git config user.email johndoe@example.com

Make sure that your user name and email are consistent on all of the machines
you use. If you use one email on your laptop and a different one on your
desktop, github will get confused and not attribute your contributions
correctly.

Signing your commits is a good idea, for proper attribution. 
Unfortunately, the attribution isn't counted as a contribution unless your user name for signing matches your github user name. Beware!

### Signing Your Commits

The best practice is [GPG signing](https://bcit-ci.github.io/CodeIgniter4/contributing/signing.html) 
your commits, though not all IDEs support that. 
If yours doesn't, then you might have to do commits inside your git bash shell, 
though you can still submit PRs through your IDE.

## <a name="repo"></a>Repository Setup

When you create a team repository, there are a few things to keep in mind.

The repository maintainer ("captain") should set it up properly, before
any of the team members fork it.

When you create a repo, you get a "master" branch by default.
Make sure you create a readme file, even if it doesn't have much in it,
or else you will trouble cloning it later.

The captain should add any base files, libraries, etc to the repo.
A common practice is to have a starter, or "Hello world" app
as the initial content of the master branch, so that you
have something deployable. If you are going to have initial content,
the captain should clone the team repo, add the content,
and then push to the team repo's master branch. Once this is done,
delete your clone of the team repo, so you don't inadvertently work with
it later.

Once the master branch is setup, create a "develop" branch from master. Make "develop"
the default branch. It is the only branch you should be working with
until "release time".

Your team repo should only ever have "master" and "develop" branches, unless
you are building a "feature" that might need contributions from several
team members before being merged into the main develop branch.

### Collaborators

You can add the team members as collaborators to the repository,
BUT none of them should have admin rights. 
Collaborators can be automatically notified by email whenever
a change is proposed or made to the repo.

Non-explicit collaborators can still raise issues and
propose code, if the repo is public.
You will need to explicitly add contributors to the collaborators
list if the repos is private.

### Good Repository Naming

If you fork a team repository, that you plan to contribute to, it makes sense
to have your fork named the same as the original, shared one.

On the other hand, if you plan to use a repository fork as just a starting point
for your own project, then it is reasonable to name it differently.

Some poor repo names:

    starter-quotes
    CodeIgniter3-starter2
    mystuff

Some better repo names:

    acit2910-lab02
    Simple-TODO-List
    
### Good Branch Naming

Part of keeping things maintainable is making sure your branches and names are clear and organized. 
A branch name should clearly describe the feature or fix you are working on.

The following are good examples of branch names:

    file-attachment
    ui-rewrite
    search-api

And the following are bad:

    my-work
    enhancements
    bugfix

An even better practice is to use "namespaces", such as:

    feature/better-ui
    fix/parsing-regression-bug

And you should avoid problematic names:

    fix-#34
    master2
    Development

You would normally have a **master** and a **develop** branch. Any other branches
should only be kept around as long as you need them.

## <a name="fork"></a>Fork Setup

On github.com, "fork" a team repository to your personal account.
Your repository is the one to clone to your local system
to work on.

Feel free to change the name of your repository, in the repo settings.

## <a name="local"></a>Local Project Setup

When you clone a project locally, you automatically get a git remote, "origin".
This is the default for any "pushes" that you make.

When you save work to your repo, `git push` will save work in your current
branch to "origin".

Add an additional remote, "upstream", for your shared repo.

    git remote add upstream cloning-url-of-the-team-repo

You "pull" from this remote to synchronize your repo with the team

    git checkout develop
    git pull upstream develop
    git push origin develop

## <a name="work"></a>Work Away

Create a topic/feature branch for a set of related changes, and switch to it.

    git checkout develop
    git checkout -b feature/something

Make your changes, and save them.

Commit changes at logical breakpoints, not with every line changed.
Each commit should result in working code.

Do not wait until an entire large feature is "ready" before commiting.

Push your changes to your repo when the feature is complete,
or if you want to save them for work on a different machine.

### Good Commit Message

A Git commit should be clear and concise, not cryptic. 
Choose a name that would be helpful for teammates searching for that
commit, to see what all was modified as part of it.

It should be unique, and should not reference an issue number (save that for the PR description).

Some good commit messages:

    Fix incorrect tax formula
    Add sales tax calculation to Order

Some poor commit messages:

    Fix #34
    Update
    my stuff

## Signing Your Commits

Signing your commits is a good idea, for proper attribution. Unfortunately,
the attribution isn't counted as a contribution unless your user name
for signing matches your github user name. Beware!

The best practice is [GPG signing](https://bcit-ci.github.io/CodeIgniter4/contributing/signing.html) your commits,
though not all IDEs support that. If yours doesn't, then
you might have to do commits inside your git bash shell, though
you can still submit PRs through your IDE.


## <a name="pr"></a>Contribute 

When you have pushed your topic/feature branch to your repo, visiting it on
github will show a "Create pull request" button.
Clicking it will trigger a request to merge your feature branch
with the team repo's develop branch, **if** your feature branch
is based off of "develop".

The captain should review any PRs, rejecting outright any inappropriate ones
(eg. for the wrong branch) and commenting on changes needed before
that PR would be merged.

If a submitted PR has merging problems, it will appear in the open PR list
with a red X beside its title. 
If it is mergeable, it will have a green checkmark beside the title.

The captain can checkout a PR, for approval, by following the command
line instructions link. It shows two steps ... the testing and the merging.

If the testing is unsatisfactory, don't do the second step. Instead, comment
on the PR, so that the contributor can fix deficiencies.

If you are happy after testing, you can merge the PR using the command line instructions
step 2, or you can do so on github, which I recommend.

The testing creates a new branch locally, only for testing purposes.
The remote naming may be messy, as the instructions say to use "origin" and
you might need to use "upstream". 

The local testing branch can be deleted after testing.

### Good PR Descriptions

Anyone looking at your PR history should be able to easily determine what a PR accomplished and why it was made. 
To ensure this, make sure every PR title is clear and readable.

A good PR has a multi-line description

A PR's title should be brief but should clearly summarize what the PR is for. An example may be "Implement the API for file attachments."

The PR's description should be detailed, describing what changes you made and how they work. 
While it shouldn’t be massively long, it should cover the high points of the change, 
and perhaps why you did what you did (if you think it could be confusing).

If your PR fixes one or more issues, it is appropriate to say that in the body, eg "Closes #123".

## <a name="synch"></a>Synchronize 

Synchronization has proved to be problematic, regardless of the experience of the developer :(

Consider:

	[Team repo] --- [Your repo] --- [Local repo]

If you make changes to your [local repo], they only get saved to [your repo] after you `commit` 
and then `push` them to it. At that point, [your repo] is "ahead" of the [team repo].
This will be resolved when you submit a `pull request (PR)` that is accepted and merged
into the [team repo].

More problematic is the case that other contributions have been accepted to the
[team repo], where those changes conflict with changes you have made or are working on.
You will not be able to submit a succesful PR for them until **you** resolve the
conflicts, in your work.

If you are working in a feature branch, based on `develop`, and the [team repo]'s
`develop` has been updated, it is "ahead" of yours, and you need to synch repos.

Locally, checkout your `develop` branch, and then merge the changes from
the [team repo]:

	git pull upstream develop

If you do not have `upstream` already defined as an alias for your [team repo], 
**you will
need to do so**, for instance from the git bash shell:

	git remote add upstream [team repo cloning url]

You will then have two remote repository aliases: `origin` and `upstream`.
You can use whatever name you want for you [team repo] alias, so long as you use the 
same name in subsequent pull requests to synchronize your repos.

If updating [your repo] from [team repo] causes conflicts, you need to resolve
them locally, using a merge conflict resolution tool, or that capability in 
your IDE.

Once conflicts have been resolved, you can save your updated `develop` branch
in [your repo] by pushing the changes to it ...

	git add .
	git commit -s -m "Synch with team repo"
	git push

Those changes are in your `develop` branch, but not yet visible in your feature branch.
Make them appear by

	git checkout WhateverYouCalledYourFeatureBranch
	git merge develop

If this was needed so that a PR of yours could potentially be merged, update the
PR for your feature branch by

	git add .
	git commit -s -m "Synch changes merged"
	git push

If you or your CAPTAIN revisit the PR on github.com, it should show as having
been updated, and it hopefully will be mergeable.

## <a name="release"></a>Release 

The captain should merge develop into master, on the team repo.

They should then create a "release", from the "Releases" link on the 
repo homepage.

## <a name="cleanup"></a>Cleanup 

Remember to delete any no longer needed branches in your repository.

Remember to delete any no longer needed tracking branches locally..

    Netbeans: Team > Repository > browser or > configuration

##Wrapup

Following the above should keep you and your team safe while collaborating!

There are more links in the "Resources" tab, if you wish to learn more about Git
and gitflow.
