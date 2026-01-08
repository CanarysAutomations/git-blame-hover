# Git Blame (On hover)

> 🚀 **Instant git blame information on hover - lightweight, zero-config, with smart tooltips**

## 🎯 **What Makes This Different?**

Unlike other git blame extensions that clutter your status bar or add inline annotations, **Git Blame Hover** provides blame information exactly when and where you need it - **on hover**.

| **Git Blame Hover** ✨ | **Other Extensions** 😑 |
|------------------------|-------------------------|
| 🎯 **Hover-based** - Info appears only when needed | 📊 Status bar clutter - Always visible |
| 🚫 **Zero UI clutter** - No persistent visual elements | 📝 Inline annotations - Text everywhere |
| ⚡ **Performance optimized** - Smart caching & debouncing | 🐌 Continuous processing - CPU intensive |
| 🎨 **Smart tooltips** - Rich formatting with emojis | 📋 Plain text - Basic information |
| ⚙️ **Fully configurable** - Show exactly what you want | 🔒 Fixed format - Limited customization |

## ✨ **Key Features**

### 🎯 **Hover-First Design**
- **Non-intrusive**: Information appears only when you hover over a line
- **Context-aware**: Shows relevant details exactly where your cursor is
- **Clean workspace**: No permanent UI elements cluttering your editor

### ⚡ **Performance Optimized**
- **Smart debouncing**: Prevents excessive git calls during rapid mouse movement
- **Intelligent caching**: Reuses blame data for better performance
- **Cancellation support**: Respects VS Code's cancellation tokens

### 🎨 **Rich Tooltips**
- **Visual formatting**: Uses emojis and markdown for better readability
- **Relative time**: Shows "2 hours ago" instead of cryptic timestamps
- **Platform detection**: Identifies GitHub, GitLab, Bitbucket, Azure Repos
- **Error handling**: Clear, user-friendly error messages

### ⚙️ **Highly Configurable**
- **Selective display**: Choose exactly what information to show
- **Custom formatting**: Control tooltip appearance and content
- **Performance tuning**: Adjust hover delays and message lengths
- **Quick toggle**: Enable/disable with status bar button

## 🚀 **Getting Started**

### **Installation**
1. Open VS Code
2. Go to Extensions (`Ctrl+Shift+X`)
3. Search for "Git Blame Hover"
4. Click Install

### **Usage**
1. **Open any file** in a git repository
2. **Hover over any line** of code
3. **See instant blame info** in a beautiful tooltip!

That's it! No configuration required. 🎉

## 📸 **Screenshots**

### **Hover Tooltip in Action**
```
When you hover over line 42:

┌─────────────────────────────────────────┐
│ 👤 Author: John Doe                     │
│ 📅 Date: 2 hours ago                    │
│ 📝 Message: Fix authentication bug      │
│ #️⃣ Commit: a1b2c3d                      │
│ 🌐 Platform: GitHub                     │
└─────────────────────────────────────────┘
```

### **Error Handling**
```
For non-git files:

┌─────────────────────────────────────────┐
│ ⚠️ Error: Not a git repository          │
└─────────────────────────────────────────┘
```

### **Status Bar Toggle**
```
Bottom right corner: [$(git-commit) Blame: On]
Click to toggle On/Off
```

## ⚙️ **Configuration**

### **Quick Settings**

| Setting | Default | Description |
|---------|---------|-------------|
| `gitBlameHover.enable` | `true` | Enable/disable the extension |
| `gitBlameHover.showRelativeTime` | `true` | Show "2 hours ago" vs "1/8/2026" |
| `gitBlameHover.hoverDelay` | `200` | Delay before tooltip appears (ms) |

### **Tooltip Customization**

| Setting | Default | Description |
|---------|---------|-------------|
| `gitBlameHover.showAuthor` | `true` | Show 👤 author name |
| `gitBlameHover.showDate` | `true` | Show 📅 commit date |
| `gitBlameHover.showMessage` | `true` | Show 📝 commit message |
| `gitBlameHover.showCommitId` | `true` | Show #️⃣ commit hash |
| `gitBlameHover.showPlatform` | `true` | Show 🌐 platform info |
| `gitBlameHover.maxCommitMessageLength` | `100` | Max message length (0 = no limit) |

### **Example Configuration**

```json
{
  "gitBlameHover.enable": true,
  "gitBlameHover.showRelativeTime": true,
  "gitBlameHover.hoverDelay": 150,
  "gitBlameHover.showAuthor": true,
  "gitBlameHover.showDate": true,
  "gitBlameHover.showMessage": true,
  "gitBlameHover.showCommitId": false,
  "gitBlameHover.showPlatform": false,
  "gitBlameHover.maxCommitMessageLength": 80
}
```

## 🎨 **Customization Examples**

### **Minimal Setup** (Author + Time only)
```json
{
  "gitBlameHover.showMessage": false,
  "gitBlameHover.showCommitId": false,
  "gitBlameHover.showPlatform": false
}
```

### **Detailed Setup** (Everything visible)
```json
{
  "gitBlameHover.showRelativeTime": false,
  "gitBlameHover.maxCommitMessageLength": 0,
  "gitBlameHover.hoverDelay": 100
}
```

### **Performance Setup** (Slower devices)
```json
{
  "gitBlameHover.hoverDelay": 500,
  "gitBlameHover.maxCommitMessageLength": 50
}
```

## 🛠️ **Commands**

