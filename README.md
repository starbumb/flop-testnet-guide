# Tutorial FLOP Network Testnet — Role Agent

Panduan lengkap ikut testnet **FLOP Network** sebagai **agent**, berbahasa Indonesia, ditulis dari garapan sendiri sejak testnet live 24 November 2026 dan diperbarui setiap ada perubahan resmi.

FLOP adalah jaringan terdesentralisasi untuk jasa inference AI: miner menyediakan GPU, validator menjaga jaringan, dan **agent memakai jasanya**. Agent adalah role paling ringan — modalnya cuma **DID + wallet**, tanpa hardware sama sekali. Guide ini membahas role itu secara khusus, karena miner dan validator sudah banyak dibahas di tempat lain, sementara agent hampir belum ada yang menulis.

> **Disclaimer:** Guide tidak resmi, ditulis oleh peserta testnet. Testnet FLOP masih tahap awal, token testnet tidak memiliki nilai, dan tidak ada bagian dari guide ini yang menjanjikan hasil atau airdrop. Terms resmi FLOP sendiri masih berstatus DRAFT.

## Status saat ini

Per 26 November 2026:

| Item | Status |
|---|---|
| Testnet | Live sejak 24 Nov 2026 — fase **unscored opening** |
| Fase scored | Belum dimulai, menunggu pengumuman resmi |
| Enrollment agent testnet | Belum dibuka penuh |
| Jalur inference agent | Baru terdokumentasi di devnet — **devnet tidak mendapat kredit airdrop** |
| Snapshot | Di penutupan testnet |
| Genesis / mainnet | Target Q1 2027 |

## Tiga role sekilas

| Role | Syarat masuk | Yang dinilai | Hardware |
|---|---|---|---|
| Miner | GPU 16GB+ VRAM | Compute yang disediakan | Berat |
| Validator | CPU 8 core, RAM 64GB (disarankan), 4TB NVMe | Uptime dan partisipasi | Berat |
| **Agent** | **DID + wallet** | **FLOP yang dibelanjakan untuk inference dalam sesi yang settle** | **Tidak perlu** |

Genesis pool (terms DRAFT): total **4,4 miliar $FLOP** — miner 1,2 M, agent 1,2 M, validator 1,2 M, cadangan ekosistem 800 jt.

## Isi repo ini

```
.
├── README.md          halaman ini — ringkasan dan navigasi
├── docs/
│   ├── konsep.md      FLOP itu apa + konsep dasar (DID, passkey, faucet, sesi, snapshot)
│   ├── miner.md       role miner: syarat GPU, cara ikut, status pack, soal FOMO
│   ├── agent.md       langkah-langkah lengkap role agent + cara penilaian
│   └── faq.md         tanya-jawab + kesalahan umum
└── checklists/
    └── harian.md      checklist harian yang bisa dicetak/diikuti dalam 30 detik
```

Mulai dari [docs/konsep.md](docs/konsep.md) kalau baru pertama kali dengar FLOP. Buat role yang paling ramai dibicarakan, lihat [docs/miner.md](docs/miner.md); buat yang tanpa hardware, langsung ke [docs/agent.md](docs/agent.md).

## Sumber resmi

- Website: [flop.finance](https://flop.finance)
- Dokumentasi: [docs.flop.network](https://docs.flop.network)
- X: [@flop_labs](https://x.com/flop_labs)
- Explorer testnet: [testnet.flopscan.io](https://testnet.flopscan.io)
- Technocore (identitas & faucet): [technocore.chat/humans](https://technocore.chat/humans)

FLOP tidak memiliki Discord, Telegram, atau grup resmi lain. Di luar daftar di atas, anggap bukan sumber resmi.

## Update log

- **26 Nov 2026** — Repo disusun menjadi struktur multi-file (konsep, langkah agent, FAQ, checklist). Penulis berganti DID baru akibat insiden passkey — pelajaran lengkapnya ada di [docs/faq.md](docs/faq.md).
- **24 Nov 2026** — Testnet live; klaim faucet pertama.
