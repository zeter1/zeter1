# Profile repository

The `zeter1/zeter1` repository supplies the GitHub profile README and navigation for application users and technical reviewers. It has no application runtime, package manifest, build or test runner.

## Owners

- `README.md` / `README_EN.md`: profile entrypoints, quick task selection, technical project summary and contacts.
- `USER_GUIDE.md` / `USER_GUIDE_EN.md`: choosing applications, release downloads, startup routes and user support.
- `PROJECTS.md` / `PROJECTS_EN.md`: technical project map.
- `REVIEW_GUIDE.md` / `REVIEW_GUIDE_EN.md`: technical review route and code/check entrypoints.
- `ENGINEERING.md` / `ENGINEERING_EN.md`: engineering practices and examples.
- `SUPPORT.md` / `SUPPORT_EN.md`: bug-report guidance.
- `CHANGELOG.md`: accepted documentation changes from the start of tracking.

Application source, prerequisites, release status, testing and licenses remain owned by their respective repositories. Refer to those owners rather than creating a second setup manual here.

## Verification

Use `git diff --check` to check patch formatting. Review relative file links against the candidate files, and external repository paths against the target Git tree. Review GitHub's rendered Markdown after publication. A release asset listing proves availability, not runtime correctness or that external tools are bundled.

No program is started when editing this repository. Browser application behavior, Windows executables, devices, media output and source-project CI are separate checks and are not established by profile documentation validation.
