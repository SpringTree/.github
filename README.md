# SpringTree organisation defaults

GitHub applies the files in this repository as defaults to every repository in
the SpringTree organisation that does not carry its own copy.

- `.github/pull_request_template.md` — the pull request template. It asks the
  three things our ISMS wants to know about every change: what and why, whether
  it was read and tested, and whether it touches the project's security intake.
  Rules behind it: the Secure-developmentstandaard (§5.2) and the procedure
  Informatiebeveiliging in projectmanagement in the
  [ISMS repository](https://github.com/SpringTree/isms).

A repository that needs to deviate adds its own `.github/pull_request_template.md`;
that one wins over this default. `CODEOWNERS` cannot be set here and stays per
repository.
