# ROADMAP review (End of July '21)

We've reached the end of our third and final evaluation period for our 2021 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's current [ROADMAP](ROADMAP.md).

## ITEs

As noted in our previous reviews, ITE-5 replaces the signature wrapper with the new
SSL Signing Spec. This specification has since been renamed as the
[Dead Simple Signing Envelope (DSSE)](https://github.com/secure-systems-lab/dsse),
and has also had a stable v1.0 release! ITE-5 is still a draft, but DSSE is
also a part of the ITE-6 story.

On that note, ITE-6 discussions continued and it has been merged as a draft. The
[in-toto Attestation](https://github.com/in-toto/attestation) project which came
out of it is being actively developed and enhanced.

- [ITE-5: Replace signature wrapper with SSL signing spec](https://github.com/in-toto/ITE/blob/master/ITE/5/README.adoc)
- [ITE-6: Generalized link format](https://github.com/in-toto/ITE/blob/master/ITE/6/README.md)

## Further maturing of implementations and integrations

Several in-toto implementations and subprojects maintained by the core team saw
some activity during this evaluation period.

### in-toto-python

Our definitive implementation saw the release of v1.1.1 at the end of July
2021. While this was a relatively minor release, we were glad to see one
new external contributor submitting a patch! The reference implementation
maintains its own annual
[roadmap](https://github.com/in-toto/in-toto/blob/develop/roadmap-reviews/2021/ROADMAP.md)
and [reviews](https://github.com/in-toto/in-toto/blob/develop/roadmap-reviews/2021/),
and this can shed more light on its activity.

### in-toto-golang

The Go implementation has continued in its role of being a testbed for new
features and integrations. It now includes an implementation of DSSE v1,
and support for in-toto Attestations, both present in the latest release,
v0.2.0.

## in-toto-rs

Our Rust implementation has also seen some exciting work thanks to Qijia "Joy"
Liu (@joyliu-q), who joined us as part of Google Summer of Code. The
implementation now boasts the capability to generate in-toto link metadata by
performing what we informally refer to as the in-toto-run workflow. Part of
the project for this summer is adding in-toto link generation capabilities to
rebuilderd. In the near future, we expect rebuilders such as the
[NYU rebuilder](https://r-b.engineering.nyu.edu/) to display in-toto links for
every package rebuild attempt!

## Closing Remarks

As always, we have had a busy few months. We are excited to see many new ideas
converge in the form of new features and integrations, and we plan to continue
working with our partners in academia, open source communities, and the
industry to make software supply chains more secure.
