# Installation guide

The commands below install the public repository at `https://github.com/siavash00memar/terminator-reasoning-skill`.

## Recommended: install with Skills CLI

The open Skills CLI installs this GitHub repository into all supported agents or a selected set. It requires Node.js 22.20 or later. To install Terminator globally for all supported agents, run:

```sh
npx skills add siavash00memar/terminator-reasoning-skill --skill terminator --global --agent '*'
```

The wildcard targets every agent currently supported by Skills CLI, including Codex, Claude Code, Cursor, and Gemini CLI. To target selected agents instead, use their CLI identifiers, for example `--agent codex claude-code cursor`. To install only in the current project, omit `--global`. To update a global skill installed through Skills CLI:

```sh
npx skills update terminator --global
```

This update command manages Skills CLI installations. For a manual Git clone, use the Git update command below. See the official [supported agents list](https://github.com/vercel-labs/skills/blob/main/docs/agents.md) and [Skills CLI reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md) for current identifiers and options. Agent support and behavior can differ by product.

Terminator follows the open Agent Skills folder format. Client support for that format does not mean every feature, trigger, approval flow, or command behaves the same in every product. Use the platform-specific path below and consult its current docs when a client changes.

## Before you install

1. Review `SKILL.md` and whichever reference is relevant: `references/frameworks.md` or `references/review-recipes.md`.
2. Confirm the skill name is `terminator` and the install directory is also named `terminator`.
3. Use a project-level location when you only want the workflow in one repository. Use a user-level path for all projects.
4. Do not use Gemini CLI's `--consent` option unless you deliberately want to skip its install confirmation.

The bundle contains Markdown files only. It has no `scripts/`, package manager, API key, or runtime setup.

## Manual installation (second method)

Use these commands if you prefer a plain Git checkout or do not use Skills CLI.

### Codex

Codex discovers user skills under `~/.agents/skills/` and project skills under `.agents/skills/`.

**macOS / Linux, user-level:**

```bash
git clone https://github.com/siavash00memar/terminator-reasoning-skill.git \
  "$HOME/.agents/skills/terminator"
```

**Windows PowerShell, user-level:**

```powershell
git clone https://github.com/siavash00memar/terminator-reasoning-skill.git `
  "$HOME\.agents\skills\terminator"
```

For a project, replace the destination with `<project>/.agents/skills/terminator`. Start a new Codex session if it does not appear. Invoke with `$terminator`, or describe a matching task and allow automatic selection.

Codex also supports skill uploads in some ChatGPT/hosted experiences. Those upload flows and availability vary by product surface and account. For API use, see [OpenAI's Skills documentation](https://developers.openai.com/api/docs/guides/tools-skills): the skill folder can be supplied from a controlled local runtime, or packaged as a ZIP where that API surface supports uploads.

### Claude Code

Claude Code supports user-level skills in `~/.claude/skills/` and project skills in `.claude/skills/`.

```bash
git clone https://github.com/siavash00memar/terminator-reasoning-skill.git \
  "$HOME/.claude/skills/terminator"
```

For a project, use `<project>/.claude/skills/terminator`. Invoke it with `/terminator`, or describe a task that matches the skill. Claude Code's installation path is separate from Codex's; installing to `~/.agents/skills/` alone is not a documented Claude Code path.

### Gemini CLI (native alternative)

Gemini CLI documents direct installation from a Git repository:

```bash
gemini skills install https://github.com/siavash00memar/terminator-reasoning-skill.git --scope user
```

Use `--scope workspace` for a project-level install. The command asks for install consent by default. In an interactive session, inspect with:

```text
/skills list
```

If the skill was just installed, refresh with `/skills reload`. For workspace-scoped skills, ensure the project is trusted. The CLI also supports `--path` when the skill is in a subdirectory of a larger repository; this repository keeps `SKILL.md` at its root, so `--path` is unnecessary.

To remove it:

```bash
gemini skills uninstall terminator --scope user
```

### Cursor

Cursor discovers skills from `~/.agents/skills/` globally and `.agents/skills/` in a project. It also supports `~/.cursor/skills/` and `.cursor/skills/`.

The Codex clone command above installs into Cursor's documented shared `~/.agents/skills/` location. Project-level use works from `<project>/.agents/skills/terminator`. You can invoke it with `/terminator` in Agent chat or let the agent select it from the description.

Cursor Cloud Agents do not automatically inherit every local-only skill. For Cloud Agents or team distribution, add the project-level skill to the repository or use Cursor's supported sync/marketplace flow. See the official [Cursor skills docs](https://cursor.com/docs/skills).

## Other compatible agents

For an agent that supports the Agent Skills standard, install the folder in the path its documentation specifies. Preserve this structure:

```text
terminator/
├── SKILL.md
└── references/
    ├── frameworks.md
    └── review-recipes.md
```

An agent that only supports static system prompts, not Agent Skills folders, cannot install this package unchanged. You can adapt the instructions manually, but that is a different integration and may lose on-demand reference loading.

## Updating a manual Git checkout

Run this from any folder:

```bash
git -C "$HOME/.agents/skills/terminator" pull
```

Change the path to the actual install location. Pin a release tag rather than tracking the default branch when stable, repeatable behavior is important.

## Removing a manual clone

Remove only the `terminator` folder at the install location you chose. Do not delete the parent `.agents/skills` or `.claude/skills` directory; it may contain other skills.

## Official references

Checked 26 October 2026:

- [Codex skill locations and use](https://learn.chatgpt.com/docs/build-skills)
- [Claude Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview)
- [Gemini CLI Agent Skills](https://geminicli.com/docs/cli/skills/)
- [Cursor Agent Skills](https://cursor.com/docs/skills)
- [OpenAI API Skills](https://developers.openai.com/api/docs/guides/tools-skills)
- [Agent Skills specification](https://agentskills.io/specification)
- [Skills CLI installation and update commands](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)
