# Claude Export - Quick Reference

## Export Scripts Location
```
/dist/md.min.js     → Markdown export
/dist/json.min.js   → JSON export  
/dist/image.min.js  → PNG image export
```

## Usage Steps
1. Copy script from `/dist/` folder
2. Open conversation at [claude.ai](https://claude.ai)
3. Open browser console (`F12`)
4. Paste script and press Enter
5. File downloads automatically

## Console Shortcuts
| Browser | Windows/Linux | Mac |
|---------|---------------|-----|
| Chrome/Edge | `F12` or `Ctrl+Shift+I` | `Cmd+Opt+I` |
| Firefox | `F12` or `Ctrl+Shift+K` | `Cmd+Opt+K` |
| Safari | - | `Cmd+Opt+I` |

## Output Formats

### Markdown (.md)
- **Best for**: Documentation, sharing
- **File size**: Small
- **Speed**: Fast
- **Features**: Clean formatting, code blocks, lists

### JSON (.json)
- **Best for**: Data analysis, automation
- **File size**: Small
- **Speed**: Fast
- **Features**: Structured data, metadata, programmatic access

### PNG Image (.png)
- **Best for**: Social media, presentations
- **File size**: Large
- **Speed**: Slow (5-10 seconds)
- **Features**: Visual capture, maintains formatting

## Troubleshooting Quick Fixes

| Problem | Solution |
|---------|----------|
| Script won't run | Enable JavaScript, refresh page |
| No download | Allow downloads from claude.ai |
| Missing content | Scroll through full conversation first |
| Image export slow | Wait patiently, close other tabs |
| Console not found | Try different keyboard shortcut |

## File Naming
- Auto-generated: `Claude-[title]-YYYY-MM-DD-HH-MM-SS.[ext]`
- Example: `Claude-Python-Help-2024-07-26-10-30-15.md`

## Security Notes
- ✅ Runs locally in browser
- ✅ No data sent to servers
- ✅ Open source code
- ⚠️ Only paste trusted code in console

## Need More Help?
- 📖 [Installation Guide](./INSTALLATION.md)
- 👤 [User Guide](./USER_GUIDE.md)
- 🐛 [GitHub Issues](https://github.com/ryanschiang/claude-export/issues)
