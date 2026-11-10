# Contribution Workflow

## 1. How does CyberChef use issues?

CyberChef uses GitHub Issues to discuss bugs, feature requests, and possible improvements. Labels such as `bug`, `feature`, and `help wanted` make these easier to sort through.

Before starting a change, I would check whether someone has already reported the problem or is working on it. That would also help me understand what the maintainers expect.

[CyberChef issues](https://github.com/gchq/CyberChef/issues)

## 2. How do pull requests work?

Contributors use pull requests to propose changes. Maintainers can review the code, discuss the approach, and request adjustments before accepting it.

CyberChef's PR template asks for a description, related issues, and test coverage. Contributors must also disclose any AI tools used to create the code and understand what they submit.

[Pull request template](https://github.com/gchq/CyberChef/blob/master/.github/pull_request_template.md)

## 3. A recent pull request: #2925

### What changed?

PR #2925 was opened by Dependabot and updated 13 dependencies. It changed `package.json` and `package-lock.json`.

Some examples are:

| Package | Previous version | Updated version |
| --- | --- | --- |
| node-forge | 1.4.1 | 1.4.2 |
| moment-timezone | 0.6.4 | 0.6.6 |
| protobufjs | 8.8.0 | 8.8.1 |
| @codemirror/view | 6.43.13 | 6.43.15 |

The package file records the dependency requirements, while the lockfile records the resolved versions used during installation.

[PR #2925](https://github.com/gchq/CyberChef/pull/2925)

[Changed files](https://github.com/gchq/CyberChef/pull/2925/files)

### Why does it matter?

My takeaway is that maintaining a project also means looking after the libraries it relies on. CyberChef depends on packages for cryptography, data processing, editing, and development tooling.

These updates are less visible than a new operation, but they are still part of keeping the project maintained. A version bump alone does not prove that a particular vulnerability was fixed; that would need separate verification.

### Is it open or merged?

The PR was **merged on 4 November 2026**. Its status was verified on **10 November 2026**.

[Merge status](https://github.com/gchq/CyberChef/pull/2925)

## 4. What would I like to contribute?

One idea I would like to explore is clearer error messages for beginners. If an operation cannot process some input, an explanation of the expected format could make it easier to understand what went wrong.

I would first identify a specific confusing case and check the existing issues before proposing a change.

Another option would be adding a regression test for a confirmed bug. That would help catch the same problem if it returned later.

These are future contribution ideas, rather than changes I have already implemented.

## 5. How would I contribute?

I would fork CyberChef, create a separate branch, make a focused change, and add relevant tests. After running the appropriate checks, I would push the branch and open a pull request.

The project also requires the GCHQ Contributor Licence Agreement. Its guide specifically rejects PRs made from a fork's `master` branch, so using a separate branch matters.

[Contribution guide](https://github.com/gchq/CyberChef/blob/master/CONTRIBUTING.md)

## 6. Adding an operation later

CyberChef provides `npm run newop` to help create an operation file. The operation must also be registered in `src/core/config/Categories.json` and given suitable test coverage.

This would give me a starting point if I decide to add an operation later.

[Adding a new operation](https://github.com/gchq/CyberChef/wiki/Adding-a-new-operation)
