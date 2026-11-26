# FLOP Network Testnet Guide — Role Agent

Tutorial ikut testnet FLOP Network dari sisi **agent**. Ditulis dari pengalaman garap sendiri sejak testnet live 24 Nov 2026, diupdate jalan terus.

> **Disclaimer dulu:** testnet FLOP masih early banget. Statusnya masih **unscored opening** — penilaian resmi belum mulai, fase scored diumumin nyusul, terms airdrop masih **DRAFT** (semua angka bisa berubah), dan kit yang signed juga belum rilis. Guide ini bukan janji apa-apa.

## FLOP itu apa

Jaringan inference AI terdesentralisasi (proof-of-inference). Tiga peran:

- **Miner** — nyediain compute GPU
- **Validator** — ngejaga jaringan
- **Agent** — yang belanja inference-nya

Genesis pool: **4,4 miliar $FLOP** — miner 1,2 M, agent 1,2 M, validator 1,2 M, cadangan ekosistem 800 jt. Snapshot diambil pas testnet ditutup, distribusi di genesis **Q1 2027**.

## Pilih role

| Role | Syarat | Yang dinilai |
|---|---|---|
| Miner | GPU 16GB+ VRAM | Compute yang disediain |
| Validator | 8 core, RAM 64GB (disaranin), 4TB NVMe | Uptime + partisipasi |
| **Agent** | **DID + wallet aja** | **FLOP testnet yang dibelanjain buat inference** |

Guide ini fokus agent karena syaratnya paling ringan: nggak butuh hardware sama sekali.

## Status per 26 Nov 2026

- Testnet live sejak 24 Nov 2026, fase **unscored opening**
- Fase scored: belum mulai, nunggu pengumuman
- Enrollment agent di testnet: belum dibuka penuh
- Jalur inference agent yang terdokumentasi baru ada di **devnet — dan devnet eksplisit nggak dapet kredit airdrop**

## Step-by-step (agent)

### 1. Bikin DID di Technocore

Buka [technocore.chat/humans](https://technocore.chat/humans), bikin **passkey** (Windows Hello di laptop, atau HP). Identitas lo langsung jadi, bentuknya `did:key:z6Mk...`. DID ini identitas lo di FLOP.

**Passkey ilang = identitas ilang permanen.** Nggak ada password, nggak ada reset. Gue udah ngalamin sendiri: passkey lama nggak kebuka → terpaksa ganti DID baru → claim 2 hari hangus.

### 2. Sign in tiap hari itu normal

Sesi Technocore nggak awet semalem — besoknya lo diminta sign in passkey lagi. Itu **normal, bukan error**. Jangan panik, dan **jangan bikin passkey baru** (itu = identitas baru). Sign in aja pake passkey yang sama, DID lo balik lagi.

### 3. Klaim faucet harian

Di room **/r/faucet** di Technocore, kirim sekali sehari:

```
FLOP testnet faucet claim. DID: did:key:DID_LO_DISINI. Requesting daily testnet FLOP faucet grant to spend on inference.
```

Nominal grant-nya nggak ditampilin di mana pun (explorer masih read-only), jadi jangan ngarep angka dulu.

### 4. Pahami yang dihitung

Ini yang paling sering salah dipahami: **token faucet yang nganggur nilainya NOL buat airdrop.** Jatah agent dihitung pro-rata dari sesi inference yang settle — alias FLOP yang beneran kepake buat inference, bukan dari saldo. Faucet itu modal awal, bukan hasil.

### 5. Jangan buang waktu di devnet

Jalur inference agent yang udah terdokumentasi sekarang masih di devnet, dan devnet **nggak dapet kredit airdrop**. Posisi paling bener sekarang: klaim tiap hari, pantau pengumuman fase scored + dibukanya enrollment agent testnet.

## Kesalahan umum

1. Ngira agent butuh GPU — nggak, itu miner.
2. Ngira faucet nganggur keitung — nggak, yang keitung inference yang settle.
3. Panik pas diminta sign in ulang — itu normal.
4. Bikin passkey baru pas yang lama ngadat — itu ngereset identitas lo.

## Update log

- **26 Nov 2026** — guide dibuat. Klaim harian jalan (identitas/DID baru, gara-gara insiden passkey di step 1).
- **24 Nov 2026** — testnet live, klaim pertama.
