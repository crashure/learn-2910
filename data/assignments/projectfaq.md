#Mini-Project - F.A.Q.
ACIT2910 - BCIT - Spring 2017

My answers are italicized below.

### Github usage?

My team have been researching on how to deploy NodeJS applications on Github and so far, the answer is, it is not possible because Github only hosts static HTML pages. 
My first question is, is the main reason we're using Github, is to show our collaboration as a team and not actually host our web application?

_Github is a source code repository, and not appropriate for hosting dynamic sites. We want to use github or gitlab because of the gitflow collaborative workflow._

### Repository heads up?

_You will be setting up repositories next week. I use github for all my open source work, but you might want
to choose the ACIT gitlab server if you have concerns about any private information about you being hosted in the US._

_My suggestions: use a bogus email account (real addresswith a bogus username) for github; use github 
instead of gitlab for stuff you might want to share with a prospective employer._

**Do not setup your repository yet. We want to configure Pivotal Tracker integration when we do!!** 

### Client and/or server components

I am hearing that a lot of our classmates are using reactJS and/or Angular but those are just client side scripting 
and still require a server side script to execute database queries like mysql or postgresql. 

_Both client and server side components are needed, agreed. Some of the teams still seem confused on the server part._

_The MYSQL database lives on the server, and will not have remote access. 
It will need to be manipulated through your server-side component(s)._

_You could build a REST API server-side, or provide a web socket endpoint - I understand that Henry talked about both of those._

### Implementation language?

The only server side language that I know is node.js and PHP. There are others like Python and Ruby, but I we probably won't be using those.

_You can use the language of your choice, but we expect that most teams will stick to node+whateverJS, given the web courses so far._

_Whatever you use will need to be runnable on my system for testing._

### App deployment?

I'm just really confused on how and where the actual deployment of our web application is going to be? 
I recall you saying you have a VPS and will be providing us with a mysql database and a subdomain (ie. - acit2910.jlparry.com)? 
Is that where we will deploy our web application? Or an external web server of our choice?

_I have a deployment script, which the github repo will have a webhook setup for. 
My deployment service will automatically pull your app and deploy it on my server, eg. as earth.jlparry.com (or whatever your planet/team is),
whenever code is pushed to it. 
I am still working out details, such as running node & configuring each team's database. 
My setup is a hardened AMPP one, with MYSQL (and no remote access to it)._

_Teams do not *have* to use my server, but it will make your testing easy, and there is merit to experiencing the automatic deployment :)  
As a side benefit, you will rapidly find out if you have any case sensitivity issues,
which Windows or OSX might forgive but which Linux won't._

_If you do use something other than node or PHP, you will have to arrange your own hosting, and I will still want to run it on my system for testing.
This precludes any platform-specific toolsets, such as ASP._

_fwiw, I do all of my web development with the CodeIgniter PHP framework, using an Apache+PHP7+MYSQL stack on CentOS 6/7._
