# Telegram Setup Guide

## Step 1: Create a Telegram Bot
1. Open Telegram and search for [@BotFather](https://t.me/botfather)
2. Send `/newbot` command
3. Follow the instructions to create your bot
4. Save the bot token (it looks like `123456789:ABCdefGHIjklMNOpqrsTUVwxyz`)

## Step 2: Get Your Group ID
1. Create a new group in Telegram
2. Add your bot to the group
3. Add [@RawDataBot](https://t.me/rawdatabot) to your group
4. Save the group ID (it looks like `-123456789`)
5. Remove RawDataBot from your group

## Step 3: Configure GitHub Secrets
1. Go to your repository settings
2. Navigate to Secrets and Variables → Actions
3. Add these secrets:
   - Name: `TELEGRAM_TOKEN`
   - Value: Your bot token
   - Name: `TELEGRAM_GROUP`
   - Value: Your group ID

## Step 4: Enable Telegram Notifications
Update your `websites.json`:
```json
"notifications": {
    "telegram": {
        "enabled": true
    }
}
```