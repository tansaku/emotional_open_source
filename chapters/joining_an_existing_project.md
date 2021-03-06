Joining a Project
-----------------

:construction: UNDER CONSTRUCTION :construction:


- [Motivations for contributing to an Open Source project](#motivations-for-contributing-to-an-open-source-project)
- [Length of commitment](#length-of-commitment)
- [Type of contribution](#type-of-contribution)
  * [Testing (Sidebar?)](#testing--sidebar--)
  * [Machines you control (Sidebar?)](#machines-you-control--sidebar--)
- [What to do when stuck installing or testing](#what-to-do-when-stuck-installing-or-testing)
  * [How to pull down code (sidebar?)](#how-to-pull-down-code--sidebar--)
- [Where and how to ask (sidebar?)](#where-and-how-to-ask--sidebar--)
- [READMEs and CONTRIBUTING docs (sidebar?)](#readmes-and-contributing-docs--sidebar--)
- [When and how to contribute](#when-and-how-to-contribute)
  * [Voting or Planning Poker (sidebar?)](#voting-or-planning-poker--sidebar--)
  * [Scrums and Standups (sidebar?)](#scrums-and-standups--sidebar--)
- [Reading the project documentation](#reading-the-project-documentation)
  * [Cucumber (sidebar?)](#cucumber--sidebar--)
  * [Pull Requests (sidebar?)](#pull-requests--sidebar--)
  * [Branches and Forks (sidebar?)](#branches-and-forks--sidebar--)
- [Contacting the project manager](#contacting-the-project-manager)
- [Understanding the project contribution flow](#understanding-the-project-contribution-flow)
  * [Kanban (SideBar?)](#kanban--sidebar--)
- [Submitting your first “pull request”](#submitting-your-first--pull-request-)
- [Going with the flow](#going-with-the-flow)
- [Not much time to spare?](#not-much-time-to-spare-)
  * [PairProgramming (sidebar?)](#pairprogramming--sidebar--)
- [References](#references)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


## Motivations for contributing to an Open Source project

So you want to join an Open Source software project?  Your motivations are probably a combination of wanting to contribute something for the greater good, honing your tech skills, and/or just fixing an issue with a piece of Open Source software that's bugging you because it's preventing you getting on with something else.

## Length of commitment

Making a single contribution to an Open Source project doesn't commit you to being a lifelong project member.  Many individuals make a single contribution to a project and then move on.   However, whether you've got your eye on a single bug-fix, or getting involved for a longer period, there are some things you can do to get the most out of the experience, and maximise the chances that your contribution will be a positive one for both you, the project, and the project community.


<details>
    <summary>What's a Bug Fix?</summary>
    The term "bug" predates computers and software and has been used for many years to describe glitches or problems with mechanical systems.  To fix a software bug is to make a change to the code that removes an unanticipated problem in the software execution. Thus one common type of contribution to Open Source projects is a "bug-fix"; a change or set of changes to the code that addresses the specified problem or "bug".
</details>
 


## Type of contribution

If your contribution is a simple documentation or cosmetic interface fix, you may be able to get straight to it, particularly if you use something like GitHub's web interface to directly suggest a change.  Conversely, if you're proposing making non-trivial changes to the project code itself, it makes sense to get all the application code and tests running successfully on a machine you control.  This might mean getting the tests running on your local machine, or even on a machine in the cloud provided by an IaaS such as AWS (or on C9).  How hard this will be to do depends on the project, but having all the tests running means that you can verify for yourself that any change you've made has not inadvertently broken other functionality in the application.

### Testing (Sidebar?)

Many codebases will be split into two sorts of code; application code that gets the job done, and testing code that checks that the application code is operating correctly.  Projects differ on the amount, and type, of testing code that is necessary in order for changes to be accepted.  The presence of tests can in principle allow developers to detect bugs that would otherwise creep in to the end user experience of the project.  A well-designed and maintained test suite with the right balance of fast running low-level unit tests, intermediate-level integration tests and a smaller number of slow high-level acceptance tests, can alert developers to unanticipated knock-on side-effets caused by new code; particularly if Continuous Integration (CI) systems are used to automatically run those tests on every proposed change.

Continuous Integration systems (such as Travis, CodeShip, Semaphore, CircleCI, SnapCI, etc.) can give a green or red light to merging in changes from both core team members and new contributors alike.  However the presence of tests does not guarantee that those tests are testing the right thing, and although there are metrics such as "Test Coverage" that can give an indication of how much of the code base is exercised by the test suite, there is no guarantee that all possible bugs and problems will be excluded.   Sometimes all tests will be passing, but the high-level acceptance tests will not capture an important corner case.  In addition, indeterminately failing and long running tests may add to the overall development burden, and creating the correct test can often stretch the skills of any developer.  For a contributor short on time, writing a test in addition to their proposed change may be impractical. 

However, in the absence of any tests, only laborious manual testing by the developers will catch all potential bugs.  The risk of bugs can be reduced by keeping all code as simple as possible and following a coherent underlying design; which by the way, is a great idea independently of the nature and composition of a projects test suite.  Either way, in order to have your contribution accepted into an Open Source code base you will need to follow the project guidelines on the degree of automated testing that should be included in your submission.

### Machines you control (Sidebar?)

In the ideal world the application code and full test suite of an Open Source project will run on any machine available.  In reality the codebase of most projects will run well on a limited subset of machines not too different from those the maintainer and the core team are using.  Thus, if the team is mainly using a particular version of OSX, then you'll probably not have too much trouble installing and running the code on similar versions of OSX, but will be increasingly likely to encounter problems as the version differences increase and/or you try to run the system on Windows or Linux or other operating system.  Sometimes these problems can be frustratingly insurmountable.  The project may have limited resources to test on every platform available, and perhaps your first (very valuable) contribution will be documentation on how to successfully install and run the test suite on a new platform?

Sometimes you'll have access to a sufficiently similar machine, but it will be under-resourced so that while the project maintainers can run the test suite locally in a couple of minutes, you'll be struggling to see it finish in less than an hour, and this can serve as a serious impediment to contributing.  These days you don't have to be constrainted by a physical machine of your own, and with a good internet connection and a credit card you can get terminal (text-only) access to Linux (and other OS) machines of standard shapes and sizes via Infrastructure as a Service (IaaS) providers such as Amazon (AWS), Digital Ocean and Microsoft Azure.  There are also services such as Cloud9 (C9) which will give you an IDE environment in the browser to manipulate the code running in a cloud machine.   There are also hypervisor systems which allow you to create virtual machines on your local machine, which allow you to, for example, run Linux on a Windows machine and so forth.

None of these solutions is without it's downsides.  If your internet connection is spotty then it may be difficult to download large hypervisors and virtual machine images, while cloud based IDEs may be frustrating to use. If you don't have access to a credit card, or have limited funds, then you might run up against the size and speed constraints of the free tiers of cloud services.  Adding virtual machines via a hypervisor to your local machine can help you sidestep certain installation issues, but then the application and associated test suites will run more slowly than a native installation.   In the long run, if you want to be a serious contributor to a project you'll probably want to get set up with similar computing resources to the core project team.  In the meantime there are a lot of options for one-off or short term contributors; so be sure to talk to the team about which alternatives have worked well for others and are a good match for your current resources.

## What to do when stuck installing or testing

So pull down the code and see if you can run the tests and application locally. Given a bit of luck the code and tests will all just run on your machine.  Project maintainers will be doing their best to be platform independent, but differences in your machine setup may lead to problems. Don't suffer in silence; if you get stuck on any part of the install, running the tests, or operating the code then look into how to get help.  Projects will often state in their README or CONTRIBUTING documents whether you should post to a mailing list, open a GitHub issue or ask for help in a text chat room hosted on IRC, Slack, Gitter or similar.  For example, AgileVentures projects have a Slack chat room for every project.  You might be confused about where is the best place to ask, and if so it's worth asking somewhere, even if you get redirected to ask somewhere else.  If you are asked to follow up somewhere else, don't feel too bad; just follow the suggestion and remember that the project maintainers are trying to balance the load of incoming questions and make it easier for others to find help in future.

### How to pull down code (sidebar?)

Pulling down the code to a machine you control will often involve a version control system such as git, subversion or similar.  Git is the flavour of choice these days, and while you can still download packages of code in a single zipped file for some projects, getting set up with the version control system the project is currently using is essential for making serious contributions to the codebase.  Git repository hosting providers such as GitHub, GitLab and BitBucket provide git repository hosting for Open Source projects that can be easily cloned to your local or virtual machine via git requests from the command line.

## Where and how to ask (sidebar?)

Different projects may have standardised on different procedures for providing help to developers and users.   Sometimes you can encounter problems carrying a practise that is common in one project over to another that prefers a different approach.  For example, many projects are happy for both users and developers to open issue 'tickets' on the version control host such GitHub or GitLab; while others will prefer that those issues are only opened by core team members, and that discussion of features, bugs and chores as well as high level project direction should take place on a mailing list such as Google groups, that can be accessed via the web or through email updates.  You may have your preferred approach, e.g. you have a GitHub account and are used to opening issue tickets and having the discussions there, while other projects might prefer to have those discussions in IRC or other text chat environments.  It is sensible to read the project documentation on where to get support, as asking in an unexpected place will likely make it longer before you can get the help you want.  Sometimes it's a difficult balance.  You're exhausted from trying everything you can think of to get round some installation problem, and only have the mental energy to ask in the same way that you've tried previously.  A fair number of project maintainers would probably like you to just go ahead and ask, rather than losing your contribution.  Remember a question about an issue you are stuck on is still a contribution.

It all depends on the project maintainers and community.  They will be under varying levels of pressure from project work, from their outside lives, their attempts to earn a living and so forth.  Long term project success can come from a variety of factors, and sometimes a ruthless adherence to a particular work flow will be the key, but on a different day and in a different project it may be that being as welcoming and open as possible to all contributions is what unlocks long-term success.  As the person wanting to get support for a particular issue it's great to keep in mind the perspective of the folks you are asking help from.  Of course, you too have your own pressures, your own life, your own attempts to earn a living, and sometimes being asked to ask in a different location or using a different medium will be the last straw and you won't come back to the issue.  A great compromise position is to ask your questions on StackOverflow and then post the link to whichever help forum the project recommends or that you can find given your current energy level.   The huge advantage of posting a well-formed question to a general techincal forum like StackOverflow is that you can potentially get helpful input much faster than from the project team themselves, and the project maintainers and team can earn StackOverflow reputation by answering your questions there.

Of course, actually posting on StackOverflow itself might be a bigger barrier to some than posting to a project forum, since it is arguably more public, and sometimes those replying on StackOverflow will be less sensitive to the feelings of the poster than a project maintainer or team, but it all depends.  The skill of constructing a question such that it is easy to answer is something that needs to be practised.  One's ability to form an easily answerable question is a function of one's level of fatigue, emotional state, experience, maturity and so forth.  There is a natural tension between those struggling for help and support and those who can potentially offer it.  Those giving help would almost always like those asking for help to do more to make it easier to help them and vice versa.  StackOverflow offers [great advice on how to ask a question](http://stackoverflow.com/help/how-to-ask), if not how to deal emotionally with the challenge of asking in "public" and receiving critiques on your question from strangers.  Be brave!

## READMEs and CONTRIBUTING docs (sidebar?)

Files named 'README' have been around in Open Source projects for a long time, drawing users and contributors' attention to the first place to start reading before doing anything else.  GitHub, GitLab and others have set up their websites so that files with these names will be prominently displayed in the view of a project.  If you're interested in contributing or simply installing a project it makes sense to start with the README which, at the very least, should provide pointers to places where more information is available on a variety of topics.  CONTRIBUTING docs are like READMEs but focus specifically on those trying to contribute to the maintenance and development of the project.  GitHub has adjusted their interface so that a link to the CONTRIBUTING document is displayed prominently when anyone opens a pull request on a project.  Like many people you may hate reading documentation, but it is worth holding your feet to the fire to read at least these two documents.

## When and how to contribute

Having joined a mailing list or text chat room for the relevant project, it certainly won't hurt to spend a little time at least skimming the messages that are flowing back and forth.  There may be a lot that goes over your head, but it should give you a flavour of the project community.  Communities like AgileVentures encourage everyone to join in any [asynchronous voting](https://github.com/AgileVentures/AgileVentures/blob/master/ASYNC_VOTING.md) that's going on in a channel.  If you're interested in contributing generally rather focusing on a specific feature or bug-fix then do introduce yourself in the text chat or mailing list and ask if there is a good place to start helping out.

Also, some projects will host open scrums or standups (using systems such as Google Hangouts) that may be advertised in project forums.  If you see one of those do jump in and say hi, as it's a good chance to ask if there is anything interesting to work on.  Scrums can also be pair hookup sessions where the scrum master will try and hook you up with a pair programming partner if you want one.

### Voting or Planning Poker (sidebar?)

Planning poker (or voting on issues) is a process where a group conducts a vote to estimate the complexity of implementing a feature.  The usual procedure is that one person will outline the feature to be estimated, and there will be a short discussion of anything that is unclear from the feature description.  The group votes once everyone participating is happy that they have enough information in order to make some sort of assessment of the complexity of work needed to complete the feature.  If done in person this usually involves everyone simultaneously showing a number of fingers from 1 to 3, or by revealing specially prepared planning cards with numbers on.  In a text chat environment this can be done my everyone simultaneously typing a number and pressing return on a cue from whoever is coordinating the vote.

The point of all the votes being revealed simultaneously is to avoid the cognitive bias of anchoring, where others will often just follow suit if one person votes for a particular level of complexity first (usually 1 = simple, 2 = intermediate, 3 = hard).  If there is a consensus when the votes are revealed that number can be assigned to the issue (perhaps on a physical or digital Kanban board) and the group can move on to other issues.  If there is a disagreement then the reasons for the disparity can be discussed, and re-voted on.  The point is not to have a long protracted argument, but to expose implicit assumptions about the work at hand that might otherwise not come up through a simple discussion.  Given appropriate support one can even conduct these votes asynchronosly and online, with all votes being revealed once a sufficient number of members have voted.

### Scrums and Standups (sidebar?)

Scrum is a specific Agile project management technique that tries to address the possibility that clients will often change their minds about what they need from a project during it's development.   Open Source projects will not always have a clearly specified client, and may support a fuzzy community of users each with varying needs and preferences which may well vary over time.  Scrum is a reaction to the idea that traditional planning methods have trouble dealing with unpredictability.  Scrum is described as a feedback-driven empirical approach, which focuses on short term planning over a timeboxed "sprint" such as two, three or four weeks, which is kicked-off by an initial planning session during which the scope of work is specified and individual items of work are voted on and assigned to different team members.  Team members will commit to working on specific tasks for the duration of the sprint, meeting regularly in a daily "Scrum" which is tightly timeboxed (e.g. 15 minutes) to give everyone a chance to give a quick report on how things are going, particularly if they are blocked by anything.  The key thing here is to have a lightweight mechanism that allows team members to support each other, without consuming lots of time in long meetings.  The possibility that one team member could help another with a problem can be surfaced in the daily meeting.  However the problem would be diagnosed and fixed on a seperate occasion with anyone who is interested participating, rather than requiring the attention of the whole team.  

Scrum also specifies that at the end of a Sprint, the completed work should be presented to the stakeholders, and that the team should spend some time in a retrospective event. Retrospectives involve reflecting on how the sprint went, and what could be improved to make the next Sprint more succcessful.  Scrum is also characterised by particular roles for some team members, such as the Scrum master who ensures that the agreed Scrum practises are followed and the Product Owner who ensures that the wishes of the stakeholders are represented effectively throughout the process.  There are lots more details to Scrum implementation, and the term can be confusing given that it may be used to refer specifically to the short daily coordination meeting or "Scrum".  This is also sometimes called a "Standup" since it's common to stand rather than sit to reduce the chances of the meeting dragging on.  Scrum is said to be ideally suited to teams that are working closely together in a full-time co-located capacity, which is not always the case for Open Source projects.  Modern teleconferencing systems have made it possible to implement Scrum over a distributed team, and Open Source projects may adopt differing subsets of wider Agile and Scrum methodologies depending on the levels of commitment from their contributors.  If a project does include some sort of daily standup or scrum, then it can provide great insight into the project and the team processes used.  Some projects may do these meetings in a text format, or even record videos of the event.  If you're too timid to take part, do read the text or watch the videos and absorb as much information as you can.  When you feel ready to take part these events can become an even more valuable resource for getting help when stuck.

## Reading the project documentation

It certainly doesn't hurt to read all the documentation associated with the project, in particular the user stories in any feature tests.  In reality the project documentation may well be out of date, and possibly contain inaccurate information.  This is a particular problem with documentation that is not executable.  Natural language documentation has to be manually checked for accuracy, and not every project has the resources to be checking as often as they would like.  Executable documentation such as Cucumber scenarios has the advantage of being checked by test runs, but there's still no 100% guarantee.  If you ever find inaccurate, unhelpful or out-of-date documentation for a project, please highlight it to the project maintainers.  If possible please submit a pull-request to the documentation to fix the issue you encountered and the project managers will be very pleased if you can take a proactive role to help then with the burden of keeping the project documentation up to date.

### Cucumber (sidebar?)

Cucumber is a testing tool that allows developers to write tests in a natural language format (called Gherkin), e.g. 

```gherkin
Given that I have logged in
When I unsubscribe from email notifications
Then I should not receive any more email notifications
```

Through the use of "step definitions" each of these steps, the 'Given', 'When' and 'Then' sentences, can be connected to an explicit code action that exercises the underlying application, or checks some aspect of its behaviour.  Thus the "Gherkin" format provides executable documentation that will fail when the behaviour of the underlying system changes.

This is not entirely foolproof as even with the best of intentions the natural language sentences can be connected to pieces of code or tests that themselves contain subtle bugs.  Although in principle anyone can read this documentation, the big advantage of describing the system behaviour in natural language is that old and new developers alike can have greater clarity on the intention of a particular system feature, independently of their degree of familiarity with the specific testing and code syntax used in the project.

### Pull Requests (sidebar?)

In the past contributions to open source projects were often made by the contribution of "patches", chunks of text that specify where to insert and delete lines of code.  GitHub has popularized the concept of a Pull Request, which is now in common use over many online version repository hosting services.  A pull request is a request to pull in a code change; to implement a feature of fix a bug.  Effectively a pull request is a patch, but is generally easier to generate as pull requests can be made from another branch or fork of the code, and the precise differences between the two versions encapsulated in the pull request itself.

The pull request is treated as a resource which can be viewed online, and can have an associated discussion, output from code quality and continuous integration tools, and serve as a focal point for considering whether a contribution will be pulled into the main project.

### Branches and Forks (sidebar?)

Modern version repository hosting services allow free "forking" of open source projects, which create a complete clone of an existing project.  A fork is a fully feldged repository in it's own right, only distinguished by being connected to the head of the fork, i.e. the original codebase repository.  This can be used by those participants who don't have core commit access to make changes and then suggest pull requests, or even just take the project off in a completely different direction.  Branches are also copies of a codebase, but exist within a single repository - each fork may have multiple branches.  Branches can be used to isolate development on a particular feature or bug-fix, where it won't interfere with other work taking place.  Branches are often short-lived copies of the codebase that are quickly merged back in the main 'master' branch. 

## Contacting the project manager

One of the key things to do when becoming involved in a project is to try and make contact with the "project managers". Project managers will often be maintaining projects in their spare time, and be trying to hold down paid jobs and manage all sorts of other life complexities.  Try to avoid reaching out to them individually if possible.  You may feel shy and/or embarrassed to ask questions in a public project chat, mailing list or GitHub issues, but most project maintainers will be eternally grateful for questions that can be seen and answered by others on the team.  Asking for suggestions of things to work on, or help and support in a shared channel has the key benefit of reducing pressure on the project maintainers (as other team members can offer help) and also shows the pulse of the project, i.e. that people are interested in contributing.  Sensible project maintainers will always do their best to ensure that any question or concern shared in a public channel is met with consideration and understanding.  

Conversely, please don't feel bad if a project maintainer asks you to take a line of reasoning or questioning to another channel or a direct message (DM).  A very detailed multi-paragraph debate about the pros and cons of a particular approach can be exhausting for those trying to keep up with the project.  While some spirited discussion can be invaluable, there does come a point when the discussion should be paused and further information gathered by just trying one or other approach out.  If there's a strong disagreement about particular approaches, a pull request (see below) is usually a better place to take it up, where specific code can be used to ground the discussion.  Even then, do be careful as protracted debates can be exhausting for all concerned.

## Understanding the project contribution flow

A great way to get oriented to a project is to ask for an overview session with the project manager (in a shared hangout or discussion or chat).  Since the many open source staffing models rely heavily on volunteers, team compositions tend to be fluid as people come and go.  As a result, projects need to "on-board" new members quite frequently.

If you're not receiving responses in a project channel, try adding the name of one of the project managers to your message in that channel, to highlight that you need help moving forward.  Each project will likely have a slightly different project contribution flow.  Usually there will be some issue/ticket tracking system (e.g. Waffle, PivotalTracker, Jira, GitHub Issues/Projects) indicating work that is in progress, ready to get started, and possibles for the future.  Check with the individual project managers, and see the specific projects documentation.

### Kanban (SideBar?)

Kanban is a process of visualizing work and workflow, representing items of work as "cards" that can be moved from one column to another where the column represents the state the work is in, e.g. "unstarted", "started", "finished", "delivered", "accepted", "rejected".  These days most projects will have some form of KanBan style representation of the ongoing work in the project.  Waffle, ZenHub and GitHub Projects provide a Kanban style visualisation over Github issues, and PivotalTracker, Trello and others provide highly customizable boards for project management of all kinds.

## Submitting your first “pull request”

Most projects will prefer to receive contributions through the form of "pull requests" (see above), a confusing term that means a request to pull some code or documentation into the project.  GitHub has good [documentation on pull requests and how to make them](https://help.github.com/articles/about-pull-requests/).  Simple pull requests may even be made directly through the GitHub web interface, but they will usually involve you checking out the codebase to a machine under your control, making changes on a feature branch and then submitting a pull request to one of the main project branches so that it can be reviewed by the rest of the project team, feedback given, and then ultimately pulled into the main codebase by the project maintainers.

## Going with the flow

It is often helpful to read over any pull requests that the project has open (or at least a couple if there are a large number open) before you submit your own pull request.  You don't have to add comments, but you can learn a lot from just reading the open pull requests, seeing what issues they are trying to address, looking at the code changes, seeing how the project managers and team members are responding to the incoming code changes.  If you're up for it you will be potentially making valuable contributions by adding your own comments to the existing pull requests by joining in the discussion about the changes being made.  Remember that you don't have to work in isolation.  By contributing to an open source project you can "join a team".  You may not stay long, but your contribution doesn't exist in a vacuum.   The more you understand about what the other team members are working on, the more you can learn from them; and the more effective you can be at contributing something that doesn't conflict with, and hopefully complements, the changes they are making.

Not much time to spare?
----------------------

You might not have the time required to get set up with the complete codebase, and work through fixing a bug, completing a chore or implementing a story, but there are still lots of ways you can help.  See the list below for how to contribute based on the chunk of time you've got available:

* &lt; 15 minutes to spare?  [Review a pull request](https://help.github.com/articles/about-pull-request-reviews/), [vote on a ticket](https://github.com/AgileVentures/AgileVentures/blob/master/ASYNC_VOTING.md), or even start a new vote
* &lt; 30 minutes to spare? join a scrum and say hi, giving an update on what you're doing; read a project's documentation; observe a pairing session
* &lt; 60 minutes to spare? Start getting set up with a code base for a new project
* &lt; 90 minutes to spare? Start working on a ticket, join a pairing session

### PairProgramming (sidebar?)

Pair programming is an extreme programming practice that follows from the idea that if code review is good, why not have two pairs of eyes on all code at all times.  Effective pair programming involves frequence driver/navigator rotation, where each individual in the pair takes turns at typing code, and doing support tasks such as looking up documentation, of thinking more strategically.  Pair programming might seem like a waste of a second programmers time, but when well coordinated it can be enjoyable, educational and improve code quality.

References
----------

* [Git Basics: Getting a Git Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
* [GitHub's guide to contributing to an open source project](https://guides.github.com/activities/contributing-to-open-source/)
