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

---

# Learning Document: Claude Code Workflows

## Topic: Attending the Claude Code workshop and learning different workflows for using skills and slash commands, Monologue 06-12-2025

### Key Learnings

#### 1. **Attending the Claude Code workshop and learning different workflows for using skills and slash commands, Monologue. I think today was a big day of learning the use of Monologue.**

---

# Learning Document: Claude Code Plugin Installation

## Topic: Installing Plugins for Claude Code 06-12-2025

### Key Learnings

#### 1. **Plugin Marketplace Management**
- Added custom marketplace using `/plugin marketplace add https://github.com/EveryInc/every-marketplace`
- Marketplaces extend available plugins beyond default options
- Successfully added every-marketplace for additional plugin sources

#### 2. **Plugin Installation Process**
- Installed compound-engineering plugin using `/plugin install compound-engineering`
- Plugin installation requires Claude Code restart to load new plugins
- Simple command-based installation workflow

---

# Learning Document: Arduino Puzzle Box Development

## Topic: Building a 4-Stage Arduino Puzzle Box and Understanding State Machines 08-12-2025

### Key Learnings

#### 1. **Hardware Connection and Debugging Fundamentals**
- Arduino Uno works via USB hub to MacBook Air as long as hub and cable support data transfer
- Debugging no-board-detected issue: verified cable was plugged into hub but NOT into the Uno itself
- macOS expects ports like /dev/cu.usbmodem… and requires Arduino AVR Boards + correct libraries installed

#### 2. **State Machine Architecture for Sequential Puzzles**
- Built ~200-line sketch as 4-stage state machine: LDR (red LEDs when dark) → Accelerometer shake (buzzer beep) → RFID tag (green LEDs) → Hall sensor + magnet (LED chase animation)
- Variables as state (stageone…stagefour) control sequence flow, not just individual sensor responses
- Each stage unlocks only after previous stage completes, creating linear puzzle progression

#### 3. **Debugging Helpers for State Visibility**
- Added printStage() helper function so Serial Monitor displays current stage in real-time
- Designed resetStages() helper to return puzzle to "Stage 0": resets all flags, RFID status, and LEDs
- Helper functions improve debugging experience and make code easier to inspect during development

#### 4. **Refactored Documentation for Educational Context**
- Rewrote technical explanation into 4 clear sections: what device does, code organization (pins/setup/loop), concepts illustrated (variables/state & iteration), and facilitator classroom instructions
- Framed documentation for both student understanding and facilitator teaching use
- Created Mermaid flowchart diagram showing hardware connections: power rails, Arduino pins, sensors (LDR, Hall), and outputs (LED strip, buzzer)

---

# Learning Document: Game Master Prompts for Skills Learning

## Topic: Using AI Game Master Prompts to Generate Learning Scenarios 12-12-2025

### Key Learnings

#### 1. **Game Master Prompts as Educational Tool**
- Created game master prompt that generates interactive scenarios for different skills
- Fun, engaging approach to learning technical and non-technical concepts
- Scenarios can be tailored to specific skills the learner wants to develop

#### 2. **Factual Verification Concerns for Technical Content**
- Key concern: ensuring accuracy of technical concepts taught through generated scenarios
- Game master prompts may prioritize engagement over factual precision
- Need verification mechanism for technical accuracy in educational content

#### 3. **Playtesting Methodology for Educational Tools**
- Distributed game master prompt scenarios to others for playtesting
- Playtesting helps validate both engagement and educational effectiveness
- User testing provides feedback on factual accuracy and learning outcomes

---

# Learning Document: Claude Code File Size Limitations and Python Web Protocols

## Topic: Working Around File Size Constraints and Encountering WSGI/ASGI 20-12-2025

### Key Learnings

#### 1. **File Size Limitations in Claude Code and Workaround Strategy**
- Encountered "file size too big" error when working with large files in Claude Code
- Successfully overcame limitation by delegating work to chatbot applications instead
- Demonstrates flexibility in toolchain - use appropriate tool for each constraint

