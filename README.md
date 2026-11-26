# Tutorial FLOP Network Testnet — Role Agent

Panduan lengkap ikut testnet **FLOP Network** sebagai **agent**, berbahasa Indonesia, ditulis dari garapan sendiri sejak testnet live 24 November 2026 dan diperbarui setiap ada perubahan resmi.

**Ringkasan 30 detik:** FLOP itu jaringan jasa inference AI. Ada tiga role — miner, validator, agent. Agent itu yang paling ringan: modalnya cuma **DID + wallet**, tanpa GPU. Tugas hariannya simpel: jaga identitas (DID), klaim faucet tiap hari, dan tahan posisi sampai fase scored dimulai — karena yang dinilai nanti adalah FLOP yang dibelanjakan untuk inference, bukan saldo yang ditimbun.

> **Disclaimer:** Testnet FLOP masih tahap awal. Status saat ini **unscored opening** (penilaian resmi belum mulai), terms airdrop masih **DRAFT** dan bisa berubah, kit resmi yang signed belum rilis, dan token testnet tidak memiliki nilai. Guide ini bukan materi resmi FLOP Labs dan tidak menjanjikan hasil apa pun.

---

## Daftar isi

1. [FLOP itu apa](#1-flop-itu-apa)
2. [Tiga role, dan kenapa agent](#2-tiga-role-dan-kenapa-agent)
3. [Konsep dasar yang wajib paham](#3-konsep-dasar-yang-wajib-paham)
4. [Status testnet saat ini](#4-status-testnet-saat-ini)
5. [Prasyarat](#5-prasyarat)
6. [Langkah-langkah](#6-langkah-langkah)
7. [Cara penilaian agent](#7-cara-penilaian-agent)
8. [Kesalahan umum](#8-kesalahan-umum)
9. [FAQ](#9-faq)
10. [Checklist harian](#10-checklist-harian)
11. [Sumber resmi](#11-sumber-resmi)
12. [Update log](#12-update-log)

---

## 1. FLOP itu apa

Inference adalah proses AI "berpikir" dan menghasilkan jawaban — setiap kali sebuah model AI menjawab pertanyaan, ada komputer yang melakukan hitungannya. FLOP adalah jaringan terdesentralisasi untuk jasa itu: hitungannya dikerjakan oleh komputer milik para peserta jaringan, bukan oleh satu perusahaan, dan sistem **proof-of-inference** memastikan pekerjaan itu bisa dibuktikan dan dicatat dengan jujur.

Sederhananya, FLOP adalah pasar jasa AI:

- **Miner** menyediakan mesin hitungnya (GPU).
- **Validator** menjaga dan mencatat jaringan.
- **Agent** memakai jasanya — membeli inference untuk menjalankan tugas-tugas AI.

Token $FLOP adalah "bahan bakar" untuk transaksi di jaringan ini. Testnet adalah jaringan percobaannya sebelum mainnet meluncur (target genesis **Q1 2027**).

## 2. Tiga role, dan kenapa agent

| Role | Syarat masuk | Yang dinilai | Hardware |
|---|---|---|---|
| Miner | GPU 16GB+ VRAM | Compute yang disediakan | Berat |
| Validator | CPU 8 core, RAM 64GB (disarankan), 4TB NVMe | Uptime dan partisipasi | Berat |
| **Agent** | **DID + wallet** | **FLOP yang dibelanjakan untuk inference dalam sesi yang settle** | **Tidak perlu** |

Pembagian genesis pool menurut terms (masih DRAFT) — total **4,4 miliar $FLOP**:

- Miner: 1,2 miliar
- Agent: 1,2 miliar
- Validator: 1,2 miliar
- Cadangan ekosistem: 800 juta

Guide ini khusus membahas agent: role yang tidak butuh modal hardware sama sekali, dan yang sejauh ini paling jarang dibahas. Untuk miner dan validator, rujuk dokumentasi resmi dan guide operator komunitas.

## 3. Konsep dasar yang wajib paham

**DID** — Identitas kamu di FLOP, berformat `did:key:z6Mk...`. Semua aktivitasmu tercatat atas nama DID ini. DID bersifat publik dan aman dibagikan.

**Passkey** — Satu-satunya kunci masuk ke DID kamu, dibuat lewat Windows Hello (laptop) atau biometrik (HP). Tidak ada password, tidak ada frasa cadangan, tidak ada reset. **Passkey hilang = DID hilang permanen**, beserta seluruh riwayatnya. Ini poin paling penting di seluruh guide ini.

**Faucet** — Sumber token testnet gratis. Di FLOP, klaim faucet dilakukan dengan mengirim pesan di room chat Technocore (bukan tombol di website), sekali sehari.

**Sesi inference yang settle** — Sesi pemakaian inference yang pembayarannya selesai tercatat. Inilah aktivitas yang dihitung untuk jatah agent (lihat bagian 7).

**Snapshot** — Momen testnet ditutup dan seluruh aktivitas dibekukan menjadi data final untuk distribusi di genesis.

## 4. Status testnet saat ini

Per 26 November 2026:

- Testnet live sejak 24 November 2026, fase **unscored opening** — aktivitas sekarang belum dinilai secara resmi.
- Fase **scored** (yang benar-benar dihitung) belum dimulai; tanggalnya menunggu pengumuman resmi.
- **Enrollment agent di testnet belum dibuka penuh.**
- Jalur inference agent yang terdokumentasi saat ini masih berada di **devnet**, dan devnet secara eksplisit **tidak** mendapat kredit airdrop.
- Explorer (testnet.flopscan.io) masih read-only dan datanya sering belum tampil.

Kesimpulan praktis: pekerjaan agent saat ini adalah **persiapan** — punya DID yang sehat, klaim faucet harian sebagai modal, dan menunggu fase scored serta enrollment dibuka.

## 5. Prasyarat

- Laptop atau HP yang bisa membuat passkey (Windows Hello / biometrik).
- Akses ke [Technocore](https://technocore.chat/humans).
- Wallet crypto (untuk kebutuhan agent berikutnya saat enrollment dibuka).
- Tidak perlu: GPU, server, modal uang asli.

## 6. Langkah-langkah

### Langkah 1 — Buat DID lewat Technocore

1. Buka [technocore.chat/humans](https://technocore.chat/humans).
2. Buat **passkey** — perangkatmu akan meminta Windows Hello atau biometrik.
3. Identitasmu langsung dibuat; DID-mu tampil dalam format `did:key:z6Mk...`.
4. Catat DID-mu di tempat yang aman. DID itu publik, mencatatnya tidak berisiko.

Hasil langkah ini: satu identitas FLOP yang melekat pada passkey di perangkatmu.

### Langkah 2 — Pahami hubungan DID dan passkey

DID adalah identitasnya; passkey adalah satu-satunya cara masuk ke identitas itu. Jika passkey hilang atau perangkat berganti tanpa passkey yang sama, DID lama tidak bisa dipakai lagi dan seluruh riwayatnya hangus — DID baru berarti mulai dari awal.

Pengalaman penulis: pada 26 November 2026 passkey lama tidak bisa dibuka lagi, sehingga penulis berganti DID baru dan klaim dua hari sebelumnya tidak lagi terhubung. Jadikan ini pengingat untuk memakai perangkat yang benar-benar kamu pegang setiap hari.

### Langkah 3 — Sign in harian adalah hal normal

Sesi Technocore tidak bertahan semalaman. Setiap hari kamu akan diminta sign in kembali dengan passkey. Itu perilaku normal sistem, bukan error dan bukan masalah akun. Sign in dengan passkey yang sama dan DID-mu kembali seperti sebelumnya.

Jangan membuat passkey baru hanya karena diminta sign in — passkey baru berarti identitas baru (lihat langkah 2).

### Langkah 4 — Klaim faucet setiap hari

Di room **/r/faucet** pada Technocore, kirim pesan berikut **satu kali sehari**:

```
FLOP testnet faucet claim. DID: did:key:DID_KAMU_DISINI. Requesting daily testnet FLOP faucet grant to spend on inference.
```

Perhatikan:

- Ganti `DID_KAMU_DISINI` dengan DID-mu sendiri, persis tanpa salah satu karakter pun.
- Format resminya tidak memakai alamat wallet — jangan menambah field lain.
- Nominal grant tidak ditampilkan di mana pun (tidak di room, tidak di explorer), jadi tidak adanya angka saldo yang terlihat adalah hal yang normal untuk semua orang.

### Langkah 5 — Tahan posisi sampai fase scored

Setelah klaim, tidak ada lagi yang perlu dikejar setiap hari selain mengulang langkah 3–4. Grant faucet adalah modal untuk fase berikutnya: ketika enrollment agent testnet dibuka dan fase scored berjalan, agent mulai membelanjakan FLOP untuk inference dan aktivitas itulah yang dihitung.

Sambil menunggu:

- Klaim faucet setiap hari.
- Ikuti pengumuman resmi soal fase scored dan enrollment.
- Jangan membelanjakan apa pun di devnet dengan harapan dihitung — devnet tidak mendapat kredit.

## 7. Cara penilaian agent

Jatah agent (pool 1,2 miliar $FLOP) dibagi secara **pro-rata berdasarkan compute yang dibeli agent dalam sesi inference yang settle**. Artinya:

- FLOP yang dibelanjakan untuk inference dan sesinya settle → terhitung.
- FLOP faucet yang hanya disimpan → **tidak terhitung sama sekali**.

Faucet adalah modal, bukan skor. Seluruh mekanisme ini berasal dari terms yang masih berstatus DRAFT, sehingga detailnya dapat berubah; guide ini diperbarui mengikuti pengumuman resmi.

## 8. Kesalahan umum

1. **Kehilangan passkey.** Akibatnya fatal dan permanen: DID baru, riwayat hangus. Pakai perangkat utama, dan kenali DID-mu sendiri.
2. **Panik saat diminta sign in ulang.** Itu rutinitas harian, bukan kerusakan.
3. **Mengira saldo faucet adalah skor.** Yang dinilai adalah pemakaian inference yang settle, bukan timbunan token.
4. **Mengira agent butuh GPU.** GPU adalah syarat miner. Agent hanya butuh DID dan wallet.
5. **Beraktivitas di devnet demi airdrop.** Devnet tidak mendapat kredit — waktu terbuang.
6. **Klaim berulang dalam sehari.** Format faucet adalah harian; satu kali sehari sudah cukup.

## 9. FAQ

**Apakah agent benar-benar tidak butuh GPU?**
Benar. GPU 16GB+ adalah syarat miner. Agent hanya membutuhkan DID dan wallet.

**Bagaimana cara tahu klaim faucet saya sudah masuk?**
Saat ini tidak ada tampilan nominal grant di room maupun explorer. Jika pesan klaimmu terkirim di /r/faucet dengan DID yang benar, itulah yang bisa dilakukan — sisanya belum dapat diverifikasi oleh siapa pun.

**Saya sudah klaim beberapa hari tapi tidak ada progres. Kenapa?**
Karena fase scored belum dimulai. Yang sedang kamu bangun sekarang adalah posisi dan modal, bukan skor.

**Apakah DID aman dibagikan?**
Aman — DID bersifat publik. Yang tidak boleh dibagikan adalah akses ke passkey atau perangkatmu.

**Kapan fase scored dimulai?**
Belum ada tanggal resmi. Guide ini diperbarui pada hari yang sama ketika pengumumannya keluar.

**Apakah ada grup resmi FLOP di Discord/Telegram?**
Tidak ada. Sumber resmi hanya yang tercantum di bagian 11.

## 10. Checklist harian

- [ ] Sign in Technocore dengan passkey — pastikan DID yang tampil adalah DID yang sama.
- [ ] Kirim klaim faucet di /r/faucet dengan format pada langkah 4.
- [ ] Sekilas cek @flop_labs untuk pengumuman fase scored / enrollment.
- [ ] Selesai. Tidak perlu aktivitas devnet.

## 11. Sumber resmi

- Website: [flop.finance](https://flop.finance)
- Dokumentasi: [docs.flop.network](https://docs.flop.network)
- X: [@flop_labs](https://x.com/flop_labs)
- Explorer testnet: [testnet.flopscan.io](https://testnet.flopscan.io)
- Technocore (identitas & faucet): [technocore.chat/humans](https://technocore.chat/humans)

## 12. Update log

- **26 Nov 2026** — Guide disusun ulang menjadi versi lengkap: konsep dasar, prasyarat, langkah terperinci, penilaian, FAQ, checklist, dan sumber resmi. Penulis berganti DID baru akibat insiden passkey (bagian 8) — klaim berjalan kembali dengan DID baru.
- **24 Nov 2026** — Testnet live; klaim faucet pertama.
