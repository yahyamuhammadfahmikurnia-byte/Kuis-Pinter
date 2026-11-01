# Tantangan Cerdas

Project game kuis yang dibuat dengan Unity. Pemain memilih jawaban, menerima umpan balik benar atau salah, dan memperoleh skor untuk jawaban yang benar.

## Persyaratan

- Unity **2021.3.18f1**
- Paket project dikelola melalui Unity Package Manager dan tercantum di `Packages/manifest.json`

## Menjalankan Project

1. Buka Unity Hub, pilih **Add**, lalu pilih folder project ini.
2. Buka project menggunakan Unity 2021.3.18f1.
3. Buka `Assets/Scenes/SampleScene.unity` jika scene belum terbuka.
4. Tekan **Play** di Unity Editor untuk menjalankan kuis.

## Struktur Utama

```text
Assets/
├── Scenes/          Scene permainan
├── kuis pawaji/     Folder aset kuis (saat ini kosong)
├── *.cs             Skrip logika game
├── *.anim           Klip animasi
├── *.controller     Animator Controller
├── *.png, *.jpg     Aset gambar
└── *.mp3            Efek suara
Packages/            Daftar dependensi Unity
ProjectSettings/     Pengaturan project dan konfigurasi build
```

Folder `Library/`, `Temp/`, `Logs/`, dan `UserSettings/` berisi data lokal atau hasil generate Unity. Folder-folder tersebut dapat dibuat kembali oleh Unity dan diabaikan oleh Git sesuai `.gitignore`.

## Skrip

- `Assets/jawab.cs`: menangani pilihan jawaban, menampilkan umpan balik, menambahkan 10 poin untuk jawaban benar, lalu mengaktifkan objek berikutnya dalam urutan sibling yang sama.
- `Assets/skor.cs`: mengatur skor menjadi 0 saat komponen dimulai dan menampilkan nilai skor pada komponen UI Text.
- `Assets/cx.cs`: belum berisi logika game.

Skor disimpan menggunakan `PlayerPrefs`. Pastikan referensi objek umpan balik benar dan urutan objek jawaban/pertanyaan di Hierarchy sesuai dengan alur kuis. Skrip `jawab.cs` mengharapkan ada objek berikutnya setelah objek jawaban yang dipilih.

## Scene Build

Scene yang saat ini terdaftar untuk build adalah `Assets/Scenes/SampleScene.unity`, sebagaimana diatur dalam `ProjectSettings/EditorBuildSettings.asset`.
