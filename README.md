# FLOP Network Testnet — Guide Role Agent

Guide ikut testnet FLOP Network dari sisi **agent**, ditulis dari garapan sendiri sejak testnet live 24 Nov 2026. Bukan guide resmi — ini catatan orang yang lagi garap beneran, termasuk kesalahan yang udah gue bayar sendiri. Diupdate jalan terus tiap ada perubahan.

> **Disclaimer:** testnet FLOP masih early banget. Statusnya **unscored opening** — penilaian resmi belum mulai, terms airdrop masih **DRAFT** (semua angka bisa berubah), kit yang signed juga belum rilis. Token testnet nggak ada harganya. Guide ini nggak janjiin apa-apa.

---

## 1. FLOP itu apa, dijelasin gampang

FLOP itu jaringan buat **jasa AI (inference)** yang nggak dikontrol satu perusahaan. Inference itu proses AI mikir dan ngasih jawaban — kayak pas lo nanya sesuatu ke chatbot, ada komputer di belakang yang ngitung jawabannya. Nah, di FLOP, komputer yang ngitung itu punya orang-orang yang ikutan jaringan, bukan punya satu data center.

Sistemnya disebut **proof-of-inference**: yang nyediain hitungan harus bisa buktiin kerjanya bener, dan dari bukti kerja itulah pembagian hasilnya dihitung.

Di dalem jaringan ini ada tiga peran:

- **Miner** — yang punya "mesin hitung" (GPU). Dia yang ngerjain inference-nya.
- **Validator** — yang ngecek dan nyatet semua transaksi biar jaringan jujur dan jalan terus.
- **Agent** — yang **belanja** inference. Kayak pelanggan yang make jasa AI lewat jaringan ini.

Guide ini fokus ke **agent**, karena itu peran yang lagi gue garap dan syaratnya paling ringan.

## 2. Kenapa agent, bukan miner atau validator

| Role | Syarat masuk | Yang dinilai | Butuh hardware? |
|---|---|---|---|
| Miner | GPU 16GB+ VRAM | Compute yang disediain | Iya, berat |
| Validator | 8 core CPU, RAM 64GB (disaranin), 4TB NVMe | Uptime + partisipasi | Iya, berat |
| **Agent** | **DID + wallet** | **FLOP testnet yang dibelanjain buat inference** | **Nggak** |

Buat miner/validator, guide operator yang lengkap udah ada di tempat lain. Buat agent, hampir nggak ada yang nulis — makanya guide ini ada.

Soal hadiahnya: genesis pool-nya **4,4 miliar $FLOP** — miner 1,2 M, agent 1,2 M, validator 1,2 M, cadangan ekosistem 800 jt. Snapshot diambil pas testnet ditutup, distribusi di genesis **Q1 2027**. Semua ini dari terms yang masih DRAFT.

## 3. Konsep yang wajib paham dulu

Lima istilah ini bakal muncul terus. Paham ini dulu, sisanya gampang.

**DID** — identitas lo di FLOP, bentuknya `did:key:z6Mk...`. Ini yang nempel ke semua aktivitas lo. DID itu publik, aman dishare ke mana-mana.

**Passkey** — kunci buat masuk ke DID lo (Windows Hello di laptop, atau biometrik HP). Ini bagian paling penting di seluruh guide: **passkey ilang = DID lo ilang permanen.** Nggak ada password cadangan, nggak ada tombol reset, nggak ada CS yang bisa nolong. Gue nulis ini karena gue udah ngalamin sendiri (ceritanya di bagian 7).

**Faucet** — keran token testnet gratis. Lo klaim, lo dapet modal FLOP testnet buat dipake. Di FLOP, klaimnya lewat room chat, bukan tombol di website (detailnya di bagian 5).

**Inference session** — sesi pas agent beneran make jasa inference dan pembayarannya settle (kelar tercatat). **Ini yang dihitung buat jatah agent**, bukan saldo lo.

**Snapshot & genesis** — snapshot itu momen testnet ditutup dan semua aktivitas dibekukan jadi data final. Genesis itu lahirnya mainnet (target Q1 2027), dan di momen itulah distribusi $FLOP kejadian.

## 4. Status sekarang (26 Nov 2026)

Biar nggak salah ekspektasi, ini kondisi lapangannya:

- Testnet live sejak 24 Nov 2026, fase **unscored opening** — aktivitas sekarang **belum dinilai resmi**
- Fase **scored** (yang beneran dihitung): belum mulai, nunggu pengumuman
- **Enrollment agent di testnet: belum dibuka penuh**
- Jalur inference agent yang terdokumentasi baru ada di **devnet — dan devnet eksplisit nggak dapet kredit airdrop**
- Explorer (testnet.flopscan.io) masih read-only, datanya sering kosong

Artinya posisi paling bener sekarang: **siapin identitas, klaim faucet tiap hari, dan tunggu fase scored + enrollment dibuka.** Bukan kejar-kejaran aktivitas yang belum tentu kehitung.

## 5. Step-by-step

### Step 1 — Bikin DID di Technocore

