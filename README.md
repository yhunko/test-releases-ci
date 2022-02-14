# test-releases-ci

Some example actions:

- [#2](https://github.com/yegorgunko/test-releases-ci/pulls/2) is example workflow of creating a PR against `develop` and using squash to merge | Results in complete ignore of the release tool. More info: [Squashed commits are ignored by semantic-release](https://semantic-release.gitbook.io/semantic-release/support/troubleshooting#squashed-commits-are-ignored-by-semantic-release).
- [#3](https://github.com/yegorgunko/test-releases-ci/pulls/3) is example workflow of creating PR against `develop` and merging it using rebase. | Results in linear history and no problems with release.
- [#4](https://github.com/yegorgunko/test-releases-ci/pulls/4) is example workflow of creating PR against `stage` and merging it using rebase. | Results in linear history and no problems with release. PR title is expectedly ignored. Do not create additional commits in PRs against `stage` not to handle the merging them back to `develop` later.
