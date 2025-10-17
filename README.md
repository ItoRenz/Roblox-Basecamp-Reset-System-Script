# 🏠 Roblox Basecamp Reset Script

A Roblox script that allows players to easily reset all checkpoints and return to basecamp with a single click or keyboard keystroke. It features a super minimalist, responsive toggle button that doesn't interrupt gameplay.

## ✨ Key Features

- **Ultra Minimalist Toggle Button** - An elegant house icon (⌂) in the top right corner of the screen, close to the end
- **Optimal Size** - Mobile: 32×32px |  PC: 36x36px (does not interfere with gameplay)
- **Responsive Design** - Button size automatically adjusts for PC and mobile
- **Smooth Animations** - Hover and click effects with smooth and fluid tweens
- **Multi-Platform Controls** - Click buttons or press the **R** key on PC, tap on mobile
- **Lightweight** - Script is lightweight and does not affect game performance
- **Modern UI** - Attractive corner radius, stroke border, and color transitions
- **Auto Device Detection** - Automatically detects player device (PC vs. mobile)
- **Error Handling** - Fallback system if basecamp is not found

## 📋 Requirements

- Roblox Studio or Roblox Game
- LocalScript in **StarterGui**
- Part named "Basecamp," "SpawnLocation," or "Base" in Workspace (optional)

## 🚀 Installation

1. Open your Roblox game in Roblox Studio
2. Log in  **StarterGui** in Explorer
3. Insert → **LocalScript**
4. Copy-paste the script from `basecamp_reset.lua`
5. Make sure there is a spawn/basecamp part in the workspace with one of the following names:
- `Basecamp`
- `SpawnLocation`
- `Base`
6. Test in game by pressing Play

## 🎯 How to Use

### PC Users
- **Click the ⌂** button in the top right corner
- **Press the R key** on the keyboard for an instant reset

### Mobile Users
- **Tap the ⌂** button in the top right corner to reset

## ⚙️ Customization

### Changing Button Color
Find the following line and change the RGB color:
```lua
toggleButton.BackgroundColor3 = Color3.fromRGB(59, 89, 152) -- Change the number  RGB
```

**Example colors:**
- Red: `Color3.fromRGB(255, 0, 0)`
- Green: `Color3.fromRGB(0, 255, 0)`
- Gold: `Color3.fromRGB(255, 215, 0)`

### Changing Icons/Emojis
Replace characters in the text:
```lua
toggleButton.Text = "⌂" -- Replace with ↻, 🏠, ⬆️, or other characters
```

### Changing Basecamp Name
Adjust to the name of the spawn part in your game:
```lua
local basecamp = workspace:FindFirstChild("Basecamp") -- Change "Basecamp"
```

### Changing Button Position
Edit the position parameter:
```lua
local buttonPosition =  UDim2.new(1, -42, 0, -2)
-- (-42 = distance from right, -2 = distance from top/bottom)
```

### Changing Button Size
```lua
local buttonSizeX = isMobile and 32 or 36
local buttonSizeY = isMobile and 32 or 36
-- Mobile: 32x32 | PC: 36x36
```

## 📱 Responsiveness

This script automatically detects the player's device:

| Device | Button Size | Icon Size | Position |
|--------|--------------|-----------|----------|
| Mobile | 32 × 32 px | 18 pt | Top Right Corner |
| PC | 36 × 36 px | 20 pt |  Top Right Corner |

 ## 🎨 UI Features

- **Hover Effect** - Button changes color to a brighter color when hovered
- **Click Animation** - Button scales down by 85% and scales up when clicked
- **Stroke Border** - Border with a modern blue color
- **Corner Radius** - Rounded corners (10px) for a smooth appearance
- **Notification** - Welcome message when the player spawns
- **Smooth Transitions** - All animations use the Tween service

## 📂 File Structure

```
roblox-basecamp-reset/
├── basecamp_reset.lua # Main script
└── README.md # Documentation
```

## 🐛 Troubleshooting

**Button not appearing?**
- Make sure the script is LocalScript in StarterGUI
- Check the Studio Output Console for error messages

**Reset not working?**
- Make sure there is a basecamp part in  Workspace
- Change the name "Basecamp" to match the name of your spawn section in the basecamp detection line.

Button too big/small?**
- Edit the `buttonSizeX` and `buttonSizeY` variables according to your preferences.

R keyboard not working on PC?**
- Make sure no TextBox or other input handlers are active.
- Check if any other scripts are overriding input.

Toggle Button covered by other UI elements.**
- Change the `buttonPosition` parameter to change the button position.

## 💡 Tips & Best Practices

- **Test before publishing** - Test the script in the studio before publishing the game.
- **Adjust colors** - Choose colors that match your game's theme.
- **Don't make the size too large.** - To avoid disrupting gameplay and other interactions.
- **Keyboard shortcuts** - Use rarely used keys to avoid conflicts.
- **Mobile optimization** - Test on various mobile screen sizes.

## 📝 License

Free to use and modify for your Roblox games.

##  👨‍💻 Author

Made with ❤️ for the Roblox Developer community

## 🤝 Contributing

If you have any suggestions or improvements, please create an issue or pull request!

---

**⭐ If this helps, please star it! Thanks!**

**Made with ❤️ for Roblox Developers**
