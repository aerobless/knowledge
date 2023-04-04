---
description: A better way to work together and get work done
---

# 👨💻 Scrum

Scrum is an agile project management framework, originally intended for software development but now used in various other industries as well. Being agile it focuses on an iterative approach to project management where in regular intervals (sprints) an increment of a product is produced. The length of a sprint can be defined between 1-4 weeks.

## Roles

A scrum team consists of three key roles:

### Product Owner

The product owner is accountable for maximizing the value of the product. They are responsible for ordering the backlog and negotiating with stakeholders.

### Scrum Master

The scrum master is accountable for establishing Scrum. They help the team understand Scrum and provide inputs to the team to continue to improve. The scrum master is considered a servant leader. They do not need to solve problems themselves but they should help the team recognise problems and then find a solution together with the team.

A good Scrum Master works on making themselves unnecessary. A team where this has succeeded could continue working & improving without actually having a Scrum Master present.

### Developers

Developers work on the product during the sprint. Developers don't necessarily need to be software developers.

## Scrum Events

During a sprint the following events occur:

<figure><img src="../.gitbook/assets/Screenshot 2023-03-31 at 13.59.39.png" alt=""><figcaption><p>Source: <a href="https://www.scrum.org/learning-series/what-is-scrum/what-is-scrum">https://www.scrum.org/learning-series/what-is-scrum</a></p></figcaption></figure>

### Planning

In the sprint planning the backlog for the next sprint is created by taking item from the product backlog. It is also a good idea to decide on a sprint goal together with the PO and the developers. Ideally the sprint goal has a product focus and is something that brings value to the stakeholders. E.g. "New user registration works" or "Product order flow until checkout page can be demoed".

When the sprint backlog is filled and the goal is defined the team commits to the sprint scope. The scope of the sprint is then fixed and should not be changed.

### Daily Scrum

During the Daily Scrum or Standup the team discussed the plan for the current day and whether they need help or input from each other. It can also be a good time to have a look at a build server and quickly mention project/product news that might be interesting to the team. The Daily Scrum should be timeboxed at 15min. It is not meant as a status meeting where everyone says what they've done.

### Review

During the sprint review the increment creating during the sprint is presented to the product owner and other potential stakeholders. They may ask questions of the team and discuss things that they would like to have changed. Any desired changes are put into new stories that are then prioritised by the product owner.

### Sprint Retrospective

At the end of the sprint a retrospective (retro) is held with all the members of the scrum team. The retro is moderated by a member of the team, this can be the SM, but it can also be the PO or one of the developers.

The goal of the retrospective is to find ways to improve collaboration, detect pain points, and in general find ways to work together better.

Depending on the team it can be helpful to have a warm up exercise first to get everyone to open up and in the mood of participating.

It is also important to find action items as a result of discovered problems/pains. If no action items are found for a problem it is likely that it will just come up again in the next retro and this makes the whole event rather pointless because only talking about a thing doesn't change anything.

* [Retromat.org: Generate retro exercise ideas](https://retromat.org/)
* ChatGPT: Ask ChatGPT to generate a retro exercise

## Artefacts

### Product backlog

### Spring backlog

### Increment

### Definition of Done

In a Scrum team the developers are responsible for creating done increments. In order to find out if something is done we need a definition, namely the DoD.

#### Establishing a Definition of Done

* Start with a short list of measurable checks, that ideally can be automated.
* The list should include all necessary work that is required to ship the product increment into production.
* The DoD needs to be doable by the team. There is little value to adding checks to the DoD that cannot be satisfied by the team. It is therefor better to start with a smaller DoD and expand it rather then make a massive list of checks upfront.

#### Examples of what could be on a DoD

* Increment passes SonarCube checks with no Critical errors
* Cover Coverage is above a certain threshold
* Increment meets design / architecture standards
* Acceptance criteria pass
* Security checks pass
* Increment meets UX standards
* ...

#### Resources

* [Nkdagility.com: Getting started with DoD](https://nkdagility.com/blog/getting-started-definition-done-dod/)

## Resources

* [Scrum.org: What is Scrum?](https://www.scrum.org/learning-series/what-is-scrum)
* [Scrum.org: Evidence-based Management (EBM)](https://www.scrum.org/resources/evidence-based-management)
* [Agile Manifesto](https://agilemanifesto.org/)
