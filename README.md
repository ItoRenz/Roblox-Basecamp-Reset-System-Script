# 🏠 Roblox Basecamp Reset Script

Script Roblox yang memungkinkan player untuk kembali ke basecamp dengan satu klik tombol, lengkap dengan reset checkpoint dan healing otomatis.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Roblox](https://img.shields.io/badge/Roblox-Script-red)
![License](https://img.shields.io/badge/license-MIT-green)

## ✨ Fitur

- 🏠 **Teleport ke Basecamp** - Kembali ke spawn point dengan satu klik
- 🔄 **Reset Checkpoint** - Menghapus checkpoint/stage yang tersimpan
- ❤️ **Auto Healing** - Mengisi HP penuh saat reset
- 🎨 **UI Modern** - Button elegan dengan animasi smooth
- 📱 **Mobile & PC Support** - Responsive untuk semua device
- ⚡ **Lightweight** - Tidak membebani performa game
- 🎭 **Animasi Smooth** - Pulse effect dan hover animation

## 📸 Preview

Button akan muncul di pojok kanan atas layar dengan icon ⌂ (home).

**Fitur Visual:**
- Hover effect dengan perubahan warna smooth
- Pulse animation saat di-klik
- Flash effect pada border
- Notifikasi saat script aktif

## 📦 Instalasi

1. Buka Roblox Studio
2. Buka game project Anda
3. Navigasi ke **StarterGui**
4. Klik kanan → **Insert Object** → **LocalScript**
5. Copy-paste script dari file `basecampReset.lua`
6. Rename script (opsional)
7. Test di game!

## 🎮 Cara Penggunaan

1. Join game Anda
2. Lihat button ⌂ di pojok kanan atas
3. Klik button untuk:
   - Teleport ke basecamp
   - Reset checkpoint/stage
   - Heal HP penuh

**Kontrol:**
- **PC:** Klik button dengan mouse
- **Mobile:** Tap button

## ⚙️ Konfigurasi

### Mengubah Nama Basecamp

Edit bagian ini di script untuk menyesuaikan nama basecamp Anda:

```lua
local basecamp = workspace:FindFirstChild("Basecamp") 
    or workspace:FindFirstChild("SpawnLocation") 
    or workspace:FindFirstChild("Base")
```

### Mengubah Posisi Button

```lua
-- Posisi button (default: pojok kanan atas)
local buttonPosition = UDim2.new(1, -42, 0, -2)
```

### Mengubah Ukuran Button

```lua
-- Ukuran button
local buttonSizeX = isMobile and 32 or 36
local buttonSizeY = isMobile and 32 or 36
```

### Mengubah Warna

```lua
-- Warna button
toggleButton.BackgroundColor3 = Color3.fromRGB(59, 89, 152)

-- Warna border/stroke
stroke.Color = Color3.fromRGB(100, 150, 220)
```

## 🔧 Kompatibilitas

Script ini kompatibel dengan:
- ✅ Stage-based Obbies
- ✅ Tower Games
- ✅ Adventure Games
- ✅ Checkpoint Systems
- ✅ RespawnLocation Systems
- ✅ Leaderstats Stage Systems

**Tested on:**
- Mobile (iOS & Android)
- PC (Windows & Mac)
- Tablet

## 📋 Requirements

- Roblox Studio
- LocalScript support
- StarterGui access

**Tidak memerlukan:**
- Server scripts
- RemoteEvents
- DataStore
- HTTP Service

## 🛠️ Troubleshooting

### Button tidak muncul?
- Pastikan script ada di **StarterGui** sebagai **LocalScript**
- Check console untuk error messages
- Pastikan `ResetOnSpawn = false` di ScreenGui

### Teleport tidak bekerja?
- Pastikan ada Part bernama "Basecamp", "SpawnLocation", atau "Base" di Workspace
- Check posisi basecamp (harus ada collision)
- Pastikan character memiliki HumanoidRootPart

### Checkpoint tidak reset?
- Check apakah game menggunakan custom checkpoint system
- Modifikasi fungsi `resetCheckpoint()` sesuai sistem game Anda
- Hubungi developer untuk custom implementation

## 🤝 Contributing

Kontribusi sangat diterima! Silakan:

1. Fork repository ini
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📝 Changelog

### Version 1.0.0 (2025-10-18)
- ✨ Initial release
- 🏠 Basecamp teleport feature
- 🔄 Checkpoint reset system
- ❤️ Auto healing
- 🎨 Modern UI with animations
- 📱 Mobile & PC support

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 👤 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- Roblox: [@yourrobloxname](https://www.roblox.com/users/USERID/profile)

## 🌟 Support

Jika script ini membantu, berikan ⭐ star pada repository!

**Found a bug?** Open an issue
**Have suggestions?** Create a discussion
**Want to contribute?** Submit a pull request

## 📞 Contact

- Discord: YourDiscord#0000
- Email: your.email@example.com
- Roblox Group: [Your Group](https://www.roblox.com/groups/GROUPID)

---

Made with ❤️ for Roblox Community
