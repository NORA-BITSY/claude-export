# Claude Export - Installation and Setup Guide

## Table of Contents

1. [Overview](#overview)
2. [Prerequisites](#prerequisites)
3. [Installation Methods](#installation-methods)
   - [Method 1: Direct Usage (Recommended for Users)](#method-1-direct-usage-recommended-for-users)
   - [Method 2: Development Setup](#method-2-development-setup)
4. [Usage Instructions](#usage-instructions)
5. [Browser Compatibility](#browser-compatibility)
6. [Troubleshooting](#troubleshooting)
7. [Security Considerations](#security-considerations)

## Overview

Claude Export is a browser-based tool that allows you to export your Anthropic Claude conversations to various formats (Markdown, JSON, and PNG images). The tool runs entirely in your browser - no data is sent to external servers.

## Prerequisites

### For Direct Usage (Method 1)
- A modern web browser (Chrome, Firefox, Safari, or Edge)
- Access to [claude.ai](https://claude.ai)
- Basic knowledge of browser developer tools

### For Development Setup (Method 2)
- **Node.js** (version 14.0 or higher)
- **npm** (usually comes with Node.js)
- **Git** (for cloning the repository)
- A code editor (VS Code, Sublime Text, etc.)

## Installation Methods

### Method 1: Direct Usage (Recommended for Users)

This method requires no installation. You can use the pre-built scripts directly from the `/dist` folder.

#### Step 1: Download the Scripts
You have two options:

**Option A: Download Individual Files**
1. Go to the [claude-export GitHub repository](https://github.com/ryanschiang/claude-export)
2. Navigate to the `/dist` folder
3. Download the script you need:
   - `json.min.js` - For JSON export
   - `md.min.js` - For Markdown export
   - `image.min.js` - For PNG image export

**Option B: Clone the Repository**
```bash
git clone https://github.com/ryanschiang/claude-export.git
cd claude-export
```

#### Step 2: Prepare the Script
1. Open the downloaded `.js` file in a text editor
2. Copy the entire contents of the file
3. Keep it ready for pasting into the browser console

### Method 2: Development Setup

Follow this method if you want to modify the code, contribute to the project, or build the scripts yourself.

#### Step 1: Clone the Repository
```bash
git clone https://github.com/ryanschiang/claude-export.git
cd claude-export
```

#### Step 2: Install Dependencies
```bash
npm install
```

This will install:
- **Webpack** - Module bundler
- **Babel** - JavaScript compiler
- **html2canvas** - Library for image capture
- **Terser** - JavaScript minifier

#### Step 3: Build the Project
```bash
npm run build
```

This command will:
- Compile the source files from `/src`
- Bundle and minify the JavaScript
- Output the built files to `/dist`

#### Step 4: Verify Build
After building, you should see these files in the `/dist` directory:
- `json.min.js`
- `md.min.js`
- `image.min.js`

## Usage Instructions

### Basic Usage Workflow

1. **Navigate to Claude**
   - Go to [claude.ai](https://claude.ai)
   - Log into your account
   - Open the conversation you want to export

2. **Open Browser Console**
   - **Chrome/Edge**: Press `F12` or `Ctrl+Shift+I` (Windows/Linux) / `Cmd+Opt+I` (Mac)
   - **Firefox**: Press `F12` or `Ctrl+Shift+K` (Windows/Linux) / `Cmd+Opt+K` (Mac)
   - **Safari**: Enable Developer menu first (`Safari > Preferences > Advanced > Show Develop menu`), then press `Cmd+Opt+I`

3. **Run the Export Script**
   - Copy the contents of your desired export script
   - Paste into the console
   - Press Enter to execute

### Export Format Details

#### JSON Export
**File to use**: `dist/json.min.js`

**Output**: Structured JSON file containing:
- Metadata (export timestamp, conversation title)
- Array of messages with type, content, and formatting information
- Preserves code blocks, lists, and other formatting

**Best for**: 
- Programmatic processing
- Data analysis
- Integration with other tools

#### Markdown Export
**File to use**: `dist/md.min.js`

**Output**: Markdown file with:
- Conversation title and timestamp
- Clean formatting with headers for each speaker
- Preserved code blocks with syntax highlighting
- Lists and tables in markdown format

**Best for**: 
- Documentation
- Sharing in markdown-compatible platforms
- Easy reading and editing

#### PNG Image Export
**File to use**: `dist/image.min.js`

**Output**: High-quality PNG screenshot of the conversation

**Features**:
- Captures the visual appearance of the chat
- Automatically trims whitespace
- Maintains syntax highlighting and formatting

**Best for**: 
- Social media sharing
- Presentations
- Visual documentation

**Note**: Image export may take 5-10 seconds to process depending on conversation length.

### Advanced Usage

#### Customizing Export Behavior

If you're using the development setup, you can modify the source files:

- **`src/exportJSON.js`** - Customize JSON structure and content
- **`src/exportMarkdown.js`** - Modify markdown formatting
- **`src/exportImage.js`** - Adjust image capture settings
- **`src/util/`** - Utility functions for content extraction

After making changes, rebuild with:
```bash
npm run build
```

#### Batch Processing

To export multiple conversations:
1. Open each conversation in a separate tab
2. Run the export script in each tab's console
3. Files will be downloaded automatically with timestamps

## Browser Compatibility

### Fully Supported
- **Chrome** 80+
- **Firefox** 75+
- **Safari** 13+
- **Edge** 80+

### Partially Supported
- **Internet Explorer**: Not supported (lacks modern JavaScript features)
- **Older browser versions**: May work but not guaranteed

### Required Browser Features
- ES6 JavaScript support
- HTML5 Canvas API (for image export)
- File download API
- Developer console access

## Troubleshooting

### Common Issues

#### "Script doesn't run" or "Nothing happens"
**Possible causes:**
- Browser blocking console execution
- JavaScript disabled
- Network security policies

**Solutions:**
1. Ensure JavaScript is enabled in your browser
2. Try refreshing the Claude page and running the script again
3. Check browser console for error messages

#### "Download doesn't start"
**Possible causes:**
- Browser blocking file downloads
- Pop-up blocker interference

**Solutions:**
1. Allow downloads from claude.ai in browser settings
2. Disable pop-up blocker temporarily
3. Check Downloads folder - file may have downloaded silently

#### "Image export fails" or "Takes too long"
**Possible causes:**
- Very long conversations
- Browser memory limitations
- html2canvas compatibility issues

**Solutions:**
1. Try exporting shorter conversation segments
2. Close other browser tabs to free memory
3. Use JSON or Markdown export as alternatives

#### "Exported content is incomplete"
**Possible causes:**
- Conversation not fully loaded
- Dynamic content still loading

**Solutions:**
1. Scroll through entire conversation before exporting
2. Wait for all images/content to load
3. Refresh the page and try again

### Getting Help

If you encounter issues:

1. **Check the Issues**: Visit the [GitHub Issues page](https://github.com/ryanschiang/claude-export/issues)
2. **Browser Console**: Check for error messages in the developer console
3. **Report Bugs**: Create a new issue with:
   - Browser version and OS
   - Error messages (if any)
   - Steps to reproduce the problem

## Security Considerations

### Data Privacy
- **Local Processing**: All export processing happens locally in your browser
- **No Data Transmission**: No conversation data is sent to external servers
- **No Tracking**: The tool doesn't collect any usage analytics

### Code Safety
- **Open Source**: All code is publicly available for inspection
- **No Obfuscation**: Source code is readable and auditable
- **Minimal Dependencies**: Uses only essential, well-known libraries

### Best Practices
1. **Verify Code**: Always review scripts before pasting into console
2. **Use Official Sources**: Only download from the official GitHub repository
3. **Keep Updated**: Use the latest version for security and compatibility
4. **Be Cautious**: Never paste unknown code into browser consoles

### Console Safety Warning

⚠️ **IMPORTANT**: Pasting code into browser consoles can be dangerous. Only paste code from trusted sources. This tool's code is open source and available for inspection at the GitHub repository.

## Additional Resources

- **GitHub Repository**: https://github.com/ryanschiang/claude-export
- **Example Outputs**: See `/public` folder for sample exports
- **Source Code**: Check `/src` folder for implementation details
- **Build Configuration**: Review `webpack.config.js` and `package.json`

## Contributing

If you want to contribute to the project:

1. Fork the repository
2. Set up the development environment (Method 2)
3. Make your changes
4. Test thoroughly
5. Submit a pull request

For detailed contribution guidelines, see the main README.md file.
