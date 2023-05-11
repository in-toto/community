# ROADMAP review (End of August '19)

We've reached the end of the first evaluation period for our 2020 roadmap, and
we are due a review of our activities. Here's a rundown of what has happened in
the scope of the in-toto project's
[ROADMAP](ROADMAP.md) for this year.

## ITE

We've had two ITE's submitted describing how to use TUF and in-toto in a
reasonable way. Thanks @trishankatdatadog for spearheading this initiative!

- [ITE-2: Using TUF and in-toto to build compromise-resilient CI/CD](https://github.com/in-toto/ITE/pull/4)
- [ITE-3: Real-world example of combining TUF and in-toto for packaging Datadog Agent integrations](
https://github.com/in-toto/ITE/pull/5)


## Achieving tighter specification compliance

We have reviewed our implementations to achieve a better coverage of the
in-toto specification. Both the in-toto reference and the golang implementation
now provide fully compliant artifact rule processing (see
[in-toto#269](https://github.com/in-toto/in-toto/pull/269),
[in-toto#280](https://github.com/in-toto/in-toto/pull/280),
[in-toto-golang#35](https://github.com/in-toto/in-toto-golang/pull/35),
[in-toto-golang#40](https://github.com/in-toto/in-toto-golang/pull/40)).

We also ported support for the very useful feature of [parameter
substitution](https://github.com/in-toto/in-toto-golang/pull/38/files) from our
reference implementation to our golang implementation.


## Maturing of existing sub-projects

### Jenkins

Our jenkins implementation has mostly seen work on cosmetic changes, as well as
simplifying the build procedures. We expect the rest of the roadmap period to
take on the standard stream capturing features.

### Kubernetes components

The kubernetes admission controller saw mostly movement on the kubectl side,
which comprised of making it work with newer versions of kubectl. In addition,
we are working towards simplifying the codebase and achieving a better user
story.

### GPG support

We took on the task of having our GPG support be part of the bigger SSL
ecosystem. With the goal of helping TUF integrators benefit from our GPG
features, we transferred the corresponding subpackage from in-toto to
securesystemslib (see
[secure-systems-lab/securesystemslib#174](https://github.com/secure-systems-lab/securesystemslib/pull/174)).
We also extended its feature set by adding key expiration export and
verification (see [#266](https://github.com/in-toto/in-toto/pull/266),
[#288](https://github.com/in-toto/in-toto/pull/288)).

### Apt transport and rebuilders

Of all the subprojects, our in-toto apt transport and the Debian rebuilders
have seen the most movement. We have plenty of exciting news on this front:

- securesystemslib is in Debian! You can install python-securesystemslib on
  [testing](https://tracker.debian.org/pkg/python-securesystemslib) now. This
  is an important step towards fully integrating in-toto with Debian, which is
  on the way, as
- we have submitted an "Intent To Package" bug for in-toto (the library) and
  made the package available for review on
  [mentors.debian.net](https://mentors.debian.net/package/python-in-toto). You
  can follow its progress on the [Debian bug
  tracker](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=934142).
- A similar story follows the in-toto apt transport, which was also built and
  uploaded to
  [mentors](https://mentors.debian.net/package/apt-transport-in-toto), and can
  be followed on the [Debian bug
  tracker](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=934143).

But, how useful would it be to have an in-toto apt transport if there are no
rebuilders? This is why we pushed hard on the other side of the equation, that
is setting up trusted debian rebuilders:

- Morten Linderud (@foxboron) published a thesis aptly named ["Reproducible
  Builds: break a log, good things come in
  trees"](http://bora.uib.no/bitstream/handle/1956/20411/Morten-Linderud-masteroppgave-Finale2.pdf?sequence=1&isAllowed=y).
  It describes how future iterations of the rebuilder infrastructure could host
  in-toto metadata into an artifact transparency log, and how this metadata can
  be used to verify reproducibility of builds as well as providing granular
  artifact lineage information.
- Lukas (@lukpueh) gave a talk and live demo of the apt transport at
  MiniDebConf in Hamburg. The recording is [available on
  youtube](https://www.youtube.com/watch?v=hbHa4OFv7Qo).
- Santiago (@SantiagoTorres) spent some time talking with people in the
  industry to have more rebuilders out there, and published instructions to set
  up a [MS-hosted rebuilder with
  in-toto](https://lists.reproducible-builds.org/pipermail/rb-general/2019-August/001640.html).
  We are still in early stages, but having rebuilders from government,
  industry, and nonprofits would help to provide diverse ecosystems and thus
  increase the assurance provided by reproduced builds.
- A summer intern, Kristel Fung (@kristelfung), took on the ambitious task of
  making the rebuilder monitor more robust and to use the newer interface for
  buildinfos and include it into the rebuilder setup. You can have a sneak peek
  [here](https://github.com/kristelfung/debian-intoto-rebuilder). We're also
  thrilled to have Kristel join the team as a regular contributor!

You can take a closer look at how the reproducible builds project is working,
and how in-toto participates by looking at their recent monthly reports:

- [August](https://reproducible-builds.org/reports/2019-08/)
- [July](https://reproducible-builds.org/reports/2019-07/)
- [June](https://reproducible-builds.org/reports/2019-06/)

## Closing remarks.

This is it for this evaluation period. We are very excited about building a
thriving community of people from Academia, Open Source and Industry. Across
the whole in-toto project, we have almost doubled the amount of contributors
since this year. We have also seen more occasional committers, as well as
people looking for ways to contribute. We hope that from there we get more
regular contributors to help us secure the software supply chain as a whole.
