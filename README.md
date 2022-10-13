# test-releases-ci

### Current preferred flow (WIP):

- `develop` is set as default branch. Every new feature / fix / chore etc. should branch off the `develop` branch.
- After the feature is done on any branch it should be merged into develop. It is preferred not to use squash merge.
- When the set of features is ready to be deployed to stage, create a PR or a `release/...` branch. It should be branched off `develop` and use `stage` as target.
- Merge the release PR into `stage`.
- Release CI should run and update the version on `stage`.
- Merge the CI release commit back into `develop` (optional).

### Some example actions:

- [#2](https://github.com/yegorgunko/test-releases-ci/pull/2) is example workflow of creating a PR against `develop` and using squash to merge | Results in complete ignore of the release tool. More info: [Squashed commits are ignored by semantic-release](https://semantic-release.gitbook.io/semantic-release/support/troubleshooting#squashed-commits-are-ignored-by-semantic-release).
- [#3](https://github.com/yegorgunko/test-releases-ci/pull/3) is example workflow of creating PR against `develop` and merging it using rebase. | Results in linear history and no problems with release.
- [#4](https://github.com/yegorgunko/test-releases-ci/pull/4) is example workflow of creating PR against `stage` and merging it using rebase. | Results in linear history and no problems with release. PR title is expectedly ignored. Do not create additional commits in PRs against `stage` not to handle the merging them back to `develop` later.
- At the point of 764f2368ba4ec8829a56e1e761d43d4098ec6c7b `develop` had wrong version for own branch. 9b9ca0a108aedd6a7806f5b31dc68974ee8e0685 created `feat` commit into `develop`. | Results in correct work of release: overwrites version as per config and to problems with GitHub release.
