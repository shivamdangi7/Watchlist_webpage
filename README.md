# TradingView Watchlist Manager

A comprehensive web-based tool for managing TradingView watchlists with advanced organization features, batch opening, journaling, and cloud sync capabilities.

## Features

### 📋 Clipboard Data Parsing
- Paste formatted stock data into the textarea
- Format: `### Folder Name, NSE:SYMBOL1, NSE:SYMBOL2, BSE:SYMBOL3`
- Automatically extracts folder names and stock symbols
- Supports all TradingView exchanges (NSE, BSE, etc.)

### 💾 Persistent Storage
- All data automatically saved to browser's localStorage
- Watchlists, notes, journal, and rules persist across browser sessions
- Your data is preserved even after closing the page

### 📁 Folder Management
- Add multiple folders by pasting formatted data
- Update existing folders by pasting data with the same folder name
- Delete individual folders with the "Delete" button
- Clear all folders at once with "Clear All" button
- **Collapse/Expand folders** to manage screen space
- Expand All (▼) / Collapse All (▶) buttons for quick folder management

### 🎨 View Modes
Switch between two display modes:
- **📊 Detailed View**: Shows full symbol information with note previews
- **📋 Compact View**: Space-efficient grid with hover tooltips for notes
  - Smaller cards for more symbols on screen
  - Note tooltips appear on hover
  - Edit controls appear on hover in edit mode
  - Golden glow for symbols with notes

### 🏷️ Color Tagging System
Organize your symbols with 5 color tags:
- **Red, Blue, Green, Orange, Purple** tags available
- Click the 🔖 icon on each symbol to assign tags
- Only one tag per symbol
- Symbol cards display colored borders based on their tag
- Tag count badges shown in folder headers
- Click tag badges to open all symbols with that tag

### 📝 Stock Notes
- Add notes to individual stocks
- Click the 📝 icon (appears in Edit mode)
- Notes displayed as preview in detailed view
- Golden glow indicator for symbols with notes in compact view
- Notes sync across devices via cloud backup

### 📖 Trading Journal & Rule Book
Built-in journaling system with two tabs:
- **📋 Rule Book**: Write and maintain your trading rules and strategies
- **📝 Journal**: Record trades, observations, and learnings
- Large text area with example templates
- Auto-save to localStorage
- Syncs with cloud backup
- Access via 📖 button in toolbar

### 🔗 Smart Link Opening
Multiple ways to open TradingView charts:

1. **Individual Symbols**: Click any symbol name to open its chart
2. **Open All**: Opens all symbols in the folder at once
3. **Open by Tag**: Click tag badges (e.g., "📕 4") to open all symbols with that tag
4. **Batch Opening**:
   - Configurable batch sizes: 2x, 3x, 5x, or 10x
   - Opens symbols in controlled batches
   - Click "Next N" to continue to next batch
   - Progress tracking: "Opened X of Y symbols"
   - Stop button to pause batch opening
   - **Progress preserved** during notes/editing/removal

### ✏️ Edit Mode
Toggle edit mode per folder:
- Shows note (📝) and remove (✕) buttons
- Edit button changes to "Done" when active
- In compact view, controls appear on hover with overlay
- Add/edit notes without losing batch progress
- Remove symbols without resetting your position

### 🗑️ Symbol Management
- Remove individual symbols via ✕ button (in Edit mode)
- Confirmation dialog prevents accidental deletions
- **Batch progress preserved** when removing symbols
- Automatic index adjustment for remaining symbols

### ✅ Visual Feedback
- Clean, modern AMOLED dark theme
- Symbol cards with colored borders matching tags
- Success/info notifications for all actions
- Real-time progress tracking
- Confirmation dialogs for destructive actions
- Exchange prefixes (NSE:, BSE:) hidden in UI for cleaner display

### 📦 Data Sync & Backup
Complete backup and sync functionality:

**💾 Local Backup (Export/Import):**
- **Export**: Download complete backup as JSON
  - Includes: folders, symbols, tags, notes, journal, and rule book
  - Timestamped filename
- **Import**: Upload backup file to restore
  - Backward compatible with old format (folders only)
  - Shows summary before importing
- Transfer files via email, USB, cloud storage, etc.

