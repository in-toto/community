# ROADMAP review (End of August '23)

This is the second review of the in-toto [roadmap](/ROADMAP.md) for 2023.

## in-toto v1.0

During this period, the in-toto specification reached the v1.0 milestone. The
v1.0 specification adheres to or recommends (as appropriate) ITEs 1, 2, 3, 4,
and 5. Future versions of the specification are expected to incorporate the
ITE-6 and above, i.e., the Attestation Framework and more.

## ITEs

The ITE-10 proposal was split into two ITEs,
[10](https://github.com/in-toto/ITE/blob/master/ITE/10/README.adoc) and
[11](https://github.com/in-toto/ITE/pull/50). The new ITE-10 focuses exclusively
on how the in-toto layouts can use existing semantics like artifact rules with
attestations. The ITE was accepted as a draft.

ITE-11, on the other hand, describes the use of expression languages like Common
Expression Language (CEL) for attribute checks in layouts. With ITE-11, in-toto
adopters can stop relying on complicated inspection scripts for relatively
simple checks, instead defining such checks within the layout itself. Both
ITE-10 and ITE-11 are being actively prototyped ahead of their adoption in
in-toto implementations.

## Implementations

Following the conclusion of the in-toto security audit, the in-toto Python
implementation received several updates including a breaking change that led to
the release of [v2.0.0](https://github.com/in-toto/in-toto/releases/tag/v2.0.0).
The implementation also published two [security
advisories](https://github.com/in-toto/in-toto/security/advisories) with one
CVE. These were accompanied by a detailed
[blog post](https://in-toto.io/security-audit-23/) describing the outcome of the
audit with all the findings.

The audit unearthed no issues with in-toto's Go implementation. That said, the
implementation received other updates such as experimental support for DSSE,
introduced via
[ITE-5](https://github.com/in-toto/ITE/blob/master/ITE/5/README.adoc).

## Graduation

Following various milestones such as v1.0 releases and the completion of the
security audit, the in-toto Steering Committee decided it was time to apply for
graduation at the CNCF. This proposal is [currently
open](https://github.com/cncf/toc/pull/1162) pending further action from the
CNCF TOC.
