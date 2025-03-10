# uptimePluma

Track your websites uptime with GitHub Actions - no extra servers required

> Why "Pluma"? In Bolognese dialect, "pluma" means being flat broke - just like the lint in your empty pockets. And this tool keeps your wallet just as empty: zero costs, zero servers.


## How it works

This tool checks your websites and sends you instant notifications through Telegram, Slack, or Discord if any site becomes unreachable. No servers to maintain, no complicated setup - just GitHub Actions doing the work for you.

- No server required
- Multiple notification channels (Telegram, Slack, Discord)
- Auto-retry before marking a site as down
- Customizable check frequency
- Easy to set up and customize

## Quick Start

1. **Fork** this repository

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
**Settings configuration:**
- `retries`: Number of attempts before marking a site as down
- `timeout`: Timeout in seconds for each request

**Websites configuration:**
- `name`: Display name that will appear in notifications
- `URL`: The URL to monitor

**Notifications configuration:**
- Set `enabled` to true for each platform you want to use

3. Set up notifications:
   - Enable your preferred platform(s) in the notifications section of `websites.json`
   - Follow the configuration guide for each platform you enabled:
     - [Telegram configuration](docs/TELEGRAM.md)
     - [Slack configuration](docs/SLACK.md)
     - [Discord configuration](docs/DISCORD.md)

That's it! The monitoring will start automatically.

## What you'll get

When a website becomes unreachable, you'll receive a notification like this:

```
⚠️ WARNING: Website My Website is not accessible.
URL: https://example.com
```

## GitHub Pages

You can check the status of your monitoring setup using GitHub Pages. The provided `index.html` will display a summary of your configuration in a nice dashboard.

To enable this feature:
1. Go to repository Settings → Pages
2. Select the main branch as source
3. Click Save

Your dashboard will be available at: `https://{your_git_username}.github.io/uptimePluma/`

Live demo: https://rempairamore.github.io/uptimePluma/

## Crontab Customization

Edit the cron schedule in `.github/workflows/check-websites.yml`:

```yaml
schedule:
  - cron: '*/30 * * * *'  # Example: every 30 minutes
```

## Support

Found a bug? Have a suggestion? Open an issue!