**☁️ GitHub Gist Sync:**
- Sync all data across devices using free GitHub Gist
- **Upload**: Creates 3 files in your private Gist:
  - `watchlist-data.json` - Folders with symbols, tags, and notes
  - `trading-rulebook.txt` - Your trading rules
  - `trading-journal.txt` - Your trade journal
- **Download**: Restore all data from any device
- Auto-saves Gist ID for easy subsequent syncs
- Token stored locally and persists across sessions
- Test token validity before syncing

### 🎯 Minecraft-Style Favicon
- Custom pixelated brown dirt block favicon
- Minecraft aesthetic design
- Appears in browser tabs, bookmarks, and history

## How to Use

1. **Open the webpage**: Open `index.html` in any modern web browser

2. **Paste your data**:
   ```
   ### 11 Nov 2025,NSE:URBANCO, NSE:RUPA, NSE:SEAMECLTD, NSE:PREMEXPLN
   ### 12 Nov 2025,NSE:RELINFRA, NSE:KIRLPNU, BSE:TEXRAIL
   ```

3. **Click "Add"**: Your folders will appear with all symbols

4. **Organize with tags** (optional):
   - Click 🔖 icon on any symbol
   - Select a color tag from dropdown menu
   - Use tags to categorize by strategy, sector, risk, etc.

5. **Add notes to symbols**:
   - Click "Edit" button on folder
   - Click 📝 icon on any symbol
   - Write your analysis, targets, stop loss, etc.
   - Click "Save Note"

6. **Choose opening method**:
   - Click symbol names for individual charts
   - Use "Open All" for all symbols
   - Click tag badges (e.g., "📕 4") for tagged symbols
   - Use batch opening (select 2x/3x/5x/10x from dropdown)

7. **Manage view and layout**:
   - Use ▼/▶ to expand/collapse all folders
   - Switch between 📊 Detailed and 📋 Compact view
   - Adjust batch size (2x, 3x, 5x, 10x)

8. **Track your trading**:
   - Click 📖 to open Trading Journal & Rule Book
   - Write rules in Rule Book tab
   - Record trades in Journal tab
   - Click "Save" to store locally

9. **Backup and sync**:

   **Local Backup:**
   - Click 💾 to export all data
   - Click 📥 to import from backup file

   **Cloud Sync:**
   - Click ☁️ to open sync panel
   - Get GitHub token (click ? for instructions)
   - Click "Upload" to sync to cloud
   - On other device: Click "Download" and enter Gist ID
   - All data (folders, notes, journal, rules) syncs!

## Data Format

```
### FolderName, EXCHANGE:SYMBOL1, EXCHANGE:SYMBOL2, EXCHANGE:SYMBOL3
```

- Line must start with `###`
- First item after `###` is the folder name
- Remaining items are stock symbols in format `EXCHANGE:SYMBOL`
- Comma-separated values

## Example

```
### Momentum Plays,NSE:RELIANCE, NSE:TCS, NSE:INFY, NSE:HDFCBANK
### Breakout Watch,NSE:TATASTEEL, NSE:JSWSTEEL, BSE:SAIL
### Long Term Holdings,NSE:ITC, NSE:HINDUNILVR
```

## Technical Details

