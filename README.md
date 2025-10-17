# Basecamp Reset System

A Roblox checkpoint reset system that allows players to instantly reset their progress and return to basecamp while preserving their permanent achievements.

## Features

✨ **Instant Checkpoint Reset** - Reset progression to 0 with one click  
🏔️ **Summit Preservation** - Summit achievements remain safe and unaffected  
📱 **Mobile & PC Support** - Works seamlessly on both platforms  
🎨 **Modern UI** - Elegant button with smooth animations and hover effects  
⚡ **Lightweight** - Minimal performance impact  
🔒 **Server-Side Validation** - Secure checkpoint changes via RemoteEvent  

## Installation

### Prerequisites
- Roblox Studio
- Basic understanding of Lua scripting
- Existing leaderstats system (Checkpoint & Summit values)

### Setup Instructions

#### Step 1: Client Script (LocalScript)

1. Open your Roblox game in Studio
2. Navigate to **StarterGui** in the Explorer panel
3. Right-click → **Insert Object** → **LocalScript**
4. Rename to `BasecampResetClient` (optional)
5. Copy and paste the entire Client Script code
6. Save (Ctrl+S)

**Location:** `StarterGui → BasecampResetClient (LocalScript)`

#### Step 2: Server Script

1. Navigate to **ServerScriptService** in the Explorer
2. Right-click → **Insert Object** → **Script** (NOT LocalScript)
3. Rename to `BasecampResetServer` (optional)
4. Copy and paste the entire Server Script code
5. Save

**Location:** `ServerScriptService → BasecampResetServer (Script)`

#### Step 3: Verify Installation

After both scripts are in place, check the Output console:

```
✓ Checkpoint Reset Server Event Active!
✓ Listening for reset commands from clients...
✓ Basecamp Reset Script Loaded (CLIENT)!
```

## Usage

### In-Game Usage

1. Click **Play** (▶) to start your game
2. Look for the **⌂** button in the **top-right corner** of your screen
3. Click (PC) or tap (Mobile) the button to reset

### What Happens on Reset

- ✓ Checkpoint value reset to 0
- ✓ Summit value preserved (permanent achievement)
- ✓ Character teleported to Basecamp
- ✓ Health fully restored
- ✓ Velocity and rotation reset

## Configuration

### Button Position

Edit this line in the Client Script:

```lua
local buttonPosition = UDim2.new(1, -42, 0, -2)
```

- `1, -42` = 42px from the right
- `0, -2` = 2px from the top

Adjust the negative values to change positioning.

### Button Size

```lua
local buttonSizeX = isMobile and 32 or 36
local buttonSizeY = isMobile and 32 or 36
```

- Mobile: 32×32 pixels
- PC: 36×36 pixels

Modify the numbers to change button dimensions.

### Button Color

```lua
toggleButton.BackgroundColor3 = Color3.fromRGB(59, 89, 152)
```

Replace RGB values (0-255) with your preferred colors.

### Notification Duration

```lua
showNotification("Your text", 5)  -- 5 seconds
```

Change the second parameter to adjust how long the notification displays.

## Compatibility

- ✅ Sequential CP System
- ✅ Summit System
- ✅ Custom leaderstats variations
- ✅ Mobile & PC devices
- ✅ Roblox Studio (all recent versions)

## File Structure

```
├── README.md
├── src/
│   ├── client/
│   │   └── BasecampResetClient.lua (LocalScript)
│   └── server/
│       └── BasecampResetServer.lua (Script)
└── .gitignore
```

## Troubleshooting

### Button Not Appearing

- Ensure **LocalScript is in StarterGui**
- Check Console Output for errors (View → Output)
- Verify `ResetOnSpawn = false` is set

### Checkpoint Not Resetting

- Ensure **Server Script is in ServerScriptService**
- Check Server Output for errors
- Verify leaderstats are created before player spawn

### Teleport Not Working

- Verify Basecamp exists in workspace (check names: Basecamp, SpawnLocation, Base, or Spawn)
- Ensure Basecamp contains at least one BasePart
- Check character HumanoidRootPart exists

### Animation Feels Laggy

- Reduce TweenService duration values
- Disable UIStroke effects if needed
- Check for other UI elements causing conflicts

## Technical Details

### Communication Flow

```
Client Click
    ↓
FireServer("ResetCheckpoint")
    ↓
Server Receives Event
    ↓
Reset Checkpoint Value (leaderstats)
    ↓
Client Teleports Character
    ↓
Reset Character State
```

### Remote Event

- **Name:** `ResetCheckpointEvent`
- **Location:** `ReplicatedStorage`
- **Type:** RemoteEvent
- **Auto-Created:** Yes (if doesn't exist)

### Supported Checkpoint Names

- Checkpoint
- CheckPoint
- checkpoint
- CHECKPOINT

### Supported Summit Names

- Summit
- summit
- SUMMIT

## Performance

- **Memory Usage:** < 2 MB
- **Network Traffic:** Minimal (only on button click)
- **UI Rendering:** Optimized animations
- **Server Load:** Negligible

## Security Notes

- Server-side validation ensures checkpoint changes are legitimate
- Client cannot modify leaderstats directly
- All changes are validated on the server
- RemoteEvent prevents exploits via rate limiting

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

This project is provided as-is for use in Roblox games.

## Credits

Developed for Sequential CP + Summit System compatibility.

## Support

For issues or questions:
1. Check the Troubleshooting section
2. Verify installation steps
3. Check Console Output for error messages
4. Review script comments for more details

## Changelog

### Version 1.0.0
- Initial release
- Client & Server script separation
- Mobile & PC support
- Modern UI with animations
- Full documentation

---

**Last Updated:** 2024  
**Status:** Stable ✅
