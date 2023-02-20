The in-toto Project succeeds because of an open, inclusive, and respectful community. Ideas and contributions are accepted based on their technical merit and alignment with project objectives, scope, and design principles. This document lists a non-exclusive set of guidelines to help ensure fairness and transparency in managing the in-toto Project.

## Code of Conduct

See [CODE-OF-CONDUCT.md](/CODE-OF-CONDUCT.md).

## Project Roles

### Users

These are individuals who 1) want to learn more about the in-toto Project; or 2) are existing users of in-toto and its tools who wish to follow the Project's progress. They may have questions, comments, or suggestions that can be communicated via Slack, GitHub, or during community calls and events.

### Contributors

These are individuals who wish to contribute code or ideas to in-toto projects. Contributors submit code and ideas through GitHub or through participation in in-toto's community calls.

### Maintainers

These are individuals who can merge submitted PRs into the primary codebase (note: the Project requires PRs be approved by at least one (1) maintainer). Maintainers also adhere to the following:

* They are an active in-toto contributor. This includes, but is not limited to, regular attendance of in-toto community meetings and subprojects relevant to the components they maintain.
* They respond to PR review requests in a timely manner. Generally, a response is expected within 24 hours of the PR being submitted.
* They ensure that code changes they approve:
  * Meet the [coding conventions](/CONTRIBUTING.md) required by the Project. This includes ensuring the code is sufficiently well tested, follows the appropriate standards, and, of course - does not break the build.  
  * Is consistent with the goals and direction of the Project. This requires not just code and architectural correctness, but also ensuring that it does not introduce "scope creep," and does not unduly affect existing users.
* Once a PR has the requisite approvals, the last approving maintainer is responsible for merging the change (however, the PR's author must ensure the change is merge-ready).

Maintainers are documented in each repository's [CODEOWNERS](https://help.github.com/articles/about-codeowners/) file. To become a maintainer, one must:

* Work in a helpful and collaborative way with the community
* Have a track record of providing constructive feedback on others' PRs
* Have submitted at least 20 PRs themselves

The process for nominating and approving Maintainers is:

* Open a PR against the CODEOWNERS file that covers the parts of the project you wish to nominate someone (or yourself) for
* A consensus of existing Maintainers must approve your PR

### The in-toto Steering Committee (ITSC)

The in-toto Project is governed by the [ITSC](https://github.com/in-toto/community/blob/main/ITSC.md) that is exclusively responsible for in-toto's [specification](https://github.com/in-toto/docs), [enhancements](https://github.com/in-toto/in-toto/ite), the [attestation framework](https://github.com/in-toto/attestation), and the Project's strategic goals and direction. ITSC members have final authority over:

* Technical direction of the Project and subprojects
* Project governance and process (this document)
* Contribution policy
* Conflict resolution

The ITSC adheres to the following:

* Be comprised of at least five (5) members with representation from both Academia and Industry.
* No more than 2 ITSC members may be affiliated with the same organization.
* At least 40% of the ITSC must be represented by organizations that currently have an in-toto implementation deployed in production OR that are actively working to integrate in-toto into other software supply chain efforts or standards.
* Each ITSC member's term is 24 months.
* There is no limit to the number of terms an ITSC member can serve.
* ITSC members may remove themselves voluntarily at any time.

For more information about the ITSC, please refer to the ITSC Charter

## Decision Making

Maintainer and ITSC decisions are made by a [lazy consensus](http://rave.apache.org/docs/governance/lazyConsensus.html) approach. When formal voting is required, members may abstain. Negative votes must be accompanied by an explanation or alternative proposal.

## Change Review Process

**All changes must be submitted as a GitHub Pull Request (PR)**

The submitter of a PR is responsible for responding to feedback from reviewers and maintainers. While the PR remains open, they are also responsible for ensuring the change is always in a state where it can be merged. Guidelines for submitting a PR for approval can be found [here](/CONTRIBUTING.md).

**All minor changes must be approved by at least one other Maintainer**

Documentation changes, bugfixes, or other minor changes that do not significantly impact most users must be approved by at least one (1) maintainer.

**All major changes must be approved by at least two (2) other Maintainers**

New or changed functionality requires two (2) maintainer approvals.

**All governance changes must be approved by a majority of the ITSC**

Changes to the processes defined here and elsewhere that detail in-toto's governance structure must be approved by a majority of the seated ITSC in a public vote.

## Subprojects

The in-toto Project has various Subprojects, which focus on different aspects of the ecosystem (e.g., client language implementations, extensions to the specification, attestation types). Subprojects provide an avenue for face-to-face discussion of important design changes with key stakeholders. Each Subproject may be run by a maintainer group (e.g., Attestation Maintainers or ITE Editors) who are responsible for the logistics of running the meeting, and for ensuring the group reaches consensus on any issues raised. Active Subprojects  are [listed here](/README.md#subprojects), further information can be found on the subproject's site.

### Responsibilities of the Subproject Leads

* Organize regular meetings as necessary, ideally at least for 30 minutes every two weeks.
* Create and moderate a Slack channel on the CNCF workspace for the Subproject. The channel name must use the following format: `in-toto-<subproject name>`.
* Announce meeting agenda and minutes after each meeting on the in-toto mailing list.
* Keep up-to-date meeting notes, linked from the Subproject page in the community repository.
* Optionally record Subproject meetings and make said recordings publicly available.
* Report activity in the monthly community meeting.
* Use the above forums as the primary means of working, communicating, and collaborating, as opposed to private e-mails and meetings.

## License

All software is licensed under the [Apache License version 2.0](https://www.apache.org/licenses/LICENSE-2.0), and all documentation is licensed under the [Creative Commons License version 4.0](https://creativecommons.org/licenses/by/4.0/legalcode).