| Command | Keybinding | Description |
|---------|------------|-------------|
| `Git Blame Hover: Toggle Enable/Disable` | None | Toggle extension on/off |

**Access via:**
- Command Palette (`Ctrl+Shift+P`)
- Status bar button click

## 🔧 **Troubleshooting**

### **Common Issues**

#### **"Git not found in PATH" Error**
**Cause**: Git is not installed or not in system PATH
**Solution**: 
1. Install Git from [git-scm.com](https://git-scm.com)
2. Restart VS Code
3. Verify with `git --version` in terminal

#### **"Not a git repository" Error**
**Cause**: File is not in a git repository
**Solution**: Initialize git in your folder: `git init`

#### **No hover tooltip appears**
**Possible causes:**
1. Extension is disabled - Check status bar or settings
2. File is not git-tracked - Add file to git: `git add filename`
3. Hover delay is too high - Reduce `hoverDelay` setting

#### **Slow performance**
**Solutions:**
1. Increase `hoverDelay` to 300-500ms
2. Reduce `maxCommitMessageLength` to 50-80
3. Disable less important info (platform, commit ID)

### **Debug Steps**
1. Check extension is enabled in status bar
2. Open Developer Tools (`Help > Toggle Developer Tools`)
3. Look for error messages in Console tab
4. Try toggling extension off/on

## 🚀 **Performance Tips**

### **Optimize for Large Repositories**
```json
{
  "gitBlameHover.hoverDelay": 300,
  "gitBlameHover.maxCommitMessageLength": 60,
  "gitBlameHover.showPlatform": false
}
```

### **Optimize for Remote Work (Slow Git)**
```json
{
  "gitBlameHover.hoverDelay": 500,
  "gitBlameHover.showMessage": false,
  "gitBlameHover.showPlatform": false
}
```

## 🤔 **FAQ**

### **Q: How is this different from the popular Git Blame extension?**
**A:** The popular extension shows blame info in the status bar and inline. Git Blame Hover shows info only when you hover, keeping your workspace clean.

### **Q: Does it work with all Git platforms?**
**A:** Yes! Detects GitHub, GitLab, Bitbucket, Azure Repos, and shows "Local/Other" for custom setups.

### **Q: Will it slow down my editor?**
**A:** No! It uses smart debouncing and caching. Git commands only run when you actually hover over lines.

### **Q: Can I use both this and other git blame extensions?**
**A:** Yes! This extension doesn't conflict with others since it only uses hover events.

### **Q: What about uncommitted changes?**
**A:** Shows "You" as author, "just now" as time, and "Uncommitted changes" as message.

## 🎯 **Supported Platforms**

| Platform | Status | URL Format |
|----------|---------|------------|
| 🐙 **GitHub** | ✅ Full support | `github.com` |
| 🦊 **GitLab** | ✅ Full support | `gitlab.com` |
| 🪣 **Bitbucket** | ✅ Full support | `bitbucket.org` |
| 🔵 **Azure Repos** | ✅ Full support | `dev.azure.com`, `visualstudio.com` |
| 🏠 **Self-hosted** | ✅ Basic support | Shows as "Local/Other" |

## 📋 **Requirements**

- **VS Code**: Version 1.90.0 or higher
- **Git**: Must be installed and available in PATH
- **Repository**: Must be a valid git repository

## 🐛 **Known Limitations**

1. **Large files**: Very large files (>10MB) may have slower git blame performance
2. **Binary files**: No blame information for binary files
3. **Merge conflicts**: Limited info during active merge conflicts
4. **Shallow clones**: May show incomplete history information

## 🔄 **Changelog**

### **v0.0.12** - Latest
- ✨ Added relative time display ("2 hours ago")
- ⚡ Implemented hover debouncing for better performance  
- 🛠️ Improved error messages and handling
- ⚙️ Added configurable tooltip format options
- 🎨 Enhanced tooltip formatting with emojis

### **v0.0.11** 
- 🐛 Fixed platform detection issues
- 📝 Updated documentation

### **v0.0.10**
- 🚀 Initial release
- ✨ Basic hover functionality
- 🎯 Status bar toggle

## 🤝 **Contributing**

We welcome contributions! Here's how you can help:

### **Report Issues**
Found a bug? [Create an issue](https://github.com/canarysautomationspvtltd/git-blame-hover/issues) with:
- Steps to reproduce
- Expected vs actual behavior
- VS Code version & OS

### **Suggest Features**
Have an idea? [Open a feature request](https://github.com/canarysautomationspvtltd/git-blame-hover/issues) with:
- Detailed description
- Use case examples
- Mockups if applicable

### **Development Setup**
```bash
# Clone the repository
git clone https://github.com/canarysautomationspvtltd/git-blame-hover

# Install dependencies
npm install

# Open in VS Code
code .

# Start development
npm run watch

# Test the extension
Press F5 to launch Extension Development Host
```

## 📄 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 **Acknowledgments**

- Thanks to the VS Code team for the excellent extension API
- Inspired by the need for cleaner git blame UX
- Community feedback and feature requests

## 📞 **Support**

- 📧 **Email**: [mailto:vststoolssupport@ecanarys.com](mailto:vststoolssupport@ecanarys.com)
- 🐛 **Issues**: [GitHub Issues](https://github.com/CanarysAutomations/git-blame-hover/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/CanarysAutomations/git-blame-hover/discussions)

---

**Made with ❤️ by [Canarys Automations](https://www.ecanarys.com)**

*If you find this extension helpful, please ⭐ star the repository and leave a review on the marketplace!*