# FAQ dan Kesalahan Umum

## FAQ

**Apakah agent benar-benar tidak butuh GPU?**
Benar. GPU 16GB+ adalah syarat miner. Agent hanya membutuhkan DID dan wallet. Penjelasannya ada di [konsep.md](konsep.md#kenapa-agent-tidak-butuh-gpu).

**Bagaimana cara tahu klaim faucet saya sudah masuk?**
Saat ini tidak ada tampilan nominal grant di room maupun explorer. Jika pesan klaimmu terkirim di /r/faucet dengan DID yang benar, itulah yang bisa dilakukan — sisanya belum dapat diverifikasi oleh siapa pun.

**Saya sudah klaim beberapa hari tapi tidak ada progres. Kenapa?**
Karena fase scored belum dimulai. Yang sedang kamu bangun sekarang adalah posisi dan modal, bukan skor.

**Apakah DID aman dibagikan?**
Aman — DID bersifat publik. Yang tidak boleh dibagikan adalah akses ke passkey atau perangkatmu.

**Kapan fase scored dimulai?**
Belum ada tanggal resmi. Guide ini diperbarui pada hari yang sama ketika pengumumannya keluar.

**Apakah ada grup resmi FLOP di Discord/Telegram?**
Tidak ada. Sumber resmi hanya website, dokumentasi, X @flop_labs, explorer, dan Technocore.

## Kesalahan umum

1. **Kehilangan passkey.** Akibatnya fatal dan permanen: DID baru, riwayat hangus. Penulis mengalaminya sendiri pada 26 November 2026 — passkey lama tidak bisa dibuka, DID berganti, dan klaim dua hari sebelumnya tidak lagi terhubung. Pakai perangkat utama yang kamu pegang setiap hari, dan hafalkan seperti apa DID-mu.
2. **Panik saat diminta sign in ulang.** Itu rutinitas harian, bukan kerusakan.
3. **Mengira saldo faucet adalah skor.** Yang dinilai adalah pemakaian inference yang settle, bukan timbunan token.
4. **Mengira agent butuh GPU.** Itu syarat miner. Agent hanya butuh DID dan wallet.
5. **Beraktivitas di devnet demi airdrop.** Devnet tidak mendapat kredit — waktu terbuang.
6. **Klaim berulang dalam sehari.** Format faucet adalah harian; satu kali sehari sudah cukup.
7. **Salah menyalin DID saat klaim.** Satu karakter berbeda berarti klaim tercatat untuk identitas yang bukan milikmu. Salin-tempel, jangan ketik ulang.
