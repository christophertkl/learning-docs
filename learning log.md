# Learning Document: macOS Reminders CLI Integration

## Topic: Building a CLI Tool to Interface with macOS Reminders 23-11-2025

### Key Learnings

#### 1. **Claude Code Can Interface with macOS Reminders via Simple Script**
- macOS Reminders app is scriptable using AppleScript wrapped in bash scripts
- You can add reminders from terminal without opening the GUI
- Simple command: `osascript -e 'tell application "Reminders"...'`

#### 2. **AppleScript Date Format Quirks**
- ISO format (YYYY-MM-DD) doesn't work - AppleScript misparses it completely
- European format (DD/MM/YYYY) works correctly
- Always test date parsing - created test script to verify different formats

#### 3. **User-Friendly CLI Design**
- Accept standard input format (YYYY-MM-DD) for ease of use
- Convert internally to system-required format (DD/MM/YYYY)
- Use `date -j -f "%Y-%m-%d" "$INPUT" "+%d/%m/%Y"` for conversion

#### 4. **GitHub CLI Workflow**
- Installed `gh` via Homebrew, authenticated with device flow
- Created and pushed repo in one command: `gh repo create --public --source=. --push`
- Use `gh auth setup-git` to configure git authentication

#### 5. **Testing Prevented Production Issues**
- Built test script to verify date formats before deployment
- Discovered date parsing bug through testing
- Testing saved time by catching issue early

---

# Learning Document: arXiv Notifier Automation

## Topic: Setting Up Automated arXiv Paper Notifications 23-11-2025

### Key Learnings

#### 1. **Preference for Simple Automations Without Exposing Credentials**
- Local file-based automation (cron + file writing) preferred over email/API services
- No need to store Gmail app passwords or expose credentials in config files
- macOS native notifications (`osascript`) provide clean, secure notification method

#### 2. **Token Usage Awareness is Important**
- Need to be mindful about using too many tokens during conversations
- Efficient tool usage and focused tasks help minimize token consumption
- Balance between thoroughness and efficiency in exploration/implementation

#### 3. **Dated File Outputs for Historical Records**
- Adding dates to filenames (`daily_report_2025-11-23.md`) creates automatic history
- Better than overwriting single file - preserves all previous reports
- Format: `YYYY-MM-DD` for proper sorting and clarity

---

# Learning Document: Automating Workflows with Claude Code

## Topic: Automating Personal Actions and YouTube Transcript API Discovery 23-11-2025 22:02

### Key Learnings

#### 1. **Automating Personal Actions Through Claude Code**
- Claude Code can write custom automation scripts for repetitive tasks
- Created arXiv notifier with cron job for daily paper notifications
- Preference for simple, local automations that don't expose credentials

#### 2. **YouTube Transcript API Still Works with Updates**
- YouTube transcript API remains functional and accessible
- API has been updated from previous versions
- Still viable option for extracting video transcripts programmatically

---

# Learning Document: Custom Slash Commands

## Topic: Manually Writing Slash Commands 23-11-2025

### Key Learnings

#### 1. **Learnt how to manually write a slash command**
- Slash commands can be created manually in the `.claude/commands/` directory
- Commands are markdown files that define custom prompts for Claude Code
- Enables quick reuse of common workflows and automations

---

# Learning Document: Strategic Project Planning

## Topic: Being More Strategic About Project Selection and Impact 24-11-2025

### Key Learnings

#### 1. **Need to Be More Strategic for Actions Taken**
- Important to think through how to reap the benefits of projects undertaken
- Spending more time on strategic planning upfront can maximize project value
- The outstanding contribution award demonstrates how much colleagues have been supported by my work

---

# Learning Document: Claude Skills

## Topic: Manual creation of Claude Skills, and thinking though how they can be applied 25-11-2025

### Key Learnings

#### 1. **Manual creation of Claude Skills, and thinking though how they can be applied**

---

# Learning Document: JavaScript Console Snippets for Web Scraping

## Topic: Building Reusable Console Snippets for Authenticated Content Extraction 30-11-2025

### Key Learnings

#### 1. **Built JavaScript Console Snippet to Extract YouTube Videos from AJAX-loaded Course Content Behind Authentication**
- Developed console snippet to extract YouTube video links from course content requiring authentication
- Pattern: detect sections dynamically from DOM → loop with FormData POST → regex extract from JSON response → summarize results
- Key insight: generalize by scraping section IDs/names from page instead of hardcoding, making snippet work across all course modules

#### 2. **Output Design for Manual Workflow Control**
- Clean console logs with module context and progress indicators
- Summary output showing total videos found and extraction status
- No auto-copy functionality - designed for manual workflow control and user review

#### 3. **Created Reusable Template for LLMs**
- Placeholder table structure for different extraction scenarios
- Common extraction patterns documented: YouTube, PDF, email, images
- Adaptation checklist to help LLMs customize snippets for different sites
- Integration: packaged as Raycast snippet with keyword trigger for fast paste-into-console workflow
