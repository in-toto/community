# in-toto

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

## Other Repositories of Note

in-toto is integrated into several other ecosystems and complementary software
supply chain security efforts. An inexhaustive list of integrations and
adoptions is maintained in the
[in-toto/friends](https://github.com/in-toto/friends) repository.

The project maintains several integrations and resources pertaining to in-toto
such as:
* [in-toto Jenkins Plugin](https://github.com/jenkinsci/in-toto-plugin/)
* [Dockerfiles](https://github.com/in-toto/Dockerfiles)
* [in-toto Grafeas Connector](https://github.com/in-toto/totoify-grafeas)
* [Debian apt in-toto transport](https://github.com/in-toto/apt-transport-in-toto)

Contributions are welcome to these projects and any other repository in the
[in-toto GitHub organization](https://github.com/in-toto).