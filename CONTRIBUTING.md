# Contributing to in-toto

There are several areas or means to contribute to the development of in-toto.
They are:
* making code changes: these can be for feature additions or bug fixes to
  in-toto implementations
* submitting changes to specifications: these can be direct changes if they are
  trivial or as new in-toto Enhancements (ITEs)
* creating new integrations: in these cases, other projects are updated to
  generate or use in-toto metadata as appropriate, and these integrations are
  noted in [in-toto/friends](https://github.com/in-toto/friends)
* submitting issues, feature requests and more: these are typically
  implementation or sub-project specific, and can be submitted to the
  corresponding GitHub repositories

Any developer or user submitting these types of changes is considered an in-toto
contributor. Over time, as described in [in-toto's Governance](GOVERNANCE.md),
contributors may be promoted to maintainers of relevant implementations or
sub-projects.

## Contributor Workflow

A contributor can submit GitHub pull requests to the project's repositories.
They must follow the project's [code of
conduct](CODE-OF-CONDUCT.md), the [Developer Certificate of
Origin (DCO)](https://developercertificate.org/) and the [code style
guidelines](https://github.com/secure-systems-lab/code-style-guidelines), and
they must unit test any new software feature or change.  Submitted pull
requests undergo review and automated testing, including, but not limited to:

* Unit and build testing
* Static code analysis via linters
* Checks for *Signed-off-by* commits
* Review by one or more maintainers

The specifics of development practices for a sub-project or implementation are
detailed in their repositories. For implementations, this includes information
such as the name of the development branch and any additional checks pertaining
to that project. For ITEs, the process of submitting a new proposal is described
in ITE-1.

## How to Submit a Pull Request (PR)

1. **Fork the Repository**
   - Click the "Fork" button at the top right of the repository page on GitHub.

2. **Clone Your Fork**
   - Clone your fork to your local machine:
     ```sh
     git clone https://github.com/your-username/in-toto.git
     ```

3. **Create a New Branch**
   - Create a new branch for your changes:
     ```sh
     git checkout -b my-feature-branch
     ```

4. **Make Your Changes**
   - Make your changes in the code or documentation.

5. **Sign and Commit Your Changes**
   - Commit your changes with a descriptive message:
     ```sh
     git add .
     git commit -s -m "Description of my changes"
     ```

6. **Push Your Changes**
   - Push your changes to your forked repository:
     ```sh
     git push origin my-feature-branch
     ```

7. **Create a Pull Request**
   - Go to the original repository on GitHub and click "New Pull Request".
   - Select your branch and provide a detailed description of your changes.

## Finding Good First Issues

1. **Navigate to Issues**
   - Go to the [issues](https://github.com/in-toto/in-toto/issues?q=is%3Aissue+is%3Aopen+label%3A%22help+wanted%22) section of the repository on GitHub.

2. **Filter Issues**
   - Use labels like "good first issue" or "help wanted" to find issues suitable for beginners.

3. **Select an Issue**
   - Choose an issue that matches your skills and interests, and leave a comment expressing your intent to work on it.
