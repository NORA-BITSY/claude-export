# Claude Export - User Guide

## Quick Start

### 1. Choose Your Export Format

| Format | Use Case | File Size | Processing Time |
|--------|----------|-----------|----------------|
| **Markdown** | Documentation, sharing, editing | Small | Fast |
| **JSON** | Data analysis, automation | Small | Fast |
| **PNG Image** | Social media, presentations | Large | Slow (5-10s) |

### 2. Get the Script

**Easiest Method**: Copy from the repository
1. Go to https://github.com/ryanschiang/claude-export
2. Navigate to `/dist/` folder
3. Open the file you need:
   - `md.min.js` for Markdown
   - `json.min.js` for JSON  
   - `image.min.js` for PNG
4. Copy all the code (Ctrl+A, Ctrl+C)

### 3. Export Your Conversation

1. Open your Claude conversation at [claude.ai](https://claude.ai)
2. Open browser console:
   - **Windows/Linux**: Press `F12` or `Ctrl+Shift+I`
   - **Mac**: Press `Cmd+Option+I`
3. Paste the script and press Enter
4. Your file will download automatically

## Detailed Usage Guide

### Before You Start

#### Preparing Your Conversation
- **Load completely**: Scroll through the entire conversation to ensure all content is loaded
- **Wait for media**: Let images and code blocks fully render
- **Check formatting**: Verify tables and lists display correctly

#### Browser Setup
- **Enable downloads**: Allow file downloads from claude.ai
- **Disable pop-up blocker**: Temporarily disable if downloads fail
- **Close extra tabs**: Free up memory for better performance

### Step-by-Step Export Process

#### For Markdown Export

1. **Access the Script**
   ```
   File needed: dist/md.min.js
   ```

2. **Open Claude Conversation**
   - Navigate to the specific conversation thread
   - Ensure the conversation title is visible (if you want it included)

3. **Execute Export**
   - Open browser developer tools
   - Go to Console tab
   - Paste the markdown export script
   - Press Enter

4. **File Download**
   - File will be named: `Claude-[conversation-title]-[timestamp].md`
   - Default location: Your browser's Downloads folder

**Example Markdown Output:**
```markdown
# My AI Assistant Conversation
2024-07-26 10:30:15

_Prompt_:
How do I export Claude conversations?

_Claude_:
You can export Claude conversations using a browser script...
```

#### For JSON Export

1. **Access the Script**
   ```
   File needed: dist/json.min.js
   ```

2. **Execute Export** (same steps as Markdown)

3. **File Structure**
   ```json
   {
     "meta": {
       "exported_at": "2024-07-26 10:30:15",
       "title": "My Conversation"
     },
     "chats": [
       {
         "index": 0,
         "type": "prompt",
         "message": [...]
       }
     ]
   }
   ```

**JSON Benefits:**
- Structured data format
- Easy to parse programmatically
- Preserves all formatting metadata
- Smallest file size

#### For PNG Image Export

1. **Access the Script**
   ```
   File needed: dist/image.min.js
   ```

2. **Prepare for Capture**
   - Scroll to top of conversation
   - Ensure all content is visible
   - Wait for any loading animations to complete

3. **Execute Export**
   - Paste and run the script
   - **Wait patiently** - processing takes 5-10 seconds
   - Do not scroll or interact with the page during capture

4. **Processing Indicators**
   - You may see a "Processing..." message
   - The page might briefly flash or change appearance
   - Download will start automatically when complete

**Image Export Features:**
- High-resolution capture
- Automatic whitespace trimming
- Preserves syntax highlighting
- Maintains visual formatting

### Advanced Usage Tips

#### Organizing Your Exports

**File Naming Convention:**
- Files are automatically named with timestamps
- Format: `Claude-[title]-YYYY-MM-DD-HH-MM-SS.[extension]`
- Example: `Claude-Python-Tutorial-2024-07-26-10-30-15.md`

**Folder Organization:**
```
Downloads/
├── Claude-Exports/
│   ├── 2024-07/
│   │   ├── Programming-Help/
│   │   │   ├── Python-Tutorial.md
│   │   │   ├── JavaScript-Debug.json
│   │   │   └── Code-Review.png
│   │   └── Research/
│   │       ├── AI-Ethics.md
│   │       └── Machine-Learning.json
```

#### Batch Export Workflow

For exporting multiple conversations:

1. **Open Multiple Tabs**
   - Open each conversation in a separate tab
   - Keep all tabs loaded

2. **Export Sequentially**
   - Work through tabs one by one
   - Use the same script for consistency
   - Wait for each download to complete

3. **Organize Downloads**
   - Move files to appropriate folders
   - Rename if needed for better organization

#### Content Optimization

**For Better Markdown:**
- Use clear, descriptive conversation titles
- Include context in your prompts
- Break up very long conversations

**For Better JSON:**
- Ensure code blocks have proper language tags
- Use structured lists and tables when possible
- Keep formatting consistent

**For Better Images:**
- Use shorter conversations (better visual quality)
- Ensure good contrast in your browser theme
- Avoid very wide content that might be cut off

### Working with Exported Files

#### Markdown Files
- **View**: Any text editor, Markdown viewer, or browser
- **Edit**: VS Code, Typora, Notion, GitHub
- **Convert**: Pandoc to PDF, Word, HTML
- **Share**: GitHub, GitLab, documentation sites

#### JSON Files
- **View**: Text editor with JSON formatting
- **Process**: Python, JavaScript, any programming language
- **Analyze**: Data analysis tools, custom scripts
- **Convert**: Various formats using scripts

#### PNG Images
- **View**: Any image viewer
- **Edit**: Photoshop, GIMP, online editors
- **Share**: Social media, presentations, documentation
- **Print**: High quality for physical documents

### Quality Assurance

#### Checking Your Exports

**For Markdown:**
- Open in a Markdown preview tool
- Verify code syntax highlighting works
- Check that lists and tables format correctly
- Ensure links are preserved

**For JSON:**
- Validate JSON syntax with online tools
- Check that all messages are captured
- Verify metadata is correct
- Ensure special characters are properly escaped

**For Images:**
- Check image clarity and resolution
- Verify all content is visible
- Ensure text is readable
- Check that colors and formatting are preserved

#### Common Export Issues

**Missing Content:**
- Solution: Scroll through entire conversation before export
- Cause: Dynamic loading of older messages

**Formatting Problems:**
- Solution: Wait for page to fully load before export
- Cause: CSS and JavaScript still rendering

**Download Failures:**
- Solution: Check browser download settings
- Cause: Pop-up blockers or security restrictions

**Large File Sizes:**
- Solution: Export shorter conversation segments
- Cause: Very long conversations or many images

### Privacy and Security

#### Data Handling
- **Local Processing**: All work done in your browser
- **No Uploads**: No data sent to external servers
- **No Storage**: Scripts don't save data locally
- **No Tracking**: No analytics or user tracking

#### Best Practices
- Review exported files before sharing
- Remove sensitive information if needed
- Use secure file storage for confidential conversations
- Be aware of who has access to exported files

### Troubleshooting Common Issues

#### Script Won't Run
1. Check JavaScript is enabled
2. Try refreshing the Claude page
3. Ensure you're on claude.ai (not other domains)
4. Check browser console for error messages

#### Download Doesn't Start
1. Allow downloads from claude.ai in browser settings
2. Disable pop-up blockers temporarily
3. Try running script again
4. Check Downloads folder - file may have downloaded

#### Exported Content Is Wrong
1. Ensure conversation is fully loaded
2. Scroll through entire conversation first
3. Wait for all content to render
4. Try refreshing page and exporting again

#### Image Export Takes Too Long
1. Try shorter conversations
2. Close other browser tabs
3. Wait longer - large conversations need more time
4. Use Markdown or JSON export as alternatives

### Getting Support

If you need help:

1. **Check this guide** for common solutions
2. **Review the code** - it's open source and readable
3. **Check GitHub Issues** for similar problems
4. **Create a new issue** with detailed problem description

For technical support, include:
- Browser name and version
- Operating system
- Error messages (if any)
- Steps you followed
- Expected vs actual behavior
