# uptimePluma

Track your websites uptime with GitHub Actions - no extra servers required

> Why "Pluma"? In Bologna's dialect, "pluma" means being flat broke - just like the lint in your empty pockets. And this tool keeps your wallet just as empty: zero costs, zero servers.


## How it works

This tool checks your websites and sends you instant notifications through Telegram, Slack, or Discord if any site becomes unreachable. No servers to maintain, no complicated setup - just GitHub Actions doing the work for you.

## Quick Start

1. Fork this repository

2. Edit `websites.json` with your websites and notification preferences:
```json
{
    "settings": {
        "retries": 2,
        "timeout": 15
    },
    "websites": [
        {
            "name": "My Company Website",
            "URL": "https://mycompany.com"
        },
        {
            "name": "My E-commerce",
            "URL": "https://shop.mycompany.com"
        }
    ],
    "notifications": {
        "telegram": {
            "enabled": true
        },
        "slack": {
            "enabled": false
        },
        "discord": {
            "enabled": false
        }
    }
}
```

3. Set up notifications:
   - Enable your preferred platform(s) in the notifications section of `websites.json`
   - Follow the configuration guide for each platform you enabled:
     - [Telegram configuration](docs/TELEGRAM.md)
     - [Slack configuration](docs/SLACK.md)
     - [Discord configuration](docs/DISCORD.md)

That's it! The monitoring will start automatically.

## What you'll get

When a website becomes unreachable, you'll receive a notification like this (example for Telegram):
```
⚠️ WARNING: Website My Website is not accessible.
URL: https://example.com
```

## Features

- No server required
- Multiple notification channels (Telegram, Slack, Discord)
- Auto-retry before marking a site as down
- Customizable check frequency
- Easy to set up and customize

## Customization

Want to change how often the checks run? Edit the cron schedule in `.github/workflows/check-websites.yml`:
```yaml
schedule:
  - cron: '*/30 * * * *'  # Example: every 30 minutes
```

## Support

Found a bug? Have a suggestion? Open an issue!