#### 2. **WSGI vs ASGI Protocol Distinction (Learning in Progress)**
- Encountered different protocols (WSGI vs ASGI) in separate Python web project
- Currently don't fully understand the differences between these protocols
- Identified knowledge gap to explore further for web application development

---

# Learning Document: ESP32 Development Basics

## Topic: PIR Sensor Setup, WiFi Connection, and Device Debugging 20-12-2025

### Key Learnings

#### 1. **PIR Sensor Setup - Reading Digital Input from Motion Sensor**
- PIR (Passive Infrared) sensors detect motion by reading digital input signals
- ESP32 can read sensor state to trigger actions based on motion detection
- All project files follow naming convention: `esp32_*`

#### 2. **WiFi Connection - Getting ESP32 Online**
- ESP32 can connect to WiFi networks for IoT functionality
- Connection status can be checked and monitored programmatically
- Enables remote communication and cloud integration capabilities

#### 3. **Terminal Debugging - Device Identification**
- Use `ls /dev/cu.*` command to identify connected ESP32 devices on macOS
- Terminal-based debugging helps locate USB-connected microcontrollers
- Essential for verifying board connection before uploading code

---

# Learning Document: Claude Interface File Type Limitations

## Topic: PowerPoint File Handling and Hallucination Behavior 24-12-2025

### Key Learnings

#### 1. **Claude Cannot Read PowerPoint Files Despite Tool Availability**
- Claude interface claims to support various file types but cannot actually read .pptx files
- Read tool does not have native PowerPoint parsing capability
- Attempting to read .pptx files results in gibberish or parsing errors

#### 2. **Hallucination Risk When Working with Unsupported Formats**
- Claude may hallucinate content when asked about files it cannot properly read
- System does not properly reject or warn about incompatible file types
- Creates false confidence in ability to process PowerPoint content

#### 3. **Workaround: Alternative Approaches for PowerPoint Content**
- Convert .pptx to supported formats (PDF, images, or extracted text) before analysis
- Use external tools to extract content before providing to Claude
- Verify Claude's actual capability before trusting outputs on file types

---

# Learning Document: ChatGPT Mode Selection Strategy

## Topic: Choosing Between Thinking Mode and Instant Mode for Task Efficiency 29-12-2025

### Key Learnings

#### 1. **Thinking Mode Performance Issue for Transcription Tasks**
- ChatGPT thinking mode proved too slow for transcription work
- Processing time outweighed benefits for this specific task type
- Speed became bottleneck rather than quality improvement

#### 2. **Instant Mode as Better Alternative for Certain Tasks**
- Instant mode delivered better results for transcription despite less processing time
- Not all tasks benefit from extended reasoning - some require fast execution
- Task characteristics should drive mode selection, not default assumptions

#### 3. **Hybrid Workflow Pattern: Handover Memo Strategy**
- Used thinking mode to generate detailed handover memo for instant mode
- Thinking mode excels at strategic planning and context preparation
- Instant mode then executes based on clear instructions from handover memo
- Combines strengths of both modes: strategic planning + fast execution

---

---

# Learning Document: Compound Engineering Planning Process

## Topic: Planning Process and Skill Development for Project Knowledge Retention 01-01-2026

### Key Learnings

#### 1. **Compound Engineering Planning Methodology**
- Learned about the planning process used in compound engineering workflows
- Planning helps leverage and compound learnings across projects
- Systematic approach to capturing and reusing project knowledge

#### 2. **Skill Writing for Repeatable Knowledge**
- Created skills for project management workflows
- Wrote skills for feedback processes to enable repeated reference
- Skills serve as reusable knowledge artifacts for common patterns and ideas

#### 3. **Building Knowledge Systems for Long-term Value**
- Documentation through skills enables future reference without relearning
- Converting project learnings into structured formats compounds knowledge over time
- Investing time in skill creation pays dividends through reusability
