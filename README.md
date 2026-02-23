# ultimate-twitter-reader

OpenClaw skill for reading Twitter/X posts via fxtwitter API with DeepReeder Markdown format.

## Features

- 📖 **Fetch full tweet content** including long threads and articles
- 🔗 **Resolve X URLs** automatically using fxtwitter/vxtwitter API
- 📝 **DeepReeder Markdown format** - clean, readable output for Telegram
- 🖼️ **Vision OCR support** - extract text from tweet images
- 🌐 **Browser fallback** - use agent-browser for login-required content

## Installation

```bash
npx skills add https://github.com/ooosvsv/ultimate-twitter-reader --skill ultimate-twitter-reader
```

Or manually:

```bash
git clone https://github.com/ooosvsv/ultimate-twitter-reader.git /path/to/skills/ultimate-twitter-reader
```

## Usage

### Direct URL Fetching (API)

```
Read https://x.com/username/status/1234567890
```

Uses fxtwitter API - fast, no login needed for public tweets.

### With Browser (for full articles/login-required content)

For X Articles, private tweets, or content requiring login, use **agent-browser**:

```bash
agent-browser open https://x.com/username/status/1234567890
agent-browser snapshot
agent-browser get text @e13
```

This skill integrates with agent-browser to fetch:
- 📰 **X Articles** - Full article content beyond tweet character limit
- 🔒 **Login-required content** - Protected tweets and threads
- 🖼️ **Full page snapshots** - Complete conversation view
- 💬 **Thread replies** - All replies in a conversation

### With Vision OCR (for images)

```
Read the image at https://x.com/username/status/1234567890/photo/1
Use vision to extract text
```

### Examples

**Simple tweet (API):**
```
Read https://x.com/yibie/status/2025413319549394996
```

**Long article (browser):**
```
agent-browser open https://x.com/yibie/article/2025413319549394996
agent-browser snapshot
```

**Thread (API or browser):**
```
Read https://x.com/elonmusk/status/1234567890
```

## Output Format

Tweets are formatted using **DeepReeder Markdown**:

```markdown
## @username (Display Name) 📝

Tweet content here...

🔗 [Original Tweet](https://x.com/username/status/1234567890)
📅 Date | 💬 Likes | 🔄 Reposts | 👁️ Views

---

*Extracted via fxtwitter API*
```

## API vs Browser

| Feature | fxtwitter API | agent-browser |
|---------|--------------|---------------|
| Public tweets | ✅ Fast | ✅ Full access |
| X Articles | ❌ Limited | ✅ Full content |
| Login required | ❌ No | ✅ Yes |
| Speed | ⚡ Fast | 🐢 Slower |
| Setup | None | Requires browser |

## Requirements

- **OpenClaw** 2026.2.21 or later
- **agent-browser** (optional, for login-required content)
- **Internet connection** for API access

## API Used

- **fxtwitter/vxtwitter API** - Free Twitter/X API proxy
- No authentication required for public tweets
- Rate limits apply (use responsibly)

## Files

```
ultimate-twitter-reader/
├── SKILL.md          # OpenClaw skill definition
├── fetcher.py        # Main fetch logic
└── README.md         # This file
```

## License

MIT

## Author

小龙虾 🦞
