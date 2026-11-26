# Role Miner — Syarat, Cara Ikut, dan Statusnya

Miner adalah role yang paling ramai dibicarakan di testnet FLOP — dan juga yang paling banyak disalahpahami. Halaman ini merangkum syaratnya, cara ikutnya, dan yang paling penting: **status sebenarnya saat ini**, supaya kamu bisa membedakan FOMO dari fakta.

## Miner itu ngapain

Miner menyediakan mesin hitung (GPU) yang mengerjakan inference — proses AI "berpikir" dan menghasilkan jawaban — untuk jaringan FLOP. Sebagai gantinya, miner mendapat bagian dari genesis pool: **1,2 miliar $FLOP** untuk seluruh miner, dibagi menurut compute yang disediakan (terms masih DRAFT).

## Syaratnya

- **GPU NVIDIA dengan VRAM 16GB atau lebih**, per unit.
- **Docker** untuk menjalankan perangkat lunaknya.
- Koneksi internet yang stabil — mesin miner diharapkan online dan mengerjakan sesi, bukan sekadar terdaftar.

Tidak ada syarat membeli atau memegang token: **stake untuk miner disponsori** (sponsored stake). Kamu menyediakan hardware dan listriknya, bukan modal token.

## Cara ikutnya

1. **Siapkan hardware-nya.** GPU NVIDIA 16GB+ VRAM dan Docker terpasang. Ini satu-satunya "modal" miner.
2. **Masuk jalur pendaftaran miner.** Tempat yang disponsori tidak terbuka begitu saja: hardware kamu perlu **di-attest** (dibuktikan spesifikasinya oleh sistem), atau kamu masuk lewat **admission list** (daftar aplikasi yang diseleksi).
3. **Tunggu miner pack rilis.** Perangkat lunak resmi untuk miner di testnet — miner pack — adalah kunci untuk benar-benar mulai mengerjakan sesi.

## Status sebenarnya (26 November 2026)

Ini bagian yang sering hilang di tengah FOMO:

- **Miner pack BELUM dirilis.** Sampai pack itu keluar, belum ada yang bisa benar-benar mining inference di testnet — yang berjalan sekarang adalah tahap pendaftaran dan persiapan.
- Proses miner yang terdokumentasi saat ini masih mengacu ke **devnet**, dan devnet tidak mendapat kredit airdrop.
- Fase **scored** juga belum dimulai untuk semua role.

Artinya: posisi yang benar untuk miner saat ini adalah **siap di garis start** — hardware siap, pendaftaran beres — sambil menunggu pack rilis. Bukan panik, dan bukan juga santai sampai ketinggalan pengumuman.

## Soal FOMO beli GPU

Karena miner sedang ramai, harga GPU bekas ikut jadi topik. Timbang baik-baik sebelum mengeluarkan uang:

- Pack-nya belum rilis; belum ada jadwal resmi kapan sesi miner testnet benar-benar dihitung.
- Syarat masuknya bukan cuma punya GPU — ada attest hardware dan admission list, jadi punya GPU saja tidak menjamin tempat.
- Terms pembagian pool masih DRAFT dan bisa berubah.

Kalau kamu memang sudah punya GPU 16GB+ nganggur, miner adalah peluang bagus tanpa modal tambahan. Kalau harus membeli khusus untuk ini, sadari bahwa kamu membeli *opsi* untuk ikut — bukan kepastian hasil.

## Miner vs agent

| | Miner | Agent |
|---|---|---|
| Modal | GPU 16GB+ VRAM + Docker | DID + wallet |
| Yang dinilai | Compute yang disediakan | Inference yang dibeli (sesi settle) |
| Stake | Disponsori | — |
| Status | Pack belum rilis, pendaftaran berjalan | Enrollment testnet belum dibuka penuh |

Keduanya menunggu fase berikutnya. Bedanya cuma di modal: hardware, atau tanpa hardware sama sekali ([agent.md](agent.md)).
