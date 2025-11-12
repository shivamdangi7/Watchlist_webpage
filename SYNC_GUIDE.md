# Data Sync & Backup Guide

This guide explains how to backup and sync your TradingView Watchlist data across multiple devices.

---

## Method 1: Export/Import (Offline, No Setup Required)

### Use Case
- Quick offline backup
- One-time data transfer between devices
- No external accounts needed
- Complete privacy

### How to Use

**On Device A (Export):**
1. Open your watchlist webpage
2. Click **"Export Data"** button
3. File downloads: `watchlist-backup-2025-01-12T15-30-45.json`
4. Transfer file to Device B via:
   - Email attachment
   - WhatsApp/Telegram
   - Google Drive / Dropbox
   - USB drive
   - Any file sharing method

**On Device B (Import):**
1. Open your watchlist webpage
2. Click **"Import Data"** button
3. Select the downloaded JSON file
4. Confirm replacement
5. ✅ All your folders and tags are now on Device B!

### Pros & Cons

✅ **Pros:**
- Zero setup required
- Works completely offline
- No external accounts needed
- 100% private (data never leaves your control)
- Simple and fast

❌ **Cons:**
- Manual process (not automatic)
- Need to export/import each time
- File management required

---

## Method 2: GitHub Gist Sync (Cloud, Automatic)

### Use Case
- Automatic sync across multiple devices
- Always have latest data available
- Cloud backup for safety
- Professional solution

### One-Time Setup (5 minutes)

**Step 1: Get GitHub Token**
1. Go to: https://github.com/settings/tokens
2. Click **"Generate new token (classic)"**
3. Give it a name: `TradingView Watchlist`
4. Set expiration: **No expiration** (or your preference)
5. Select scope: ✅ **gist** (only this one!)
6. Click **"Generate token"**
7. Copy the token: `ghp_xxxxxxxxxxxxxxxxxxxx`
8. ⚠️ Save it somewhere safe! You won't see it again.

