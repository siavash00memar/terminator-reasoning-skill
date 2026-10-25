# Security and responsible use

## What ships in this repository

The skill package currently contains Markdown instructions and references only. It bundles no executable code, dependencies, credentials, or telemetry. Its instructions may recommend browsing or using tools already available to the host AI client; the package itself does not provide, sandbox, or limit those capabilities.

## Review before installation

Skills are instructions an agent may follow. Before installing Terminator or any third-party skill:

1. Read `SKILL.md` and its referenced files.
2. Check the repository owner and source history.
3. Understand what the target client can access and which tools it may call.
4. Keep approval requirements in place for destructive, external, financial, or production-impacting actions.
5. Re-review updates before upgrading if you need pinned behavior.

Terminator's instructions do not outrank system policies, client safeguards, repository rules, or the user's authorization. Do not treat installation as proof that instructions are safe for every environment.

## Privacy

This repository does not collect data. When an agent uses a browser, shell, or connected tool, the handling of that data is governed by the client and service—not by this skill. Do not put secrets or private customer data into public issues or examples.

## Reporting a vulnerability

Do not publish exploit details or private data in a public issue. Use GitHub's private vulnerability reporting for this repository if it is enabled. Until it is enabled, contact the repository owner through a private channel before disclosing details publicly.
