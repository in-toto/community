Roadmap
=======

_Note: Previous roadmaps can be found with the roadmap reviews for that period.
[Link to Roadmap 2022](/roadmap-reviews/2022/ROADMAP.md)_

This document spans the Roadmap for the in-toto project for the 2023 calendar
year. As before, the theme of this year's efforts are focused on extending
in-toto through new and existing ITEs, and adding support for them in the
implementations we maintain.

## in-toto v1.0

The last tagged release of the in-toto specification was v0.9. We are gearing
up to tag v1.0 of the specification. This process entails addressing some long
standing discussions and issues, and several rounds of reviews to catch any
inconsistencies and errors that may require breaking changes to fix later.
Apart from these processes, there aren't any major blockers to the
specification reaching the 1.0 milestone -- it has been stable for a significant
amount of time and much of in-toto's development happens through in-toto
Enhancements (ITEs). We expect the v1.0 release to happen in the first review
period of this roadmap.

Note that this planned v1.0 release checkpoints in-toto at its pre-attestation
stage. As the attestation framework matures and reaches stability, it is likely
to have its own tagged releases, either as a standalone specification or as part
of the main specification's future releases.

## ITEs

Several important ITEs were introduced in the last few years.
[ITE-2](https://github.com/in-toto/ITE/blob/master/ITE/2) and
[ITE-3](https://github.com/in-toto/ITE/blob/master/ITE/3)
discussed how to use TUF as a root of trust for in-toto metadata.
[ITE-4](https://github.com/in-toto/ITE/blob/master/ITE/4)
introduced the notion of non-file artifacts in in-toto, a semantic that is very
useful in capturing attestations about abstract artifacts and processes such as
GitHub pull requests and reviews that are prevalent in real world software
supply chains. [ITE-5](https://github.com/in-toto/ITE/blob/master/ITE/5)
disassociated the signature wrapper from the in-toto specification and
recommended a switch to DSSE.
[ITE-6](https://github.com/in-toto/ITE/blob/master/ITE/6) perhaps had the most
impact of all the ITEs, introducing the in-toto Attestation framework. This was
paired with [ITE-9](https://github.com/in-toto/ITE/blob/master/ITE/9) that
described a process for the in-toto community to introduce new attestation
types, and established the in-toto attestation maintainers, a group of industry
stakeholders who review and provide feedback about new attestation types.
[ITE-7](https://github.com/in-toto/ITE/blob/master/ITE/7) added support for
creating and verifying signatures using X.509 certificates.

### ITE-6, ITE-9, and Policies for in-toto Attestations

This year, we are working towards having ITE-6 and ITE-9 accepted. ITE-6 is
already used in a number of applications, most notably by the SLSA
specification. We believe it's time to accept ITE-6 and continue to develop the
attestation framework. Similarly, ITE-9 is still a draft but the process
described in it is already being applied to several new attestation type
proposals. The attestation maintainers have reviewed proposals for runtime
traces and the Software Supply Chain Attribute Integrity (SCAI) specification.
We expect both ITEs to be accepted in the first review period of this roadmap.

Besides these existing ITEs, a key aim for this year is to introduce a new ITE
that proposes modifications to in-toto layouts. As it stands, in-toto layouts
cannot be used to verify ITE-6 attestations. With ITE-6 close to being accepted,
the focus is now on closing this gap so that in-toto attestations can be
verified using our verification workflows. Alongside defining new layout
schemas, we hope to revive the work on ITE-8 to introduce a library of in-toto
policies. Early drafts of the new ITE should be available for the community to
peruse in the first review period, and depending on the capabilities it
introduces, ITE-8 will likely be revived right after.

### Hierarchy for Attestation Types and the Predicate Dictionary

In the last year, we have discussed at several times if we want to establish a
hierarchy for in-toto attestation types. As more attestations are introduced for
various contexts, some may be derived or may extend others. As such, one of the
aims for this year is to formally study how to handle these scenarios.

Another closely related discussion was about the creation of a "predicate
dictionary". The idea here was to identify how different attestation types
overlap, and when they can be used interchangeably. For example, a SLSA
Provenance attestation contains every information used by in-toto's verification
workflow from in-toto link metadata. We believe that building this out will go a
long way to improving in-toto's usability and a sense of the minimum set of
attestations necessary to secure software supply chains as per current
standards.

### ITE-7

As noted before, this ITE introduced the use of X.509 certificates in in-toto.
This ITE has been implemented in in-toto-golang and other implementations such
as TestifySec's Witness. After another round of reviews at KubeCon late last
year, this ITE is also nearing acceptance. Depending on when implementations
that prototype this ITE get updated, we expect ITE-7 to be accepted either in
the first or second review periods.

## in-toto Attestations

Apart from the task of reviewing and providing feedback for the development of
new attestation types, the attestation maintainers also plan to work on updating
and maintaining the in-toto attestation specification itself. There are several
tasks planned as part of this effort. Some broad plans are:
* addressing ongoing discussions and issues pertaining to the attestation
  framework
* improving the discoverability of reviewed (ITE-9) predicates
* creating language-independent definitions of reviewed predicates to streamline
  their adoption

## in-toto Implementations

Several of in-toto's implementations were updated with support for various ITEs
in the last year. The Python reference implementation is close to receiving
support for DSSE. in-toto-java and in-toto-rs were updated with support for ITEs
5 and 6. We plan to continue working on our implementations to support new and
existing ITEs. This will greatly aid us as we develop integrations with other
projects and foster adoption in various organizations.

In particular, we plan to work on the Python reference implementation to support
ITE-6 attestations. It is the only implementation that currently has no support
for attestations, and this is because of the stability guarantees we make for
it. The last year has showed us that in-toto attestations are reaching stability
and when ITE-6 is accepted, it will be time to support attestations in the
reference implementation as well.

Our work on in-toto implementations will continue to be in conjunction with the
development of ITEs. Some exciting projects we expect to work on this year are:
* supporting in implementations for the layouts that can verify attestations
* adding ITE-9 reviewed predicates to one or more implementations
* improving usability and simplifying the deployment of in-toto and TUF (ITE-2)
  in software supply chains

## Integrations

Over the years, in-toto has been integrated into various other tools and
systems. We plan to continue supporting their development and collaborating with
other software supply chain security stakeholders. We are excited about the work
we're doing with projects like Keylime, GUAC, and Sigstore, and we hope to talk
about it more over the course of this year.

Integrations we maintain ourselves will continue to get new features and
support. Our Jenkins plugin recently received the capability to generate SLSA
Provenance alongside its support for in-toto link metadata.

## Community

One of the efforts that has already started is a revamp of how the in-toto
community is managed. A new starting point for all things in-toto was set up
recently: https://github.com/in-toto/community. We believe this will help
summarize the various in-toto projects and implementations in one place, as well
as describe aspects of the community such as its governance, meeting cadence,
contributing guidelines, and more.

## Roadmap Review Schedule

We have a new release schedule for our reviews as our roadmap now applies to the
calendar year.

- End of April 2023
- End of August 2023
- End of December 2023

We will use these slots to release our roadmap reviews and depending on the
development of various features, reviews may be accompanied by releases of our
implementations.