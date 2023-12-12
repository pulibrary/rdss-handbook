# GitHub Issues

## Types of Issues

Within RDSS, GitHub issues are essential for driving much of the labor within any given team sprint. There currently exist several types of GitHub issues for any given Repository:

- Feature Implementation/Improvement
- Bug Report
- Spike
- Documentation
- Generic Task
- *User Story (Please see the section below)*
- *Epic (Please see the section below)*

For any given GitHub issue to become actionable, there must exist three
properties in which it has explicit acceptance criteria, an implicit or explicit
definition of done (often times this is comprised of the acceptance criteria),
and Zenhub point estimation. Once actionable, an issue may be assigned to an
existing sprint. Should this be the current sprint, then the issue should also
be moved from either the `New Issues` or `Product Backlog` into the `Sprint
Backlog`, where it shall then be assigned to a RDSS team member.

Please note that there exist three types of issues which cannot become
actionable, or which cannot be restricted to a single sprint:

### User Story

Often times the `User Story` issues shall be created by [Product Owners](product_owners.md) rather than developers within the RDSS team, and as such, cannot be closed by source code contributions or technical tasks. As such, it often requires discussion with the Product Owner(s) for the related project to determine whether or not
the `User Story` may be considered closed.

### Epic

`Epic` issues are, like `User Story` issues, created and maintained primarily by
Product Owners. These are typically placed within a separate, dedicated `Epics`
Zenhub column. These [contain one or many derived (or child) issues](https://help.zenhub.com/support/solutions/articles/43000010341-an-intro-to-zenhub-epics) which are actionable, but are not actionable themselves. They often also are assumed to
consume more than one sprint to complete.

## Story Point Estimation

(Please see the [Zenhub article](https://help.zenhub.com/support/solutions/articles/43000010347-estimating-work-using-story-points) for a more detailed discussion of the usage of story points and their relationship with the Zenhub platform).

In order to estimate and ensure that GitHub issues have acceptance criteria and,
where necessary, the definition of done, there is scheduled a bi-weekly `Ticket
Refinement` meeting. During this meeting, participants will, after ensuring that
each issue is actionable, also provide a vote in order to determine the `story
points` assigned to the issue. This `story point` value is used to approximate
the amount of labor and time required to complete the issue. While there exists
no strictly defined time periods associated with each value, the following might
be useful as guidelines:

- 1 point: Correcting typographical or grammatical errors within documentation
- 3 points
- 5 points
- 8 points
- 13 points
- 21 points: Issue requires more than one week within a given sprint to resolve
- 40 points: Issue requires more than one entire sprint to resolve

## Sprint Wrap-up and Review

Scheduled for the last day of any given sprint is the [Wrap-Up and Review
Meeting](meetings.md#work-cycle-wrap-up), which is a time reserved for a team meeting in which the issues resolved, remaining in progress, and prioritized for the sprint but still in the backlog are each reviewed and discussed.


