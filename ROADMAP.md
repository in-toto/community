# Roadmap

_Note: Previous roadmaps can be found with the roadmap reviews for that period.
[Link to Roadmaps](/roadmap-reviews/)_

## Ongoing Work

Cross-collaboration with many external groups and projects, including:

- OpenSSF and  groups
  - SBOMit
  - GitTUF
  - Protobom
- IETF
  - SCITT
- Package Repositories
  - PyPi
  - RubyGems

## Recently Completed Work

### Ecosystem

Several major products and repositories now have support for in-toto attestations, including:

- NPM
- Homebrew
- GitHub
- GitLab

### Specification and In-toto Enhancements (ITEs)

- The in-toto v1.0 [Specification](https://github.com/in-toto/specification/blob/v1.0/in-toto-spec.md) was tagged June 5th 2023
- ITEs to support layouts with the attestation framework were merged as `Draft`
  - [ITE-10](https://github.com/in-toto/ITE/tree/master/ITE/10): Supporting Contextual in-toto Attestations in Layouts
  - [ITE-11](https://github.com/in-toto/ITE/tree/master/ITE/11): Verifying Attributes in in-toto Attestations

### Attestations

- New Predicate Types
  - Software Supply Chain Attribute Integrity ([SCAI](https://github.com/in-toto/attestation/blob/main/spec/predicates/scai.md))
  - [Release](https://github.com/in-toto/attestation/blob/main/spec/predicates/release.md)
  - [Reference](https://github.com/in-toto/attestation/blob/main/spec/predicates/reference.md)
- Protobuf Language Bindings available
  - [Go](https://github.com/in-toto/attestation/tree/main/go)
  - [Java](https://github.com/in-toto/attestation/tree/main/java)
  - [Python](https://github.com/in-toto/attestation/tree/main/python)

### Witness

- [Donation](https://github.com/in-toto/community/issues/17) of the project to in-toto during KubeCon '23 - Chicago
- Improvement of [CLO Monitor Scores](https://clomonitor.io/projects/cncf/in-toto#witness) to 99+
- Support for generating new types of attestations:
  - [SLSA Attestor](https://witness.dev/docs/docs/attestors/slsa)
  - [Link Attestor](https://witness.dev/docs/docs/attestors/link)
  - [Jenkins Attestor](https://github.com/in-toto/go-witness/pull/323)
  - [SBOM Attestor](https://witness.dev/docs/docs/attestors/sbom)
  - [VEX Attestor](https://witness.dev/docs/docs/attestors/vex)
- Support for new Key Management Systems (KMS)
  - [AWS KMS](https://witness.dev/docs/docs/signers/kms#aws)
  - [GCP KMS](https://witness.dev/docs/docs/signers/kms#gcp)
- New documentation [website](https://witness.dev/)

### Archivista

- [Donation](https://github.com/in-toto/community/issues/18) of the project to in-toto during KubeCon '23 - Chicago
- Improvement of [CLO Monitor Score](https://clomonitor.io/projects/cncf/in-toto#archivista) to 95+
- Helm [charts](https://github.com/in-toto/archivista/tree/main/chart) for deployment
- Support for [eventing](https://github.com/in-toto/archivista/pull/377) on attestation uploads
- Storing of Witness [Policies](https://github.com/in-toto/archivista/pull/251)

### Others

- Docs [assessment](https://github.com/cncf/techdocs/blob/main/analyses/0009-in-toto/README.md) from CNCF Tech Docs group

## Near and Mid-term Work

### Specification and In-toto Enhancements (ITEs)

- Formal acceptance of ITE-10 and ITE-11

### Attestations

- Continued work to build out library of common predicate types
- Documentation on best practices and considerations in choosing when to use a specific predicate type when there may be multiple similar options

### Witness

- Support for ITE-10 and ITE-11-style policies
- New attestor types
  - OmniTrail: based on the Omnibor project
  - Lockfile: Storing contents of common language lock files
- Support for Sigstore bundle format during signing
- Continued documentation updates
- A framework to allow external attestors
- TUF Client to securely receive up-to-date policies from Archivista

### Archivista

- Integration with RSTUF
  - Policies: the ability to store, approve, and revoke trust in Witness policies via TUF metadata
  - Attestations: the ability to store, approve, and revoke trust in attestations via TUF metadata

### Others

Policy WG continuing collaboration on new policy specification, moving ITE-10 and ITE-11 towards acceptance

## Long-term Work

- Deprecate in-toto golang
- Documentation and Github repository restructuring
- Consolidate cryptographic signing libraries
- Continued collaboration and integration with open source build and security tools
