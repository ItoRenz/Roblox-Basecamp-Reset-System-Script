# 🏠 Roblox Basecamp Reset Script

A Roblox LocalScript that allows players to return to basecamp with a single click, complete with checkpoint reset and automatic healing. Fully compatible with sequential checkpoint systems.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Roblox](https://img.shields.io/badge/Roblox-Script-red)
![License](https://img.shields.io/badge/license-MIT-green)
![Compatibility](https://img.shields.io/badge/compatible-Sequential%20CP-orange)

## ✨ Features

- 🏠 **Instant Basecamp Teleport** - Return to spawn point with one click
- 🔄 **Sequential Checkpoint Reset** - Reset checkpoint progress to 0
- 🏆 **Summit Preservation** - Keeps summit achievements intact
- ❤️ **Auto Healing** - Restores full HP on reset
- 🎨 **Modern UI** - Elegant button with smooth animations
- 📱 **Cross-Platform** - Responsive for Mobile & PC
- ⚡ **Lightweight** - Zero performance impact
- 🎭 **Smooth Animations** - Pulse effects and hover states
- 🔒 **DataStore Safe** - Works seamlessly with existing save systems

## 🎮 Compatible Systems

This script is specifically designed for:
- ✅ **Sequential Checkpoint Systems** (anti-skip)
- ✅ **Obby/Tower Games** with progressive stages
- ✅ **StatsCore.server.lua** compatible
- ✅ **DataStore-based** save systems
- ✅ **Summit/Achievement** tracking

### System Requirements
- Sequential checkpoint numbering (CP 1, CP 2, CP 3...)
- Leaderstats with `Checkpoint` and `Summit` IntValues
- `CheckPoint` or `Checkpoint` folder in Workspace
- Optional: `Basecamp`, `SpawnLocation`, or `Base` part/folder

## 📸 Preview

The button appears in the top-right corner with a ⌂ (home) icon.

**Visual Features:**
- Smooth color transitions on hover
- Pulse animation on click
- Flash effect on border
- Informative notification on spawn
- Mobile-optimized touch support

## 📦 Installation

### Quick Setup

1. Open **Roblox Studio**
2. Open your game project
3. Navigate to **StarterGui**
4. Right-click → **Insert Object** → **LocalScript**
5. Copy-paste the script from `basecampReset.lua`
6. Rename the script (optional)
7. Test in-game!

### Detailed Setup

```
Workspace/
├── CheckPoint/ (or Checkpoint/)
│   ├── CP 1/
│   ├── CP 2/
│   └── CP 3/
├── Summit/
│   └── SummitPart
└── Basecamp/ (or SpawnLocation or Base)
    └── BasePart

StarterGui/
└── BasecampResetScript (LocalScript)

ServerScriptService/
└── StatsCore.server.lua (your checkpoint system)
```

## 🎮 Usage

### In-Game Controls

1. Join your game
2. Look for the ⌂ button in the top-right corner
3. Click/tap the button to:
   - Teleport to basecamp
   - Reset checkpoint progress to 0
   - Restore full health
   - Clear momentum/velocity

**Controls:**
- **PC:** Click button with mouse (hover for preview)
- **Mobile:** Tap button directly
- **Tablet:** Touch support enabled

### What Gets Reset?

✅ **Reset:**
- Checkpoint progress → 0
- Character position → Basecamp
- Health → 100%
- Velocity → Cleared
- Rotation → Normalized

❌ **Preserved:**
- Summit count (achievements)
- Player data/stats
- Inventory/tools
- Game progress

## ⚙️ Configuration

### Change Basecamp Name

Edit this section to match your basecamp object name:

```lua
local basecamp = workspace:FindFirstChild("Basecamp") 
    or workspace:FindFirstChild("SpawnLocation") 
    or workspace:FindFirstChild("Base")
    or workspace:FindFirstChild("Spawn")
```

### Customize Button Position

```lua
-- Button position (default: top-right corner)
local buttonPosition = UDim2.new(1, -42, 0, -2)

-- Examples:
-- Top-left: UDim2.new(0, 10, 0, -2)
-- Bottom-right: UDim2.new(1, -42, 1, -42)
-- Bottom-left: UDim2.new(0, 10, 1, -42)
```

### Adjust Button Size

```lua
-- Button dimensions
local buttonSizeX = isMobile and 32 or 36
local buttonSizeY = isMobile and 32 or 36

-- Make it larger:
local buttonSizeX = isMobile and 40 or 48
local buttonSizeY = isMobile and 40 or 48
```

### Customize Colors

```lua
-- Button background color
toggleButton.BackgroundColor3 = Color3.fromRGB(59, 89, 152) -- Blue

-- Border/stroke color
stroke.Color = Color3.fromRGB(100, 150, 220) -- Light Blue

-- Hover color
{BackgroundColor3 = Color3.fromRGB(79, 109, 172)} -- Lighter Blue
```

### Change Button Icon

```lua
-- Button text/icon
toggleButton.Text = "⌂"  -- Home icon

-- Alternatives:
-- "🏠" - House emoji
-- "↺" - Circular arrow
-- "⟲" - Anticlockwise arrow
-- "⌘" - Command symbol
-- "RST" - Reset text
```

## 🔧 Advanced Integration

### Custom Checkpoint System

If you have a custom checkpoint naming convention:

```lua
-- Example: Your checkpoints are named "Stage_1", "Stage_2"
local checkpoint = leaderstats:FindFirstChild("Stage")

-- Example: Your checkpoints use different variable names
local checkpoint = leaderstats:FindFirstChild("Level") 
    or leaderstats:FindFirstChild("Progress")
```

### Additional Reset Actions

Add custom logic after reset:

```lua
local function resetToBasecamp()
    -- ... existing code ...
    
    -- YOUR CUSTOM CODE HERE:
    -- Reset custom variables
    local customStats = player:FindFirstChild("CustomStats")
    if customStats then
        customStats.Power.Value = 0
        customStats.Speed.Value = 100
    end
    
    -- Fire custom events
    game.ReplicatedStorage.ResetEvent:FireServer()
    
    -- Play sound effect
    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://YOUR_SOUND_ID"
    sound.Parent = player.PlayerGui
    sound:Play()
end
```

## 📋 Compatibility Notes

### Works With:
- ✅ Sequential checkpoint systems (CP 1, 2, 3...)
- ✅ StatsCore-based progression
- ✅ DataStore save systems
- ✅ Leaderstats systems
- ✅ FilteringEnabled games
- ✅ R6 and R15 characters

### Limitations:
- ❌ Non-sequential checkpoints (free-roam style)
- ❌ Server-side only checkpoint systems
- ❌ Games without leaderstats
- ⚠️ Custom checkpoint names require modification

## 🛠️ Troubleshooting

### Button doesn't appear?
**Solution:**
- Ensure script is in **StarterGui** as a **LocalScript**
- Check Output console for error messages
- Verify `ResetOnSpawn = false` in ScreenGui properties
- Test in actual game, not Studio Edit mode

### Teleport not working?
**Solution:**
- Verify basecamp object exists in Workspace
- Check basecamp name matches script configuration
- Ensure basecamp has a solid BasePart
- Check that character has HumanoidRootPart

### Checkpoint doesn't reset?
**Solution:**
- Verify leaderstats exists with `Checkpoint` IntValue
- Check that StatsCore or similar system is running
- Ensure checkpoint naming matches (case-sensitive)
- Review server script for checkpoint management

### Button position off-screen?
**Solution:**
```lua
-- Adjust position values
local buttonPosition = UDim2.new(1, -50, 0, 10)
-- Format: UDim2.new(X_Scale, X_Offset, Y_Scale, Y_Offset)
```

### Performance issues?
**Solution:**
- Script is already optimized and lightweight
- Check for other conflicting scripts
- Reduce animation TweenInfo durations if needed
- Disable debug prints in production

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. Create a **feature branch**: `git checkout -b feature/AmazingFeature`
3. **Commit** your changes: `git commit -m 'Add AmazingFeature'`
4. **Push** to branch: `git push origin feature/AmazingFeature`
5. Open a **Pull Request**

### Contribution Guidelines
- Follow existing code style
- Add comments for complex logic
- Test thoroughly before submitting
- Update README if adding features
- Include screenshots/videos for UI changes

## 📝 Changelog

### Version 1.0.0 (October 18, 2025)
**Initial Release**
- ✨ Basecamp teleport functionality
- 🔄 Sequential checkpoint reset (0-based)
- 🏆 Summit preservation system
- ❤️ Automatic health restoration
- 🎨 Modern animated UI
- 📱 Mobile & PC responsive design
- ⚡ Velocity clearing
- 🔒 DataStore compatibility
- 📖 Comprehensive documentation

## 📄 License

Distributed under the **MIT License**. See `LICENSE` file for more information.

You are free to:
- ✅ Use commercially
- ✅ Modify the code
- ✅ Distribute
- ✅ Use privately

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Roblox: [@yourrobloxname](https://www.roblox.com/users/USERID/profile)
- Discord: YourDiscord#0000

## 🌟 Support the Project

If this script helped your game:
- ⭐ **Star** this repository
- 🐛 **Report bugs** via Issues
- 💡 **Suggest features** in Discussions
- 🔀 **Contribute** via Pull Requests
- 📢 **Share** with other developers

## 🔗 Related Projects

- [StatsCore System](https://github.com/yourusername/stats-core) - Checkpoint management
- [Obby Framework](https://github.com/yourusername/obby-framework) - Complete obby system
- [UI Library](https://github.com/yourusername/ui-library) - Roblox UI components

## 📞 Contact & Support

**Need help?**
- 📧 Email: your.email@example.com
- 💬 Discord Server: [Join Here](https://discord.gg/yourserver)
- 🎮 Roblox Group: [Your Group](https://www.roblox.com/groups/GROUPID)
- 🐛 Bug Reports: [GitHub Issues](https://github.com/yourusername/repo/issues)
- 💡 Feature Requests: [GitHub Discussions](https://github.com/yourusername/repo/discussions)

## ⚠️ Disclaimer

This script is provided "as-is" without warranty. Always test thoroughly before using in production games. The author is not responsible for any issues arising from the use of this script.

## 🙏 Acknowledgments

- Roblox Developer Community
- Contributors and testers
- Users who provided feedback

---

**Made with ❤️ for the Roblox Developer Community**

*If you use this in your game, consider crediting in your game's description!*
