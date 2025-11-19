# WarmBadge

Dynamic inbox health badge for Gmail — built as a Chrome extension with a modular backend.

## 🔧 Features

- Injects a badge into Gmail compose windows  
- Polls backend every 60 seconds for inbox health  
- Visual score + status (excellent, healthy, warning, critical)  
- Extensible signals: unread count, bounce rate, DMARC, etc.

## 📁 Project Structure

```
warmbadgedynamic/
├── backend/         # Express.js API
├── extension/       # Chrome extension (MV3)
└── README.md
```

## 🚀 Setup

### Backend

```bash
cd backend
npm install
npm start
```

- Endpoint: `GET /api/inbox-health`  
- Returns JSON with score, status, message, and signals

### Chrome Extension

- Go to `chrome://extensions`  
- Enable **Developer Mode**  
- Click **Load unpacked**  
- Select the `extension/` folder

## 🔐 Auth (Optional)

- Replace `userId` logic in `server.js` with real token/session decoding  
- Gmail API integration can be added in `inboxHealthService.js`

## 🧩 Extending Signals

Add fields to the `signals` object and update `computeScoreFromSignals()`.

## 📄 License

MIT