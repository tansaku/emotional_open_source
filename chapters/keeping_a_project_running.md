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

Depending on the experience and circumstances of the contributor they might need help to understand and make any of the above changes.  Some pull requests might require many, even all, of the above changes but asking for every single change to be made at the same time will likely overwhelm and overload both new and old contributors.

The key technique that's excited me recently is not having to get PRs from others perfect before pulling them in.  In a wonderful step GitHub has made it so that by default you are able to edit others PRs on your project which means that if there are little changes you want made you can just make them.  This is great because those little changes will often be tedious for others to make, and when they are volunteering their time, the request for those minor changes might be the thing that causes the PR to die.  Of course sometimes the contributor will really want to be the one to make the suggested changes as part of their own learning or simply getting the satisfaction of having made the update.

In the past I have often thought that in order to maintain the code quality of the project we must keep requesting changes until a pull request is of sufficient quality, but my rule of thumb now is to ask for one or two rounds of non-trivial changes before merging it in or closing it.   Where possible any trivial changes should be automated or made my the maintainer themselves.  Contributors get a great emotional boost from having their contributions merged, so unless it is a security risk or will break the build then I think it's preferrable to merge the PR in and then if, as the maintainer, you have serious concerns that the code should be going in a different direction, or you want extensive variable renaming etc. then you can make those changes yourself later.  Or serendipitously discover later that actually those changes you wanted weren't so important.

Naturally given committed contributors that you have good communications with, you can discuss the code direction and domain model (naming etc.) in friendly terms in a way that hopefully doesn't quash people's enthusiasm.  However when people are getting started the boost from having just a single round of simple changes and getting their PR merged can reap dividends in terms of the mood of the community and the contributors enthusiasm for the project in future.


Managing Project Flow
=====================

Network Testing
----------------

Testing level abstraction (Mark Burns)

* allow tests to hit network
* record and cache the network interactions
* stub the network calls
* stub the libraries that wrap the network operations

Mark Burns suggests:

> Generally I think people tend to test HTTP services at the wrong abstraction. So it might be why it’s a pain point for you. Your non http related test code ends up having to know about http (via VCR or web mock or whatever).

> It might be easier for you to wrap your services in a gem or library and inside that library thoroughly test the HTTP interactions.

> Then outside of the library avoid the leaky http abstraction.
> I’ve seen and done it myself so I wrote a post about it a few years ago. It’s probably a bit dated now.

http://blog.polyglotsoftware.co.uk/2014/02/07/a-pattern-for-stubbing-out-apis-with-rspec.html

The rule of thumb that we've followed it to make our acceptance tests (using Cucumber/Capybara/RSpec) as "realistic" as possible, so they use VCR as much as possible, and webmock in places where we need extra confirmation about network connections (just reviewing I think we're mainly recording interactions with 3rd party services such as stripe, pivotaltracker, codeclimate and github).

> These are exactly the kinds of tests that you should be able to draw a line in the stack trace beyond which you stop testing and start trusting.  Presumably you’re using a gem for this. As soon as you enter that library code is the point at which it makes sense to stub or mock.  Your business has already implicitly chosen to trust these services and gems.  I’d say you gain little extra confidence from recording and replaying those interactions for every integration test. Now if you _did_ want to be more cautious, you could always have some tests that test the specific integration and occasionally update the cassettes. But most of the time you’d be repeating tests that should exist inside the gem test suite. And it’s literally not your business to be doing that. Unless you wrote the gem. But even then the tests should live together and not be repeated all over the test suite for unrelated tests.  It’s probably only an approach I’d advise if I didn’t trust the third party and still I would want localised tests for the specific integration.  But if it were the case that I didn’t trust the gem’s own test suites, I probably wouldn’t have recommended using them anyway.

Our unit tests are all well stubbed, and then the integration tests have a mix of gem stubbing and webmock.  You might well be right, and perhaps we need to give up on purist "realism" in our acceptance tests and use more gem/library stubbing ...

