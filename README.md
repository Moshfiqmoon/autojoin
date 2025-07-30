# Telegram Bot Admin Panel

A comprehensive Telegram bot admin panel with real-time chat, user management, and automated join request handling.

## Features

- 🤖 **Telegram Bot Integration** - Handle user messages and media
- 👥 **User Management** - Track users, labels, and activity
- 💬 **Real-time Chat** - Admin can chat with users in real-time
- 📊 **Dashboard** - Statistics and user analytics
- 🎯 **Auto-join Approval** - Automatically approve join requests
- 📱 **Voice Messages** - Hold-to-record voice messages
- 🖼️ **Media Support** - Images, videos, GIFs, and audio files
- 🔔 **Real-time Notifications** - Socket.IO for live updates

## Deployment on Render

### 1. Create a New Web Service

1. Go to [Render Dashboard](https://dashboard.render.com/)
2. Click "New +" and select "Web Service"
3. Connect your GitHub repository
4. Choose the repository containing this code

### 2. Configure Environment Variables

Add these environment variables in Render dashboard:

```
BOT_TOKEN=your_telegram_bot_token
API_ID=your_telegram_api_id
API_HASH=your_telegram_api_hash
CHAT_ID=your_channel_chat_id
ADMIN_USER_ID=your_admin_user_id
DASHBOARD_PASSWORD=your_dashboard_password
GROUP_INVITE_LINK=your_group_invite_link
CHANNEL_URL=your_channel_url
WELCOME_MESSAGE=your_welcome_message
WELCOME_TEXT=your_welcome_text
SECRET_KEY=your_secret_key_for_flask
```

### 3. Build Configuration

- **Build Command**: `pip install -r requirements.txt`
- **Start Command**: `gunicorn --worker-class eventlet -w 1 api:app --bind 0.0.0.0:$PORT`

### 4. Environment Settings

- **Python Version**: 3.11.0
- **Region**: Choose closest to your users

## Local Development

### Prerequisites

- Python 3.11+
- Telegram Bot Token
- Telegram API ID and Hash

### Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Create `config.py` with your credentials:
   ```python
   BOT_TOKEN = 'your_bot_token'
   API_ID = your_api_id
   API_HASH = 'your_api_hash'
   CHAT_ID = your_chat_id
   # ... other config variables
   ```

4. Run the API:
   ```bash
   python api.py
   ```

5. Start the React frontend:
   ```bash
   cd admin
   npm install
   npm start
   ```

## API Endpoints

- `GET /dashboard-users` - Get user list with pagination
- `GET /dashboard-stats` - Get dashboard statistics
- `GET /chat/{user_id}/messages` - Get chat messages
- `POST /chat/{user_id}` - Send message to user
- `POST /send_all` - Broadcast message to all users
- `POST /send_one` - Send message to specific user
- `GET /get_channel_invite_link` - Generate invite link

## Features

### User Management
- View all users with pagination
- Search and filter users
- Label users (Register, Depositor, VIP, etc.)
- Track user activity and online status

### Real-time Chat
- Chat with users in real-time
- Send text messages, images, videos, GIFs
- Voice message recording
- File upload support

### Auto-join Approval
- Automatically approve join requests
- Send welcome messages
- Track new joins

### Dashboard Analytics
- Total users count
- Active users (last 60 minutes)
- Total messages sent
- New joins today

## Technologies Used

- **Backend**: Flask, Flask-SocketIO, python-telegram-bot, Pyrogram
- **Frontend**: React, Material-UI
- **Database**: SQLite
- **Real-time**: Socket.IO
- **Deployment**: Render

## License

Developed by Mushfiqur 