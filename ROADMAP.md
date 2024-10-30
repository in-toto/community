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

- The in-toto v1.0 Specification was tagged June 5th 2023
- ITEs to support layouts with the attestation framework were merged as `Draft`
  - ITE-10: Supporting Contextual in-toto Attestations in Layouts
  - ITE-11: Verifying Attributes in in-toto Attestations

### Attestations

- New Predicate Types
  - Software Supply Chain Attribute Integrity (SCAI)
  - Release
  - Reference
- Protobuf Language Bindings available
  - Go
  - Java
  - Python

### Witness

- Donation of the project to in-toto during KubeCon '23 - Chicago
- Improvement of CLO Monitor Scores to 99+
- Support for generating new types of attestations:
  - SLSA Attestor
  - Link Attestor
  - Jenkins Attestor
  - SBOM Attestor
  - VEX Attestor
- Support for new Key Management Systems (KMS)
  - AWS KMS
  - GCP KMS
- New documentation website

### Archivista

- Donation of the project to in-toto during KubeCon '23 - Chicago
- Improvement of CLO Monitor Scores to 95+
- Helm charts for deployment
- Support for eventing on attestation uploads
- Storing of Witness Policies

### Others

- Docs assessment from CNCF Tech Docs group

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