What's unclear is how much the more "realistic" acceptance tests have ever bought us (nothing? a little? a lot?), compared to the trouble it creates for new developers trying to manage the VCR caches ...

> I’d guess close to nothing, but costing a lot. 

Tim Diggins says:

> I think a few "smoke tests" with as realistic end points as possible are really great -- but for me, these need to run primarily on CI rather than on developer machines (so VCR never seems like an option to me, but maybe I just don't understand it well enough) -- and I've tried to go with fully real services (e.g. a real google sheet, a real (but sandboxed) payment processor) etc. Then if I've got a smoke test ~ per service, then hopefully it is just flakey enough to fail when something substantial changes with that service (or our usage of it), and hopefully not so flakey that we just say -- oh that's just that flakey smoke test, let's ignore it (though "rerun" on CI usually gets around that.

> I think it's worth identifying the division(and function) of smoke tests as opposed to  acceptance tests. One to ruminate on.


Network caches

* automatic re-recording
* manual update (using live mode?)


Machine to machine variation

Rhodri Davies says:

> When you say cache are you referring to cassettes? If so then I've always kept them in the repo. If there are fields in the request/response that vary from machine to machine then there are ways to get VCR to ignore those fields. 

Yes, the cassettes.  We also have puffing billy caching network interactions from the browsers running in the acceptance tests, so I tend to use the word "cache" to refer to the set of files that VCR and PuffingBilly generate and "manage".  Perhaps I am using the term incorrectly ...

That's an interesting idea that some of the problem is caused by machine to machine variation, e.g. in the user agent field of what have you.

I had been assuming that the problem was arising when tests failed on another developers machine (for whatever reason) and then a slightly different set of network interactions was arising.  Or more specifically when a developer was working on a new feature and adding to the tests and then seeing a load of new cassettes and not being sure about whether to add the files, leave them out, .gitignore them or what.  Not such a hassle for an experienced developer, but working with a lot of folks just getting into coding it seems this is a particular pain point.

Recently I've been working with some projects that involve webdav and I've noticed the testing setup involves running a little test webdav server locally to give a complete endpoint for the client to be tested against.  In another project we set up a dummy test server for the tests to run against - not disimilar from what Stripe provides.  These are feeling like good options to me at the moment as it seems to allow removing the brittleness from acceptance tests, but I expect there are downsides.  Trying the same approach in a closed source project I'm experiencing inconsistency, but I think that may just be me not using node promises correctly ...


Notes
-----

Could ask LRUG about various things:

* what folks are doing with VCR caches (dependabot concept)
* automated deployment along develop, staging, production pipeline ...
* their thoughts on responding to pull requests ...
* how to get CI to pop the actual error message into the PR
* instance variables discussion

Refactoring Directions
----------------------

There can be many motivations for extracting components (methods, objects, functions, what have you) from existing code that might be judged in need of refactoring, e.g. 

* the current code is not easy to unit test and we want to make it easier to test
* we want to practice the process of refactoring code into smaller components
* we want shorter files for readability and maintainability
* we want (or just anticipate) to re-use the smaller components

There's the DRY mantra which is Don't Repeat Yourself and at the high level is a warning about copying and pasting the same code into multiple places.  Repeating the same code over and over means that the code is longer and when that small section of code needs to change, it needs to be updated in multiple places.  However it's also important to note the flip-side of DRYing things out, which is that each time you do it you introduce a dependency, a single point of failure.  The real difficulty is that no one has a privileged view of the future, being able to predict precisely when and in what ways the code will need to evolve to meet users needs.  There may be general agreement that a spaghetti mess of replicated code with little apparent rhyme or reason is a nightmare to maintain, but personally I tend to use the rule of three and my knowledge about upcoming feature requests and likely changes when deciding whether to DRY something out.

Seeing some piece of code replicated two times is not enough for me.  If only twice I worry that the two pieces of code might need to diverge in future, and that prematurely DRYing them out will force me into a situation where I have to extract the two pieces out again later on in order to support that divergence.  You might say, hey, well when you need to split them back out, split them back out then, why worry about the future?  The point is that I don't have unlimited spare time to spend on arbitary refactorings if I want to continue to be able to keep working on the kinds of charity open source projects I want to work on.  I'm not being paid for arbitrary refactorings, but for delivering working software to clients, or not being paid for it, but that's another story :-)

Ah, you say, but refactoring the code well will ultimately help you deliver working software to the clients, and to an extent you are absolutely right, but which is the right refactoring and when is the right time to do it?  I don't think anyone would assert that there is any refactoring that is absolutely correct.  It all depends on how the code will evolve in the future, so I like to see something repeated at least three times before I start to really pay attention to it.  Of course that's another rought guideline that could be overlooked when the circumstances demanded.  The point I'm trying to make is just that caution should be exercised on both sides; excessive refactoring and too-little are both evils depending on the circumstances.

Imagine that we're perusing some code with the following chunk structure:

```
chunk 3
chunk 4
chunk a
chunk 5
chunk 6
chunk b
chunk 7
chunk 8
chunk c
chunk 9
```

and we notice that chunks a, b and c are extremely similar, nay identical, and that we can refactor the code by extracting a method out called `foo`.  Now our code looks like this

```
chunk 3
chunk 4
chunk foo
chunk 5
chunk 6
chunk foo
chunk 7
chunk 8
chunk foo
chunk 9

method foo
  chunk a/b/c/
```

Now when we need to make a change to `foo` we can do it all in one place, rather than three times over.  And if we've chosen an nice comprehensible unambiguous name for `foo` then we can more easily understand the code rather than having to mentally parse the contents of foo each time, "unpacked" as it were, in each of the three locations.

However there is a danger, at least a hypothetical one.  What if the first chunk foo now needs to do something different from the subsequent two?


```
chunk 3
chunk 4
chunk foo <-- needs to be different from next two
chunk 5
chunk 6
chunk foo
chunk 7
chunk 8
chunk foo
chunk 9

method foo
  chunk a/b/c/
```

What do we do here?  Perhaps we set it up such that we can change foo with a parameter, perhaps a boolean that can be false by default so that `foo` retains its default functionality for the latter two cases.   Perhaps the change is more extensive and we are tempted to reinsert the changed `foo` code back into the original location:

```
chunk 3
chunk 4
chunk i
chunk ii
chunk iii
chunk 5
chunk 6
chunk foo
chunk 7
chunk 8
chunk foo
chunk 9

method foo
  chunk a/b/c/
```

All good perhaps, and difficult to imagine without the specifics of the code and the requested changes, but in some ways this is the point.  Choosing to refactor by extracting a component is a subjective judgement call that depends on the circumstances.  And as circumstances change, maybe you'll be un-doing that change in the future.  Maybe un-doing it in the future is okay.  Nicely refactored code is being considerate to your fellow developers and yourself in the future, but the future is unclear.  Taking the code in one refactored direction today could just as easily create an architecture that has to be unpicked tomorrow.  As Sandi Metz says in POODR, you should be thinking about which parts of the codebase are likely to be affected by upcoming feature requests.  If there's about to be a lot of activity in a particular part of a codebase then you might want to hold off refactoring until you better understand all the pressures that the new requests are going to put on that area. 

Quiet areas of the codebase can be less controversially cleaned up, although the pressure may always be on delivering features.  If you're lucky you're working in a situation where your living expenses are being met and are not contingent on delivering a feature by a particular time.  Then you can slowly and calmly be cleaning up parts of the codebase and taking the long view.  Many of us work in slightly more pressured environments and maybe want to avoid unpicking refactorings that didn't seem to fit with the new features that fell on us.  Maybe there are refactorings that are unequivocally good under all, or most circumstances?  If there are I'm not clear on what they are ...

