<img src="http://www.zerocracy.com/logo.svg" width="64px" height="64px"/>

[![Availability at SixNines](http://www.sixnines.io/b/2b3a)](http://www.sixnines.io/h/2b3a)
[![Build Status](https://travis-ci.org/zerocracy/datum.svg?branch=master)](https://travis-ci.org/zerocracy/datum)

Zerocracy is management without managers.

Information about current project status is kept in XML and text
files. This repository contains full list of XSD Schemas for them
and rules of usage.

Any problems you have with [Zerocracy](http://www.zerocracy.com)
please report [here](https://github.com/zerocracy/datum/issues).
We promise to do our best to resolve them as soon as possible.

## How it works

Product Owner (`PO`) is a representative of a project sponsor.
As a PO you can:

  - [x] [Invite](http://www.0crat.com/invite) `@0crat` to your Slack
  - [x] [Create](https://get.slack.help/hc/en-us/articles/201402297-Create-a-channel) a new Slack channel for a project
  - [ ] [Invite](#invite-only) a friend
  - [x] Start talking to the bot: `@0crat hello`
  - [x] Bootstrap a project: `@0crat bootstrap`
  - [ ] Fund the project using a credit card: `@0crat fund`
  - [x] Link the project with GitHub repositor(ies): `@0crat links`
  - [x] Register `ARC` and `DEV` roles: `@0crat roles`
  - [x] Add tickets to the scope in GitHub: `@0crat in`
  - [x] Remote tickets from the scope: `@0crat out`
  - [x] See the WBS: `@0crat wbs`
  - [ ] See the budget: `@0crat budget`
  - [ ] See the schedule: `@0crat schedule`

An Architect (`ARC`) is the key technical decision maker
in the project. As an ARC or a PO you can:

  - [x] Assign a performer to a job: `@0crat assign`
  - [x] Resign a performer: `@0crat resign`
  - [ ] Increase/decrease job budget: `@0crat boost`
  - [ ] Attach a job to a milestone: `@0crat milestone`

As a Developer (`DEV`) you can:

  - [x] Join one of Slack teams
  - [x] Start talking to the bot in a private channel: `@0crat hello`
  - [x] Modify your hourly rate: `@0crat rate`
  - [x] Modify your payment details: `@0crat wallet`
  - [x] Modify your set of skills: `@0crat skills`
  - [ ] Quit a project: `@0crat quit`
  - [ ] Set/reset "away" mode: `@0crat away`
  - [x] Reject a job: `@0crat resign`
  - [ ] Announce an impediment: `@0crat hold`
  - [ ] Check the status of a job: `@0crat status`
  - [ ] Request your profile metrics: `@0crat metrics`

As a Quality Assurance (`QA`) you can:

  - [ ] Confirm the quality of a task: `@0crat quality`

The bot can:

  - [x] Assign a job to a performer
  - [ ] Announce job budget
  - [ ] Announce job deadline
  - [ ] Resign a performer
  - [ ] Request quality control
  - [ ] Update performer's metrics
  - [ ] Pay for bugs reported
  - [ ] Pay performer for task completion

## Invite Only

You can use the system only if someone invites you. That person has to
know your GitHub login and say this to `@0crat` bot (provided your name
is `yegor256`):

```
@0crat invite yegor256
```

That's enough. From that moment you have a "mentor."
