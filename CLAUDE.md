# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Orlando vacation packing list web application - a single-page HTML application with embedded CSS and JavaScript that helps families track their packing progress for an Orlando trip.

## Architecture

The application is a self-contained single-file web application (`index.html`) that includes:
- **Firebase Integration**: Uses Firebase Realtime Database for real-time data synchronization across devices and Google Authentication for user management
- **Local Storage Fallback**: Falls back to localStorage when Firebase is not available or user is not authenticated
- **No Build Process**: Pure HTML/CSS/JavaScript with no build tools or dependencies beyond Firebase SDK

## Key Implementation Details

### Data Persistence
The app uses a dual storage approach:
1. **Firebase Realtime Database** (when authenticated): Syncs data across devices in real-time
2. **localStorage** (fallback): Stores data locally when offline or not authenticated

### State Management
- All checkbox states and custom items are automatically saved on change
- Dark mode preference is stored separately
- Progress tracking updates dynamically

### Categories Structure
The packing list is organized into 7 predefined categories:
1. Medical & Health (💊)
2. Electronics (📱)
3. Parks & Activities (🎢)
4. Parents' Clothing (👔)
5. Teen items (🎧)
6. 13-year-old items (🎮)
7. 8-year-old items (🧸)

## Deployment

The site is deployed on GitHub Pages at: https://drorlazar.github.io/Orlando/

To deploy updates:
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

Changes will be automatically reflected on the live site within a few minutes.

## Development

Since this is a single HTML file with no build process:
1. Edit `index.html` directly
2. Test by opening the file in a browser
3. Commit and push to update the live site

## Testing Considerations

- Test both authenticated (with Google account) and non-authenticated states
- Verify data persistence across page refreshes
- Check dark mode toggle functionality
- Test on mobile devices for responsive design
- Verify RTL (right-to-left) Hebrew text display