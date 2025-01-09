![in-toto Logo](images/in-toto-logo.png "in-toto Logo")

in-toto provides a framework to protect the integrity of the software supply
chain. It does so by verifying that each task in the chain is carried out as
planned, by authorized personnel only, and that the product is not tampered with
in transit.

## Specification

Primarily, in-toto is a [specification](https://github.com/in-toto/docs). This
specification has been implemented in multiple languages. The specification can
be extended or changed by proposing
[in-toto Enhancements](https://github.com/in-toto/ite). Several have been
proposed and accepted and the full ITE process is documented as
[ITE-1](https://github.com/in-toto/ITE/blob/master/ITE/1/README.adoc).

Newcomers to the in-toto project are encouraged to familiarize themselves with
the specification and to see it in action with the in-toto
[demo](https://github.com/in-toto/demo).

## Attestations

The [in-toto attestation framework](https://github.com/in-toto/attestation) is a
stand-alone specification that defines the attestation format. An in-toto
attestation is a piece of authenticated metadata that captures information about
a set of software artifacts. The attestation framework was introduced in ITE-6.


### attestation-verifier

Attestation-verifier is a prototype of verification capabilities introduced in
in-toto enhancements 10 and 11. 

* [GitHub Repository](https://github.com/in-toto/attestation-verifier)


## Implementations

The in-toto maintainers oversee the development of four implementations of the
specification. They are in varying states of conformance with the
[in-toto specification](#specification) and the
[attestation framework](#attestations).

### in-toto-python (Reference Implementation)

This implementation was the first one and has reached the v1.0 milestone. As
such, it makes stability guarantees and is actively used in production by some
in-toto adopters.

Links:
* [GitHub Repository](https://github.com/in-toto/in-toto)
* [Good First Issues](https://github.com/in-toto/in-toto/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)

### in-toto-golang

This implementation is used for various cloud native integrations. It sees very
active development as it's the testbed for experimental features and changes
introduced as ITEs.

Links:
* [GitHub Repository](https://github.com/in-toto/in-toto-golang)
* [Good First Issues](https://github.com/in-toto/in-toto-golang/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)

### in-toto-java

The Java implementation was originally written to support integrations with the
Jenkins CI/CD system. It implements some of the in-toto specification and also
includes support for some attestation types.

Links:
* [GitHub Repository](https://github.com/in-toto/in-toto-java)
* [Good First Issues](https://github.com/in-toto/in-toto-java/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)

### in-toto-rs

in-toto-rs implements the in-toto specification in Rust. It is used in
integrations with the
[Reproducible Builds project](https://reproducible-builds.org) such as with
[rebuilderd](https://github.com/kpcyrd/rebuilderd).

Links:
* [GitHub Repository](https://github.com/in-toto/in-toto-rs)
* [Good First Issues](https://github.com/in-toto/in-toto-rs/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)

## User & Client Libraries and Tools 

### Witness

Witness is a dynamic CLI tool that integrates into pipelines and infrastructure to create an audit trail for your software's entire journey through the software development lifecycle (SDLC) using the in-toto specification. In addition Witness also features its own policy engine with embedded support for OPA Rego, so you can ensure that your software was handled safely from source to deployment.

Links:
* [GitHub Repository (cli tool)](https://github.com/in-toto/witness)
* [GitHub Repository (library)](https://github.com/in-toto/go-witness)
* [Good First Issues (cli tool)](https://github.com/in-toto/witness/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)
* [Good First Issues (library)](https://github.com/in-toto/go-witness/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)
* [Website](https://witness.dev)

### Archivista 

Archivista is a graph and storage service for in-toto attestations. Archivista enables the discovery and retrieval of attestations for software artifacts.

Links:
* [GitHub Repository](https://github.com/in-toto/archivista)
* [Good First Issues](https://github.com/in-toto/archivista/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)


## How is in-toto differentiated in the Cloud Native landscape?   What does it do differently and why?

One of the most pressing security problems in cloud native is software supply chain security.  in-toto  addresses this issue by providing a secure and trustworthy means for representing all the operations within the cloud-native pipeline and verifying that they were carried out to the letter.
A good way to understand the need for in-toto in the Cloud Native space is to understand the value of signed SBOMs vs in-toto metadata + layouts.  A signed SBOM indicates that some party (whose key you presumably have a reason to trust) states what the software contains.  In contrast, in-toto will have signed information about the individual steps of the supply chain cryptographically linking metadata together from various parties and validating this all against the software’s policies.  As a result, their protection modes would work quite differently in many cases.  For example, see the following table:


| Attack scenario |   Signed SBOM Result | In-toto layout + metadata result |
|-----------------|----------------------|----------------------------------|
| Software manipulated after software supply chain completed | Detect and reject the malicious software | Detect and reject the malicious software |
| Attacker compromises VCS and inserts malicious (unsigned) code where signatures are required  |Undetected.  User compromised. | Detect and reject the malicious software |
| Attacker substitutes a malicious dependency (not signed by that dependeny’s maintainer) |Undetected.  User compromised. | Detect and reject the malicious software 
| Attacker provides files to the build system which did not come from the VCS | Undetected.  User compromised | Detect and reject the malicious software |
| Attacker containerizes / packages binaries other than the ones the build system built | Undetected.  User compromised | Detect and reject the malicious software |
| Tests are not run on the software but it is (accidentally?) released to production | Undetected.  User compromised | Detect and reject the malicious software |
| The legal team has not reviewed source code licenses for included libraries | Undetected.  Impact varies | Detect and reject the software |

One important thing to note about the table above is that it isn’t impossible for someone to do many of these steps and checks before signing an SBOM.  If you did all of these checks, and signed the statements saying you did them to provide stronger validation, and distributed the root of trust for your signatures in a secure way, and managed situations where signing keys need to be revoked / rotated / expired, and handled trust delegation to different parties, and linked metadata between steps together, and let people write policies to reason about those steps, and let them link metadata in from dependencies to do so, and handled all of the above in scenarios where insiders can be maliciously interfering with your, system, then you would effectively reconstruct in-toto.
We are aware of some efforts, like the Zephyr project, where project members have worked to try to reconstruct some of the guarantees of in-toto and decided to live with the gaps in their security for other portions.  For groups that have done this work already this does make sense to us as a viable alternative in the short term.  However, we do believe that using a common, holistic approach like in-toto will be necessary as projects continually add the missing security pieces from in-toto and want to reason more and more about each other as dependencies.

Note that in-toto is not a substitute for having appropriately secure steps in the software supply chain.  For example, if you use an insecure process of building software that just curls and builds software from a website, in-toto will happily sign metadata indicating that you did the same insecure action indicated you would.  

This is why projects like SLSA and FRSCA are built as an opinionated set of steps on top of in-toto.  They specify which actions they feel are more important for software supply chain security and mandate their use.  

These projects are solving different problems at different levels.  In-toto allows you to capture information about your steps, ensure policies about them are applied, handle trust of keys, etc.  Frameworks like SLSA and FRSCA use in-toto as a mechanism to capture and enforce a specific set of policies 


## Adopters and other repositories of note

in-toto is integrated into several other ecosystems and complementary software
supply chain security efforts. An inexhaustive list of integrations and
adoptions is maintained in the
[in-toto/friends](https://github.com/in-toto/friends) repository.

The project maintains several integrations and resources pertaining to in-toto
such as:
* [in-toto Jenkins Plugin](https://github.com/jenkinsci/in-toto-plugin/)
* [in-toto Helm Charts](https://github.com/in-toto/helm-charts/)
* [Dockerfiles](https://github.com/in-toto/Dockerfiles)
* [in-toto Grafeas Connector](https://github.com/in-toto/totoify-grafeas)
* [Debian apt in-toto transport](https://github.com/in-toto/apt-transport-in-toto)

Contributions are welcome to these projects and any other repository in the
[in-toto GitHub organization](https://github.com/in-toto).

