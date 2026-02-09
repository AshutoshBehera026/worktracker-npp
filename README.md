# WorkTracker - Notepad++ Daily Work Tracker

A speed-optimized syntax highlighting system for tracking daily tasks, notes, and progress in Notepad++. Designed for developers and professionals who want a fast, keyboard-friendly way to manage their daily work without leaving their text editor.

## Features

-   **Lightning-fast typing** - Single character markers for quick note-taking
-   **Visual priority system** - Color-coded tasks by urgency and status
-   **Logger-style keywords** - Familiar TODO, FIXME, NOTE syntax
-   **5 beautiful themes** - One Dark, Nord, Dracula, Gruvbox, Tokyo Night
-   **Zero dependencies** - Just Notepad++ and these XML files

---

## Installation

### Step 1: Choose Your Theme

Pick a theme that matches your Notepad++ global theme:

-   `WorkTracker-OneDark.xml` - Clean, modern (matches Atom One Dark)
-   `WorkTracker-Nord.xml` - Calm, muted (easy on eyes)
-   `WorkTracker-Dracula.xml` - Vibrant, high contrast
-   `WorkTracker-Gruvbox.xml` - Warm, retro feel
-   `WorkTracker-TokyoNight.xml` - Modern, anime-inspired

### Step 2: Import the UDL

1. Open Notepad++
2. Go to **Language → User Defined Language → Define your language...**
3. Click the **Import** button
4. Select your chosen XML file
5. Restart Notepad++

### Step 3: Start Using

Create a file with one of these extensions:

-   `.wtk` - Work Tracker
-   `.track` - Track
-   `.todo` - Todo

The syntax highlighting will activate automatically!

---

## Syntax Guide

### Task Structure

```
# Main Task Name !!!
  - Subtask 1 +
  - Subtask 2 >
  - Subtask 3 x
  TODO Add password reset flow
  **Remember to check with **@alice****
  ~Cancelled or deprecated item~

```

code block here

```

```

### Priority Markers (for task headers)

Use these at the **end** of your `#` task headers:

| Marker | Meaning         | Color                         | Usage                        |
| ------ | --------------- | ----------------------------- | ---------------------------- |
| `!!!`  | Critical/Urgent | Red text + Dark red bg (Bold) | `# Deploy to production !!!` |
| `!!`   | High Priority   | Orange text + Dark orange bg  | `# Code review !!`           |
| `!`    | Medium Priority | Yellow                        | `# Update docs !`            |
| (none) | Low/Normal      | Default                       | `# Refactor utils`           |

**Note:** `#` headers get a full-line cyan background for easy scanning!

### Status Markers (for subtasks)

Use these at the **end** of your `-` subtasks:

| Marker | Meaning        | Color   | Usage                   |
| ------ | -------------- | ------- | ----------------------- |
| `+`    | Done/Completed | Green   | `- Write tests +`       |
| `>`    | In Progress    | Cyan    | `- Implement feature >` |
| `x`    | Blocked/Stuck  | Yellow  | `- Deploy script x`     |
| (none) | Not Started    | Default | `- Review PR`           |

### Logger Keywords (at start of line)

These work like programming log levels - type them at the **beginning** of a line:

#### Critical (Red, Bold)

-   `TODO` - Things to do
-   `FIXME` - Needs fixing urgently
-   `DEADLINE` - Time-sensitive items
-   `!!!` - Triple exclamation for extreme urgency

#### High Priority (Orange)

-   `WARN` - Warnings or cautions
-   `REVIEW` - Needs review
-   `HACK` - Temporary workaround
-   `!!` - Double exclamation

#### Medium Priority (Yellow)

-   `NOTE` - General notes
-   `INFO` - Information
-   `MEETING` - Meeting notes
-   `!` - Single exclamation

#### Informational (Cyan)

-   `QUESTION` - Questions to resolve
-   `IDEA` - Future ideas
-   `DEBUG` - Debug information

#### Improvement (Green)

-   `OPTIMIZE` - Performance improvements
-   `TEST` - Testing related
-   `BUG` - Bug tracking
-   `REFACTOR` - Code refactoring

### Special Markers

