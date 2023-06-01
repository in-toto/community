# ROADMAP review (End of June '20)

We've reached (and slightly shot past) the end of our 2020 roadmap, and it's
time to review of our activities over the past year.

## Cloud Native Computing Foundation

We are very proud to announce that in-toto
[joined](https://github.com/cncf/toc/pull/252) the Cloud Native Computing
Foundation (CNCF) sandbox in the last year. This is another positive step to
broader integrations in the industry, especially in the Cloud Native space.

## Cross-implementation interoperability

- [__in-toto-golang__](https://github.com/in-toto/in-toto-golang) Apart from
  [ed25519 signing](https://github.com/in-toto/in-toto-golang/pull/48) and
  [bug fixes in the canonical JSON implementation](https://github.com/in-toto/in-toto-golang/pull/50)
  discussed in the previous reviews, work began in earnest on bringing
  in-toto's _runlib_ to the Go implementation. The implementation has already
  gained the
  [ability to record to symbolic links](https://github.com/in-toto/in-toto-golang/pull/55),
  and work is under way to
  [add exclude patterns](https://github.com/in-toto/in-toto-golang/pull/53).
  Christian Rebischke (@shibumi) joined the in-toto team to implement _runlib_
  as part of
  [Google Summer of Code (GSoC)](https://summerofcode.withgoogle.com/projects/#4804162597945344)
  and you can find his detailed plan [here](https://github.com/in-toto/in-toto-golang/pull/56).
  in-toto is participating in GSoC through the CNCF.
  In the process, Christian also identified a nil pointer dereference in Go's
  standard library for RSA, and he opened a
  [pull request](https://go-review.googlesource.com/c/go/+/240008/) to address
  it. Efforts are also underway to improve interoperability between this
  implementation and the reference implementation, and they're part of this work
  on adding _runlib_.

- [__in-toto-rs__](https://github.com/in-toto/in-toto-rs) Santiago
  Torres-Arias (@SantiagoTorres) began work on a Rust implementation of in-toto.
  This broadens in-toto's attestation generation capabilities, and in-toto-rs is
  [being added](https://github.com/kpcyrd/rebuilderd/pull/22) to _rebuilderd_ to
  generate attestations as part of the Reproducible Builds effort.

- [__in-toto-java__](https://github.com/in-toto/in-toto-java) The Java
  implementation saw relatively lesser activity this year. The only activity was
  the
  [updating of some documentation](https://github.com/in-toto/in-toto-java/pull/16)
  and a minor [update](https://github.com/in-toto/in-toto-java/pull/19) to
  enable a new feature in the in-toto Jenkins plugin. Additionally, a
  third-party SaaS provider is working on a Java framework based on in-toto.

## ITE Proposals

As noted in the last two reviews, we've had three ITEs accepted as drafts in
the last year. ITE-2 and ITE-3, both authored by Trishank Karthik Kuppusamy
(@trishankatdatadog), describe how to use The Update Framework (TUF) and
in-toto. Santiago Torres-Arias sponsored ITE-4 which describes how to extend
in-toto's security guarantees to non-file software supply chain artifacts.
ITE-4 has been prototyped to provide in-toto's security properties in a more
granular manner for artifacts within Cloud Native Application Bundles' (CNAB)
metadata files. The in-toto team has also developed a trial GitHub prototype
which can generate in-toto attestations for GitHub operations.

With these three ITEs, we have successfully formalized all the ideas we
announced in our roadmap last year. We look forward to any feedback and more
use cases that will expand the impact of these ITEs.

- [ITE-2: Using TUF and in-toto to build compromise-resilient CI/CD](https://github.com/in-toto/ITE/pull/4)
- [ITE-3: Real-world example of combining TUF and in-toto for packaging Datadog Agent integrations](https://github.com/in-toto/ITE/pull/5)
- [ITE-4: Add generic URI schemes for artifacts in in-toto metadata](https://github.com/in-toto/ITE/pull/6)

## Tighter Spec Compliance

We have been chasing this goal by adding support for various features,
especially to do with artifact rule processing (see:
[in-toto#269](https://github.com/in-toto/in-toto/pull/269),
[in-toto#280](https://github.com/in-toto/in-toto/pull/280),
[in-toto-golang#35](https://github.com/in-toto/in-toto-golang/pull/35),
[in-toto-golang#40](https://github.com/in-toto/in-toto-golang/pull/40)) in the
reference implementation and in-toto-golang. Further, parameter substitution
was [ported over](https://github.com/in-toto/in-toto-golang/pull/38) to
in-toto-golang from the reference implementation.

Also, as noted earlier, work is ongoing to bring runlib to in-toto-golang,
which will bring the implementation closer to being fully featured and spec
compliant.

## Maturing of existing sub-projects and integrations

As noted in our roadmap last year, we intended to mature the sub-projects that
have sprouted, as well as beef up the in-toto integration in third-party
projects.

### Grafeas integration

Grafeas is an open source artifact metadata API developed by Google. Santiago
Torres-Arias (@SantiagoTorres) and Aditya Sirish (@adityasaky) worked with the
Grafeas team to
[integrate in-toto metadata](https://github.com/grafeas/grafeas/pull/391) as a
metadata type in Grafeas, bringing in-toto's security properties to Grafeas.

### Jenkins plugin

The official [in-toto Jenkins plugin](https://github.com/jenkinsci/in-toto-plugin)
saw some activity in the form of some bug fixes with how generated metadata were
written to a filesystem. But the bigger news with the plugin is the addition of
Grafeas as a first-party transport. Now, any in-toto attestations generated for
steps in a Jenkins pipeline can be directly stored on a Grafeas server.

### Kubernetes components

As noted in an earlier review, we worked on the
[in-toto kubectl plugin](https://github.com/in-toto/kubectl-in-toto), ensuring
that in-toto continued to work with a newer version of kubectl. Further, a new
user story combining Kubernetes, Grafeas, Jenkins (with the official plugin) was
evaluated, and a demo combining these is brewing.

### Kubesec integration

We worked with the amazing team at ControlPlane to bring
[in-toto signing to Kubesec scans](https://github.com/controlplaneio/kubesec/pull/75).
This improves the scanner ecosystem and also demonstrates the ease of
integrating in-toto's libraries to provide attestations --- the diff to add
in-toto to Kubesec was only about 50 lines.

### GPG support

We [moved in-toto's GPG support](https://github.com/secure-systems-lab/securesystemslib/pull/174)
to securesystemslib so that other SSL projects can benefit from it. Further, we
added support for key expiration export and verification (see
[#266](https://github.com/in-toto/in-toto/pull/266),
[#288](https://github.com/in-toto/in-toto/pull/288)). In addition, at the
request of an industry partner, we added ed25519 signing capabilities to the
submodule.

### Layout creation tools

in-toto currently provides a [web tool](https://github.com/in-toto/layout-web-tool)
to generate layouts. We are working on extending this tool with the capabilities
to generate layouts for existing software supply chains. To that end, we have a
team of summer interns who are joining us to work on this effort. We're very
excited to welcome Isha Dave (@IshaDave), Yuanrui Chen (@SolidifiedRay), and
Benjamin Wu (@itsbenwu) to the team, and we hope to have more to report on this
front in the coming months.

### Apt transport and rebuilders

We had a lot of movement in our apt transport and the integration with Debian
rebuilders! Here's a rundown of everything that has happened over the past
year:

- in-toto continues to work closely with the Reproducible Builds project. As a
  result, there are many mentions of in-toto on the website.

- securesystemslib and in-toto have both been accepted into the Debian
  repositories! You can find securesystemslib
  [here](https://tracker.debian.org/pkg/python-securesystemslib) and in-toto
  [here](https://tracker.debian.org/pkg/in-toto).

- We are working on
  [updating](https://github.com/in-toto/apt-transport-in-toto/pull/26)
  in-toto's apt transport to make it suitable for Debian packaging. You can
  follow this on the
  [official Debian bug tracker](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=934143).

- Lukas Pühringer (@lukpueh) attended the 
  [5th Reproducible Builds Summit](https://reproducible-builds.org/events/Marrakesh2019/)
  in Marrakesh. There was considerable interest in using in-toto as a means for
  verifying the results of various rebuilders. This event in particular spurred
  on the development of the apt transport, and its packaging for Debian.

- Santiago Torres-Arias is working on
  [adding in-toto attestations to rebuilderd](https://github.com/kpcyrd/rebuilderd/pull/22),
  an
  [independent verification system for binary packages](https://lists.reproducible-builds.org/pipermail/rb-general/2020-April/001905.html).
  This fleshes out the earlier discussions about using in-toto attestations as
  a verifiable format for results of rebuilders.
  
- Kristel Fung (@kristelfung), who originally joined us as a summer intern, has
  spent the last year working on making the rebuilder monitor more robust, and
  to use the newer buildinfos interface.

## Community Meetings

In an effort to interact directly with stakeholders, both to update them as
well as understand their needs and use cases, we have begun conducting regular
community meetings. This has helped grow the in-toto community which is also
good for software supply chain security as a whole. If you're interested in
joining the next community meeting, please subscribe to the
[in-toto mailing list](https://groups.google.com/forum/#!forum/in-toto-public).
You can also find notes
[[1](https://groups.google.com/forum/#!topic/in-toto-public/Bd3VF9hn1p4),
[2](https://groups.google.com/forum/#!topic/in-toto-public/AZwXzCiY24A)] on the
meetings held thus far in the archive.

## Closing Remarks

That brings us to the end of the in-toto roadmap for 2020. We have a robust
community that's working in many different projects and ecosystems to improve
software supply chain security. We have met our goals of formalizing an
approach to integrate TUF and in-toto to provide end-to-end guarantees, as well
as a way to extend in-toto's properties to supply chain artifacts beyond files,
through ITE-2, ITE-3, and ITE-4. We have also made progress towards achieving
spec compliance in our reference implementation and in making in-toto-golang
fully featured to enable its integration in cloud native / cloud first contexts.

We have also grown our integrations with the industry by adding in-toto
attestations to Grafeas and Kubesec. We believe this both improves the current
state of the software supply chain and demonstrates the ease of adding in-toto
attestations to a tool by making use of one of our many implementations.
