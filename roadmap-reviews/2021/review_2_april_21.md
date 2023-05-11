# ROADMAP review (End of April '21)

We've reached the end of the second evaluation period for our 2021 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's current [ROADMAP](ROADMAP.md).

## ITEs

We have had a lot happening on the in-toto Enhancement (ITE) front! As noted in
our last review, Mark Lodato (@MarkLodato) of the Binary Authorization team at
Google worked on two ITEs, ITE-5 and ITE-6. Since then, ITE-5 has been merged
as a "draft", and ITE-6 has had active discussions that are still ongoing. The
new [signature specification](https://github.com/secure-systems-lab/signing-spec)
has also had several updates, and we published an initial
[v0.1.0 release](https://github.com/secure-systems-lab/signing-spec/releases/tag/v0.1.0).

Further, the work described in ITE-6 has also led to the formation of
[in-toto/attestation](https://github.com/in-toto/attestation). This repository
describes various attestations that describe different aspects of software
supply chains, such as `Provenance`, `Code Review`, `Vulnerability Scan` etc.

- [ITE-5: Replace signature wrapper with SSL signing spec](https://github.com/in-toto/ITE/blob/master/ITE/5/README.adoc)
- [ITE-6: Generalized link format](https://github.com/in-toto/ITE/pull/15)

## Further maturing of implementations and integrations

Several in-toto implementations and subprojects maintained by the core team saw
some activity during this evaluation period.

### in-toto-python

We released the final version, 1.0.1, of our reference implementation that
supports Python 2. Several of our explicit and transitive have dropped support
for Python 2, and our latest release at the end of April 2021, 1.1.0, supports
Python 3 only. The reference implementation has a roadmap that details its
developments, and its latest roadmap review can be found
[here](https://github.com/in-toto/in-toto/blob/develop/roadmap-reviews/2021/review_2_april_21.md).

### in-toto-golang

The Go implementation of in-toto has seen quite a bit of activity. It has
emerged as the ideal testbed for new features and integrations. BoxBoat
recently demonstrated their integration of in-toto and SPIRE.
[This implementation](https://github.com/boxboat/in-toto-golang) is not yet
ready for use in production.

Additionally, contributors from SolarWinds began work on
[adding support](https://github.com/in-toto/in-toto-golang/pull/100) for ITE-6
and in-toto/attestations in in-toto-golang. It is currently a work in progress,
based on how ITE-6 discussions proceed.

The same contributors also added support for the new signature specification.
This [change](https://github.com/in-toto/in-toto-golang/pull/101) makes
in-toto-golang compliant with ITE-5.

### in-toto-rs

We listed our Rust implementation for this year's Google Summer of Code. We
hope to [develop its functionality](https://github.com/in-toto/in-toto-rs/issues/4)
to enable its integration with the
[rebuilderd](https://github.com/kpcyrd/rebuilderd) project. We have some
[ongoing work](https://github.com/kpcyrd/rebuilderd/pull/22) with integrating
in-toto metadata into rebuilderd, and we look forward to testing this out on
our [hosted instance](https://r-b.engineering.nyu.edu/).

## Closing Remarks

As always, we have had a busy few months. We are excited to see many new ideas
converge in the form of new features and integrations, and we plan to continue
working with our partners in academia, open source communities, and the
industry to make software supply chains more secure.
