# ⚽ Football Betting System - Web UI

Web interface for the Football Betting System powered by n8n workflows.

## 🚀 Quick Start

### Option 1: Deploy to GitHub Pages

1. Create a new GitHub repository
2. Upload `index.html` to the repository
3. Go to **Settings** → **Pages**
4. Source: **Deploy from a branch**
5. Branch: **main** / **root**
6. Save → Wait 1-2 minutes
7. Access at: `https://yourusername.github.io/repository-name`

### Option 2: Test Locally

1. Download `index.html`
2. Open with any browser

## 🔐 Authentication

Default password: `admin`

### Change Password

1. Go to https://emn178.github.io/online-tools/sha256.html
2. Enter your new password
3. Copy the hash
4. Replace `PASSWORD_HASH` in the code:

```javascript
const PASSWORD_HASH = 'your-new-hash-here';
```

## ⚙️ Configuration

### Webhook URL

The UI connects to n8n webhooks. Default: `https://thihx.app.n8n.cloud`

Change in **Settings** tab or update the default in code:

```javascript
webhookUrl: 'https://your-n8n-domain.com'
```

### Required n8n Workflow

Make sure **Workflow 03 - Webhook Handler** is:
1. Imported into n8n
2. **Activated** (toggle ON)

## 📱 Features

| Tab | Description |
|-----|-------------|
| **Dashboard** | Overview stats, recent activity |
| **Matches** | Browse all matches, filter by status/date/team |
| **Watchlist** | Manage tracked matches |
| **Recommendations** | View AI betting recommendations |
| **Settings** | Configure webhook URL, password |

## 🔗 Webhook Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/webhook/get-matches` | GET | Fetch all matches |
| `/webhook/get-watchlist` | GET | Fetch watchlist |
| `/webhook/add-watchlist` | POST | Add match to watchlist |

## 🛠️ Troubleshooting

### "Failed to load matches"
- Check if workflow is **Activated** in n8n
- Verify webhook URL in Settings
- Check browser console for CORS errors

### CORS Errors
If using local file, some browsers block cross-origin requests. Solutions:
- Deploy to GitHub Pages
- Use a local server: `python -m http.server 8000`

### Password not working
- Default is `admin`
- Check if PASSWORD_HASH matches your password
- Clear localStorage and try again

## 📄 License

MIT License
