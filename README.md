# A1111 Metadata Embedder - iOS PWA

A Progressive Web App that embeds AUTOMATIC1111 metadata into PNG images, making them CivitAI compatible.

## Features

✨ Works entirely offline after installation
📱 Installable as an iOS Home Screen app
🎨 Beautiful gradient UI optimized for mobile
📸 Drag & drop or tap to select images
🔒 100% client-side processing (no uploads)
✅ CivitAI compliant metadata embedding

## Installation Instructions

### For iOS (iPhone/iPad):

1. **Upload the files to a web server or GitHub Pages:**
   - Upload `a1111-metadata-app.html`, `manifest.json`, `sw.js`, and `icon.png` to your web hosting
   - Make sure all files are in the same directory
   - Access the HTML file via HTTPS (required for PWA features)

2. **Add to Home Screen:**
   - Open Safari and navigate to your hosted app URL
   - Tap the Share button (square with arrow pointing up)
   - Scroll down and tap "Add to Home Screen"
   - Name it "A1111 Meta" or whatever you prefer
   - Tap "Add"

3. **Launch the app:**
   - Find the new icon on your home screen
   - It will open as a full-screen app without Safari's UI

### Quick Local Testing:

If you want to test locally first:

```bash
# Simple Python server
python3 -m http.server 8000

# Then visit http://localhost:8000/a1111-metadata-app.html
```

Note: PWA features (home screen install) require HTTPS, so local testing won't allow installation.

## How to Use

1. **Open the app** from your home screen
2. **Tap or drag** an image into the drop zone
3. **Paste your A1111 parameters** in the text area, for example:
   ```
   masterpiece, best quality, 1girl, portrait, detailed face
   Negative prompt: bad quality, low res, blurry
   Steps: 20, Sampler: DPM++ 2M Karras, CFG scale: 7, Seed: 123456789, Size: 512x768, Model: realistic_v3
   ```
4. **Tap "Embed & Download"**
5. Your image will download with metadata embedded as a PNG tEXt chunk with "parameters" keyword

## Technical Details

- Embeds metadata as PNG tEXt chunks (CivitAI standard)
- Uses the "parameters" keyword for A1111 compatibility
- Properly calculates CRC32 checksums for PNG chunks
- Converts non-PNG images to PNG before embedding
- All processing happens in your browser

## Files Included

- `a1111-metadata-app.html` - Main app file
- `manifest.json` - PWA manifest for installation
- `sw.js` - Service worker for offline functionality
- `icon.png` - App icon (512x512)

## Hosting Options

### GitHub Pages (Free & Easy):
1. Create a new GitHub repository
2. Upload all 4 files
3. Enable GitHub Pages in repository settings
4. Access via `https://yourusername.github.io/repo-name/a1111-metadata-app.html`

### Other options:
- Netlify (drag & drop deployment)
- Vercel (instant deployment)
- Your own web hosting

## Troubleshooting

**"Add to Home Screen" not showing:**
- Make sure you're using Safari (not Chrome or Firefox on iOS)
- Ensure the site is served over HTTPS
- Try refreshing the page

**Downloads not working:**
- Check Safari's download settings
- Ensure you've granted necessary permissions

**Metadata not embedding:**
- Verify your metadata format matches A1111 output
- Check browser console for errors

## Privacy

This app works 100% offline after installation. No data is ever uploaded to any server. All image processing happens locally in your browser.
