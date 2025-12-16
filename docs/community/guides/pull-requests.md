# Pull Requests


The process and requirements we describe below serve as important guardrails
that are essential to running an Open Source project and help us prevent wasted
effort and ensure the integrity of the codebase. This is more important than 
ever as the number of attacks on Open Source projects by malicious actors and 
the amount of AI slop both increase.

## Before you start

Before you start work on a pull request (PR), we need you to open an issue and
discuss it with us so we know what you are working on and so we can agree on the
approach to take. This prevents you from spending time on a feature that may not
align with the project's goals. You then reference the issue number in your PR
to link back to our discussion.

## Styles and linting

It is important that your edits produce clean commits that can be reviewed
quickly and without distractions caused by spurious diffs caused by format
changes that conflict with the style we use. The projects use the following
styling and linting tools and you must make sure that you follow the configured
styles and rules:

| Language   | Tool                | Notes                        |
| :--------- | :------------------ | :--------------------------- |
| Rust       | [rustfmt]           | Code formatting              |
| Rust       | [clippy]            | Linting                      |
| Python     | [ruff]              | Linting and code formatting  |
| Python     | [mypy]              | Type checking                |
| Typescript | [typescript-eslint] | Linting                      |

  [rustfmt]: https://rust-lang.github.io/rustfmt
  [clippy]: https://doc.rust-lang.org/stable/clippy/usage.html
  [ruff]: https://docs.astral.sh/ruff/
  [mypy]: https://www.mypy-lang.org/
  [typescript-eslint]: https://typescript-eslint.io/

In addition, we use an [editorconfig] file that configures compatible editors to
behave the same way for tasks like removing trailing whitespace or applying
indentation styles. Please check if your editor honors editorconfig settings [by
default] or [requires a plugin]. If you also add plugins for the style checkers
and linters then this should help to make sure that the diffs in your commits
are minimal and focused on the intended changes.

  [editorconfig]: https://editorconfig.org/
  [by default]: https://editorconfig.org/#pre-installed
  [requires a plugin]: https://editorconfig.org/#download
  
## Verified commits

To ensure the integrity of our projects, we require [verified commits] that are  cryptographically signed. For this to work, you need to install the _public_ key of a keypair into your GitHub account. Follw the instructions on GitHub for using [gpg], [ssh], [s/mime] keypairs.

  [verified commits]: https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification
  [gpg]: https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification#gpg-commit-signature-verification
  [ssh]: https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification#ssh-commit-signature-verification
  [s/mime]: https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification#smime-commit-signature-verification

## Developer certificate of origin

To ensure the legal integrity of our project, we require all contributors to
_sign off_ on their commits, thus accepting the Developer Certificate of Origin.
This certifies that you have the right to submit the code under the project's
license.

You must add a Signed-off-by line to every commit message. You can do this
automatically by adding the `--signoff` flag to the commit command:

```
git commit –signoff -m "
<type>: <summary description>

[issue number]
```

At the moment, you need to use your GitHub username. To configure this for the
repository you are working on:

```
git config user.name "Your GitHub username here"
git config user.email your@email.example
```

**email also necessary? Just when will these requirements change? **


## Use of AI

AI-assisted coding can be useful but the unreflected inclusion of AI-generated
code can also do great harm. By signing off on commits, you attest that you have
either written all the code yourself or have thoroughly reviewed and fully
understood any generated code. 

Code contributions that contain obviously AI-generated code that you cannot
fully explain to us will be rejected. We must ensure, after all, that the
contribution does not contain bugs or malicious code, and that we can commit to
maintaining it in the future.

## Commit Message Standards

We follow the [Conventional Commits] specification, except that our tooling
automatically calculates the scope of changes, so a scope is not permitted. This
helps us automate our release notes and versioning. Each commit message must
follow this structure:

  [Conventional Commits]: https://www.conventionalcommits.org/

```
<type>: <summary description>

[issue number]

[sign-off]
```

Note that we require PRs to be [linked to an issue] that has been discussed with
us. We also [require sign-off] with every commit of the [Developer Certificate
of Origin].

  [linked to an issue]: #before-you-start
  [require sign-off]: #developer-certificate-of-origin  
  [Developer Certificate of Origin]: https://developercertificate.org

Please note that commit messages of commits accepted into the master branch are
published in our [changelog] when we release new versions. To ensure consistent
formatting, we automatically check commit messages in our CI setup. The commit
types we support are listed in the table below. The CI job checks that:

  [changelog]: https://github.com/zensical/zensical/releases

* An accepted commit type is used.
* The summary line does not contain additional whitespace: preceding, trailing,
  between type and colon, or double whitespace between the colon and the commit
  summary.
* The commit summary starts with lowercase and does not end with punctuation (it
  is not a full sentence).
* The commit summary must not contain an issue reference. The issue reference
  belongs in the box instead.

| Type          | Description                                     |
| :------------ | :---------------------------------------------- |
| `feature`     | Implements a new feature.                       |
| `fix`         | Fixes a bug.                                    |
| `performance` | Improves performance.                           |
| `refactor`    | Improves code without changing behavior.        |
| `build`       |                                                 |
| `docs`        | Adds or improves documentation.                 |
| `style`       |                                                 |
| `test`        | Adds or improves tests.                         |
| chore         | Updates build process, prepares releases, etc.  |
