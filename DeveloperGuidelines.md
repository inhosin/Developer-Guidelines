General Developer Guidelines
============================

Overview
--------

Generally speaking, no two digital projects the same and are unique in the design and implementation. However, regardless of how and what is used to execute a project, developers should follow some guidelines when working on any projects. This document serves to describe these guidelines in some detail.

Technology
----------

The word ‘Technology’ is used to describe anything that is used to develop and execute a project. It can refer to languages, platforms, frameworks, and more. Technologies used for any project are chosen based on the project's requirements and what we believe will best serve the project and it’s future development. Technology should never be chosen for the sake of using it.

New technologies and updates to existing technology are appearing at a faster rate than ever. It’s difficult to stay up to date at times, but developers should research and experiment with new technology whenever possible. Having a basic understanding of something before starting a project or deciding what to use is always a plus. 

Development Environment
-----------------------

Having a well structured and organized development environment is a great way to improve your productivity. The following is a set of tips when structuring your development environment.

- Create a folder called Workspace or Projects within your home folder.
- Organize projects within the aforementioned folder using an easy to follow hierarchy of subfolders. 
- Install any compilers or SDK’s outside the scope of your user account folder.
- Install a web server bundle such as WAMP (Windows) or XAMPP (OS X). 
- Configure your web server and hosts file to support running projects locally. 


Code Style
----------

Code style is a topic of great debate and varies widely between programming languages. The project lead should discuss code style with other developers on the project and come to a consensus on what to follow. Consistency in code style is important for many reasons, but most of all it will make it easier to digest another developer’s code. Consistency should be applied not only to parentheses, brackets, and white space but also the naming of variables, methods, and objects. For example, a good practice is to enforce using ‘is’ or ‘has’ prefixes on boolean properties e.g. isEnabled() or hasChildren().

Version Control
---------------

Whether you're using Subversion, Git, or some other VSC product, its important to follow similar practices as a team of developers. The following is a list of general guidelines to follow. It is not meant to be exhaustive.

- Commit code early and often. 
- Never commit code that contains errors or does not compile.
- Keep commits aimed at specific changes or additions. Try not to lump massive amounts of code into one commit. It’s much easier to rollback to a previous state if work on a new bug or feature just doesn’t work out well.
- Always include a descriptive message with your commit
- Only commit source files and the minimum amount of required assets into the repository. Never commit compiled files (.swf, .class, .apk, .ipa) or large binary files such as videos. Large binary files should be organized and stored on a web server, and downloaded during a build process if necessary.
- Always create a branch to add a new feature or fix a specific bug. Once you feel as if the feature is complete or bug has been fixed, merge into the trunk.
- Always tag the trunk with an established naming convention when delivering, deploying, or releasing the code base.



Bug Tracking
------------

Generally, a project lead will setup the bug tracking system so you can begin opening and responding to tickets. If you find a bug, open a ticket. If someone asks you to add a feature, or you have an idea for a new feature yourself, open a ticket. Having a back log of ideas ensures they don’t get lost. Be explicit as possible when opening tickets. If its a bug be sure to enter the exact steps to reproduce the bug. 

Don’t be afraid to open tickets for yourself. Tickets are a great way to keep track of your tasks. Lastly, get familiar with the bug tracker's features. For instance, some allow you to close tickets by placing a ticket number in your commit messages.

Testing
-------

Unit tests are widely considered a best practice by most developer communities. All developers are encouraged to write unit tests for the code they are responsible for. While not all projects will warrant unit tests, some tests are better than no tests at all. Most languages have some sort of unit test framework that is widely used by the industry. Always use these frameworks. Examples include PHPUnit, FlexUnit, JUnit, etc. Unit tests are helpful for:

- Refactoring: This becomes much easier if you have automated tests in place. The tests will ensure that your code still does what its supposed to do even though you may be changing some internal routines. 
- Integration: Tests can ensure that your code hasn’t broken another developer’s code. This is more relevant if you have various components or modules that rely on each other and are developed by separate people.
- Documentation: Unit tests serve as a great way of documenting the usage of objects and classes. They should generally cover all significant functions of an object or system and can describe it to new developers.
- Design: Unit tests can sometimes take place of formal design. The unit tests then act as a design element. In this case tests are written before any system code is written, unlike most cases when unit tests are often written along side or after system code.

Documentation
-------------

Regardless of the size of the project or how many people are working on it, documentation is critical to the lifespan of any project. Most developers know what its like to inherit a project that has no documentation at all. If you haven’t experienced it yet, you are quite lucky! Developers are expected to keep all projects well documented. There are generally two forms of documentation that should be included in each project:

- Code: Code documentation is not only important for future developers but also for yourself. You’ll appreciate it when you come back to some code after a month of not looking at it and having a few lines of documentation that explain how you achieved something. Code documentation is also helpful for anyone who may inherit the project in the future. All code documentation should follow best practices for the given programming language. This usually means formatting it in such a way that documentation generators can parse your comments.

- Guides: Guides are general documents that explain the project as a whole. This can be a simple README file at the root of a project repository that explains the various parts of the project, frameworks, dependencies, etc. If a README file is not sufficient for the project, create a project wiki on Redmine. If a wiki isn’t appropriate, develop an HTML ‘book’ that can be shared or deployed for others to see.

Environments
------------

Setting up development environments is a crucial part to any project. Depending on the type of project, environments can include development, staging, and production. An environment is physical hardware which the project can successfully run on. The development environment is considered the developers local machine. The staging environment can exist in many different places but will often be a server under the control of the developers or IT staff involved on the project. The production environment is similar to the staging environment except that persistent data is never modified.

Setting up a local development environment is not as hard as it seems. Products like WAMP and XAMPP make setting up a web server and MySQL quite easy. If your project requires more than this, consider using VMWare or Virtual Box to setup virtual machines.

Deployment
----------

Deployment to most environments should be handled by a project lead and, whenever possible, should be automated. If deployment can’t be automated, then it should at least be well documented. Automating deployment will cut down on human error during the deployment process. This is something we’ve all struggled with in the past when FTP was all we had. Automation can be handled in a number of ways using tools such as Ant, Phing, Maven, Gradle, Capistrano, Fabric...the list goes on. It will be up to the project lead to define the deployment process and all developers should be familiar with it in case a project lead is not available to deploy a project.

Quality Assurance
-----------------

Quality assurance (also known as QA) is a process that will be followed to ensure projects fulfill their requirements. There are generally two types of QA: Functional and Creative. Functional QA is, arguably, the most important. A project must first do what it is intended to do before any focus should be put on visual preciseness. Creative QA is generally finer details in how the project looks and feels.

QA will only begin after a test plan has been developed. The test plan is developed by various people who are involved with the design of the project. This can include the client, interaction designers, art directors, project managers and tech leads. Regardless of who is appointed to the task of creating the test plan, no testing will be done until it is completed. This is because the test plan is the official agreement that describes when a project suitable for delivery. 

Once the test plan is completed a test team is assigned to execute it. This generally means checking the functional and creative requirements and logging bugs in the bug tracking system. As a developer it is your job to respond to tickets that are assigned to you. When fixing bugs of any kind, create a new branch in the code repository with the name of the ticket and do all your work in that branch instead of the trunk. Merge your fix into the trunk when you are done. 