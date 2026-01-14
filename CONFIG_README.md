# Using Separate Config File

## Setup Instructions

### Files You Need:
1. `index.html` - Main payment page
2. `config.js` - Your private configuration file (UPI ID)

### Step 1: Upload Both Files to GitHub
1. Go to your GitHub repository
2. Upload `index.html`
3. Upload `config.js`

### Step 2: Configure Your UPI ID
Edit `config.js`:
```javascript
const CONFIG = {
    MERCHANT_UPI_ID: 'yourname@paytm',  // ⬅️ YOUR UPI ID
    MERCHANT_NAME: 'Your Mentorship Program'
};
```

### Step 3: Enable GitHub Pages
Your site will work at: `https://yourusername.github.io/repository-name/`

## ⚠️ Important Security Note

**GitHub repositories are PUBLIC by default!**

Even with a separate file, anyone can view `config.js` by visiting:
`https://yourusername.github.io/repository-name/config.js`

### Why This Still Works Safely:

✅ UPI IDs are **receive-only** - no one can withdraw money with just your UPI ID
✅ It's like sharing your email address - public but safe
✅ All UPI payment pages work this way (QR codes contain your UPI ID too)

### For True Privacy (Advanced):

If you want to completely hide your UPI ID from public view, you would need:

1. **Private Repository** (GitHub Pro required - $4/month)
   - Make your repository private
   - Only you can see the code
   - GitHub Pages still works

2. **Backend Server** (More complex)
   - Use a server to store UPI ID
   - Frontend calls your server API
   - Requires hosting (not free)

3. **Environment Variables** (Most secure, requires build process)
   - Use GitHub Actions
   - Store UPI ID as secret
   - Build and deploy automatically

## Recommendation

For most users, the **current approach is fine** because:
- UPI IDs are meant to be shared (that's how people pay you)
- They're already visible in QR codes
- No security risk - receive-only identifier

The separate file just makes it easier to update your UPI ID without touching the main code.