| Marker           | Purpose                                 | Example                              |
| ---------------- | --------------------------------------- | ------------------------------------ |
| `#`              | Task header (full-line cyan background) | `# Implement feature`                |
| `-`              | Subtask                                 | `- Write unit tests`                 |
| `**text**`       | Personal reminder/emphasis              | `** Check with **@john** **`         |
| `@name`          | Mention person (use with \*\*)          | `**@alice**` for highlighted mention |
| `~text~`         | Strikethrough/cancelled                 | `~Old approach~`                     |
| ` ``` text ``` ` | Code block                              | ` ``` function() {} ``` `            |

---

## Quick Start Examples

### Daily Work Log

```
# 2025-01-07 Work Log

# Authentication System !!!
  - Implement JWT tokens ~
  - Write unit tests
  - Update documentation x
  TODO Add password reset flow
  FIXME Token expiry too short
  >> Working on token refresh mechanism
  ** Remember to update API docs @john

# Database Migration !!
  - Backup production DB +
  - Test migration locally ~
  - Schedule maintenance window
  WARN This will take 2+ hours
  NOTE Using PostgreSQL 15.2

# Code Reviews
  - Review PR #245 +
  - Review PR #248
  QUESTION Should we merge before release?
```

### Bug Tracking

```
# Bug Fixes - Sprint 12

# Critical Bugs !!!
  - Login timeout issue +
  - Payment processing error >
  FIXME Memory leak in dashboard

```

// Temporary fix - needs refactor
clearInterval(timer);

```

# Minor Bugs !
- UI alignment on mobile
- Tooltip positioning
BUG Export CSV button not working
~Duplicate entry validation~ (Won't fix)
```

### Meeting Notes

```
# Team Standup - 2025-01-07

# Alice
  - Completed user profile feature +
  - Working on notifications >
  BLOCKED Waiting for API key from backend
  **Follow up with **@bob** on API access**

# Bob
  - Code review done +
  - Starting authentication module
  TODO Need to discuss architecture with team

# Charlie
  - Database optimization >
  - Performance testing x
  WARN Server resources running low
  **Follow up on cloud billing**
```

### Project Planning

```
# Q1 2025 Projects

# Mobile App Launch !!!
  - Design mockups +
  - Backend API >
  - iOS development
  - Android development
  DEADLINE March 15, 2025
  REVIEW Weekly check-ins with product team
  **Coordinate with **@sarah** on design assets**

# Website Redesign !!
  - User research +
  - Wireframes >
  - Component library
  IDEA Consider dark mode support
  NOTE Targeting mid-February launch

# Internal Tools !
  - Admin dashboard
  - Reporting system
  OPTIMIZE Can reuse existing components
```

---

## Tips & Best Practices

### Speed Typing Workflow

1. **Write first, mark later**: Type your tasks quickly, then add status markers

    ```
    - Implement feature
    - Write tests
    - Deploy
    ```

    Then update:

    ```
    - Implement feature +
    - Write tests >
    - Deploy
    ```

2. **Use consistent daily structure**: Start each day with the same format

    ```
    # 2025-01-07 Work Log

    # High Priority !!!
    # Today's Tasks
    # Follow-ups
    # Notes
    ```

3. **Leverage logger keywords**: Use them like you would in code

    ```
    TODO Implement error handling
    FIXME Memory leak in loop
    NOTE API rate limit is 100/hour
    ```

4. **Use code blocks for snippets**: Wrap code in triple backticks

    ```
    ` `` `
    function example() {
      return true;
    }
    ` `` `
    ```

5. **Highlight important mentions**: Use `**@name**` to make mentions stand out

    ```
    **Check deployment with **@alice** before 3pm**
    ```

6. **Group related tasks**: Use `#` headers to organize by project/category

    ```
    # Frontend Work
      - Component A
      - Component B

    # Backend Work
      - API endpoint
      - Database schema
    ```

### Organization Strategies

**By Priority:**

```
# Critical !!!
# High Priority !!
# Medium Priority !
# Low Priority
```

**By Project:**

```
# Project Alpha !!
# Project Beta !
# Maintenance Tasks
```

**By Time:**

```
# Morning Tasks
# Afternoon Tasks
# End of Day
```

**By Status:**

```
# In Progress ~
# Blocked x
# Completed Today +
```

### Keyboard Shortcuts

Make Notepad++ even faster:

-   `Ctrl + D` - Duplicate line (repeat tasks)
-   `Ctrl + L` - Delete line (remove completed tasks)
-   `Ctrl + Shift + Up/Down` - Move lines (reorder priorities)
-   `Alt + Shift + Arrow` - Column selection (bulk edit status markers)

