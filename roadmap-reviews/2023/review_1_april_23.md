# ROADMAP review (End of April '23)

This is a retrospective review for the first evaluation period of the 2023
[roadmap](/ROADMAP.md).

## Change in in-toto Governance

Though not recorded as an item in the roadmap, in-toto's biggest update in this
period was the change in governance model and the formation of the in-toto
Steering Committee (ITSC). Previously, in-toto's governance had one Consensus
Builder who oversaw the community. The new governance model was
[proposed](https://github.com/in-toto/community/pull/3) by Santiago
Torres-Arias, then the Consensus Builder for in-toto, and was approved by other
maintainers and community members along with the [ITSC
charter](https://github.com/in-toto/community/pull/4). Following this, the
in-toto community was invited to [nominate and vote on the
members](https://github.com/in-toto/community/issues/5) of the first ITSC. The
members are Santiago Torres-Arias (Purdue University), Justin Cappos (New York
University), Jack Kelly (ControlPlane), Cole Kennedy (TestifySec), and Trishank
Karthik Kuppusamy (Datadog).

## in-toto v1.0

The in-toto specification was updated with several clarifications to prepare for
its v1.0 release. In addition, the specification started a security audit
courtesy of the CNCF and OSTIF. [Some security
reports](https://github.com/in-toto/docs/security/advisories) were published for
the specification as part of this effort.

## in-toto Attestations

The [in-toto Attestation
Framework](https://github.com/in-toto/attestation/releases/tag/v1.0) reached its
v1.0 milestone. This was accompanied by a concerted effort to improve the
framework's tooling. These changes make it easier for developers to adopt
in-toto's attestations and the different vetted predicates.

## ITEs

This review period also saw several ITE updates. First, Aditya Sirish A
Yelgundhalli joined the roster of ITE editors. He joins the current ITE editors
Santiago Torres-Arias, Justin Cappos, and Trishank Karthik Kuppusamy.

The most significant ITE update is the acceptance of
[ITE-6](https://github.com/in-toto/ITE/blob/master/ITE/6/README.adoc). This was
paired with the aforementioned release of v1.0 of the in-toto Attestation
Framework.

This period also saw the introduction of
[ITE-10](https://github.com/in-toto/ITE/pull/38) that describes how in-toto
layouts must be updated to support attestations. The ITE details how in-toto's
artifact rules can be used with attestations representing different predicate
types, as well as how existing policy or expression languages can be used for
certain attribute checks that previously required complicated inspection
scripts.

## Implementations

This period was relatively quiet for in-toto's implementations. The most
significant update to in-toto's Python reference implementation added support
for DSSE, using semantics described in
[ITE-5](https://github.com/in-toto/ITE/blob/master/ITE/5/README.adoc). in-toto's
Go implementation received support for the Provenance format defined in SLSA v1,
with work underway to merge efforts with the in-toto Attestation Framework's
tooling for the predicate.

Apart from these updates, in-toto's Python and Go implementations also started a
security audit alongside the in-toto specification.

## Community

The in-toto community continued to grow, spurred on by the new governance model
and events like KubeCon + CloudNativeCon EU. As always, we're excited to see
in-toto develop with participation from community members from a variety of
backgrounds, open source, academia, and industry.
