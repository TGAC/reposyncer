# Sync any number of GitHub repo mirrors regularly

A simple GitHub workflow to regularly sync multiple repository mirrors (i.e. identical forks).

Note that the workflow uses a simple `git push` (i.e. it does NOT force push) to the mirror.
This means that if commits were force-pushed to the upstream repository branch which would overwrite existing commits in the mirror, the sync job for this repo will fail and the mirror will need to be synced manually.
This is on purpose, and we recommend not force-pushing to the main branch of your repository.

If you'd like to have your repository mirrored on the [Earlham Institute GitHub organisation](https://github.com/TGAC),
please:
1. Fork this repository.
2. Modify the `.github/workflows/sync.yaml` file by adding a new job configuration to the matrix of the `repo-sync` job
as in [these lines](https://github.com/TGAC/reposyncer/blob/main/.github/workflows/sync.yaml#L13-L15).
3. Open a pull request.