- **Technology**: Pure HTML, CSS, and JavaScript (no external dependencies)
- **Storage**: Browser localStorage API
- **Compatibility**: All modern browsers
- **Offline**: Fully functional offline after initial load
- **File Size**: ~2400 lines of code
- **Design**: Modern AMOLED dark theme
  - Pure black background (#000000) for AMOLED screens
  - Material Design elevation colors
  - Soft, eye-friendly accent colors
  - Optimized for performance - no GPU-intensive effects

### Responsive Design
Fully optimized for mobile devices:
- Reduced padding and spacing on mobile (≤768px)
- Full-width buttons for easier tapping
- Compact layout to minimize scrolling
- 2-column symbol grid on small screens (≤480px)
- Touch-friendly button sizes
- Stacked controls on mobile

## Button Controls

### Main Toolbar
- **Add**: Parse textarea and add folders
- **Clear**: Clear textarea without affecting saved folders
- **Clear All**: Remove all folders (with confirmation)
- **💾**: Export all data to JSON file
- **📥**: Import data from backup file
- **☁️**: Toggle GitHub Gist sync panel

### Folder Management (appears when folders exist)
- **▼**: Expand all folders
- **▶**: Collapse all folders
- **2x/3x/5x/10x**: Select batch opening size
- **📊/📋**: Toggle between Detailed and Compact view
- **📖**: Open Trading Journal & Rule Book

### Per Folder Controls
- **Folder Name**: Click to collapse/expand folder
- **Open All**: Open all symbols at once
- **Open N at a time**: Batch opening with selected size
- **Next N**: Continue to next batch (appears during batch mode)
- **Stop**: Stop batch opening
- **Edit**: Toggle edit mode (shows note/remove buttons)
- **Delete**: Remove entire folder (with confirmation)
- **Tag Badges** (e.g., 📕 4): Open all symbols with that tag

### Per Symbol Controls
- **Symbol Name**: Click to open TradingView chart
- **🔖**: Tag dropdown menu (assign/change color tag)
- **📝**: Add/edit note (visible in Edit mode)
- **✕**: Remove symbol (visible in Edit mode)

## Notes

### General
- **Auto-save**: All changes save to localStorage automatically
- **Folder Updates**: Pasting existing folder name updates symbols while preserving tags and notes
- **Clean Display**: Exchange prefixes hidden in UI but maintained in data
- **Browser Compatibility**: Works with Chrome, Firefox, Safari, Edge

### Tag Organization
Use color tags to categorize by:
- Trading strategy (Red = Breakout, Blue = Swing, etc.)
- Sector grouping
- Risk level or position size
- Time horizon (Short-term, Medium-term, Long-term)
- Any custom system you prefer

### Batch Opening
- Progress tracking shows "Opened X of Y symbols"
- **Progress preserved** when adding notes or removing symbols
- Stop button appears during batch operation
- Automatic index adjustment when symbols removed
- Prevents browser tab overload

### Notes System
- Add rich text notes to any symbol
- Notes preserved during folder updates
- Golden glow indicator in compact view
- Note preview in detailed view
- Notes sync via cloud backup

### Sync & Backup

**Export/Import:**
- Files named with timestamp: `watchlist-backup-2025-01-15T14-30-45.json`
- Import shows summary before replacing data
- Backward compatible with old format
- Transfer via any method (email, cloud, USB)

**GitHub Gist Sync:**
- Token stored locally (OS-encrypted via browser)
- Gist ID saved after first upload
- Private gists recommended (default)
- Free unlimited storage with GitHub
- Updates same gist on subsequent uploads
- Multiple devices sync to same Gist ID
- Download works without token for public gists
- Includes all data: folders, notes, journal, rules

## Security Features

### Data Protection
- **File Size Limits**: 10MB max for import/download
- **Data Validation**: Comprehensive validation of imported data
- **File Type Verification**: Only .json files accepted
- **No External Dependencies**: Zero third-party scripts
- **No Tracking**: Zero analytics or external tracking

### Token Security
- **Minimal Permissions**: Only `gist` scope required
- **Local Storage**: Token stored in browser localStorage
- **Clear Token**: One-click credential removal
- **Private Gists**: Default to private
- **Revocable**: Instantly revoke at github.com/settings/tokens

### Privacy
- **No Server**: Fully client-side application
- **Offline-First**: Works completely offline
- **Your Data Only**: Data never sent to third parties
- **Local Processing**: All operations in browser

### Best Practices
1. Only grant `gist` permission to GitHub token
2. Use "Clear Stored Token" on shared/public computers
3. Keep regular offline backups (💾 Export)
4. Use private gists (default) for sensitive data
5. Revoke token immediately if compromised
6. Test token validity before first sync

## Development

- **File**: `index.html` (single file application)
- **No Build Process**: Direct browser execution
- **No Dependencies**: Pure vanilla JavaScript
- **ES6+**: Modern JavaScript features
- **localStorage API**: For data persistence
- **Fetch API**: For GitHub Gist integration

## License

Free to use and modify for personal or commercial purposes.

## Credits

Built with vanilla JavaScript, HTML, and CSS. No frameworks, no dependencies, no nonsense.
