# RDSS Meetings

## Sprint Planning Meetings

At the end of each work sprint, the RDSS team meets to plan for an upcoming sprint. A running agenda and notes document is internally maintained by the team. Going into the meeting, there is an expectation that the team is aware of the primary focus of the work sprint to be planned, in terms of services/applications.

At each meeting, the team works from the [RDSS Sprint ZenHub board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board) together. One person, the driver, updates the board during the meeting and shares their screen.

1. As issues are reviewed, the team adds information to the descriptions as needed so they are actionable, and then agrees on a GitHub estimate for each one.

2. Issues that the team will work on are moved into the "Sprint Backlog" column.  Ideally, all issues targeted for the sprint should have an estimate already.  However if they do not, they can be estimated during the planning meeting if appropriate, or targeted for estimation during the next Ticket Refinement meeting.

3. Issues targeted for the upcoming sprint are placed into the "Sprint Backlog" under the upcoming sprint.

### Other norms

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

Every two weeks, on the last day of the sprint being closed out (referred to from here on as the closeout sprint), a sprint wrap-up meeting will be held.  This meeting is attended by the RDSS team.  Each meeting will have the following format:

1. Populate the agenda with the currently-worked epic(s) and any highlighted completed issues from the closeout sprint to review.  Review these issues as a group.  

2. Review the [Sprint Report](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/reports/burndown) (ensure the correct sprint is selected from the dropdown on the page) for story points and issues/pull requests estimated vs. completed.

3. Review in-progress issues and review/QA issues in the closeout sprint.  Move them to the new sprint as needed.

4. Review remaining issues in the closeout sprint in the backlog.

5. Determine which issues should move to the next sprint and which issues should be rescheduled or unscheduled, and move tickets accordingly. 

6. Discuss in brief the following:

    1. Any unplanned work (using the [unplanned-work](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=unplanned-work) label).

    2. Any concerns for anticipated risks to the upcoming sprint (known major upgrades or planned outages, departmental deadlines outside of IT, etc).

7. Review [UX](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=UX) labeled issues and schedule for future sprints (not the upcoming sprint).

8. Review [accessibility](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=accessibility) labeled and schedule for future sprints (not the upcoming sprint).

9. Review [post-incident](https://github.com/pulibrary/rdss-catchall/issues/108#workspaces/rdss-61a4f1a12a399b001730f65a/board?labels=post-incident) labeled and schedule for future sprints (not the upcoming sprint).

10. Review security vulnerabilities ([example](https://github.com/pulibrary/pdc_describe/security/dependabot)) on active projects and schedule for future sprints (not the upcoming sprint).

11. Review the RDSS [roadmap](roadmap.md) and talk about the products being developed and upcoming features to focus on.

12. Select a [runner](runner.md) for the upcoming sprint.

13. Select a new emoji for the upcoming sprint.

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
|  1   | [Feature Refinement](product_owners.md); Sprint Planning (sprint begins) | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in | Daily Check-in                                           |
|  2   | [Feature Refinement](product_owners.md); Ticket Refinement        | Daily Check-in | Daily Check-in and Learnings Chat | Daily Check-in | Daily Check-in; Sprint Wrap-up (sprint ends); [Sprint Retrospective](retros.md) |
