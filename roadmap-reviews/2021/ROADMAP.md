Roadmap
=======

_Note: Previous roadmaps can be found with the roadmap reviews for that period.
[Link to Roadmap 2020](/roadmap-reviews/2020/ROADMAP.md)_

This document spans the Roadmap for the in-toto project for the time window
from August 2020 to August 2021. The main theme of this year's efforts are
focused on further maturing of our various implementations and integrations in
an effort to encourage adoption, refining ITE-2 and ITE-3 to standardize the
integration of TUF and in-toto in software supply chains, and developing an
ecosystem for resolvers as defined in ITE-4.

## Further maturing of implementations and integrations

Apart from the reference implementation written in Python, in-toto now provides
libraries in three different languages - in-toto-golang, in-toto-java,
and in-toto-rs (written in Rust). This allows for in-toto attestations in
a variety of use-cases. And as noted in the prior roadmap and the subsequent
reviews, in-toto provides applications to integrate with platforms such as
Jenkins, Kubernetes, apt for Debian, and rebuilderd for Reproducible Builds. We
were able to improve cross-implementation interoperability in the last year,
but we still lack a thorough integration test harness that ensures metadata
generated in any of our various implementations and applications can be
correctly verified. We plan to implement such a harness over the course of this
next roadmap.

The further maturing of our implementations allows us to provide more guarantees
to our adopters, enabling them to use in-toto to secure their supply chains
without worry of any breaking changes. Our plan of releasing version 1.0 of the
reference implementation in the next few months should go a long way to
achieving that.

### in-toto-golang

Christian Rebischke (@shibumi) joined us for the summer of 2020 to work on
[in-toto-golang](https://github.com/in-toto/in-toto-golang)'s runlib
capabilities as part of
[Google Summer of Code](https://summerofcode.withgoogle.com/projects/#4804162597945344).
We are very excited to see the maturing of this in-toto implementation, which
will also help us further our interoperability.

### in-toto-java

The [Java implentation of in-toto](https://github.com/in-toto/in-toto-java) is
currently not entirely compliant with the in-toto specification. Instead, it
aims to provide a reduced, but usable core feature-set. We aim to add more
features in the next roadmap, as noted in the implementation's
[documentation](https://github.com/in-toto/in-toto-java/blob/master/README.md).

### in-toto-rs

This [in-toto implementation](https://github.com/in-toto/in-toto-rs) was written
to serve as a Rust library for generating in-toto attestations. In particular,
it is handy for use in rebuilderd. Speaking of which....

### rebuilderd

As noted in the final roadmap review of 2020, Santiago Torres-Arias
(@SantiagoTorres) has been working on
[adding in-toto attestations](https://github.com/kpcyrd/rebuilderd/pull/22) to
rebuilderd. We plan to continue working on this effort and to work towards using
in-toto links as a verifiable format for results of rebuilders.

### Tekton Project

We are very excited to see Tekton, a Kubernetes-based pipeline manager, to take
a stab at the software supply chain security problem with their [chains](https://github.com/tektoncd/chains/)
project. We are even more excited to see that chains will be able to create
[in-toto](https://github.com/tektoncd/chains/pull/13) links to attest for the
operations when using Tekton. This way, you can automagically secure the
actions in your Tekton pipelines. This year, we will work closely with the
Tekton community to make Chains a widespread, strong component of the software
supply chain security ecosystem.

### Kubernetes components

Our Kubernetes components (namely, a [kubectl plugin](https://github.com/in-toto/kubectl-in-toto) and a k8s [admission
controller](https://github.com/in-toto/in-toto-webhook)) have seen little
movement throughout the year. However, as we start supporting more and more
cloud-native deployments, we are starting to see more use for these. This year,
we will mature these projects into more reliable and easy-to-use tools.

### in-toto Jenkins plugin

The [in-toto Jenkins plugin](https://github.com/jenkinsci/in-toto-plugin) is
used to generate in-toto links for steps in Jenkins pipelines. During the last
roadmap period, we added Grafeas as a native transport. During this next
roadmap, we aim to work on further maturing the plugin with greater granularity,
particularly in better specifying the artifacts to record while generating the
attestations, and some other refactoring as recorded in the repository's issues.

## TUF + in-toto

We are continuing to work on better integrating in-toto with our sister project,
The Update Framework (TUF).

### ITE-2 and ITE-3

Trishank Karthik Kuppusamy (@trishankatdatadog) sponsored
[ITE-2](https://github.com/in-toto/ITE/blob/master/ITE/2/README.adoc) and
[ITE-3](https://github.com/in-toto/ITE/blob/master/ITE/3/README.adoc) that
detail how TUF and in-toto can be combined to provide end-to-end security
guarantees. We aim to work with the stakeholders of these ITEs to standardize 
the recommendations.

### Streamline development of overlapping components

During this next year, we plan to propose an ITE (and perhaps a TAP) to
coordinate the development of the overlapping parts of the specifications. The
two projects share parts of the document formats, and it is beneficial to
maintain consistency.

## ITE-4

[ITE-4](https://github.com/in-toto/ITE/blob/master/ITE/4/README.adoc) introduced
generic resource types to artifacts in in-toto. It is being implemented by Cloud
Native Applicaton Bundles (CNAB) to verify the generation of their metadata. We
aim to work with interested parties to develop resolvers for other resource
types. This experience will also help refine the ITE.

## Roadmap review schedule

As before, we intend to review the progress done in these efforts in the
following windows.

- [End of December](roadmap-reviews/2021/review_1_december_20.md)
- [End of April](roadmap-reviews/2021/review_2_april_21.md)
- [End of July](roadmap-reviews/2021/review_3_july_21.md)

These windows will also be used to update all stakeholders with the status of
the in-toto project as a whole.
