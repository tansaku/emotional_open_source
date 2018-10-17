How Does Open Source Work?
--------------------------

:construction: UNDER CONSTRUCTION :construction:

_The difference between open and closed source software; who pays for work on open source; examples of successful open source projects_

So, open source software; different from closed source.  Closed source being where the code that runs the software is hidden, as opposed to being available to the general public to browse in some form.  In broad terms that's it. Closed source software, also referred to as proprietary software, involves intentionally restricting access to the software code.  Usually access is restricted to employees of a particular company or organisation, or possibly to specific teams within those organisations.  But why would anyone want to restrict who looks at the raw code for a particular piece of software?

Conceivably if you're a company who's just paid some programmers a lot of money to write the code for the software and you are hoping that you will make at least some of that money back by selling the software you might well not want people to review that code by themselves, since they might be able to make the same software and sell it cheaper than you.  Or they might be able to package it up and just run it for themselves without needing to pay you.

In the early days there wasn't a clear distinction between open and closed source.  Early computer hobbyists freely exchanged their software code.  There wasn't an internet to easily share code on.  Then software companies got in on the act and wanted to derive revenue from the software they were creating.  Other companies liked the idea of having a specific company responsible for the correct operation of their software, someone they could call for technical support and someone they could sue if things went really wrong.  This was the dominant model towards the end of the last century, but then it started to seem that even very large and powerful companies were having trouble keeping up with open source operating systems like Linux which operated on a completely different model.

The source code for Linux was freely available for anyone to look at.  In addition the project was set up to welcome contributions for changes to the source code, and under the guidance of Linus Torvalds the operating system grew and improved and became a serious competitor for the then dominant closed source solutions.  These days it's a given that many organisations large and small will rely on open source operating systems like Linux, particularly in the cloud.  It wasn't always the case.  For a long time the received wisdom was that these hobbyist projects couldn't compete with proprietary systems for security or features.  In the long run however it's the open source systems that are more secure and robust because they can rely on a global community to help them evolve and adapt, rather than on the command and control structure of a single organisation spending most of its time trying to keep its secrets safe.

Now this doesn't mean that open source is a panacea solution for every software project.  Linux is a special case of timing and circumstances but it shows us what is possible; and there's still the question of who pays for all this work.  In recent years we've have the odd spectacle of tremendously wealthy multi-national corporations being dependent on the volunteer time of open source coders putting in efforts here and there on critical pieces of network infrastructure (https thing?).  Is open source software supposed to survive on the good will of programmers contributing in their spare time?  How are those programmers supposed to make money from their day jobs if we're replacing all proprietary software with open source alternatives?

There are various approaches to funding open source software which include, but are not limited to:

### Selling the software sometimes

* Dual Licensing

  - One version of the software is available as open source, while another is closed source and proprietary. Oracle's MySQL is available under a dual license, as is MongoDB.  Customers can be attracted to the open source version and potentially upsold to the closed source enterprise edition.

See also https://en.wikipedia.org/wiki/Multi-licensing

* Delayed Open Sourcing

  - This involves keeping the latest version of a software package closed source, but releasing older versions as OS after some time period.  The value of this is that customers will pay for the latest version, but are also reassured that there will potentially be community support for older versions, meaning they will have an option rather than always being forced to upgrade to the latest version.

* Open Sourcing on End of Life

  - An extreme version of the delayed release is only open sourcing at the end of the commercial life of proprietary software, again for the benefit of communities that might want to maintain that software.

* Re-licensing under a Proprietary License

  - Apple did this, taking the BSD Unix operating system kernal and using it in Apple's Mac PCs which are then sold as proprietary products.

### Selling something else 

* Selling Professional Services

  - While the software is given away for free, organisations can sell services such as training, technical support and/or consulting related to the software itself.  RedHat and IBM do this around the linux operating system.  Other commercial services could include compiling and packaging the software into a binary, and/or providing physical installation media such as DVDs.

* Selling of Branded Merchandise

  - The Mozilla and Wikimedia Foundations sell branded merchandise articles like t-shirts and coffee mugs.

* Selling of Certificates and Trademark Use

  - The LMS education company Moodle has a business model that involves certifying and licensing a network of commercial partners who are then authorised to use the Moodle name and logo.  A proportion of the revenue is then contributed back to core development by the Moodle Trust. 

* Selling Software as a Service

  - While the software may be open source, it is possible to sell subscriptions for online accounts or server access.

* Selling of Optional Proprietary Extensions

  - Optional extensions, modules, plugins or add-ons can be sold by a company for use with an open source software package.  Assuming the extension and the core code are sufficiently separated by interfaces then this can still adhere to the core open source license.  IBM, RedHat and Cloudera sell optional extensions of this kind.  There are also vendors of optional electronics hardware that work with a free open source software project

* Selling of Required Proprietary Parts of a Software Product

  - Several games have been released open source, while requiring payment for non-software digital content such as artwork, audio or graphics materials. FSF/Stallman approved.

* Selling of Proprietary Update Systems

  - Another approach involves making the update scripts closed source.  Each individual version of the OS software is open, but the update script is closed.  This might seem trivial, but in data-intensive applications that require a big data export/import between versions, clients may be willing to pay to make that process easier. Not FSF/Stallman approved.


### Getting help from those with money

* Partnership with Funding Organisations

  - Some organisations may release code as open source when they've developed them internally as part of an open source partnership.  These organisations can be NGOs, companies, universities or governments and may hire contractors, internal developers or provide grants and stipends as does Google's Summer of Code.

* Voluntary Donations

  - Those interested in the success of open source projects may be willing to donate to see them reach their goals.

* Bounty Driven Development

  - The development of individual features or functions in open source software can be incentivized by bounties, such as the Ethereum bounties of Gitcoin.  Mozilla pays and funds for security bug hunting and fixing via bounties, as does the [BountySource](https://www.bountysource.com/) platform.

* Pre-Order/Crowdfunding/Reverse-Bounty Model

  - Crowd-funding platforms such as KickStarter and IndieGogo provide frameworks to collect "pre-orders" or "donations" from individuals that can be used to pay for open source software development.

* Crowdsourcing

  - In the absence of funds per se, one can crowd-source the development of open source software, asking developers and other professionals to devote their time to the development of the software.  Linux, Google Android and Wikipedia are in part successful examples of this approach.

* Advertising Supported Software

  - Revenue can be generated from adverts on the site promoting the software.

  
### Making it not so open  

* Obfuscation of Source Code

  - Some companies release source code in an unreadable obfuscated form to be able to say they are open source, but to prevent anyone else actually understanding the code.  Not FSF approved.

References

* https://en.wikipedia.org/wiki/Business_models_for_open-source_software

