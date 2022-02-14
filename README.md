# test-releases-ci

Some example actions:

- [#2](https://github.com/yegorgunko/test-releases-ci/pulls/2) is example workflow of creating a PR against `develop` and using squash to merge | Results in complete ignore of the release tool. More info: [Squashed commits are ignored by semantic-release](https://semantic-release.gitbook.io/semantic-release/support/troubleshooting#squashed-commits-are-ignored-by-semantic-release).
- [#3](https://github.com/yegorgunko/test-releases-ci/pulls/3) is example workflow of creating PR against `develop` and merging it using rebase. | Results in linear history and no problems with release.
- [#4](https://github.com/yegorgunko/test-releases-ci/pulls/4) is example workflow of creating PR against `stage` and merging it using rebase. | Results in linear history and no problems with release. PR title is expectedly ignored. Do not create additional commits in PRs against `stage` not to handle the merging them back to `develop` later.
- At the point of 764f2368ba4ec8829a56e1e761d43d4098ec6c7b `develop` had wrong version for own branch. 9b9ca0a108aedd6a7806f5b31dc68974ee8e0685 created `feat` commit into `develop`. | Results in correct work of release: overwrites version as per config and to problems with GitHub release.
