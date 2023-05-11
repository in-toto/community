# ROADMAP review (End of December '19)

We've reached the end of the first evaluation period for our 2020 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's
[ROADMAP](ROADMAP.md) for this year.

## Cross-implementation interoperability

- __in-toto-golang__ We implemented ed25519 signing, which is also available in
  the in-toto reference implementation, and thus allows for a more feature-rich
  cross-implementation interoperability.
  [[in-toto-golang#48](https://github.com/in-toto/in-toto-golang/pull/48)]
  Furthermore, we identified a small flaw in our Go implementation of the
  OLPC canonical json standard and provided a fix and corresponding testing.
  [[in-toto-golang#50](https://github.com/in-toto/in-toto-golang/pull/50)]

- __in-toto-java__
  While the in-toto Java implementation maintained by the Secure Systems Lab
  remained untouched in this evaluation period, we have been in contact with a
  SaaS-provider that is working on an Java framework based on in-toto. We hope
  to provide more details in the next roadmap evaluation.

## ITE

In the last roadmap review we showed the results from two ITE proposals that
provide recommendations about how to operate in-toto with TUF, namely ITE-2 and
ITE-3.
This time we proudly present ITE-4. It formalizes the second idea announced
via the roadmap, that is a way to represent artifacts other than files
in in-toto metadata. The work was mainly driven by one of the lab's master's
students, Aditya Sirish (@adityasaky), and proves our commitment to
integrating with the Software Package Data Exchange (SPDX) open standard. ITE-4
will allow in-toto to not only refer to artifacts as files, but rather as more
rich elements, such as SPDX elements, or CI actions (like GitHub's) and more!

- [ITE-2: Using TUF and in-toto to build compromise-resilient CI/CD](https://github.com/in-toto/ITE/pull/4)
- [ITE-3: Real-world example of combining TUF and in-toto for packaging DataDog Agent integrations](https://github.com/in-toto/ITE/pull/5)
- [ITE-4: Add generic URI schemes for artifacts in in-toto metadata](https://github.com/in-toto/ITE/pull/6)

## Maturing of existing sub-projects

### Jenkins

We have had very little activity on the Jenkins plug-in side, mostly because the
reduced feature set has had very little to update and/or fix. However, we are
brewing support for [Grafeas](https://github.com/grafeas/grafeas) as a
transport. This way, the in-toto Jenkins plug-in will be able to store in-toto
link metadata in a Grafeas server seamlessly. More to come on this front!

### Kubernetes components

As part of our work with the Grafeas adoption, we have had the chance to
evaluate a user story of the in-toto admission controller that uses Grafeas to
store link metadata (and possibly query other metadata as part of its
verification process). Although only sketches have come out so far, we are very
excited to show this to everybody once things come to fruition.

### GPG support

We started using securesystemlib's version of the gpg module. In addition, as
one of our industry partners requested, we gave the module support for
[ed25519](https://github.com/secure-systems-lab/securesystemslib/pull/188) keys
and signatures. As a result, everybody can benefit from a more feature-rich gpg
submodule.

### Apt transport and rebuilders

The apt transport and rebuilder saw a lot of work from senior and junior
members of the team.

- securesystemslib and in-toto have both been accepted into Debian testing and
  new downstream releases are constantly prepared. [[securesystemslib on
  Debian](https://tracker.debian.org/pkg/python-securesystemslib), [in-toto on
  Debian](https://tracker.debian.org/pkg/in-toto)]

- We are working hard on getting our in-toto apt transport into the Debian
  repository, and are fixing bugs on the go. This sub-project has seen new
  uplift in particular after Lukas attended the 5th reproducible builds summit
  in December, where there was much interest in the in-toto project.
  [[transport packaging
  update](https://github.com/in-toto/apt-transport-in-toto/pull/26), [5th
  Reproducible Builds
  summit](https://reproducible-builds.org/events/Marrakesh2019/)]

- Our continued collaboration with the Reproducible Builds community can be
  observed in various places on the Reproducible Builds website. [[involved
  projects](https://reproducible-builds.org/who/), [related
  publications](https://salsa.debian.org/reproducible-builds/reproducible-website/issues/22),
  [September report](https://reproducible-builds.org/reports/2019-09/),
  [October report](https://reproducible-builds.org/reports/2019-10/), [December
  report](https://reproducible-builds.org/reports/2019-12/)]

- Kristel Fung (@kristelfung) joined the team in a more-permanent fashion, and
  continued her work on making the rebuilder monitor more robust and to use the
  newer interface for buildinfos. We have continuously tested these changes on
  the rebuilder we host here at NYU. [[new rebuilder
  monitor](https://salsa.debian.org/reproducible-builds/debian-rebuilder-setup/merge_requests/2)]

### Kubesec integration

We managed to work with the amazing team at ControlPlane, in order to provide
the ability of signing your [kubesec scans using
in-toto](https://github.com/controlplaneio/kubesec/pull/75). We believe this is
a great step forward not only to improve the security of the scanner ecosystem
(by effectively generating signed http exchanges), but to set a precedent for
other scanner services that may want to integrate in-toto --- the total diff
was around 50 lines.

## Closing remarks.

This is it for this evaluation period. This period has mostly been centered
around showing people how to use in-toto in their ecosystem. As such, we've
moved greatly in the direction of a broader industry adoption. We believe that,
before the closing ROADMAP review, we'll have many surprises to share regarding
adoption, user stories and more.
