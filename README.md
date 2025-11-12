# TradingView Link Manager

A web-based tool for managing and opening TradingView chart links for multiple stock symbols organized in folders.

## Features

### 📋 Clipboard Data Parsing
- Paste formatted stock data into the textarea
- Format: `### Date/Folder Name, NSE:SYMBOL1, NSE:SYMBOL2, BSE:SYMBOL3`
- Automatically extracts folder names and stock symbols
- Supports both NSE and BSE exchanges

### 💾 Persistent Storage
- All folders are automatically saved to browser's localStorage
- Folders persist across browser sessions
- Your watchlists are preserved even after closing the page

### ➕ Multiple Folder Management
- Add multiple folders by pasting new data
- Folders are cached - they don't get replaced when adding new ones
- Update existing folders by pasting data with the same folder name
- Delete individual folders with the "Delete" button
- Clear all folders at once with "Clear All Folders" button

### 🔗 Smart Link Opening
Each folder provides multiple ways to open TradingView charts:

1. **Individual Symbol Buttons**: Click any symbol to open its TradingView chart
2. **Open All**: Opens all symbols in the folder at once in separate tabs
3. **Open 2 at a time**:
   - Opens 2 symbols at a time
   - Shows progress tracking
   - Click "Next 2" to continue opening the next batch
   - Helps avoid browser tab overload
   - Can stop the process anytime with "Stop" button

### ✅ Visual Feedback
- Opened symbols are highlighted in green
- Success notifications when folders are added/deleted
- Real-time progress tracking for batch opening
- Confirmation dialogs for destructive actions

## How to Use

1. **Open the webpage**: Open `tradingview-links.html` in any modern web browser

2. **Paste your data**:
   ```
   ### 11 Nov 2025,NSE:URBANCO, NSE:RUPA, NSE:SEAMECLTD, NSE:PREMEXPLN
   ### 12 Nov 2025,NSE:RELINFRA, NSE:KIRLPNU, BSE:TEXRAIL
   ```

3. **Click "Add Folder"**: Your folders will appear below with all symbols as clickable buttons

4. **Choose your opening method**:
   - Click individual symbols as needed
   - Use "Open All" for quick access to all charts
   - Use "Open 2 at a time" for controlled batch opening

5. **Manage your folders**:
   - Add more folders by pasting new data
   - Delete folders you no longer need
   - Clear input box after adding folders

## Data Format

The input format is simple:
```
### FolderName, EXCHANGE:SYMBOL1, EXCHANGE:SYMBOL2, EXCHANGE:SYMBOL3
```

- Line must start with `###`
- First item after `###` is the folder name
- Remaining items are stock symbols in format `EXCHANGE:SYMBOL`
- Supported exchanges: NSE, BSE, and others supported by TradingView

## Example

```
### 11 Nov 2025,NSE:URBANCO, NSE:RUPA, NSE:SEAMECLTD, NSE:PREMEXPLN, NSE:STERTOOLS, NSE:MADRASFERT
### 12 Nov 2025,NSE:RELINFRA, NSE:KIRLPNU, BSE:TEXRAIL, NSE:MOTHERSON
```

## Technical Details

- **Technology**: Pure HTML, CSS, and JavaScript (no external dependencies)
- **Storage**: Browser localStorage API
- **Compatibility**: Works with all modern browsers
- **Offline**: Fully functional offline after initial load

## Button Controls

### Main Controls
- **Add Folder**: Parses the textarea and adds folders to your list
- **Clear Input**: Clears the textarea without affecting saved folders
- **Clear All Folders**: Removes all saved folders (with confirmation)

### Folder Controls
- **Open All**: Opens all symbols in the folder simultaneously
- **Open 2 at a time**: Opens symbols in batches of 2 with manual progression
- **Stop**: Stops the batch opening process
- **Delete**: Removes the specific folder (with confirmation)

## Notes

- Folders are automatically saved and will be available when you revisit the page
- If a folder with the same name already exists, it will be updated with new symbols
- Opened symbols are visually marked (green) to track which ones you've already viewed
- The batch opening feature helps prevent overwhelming your browser with too many tabs at once