Roadmap
=======

This document spans the Roadmap for the in-toto project for the time window
from April 2019 to April 2020. The main theme of this year's efforts are
focused on cross-implementation interoperability, two ITE proposals, tighter
spec compliance checks and maturing of the existing sub-projects.

## Cross-implementation interoperability

Throughout the years, in-toto has developed libraries in 3 different languages,
as well as different applications that leverage these libraries for platforms
such as Jenkins, Kubernetes and apt. With these changes, the need to ensure
metadata generated from other implementations can be verified by everyone is
paramount.

Although, to the best of our knowledge this is already the case, this year
we'll work on making sure that this can be strongly secured by the use of a
more thorough integration test harness.

## ITE proposals

The in-toto community has toyed with the idea of formalizing two ITE's so far:

1. resource-type identifiers for artifacts. A way to represent artifacts that
   go beyond files, such as Docker containers, SPDX metadata and OCIv2 images.
   Although it is possible to secure artifacts of this nature already, a richer
   language will allow integrators to further introspect the artifacts created,
   consumed and modified.
2. A TUF+in-toto recommendation ITE. We want to allow integrators to refer to a
   document that can simplify the deployment of both technologies together with
   meaningful security guarantees. Batteries included.

## Tighter spec compliance

The in-toto specification drives the behavior of all of our implementations,
yet 100% compliance is not yet achieved by all of them. This year we will focus
efforts on making sure that the existing implementations follow the
specification to the word.

## Maturing of existing sub-projects

The in-toto project has sprouted to host multiple implementations, plugins, cli
tools, helper commands, ansible playbooks, etc. This year we intend to mature
at least the following components:

### Jenkins plugin

The official Jenkins plugin is already usable, yet some features like
stdin/stdout registration are desirable, other environment information is
worth having.

This also calls for a more mature Java implementation, with higher test
coverage and a more user-friendly API.

### Kubernetes components

The kubernetes admission controller will greatly benefit from a resource-type
identifier, and proper handling of container images. Given it's cloud-native
nature, verification will mostly run over containers that are about to be
admitted into an organization's cloud.

This will also call for a smarter interaction between our go implementation and
containerd/runc to intelligently handle container resource-types.

### GPG support

We intend to move the GPG components to securesystemslib and standardize this as
either a TAP or an ITE so our sister project, TUF can benefit from GPG support.

### Apt transport and rebuilders

An in-toto transport method for apt to verify the reproducibility of Debian
packages before their installation using link metadata from custom rebuilders,
is fully tested and ready to be used. Yet, it still awaits further endorsement
from the Debian community.

This calls for promoting the project to the related community and finding
packagers for the transport as well as its dependencies, in-toto and
securesystemslib. Furthermore, we intend to make the in-toto rebuilders more
robust and better document their usage, so that independent organizations can
easily provide evidence of reproducibility.

# Roadmap review schedule

We intend to review the progress done in these efforts on these time windows.

- [End of August](roadmap-reviews/2020/review_1_august_19.md)
- [End of December](roadmap-reviews/2020/review_2_december_19.md)
- [End of June - final review Roadmap 2020](roadmap-reviews/2020/review_3_june_20.md)

These time windows will also be used to update all stakeholders with the status
of the in-toto project.
