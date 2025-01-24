# Discord Setup Guide

## Step 1: Create a Discord Webhook
1. Open your Discord server
2. Go to Server Settings → Integrations
3. Click "Create Webhook"
4. Choose a name and channel for the webhook
5. Copy the Webhook URL

## Step 2: Configure GitHub Secret
1. Go to your repository settings
2. Navigate to Secrets and Variables → Actions
3. Add new secret:
   - Name: `DISCORD_WEBHOOK`
   - Value: Your webhook URL

## Step 3: Enable Discord Notifications
Update your `websites.json`:
```json
"notifications": {
    "discord": {
        "enabled": true
    }
}
```