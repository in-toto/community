# ROADMAP review (End of December '22)

We've reached the end (and shot past by a bit) of our final evaluation period
for in-toto's [2022 roadmap](/roadmap-reviews/2022/ROADMAP.md).
It's been a busy few months with a lot of updates, and we're happy to find that
we've largely achieved everything we set out to with the 2022 roadmap!

## First Class ITE Support

A number of in-toto Enhancements made progress towards _application_. This is
very heartening as it demonstrates the real world need for the ideas in the
proposals.

### ITE-4

Thanks to the tireless efforts of Yuanrui Chen (NYU) and Alan Chung Ma (Purdue
University), the work on our ITE-4 resolvers has progressed significantly. We
showed off this progress in the form of a demo during in-toto's maintainers
track talk at KubeCon + CloudNativeCon 2022. The demo repository can be found
[here](https://github.com/in-toto/ite-4-demo). It combines ITE-4 resolvers for
GitHub-specific artifacts with one designed to record container artifacts.

### ITE-5

As noted before, we had two Google Summer of Code (2022) students join us to
work on ITE-5 and ITE-5 adjacent projects. Pradyumna Krishna contributed an
implementation of DSSE to securesystemslib, in-toto-python's cryptographic
backend. This was followed by another contribution to in-toto-python that
enables developers to generate and sign metadata using DSSE rather than the
outgoing signature wrapper. These features will be part of an in-toto-python
release in early 2023.

Lenery Chen worked on in-toto-rs through GSoC to add similar DSSE capabilities.
While some of these features were released as v0.3.0, more will land in the next
release in early 2023.

### ITE-6 and ITE-9

The in-toto Attestation framework has seen significant activity. A number of new
attestation formats are being developed and proposed by members of the in-toto
community. Some of these were prototyped and shown off at CloudNativeSecurityCon
2022 and KubeCon + CloudNativeCon 2022. To handle these new formats and to
avoid fragmentation, ITE-9 constituted a group of community members to oversee
and shepherd the proposals. The current maintainers are Marcela Melara (Intel),
Parth Patel (Kusari), Tom Hennen (Google), Mikhail Swift (TestifySec), and
Joshua Lock (VMware).

Parth Patel and Shripad Nadgowda (Intel) are leading the development of an
attestation type to capture runtime traces. There are a number of applications
for traces and some in-toto implementations like Witness already capture this
information. By standardizing the attestation format, different in-toto
implementations and monitors can "speak the same language", allowing them to
consume and make sense of each others' attestations. Runtime traces are planned
to be a key part of Factory for Repeatable Secure Creation of Artifacts (FRSCA),
and the plan is for this work to eventually be integrated with Tekton Chains.

Marcela Melara introduced the Software Supply Chain Attribute Integrity (SCAI)
specification and an in-toto attestation format alongside it. SCAI enables
developers to make evidence-backed claims about certain attributes or properties
of software artifacts. Among other use cases, work is underway to use SCAI to
make assertions about runtime traces where the traces themselves may be private
or too large to share trivially.

We're still working on attestation formats for human reviews. Currently, an
attestation type is being planned apiece for typical code reviews conducted via
services like GitHub as well as reviews or audits of packages consumed as
dependencies, similar to the crev project. In a related effort, the OpenSSF's
Alpha Omega project is evaluating and prototyping in-toto Attestations as a
means to communicate information about automated scans of packages performed as
part of Omega. We're working with them to develop this format as well as to
possibly upstream some of the necessary changes to in-toto-python.

Finally, the SLSA Provenance type got some attention as well. Lakshya Gupta,
another in-toto GSoC student, enabled the generation of SLSA Provenance v0.2 in
in-toto-java. in-toto-java v0.5.0 is now live with this support. Lakshya has
also updated the in-toto Jenkins plugin to optionally generate SLSA Provenance
instead of just in-toto link metadata. We will release this plugin in the coming
weeks. Lenery's work on in-toto-rs also involved SLSA Provenance. The upcoming
release of in-toto-rs will include support for SLSA Provenance v0.2 and we hope
to use this in the rebuilderd integration alongside the existing support for
in-toto link metadata.

## New Integrations / Efforts

In the last few months, some new efforts or projects that consume in-toto
metadata have come forth.

### GUAC

The Graph for Understanding Artifact Composition (GUAC) project was conceived
and architected by in-toto maintainer Santiago Torres-Arias in collaboration
with several industry stakeholders such as Google, Citi, and Kusari. GUAC helps
correlate metadata pertaining to software supply chains such as in-toto
attestations and others such as SBOMs and CVE information. GUAC presents this
information as a queryable graph to decision makers in the software supply
chain.

### Keylime

Mark Bestavros, one of the developers of Keylime, worked to integrate the two
projects. [Keylime](https://keylime.dev) is a CNCF sandbox project that provides
remote boot attestations to nodes in the cloud and IoT spaces, and monitors
runtime to enforce the integrity of executed programs. All of this is backed by
a hardware root of trust.

During in-toto's KubeCon + CloudNativeCon 2022 talk, we showed off a demo by
Mark of this integration in action. We will make more information available as
this integration between two CNCF projects matures.

### Verifiable SBOMs

At KubeCon + CloudNativeCon 2022, a number of software supply chain security
stakeholders convened to discuss how we can use in-toto to derive what are
tentatively called Verifiable Software Bills of Materials (SBOMs). SBOMs are a
key part of visibility into software supply chains, and are complementary to
in-toto's properties that ensure the _integrity_ of software supply chains. This
effort is attempting to combine the features of both, with integrity assurances
via in-toto metadata that can then emit SBOMs in standards like SPDX or
CycloneDX.

This project is _not_ an in-toto project alone. While we are involved, it is
a standalone community effort with input from a variety of supply chain related
metadata.

## OpenSSF Best Practices Badge

We've achieved the OpenSSF Best Practices Gold Badge! in-toto is the 14th
project to achieve this tier.

## Community

We're revamping a number of aspects related to community management. Towards the
end of 2021, we moved our community meetings to a monthly cadence. This has
significantly improved our community engagement and we've seen the benefits in
the form of higher velocity on ITEs and attestation types.

In the coming months, we will be publishing a community oriented repository.
This repository will point folks to the different documents (in-toto-spec,
in-toto Attestation framework, roadmaps), implementations, integrations and
adoptions, governance of different sub-projects, and other logistical
information pertaining to community meeting agendas and notes.

Finally, we've created a new in-toto/friends repository to track adoptions and
integrations. This is preferable to our previous page on the in-toto website
because each entry can be more detailed, helping newcomers understand how
in-toto is used in practice, and a repository is easier for adopters to update
with their own experiences. Feel free to add your in-toto adoption or
integration story!

## Closing Remarks

We've had a busy few months, to the point that this review is in fact VERY
late. It's practically a double feature. We're immensely excited to see all the
activity within the in-toto community and outside. We look forward to continuing
to collaborate with industry and academic practitioners to secure software
supply chains everywhere!