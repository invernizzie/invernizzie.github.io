---
layout: post
title:  "Software development process"
date:   2015-05-17 17:10:50 -0300
categories: software management
---

# Software development process

A development process is a set of practices and techniques with the goal of ensuring certain properties of a software product and the project in which it's developed. Importantly, a develpoment process is not defined by tools but rather by activities.

The creation of a software development process is the adoption of practices. Focus should be put on selecting practices that contribute to desirable properties of software.

## Desirable traits of software products
Preferable properties of a software product are correctness, stability, maintainability, usability, security, extensibility, modularity and scalability. The first three are achieved through an appropriate development process. The other five are mostly achieved through design, so we won't cover them today.

Software development is the craft of meeting user requirements. That's the simplest way I can describe it. You might get everything else right, but if you don't meet your user's requirements, the final product is useless. This is known as *correctness*. Practices that ensure correctness must be the core of software development. Translating user requirements into the right engineering tasks will ensure correctness. This is done by analysing use cases or describing **user stories**, two not too different practices. Involving end users and the product owner in the writing is essential. I've seen many projects create software that implements use cases or user stories precisely, yet it wasn't *correct*. Unless the user agrees with the stories, it never will be.

The next step to correctness is testing. As any human beings, programmers make mistakes. Production software is complex, there are many variables to keep track of at any time. Even though complexity must be managed by a subset of software development practices, it can't be avoided. Hence, testing must be in place. Its goal is to verify that users' requirements are met. Ultimately, verification will be done by end users. To prevent too much progress from going unverified, which might cause a lot of rework, user testing must be done regularly. This points us to **incremental development**, whereby frequent intermediate releases of the software are made. It enables the users to verify what was built, and make adjustments as needed.

As users are never really thorough, testing should also be done by the development team. Here, **automated tests** pose a clear advantage. They're cheap to repeat, which is crucial to catch regression issues. Manual tests, on the other hand, are not. And even worse, they're harder to execute than it might seem. Bias makes testing by the developer of the functionality useless. Similarly, manual tests should be executed by different testers. Getting manual testing right is hard. And synchronizing manual testing with an incremental release cycle is by all means a nightmare. Let alone continuous delivery! Automated tests can take a while to get used to, but once a developer hits the sweet spot, it will be too hard to pass on them.

As much as testing can help, bugs will eventually make it into a release. To ensure *stability*, the development team must be able to fix issues in production. To do so without disrupting development requires a flexible **versioning scheme**. Modern source code management tools make it easy to achieve. Having a "production" and "development" branches living side by side should be sufficient to implement a maintenance process. Issues fixed in the production branch must reach the development branch. And development must be able to continue independently in the meantime.

*Maintainability* is much more related to code than the former properties. It's a known fact that code is read more than written. Being able to understand and modify software is key to getting a decent ROI from software. If code is hard to maintain, the cost of supporting software evolution to catch up with ever-changing user needs grows unsustainable. It literally becomes economical to rewrite complete systems if they're not made maintainable. Measures to obtain maintainability are well known by engineers. They have been solidified (pun intended) in five principles of objects in OOP; however, they are analogous to every paradigm. Single responsibility, closure (aka "open-closed"), contract based substitution, cohesive interfaces and dependency on abstractions.

The best way that I've found for a development team to enforce maintainability measures is to set up a **code review** practice. Having at least one developer review a peer's code before it gets merged into the codebase is a must. It will also help knowledge spread through a team and mature conventions, so adoption seems like a no brainer.

These practices, of course, are just the tip of the iceberg. We haven't gone into detail or related practices; why not some continuous integration to go with those tests and enforce the versioning scheme? We're yet to discuss practices that will make projects' ends meet; because, yes, all of this needs to get done in time, on budget and within a certain scope. But those topics we'll cover in future posts.