1. Buka [technocore.chat/humans](https://technocore.chat/humans)
2. Bikin **passkey** — laptop lo bakal minta Windows Hello (PIN/sidik jari), atau arahin ke HP
3. Identitas lo langsung jadi, DID-nya muncul dalam bentuk `did:key:z6Mk...`
4. **Catat DID lo** (aman, ini publik)

Yang lo dapet dari step ini: satu identitas FLOP. Yang lo pegang: passkey-nya ada di device lo — jagain kayak lo jagain kunci rumah satu-satunya, karena memang nggak ada duplikatnya.

### Step 2 — Paham hubungan DID dan passkey

DID = nama identitasnya. Passkey = satu-satunya cara masuk. Ganti device atau passkey ilang, DID lama **nggak bisa dipake lagi** dan semua riwayat di DID itu hangus. DID baru = mulai dari nol. Ini bukan teori — gue ganti DID tanggal 26 Nov dan claim 2 hari gue sebelumnya nggak keitung lagi.

### Step 3 — Sign in tiap hari itu normal

Sesi Technocore nggak awet semalem. Besoknya lo bakal diminta sign in passkey lagi. Itu **normal, bukan error, dan bukan tanda akun lo kenapa-kenapa**. Sign in aja pake passkey yang sama — DID lo balik persis kayak kemarin. Yang jangan dilakuin: bikin passkey baru (itu = identitas baru, lihat step 2).

### Step 4 — Klaim faucet harian

Di room **/r/faucet** di Technocore, kirim pesan ini **sekali sehari**:

```
FLOP testnet faucet claim. DID: did:key:DID_LO_DISINI. Requesting daily testnet FLOP faucet grant to spend on inference.
```

Catatan soal klaim ini:

- Ganti `DID_LO_DISINI` sama DID lo sendiri, persis, jangan sampai salah satu karakter
- Nggak ada field wallet di format resminya — jangan nambah-nambahin
- Nominal grant-nya **nggak ditampilin di mana pun** (nggak di room, nggak di explorer). Jadi jangan bingung kalo lo nggak bisa liat saldo — semua orang juga gitu

### Step 5 — Habis klaim, ngapain?

Jujur aja: sekarang ya **nahan posisi**. Grant faucet itu modal buat nanti, pas enrollment agent testnet dibuka dan fase scored jalan — di titik itu agent mulai belanja inference dan aktivitasnya mulai kehitung. Sambil nunggu:

- Klaim lagi besok (step 4), tiap hari
- Pantau pengumuman @flop_labs soal fase scored
- **Jangan** belanja inference di devnet ngarep kehitung — devnet nggak dapet kredit, titik

## 6. Cara penilaian agent, dijelasin

Jatah agent (pool 1,2 M $FLOP) dibagi **pro-rata dari compute yang dibeli agent dalam sesi inference yang settle**. Maksudnya:

- Lo belanja inference → sesi lo settle → porsi lo kehitung
- Lo cuma pegang token faucet nganggur → **porsi lo nol**, sesimpel itu

Faucet itu modal awal, bukan hasil. Yang dinilai itu pemakaiannya. Dan karena fase scored belum mulai, semua angka cara hitung ini masih dari terms DRAFT — bisa berubah, makanya guide ini gue update terus.

## 7. Kesalahan yang udah gue bayar sendiri

**Passkey ilang (26 Nov 2026).** Passkey lama gue nggak kebuka lagi. Nggak ada jalan pulang: gue bikin identitas baru, DID baru, dan claim tanggal 24–25 Nov hangus begitu aja. Pelajarannya: pastiin passkey lo kesimpen di device yang beneran lo pegang tiap hari, dan kenali DID lo sendiri biar lo sadar kalo yang kebuka tiba-tiba DID yang beda.

**Panik pas diminta sign in ulang.** Hari pertama gue kira sesi gue rusak. Ternyata emang begitu sistemnya tiap hari. Udah gue tulis di step 3 biar lo nggak panik kayak gue.

**Ngira faucet nganggur keitung.** Awalnya gue kira makin rajin klaim makin gede jatah. Salah — baca lagi bagian 6.

**Ngira agent butuh GPU.** Itu miner. Agent cuma DID + wallet.

## 8. FAQ

**Q: Agent beneran nggak butuh GPU sama sekali?**
A: Beneran. GPU itu syarat miner. Agent modalnya DID + wallet.

**Q: Klaim faucet gue udah masuk belum? Saldonya kok nggak keliatan?**
A: Emang nggak ada tempat buat liat nominalnya sekarang. Kalo pesan klaim lo udah terkirim di /r/faucet pake DID yang bener, itu yang bisa lo lakuin. Sisanya belum bisa diverifikasi siapa pun.

**Q: Gue udah klaim 2 hari, kok rasanya nggak ada progres?**
A: Karena fase scored belum mulai. Yang lo bangun sekarang itu posisi + modal, bukan skor.

**Q: Boleh klaim lebih dari sekali sehari?**
A: Formatnya harian. Sekali sehari, jangan spam room orang.

**Q: DID gue aman dishare?**
A: Aman, DID itu publik. Yang nggak boleh dishare itu akses ke passkey/device lo.

**Q: Kapan fase scored mulai?**
A: Belum ada tanggal resmi. Kalo udah diumumin, guide ini gue update di hari yang sama.

## 9. Checklist harian (versi 30 detik)

- [ ] Sign in Technocore pake passkey (DID yang sama!)
- [ ] Kirim klaim di /r/faucet pake format di step 4
- [ ] Cek sekilas @flop_labs — ada pengumuman fase scored / enrollment nggak
- [ ] Udah. Tutup. Jangan devnet.

## Update log

- **26 Nov 2026** — guide ditulis ulang total: penjelasan konsep, step detail, FAQ, checklist. Penulis ganti DID baru gara-gara insiden passkey (bagian 7) — klaim jalan lagi dari DID baru.
- **24 Nov 2026** — testnet live, klaim pertama.
