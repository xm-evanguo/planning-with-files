# Codex IDE Support

## Overview

The canonical Codex-ready skill lives at `skills/planning-with-files`.

Install it either:
- in your personal skills at `~/.codex/skills/planning-with-files`
- in a repo-local `.codex/skills/planning-with-files` folder so teammates can use it too

## Installation

Codex discovers skills from repo-local `.codex/skills/` directories and from your personal `~/.codex/skills/` directory.

### Method 1: Workspace Installation (Recommended)

Share the skill with your entire team by adding it to your repository:

```bash
# In your project repository
git clone https://github.com/OthmanAdi/planning-with-files.git /tmp/planning-with-files

# Copy the skill into your repo-local Codex skills directory
mkdir -p .codex/skills
cp -R /tmp/planning-with-files/skills/planning-with-files .codex/skills/

# Commit to share with team
git add .codex/skills/planning-with-files
git commit -m "Add planning-with-files Codex skill"
git push

# Clean up
rm -rf /tmp/planning-with-files
```

Teammates using Codex will now discover the skill from the repo.

### Method 2: Personal Installation

Install it just for yourself:

```bash
# Clone the repo
git clone https://github.com/OthmanAdi/planning-with-files.git /tmp/planning-with-files

# Copy to your personal Codex skills folder
mkdir -p ~/.codex/skills
cp -R /tmp/planning-with-files/skills/planning-with-files ~/.codex/skills/

# Clean up
rm -rf /tmp/planning-with-files
```

## Usage

Codex can pick the skill automatically when the task matches its description, or you can mention `$planning-with-files` explicitly.

Codex does not use Claude-style hook metadata from older skills, so follow the workflow in `SKILL.md` directly:
- create or refresh `task_plan.md`, `findings.md`, and `progress.md`
- re-read `task_plan.md` before major decisions
- update the files after each phase
- run `scripts/check-complete.sh` when you want a quick completion summary

If you want a standing reminder, add a note like this to `~/AGENTS.md`:

```markdown
## Planning With Files

For complex multi-step work, use $planning-with-files and keep `task_plan.md`,
`findings.md`, and `progress.md` updated in the project directory.
```

## Verification

```bash
ls -la ~/.codex/skills/planning-with-files/SKILL.md
ls -la ~/.codex/skills/planning-with-files/agents/openai.yaml
```

## Learn More

- [Installation Guide](installation.md)
- [Quick Start](quickstart.md)
- [Workflow Diagram](workflow.md)
