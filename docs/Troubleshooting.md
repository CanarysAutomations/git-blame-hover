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

### **Q: How is this different from other Git Blame extensions?**
**A:** Git Blame Hover combines hover tooltips with optional inline annotations, heat maps, author analytics, and clickable commits - offering the most comprehensive blame experience while maintaining performance.

### **Q: Does it work with all Git platforms?**
**A:** Yes! Automatically detects and provides direct links to GitHub, GitLab, Bitbucket, Azure DevOps, and shows "Local/Other" for custom setups.

### **Q: Will the heat maps and inline annotations slow down my editor?**
**A:** No! All features use smart rendering (visible lines only), intelligent caching, and configurable performance limits. You can adjust settings for optimal performance.

### **Q: Can I disable features I don't want?**
**A:** Absolutely! Every feature is toggleable. You can use just hover tooltips, or enable heat maps, inline annotations, and analytics as needed.

### **Q: How do author avatars work?**
**A:** The extension uses Gravatar to fetch author avatars based on email addresses from git commits. This works for most developers who have Gravatar accounts.

### **Q: What about uncommitted changes?**
**A:** Shows "You" as author, "just now" as time, and "Uncommitted changes" as message. Heat maps and analytics respect uncommitted changes.

### **Q: Can I customize the inline annotation format?**
**A:** Yes! Use the `inlineAnnotationFormat` setting with tokens like `{author}`, `{timeAgo}`, `{hash}`, and `{message}` to create your preferred format.

### **Q: Does it work with large files?**
**A:** Yes, with configurable file size limits. The extension intelligently handles large files with optimized rendering and caching strategies. Default limit is 1MB, configurable via the `maxFileSize` setting.

### **Q: How does the caching work?**
**A:** Git Blame Hover uses an intelligent cache system with a 5-minute default timeout. Blame information is cached per file and line to avoid repeated Git operations, significantly improving performance. Cache timeout is configurable via the `cacheTimeout` setting.


## 🔄 **Changelog**

### **v1.0.4** - Latest (Enhanced Release)
- 🚀 **Major Enhancement**: Comprehensive feature overhaul with improved performance
- 🌈 **Enhanced Heat Map**: Better visualization with improved decoration logic  
- ⚡ **Performance Boost**: Advanced caching system with 5-minute default timeout
- 🛡️ **File Size Limits**: Configurable limits for large files (1MB default)
- 📊 **Enhanced Analytics**: Improved author statistics and file contribution insights
- 🎯 **Better Error Handling**: More informative error messages and graceful failures
- 📝 **Inline Annotations**: Optional end-of-line blame information
- 🗺️ **Heat Maps**: Visual code age representation with color coding
- 🖼️ **Avatar Integration**: Gravatar support for author identification
- 🔗 **Clickable Commits**: Direct links to commit pages on platforms
- ⚡ **Advanced Caching**: Intelligent cache system with configurable timeouts
- 🎯 **Multiple Commands**: 7 new commands with keyboard shortcuts
- ⚙️ **Enhanced Configuration**: 17+ customization options including `showAuthorAvatar`
- 🛡️ **Performance Limits**: File size limits and loading indicators
- 🎨 **Rich Tooltips**: Enhanced markdown tooltips with file context and unordered list formatting

### **v0.0.12** - Previous
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
Found a bug? [Create an issue](https://github.com/CanarysAutomations/git-blame-hover/issues) with:
- Steps to reproduce
- Expected vs actual behavior
- VS Code version & OS

### **Suggest Features**
Have an idea? [Open a feature request](https://github.com/CanarysAutomations/git-blame-hover/issues) with:
- Detailed description
- Use case examples
- Mockups if applicable