### File Organization

Create a folder structure:

```
work-tracker/
├── 2025-01-07.wtk
├── 2025-01-08.wtk
├── projects/
│   ├── project-alpha.wtk
│   └── project-beta.wtk
└── archive/
    └── 2024-12.wtk
```

Or use a single rolling file:

```
daily-log.wtk (keep current week)
```

---

## Customization

### Adding Your Own Keywords

You can modify the XML to add custom keywords:

1. Open the XML file in a text editor
2. Find the `<Keywords name="Keywords5">` section
3. Add your custom words (space-separated)
4. Reimport the UDL

Example:

```xml
<Keywords name="Keywords5">OPTIMIZE TEST BUG REFACTOR DEPLOY HOTFIX</Keywords>
```

### Changing Colors

Each `<WordsStyle>` tag controls colors:

```xml
<WordsStyle name="KEYWORDS1" fgColor="E06C75" bgColor="282C34" fontStyle="1" />
```

-   `fgColor` - Text color (hex without #)
-   `bgColor` - Background color
-   `fontStyle` - 0=Normal, 1=Bold, 2=Italic, 3=Bold+Italic

### Adding File Extensions

In the XML header:

```xml
<UserLang name="WorkTracker-OneDark" ext="wtk track todo log notes">
```

Add more extensions separated by spaces.

---

## Troubleshooting

### Syntax highlighting not working

-   Check that your file has the correct extension (`.wtk`, `.track`, `.todo`)
-   Restart Notepad++ after importing
-   Verify the UDL is active: Language menu should show "WorkTracker-[Theme]"

### Keywords not highlighting

-   Keywords are **case-insensitive** (TODO = todo)
-   Logger keywords need whitespace before them (start of line)
-   Status markers work anywhere in the line

### Colors look wrong

-   Make sure you imported the UDL that matches your Notepad++ global theme
-   Check Settings → Style Configurator for theme compatibility

### Strikethrough not working

-   Notepad++ may need additional configuration for strikethrough
-   As a workaround, use `~text~` visually to indicate cancelled items

---

## Philosophy

This system is designed around these principles:

1. **Speed First**: Every marker is 1-2 characters. No typing `[URGENT]` when `!!!` works.

2. **Visual Hierarchy**: Your eyes should immediately see what's critical (red), what's done (green), and what's in progress (blue).

3. **Familiar Patterns**: Uses conventions from programming (TODO, FIXME) and project management (+, ~, x).

4. **Distraction-Free**: Works in a simple text editor. No databases, no sync, no cloud. Just you and your notes.

5. **Flexible**: No enforced structure. Use what works for you. Ignore what doesn't.

---

## Comparison with Other Systems

### vs TODO apps (Todoist, TickTick, etc.)

-   ✅ Faster typing (no mouse, no UI)
-   ✅ Works offline always
-   ✅ Plain text = portable forever
-   ✅ Code blocks for technical notes
-   ❌ No reminders or mobile sync

### vs Markdown TODO lists

-   ✅ Prettier syntax highlighting
-   ✅ Faster status markers (`>` vs `- [ ]`)
-   ✅ Visual priority system with backgrounds
-   ✅ Logger keywords (TODO, FIXME, etc.)
-   ✅ Full-line header highlighting
-   ✅ Code block support
-   ➖ Still readable as plain text

### vs Project management tools (Jira, Asana)

-   ✅ Instant, no loading
-   ✅ Personal, private notes
-   ✅ No context switching
-   ✅ Perfect for technical documentation
-   ❌ Not for team collaboration

---

## Contributing

Have ideas for improvements? Suggestions:

-   Additional logger keywords
-   New status markers
-   Different color schemes
-   Folding support
-   Date/time highlighting

Feel free to modify the XML files to suit your workflow!

---

## License

These UDL files are provided as-is for personal and commercial use. Modify and share freely.

---

## Credits

-   Theme colors from: Dracula, Nord, Gruvbox, One Dark, Tokyo Night projects
-   Syntax inspired by developer log patterns and project management workflows
-   Built for Notepad++ User Defined Language system

---

## Version

**v1.0** - January 2025

-   Initial release with 5 themes
-   Speed-optimized syntax
-   Logger keyword support
-   Status and priority markers

---

**Happy tracking! 🚀**

_For questions or issues, refer to the Notepad++ UDL documentation or community forums._
