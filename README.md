# .github

The organization-wide defaults repository for SpringTree.

GitHub treats a **public** repository named `.github` as a special one: a
handful of files placed here are shown automatically in every other SpringTree
repository that does not provide its own copy. This repository holds those
defaults, plus a few documents that projects are expected to copy.

> This repository must stay **public**. GitHub ignores default community
> health files in a private `.github` repository, and the defaults silently
> stop applying — there is no warning.

## How the defaults work

The mechanism is **display only**. GitHub renders the file from here when a
repository has none of its own; it never copies anything into that
repository. Quoting the [GitHub documentation][docs]:

> they won't appear in the file browser or Git history of the individual
> repositories, and are not included in their clones, packages, or downloads

Two consequences that catch people out:

- **No tool ever sees these files.** A build, a linter or a package manager
  running inside another repository cannot read anything from here, because
  the file is not on disk there.
- **A local copy always wins.** Commit the same file to a project repository
  and that version is used instead. That is the supported way to deviate from
  an organization default.

## Which files are picked up

This list is fixed. A file that is not on it does nothing here, however
sensible it looks.

| File                                        | Purpose                                     |
| ------------------------------------------- | ------------------------------------------- |
| `CODE_OF_CONDUCT.md`                        | Code of conduct                             |
| `CONTRIBUTING.md`                           | Contribution guidelines                     |
| `DISCUSSION_TEMPLATE/`                      | Discussion category forms                   |
| `FUNDING.yml`                               | Sponsor button                              |
| `ISSUE_TEMPLATE/` and `config.yml`          | Issue templates and the chooser config      |
| `PULL_REQUEST_TEMPLATE/`, `pull_request_template.md` | Pull request template              |
| `SECURITY.md`                               | Security and disclosure policy              |
| `SUPPORT.md`                                | Where to get help                           |

Each may live in the repository root, in `docs/`, or in `.github/`.

## What is in this repository

| Path                             | Propagates? | Notes                                                      |
| -------------------------------- | ----------- | ---------------------------------------------------------- |
| `.github/CODEOWNERS`             | No          | Applies to this repository only. Assigns the security officers as reviewers for the two security documents. |
| `.github/pull_request_template.md` | Yes       | The default pull request template for every SpringTree repository. |
| `LICENSE.md`                     | No          | Proprietary notice, meant to be **copied** into a project repository. |
| `SECURITY-INTAKE.md`             | No          | ISMS security intake questionnaire, meant to be **copied** into a project repository at project start. |
| `SECURITY.md`                    | Yes         | The default security policy. Vulnerability reports go to <security@springtree.nl>. |

## What does not propagate, and what to use instead

`README.md`, `LICENSE`, `CODEOWNERS`, `.npmrc`, `bunfig.toml`, `tsconfig.json`,
lint configuration — none of these are inherited. GitHub is explicit that a
[license file in particular][docs] can never be a default, because the license
has to travel with the code when a project is cloned or packaged.

To share those across repositories, pick the mechanism that matches what you
need:

- **A template repository.** Files in a repository marked as a template are
  genuinely copied into each new repository created from it. Use this for
  tooling configuration and starter files. The trade-off is that it is a
  copy: later changes to the template do not reach repositories that already
  exist.
- **A reusable workflow.** A workflow committed to `.github/workflows/` in
  *this* repository can be called from any SpringTree repository as
  `SpringTree/.github/.github/workflows/<name>.yml@main`, and changes take
  effect immediately. This is the right home for shared CI, including
  registry setup that writes an `.npmrc` at run time.
- **A published package.** Shared configuration that a tool can extend
  (ESLint, TypeScript, Prettier) belongs in a versioned `@springtree/*`
  package, so repositories can adopt updates deliberately.

Never commit registry credentials. An `.npmrc` containing an `_authToken`
belongs in `~/.npmrc` locally and in Actions secrets in CI — this repository
is public.

## The organization profile page

The panel rendered at <https://github.com/SpringTree> comes from
`profile/README.md` in this repository. That file does not exist yet, so no
profile panel is shown. It is a separate mechanism from the defaults above.

[docs]: https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file

