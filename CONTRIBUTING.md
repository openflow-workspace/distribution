# Contributing to Openflow

Contributions from people working with or without coding agents are welcome. Start with a small, reviewable change tied to a requirement and a clear outcome.

Openflow is in the requirements and architecture stage. There is no complete runtime, installation command, or universal test suite yet. Useful contributions include improving requirements, defining a standard business process, documenting compatibility evidence, designing connector contracts, and preparing synthetic fixtures.

## Read first

1. [README.md](README.md) for scope and current status.
2. [REQUIREMENTS.md](REQUIREMENTS.md) for requirement IDs and acceptance criteria.
3. [AGENTS.md](AGENTS.md) for coding-agent instructions and repository boundaries.
4. [Roadmap](docs/roadmap.md) for milestone sequencing.

Write documentation, comments, examples, issue descriptions, and PR descriptions in English. Preserve exact upstream identifiers, license text, and attribution. Do not translate third-party repositories.

## Find or propose a task

Browse [issues](https://github.com/openflow-workspace/distribution/issues) or open a focused proposal using an issue template. Include the user problem, relevant requirement IDs, expected outcome, and how it can be checked.

Small documentation corrections can go directly to a PR. For changes to the architecture, dependencies, public interfaces, role mappings, data contracts, or metric definitions, describe the proposal in an issue before investing in a large implementation. Explain any changed requirement in the same PR.

Good early tasks have a bounded result: document the compatibility of one pg_ducklake/PostgreSQL combination, define one connector's pagination and checkpoint behavior, or specify a Gold dataset's grain and metrics. Avoid a PR that attempts the entire enterprise suite at once.

## Create a contribution

Fork the repository into your GitHub account, then work on a branch:

```sh
git clone https://github.com/YOUR-USERNAME/distribution.git
cd distribution
git remote add upstream https://github.com/openflow-workspace/distribution.git
git switch -c docs/clarify-sales-metrics
```

Replace `YOUR-USERNAME` and the example branch name with your own. Keep this repository separate from downloaded upstream source trees. The local development collection may contain hundreds of independent repositories, which are deliberately excluded by `.gitignore`.

Keep one coherent problem per PR. Prefer supported configuration and extension mechanisms; avoid importing whole applications. New dependencies and core patches need an explanation of why existing mechanisms are insufficient.

## Working with a coding agent

Give the agent a bounded task, the relevant requirement IDs, expected behavior, and allowed scope. For example:

```text
Read README.md, REQUIREMENTS.md, CONTRIBUTING.md, and AGENTS.md.
Improve the specification for PP-001 sales and receivables.
Define invoice/payment grain, partial payment allocation, currencies,
cancellations, and synthetic examples with expected outstanding balances.
Change documentation only. Keep all content in English.
Check local Markdown links and report exactly what you validated.
Do not claim a connector or dashboard has been implemented.
```

Before submitting agent-assisted work:

- Read the complete diff yourself and verify factual claims against the appropriate upstream release.
- Remove unrelated edits, speculative APIs, secrets, and private company data.
- Confirm that acceptance criteria are meaningful and that tests exercise the behavior rather than merely repeat its implementation.
- Explain the validation actually performed. Agent output is not evidence that a test ran.
- Keep any generated code understandable and maintainable by someone who did not see the conversation.

Do not give agents production credentials to work on sample integrations. Use synthetic data and least-privileged development environments. Agents should not publish, contact maintainers, or change external systems unless the contributor's task authorizes those actions.

## Where work belongs

| Area | Intended location |
|---|---|
| Product scope and acceptance criteria | `REQUIREMENTS.md` |
| Architecture, compatibility findings, design decisions | `docs/` |
| Contributor and agent guidance | `CONTRIBUTING.md`, `AGENTS.md` |
| Deployment configuration and image recipes | Future implementation directories, introduced with their validation instructions |
| Standard process packages | Planned `processes/<process-id>/` layout |
| Changes to an upstream application | A focused upstream contribution or a justified dedicated downstream fork |

The process package layout is a target, not an existing runtime contract. A package should keep extraction DAGs, models, quality rules, synthetic fixtures, metric definitions, and Superset assets versioned together. Its README must identify supported sources and versions, the dataset grain, access assumptions, refresh behavior, and relevant checks.

## Validate your change

For documentation-only changes:

- Check relative links and referenced files.
- Check English language, requirement IDs, and consistency with current project status.
- Preview diagrams and tables where possible.
- Run `git diff --check` and review `git diff` and `git status` before committing.

For implementation changes, include setup and validation instructions in the relevant component or package. Run the checks applicable to your change. Do not copy a command from another project and claim it is supported here.

Data pipelines should demonstrate retry behavior, checkpoint recovery, schema/error handling, and expected fixture results. BI changes should reconcile to documented expected metrics, preserve stable asset identities, and test the relevant data-access rules. Deployment changes should validate rendering, version compatibility, upgrades, and recovery paths as applicable.

If a check could not run, say why. Do not describe a static review as an integration test. Do not claim SAP replacement, production readiness, security certification, or compatibility that has not been demonstrated.

## Open a pull request

Push your branch to your fork and open a PR targeting `main` in `openflow-workspace/distribution`. Use the PR template to state:

- The user problem and resulting behavior or documentation.
- Related issue and requirement IDs.
- Validation commands or review steps with results.
- Unrun checks, compatibility assumptions, and remaining limitations.

Maintainers may request a smaller scope, clearer acceptance criteria, or additional evidence. Keep the title and description aligned with the final change. A contributor is responsible for reviewing and submitting their work, including work produced with an agent.

## Attribution and licensing

Preserve upstream copyright, license, and NOTICE files. Do not apply one component's license to the entire suite. The license for new Openflow-owned work is an open project decision recorded in the requirements; do not invent a CLA, signing requirement, or license grant. Resolve the licensing policy with maintainers before importing third-party code or accepting substantive executable components.
