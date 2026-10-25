# Contributing

Contributions should make the workflow more useful, clearer, safer, or easier to verify—not merely longer or more skeptical.

## Report a behavior problem

Include, when safe to share:

- The exact prompt and relevant non-sensitive context.
- The client and model, if known.
- What the agent did and what you expected it to do.
- Which criterion in [`docs/evaluation.md`](docs/evaluation.md) was missed.
- A minimal fix or a concrete counterexample, if you have one.

Remove API keys, personal data, proprietary source code, and private tool output. For security reports, follow [`SECURITY.md`](SECURITY.md), not a public issue.

## Propose a change

1. State the observed failure mechanism or user need.
2. Make the smallest instruction or documentation change that addresses it.
3. Run the relevant scenario and at least one adjacent scenario from the evaluation set.
4. Report what you ran and what changed; do not claim broader gains from a small sample.
5. Keep `SKILL.md` focused. Put detailed domain material in `references/` and link to it directly.

## Documentation conventions

- English is the primary version; keep `README.fa.md` aligned when changing user-facing claims or installation steps.
- Prefer primary platform documentation for client-specific instructions.
- Date claims that can go stale.
- Separate compatibility with the file format from tested runtime behavior.
- Avoid unmeasured claims such as guaranteed accuracy, eliminated bias, or time saved.

## Pull request checklist

- [ ] The change serves an identified user need or fixes a reproducible failure.
- [ ] The Agent Skills frontmatter remains valid and the `terminator` name matches its install folder.
- [ ] Referenced files exist and are linked from the skill root.
- [ ] Relevant evaluation scenarios were rerun; results are described accurately.
- [ ] The change does not add executable code, network behavior, or permissions without explicit justification and security review.
- [ ] English and Persian documentation are consistent where applicable.
