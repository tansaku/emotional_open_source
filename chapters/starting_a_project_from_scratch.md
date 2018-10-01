Starting a Project from Scratch
-------------------------------

:construction: UNDER CONSTRUCTION :construction:

Getting your idea off the ground; technology, infrastructure and architecture decisions

Do you've got a project idea, and you're considering open sourcing it.  Often a project idea comes with a bundle of thoughts about how it might make you rich and how you can sell it to others in future.

 info about the risk/rewards situation with open source. Will it be the right business decision?
 ------------------------------
 
 I don't think there are any guarantees - it's really complicated
here are some links

https://opensource.com/business/13/5/open-source-your-code

https://www.quora.com/Should-I-opensource-my-software-project

what I can say is that open sourcing the code in your project is not a magic bullet - it doesn't guarantee anything
the potential benefit is that you can get a multiplying effect of others helping you, but you might not
and in some business situations if you release everything you may give the idea to a competitor, although to be honest there are very few "new" ideas

Robert:

> open source everything - the advantages far outweigh the disadvantages

> a common misunderstanding is that ideas are a thing - it's the execution that matters

Praveen

> if the idea is about helping the community, then I think its makes sense to open source the idea.

Federico

> Speaking of learning on Twitter and open-source, just an hour ago we scheduled an AV tweet for Thursday about *the dark side of open-source.* Let me retrieve the link...

https://medium.com/@codesponsor/fighting-for-open-source-sustainability-introducing-code-sponsor-577e0ccca025

Sivan

> The Big issue with open sourcing is that you must have community support. From what I’ve read this is essential. And also, it’s not very easy yo achieve that.One reason I want to OS it that I can share the load of development. What I see as the strongest point for open sourcing is marketing. If you saw MS also open sourced lately parts of their services. But there always the risk of theft and I do want to be viligant as much as possible when managing so it would not be made into a something it had not meant to in the first place. That open source frame protect it’s core aspirations is a viable reason


in my mind there is no real such thing as "theft" in open source - the point is that you are saying it is okay to copy your code when you make it open source - so it can't be "stolen"

open sourcing has lots of benefits even if a strong community never forms around your code, and it often won't
the big benefit is that when you are asking on StackOverflow for help with something you can post a link to your repo and the person trying to help you can actually see the specific code and context of your problem and that makes it so much easier for them to help, rather than them just guessing what is going on
there's also the issue that closed source tends to be an unreliable mess ...
without many many eyeballs on code it's very difficult to create something that's easily maintainable and adaptable, so you either need open source, or to have loads and loads of cash to pay lots of great developers, and even then ...

Robert

> nobody is going to "steal" your code - usually nobody even **cares** about it

> open source has the potential (no guarantee) that people might join
> closed source makes that impossible

Matthew

> Many companies have Open Sourced major parts of their software stack and are still doing great including:

GitHub - https://github.com/libgit2/rugged
Reddit - https://github.com/reddit/reddit
Netflix - https://netflix.github.io

Mikael

> whatever you decide, open source methodology (git, issue tracking, sharing code with others) is, in my opinion, the best one. You may begin with a private repository on github, if you're afraid of opening your code to anyone, but you should prepare for opening your code to more and more people. And Making a code base portable so that anyone can install it easily is a big deal. Configuration parameters, IP adresses, passwords are sometimes where there should not be. The documentation may be poor. The issue management process is sometimes a bit bumpy..

Sivan

> Before we moved the discussion into here I had a chat about this topic with Sam and he shared this link with me, which points out that it should be a business decision first and foremost (if that’s what you’re making living of). I think  that I read it also somewhere else. Quality of  code is not the only standard. I also don’t feel that I need the whole world for a code review, one good reviewer might be able to point out the key problems about code and about UX also. And so we back to cost of development and social impact. I’m totally trying to see it from a sane point of view. But if you look at the two extremes it’s interesting. The big question for me is does open source will be able to maintain life of a developer. And I’m yet to know the answer. Most of big software companies are not really open source or their business logic part at least is not.  Here’s the link: https://www.quora.com/Should-I-opensource-my-software-project

Federico

> *To go the closed-source route* and have it viably grow into something like a Microsoft (or something much smaller, but successful), *you need immediate revenue, financing, or investment,* in order *to pay the* development and maintenance *costs.*
It can still be closed-source without financing or revenue, but then it’s just the opportunity cost of your time.

Tatyana
> agree  that "I also don’t feel that I need the whole world for a code review, one good reviewer might be able to point out the key problems...."
Some observation: I'll try to develop some extra feature in my Ruby on Rails app... but I could not find any chat room in stack overflow regarding RoR - those rooms are frozen because of inactivity.. And another hand,  Java Script room is very active: you can ask question and got the answer regarding subject.

one good programmer can fix your immediate problem, but one good programmer can't necessarily make your legacy app maintainable

Also one, two, or even a team of programmers can code an app that works, but it doesn't mean it's going to be maintainable
Why is there such a demand for programmers? It's partly to maintain all the appalling closed source code that's build up over the years
Not that there isn't appalling open source code too, but that's another story ... :-)


and in case anyone's interested in a retro blog on how we focus the AV community's plan for sustainability: https://medium.com/agileventures/focusing-on-the-right-thing-2a7c17af1a88


Who decides on whether a project would be accepted by Agile Ventures or not?
-----------------------------------

Along with a charity aspect, can the project also have a commercial angle to it?

Ultimately the decision about whether a project is accepted into AgileVentures is up to the charity trustees and charity members

we have a charity constitution with objectives of 1) open education accessible to all AND 2) helping charities, non-profits and other socially beneficial causes
the process usually starts with someone proposing a project here and us discussing whether it's appropriate - if you scroll up you can see some examples of that
projects do occasionally have commercial angles to them - I believe #take_me_away was for a normal business where the owner had agreed to make the project completely open source for learning purposes
where we'd have difficulty is supporting a project that was for a for-profit business where the code was close-sourced.  It might still have educational benefit to the volunteer coders, but really developers should receive payment for that sort of work, and while we're happy to help our members make connections with private businesses, we can't really support those projects directly
you're most welcome to brainstorm product and project ideas.  Our platform could certainly help you take that to the product stage given commitment to open source and open development so that all our members could benefit from the experience, and especially if you're committed to non-profit and charitable objectives
our official charity objects are:

> 1. To promote efficiency and effectiveness in the charitable activities of not-for-profit organisations, voluntary groups and charities including by providing software project management services and software development.
> 2. The advancement of education including by providing the opportunity for members all over the world to develop their software development and project management skills by working in teams and contributing to projects with not-for-profit organisations, voluntary groups and charities.
