**Язык / Language:** [Русский](CONTRIBUTING.md) · **English**

[Profile](README_EN.md) · [Projects](PROJECTS_EN.md) · [Technical review](REVIEW_GUIDE_EN.md) · [Support](SUPPORT_EN.md)

# Propose a change or bug fix

This page helps prepare a reproducible contribution to a public repository listed on the profile. Each project has its own requirements: read its README, LICENSE (if present), CONTRIBUTING (if present), and open issues first. A pull request is not a promise of acceptance.

## Before coding

1. Search existing issues and PRs. For bugs, provide minimal reproduction steps, expected versus actual behavior, the version/commit, and environment.
2. For behavior-changing features, describe the outcome and acceptance check in an issue first to avoid unnecessary work.
3. Do not publish credentials, personal data, client files, private dumps, or unverified executables. Redact screenshots and logs.

## Make and verify the change

1. Work in a fork or separate branch and keep the patch focused on one problem.
2. Add or update a regression test when fixing a defect. Run the commands listed for that specific project, and clearly identify skipped, unavailable, or failing checks.
3. In your PR, explain **problem → change → how to verify → limitations**, link the issue, and include a redacted screenshot if useful.
4. Never bypass CI to obtain a green badge; a successful run for another commit does not validate yours.

**Start here:** [BizPilot](https://github.com/zeter1/BizPilot) · [ZeTer Photo Editor](https://github.com/zeter1/ZeTer-Photo-Editor) · [Screen Recorder Pro](https://github.com/zeter1/Screen-Recorder-Pro). For using the applications, see the [user guide](USER_GUIDE_EN.md); for reporting a problem, see [support](SUPPORT_EN.md).
