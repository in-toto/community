# ROADMAP review (End of December '21)

We've reached the end of the first evaluation period for our 2022 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's [ROADMAP](ROADMAP.md) for this year.

## ITE Support

More and more of in-toto's development today is based on the foundation provided
by the in-toto Enhancement (ITE) mechanism. As a reminder, we have been focusing
on the following ITEs this year:

- ITE-4: Support abstract artifact resource types (more on this below)
- ITE-5: Use a new, and pluggable signing specification
- ITE-6: Support abstract link attestation types (e.g., vulnerability scan)
- ITE-7: Support external identity providers for functionaries (e.g., x509 or SPIFFE)

### ITE-4: abstract resource types

We have started work on implementing more artifact hashers / resolvers as
described in the ITE-4 spec. Alan Chung Ma (@alanssitis), an undergraduate
student at Purdue University has joined us to implement them in our reference
implementation, and we are very excited to see these efforts progress. If you
would like to see a hasher for a particular use case, please get in touch with
us via the mailing list or #in-toto on the CNCF Slack workspace!

### ITE-5: the move to DSSE (and other signature wrappers)

ITE-5 was accepted during this period! With this move, the in-toto specification
no longer specifies or mandates a particular signature wrapper, but instead
requires any wrapper used to have certain important properties. The next step is
for our key implementations to support the new wrapper, and we are working on
adding support to our Go implementation to generate in-toto link metadata using
DSSE as well as the old wrapper. This will allow our users to transition
smoothly. If you're interested in contributing to this effort, head to the
[corresponding issue](https://github.com/in-toto/in-toto-golang/issues/148)!

In the same period, our sister project The Update Framework (TUF) merged as
draft an augmentation proposal that mirrors ITE-5. This proposal disassociates
the signature wrapper and presents similar properties for any wrapper used by a
TUF implementation. It can be found here:
[TAP-17](https://github.com/theupdateframework/taps/blob/master/tap17.md)

### ITE-6: abstract attestation types

This period has seen plenty of movement in regards to experimentation and
sketching. In particular, the SLSA provenance type saw three different
iterations based on feedback from the community. It has seen plenty of use
within Chains inside of the rekor transparency log. Likewise, other attestation
types from projects such as Witness and SPDX have been created and submitted in
the wild. Other attestations are being discussed. These include the ones for
code review and vulnerability scanners.

Beyond the various types of attestations, ITE-6 types will need a
community-based process to allow discussion and agreement between different
stakeholders for each individual type. We expect the coming period to include a
discussion around these initiatives to better streamline the creation of new
types.


### ITE-7: leveraging further identity provider ecosystems

in-toto now has support for x509 certificates and SPIFFE through SPIRE. We're
excited for what this means to the broader ecosystem. ITE-7's semantics are now
available through a prerelease of the Go implementation for users to test. The
code was contributed by the folks at BoxBoat and TestifySec, and their efforts
mean that these features are available earlier than we expected in our initial
roadmap!

Further, as usage on the pre-release branch of ITE-7, and tools leverage these
features it will be easier to fine tune the last details of the proposal. With
this, we envision ITE-7 acceptance to move forward before the next roadmap
review.

### Other ITE updates

We have some logistical updates to other ITEs. ITE-2 is now up for acceptance.
If you have any thoughts on the matter, head to [this
issue](https://github.com/in-toto/ITE/issues/26). Also, ITE-3 was accepted
during this period! As a refresher, this ITE details Datadog's integration of
TUF and in-toto, which is generally specified in ITE-2.

We have also released an early proposal, ITE-8, from Furkan Türkal (@Dentrax),
Batuhan Apaydın (@developer-guy), and Erkan Zileli (@erkanzileli). This ITE
proposes a curated library of example policies that users can build on for their
supply chains.

## Quality of Life / User Experience / Other Implementation Updates

Our implementations saw a lot of UX improvements, many of which came from the
in-toto community. in-toto-golang gained a CLI, kindly contributed by the folks
at BoxBoat and TestifySec. Other members of the community also contributed
valuable documentation support, auto completion support for the CLI, and more!

Significantly, we had our first CVE during this period. Tagged CVE-2021-41087,
the vulnerability allowed authenticated attackers to create attestations that
could bypass a DISALLOW rule in the corresponding layout. The full advisory can
be found
[here](https://github.com/in-toto/in-toto-golang/security/advisories/GHSA-vrxp-mg9f-hwf3),
and was reported by Parth Patel (pxp928) of BoxBoat. A fix was submitted by
Brandon Mitchell (@sudo-bmitch), also of BoxBoat.

Our Java implementation saw significant activity as well, and we welcomed a new
maintainer, Sergio Felix (@Alos) of Google, to the team. The latest version,
v0.4.0 includes support for DSSE as well as ITE-6 style attestations.

Finally, as noted in prior updates, we have a Rust library that can generate
in-toto link metadata. This has now been integrated into
[rebuilderd](https://rebuilderd.com), meaning that rebuilders, like the [NYU
rebuilder](https://r-b.engineering.nyu.edu) and the [Purdue
rebuilder](https://reproducible.seal.purdue.wtf/), now generate in-toto links
for every package they successfully build! This was made possible by the
excellent work of Qijia "Joy" Liu (@joyliu-q) and kpcyrd (@kpcyrd).

## CII Gold Badge

We are optimistic that the activity on the Python reference implementation due
to ITE-4 resolvers / hashers will help us check off the final requirements to
qualify for the Gold badge. We should have more updates on this front in future
reviews.

## Closing Remarks

It has been a busy few months for in-toto! We are very excited about the
increased activity in and contributions from our community of like-minded
practitioners in academia, open source communities, and the industry. We hope to
continue and grow this community, while positively impacting the software supply
chain security space.
