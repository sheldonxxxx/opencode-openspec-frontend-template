# OpenSpec Frontend Template

A template for spec-driven frontend development using OpenSpec and AI-powered coding tools.

## Overview

This template integrates OpenSpec with AI coding assistants to ensure alignment between humans and AI on what to build before any code is written. It includes pre-configured skills for:

- **OpenSpec**: Spec-driven development methodology
- **OpenCode**: AI coding agent with LSP support
- **UI/UX Pro Max**: UI/UX development CLI with design guidelines
- **Vercel Agent Skills**: React, Next.js, and web design best practices

## Installation

### Required Tools

Install all tools globally:

```bash
# OpenSpec - Spec-driven development framework
npm install -g @fission-ai/openspec@latest

# OpenCode - AI coding agent
npm install -g opencode-ai@latest
# Or use the quick install script:
curl -fsSL https://opencode.ai/install | bash

# UI/UX Pro Max - UI/UX development CLI
npm install -g uipro-cli

# Vercel Agent Skills - AI agent capabilities for React, Next.js, web design
npx add-skill vercel-labs/agent-skills

# Agent broswer
npm install -g agent-browser
agent-browser install  # Download Chromium
```

### Project Setup

```bash
# Install project dependencies
npm install

# Initialize OpenSpec (if needed)
openspec init
```

## Usage

### OpenSpec Workflow

1. **Start a new change:**
   ```bash
   # Create a proposal for new features
   openspec list  # View active changes
   openspec validate <change-id> --strict --no-interactive
   ```

2. **Development with OpenCode:**
   ```bash
   # Start interactive AI coding session
   opencode

   # Run single prompt
   opencode run "Explain this codebase structure"

   # Use specific agent
   opencode run --agent code-reviewer "Review the latest changes"
   ```

3. **UI/UX Development:**
   ```bash
   # Initialize UI/UX Pro CLI
   uipro init --ai claude

   # Generate UI components
   uipro generate --component button
   ```

### AI Skills

Skills are automatically available once installed. Trigger them with natural language:

- **Web Design Guidelines**: "Review my UI", "Check accessibility", "Audit design"
- **React/Next.js Best Practices**: "Review this component for performance", "Optimize this page"
- **UI/Pro CLI**: "Create a responsive navigation", "Design a card component"

## Project Structure

```
openspec/
├── project.md              # Project conventions and context
├── specs/                  # Current truth - implemented capabilities
│   └── [capability]/
│       ├── spec.md         # Requirements and scenarios
│       └── design.md       # Technical patterns
├── changes/                # Proposed changes
│   ├── [change-name]/
│   │   ├── proposal.md     # Why and what changes
│   │   ├── tasks.md        # Implementation checklist
│   │   └── specs/          # Delta specifications
│   └── archive/            # Completed changes

.opencode/
├── package.json            # OpenCode plugin dependencies
└── skills/                 # AI agent skills
    ├── web-design-guidelines/
    ├── vercel-react-best-practices/
    └── [custom-skills]/
```

## Update Guide

### Updating OpenSpec

```bash
# Update to latest version
npm install -g @fission-ai/openspec@latest

# Verify installation
openspec --version

# Update project instructions
openspec update
```

### Updating OpenCode

```bash
# Update to latest version
npm install -g opencode-ai@latest

# Or use built-in upgrade
opencode upgrade

# Verify installation
opencode --version
```

### Updating UI/Pro CLI

```bash
# Update to latest version
npm install -g uipro-cli@latest

# Verify installation
uipro --version
```

### Updating Agent Skills

```bash
# Reinstall skills to get latest versions
npx add-skill vercel-labs/agent-skills

# Or manually update skill directories
cp -r skills/{skill-name} ~/.claude/skills/
```

### Updating Project Dependencies

```bash
# Check for outdated dependencies
npm outdated

# Update all dependencies
npm update

# Install latest compatible versions
npm install
```

## Configuration

### OpenSpec Configuration

Edit `openspec/project.md` to define:
- Project purpose and goals
- Tech stack and conventions
- Code style and architecture patterns
- Testing strategy and git workflow

### OpenCode Configuration

OpenCode uses provider-agnostic architecture. Configure providers via:
```bash
opencode auth login anthropic  # Authenticate with Anthropic
opencode auth login openai     # Authenticate with OpenAI
```

### UI/Pro CLI Configuration

Configure in `uipro.config.json`:
```json
{
  "theme": "default",
  "ai": "claude",
  "offline": false
}
```

## Best Practices

1. **Always use proposals for new features** - Ensure alignment before coding
2. **Validate changes before sharing** - Run `openspec validate --strict`
3. **Use AI skills appropriately** - Match tasks to relevant skills
4. **Keep skills updated** - Reinstall periodically for latest guidelines
5. **Document decisions** - Use design.md for architectural choices

## Troubleshooting

### OpenSpec Issues
```bash
# Reset OpenSpec configuration
openspec init --force

# Validate project structure
openspec validate --strict
```

### OpenCode Issues
```bash
# Check available models
opencode models

# Reset authentication
opencode auth logout
opencode auth login <provider>
```

### UI/Pro CLI Issues
```bash
# Reinstall with offline mode
uipro init --ai claude --offline

# Clear cache
rm -rf ~/.uipro/cache
```

## Resources

- [OpenSpec Documentation](https://fission-ai.github.io/openspec/)
- [OpenCode Documentation](https://opencode.ai/docs)
- [UI/Pro CLI Documentation](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)
- [Vercel Agent Skills](https://github.com/vercel-labs/agent-skills)
