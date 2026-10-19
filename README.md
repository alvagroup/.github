# .github

Organization default files for `alvagroup`. GitHub uses a file here for every
repository in the organization that has no file of its own with the same name.

This repository holds one file: `.github/pull_request_template.md`, the PR
template for every alvagroup repository. **This is the only copy: change it
here, by pull request.** A repository that adds its own
`.github/pull_request_template.md` replaces it entirely, so add one only for a
deliberate override (`reporting-agent` has one). `scaffold/` and
`alva-repo-template` ship no copy (`alvagroup/internal-tools#373`).

Agents write PR bodies from a file, which ignores templates. They read the one
that applies to a repository with:

```bash
gh api graphql -f query='{repository(owner:"alvagroup",name:"<repo>"){pullRequestTemplates{body}}}'
```

Every file added here becomes a default for every repository, so each one
needs its own issue in `alvagroup/internal-tools`. This repository is public
because GitHub requires it; it holds no code, no workflows (Actions is
disabled), and nothing internal. Changes need a pull request reviewed by
`@alvagroup/it-admins` (CODEOWNERS and the `governance-default-branch`
ruleset). See `alvagroup/internal-tools#364` and `#373`.
