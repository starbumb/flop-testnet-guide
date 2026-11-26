# Konsep Dasar FLOP

Halaman ini menjelaskan FLOP dan istilah-istilahnya dari nol. Kalau sudah paham, lewati saja dan langsung ke [langkah-langkah agent](agent.md).

## FLOP itu apa

Inference adalah proses AI "berpikir" dan menghasilkan jawaban — setiap kali sebuah model AI menjawab pertanyaan, ada komputer yang melakukan hitungannya. FLOP adalah jaringan terdesentralisasi untuk jasa itu: hitungannya dikerjakan oleh komputer milik para peserta jaringan, bukan oleh satu perusahaan, dan sistem **proof-of-inference** memastikan pekerjaan itu bisa dibuktikan dan dicatat dengan jujur.

Sederhananya, FLOP adalah pasar jasa AI:

- **Miner** menyediakan mesin hitungnya (GPU).
- **Validator** menjaga dan mencatat jaringan.
- **Agent** memakai jasanya — membeli inference untuk menjalankan tugas-tugas AI.

Token $FLOP adalah "bahan bakar" untuk transaksi di jaringan ini. Testnet adalah jaringan percobaannya sebelum mainnet meluncur (target genesis **Q1 2027**).

## Istilah yang wajib paham

**DID** — Identitas kamu di FLOP, berformat `did:key:z6Mk...`. Semua aktivitasmu tercatat atas nama DID ini. DID bersifat publik dan aman dibagikan.

**Passkey** — Satu-satunya kunci masuk ke DID kamu, dibuat lewat Windows Hello (laptop) atau biometrik (HP). Tidak ada password, tidak ada frasa cadangan, tidak ada reset. **Passkey hilang = DID hilang permanen**, beserta seluruh riwayatnya. Ini poin paling penting di seluruh guide ini.

**Faucet** — Sumber token testnet gratis. Di FLOP, klaim faucet dilakukan dengan mengirim pesan di room chat Technocore (bukan tombol di website), sekali sehari.

**Sesi inference yang settle** — Sesi pemakaian inference yang pembayarannya selesai tercatat. Inilah aktivitas yang dihitung untuk jatah agent (penjelasan lengkap di [agent.md](agent.md#cara-penilaian-agent)).

**Snapshot** — Momen testnet ditutup dan seluruh aktivitas dibekukan menjadi data final untuk distribusi di genesis.

**Genesis** — Peluncuran mainnet (target Q1 2027), momen distribusi $FLOP dari hasil snapshot testnet dilakukan.

## Kenapa agent tidak butuh GPU

Karena GPU adalah alat *menyediakan* inference — itu pekerjaan miner. Agent adalah pihak yang *memakai* inference, jadi "modalnya" adalah identitas (DID) untuk tercatat sebagai pemakai, dan wallet untuk bertransaksi. Sama seperti kamu tidak perlu punya dapur untuk makan di restoran — dapur itu urusan koki (miner), kamu cukup datang sebagai pelanggan (agent).
