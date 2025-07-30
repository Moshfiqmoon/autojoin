# Telegram Bot with Admin Dashboard

A comprehensive Telegram bot with a modern React admin dashboard for managing users and real-time messaging. Features include media support, voice messages, and a Messenger-style chat interface.

## 🚀 Features

### Core Functionality
- **Telegram Bot Integration**: Full bot functionality with user management
- **Real-time Chat**: Socket.IO powered instant messaging
- **Admin Dashboard**: Modern React interface with Material-UI
- **User Management**: Track users, messages, and activity

### Media Support
- **Images**: Send and receive images with preview
- **Videos**: Support for video messages
- **Voice Messages**: Browser-based voice recording (M4A/WebM)
- **Audio Files**: Support for audio file sharing
- **Bulk Media**: Send multiple files at once
- **File Size Validation**: Automatic size limit checking (20MB for images, 50MB for files)

### Chat Features
- **Multiple Chat Windows**: Messenger-style pop-up chats
- **Minimize/Restore**: Click to minimize or restore chat windows
- **Real-time Updates**: Instant message delivery with Socket.IO
- **Message Status**: Delivery confirmation indicators
- **Online Status**: Show user online/offline status
- **Profile Photos**: Display Telegram profile pictures
- **Full-size Image Preview**: Click images to view in full size

### Admin Dashboard
- **User List**: Paginated user management
- **Statistics**: Real-time user and message counts
- **Broadcast Messages**: Send messages to all users
- **Direct Messaging**: Individual user communication
- **Invite Link Generation**: Create unique invite links
- **Activity Tracking**: Monitor user engagement

## 🛠️ Technology Stack

### Backend
- **Python**: Core bot logic
- **Flask**: Web API framework
- **Flask-SocketIO**: Real-time communication
- **python-telegram-bot**: Telegram Bot API
- **Pyrogram**: Additional Telegram functionality
- **SQLite**: Database storage

### Frontend
- **React**: User interface
- **Material-UI**: Component library
- **Socket.IO Client**: Real-time updates
- **Bootstrap**: Additional styling

## 📦 Installation

### Prerequisites
- Python 3.8+
- Node.js 16+
- Telegram Bot Token
- Telegram API credentials

### Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd telegram-bot-admin
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install Node.js dependencies**
   ```bash
   cd admin
   npm install
   ```

4. **Configure the bot**
   - Edit `config.py` with your bot token and API credentials
   - Set your channel/group IDs
   - Configure admin user ID

5. **Initialize the database**
   ```bash
   python db.py
   ```

## 🚀 Running the Application

### Start the Backend
```bash
python api.py
```
The Flask server will run on `http://localhost:5001`

### Start the Frontend
```bash
cd admin
   npm start
   ```
The React app will run on `http://localhost:3000`

### Test the Setup
```bash
python test_bot.py
```

## 📱 Usage

### For Users
1. Start a conversation with your bot on Telegram
2. Send `/start` to begin
3. Join the channel when prompted
4. Start chatting with the admin

### For Admins
1. Access the dashboard at `http://localhost:3000`
2. View user list and statistics
3. Open chat windows with individual users
4. Send text messages, images, videos, or voice messages
5. Use broadcast feature to message all users

## 🔧 Configuration

### Bot Configuration (`config.py`)
```python
BOT_TOKEN = 'your_bot_token'
CHANNEL_ID = -1001234567890
API_ID = 12345678
API_HASH = "your_api_hash"
DASHBOARD_PASSWORD = 'your_admin_password'
```

### Environment Variables
- `BOT_TOKEN`: Your Telegram bot token
- `API_ID`: Telegram API ID
- `API_HASH`: Telegram API hash
- `CHANNEL_ID`: Your channel/group ID

## 📊 Database Schema

### Users Table
```sql
CREATE TABLE users (
    user_id INTEGER PRIMARY KEY,
    full_name TEXT,
    username TEXT,
    join_date TEXT,
    invite_link TEXT,
    photo_url TEXT
);
```

### Messages Table
```sql
CREATE TABLE messages (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    user_id INTEGER,
    sender TEXT,
    message TEXT,
    timestamp TEXT
);
```

## 🔒 Security Features

- **File Size Validation**: Prevents oversized uploads
- **Input Sanitization**: Protects against malicious input
- **Session Management**: Secure admin authentication
- **CORS Protection**: Configured for specific origins
- **Error Handling**: Comprehensive error management

## 🎨 UI Features

### Chat Interface
- **Responsive Design**: Works on desktop and mobile
- **Dark/Light Theme**: Material-UI theming
- **Smooth Animations**: CSS transitions and hover effects
- **Accessibility**: Keyboard navigation and screen reader support

### Admin Dashboard
- **Real-time Updates**: Live user activity
- **Pagination**: Efficient data loading
- **Search & Filter**: Find users quickly
- **Export Options**: Download user data

## 🐛 Troubleshooting

### Common Issues

1. **Bot not responding**
   - Check bot token in config.py
   - Verify bot is running on port 5001
   - Check console for error messages

2. **Media not sending**
   - Verify file size limits
   - Check file format support
   - Ensure proper MIME types

3. **Dashboard not loading**
   - Verify React app is running on port 3000
   - Check CORS configuration
   - Ensure backend is accessible

4. **Database errors**
   - Run `python db.py` to initialize database
   - Check file permissions
   - Verify SQLite installation

### Debug Mode
Enable debug logging by setting:
```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

## 📈 Performance

### Optimization Features
- **Lazy Loading**: Load messages on demand
- **Pagination**: Efficient data handling
- **Caching**: Reduce database queries
- **Compression**: Optimize file transfers

### Monitoring
- **Activity Tracking**: Monitor user engagement
- **Error Logging**: Track and resolve issues
- **Performance Metrics**: Monitor response times

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions:
- Check the troubleshooting section
- Review the configuration guide
- Test with the provided test script
- Check console logs for error messages

## 🔄 Updates

### Recent Improvements
- ✅ File size validation
- ✅ Upload progress indicators
- ✅ Online status tracking
- ✅ Message delivery status
- ✅ Enhanced error handling
- ✅ Improved UI/UX
- ✅ Voice message support
- ✅ Full-size image preview

### Planned Features
- [ ] Message encryption
- [ ] Advanced analytics
- [ ] Multi-language support
- [ ] Mobile app
- [ ] Webhook support
- [ ] Advanced media processing

---

**Enjoy your enhanced Telegram bot with admin dashboard! 🎉** 