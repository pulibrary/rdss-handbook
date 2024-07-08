# RDSS Meetings

## Sprint Planning Meetings

At the end of each work sprint, the RDSS team meets to plan for an upcoming sprint. A running agenda and notes document is internally maintained by the team. Going into the meeting, there is an expectation that the team is aware of the primary focus of the work sprint to be planned, in terms of services/applications.

At each meeting, the team works from the [RDSS Sprint ZenHub board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board) together. One person, the driver, updates the board during the meeting and shares their screen.

1. The driver creates a GitHub milestone for the work sprint if one has not already been created (see [Sprints](sprints.md) for more information).

1. The driver creates a "Candidates" column in the board and populate it with issues to be considered.

1. As issues are reviewed, the team adds information to the descriptions as needed so they are actionable, and then agrees on a GitHub estimate for each one.

1. Issues with an estimate that the team will work on are moved into the "Sprint Backlog" column.

1. Review is complete when all candidate issues have been reviewed by the team, whether or not they have been scheduled for this sprint.

1. Issues targeted for the upcoming sprint are placed into the "Sprint Backlog" under the sprint's GitHub milestone.

1. At the end of the meeting, the "Candidates" column is deleted from the board.

### Other norms

A sprint planning meeting similar to the above-described format takes place in the same timeslot during the second week of the sprint, to review tickets that are on the board that may warrant reorganization and address any issues that have been generated as a result of unplanned work (that is, work that came up or was escalated in priority due to needs from stakeholders, users, and/or Leadership within the last week).

## Daily Check-ins

The RDSS Team has daily check-in meetings on weekdays, excluding Sprint Planning days.

The goal of the meeting is to briefly check in as a group, review what everyone is currently working on, and discuss items put on the agenda based on work from the past day. A running agenda and notes document is internally kept by the team.

The team views the [RDSS Sprint ZenHub board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board) during the meeting, which runs as follows:

1. A Round Robin, where each team member shares their briefly shares their updates in turn, without going into too much detail but providing enough context so all team members know which tasks are being discussed.

1. Review the written agenda populated with items where input from the team is needed, keeping to the time set for the check-in (15 minutes total, including Round Robin).

### Other norms

The "Check-in and Coffee Chat" is a check-in immediately followed by a 30-minute informal learn-out, where team members briefly share things they learned that week in their work with the team. 

## Sprint Wrap-Up Meetings

Every two weeks, on the last day of the sprint being closed out (referred to from here on as the closeout sprint), a sprint wrap-up meeting will be held.  This meeting will be attended by the RDSS team and sprint participants from other teams such as IT Operations, Assessment and User Experience, and other software development teams.  Each meeting will have the following format:

1. Populate the agenda with the currently-worked epic(s) and any highlighted completed issues from the closeout sprint to review.  Review these issues as a group.  

1. Review the [Sprint Report](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/reports/burndown) (ensure the correct sprint is selected from the dropdown on the page) for story points and issues/pull requests estimated vs. completed.

1. Review in-progress issues and review/QA issues in the closeout sprint.  Move them to the new sprint as needed.

1. Review remaining issues in the closeout sprint in the backlog.

1. Determine which issues should move to the next sprint and which issues should be rescheduled or unscheduled, and move tickets accordingly. 

1. Discuss in brief the following:

    1. Any unplanned work (using the [unplanned-work](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=unplanned-work) label).

    1. Any concerns for anticipated risks to the upcoming sprint (known major upgrades or planned outages, departmental deadlines outside of IT, etc).

1. Review [UX](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=UX) labeled issues and schedule for future sprints (not the upcoming sprint).

1. Review [accessibility](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=accessibility) labeled and schedule for future sprints (not the upcoming sprint).

1. Review [post-incident](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=post-incident) labeled and schedule for future sprints (not the upcoming sprint).

1. Review security vulnerabilities ([example](https://github.com/pulibrary/pdc_describe/security/dependabot)) on active projects and schedule for future sprints (not the upcoming sprint).

1. Review the RDSS [roadmap](roadmap.md) and talk about the products being developed and upcoming features to focus on.

1. Select a [runner](runner.md) for the upcoming sprint.

1. Select a new emoji for the upcoming sprint.

## RDSS Departmental Monthly Meetings

Once a month, RDSS holds a meeting that includes a [demo](software_demos.md) of software developed in the closeout sprint and an open agenda portion where anyone in attendance should add items to discuss with the group during the meeting.  The meeting is be made up of all members of the RDSS team and colleagues from constituent groups such as IT Leadership, IT Operations, the Princeton Research Data Service, Research Data and Open Scholarship, Assessment and User Experience, the Princeton Plasma Physics Library, Discovery and Access Services, Digital Library Services, and any others.  The meeting is open for anyone in the Library to attend, however it is the responsibility of RDSS to specifically invite people from outside of the team to attend when there are topics specific to their goals/responsibilities.  Each meeting has the following format: 

1. Overview of agenda by RDSS leadership

1. Software demo reflecting work accomplished in closeout sprint

1. Questions and discussion of demo

1. Review and discussion of all other public agenda items

1. Review of the overall [roadmap](roadmap.md) for RDSS

## Schedule

Sprints last for 2 weeks, starting on a Wednesday and ending on a Tuesday. The RDSS sprint meetings schedule looks like this:

| Week | Wednesday                           | Thursday       | Friday                            | Monday         | Tuesday                                                  |
| :--: | :---------------------------------- | :------------- | :-------------------------------- | :------------- | :------------------------------------------------------- |
|  1   | Sprint Planning (sprint begins) | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in | Daily Check-in                                           |
|  2   | Ticket Refinement        | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in | Daily Check-in<br />Sprint Wrap-up and Retrospective |
