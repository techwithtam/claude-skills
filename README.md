# Claude Skills Collection

A curated collection of custom Claude skills for enhanced AI capabilities across Claude Code and Claude Desktop.

## Installation

### For Claude Desktop

1. Download the pre-packaged `.zip` file from the [`releases/`](./releases) folder
2. In Claude Desktop, click the skill upload button
3. Select the downloaded `.zip` file

**Available Downloads:**
- [nova.zip](./releases/nova.zip) - Nova AI persona skill

### For Claude Code

#### Install Single Skill

```bash
# Clone the repo
git clone https://github.com/techwithtam/claude-skills
cd claude-skills

# Symlink the skill
ln -s "$(pwd)/nova" ~/.claude/skills/nova
```

#### Install All Skills

```bash
git clone https://github.com/techwithtam/claude-skills
cd claude-skills

for skill in */; do
  skill_name="${skill%/}"
  if [ -d "$skill_name" ] && [ "$skill_name" != "releases" ]; then
    ln -s "$(pwd)/$skill_name" ~/.claude/skills/$skill_name
  fi
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

## Repository Structure

```
claude-skills/
├── skill-name/
│   ├── SKILL.md          # Main skill file with frontmatter
│   └── references/       # Optional supporting files
│       └── *.md
├── releases/             # Pre-packaged .zip files for Claude Desktop
│   └── skill-name.zip
└── README.md
```

## Usage

Skills are automatically invoked by Claude Code when your request matches the skill's description, or manually via:

```
skill: "skill-name"
```
