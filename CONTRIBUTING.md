# Contributing to in-toto

There are several areas or means to contribute to the development of in-toto.
They are:
* making code changes: these can be for feature additions or bug fixes to
  in-toto implementations
* submitting changes to specifications: these can be direct changes if they are
  trivial or as new in-toto Enhancements (ITEs)
* creating new integrations: in these cases, other projects are updated to
  generate or use in-toto metadata as appropriate, and these integrations are
  noted in [in-toto/friends](https://github.com/in-toto/friends)
* submitting issues, feature requests and more: these are typically
  implementation or sub-project specific, and can be submitted to the
  corresponding GitHub repositories

Any developer or user submitting these types of changes is considered an in-toto
contributor. Over time, as described in [in-toto's Governance](GOVERNANCE.md),
contributors may be promoted to maintainers of relevant implementations or
sub-projects.

## Contributor Workflow

A contributor can submit GitHub pull requests to the project's repositories.
They must follow the project's [code of
conduct](CODE-OF-CONDUCT.md), the [Developer Certificate of
Origin (DCO)](https://developercertificate.org/) and the [code style
guidelines](https://github.com/secure-systems-lab/code-style-guidelines), and
they must unit test any new software feature or change.  Submitted pull
requests undergo review and automated testing, including, but not limited to:

* Unit and build testing
* Static code analysis via linters
* Checks for *Signed-off-by* commits
* Review by one or more maintainers

The specifics of development practices for a sub-project or implementation are
detailed in their repositories. For implementations, this includes information
such as the name of the development branch and any additional checks pertaining
to that project. For ITEs, the process of submitting a new proposal is described
in ITE-1.