**Step 2: Configure on First Device**
1. Open your watchlist webpage
2. Find the "☁️ GitHub Sync" section
3. Paste your token in the input field
4. Token is automatically saved (you won't need to enter it again)

---

### Upload Data to Cloud

**On Any Device:**
1. Make sure token is entered (if first time)
2. Click **"Upload to Cloud"**
3. Wait for success message
4. Note the **Gist ID** shown (e.g., `abc123xyz789`)
5. Gist ID is automatically saved for next time

**What happens:**
- Creates a private GitHub Gist with your data
- Updates existing gist if already uploaded before
- Gist ID is saved in browser for easy access

---

### Download Data from Cloud

**On Another Device:**

**Option A: First Time (Need Gist ID)**
1. Click **"Download from Cloud"**
2. Enter the Gist ID from first device
3. Confirm download
4. ✅ Data synced! Gist ID saved for next time.

**Option B: Subsequent Times (Gist ID Already Saved)**
1. Click **"Download from Cloud"**
2. Press Enter (leave empty to use saved Gist ID)
3. ✅ Data synced instantly!

---

### Workflow Example

**Initial Setup:**
```
Device A:
1. Enter GitHub token
2. Upload to Cloud → Get Gist ID: abc123
3. Share Gist ID with yourself (WhatsApp, email, notes)

Device B:
1. Enter GitHub token (optional)
2. Download from Cloud → Enter: abc123
3. ✅ Synced!

Device C (Phone):
1. Download from Cloud → Enter: abc123
2. ✅ Synced!
```

**Daily Usage:**
```
Device A: Add new symbols → Upload to Cloud
Device B: Download from Cloud (auto uses saved Gist ID)
Device C: Download from Cloud (auto uses saved Gist ID)
```

---

### Pros & Cons

✅ **Pros:**
- Cloud backup (never lose data)
- Sync across unlimited devices
- Automatic Gist ID saving
- Free unlimited storage
- Professional solution
- Can share Gist ID with others

❌ **Cons:**
- Requires GitHub account (free)
- 5-minute initial setup
- Token management required
- Data stored on GitHub servers (private gist)

---

## Security & Privacy

### Export/Import
- ✅ 100% private - data never leaves your control
- ✅ No external services involved
- ✅ Fully offline
- ✅ File size limit: 10MB (prevents browser freeze)
- ✅ Comprehensive data validation before import
- ✅ File type verification (.json only)

### GitHub Gist
- ✅ Token stored locally in browser (not sent anywhere except GitHub)
- ✅ Private gists (default) - only you can access
- ✅ GitHub's enterprise-grade security
- ✅ Token can be revoked anytime at github.com/settings/tokens
- ✅ Content size validation (max 10MB)
- ✅ Data structure validation before accepting
- ⚠️ Data stored on GitHub servers (private and encrypted)

### Security Best Practices

**Token Security:**
1. **Minimal Permissions**: Only grant `gist` scope - nothing else
2. **Never Share**: Your token is like a password - keep it secret
3. **Stored Locally**: Token is in browser localStorage (encrypted by OS)
4. **Clear When Done**: Use "Clear Stored Token" button on shared/public computers
5. **Revoke if Compromised**: Go to github.com/settings/tokens and revoke immediately

**Data Protection:**
1. **Private Gists**: Always use private gists (default) for your watchlist data
2. **Regular Backups**: Export your data weekly for offline backup
3. **Verify Before Import**: Only import files you trust
4. **Size Limits**: App enforces 10MB limit for security

**Browser Security:**
1. **Use HTTPS**: Always access the page via HTTPS if hosted online
2. **Keep Browser Updated**: Use latest browser version for security patches
3. **No Extensions**: Disable untrusted browser extensions that can access page data
4. **Shared Computers**: Clear stored token after use

### What Data is Stored Where?

**localStorage (Your Browser):**
- Folder and symbol data
- GitHub token (if provided)
- Gist ID (if used)
- All stored locally, never sent to third parties

**GitHub Gist (Optional - If You Use Cloud Sync):**
- Your folder and symbol data
- Stored in private gist on GitHub servers
- Only accessible with your GitHub account + token
- Can be deleted anytime from github.com/gists

**Never Stored or Transmitted:**
- No analytics or tracking
- No third-party services
- No advertisements
- Zero external dependencies

---

## Troubleshooting

### "Invalid token" Error
- Check token has `gist` scope selected
- Verify token not expired
- Generate new token if needed

### "Gist not found" Error
- Double-check Gist ID spelling
- Ensure gist wasn't deleted
- Try re-uploading from original device

### Import Shows "Invalid file format"
- Ensure file is JSON format
- Don't edit the exported file manually
- Re-export if file is corrupted

---

## Best Practices

### For Maximum Safety
1. **Use Both Methods:**
   - GitHub Gist for daily syncing
   - Export/Import for weekly offline backups

2. **Regular Backups:**
   - Export data weekly to local file
   - Store backup files in cloud (Google Drive, etc.)

3. **Token Security:**
   - Never share your GitHub token
   - Use "No expiration" for convenience
   - Revoke old tokens if lost/compromised

4. **Multiple Devices:**
   - Upload from primary device
   - Download on secondary devices
   - Re-download after any changes

---

## Quick Reference

| Task | Export/Import | GitHub Gist |
|------|--------------|-------------|
| **Setup Time** | 0 seconds | 5 minutes |
| **Per-Use Time** | 30 seconds | 5 seconds |
| **Offline** | ✅ Yes | ❌ No |
| **Automatic** | ❌ No | ✅ Yes (after setup) |
| **Privacy** | ✅✅✅ Full | ✅✅ Good |
| **Multi-Device** | Manual | Automatic |
| **Best For** | Backups | Daily sync |

---

## Support

If you encounter issues:
1. Check browser console for errors (F12 → Console)
2. Verify GitHub token permissions
3. Try export/import as fallback
4. Clear browser cache if sync issues persist

---

**Happy Trading! 📈**
