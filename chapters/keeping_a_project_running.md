Keeping a Project Running
-------------------------

:construction: UNDER CONSTRUCTION :construction:


How to manage the long haul; resolving disputes; sustaining a welcoming community; handling people leaving the community; technology, infrastructure and architecture pivots





Code review, Commenting on pull requests

Github has a great section in their guide about communicating effectively and [how to submit a contribution to an open source project](https://opensource.guide/how-to-contribute/#how-to-submit-a-contribution).  From a project maintainer's perspective it would be wonderful if every contributor followed these general guidelines of:

* providing context
* reviewing the background
* being short and direct
* communicating in public
* being patient
* respecting community decisions
* keeping it classy

as well as following any specific guidelines that you may have added in your project documentation such as your CONTRIBUTING.md or elsewhere. The reality is that all sorts of people will be trying to make contributions, suggestions and/or ask questions in all sorts of different styles.  As a project maintainer you may have variable amounts of time to devote to your open source project, and many different reasons for starting the project in the first place.  Making friends might not have been the central objective when you started the project, and we certainly see all sorts of styles from project maintainers responding to members of their open source community.

Everybody has their own preferred style of communication and some prefer no-frills, straight to the point communication, and might not want to make concessions to the feelings of their contributors.  Maybe your open source project is a hard nosed piece of technical software and you're not interested in contributions from others who are not also hard-nosed experts who exactly know their stuff.  Maybe you even enjoy the process of a spirited debate in which ideas are taken apart to look for any sort of weakness or shortcoming.  Maybe it's even less about the idea and more about demonstrating that ultimately your logic and reasoning is superior to others.  Although I didn't have that thought explicitly in the past I think that some of the way that I debated and reasoned in projects could be seen in that way.

I think it was only relatively recently that I understood that some people might feel intimidated by that sort of academic debate; that some people might be put off asking a question about, or submitting to, a project because of that.  I had assumed that if someone was submitting a pull request with some code that there wouldn't be any downside to submitting it to rigorous review and debate.  In fact I thought that that was one of the reasons that the contribution was being made in the first place.

Since those times I start to think that for some people making a code contribution is a big step.  That it takes resolve and bravery in the face of various fears and concerns.  I think many people do not like the idea of something they've created being assessed, criticised, disected.  I've always relished someone wanting to start a debate on something, someone suggesting an alternate way of looking at things, even if in retrospect the relish might have been more about my ego enjoying competitive debate where I might "win" via power of intellect.  While I still might enjoy those sorts of debates from time to time, what I've realized it that others don't necessarily enjoy observing these debates.

I'm sure my mental model of others will continue to evolve, but I now think that meeting a code contribution with a detailed critique can lead to the contributor giving up on the submission.  It's not that there should never be any critique and that any code whatever the quality should be merged into every project, but that it can make a big difference to thank folks for their contribution and to be enthusiastic (within reason) about it, particularly if someone is a first time contributor.  The additional mental step that I've added before I dive into a code review is to try and get a sense about where the contributor is in their emotional journey.  Is this a regular contributor who likes the cut and thrust of debate and the pros and cons of particular coding idioms?  Is this someone who's made a few contributions and has responded positively some of my previous critiques, but is struggling with this latest contribution and is showing signs of frustration?  Is this a first time contributor who may have never opened a pull request on an open source project before?

I don't have hard evidence that our projects massively benefit from project maintainers taking this additional step of thinking about where contributors are coming from and their emotional states, but I think there have been fewer flare ups in our community since I've been doing this.  In addition I am using this approach more and more in all my relationships which recently seem to be going a lot more smoothly.  Anecdotal evidence perhaps, but it seems to make sense.  Not sure that a controlled experiment could be created or would be ethically sound, but maybe one day :-)

Doing A Pull Request Review
---------------------------

Things you might ask for:

* Adjustments to meet contributing standards, e.g.
  - branch name formatting
  - commit messages
  - pull request title and description formatting
* Adjustments to what is included in the pull request, e.g. 
  - removal of files that should not be checked in such as database config, local cache files
  - removal of files that are not related to the feature/bug-fix in question
  - removal of extraneous commits (maybe due to branches out of date, git snarl ups)
* Adjustments to the code style/formatting
* Refactoring of the code to adjust method length, class length, flow of feature
* Changes to UI
* Addition of tests
* Changes of test to remove vacuity, adjust naming
* Highlighting failures in Continuous Integration (C.I.), code coverage, tests
* requesting associated changes in production

Depending on the experience and circumstances of the contributor they might need help to understand and make any of the above changes.  Some pull requests might require many, even all, ,of the above changes but asking for every single change to be made at the same time will likely overwhelm and overload both new and old contributors.



Notes
-----

Could ask LRUG about various things:

* what folks are doing with VCR caches (dependabot concept)
* instance variables discussion
* automated deployment along develop, staging, production pipeline ...
* their thoughts on responding to pull requests ...

