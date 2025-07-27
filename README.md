# Export/Download Claude Conversations (claude-export)

[![GitHub license](https://img.shields.io/badge/license-MIT-green)](
    ./LICENSE
)

![Working as of September 24, 2024](https://img.shields.io/badge/working%20as%20of-%20september%2024,%202024-blue)

This browser script formats and downloads Anthropic Claude conversations to markdown, JSON, and PNG for sharing and exporting chat logs.

You can export the active Claude chat log directly from the browser console, entirely locally. No data is sent to any server.

**Supports the latest Claude web UI as of September 24, 2024.**

## Quick Start

> [!TIP]
> **New to claude-export?** Check out our comprehensive guides:
> - 📖 **[Installation Guide](./INSTALLATION.md)** - Detailed setup instructions for all users
> - 👤 **[User Guide](./USER_GUIDE.md)** - Step-by-step usage instructions with examples

### Simple 3-Step Process

1. **Get the script**: Copy contents from [`/dist/`](./dist/) folder (choose `md.min.js`, `json.min.js`, or `image.min.js`)
2. **Open Claude**: Navigate to [claude.ai](https://claude.ai) and open your conversation
3. **Run export**: Open browser console (`F12`), paste script, press Enter

> [!IMPORTANT]  
> Always be careful when pasting code into the console. Only paste code from trusted sources, as it can be used to execute malicious code.
> You can explore this repository and verify the code before pasting it into the console, or clone and build the code yourself.

## Detailed Usage

For complete instructions, see the **[User Guide](./USER_GUIDE.md)**. Below are quick examples for each export format:

### JSON

1. Copy contents of [`/dist/json.min.js`](./dist/json.min.js)
2. Paste into browser console

#### Example output (JSON):

```json
{
    "meta": {
        "exported_at": "2024-03-19 16:03:09",
        "title": "Sending Javascript Requests"
    },
    "chats": [
        {
            "index": 0,
            "type": "prompt",
            "message": [
                {
                    "type": "p",
                    "data": "How can I send a request in Javascript?"
                }
            ]
        },
        {
            "index": 1,
            "type": "response",
            "message": [
                {
                    "type": "p",
                    "data": "In JavaScript, you can send a request using the built-in fetch function or the XMLHttpRequest object. Here's an example using fetch:"
                },
                {
                    "type": "pre",
                    "language": "javascript",
                    "data": "fetch('https://api.example.com/data')\n  .then(response => response.json())\n  .then(data => {\n    // Handle the response data\n    console.log(data);\n  })\n  .catch(error => {\n    // Handle any errors\n    console.error('Error:', error);\n  });"
                },
                {
                    "type": "p",
                    "data": "In this example, fetch sends a GET request to the specified URL (https://api.example.com/data). The then block is used to handle the response. The first then converts the response to JSON format using response.json(), and the second then receives the parsed JSON data, which you can then process as needed."
                },
            ]
        },
    ]
}
```

### Markdown

1. Copy contents of [`/dist/md.min.js`](./dist/md.min.js)
2. Paste into browser console

#### Example output (Markdown):

````markdown
# Sending Javascript Requests
`2024-03-19 16:04:20`

_Prompt_:
How can I send a request in Javascript?

_Claude_:
In JavaScript, you can send a request using the built-in fetch function or the XMLHttpRequest object. Here's an example using fetch:

```javascript
fetch('https://api.example.com/data')
.then(response => response.json())
.then(data => {
    // Handle the response data
    console.log(data);
})
.catch(error => {
    // Handle any errors
    console.error('Error:', error);
});
```

In this example, fetch sends a GET request to the specified URL (https://api.example.com/data). The then block is used to handle the response. The first then converts the response to JSON format using response.json(), and the second then receives the parsed JSON data, which you can then process as needed.
````

### Image (.PNG)

1. Copy contents of [`/dist/image.min.js`](./dist/image.min.js)
2. Paste into browser console

> [!NOTE]  
> Downloading as an image uses the `html2canvas` library to take a screenshot of the chat log. This may take a few seconds to process.

#### Example output (Image Export):
![alt text](./public/claude-export-example.png "claude-export Example Output")

## Installation & Development

### For Users (No Installation Required)
The simplest way to use claude-export is with the pre-built scripts in the `/dist` folder. No installation needed!

See the **[Installation Guide](./INSTALLATION.md)** for detailed instructions.

### For Developers
```bash
# Clone the repository
git clone https://github.com/ryanschiang/claude-export.git
cd claude-export

# Install dependencies
npm install

# Build the project
npm run build
```

Built files will be generated in the `/dist` folder.

For complete development setup instructions, see the **[Installation Guide](./INSTALLATION.md)**.

## Browser Compatibility

- ✅ **Chrome** 80+
- ✅ **Firefox** 75+ 
- ✅ **Safari** 13+
- ✅ **Edge** 80+
- ❌ **Internet Explorer** (not supported)

## Limitations

This is a trivial implementation as Claude currently does not support sharing or exporting conversations. It may break with future changes.

It currently supports:
- Paragraphs / Text
- Lists
- Code blocks
- Tables

## Support & Contributing

### Getting Help
- 📖 **Read the guides**: [Installation Guide](./INSTALLATION.md) | [User Guide](./USER_GUIDE.md)
- 🐛 **Report issues**: [GitHub Issues](https://github.com/ryanschiang/claude-export/issues)
- 💡 **Feature requests**: Create an issue with the "enhancement" label

### Contributing
We welcome contributions! Please:
1. Fork the repository
2. Follow the development setup in [Installation Guide](./INSTALLATION.md)
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Acknowledgements

- [html2canvas](https://github.com/niklasvh/html2canvas) - Used to take a screenshot of the chat log and export as a PNG.

## You May Also Like

[`chatgpt-export`](https://github.com/ryanschiang/chatgpt-export) - Export OpenAI ChatGPT conversations to markdown, JSON, and PNG for sharing and exporting chat logs.

## Future Development

- [ ] Nested code blocks (within lists)
- [ ] Nested lists 
- [x] Fix syntax highlighting
- [x] Trim whitespace on exported images