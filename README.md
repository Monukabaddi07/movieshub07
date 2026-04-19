# Advanced Video Player with Firebase Integration

A modern, responsive video player system supporting MP4 and HLS (M3U8) streaming with Firebase Realtime Database integration.

## Files

- **player.html** - Advanced video player with download functionality
- **update.html** - Video management interface for adding and managing videos
- **config-oCsEV.js** - Firebase configuration (keep your credentials secure)

## Features

### Player (player.html)
- ✅ Support for MP4 and HLS (M3U8) video formats
- ✅ Responsive design (Portrait & Landscape)
- ✅ Download button for videos
- ✅ Playback speed control (0.5x - 2x)
- ✅ Full-screen mode
- ✅ Custom styled controls with red accent
- ✅ Auto-detect video format

### Manager (update.html)
- ✅ Add videos with name, URL, and thumbnail
- ✅ Auto-generate video IDs (consonants only)
- ✅ View all uploaded videos in history tab
- ✅ Copy player links with one click
- ✅ Delete videos from database
- ✅ Beautiful two-tab interface

## How to Use

### 1. Adding Videos

1. Open `update.html` in your browser
2. Go to the "Add Video" tab
3. Fill in:
   - **Video Name**: The name of your video (e.g., "The Matrix")
   - **Video URL**: MP4 or M3U8 streaming URL
   - **Thumbnail URL**: Image URL for the video thumbnail
4. Click "Upload Video"
5. You'll get a player link like: `player.html?id=thmtrx01`

### 2. Playing Videos

1. Copy the generated link from update.html
2. Open the link in your browser, or
3. Manually use: `player.html?id=VIDEOID`

The player will automatically:
- Fetch video data from Firebase
- Detect MP4/HLS format
- Display video info and thumbnail
- Allow downloading and streaming

## ID Generation

Video IDs are generated from the video name using consonants only:
- "The Matrix" → `thmtrx01`
- "Hello World" → `hllwrld01`
- "Avatar" → `vtr01`

The last 2 digits are a timestamp suffix for uniqueness.

## Firebase Setup

Your Firebase config includes:
- Real-time Database for storing video metadata
- Automatic timestamps on uploads
- Video information: name, URL, thumbnail, upload date

## URL Parameters

**player.html** supports:
- `?id=VIDEOID` - Load and play a specific video

Example: `player.html?id=helloworld01`

## Responsive Design

Both pages are fully responsive:
- **Mobile (Portrait)**: Optimized touch controls, full-width layout
- **Mobile (Landscape)**: Compact controls, wide video area
- **Tablet**: Larger controls, balanced layout
- **Desktop**: Full-featured interface with all controls

## Technical Stack

- **Video.js** - Advanced video player with HLS support
- **Hls.js** - HLS protocol support
- **Firebase Realtime Database** - Cloud data storage
- **Vanilla JavaScript** - No build process required
- **CSS3** - Modern responsive styling

## Error Handling

- Invalid video IDs show error messages
- Missing Firebase connection displays helpful messages
- Failed video loads trigger error notifications
- All errors are logged to browser console

## Security Notes

- Keep your Firebase config credentials private
- Consider adding authentication for the update.html page
- Use HTTPS for production deployments
- Validate all URLs before adding to database

## Browser Compatibility

- Chrome/Edge 80+
- Firefox 75+
- Safari 13+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Troubleshooting

**"Firebase is not defined"**
- Wait for page to fully load
- Check browser console for errors
- Ensure Firebase scripts loaded successfully

**Video won't play**
- Verify video URL is correct
- Check if URL is accessible from your network
- Try both MP4 and M3U8 URLs
- Check browser console for specific errors

**No videos showing**
- Ensure Firebase database connection is active
- Check that videos were uploaded to correct database path
- Verify Firebase credentials in config

## License

Free to use and modify for your projects!
