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

### Direct URL Fetching

```
Read https://x.com/username/status/1234567890
```

### With Vision OCR (for images)

```
Read the image at https://x.com/username/status/1234567890/photo/1
Use vision to extract text
```

### Examples

**Simple tweet:**
```
Read https://x.com/yibie/status/2025413319549394996
```

**Thread:**
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
