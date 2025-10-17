# 🏠 Roblox Basecamp Reset Button

A sleek and modern GUI button for Roblox that allows players to instantly teleport back to their basecamp/spawn location with a single click.

## ✨ Features

- 🎯 **One-Click Reset** - Instantly teleport back to basecamp
- 📱 **Cross-Platform** - Works on both PC and Mobile
- 🎨 **Modern UI Design** - Clean, minimal interface with smooth animations
- 🔘 **Button-Only Control** - No keyboard shortcuts to prevent accidental resets
- 💫 **Smooth Animations** - Hover effects and click feedback
- 📍 **Smart Detection** - Automatically finds basecamp/spawn location
- 🔔 **Visual Notifications** - Clear feedback when reset is successful

## 🎮 Installation

1. Open Roblox Studio
2. Navigate to **StarterGui**
3. Insert a new **LocalScript**
4. Copy and paste the entire script code
5. Make sure you have a part named `Basecamp`, `SpawnLocation`, or `Base` in your workspace

## 🔧 Configuration

### Basecamp Detection
The script automatically searches for these part names in order:
- `Basecamp`
- `SpawnLocation`
- `Base`

To customize, edit line 21:
```lua
local basecamp = workspace:FindFirstChild("YourBasecampName")
```

### Button Size
- **Mobile**: 32x32 pixels
- **PC**: 36x36 pixels

Adjust on lines 46-48:
```lua
local buttonSizeX = isMobile and 32 or 36
local buttonSizeY = isMobile and 32 or 36
```

### Button Position
Currently positioned at top-right corner. Modify line 50:
```lua
local buttonPosition = UDim2.new(1, -42, 0, -2)
```

### Colors
- **Button Color**: RGB(59, 89, 152) - Elegant Blue
- **Hover Color**: RGB(79, 109, 172) - Light Blue
- **Border Color**: RGB(100, 150, 220) - Sky Blue

Customize on lines 60 and 72-84.

## 🎨 UI Customization

### Change Button Icon
Replace the home icon (⌂) on line 66:
```lua
toggleButton.Text = "⌂"  -- Change to any emoji or text
```

### Notification Duration
Default: 4 seconds. Change on line 149:
```lua
showNotification("Your message here", 4)
```

## 📋 Requirements

- Roblox Studio
- LocalScript in StarterGui
- A designated basecamp/spawn part in workspace
- No external dependencies

## 🚀 How It Works

1. **Platform Detection**: Automatically detects if player is on Mobile or PC
2. **Character Check**: Verifies character and HumanoidRootPart exist
3. **Basecamp Search**: Finds the basecamp part in workspace
4. **Teleportation**: Moves character 3 studs above basecamp position
5. **Feedback**: Shows visual notification of successful reset

## 🎯 Usage

### For Players
- **PC**: Click the ⌂ button in the top-right corner
- **Mobile**: Tap the ⌂ button in the top-right corner

### For Developers
```lua
-- Call reset function directly
resetToBasecamp()
```

## ⚠️ Troubleshooting

### Button Not Appearing
- Ensure script is in **StarterGui**
- Check if it's a **LocalScript** (not Script)
- Wait for character to fully load

### Teleport Not Working
- Verify basecamp part exists in workspace
- Check part name matches: `Basecamp`, `SpawnLocation`, or `Base`
- Ensure character has `HumanoidRootPart`

### Mobile Issues
- Check if `TouchEnabled` is properly detected
- Verify button size is appropriate for mobile screens

## 🔄 Version History

### v1.1.0 (Current)
- ✅ Removed keyboard shortcut functionality
- ✅ Button-only control to prevent accidental resets
- ✅ Updated notification text
- ✅ Improved cross-platform consistency

### v1.0.0
- 🎉 Initial release
- ✨ Basic reset functionality
- 🎨 Modern UI design
- 📱 Mobile support

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

Created with ❤️ for the Roblox development community

## 🌟 Show Your Support

Give a ⭐️ if this project helped you!

## 📞 Support

If you have any questions or need help, please open an issue on GitHub.

---

**Note**: This script is designed for Roblox games and requires Roblox Studio to implement.
