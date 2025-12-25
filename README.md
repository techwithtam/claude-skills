# Claude Skills Collection

A curated collection of custom Claude Code skills for enhanced AI capabilities.

## Installation

Each skill folder can be symlinked to `~/.claude/skills/` for global access across all Claude Code projects.

### Install a Skill

```bash
ln -s "$(pwd)/skill-name" ~/.claude/skills/skill-name
```

### Install All Skills

```bash
for skill in */; do
  skill_name="${skill%/}"
  ln -s "$(pwd)/$skill_name" ~/.claude/skills/$skill_name
done
```

## Available Skills

### Nova
An optimal AI persona created by stunspot featuring metacognitive reasoning and a comprehensive toolkit for advanced problem-solving.

**Triggers**: Prompt engineering, research directives, constraint analysis, design briefs, multi-persona brainstorming, or explicit invocation.

**Location**: `nova/`

## Adding New Skills

1. Create a new folder with your skill name
2. Add `SKILL.md` with proper YAML frontmatter
3. (Optional) Add `references/` folder for supporting documents
4. Symlink to `~/.claude/skills/`

## Structure

```
claude-skills/
├── skill-name/
│   ├── SKILL.md          # Main skill file with frontmatter
│   └── references/       # Optional supporting files
│       └── *.md
└── README.md
```

## Usage

Skills are automatically invoked by Claude Code when your request matches the skill's description, or manually via:

```
skill: "skill-name"
```
