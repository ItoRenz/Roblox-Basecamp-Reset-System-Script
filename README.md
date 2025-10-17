# Roblox Basecamp Reset Script

Sebuah script Roblox yang memungkinkan player dengan mudah untuk reset semua checkpoint dan kembali ke basecamp dengan satu klik atau tombol keyboard. Dilengkapi toggle button yang minimalis, responsif, dan tidak mengganggu gameplay.

## 🎮 Fitur Utama

- **Toggle Button Minimalis** - Ikon rumah (⌂) yang elegan di pojok kanan atas layar
- **Responsive Design** - Ukuran button otomatis menyesuaikan untuk PC dan Mobile
- **Smooth Animations** - Efek hover dan click dengan Tween yang smooth
- **Multi-Platform Controls** - Klik button atau tekan tombol **R** di PC, tap untuk Mobile
- **Lightweight** - Script ringan dan tidak mempengaruhi performa game
- **Modern UI** - Corner radius, stroke border, dan color transitions yang menarik

## 📋 Requirements

- Roblox Studio atau Roblox Game
- LocalScript di **StarterGui**
- Part bernama "Basecamp", "SpawnLocation", atau "Base" di Workspace (opsional)

## 🚀 Instalasi

1. Buka game Roblox kamu di Roblox Studio
2. Masuk ke **StarterGui** di Explorer
3. Insert → **LocalScript**
4. Paste script dari file `basecamp_reset.lua`
5. Pastikan ada spawn/basecamp part di workspace dengan nama salah satu dari:
   - `Basecamp`
   - `SpawnLocation`
   - `Base`
6. Test di game

## 🎯 Cara Menggunakan

### PC Users
- **Klik button** ⌂ di pojok kanan atas
- **Tekan tombol R** di keyboard untuk instant reset

### Mobile Users
- **Tap button** ⌂ di pojok kanan atas untuk reset

## ⚙️ Customization

### Mengubah Warna Button
Cari line berikut dan ubah RGB color:
```lua
toggleButton.BackgroundColor3 = Color3.fromRGB(59, 89, 152) -- Ubah angka ini
```

### Mengubah Icon/Emoji
Ganti karakter dalam kurip:
```lua
toggleButton.Text = "⌂"  -- Ubah dengan ↻, 🏠, atau karakter lain
```

### Mengubah Nama Basecamp
Sesuaikan dengan nama part spawn di game kamu:
```lua
local basecamp = workspace:FindFirstChild("Basecamp") -- Ubah "Basecamp" sesuai nama part
```

### Mengubah Posisi Button
Edit parameter position:
```lua
local buttonPosition = UDim2.new(1, -75, 0, 15) -- (-75 = jarak dari kanan, 15 = jarak dari atas)
```

### Mengubah Ukuran Button
```lua
local buttonSize = isMobile and UDim2.new(0, 50, 0, 50) or UDim2.new(0, 60, 0, 60)
-- Mobile: 50x50 | PC: 60x60
```

## 📱 Responsiveness

Script ini secara otomatis mendeteksi device player:

| Device | Button Size | Icon Size |
|--------|-------------|-----------|
| Mobile | 50 × 50 px | 22 pt |
| PC | 60 × 60 px | 26 pt |

## 🎨 UI Features

- **Hover Effect** - Button berubah warna saat di-hover
- **Click Animation** - Button scale down dan scale up saat diklik
- **Stroke Border** - Border dengan gradient blue yang modern
- **Corner Radius** - Sudut rounded untuk tampilan smooth
- **Notification** - Pesan welcome saat spawn

## 📂 File Structure

```
roblox-basecamp-reset/
├── basecamp_reset.lua          # Main script
├── README.md                   # Dokumentasi
└── COMMIT_HISTORY.md          # Commit messages
```

## 🐛 Troubleshooting

**Button tidak muncul?**
- Pastikan script adalah LocalScript di StarterGui
- Check Console untuk error messages

**Reset tidak berfungsi?**
- Pastikan ada part basecamp di workspace
- Ubah nama "Basecamp" sesuai dengan nama part kamu

**Button terlalu besar/kecil?**
- Edit `buttonSize` variable sesuai preferensi

**Keyboard R tidak bekerja?**
- Pastikan tidak ada input handler lain yang conflict
- Cek apakah ada TextBox yang aktif (gameProcessed check)

## 💡 Tips

- Gunakan huruf unik untuk keyboard shortcut agar tidak conflict
- Test script di game sebelum di-publish
- Adjust ukuran button untuk preferensi player kamu
- Kombinasikan dengan game mechanic lain untuk user experience lebih baik

## 📝 License

Free to use and modify for your Roblox games

## 👨‍💻 Author

Dibuat dengan ❤️ untuk komunitas Roblox

## 🤝 Contributing

Jika ada saran atau improvement, silakan buat issue atau pull request!

---

**Made with ❤️ for Roblox Developers**
