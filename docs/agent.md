# Langkah-Langkah Role Agent

Panduan praktis menjalankan role agent di testnet FLOP, dari membuat identitas sampai rutinitas harian. Konsep di balik langkah-langkah ini dijelaskan di [konsep.md](konsep.md).

## Prasyarat

- Laptop atau HP yang bisa membuat passkey (Windows Hello / biometrik).
- Akses ke [Technocore](https://technocore.chat/humans).
- Wallet crypto (untuk kebutuhan agent berikutnya saat enrollment dibuka).
- Tidak perlu: GPU, server, modal uang asli.

## Langkah 1 — Buat DID lewat Technocore

1. Buka [technocore.chat/humans](https://technocore.chat/humans).
2. Buat **passkey** — perangkatmu akan meminta Windows Hello atau biometrik.
3. Identitasmu langsung dibuat; DID-mu tampil dalam format `did:key:z6Mk...`.
4. Catat DID-mu di tempat yang aman. DID itu publik, mencatatnya tidak berisiko.

Hasil langkah ini: satu identitas FLOP yang melekat pada passkey di perangkatmu.

## Langkah 2 — Pahami hubungan DID dan passkey

DID adalah identitasnya; passkey adalah satu-satunya cara masuk ke identitas itu. Jika passkey hilang atau perangkat berganti tanpa passkey yang sama, DID lama tidak bisa dipakai lagi dan seluruh riwayatnya hangus — DID baru berarti mulai dari awal.

Pengalaman penulis: pada 26 November 2026 passkey lama tidak bisa dibuka lagi, sehingga penulis berganti DID baru dan klaim dua hari sebelumnya tidak lagi terhubung. Jadikan ini pengingat untuk memakai perangkat yang benar-benar kamu pegang setiap hari, dan untuk mengenali DID-mu sendiri — kalau suatu hari yang tampil adalah DID yang berbeda, itu tanda identitasmu berganti.

## Langkah 3 — Sign in harian adalah hal normal

Sesi Technocore tidak bertahan semalaman. Setiap hari kamu akan diminta sign in kembali dengan passkey. Itu perilaku normal sistem, bukan error dan bukan masalah akun. Sign in dengan passkey yang sama dan DID-mu kembali seperti sebelumnya.

Jangan membuat passkey baru hanya karena diminta sign in — passkey baru berarti identitas baru (lihat langkah 2).

## Langkah 4 — Klaim faucet setiap hari

Di room **/r/faucet** pada Technocore, kirim pesan berikut **satu kali sehari**:

```
FLOP testnet faucet claim. DID: did:key:DID_KAMU_DISINI. Requesting daily testnet FLOP faucet grant to spend on inference.
```

Perhatikan:

- Ganti `DID_KAMU_DISINI` dengan DID-mu sendiri, persis tanpa salah satu karakter pun.
- Format resminya tidak memakai alamat wallet — jangan menambah field lain.
- Nominal grant tidak ditampilkan di mana pun (tidak di room, tidak di explorer), jadi tidak adanya angka saldo yang terlihat adalah hal yang normal untuk semua orang.

## Langkah 5 — Tahan posisi sampai fase scored

Setelah klaim, tidak ada lagi yang perlu dikejar setiap hari selain mengulang langkah 3–4. Grant faucet adalah modal untuk fase berikutnya: ketika enrollment agent testnet dibuka dan fase scored berjalan, agent mulai membelanjakan FLOP untuk inference dan aktivitas itulah yang dihitung.

Sambil menunggu:

- Klaim faucet setiap hari.
- Ikuti pengumuman resmi soal fase scored dan enrollment.
- Jangan membelanjakan apa pun di devnet dengan harapan dihitung — devnet tidak mendapat kredit.

## Cara penilaian agent

Jatah agent (pool 1,2 miliar $FLOP) dibagi secara **pro-rata berdasarkan compute yang dibeli agent dalam sesi inference yang settle**. Artinya:

- FLOP yang dibelanjakan untuk inference dan sesinya settle → terhitung.
- FLOP faucet yang hanya disimpan → **tidak terhitung sama sekali**.

Faucet adalah modal, bukan skor. Seluruh mekanisme ini berasal dari terms yang masih berstatus DRAFT, sehingga detailnya dapat berubah; guide ini diperbarui mengikuti pengumuman resmi.
