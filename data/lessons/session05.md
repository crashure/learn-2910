#Session 5 Survey Results	
	
Responses for the survey follow, with the number of similar
responses shown to the right of a response.
	
There were 19 responders.
	
I have interpreted and aggregated some of the results.
	
##What are topics from the lesson that *you* feel need more or better explanation?	

- Forking	5  
_Forking lets you work on a copy of a shared repository, until you are ready
to propose a contribution to the shared repo. No one else sees your
work, good or bad, until you contribute it to the shared repo._
- how would you resolve a synchronization problem?	2  
_Easy: synch your develop branch  :)  
Medium: resolve merge conflicts locally (easier with an IDE)  :(  
Hard: copy your project locally, reclone & copy your changes in :((_
- Branching Workflow 2	  
_Related changes are kept together, in a branch. 
This lets you work on multiple things at a time,
but keep them separate.
A mistake in one doesn't have to impact the others._
- Explain the purpose of the Gitflow Workflow Checklist (and each of its steps)	 _In class_
- Gitflow gotchas, how to make sure?	  
_How to make sure what? that you don't have any? 
The primary responsibility is on the captain, rejecting contributions
that don't follow gitflow or which are likely to cause problems!_
- how does a synchronization problem occur?	  
_1) not synching with the team repo before proposing changes (your starting point is out-of-date)  
2) not working in branches (too many collision possibilities)  
3) not synching when you switch machines (different hashes)_
- I understood the concept, but not the implementation	 _In class_
- i want to learn specific command line	 _In class_
- in our case, are we using a gitflow or forking workflow?	  
_gitflow, which is both forking and branching, plus conventions_
- merging a forked respository	 _In class_
- more info on Properly attributing work done?	 _In class_
- Problem scenarios using Gitflow	  
_Synchronization, attribution, messy commit history, unhelpful titles_
- since we individually have forked the main project repo, are we going to commit on our fork or on the develop branch?	  
_You commit locally, push to your fork, and submit a pull request to the develop branch of the team repo_
- what would be a good workflow for 2 people working on the same feature? should they create a new branch on they fork or maybe create a shared repository?	  
_For this, create a feature branch in the team repo, merge it to develop and delete it once complete.
The feature branch would be based off develop, and you need to be really careful to keep
your develop branch synchronized so the feature branch doesn't go awry._

##Other related questions

- "Lesson gitflow02 Gitflow techniques" link did NOT work  _Nope. It wasn't meant to yet, but does now._
- can we have a team practice tutorial for gitflow like we had for pivotal tracker?  _In class_
- Clarity on how you can avoid conflict with another team member when commiting a file. E.g If two people work on the same file and upload.  
_Avoiding conflict cannot be guaranteed. If two people work on the same file,
and submit PRs for their work, both of the PRs will look mergeable.
However, once one is merged, the other may no longer
be mergeable. The contributor of the unmergeable one has to resolve
the issue.  
First to merge gets off easy :-/_
- Do you always create another branch ON the develop branch for every issue?  
_Best practice: yes._
- how master and develop branches work together?  
_develop is merged into master only for a "release". With agile, that would likely be an iteration,
but it could also be a feature or epic, depending on the size of the project._
- In every group, there's always one member that *seems* to be doing the least amount of work. Does that member *need* to feel bad, even though they are still contributing?  
_Agreed. The commit history is one thing that I look to determine comparable contributions, and the "contributors"
view on github. If someone *seems* to be doing no work, or substantially less than their
teammates, I will award that person a lower grade and wait for the team to persuade me otherwise._
- In real-world projects, is there only one person responsible for accepting pull-requests?  
_The larger the project, the more likely there will be more than one maintainer.
Small project: only one; large project: 2-3.  
With more than one maintainer, you might agree on responsibilities, so you don't cause problems._
- Is it possible to freeze changes to files after a certain release.  Like preventing contributers from editing a package.json file?    
_No. The captain needs to watch out for that._
- So all changes that one person does is pushed to their branch? How do they push it to the project branch, or do they just push it to develop and the captain puts everything into master when it is ready?  
_One person pushes to a feature branch in their repo, and submits a PR to the team repo, requesting that their
feature branch be merged into the team develop branch._
- What about bug fixes? When i read about gitflow i saw branches for hotfixes, releases and features. Is that just another type?  
_Yes. There is no hard and fast naming required by gitflow, just the suggestion that
the naming of a branch give clues as to its purpose._
- What is a topic branch?  _Topic branch >= feature branch. It is probably a better name to use._
- Why are central workflows not locked when in use?    
_Merges are done one at a time, and that is the only "locking"._
- Why is there not a simpler method to collaborate?  
_There are many ways to collaborate, and they all have issues. Gitflow has emerged as the most robust of them,
especially with team members with widely divergent skills._

- the transfer from git to the pivotal tracker	_some possible answers..._
    - https://content.pivotal.io/blog/level-up-your-development-workflow-with-github-pivotal-tracker
    - https://www.pivotaltracker.com/help/articles/githubs_service_hook_for_tracker/
   
