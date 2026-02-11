# StreamsHub Governance

This document defines the governance rules for the StreamsHub organization.

## Organization structure

The StreamsHub organization contains multiple sub-projects. 
A sub-project is a separate repository within the StreamsHub GitHub organization. 
Each of the sub-projects may have multiple sub-modules or components.

Examples of sub-projects include `console` and `flink-sql-runner`.
Examples of components include the `console` project which has a `docs` component and an `operator` component.

## Organization Roles

For governance purposes the organization recognizes four roles:

- maintainers
- emeritus maintainers
- component owners
- emeritus component owners

At any one time, a person may be in 0 or 1 of those roles.

### Maintainers

A maintainer is actively responsible for the overall development of the whole StreamsHub organization and all its sub-projects.
The maintainers are identified in the [`MAINTAINERS`](MAINTAINERS) file.

Every maintainer is, in effect, also an owner for all sub-projects and components and does not have to be mentioned in the `COMPONENT-OWNERS` file.

### Component owners

A component owner is responsible for development of a specific sub-project or component within the StreamsHub organization.
The component owners are identified in the [`COMPONENT-OWNERS`](COMPONENT-OWNERS) file in this repository which also includes the component for which they are responsible.

### Emeritus component owners and maintainers

An emeritus component owner, or an emeritus maintainer, is someone who formerly had that role but is no longer actively involved with the organization.
Emeritus component owners and emeritus maintainers are identified in the [`EMERITUS`](EMERITUS) file.

In the rest of this document the term 'maintainer' should be taken to mean 'active maintainer' unless qualified using the term 'emeritus maintainer'.

### Changes in maintainership

New maintainers are proposed by an existing maintainer and are elected by a vote (see later for the rules of this vote).
If the vote succeeds the proposed maintainer will be invited to become a maintainer.
If the proposed maintainer accepts the invitation:

- Their name will be added to the `MAINTAINERS` file.
- They will be added to the collaborators list of the StreamsHub GitHub organization with the "All-repository write" role.
- After 6 months they will be given the "All-repository admin" role in the StreamsHub GitHub organization.

Maintainers can be removed by a vote.
If the vote succeeds:

- Their name will be removed from the `MAINTAINERS` file.
- They will be removed from the collaborators list of the StreamsHub GitHub organization.

Maintainers who wish to become emeritus simply mark the fact by opening a PR against this repository moving their name to the `EMERITUS` file.
The process for reverting from an emeritus maintainer to an active maintainer/component owner is the same as for new maintainers/component owners.

### Changes in component ownership

New component owners can be proposed by any maintainer and are elected by a vote.
If the vote succeeds the proposed component owner will be invited to become a component owner.
If the proposed component owner accepts the invitation:

- Their name will be added to the `COMPONENT-OWNERS` file.
- Owners of sub-projects which have their own GitHub repository will get "Write" rights for the given GitHub repository and will be able to merge approved PRs.
- Owners will not get "Admin" rights on any StreamsHub GitHub repositories.

Component owners can be removed by a vote.
If the vote succeeds:
- Their name will be removed from the `COMPONENT-OWNERS` file.
- They will be removed from the collaborators list of any relevant StreamsHub sub-project repositories.

Component owners who wish to become emeritus simply mark the fact by opening a PR against this repository moving their name to the `EMERITUS` file.
The process for reverting from an emeritus component owner to an active component owner/maintainer is the same as for new component owners/maintainers.

### Maintainership and Component ownership timeout

If a maintainer or component owner has not made any contributions to the organization for a period of 6 months, any other maintainer may propose that they be moved to the corresponding emeritus status.
The voting rules for removal are the same as for removing maintainers or component owners.

Contributions to the organization are defined as any of following activities performed on any of the StreamsHub organization's GitHub repositories:

- Opening issues or PRs
- Commenting on issues or PRs
- Reviewing or approving PRs
- Answering user questions in the StreamsHub Slack channels
- Giving talks about StreamsHub and its sub-projects at conferences or meetups

Before a vote is called the maintainer or component owner in question should be contacted (via the email address defined in the relevant MAINTAINERS or COMPONENT-OWNERS files) to check whether they wish to remain active or whether they have a valid reason (such as a medical issue or extended leave) for their inactivity.

