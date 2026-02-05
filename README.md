# Whiteboard to Prototype

Transform your whiteboard sketches into working prototypes using Claude Code SDK.

## How It Works

```
[Whiteboard] → [Phone photo] → [Upload to local app]
                                        ↓
                          [Claude Code SDK receives image]
                                        ↓
                   [Claude Code READS the whiteboard]
                                        ↓
                   [Claude Code BUILDS the prototype]
                      (creates files, runs, iterates)
                                        ↓
                   [Prototype lands in your local folder]
```

# Quick Start Guide

Get up and running in under 2 minutes.

## Prerequisites

- Node.js 18+ installed
- Anthropic API key ([get one here](https://console.anthropic.com))

## Quick Start

```bash
# 1. Navigate to the project directory
cd whiteboard-to-prototype

# 2. Run the startup script
./start.sh

# The script will:
# - Check Node.js installation
# - Create .env file if missing
# - Install dependencies
# - Start the server
```

## Manual Start (Alternative)

If you prefer to start manually:

```bash
# 1. Install dependencies
npm install

# 2. Create .env file
cp .env.example .env

# 3. Edit .env and add your API key
nano .env  # or use any text editor

# 4. Start server
npm start
```

## Using the App

1. **Open in browser**: http://localhost:3000
2. **On mobile**: Use your phone's browser with same URL (must be on same network)
3. **Take/upload photo**: Click the upload area
4. **Add instructions** (optional): Specify any requirements
5. **Build**: Click "Build Prototype"
6. **View**: See your live prototype in the iframe
7. **Access files**: Check `__output__/prototype-[timestamp]/`

## Viewing History

Visit http://localhost:3000/history to see:
- All previous whiteboard sessions
- Thumbnails of each whiteboard
- Cost and token usage per session
- Direct links to generated prototypes

## Common Commands

```bash
# Start server
npm start

# Development mode (auto-reload)
npm run dev

# View server logs
# (logs display in terminal with [PREFIX] format)

## Features

- **Mobile-optimized interface** for capturing whiteboard photos
- **Automatic image compression** (max 1024x1024) for faster processing
- **One-tap photo upload** from your phone
- **Live functional demo preview** in the browser
- **Claude Code SDK** autonomously builds prototypes
- **Organized output** by timestamp in `__output__/` folder
- **Real-time cost tracking** based on token usage
- **Beautiful UI** with animated particle background

## Prerequisites

- Node.js 18 or higher
- Anthropic API key (already configured in `.env`)

## Setup

1. **Install dependencies:**
   ```bash
   cd whiteboard-to-prototype
   npm install
   ```


## Usage

1. Open `http://localhost:3000` on your phone or computer
2. Tap "Take photo" or upload an existing whiteboard image
3. Optionally add specific instructions (e.g., "Make it a dark mode app")
4. Tap "Build Prototype" and wait for Claude to analyze and build
5. View your live functional demo directly in the browser
6. Open in a new tab or find files in `__output__/prototype-[timestamp]/`

## Project Structure

```
whiteboard-to-prototype/
├── server.js              # Main server with Claude Code SDK integration
├── package.json           # Dependencies
├── .env                   # API key configuration
├── public/
│   └── index.html         # Frontend UI
├── uploads/               # Uploaded whiteboard images
└── __output__/            # Generated prototypes (organized by timestamp)
    ├── prototype-2024-01-15T10-30-00/
    ├── prototype-2024-01-15T14-22-15/
    └── ...
```

## Tips

- Take clear, well-lit photos of your whiteboard
- Include all relevant details, labels, and notes in the photo
- Use the custom prompt field to specify technologies or requirements
- Check the `__output__` folder to see your generated prototypes
- Each prototype is completely self-contained in its timestamp folder

## Cost Information

Claude Opus 4.5 pricing:
- Input: $15 per million tokens
- Output: $75 per million tokens

Each prototype generation typically costs $0.10-0.50 depending on complexity.

## Troubleshooting

**"ANTHROPIC_API_KEY not set"**
- Make sure the `.env` file exists in the project root

**"Files not generating"**
- Check the server console logs for detailed error messages
- Ensure you have write permissions in the project directory

**High API costs**
- Opus 4.5 is powerful but expensive
- Consider using Sonnet 4.5 for simpler prototypes
- Each session cost is logged in the console

## What Makes This Different

Most whiteboard-to-code demos use the Messages API and return code as text that you have to manually save. This uses the **Claude Code SDK** which means:

- Claude acts as an autonomous agent
- Files are created automatically on your machine
- Complete project structure is generated
- No manual copy-pasting required
- Full build history maintained

This is the real deal - whiteboard to working prototype with zero manual file management.

## License

MIT
