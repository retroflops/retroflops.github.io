# retroflops.github.io

This repository publishes <https://retroflops.github.io/>. It contains the
deployment workflow, not the site source. The site itself lives in
[retroflops/retroflops](https://github.com/retroflops/retroflops), along with
the code, catalog, issues and data corrections.

GitHub serves an organization site at the root of its domain only from the
repository named for that domain. `actions/deploy-pages` also deploys only to
the Pages site for the repository that runs it. For that reason,
`.github/workflows/publish.yml` checks out the source repository, builds it,
and deploys the artifact. This repository never stores generated files.

The source repository keeps the canonical workflow at
`.github/pages-repository/publish.yml`, where reviewers can see it beside the
code it builds. It is copied here. Each run compares the copies and stops if
they differ.

## Publishing

A push to `main` in the source repository dispatches a run here with the commit
that passed CI. You can also start a run from the Actions tab. Its `commit`
input accepts a branch, tag, or SHA.
