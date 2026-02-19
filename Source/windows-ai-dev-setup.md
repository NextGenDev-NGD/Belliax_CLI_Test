# AI Dev Environment Setup — Windows + WSL

## Prerequisites

- Windows 10/11, 8GB+ RAM, admin access
- WSL2 installed with Ubuntu (recommended)
- Create accounts: [Anthropic](https://console.anthropic.com), [Google](https://accounts.google.com), [GitHub](https://github.com)

## 1. Install Core Tools

Open **PowerShell as Administrator**:

```powershell
# Git Bash (required for Claude Code on Windows side)
winget install Git.Git
```

All remaining tools are installed inside WSL (Ubuntu). Open your WSL terminal:

```bash
# Node.js (required for Claude Code & Gemini CLI)
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## 2. Install AI CLI Tools (via WSL)

All agents launch from WSL to keep your environment unified.

### Claude Code
```bash
npm install -g @anthropic-ai/claude-code
```

### Gemini CLI
```bash
npm install -g @google/gemini-cli
```

## 3. Configure API Keys (WSL)

Add to your WSL shell profile (`~/.bashrc`):

```bash
echo 'export ANTHROPIC_API_KEY="your-key"' >> ~/.bashrc
echo 'export GEMINI_API_KEY="your-key"' >> ~/.bashrc
source ~/.bashrc
```

## 4. Install IntelliJ IDEA + AI Plugin

```powershell
winget install JetBrains.IntelliJIDEA.Community
```

**Install GitHub Copilot (free tier):**
1. File → Settings → Plugins → Marketplace
2. Search "GitHub Copilot" → Install → Restart
3. Sign in with GitHub account

## 5. Verify Installation

```bash
claude --version && gemini --version
```

## Quick Reference

| Tool | Command | Get API Key |
|------|---------|-------------|
| Claude Code | `claude` | console.anthropic.com |
| Gemini CLI | `gemini` | aistudio.google.com/apikey |

## Troubleshooting

- **"command not found"**: Add `$HOME/.local/bin` to PATH or re-run `source ~/.bashrc`
- **Claude issues**: Run `claude doctor`
- **Copilot not working**: Check sign-in status in IDE status bar
- **WSL node not found**: Confirm `node -v` works after the nodesource install
