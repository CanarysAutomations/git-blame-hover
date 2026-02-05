# 📖 Git Blame Hover Tooltip Guide

## 🎯 Understanding the Tooltip Information

When you hover over any line of code, the Git Blame Hover extension displays a rich tooltip with comprehensive information about that specific line. Here's what each element means:

### 📁 **Header Section**
```
📁 ReleaseNotesController.cs - Line 109
```
- **File name**: The current file you're viewing
- **Line number**: The exact line number you're hovering over (1-indexed)

### 👤 **Author Information**
```
👤 Mohan BS
```
- **Author**: The person who last modified this specific line of code
- This is the Git commit author, not necessarily the file creator
- Helps you identify who to contact for questions about this code

### 📅 **Date Information**
```
📅 Date: 1 hour ago
```
- **Relative time**: Shows when the line was last modified in human-readable format
- Examples: "2 minutes ago", "3 days ago", "2 weeks ago", "6 months ago"
- **Configuration**: Can be changed to absolute dates in settings (`gitBlameHover.showRelativeTime`)

### 📝 **Commit Message**
```
📝 Message: Add GetByProduct action to filter release notes by product name and year
```
- **Context**: Explains WHY the change was made
- **Purpose**: Helps you understand the business logic or bug fix
- **Truncation**: Long messages are shortened (configurable via `gitBlameHover.maxCommitMessageLength`)

### #️⃣ **Commit Hash**
```
#️⃣ Commit: ad7a659
```
- **Short hash**: 7-character abbreviated commit identifier
- **Clickable**: Click to open the full commit in your browser (if enabled)
- **Copyable**: Use "Copy Hash" button to get the full commit hash

### 🌐 **Platform Detection**
```
🌐 Platform: Azure Repos
```
- **Git hosting service**: Automatically detected from your repository's remote URL
- **Supported platforms**: GitHub, GitLab, Bitbucket, Azure Repos, or "Local/Other"
- **Integration**: Enables direct links to commit pages

---

## 🛠️ Action Buttons Explained

The four buttons at the bottom provide powerful actions for deeper code investigation:

### 📋 **Copy Hash**
**Purpose**: Copies the full commit hash to your clipboard

**When to use**:
- Need to reference the commit in documentation
- Want to check out the specific commit: `git checkout <hash>`
- Need to create a Git command: `git show <hash>`
- Sharing commit reference with team members

**Result**: Copies something like `ad7a659123abc456def789012345678901234567`

---

### 📖 **Show Details**
**Purpose**: Displays comprehensive commit information in the Output panel

**What you'll see**:
```
Commit Details: ad7a659123abc456def789012345678901234567
==================================================

Author: Allen <allen@company.com>
Date: 2026-01-23 14:30:15 +0530
Message: Add GetByProduct action to filter release notes by product name and year

Files Changed (3):
  Controllers/ReleaseService.cs
  Services/NotesService.cs
  Models/ProductFilter.cs

Statistics: +47 -12 lines
```

**When to use**:
- Need to understand the full scope of the commit
- Want to see all files changed together
- Need to know the exact number of lines added/deleted
- Investigating a bug and need complete context

---

### 📜 **File History**
**Purpose**: Shows the complete Git log history for the current file

**What you'll see**:
```
File History for: Controllers/ReleaseNotesController.cs
====================================================

1. ad7a659 - Allen
   Date: 2026-01-23 14:30:15 +0530
   Message: Add GetByProduct action to filter release notes
   Files: 3 changed
   Changes: +47 -12 lines

2. c3b2a15 - Sarah Chen
   Date: 2026-01-20 09:15:22 +0530
   Message: Initial controller implementation
   Files: 1 changed
   Changes: +156 -0 lines
```

**When to use**:
- Understanding file evolution over time
- Finding when a feature was originally added
- Tracking who has worked on the file
- Investigating when bugs might have been introduced

---

### 📊 **Author Stats**
**Purpose**: Provides comprehensive contribution analysis for the current file

**What you'll see**:
```
Author Statistics for: Controllers/ReleaseNotesController.cs
==========================================================

📄 Current File State:
   File Age: 10/7/2025 to 1/23/2026

👥 Author Contributions (Historical Activity):
   Note: "Total Changes" includes ALL historical commits to this file,
   even content that may have been refactored or removed.

  📊 Allen:
     Historical Activity: 1 commits, 39 total line changes
     Detailed Changes: +39 additions, -0 deletions

  📊 Sarah Chen:
     Historical Activity: 1 commits, 14 total line changes
     Detailed Changes: +14 additions, -0 deletions

```

**Key Metrics Explained**:
- **Current Lines**: How many lines each author currently "owns" in the file
- **Commits**: Number of commits each author made to this file
- **Total Changes**: Cumulative lines added (+) and deleted (-) by each author
- **Hot Lines**: Lines modified in the last 30 days (active development areas)

**When to use**:
- Code reviews: Understanding who has expertise in different areas
- Team planning: Identifying code ownership and knowledge distribution
- Maintenance: Finding who to ask about specific functionality
- Performance reviews: Understanding individual contributions

---

## 💡 **Pro Tips for Maximum Productivity**

### 🔍 **Investigation Workflow**
1. **Start with tooltip** - Quick overview of the change
2. **Use "Show Details"** - Understand the full commit scope
3. **Check "Author Stats"** - Identify the expert for this file
4. **Review "File History"** - Understand the evolution timeline

### 🎯 **Common Use Cases**

**Debugging a Bug**:
1. Hover over problematic line → See when it was last changed
2. "Show Details" → Check if bug was introduced in that commit
3. "File History" → Look for recent changes that might be related

**Code Review Preparation**:
1. "Author Stats" → Understand who has context for different areas
2. "File History" → See recent activity and change patterns
3. Hover over modified lines → Understand the reasoning behind changes

**Learning New Codebase**:
1. "Author Stats" → Identify subject matter experts
2. "File History" → Understand how the file evolved
3. Hover over complex sections → Read commit messages for context

### ⚙️ **Customization Options**
Access these via VS Code Settings (`Ctrl+,`) → Search "Git Blame Hover":

- **Show/Hide Elements**: Toggle author, date, message, commit ID, platform
- **Time Format**: Relative ("2 hours ago") vs Absolute ("Jan 23, 2026 2:30 PM")
- **Message Length**: Truncate long commit messages
- **Hover Delay**: Adjust how quickly tooltips appear
- **Clickable Commits**: Enable/disable browser links for commits

### 🔗 **Platform Integration**
When commits are clickable, you can:
- **GitHub**: Direct link to commit page with diff view
- **GitLab**: Navigate to commit with merge request context
- **Azure Repos**: View commit in Azure DevOps with work item links
- **Bitbucket**: Access commit page with pull request information