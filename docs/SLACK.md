# Slack Setup Guide

## Step 1: Create a Slack App
1. Go to [Slack API Apps page](https://api.slack.com/apps)
2. Click "Create New App"
3. Choose "From scratch"
4. Choose a name and workspace

## Step 2: Configure Incoming Webhooks
1. In your app's settings, go to "Incoming Webhooks"
2. Activate Incoming Webhooks
3. Click "Add New Webhook to Workspace"
4. Choose the channel where you want to receive notifications
5. Copy the Webhook URL

## Step 3: Configure GitHub Secret
1. Go to your repository settings
2. Navigate to Secrets and Variables → Actions
3. Add new secret:
   - Name: `SLACK_WEBHOOK`
   - Value: Your webhook URL

## Step 4: Enable Slack Notifications
Update your `websites.json`:
```json
"notifications": {
    "slack": {
        "enabled": true
    }
}
```