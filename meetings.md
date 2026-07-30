# RDSS Meetings

## Sprint Planning Meetings

At the end of each work sprint, the RDSS team meets to plan for an upcoming sprint. A running agenda and notes document is internally maintained by the team. Going into the meeting, there is an expectation that the team is aware of the primary focus of the work sprint to be planned, in terms of services/applications.

At each meeting, the team works from the [RDSS Sprint ZenHub board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board) together. One person, the driver, updates the board during the meeting and shares their screen.

1. As issues are reviewed, the team adds information to the descriptions as needed so they are actionable, and then agrees on a GitHub estimate for each one.

1. Issues that the team will work on are moved into the "Sprint Backlog" column.  Ideally, all issues targeted for the sprint should have an estimate already.  However if they do not, they can be estimated during the planning meeting if appropriate, or targeted for estimation during the next Ticket Refinement meeting.

## Ticket Refinement

A "Ticket Refinement" meeting is held every other week during the sprint planning timeslot.  Tickets without estimations are reviewed and pointed using a "pointing poker" estimation process.   

## Daily Check-ins

The RDSS Team has daily check-in meetings on weekdays, excluding Sprint Planning days.

The goal of the meeting is to briefly check in as a group, review what everyone is currently working on, and discuss items put on the agenda based on work from the past day. A running agenda and notes document is internally kept by the team.

The team views the [RDSS Sprint ZenHub board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board) during the meeting, which runs as follows:

1. A Round Robin, where each team member shares their briefly shares their updates in turn, providing enough context so all team members know which tasks are being discussed.  Any topics that will take more time than an update should be added to the agenda for discussion.

1. Review the written agenda populated with items where input from the team is needed, keeping to the time set for the check-in (15 minutes total, including Round Robin).

### Other norms

The "Check-in and Coffee Chat" is a check-in immediately followed by a 30-minute informal share-out, where team members briefly share things they learned that week. 

## Sprint Wrap-Up Meetings

Every two weeks, on the last day of the sprint being closed out (referred to from here on as the closeout sprint), a sprint wrap-up meeting will be held.  This meeting is attended by the RDSS team as well as cross-team colleagues and the product owner.  Each meeting will have the following format:

1. Populate the agenda with the currently-worked epic(s) and any highlighted completed issues from the closeout sprint to review.  Review these issues as a group.  

1. The product owner demos the functionality of the currently-worked epic(s) for the teams and, along with the Design team, provides feedback on whether the epic is complete and ready to ship to production.  If it is not determined to be ready to ship to production based on feedback, additional tickets are created for whatever work is required to finish the feature if they do not already exist.

1. Review in-progress issues and review/QA issues in the closeout sprint.  Move them to the new sprint as needed.

1. Review remaining issues in the closeout sprint in the backlog.

1. Determine which issues should move to the next sprint and which issues should be rescheduled or unscheduled, and move tickets accordingly. 

1. Discuss in brief the following:

    1. Any unplanned work (using the [unplanned-work](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=unplanned-work) label).

    1. Any concerns for anticipated risks to the upcoming sprint (known major upgrades or planned outages, departmental deadlines outside of IT, etc).

1. Review [UX](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=UX), [accessibility](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=accessibility), and [post-incident](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=post-incident) labeled and schedule for future sprints.

1.  Review the RDSS [roadmap](roadmap.md) and talk about the products being developed and upcoming features to focus on.

1.  Select a [runner](runner.md) for the upcoming sprint.

1.  The runner selects a new emoji for the upcoming sprint.

## Feature Design Plans (FDP) Meetings

The RDSS team meets weekly on Mondays after stand-up to review any [feature design plan (FDP) documents](https://drive.google.com/drive/folders/1a4Qa93_P9-2ollFeWAOeoTNSfuGZh2VH) that are in process.

See more about FDPs [here](feature_design_plans.md).

At the last FDP meeting of each month, the team reviews the [RDSS calendar](https://docs.google.com/spreadsheets/d/1yrPuhA6IE32KvHfbAxa5RDsY-bK3PPzeIXDs8IjIS0I/edit?gid=0#gid=0) for accuracy/any modifications needed.

## Schedule

Sprints last for 2 weeks, starting on a Wednesday and ending on a Tuesday. The RDSS sprint meetings schedule looks like this:

| Week | Wednesday                           | Thursday       | Friday                            | Monday         | Tuesday                                                  |
| :--: | :---------------------------------- | :------------- | :-------------------------------- | :------------- | :------------------------------------------------------- |
|  1   | [Feature Refinement](product_owners.md); Sprint Planning (sprint begins) | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in; FDP Meeting | Daily Check-in                                           |
|  2   | [Feature Refinement](product_owners.md); Ticket Refinement        | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in; FDP Meeting | Daily Check-in; Sprint Wrap-up (sprint ends); [Sprint Retrospective](retros.md) |
