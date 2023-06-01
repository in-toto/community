# ROADMAP review (End of April '22)

We've reached the end of the second evaluation period for our 2022 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's current [ROADMAP](ROADMAP.md).

## First Class ITE Support

We've had some exciting movement on the ITE front, the de jure process for
changes to in-toto.

### ITE-4

Yuanrui Chen, a student at NYU, and Alan Chung Ma, of Purdue, have been
working on developing resolvers for ITE-4 entities. By adding the ability to
treat GitHub objects and containers as artifacts natively within in-toto, their
work will enable the use of in-toto across broader contexts in the software
development process.

### ITE-5

ITE-5 was accepted earlier this year, and we are now working to support
generating DSSE metadata in our implementations. As part of Google Summer of
Code (GSoC) 2022, Pradyumna Krishna will be joining us to develop DSSE
capabilities for the Python reference implementation.

Similarly, Lenery Chen will be joining in-toto through GSoC to work on the Rust
implementation. Part of this work will include adding DSSE capabilities.

### ITE-6

There has been some progress in using in-toto layout metadata to verify ITE-6
attestations like the SLSA provenance specification. There's more news to come
on this front that we hope to be able to share soon!

The topic of _accepting_ ITE-6 itself has come up in the monthly community
meetings. The final fixes and changes necessary to accept the ITE are being
worked on, and should land soon.

Finally, Lakshya Gupta is joining in-toto through GSoC to work on generating
ITE-6 attestations via in-toto's Jenkins plugin. Among other things, this work
will allow Jenkins users to make progress on SLSA compliance.

### ITE-9

A new proposal, ITE-9, was introduced to describe a process for community
members to _propose and agree on_ new attestation types. This will ensure different in-toto
implementations can handle new attestation types without confusion while also
ensuring the broader community is aware of the different options available to
them within in-toto.

## CII Gold Badge

While there hasn't been direct work on this front during this period, the
missing requirements will be met through new contributors joining in-toto in
the near future through GSoC, NYU, and Purdue.

## Closing Remarks

We've had a busy few months (to the point that this review is in fact late). We
are always excited by the work being done within the in-toto community by all
the contributors and we look forward to a busy summer with our GSoC mentees to
close out the final evaluation period of our current roadmap.