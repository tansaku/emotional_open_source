What does it mean to be Agile?
------------------------------

:construction: UNDER CONSTRUCTION :construction:

The Agile Manifesto; the alternatives for project management; the evolution of the Agile approach and variations & components such as XP, Scrum, Kanban etc.

Once upon a time I wanted to write a book about Agile Open Source projects.  However over the last few years it feels like the  term "Agile" has lost some of its gloss.  In 2012 I was taking part in a Massively Open Online Class (MOOC) and hearing all about how Agile was an alternative to Big UpFront Design (BUFD) and the waterfall style of project management.  It sounded great, so great in fact that I started an organisation that was going to be called "Agile Projects", but agileprojects.org was taken so I grabbed agileventures.org instead.

Agile now seems to mean a lot of different things to different people, but I'm still enamoured with the original [Agile Manifesto](http://agilemanifesto.org) and its emphasis on collaborations, human interaction, working software and adaptive response to change.  There's also a less well read [12 Principles behind the Agile Manifesto](http://agilemanifesto.org/principles.html).  I [previously went through all these principles](https://medium.com/agileventures/agile-workshop-d3d456857843), grouped them up into related chunks and explained how we addressed them in our online open source projects:

> 1. Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.
> 3. Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.
> 7. Working software is the primary measure of progress.

In any software project it feels like the looming danger is spending too long without showing the client or customer what's going on.  Many clients are very busy and would likely appreciate not being bothered by the developers every couple of weeks in order to check that everything's going in the right direction.  However clients are likely to be even more upset when they discover that what has been built doesn't do anything they want.  Assuming one can find a specific "client" for a project I'm keen to meet them at least once every two weeks to show them the latest developments and get feedback on any changes, as well as showing them work in progress.  

> 2. Welcome changing requirements, even late in development. Agile processes harness change for the customer’s competitive advantage.

In every meeting it's usually a good idea to go over the project board with the client, with a particular focus on the features in the backlog, so that it can be re-ordered to match the clients changing priorities.  In the absence of a specific client it's up to the individual developers and users to help order the backlog and move features/tickets in and out of an icebox.

New suggestions from the client should be added to a ticket immediately and placed in an icebox. It's then often a good idea to go through a voting process with the tea to estimate their technical complexity. Once they are estimated they can be moved onto the backlog with the client’s consent and subject to the client’s preferences regarding priority.

> 4. Business people and developers must work together daily throughout the project

This can be challenging with a distributed team of developers all around the world. We broadcast the client meetings via YouTube, and run it in a google hangout that developers are encouraged to join. Any developer can participate in a client meeting, and can communicate with the client via email. However as project manager I tend to funnel questions from developers through to the client, and bring them up in the client meeting. Given the part-time volunteer nature of our project it is difficult to support daily interaction between client and developers; and since we are all developers our “business people” are arguably the client, although we make no strong distinction between devs and non-devs in our distributed team. Everyone is learning, everyone is participating.

> 5. Build projects around motivated individuals. Give them the environment and support they need, and trust them to get the job done.

Every developer is free to work on what they are interested in. The client’s preferred priorities are expressed through the priority ordering on the backlog, but developers can start any story that takes their interest. We do strongly encourage all developers to put any unestimated story to a vote (either synchronous in a scrum, or asynchronous in a text vote) before starting work on it; just to help increase awareness that they are interested in working on something. They don’t need to wait for the vote to complete in order to start a spike or some experiments. However it makes strong sense to let others know what you are thinking about so you can benefit from their thoughts and suggestions. Even so this is not a hard and fast rule. The software is open source and anyone can submit a pull request at any time, but getting involved in the voting and estimation process is a great way of staying on top of any information relevant to the task and increases the chance of a smooth merge of code later on, while reducing the chance of duplicated effort.

> 6. The most efficient and effective method of conveying information to and within a development team is face-to-face conversation.

We agree, but we can’t afford to fly all the developers into the same location for this purpose. Google hangouts gives us a close second to a face to face conversation, and I try to meet with the client in person where possible.

> 8. Agile processes promote sustainable development. The sponsors, developers, and users should be able to maintain a constant pace indefinitely.

We’ve been maintaining a slow and steady pace for the last three years.

> 9. Continuous attention to technical excellence and good design enhances agility.

All code is submitted to the project via Pull Request for open review. We encourage everyone to use Google hangouts to pair program online in order to get more immediate ongoing feedback as code is developed, although the logistics of time zones and lives don’t always support pairing. Even with paired code, everything coming into the project is automatically checked for merge conflicts, tests passing, and style/coding guidelines. Any developer can comment on any pull request, which we try to either close or merge within a week to avoid widely diverging branches. The ultimate decision for merging rests with myself as project manager, and I try to maintain a match between any code coming in and the domain model that we have developed over the last three years.

> 10. Simplicity–the art of maximizing the amount of work not done–is essential.

I strongly encourage all developers, whether working on a chore, a bug fix or a feature, to submit the absolute minimum of code. Only things related the specific ticket being worked on should be in the pull request. The smaller the code changes in the pull request, the happier I am. Small pull requests are easier to review, easier to merge, can often be done faster, and provide a more frequent sense of completion and progress for everyone involved. See something else that needs to be fixed? Open a refactoring ticket and submit a separate pull request for that. There are always new folks coming into the project who will love a really simple refactoring ticket to allow them to get started on something where they don’t have to generate new tests.

> 11. The best architectures, requirements, and designs emerge from self-organizing teams.

I’m a single point of failure in this project, although two or three others have access to all the necessary to continue merging and deploying if I was removed. Other AgileVentures projects have more self-organising structures where PRs can be merged with the agreement of any 2 or 3 devs. All structures are subject to revision. Sensibly the LocalSupport project management structure will evolve and change.

> 12. At regular intervals, the team reflects on how to become more effective, then tunes and adjusts its behavior accordingly.

Earlier in the project we had weekly retrospectives, but with few dedicated full timers, these have fallen away. We’ve switched from many synchronous standups to more asynchronous voting in group text channels on Slack. The Agile principles are written around the idea of a full time co-located team, and we have adapted them to a volunteer part-time distributed team. Our adaptations certainly need ongoing review and adjustment. It’s not yet clear how best to ensure reflection. Tuning and adjustment happens on an ad hoc basis at the moment.
