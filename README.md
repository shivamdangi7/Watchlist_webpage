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

### 🏷️ Color Tagging System
Organize your symbols with 5 color tags:
- **Red, Blue, Green, Orange, Purple** tags available for each symbol
- Click tag buttons below each symbol to assign/remove tags
- Only one tag per symbol (clicking a new tag replaces the old one)
- Symbol cards display colored borders based on their assigned tag
- Tag counts are shown in the "Open by Tag" section

### 🗑️ Symbol Management
- **Remove individual symbols**: Each symbol has an "✕" button to remove it from the folder
- Confirmation dialog prevents accidental deletions
- Removed symbols are permanently deleted from the folder

### 🔗 Smart Link Opening
Each folder provides multiple ways to open TradingView charts:

1. **Individual Symbol Buttons**: Click any symbol name to open its TradingView chart
2. **Open All**: Opens all symbols in the folder at once in separate tabs
3. **Open by Tag**: Opens all symbols with a specific color tag
   - Buttons appear only for tags that have symbols assigned
   - Shows count of symbols for each tag
   - Opens all tagged symbols in one click
4. **Open 2 at a time**:
   - Opens 2 symbols at a time
   - Shows progress tracking
   - Click "Next 2" to continue opening the next batch
   - Helps avoid browser tab overload
   - Can stop the process anytime with "Stop" button

### ✅ Visual Feedback
- Symbol cards display colored borders matching their assigned tag
- Success notifications when folders/symbols are added/deleted/tagged
- Real-time progress tracking for batch opening
- Confirmation dialogs for destructive actions (delete/remove)
- Tag buttons highlight when active

## How to Use

1. **Open the webpage**: Open `tradingview-links.html` in any modern web browser

2. **Paste your data**:
   ```
   ### 11 Nov 2025,NSE:URBANCO, NSE:RUPA, NSE:SEAMECLTD, NSE:PREMEXPLN
   ### 12 Nov 2025,NSE:RELINFRA, NSE:KIRLPNU, BSE:TEXRAIL
   ```

3. **Click "Add Folder"**: Your folders will appear below with all symbols as clickable buttons

4. **Tag your symbols** (optional):
   - Click the color tag buttons below each symbol
   - Assign Red, Blue, Green, Orange, or Purple tags
   - Use tags to categorize symbols by strategy, sector, etc.

5. **Choose your opening method**:
   - Click individual symbol names to open charts
   - Use "Open All" for quick access to all charts
   - Use tag buttons (e.g., "Red (4)") to open all symbols with that tag
   - Use "Open 2 at a time" for controlled batch opening

6. **Manage your symbols and folders**:
   - Click "✕" next to any symbol to remove it
   - Add more folders by pasting new data
   - Delete entire folders with the "Delete" button
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

### Tag Controls (per folder)
- **Red (N)**: Opens all symbols tagged with Red
- **Blue (N)**: Opens all symbols tagged with Blue
- **Green (N)**: Opens all symbols tagged with Green
- **Orange (N)**: Opens all symbols tagged with Orange
- **Purple (N)**: Opens all symbols tagged with Purple
- N indicates the number of symbols with that tag

### Symbol Controls (per symbol)
- **Symbol Name Button**: Click to open the symbol's TradingView chart
- **✕ Button**: Remove the symbol from the folder
- **Color Tag Buttons**: Click to assign/change the symbol's tag color

## Notes

- **Persistence**: All folders, symbols, and tags are automatically saved to localStorage and persist across browser sessions
- **Folder Updates**: If you paste data for a folder that already exists, it updates the symbols while preserving existing tags
- **Tag Organization**: Use color tags to categorize symbols by:
  - Trading strategy (e.g., Red = Breakout, Blue = Trend Following)
  - Sector or industry grouping
  - Risk level or position size
  - Any custom categorization system you prefer
- **One Tag Per Symbol**: Each symbol can only have one color tag at a time
- **Symbol Removal**: Removing a symbol permanently deletes it from the folder
- **Batch Opening**: The "Open 2 at a time" feature helps prevent overwhelming your browser with too many tabs at once
- **Browser Compatibility**: Works with all modern browsers that support localStorage