## Sub-project management

The creation or archiving of sub-projects within the StreamsHub organization requires a proposal to be opened against the [proposals repository](https://github.com/streamshub/proposals).
The rules for approving proposals are defined in the ["Votes on proposals"](#votes-on-proposals) section below.

## Voting rules

The StreamsHub project employs voting to ensure no single member can dominate the project.

For formal votes, a specific statement of what is being voted on should be added to the relevant GitHub issue or PR.
Voters should indicate their yes/no vote on that issue or PR, and after a suitable period of time, the votes will be tallied and the outcome noted.

The project uses different kinds of vote for different purposes.

- PR approval votes
- Lazy consensus votes
- Explicit majority votes

Who may vote, where votes are recorded and the duration of the voting also depends on the subject of vote, as explained in the following sections.

### PR approval rules

PRs against most repositories may be merged after receiving at least two positive maintainer votes.
Voting for PRs can be done using a comment in the PR or by approving (or requesting changes to) the PR.
If the PR author is a maintainer, this counts as a vote.

PRs which affect only a single sub-project/component can be approved by at least one positive maintainer vote and one positive vote from an owner of the given sub-project/component.
If the PR author is a maintainer or an owner of given sub-project/component, this counts as a vote.

#### Automatically merging PRs for dependency updates

It is common for repositories to implement automated dependency updates using tools such as Dependabot.
In order to avoid unnecessary manual work for maintainers, PRs created by such tools which only update dependencies and do not change any other code, can be automatically merged if they pass all the configured tests and other CI checks.

### Lazy consensus rules

Lazy consensus votes use +1, 0, -1 votes and their fractions, where:
- +1 means "yes"
- -1 means "no"
- The numbers between +1 and -1 indicate how strongly you feel about the proposal

_(Inspired by [Apache Software Foundation voting](https://www.apache.org/foundation/voting.html#expressing-votes-1-0-1-and-fractions))_

Binding votes are those cast by people in specific roles defined for that vote and count towards the approval of the subject of the vote.
Non-binding votes may be cast by people not in any of those roles and do not count towards approval of the subject of the vote.

The vote succeeds when there are at least three +1 binding votes and no -1 binding votes.
The vote should be opened for at least 3 days to give everyone enough time to vote.

### Explicit majority rules

An explicit majority vote is simply a +1 or -1.
The vote succeeds when at least 50% of potential binding votes are cast and ⅔ of cast binding votes are +1.
The vote should be opened for at least 7 days to give everyone enough time to vote.

Potential binding votes are defined by the number of people in the relevant roles defined for that vote at the time the vote is opened.
Any fraction of a vote is rounded up to the nearest whole number when calculating the number of votes required for approval.

### Voting via Pull Requests

+1 votes can be expressed by approving the proposal PR or in the comments.
Other votes, with reasons, can be expressed in the comments.
For example "-1 (binding) because ...", or for a non-maintainer "-1 (non-binding) because ...".

### Votes

#### Votes on changes to governance

With the exception of maintainers and component owners marking themselves as emeritus, all changes in the governance repository require an **explicit majority** of **maintainers**.

#### Votes on adding or removing maintainers

Votes to add or remove a maintainer require an **explicit majority** of **maintainers**.

#### Votes on adding or removing component owners

Votes to add or remove a component owner require an **explicit majority** of **maintainers**.

#### Votes on proposals

Proposals can be opened against the [proposals repository](https://github.com/streamshub/proposals).
Proposals should cover:

- The creation of new sub-projects
- Any changes to a sub-project which might significantly impact the users of that sub-project or the direction of that sub-project
- The archiving of sub-projects

Approving a proposal requires a **lazy consensus** of **maintainers**.
*However, non-binding votes are encouraged as a signal to maintainers of the acceptability of the proposal to the wider community.*

#### Votes on PRs in other repositories

With the exception of the governance and proposals repositories, votes on PRs in other repositories use the [**PR approval rules**](#pr-approval-rules).

#### Votes on other changes

Unless specified above, all other changes to StreamsHub sub-projects require an **explicit majority** of **maintainers**.
Additionally, any maintainer may request that any change require an **explicit majority** of **maintainers**.
