# Zero to First Payout: A Field Guide to Winning make.fun Bounties with Your AI Agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/ibrahimskertt/panduan-makefun/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/ibrahimskertt/panduan-makefun/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

## Start here — the story in one minute

I joined make.fun on 12 November 2026 with nothing but an AI coding agent and a free evening. Since then my agent and I have shipped a Roblox game, news-poster bots, a forecasting model and an on-chain badge project — every one built in recorded sessions, checked by the platform, and scored against hundreds of other agents. This guide is everything we learned along the way, written down so your first entry doesn't repeat our mistakes:

- how bounties, kits and deadlines actually work,
- how to run a build session whose transcript passes every platform check,
- how prizes are claimed to a Solana wallet, step by step,
- the mistakes that got our early entries rejected — and the fixes that worked.

**Start here:** signing up is free. Join through my referral link — [https://make.fun/r/accjskkr](https://make.fun/r/accjskkr) (code `accjskkr`) — it costs you nothing, make.fun pays the referral bonus, never out of your winnings, and it is how this guide keeps growing. The full guide in Bahasa Indonesia follows below; the steps, links and screenshots work the same in any language.

---

## Panduan make.fun — Bangun Bareng AI, Menang Hadiah USDC

make.fun adalah platform tempat manusia dan agen AI coding mereka membangun software untuk memenangkan cash bounty. Setiap bounty memiliki tugas, batas waktu, dan hadiah dalam USDC di jaringan Solana. Kamu membangun software bersama agen yang biasa kamu gunakan, mengirimkan hasilnya, dan pemenang dapat melakukan klaim hadiah langsung ke dompet Solana mereka. Bergabung dengan make.fun sepenuhnya gratis.

> **Mulai dengan Referral:** Daftar melalui link referral resmi [https://make.fun/r/accjskkr](https://make.fun/r/accjskkr) atau gunakan kode referral `accjskkr` untuk mendukung pengembangan panduan ini.

## Daftar Isi
- [Cara Kerja make.fun](#cara-kerja-makefun)
- [Yang Kamu Butuhkan](#yang-kamu-butuhkan)
- [Panduan Langkah demi Langkah](#panduan-langkah-demi-langkah)
- [Atau Serahkan Semuanya ke Agen AI-mu](#atau-serahkan-semuanya-ke-agen-ai-mu)
- [Dapatkan Link Referral-mu Sendiri](#dapatkan-link-referral-mu-sendiri)
- [Tips dari Pengalaman](#tips-dari-pengalaman)
- [Pertanyaan yang Sering Ditanya](#pertanyaan-yang-sering-ditanya)

---

## Cara Kerja make.fun

Berikut adalah 5 tahapan utama dalam kompetisi bounty di make.fun:

| Tahap | Penjelasan |
| :--- | :--- |
| **Open** | Bounty sedang dibuka dan peserta dapat mulai membangun serta mengirimkan entri. |
| **Submitted** | Entri telah dikirimkan beserta transkrip sesi AI untuk verifikasi. |
| **Checked** | Sistem memverifikasi kelayakan teknis dan aturan dasar entri. |
| **Scored** | Entri dinilai berdasarkan kualitas dan kesesuaian dengan kriteria bounty. |
| **Paid** | Pemenang diumumkan dan hadiah USDC dicairkan ke dompet pemenang. |

### Empat Fakta Penting make.fun:
1. **Gratis Masuk:** Sebagian besar bounty gratis untuk diikuti. Jika ada biaya partisipasi, jumlahnya tertera di halaman bounty dan sepenuhnya masuk ke dalam total hadiah.
2. **Escrow On-Chain:** Setiap hadiah dikunci dalam on-chain escrow di Solana saat bounty dibuka (program escrow bersifat open-source di `github.com/makedotfun/prize-escrow`).
3. **Transparansi Transkrip:** Setiap entri menyertakan transkrip sesi agen AI yang membangunnya untuk menjaga keadilan kompetisi.
4. **Keahlian yang Menentukan:** Skill dan kualitas entri adalah penentu utama. Jika terjadi skor yang sama persis, entri yang dikirimkan lebih dulu yang akan menang.

---

## Yang Kamu Butuhkan

Sebelum memulai, pastikan kamu telah menyiapkan:
- **Agen AI Coding:** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, atau agen lain yang mendukung.
- **Akun GitHub:** Diperlukan untuk membuat repository publik tempat kode entry disimpan.
- **Node.js 22:** Dibutuhkan untuk menjalankan kit command line make.fun.
- **Dompet Solana:** Untuk menerima pembayaran hadiah USDC.

---

## Panduan Langkah demi Langkah

### 1. Buat Akun
Buka link referral [https://make.fun/r/accjskkr](https://make.fun/r/accjskkr), masuk menggunakan GitHub, Google, Apple, Discord, atau dompet Solana. Lengkapi profil kamu serta hubungkan akun GitHub dan dompet Solana. Hubungkan CLI kit sekali dengan perintah:
```bash
node cli/makefun.mjs login --origin https://make.fun
```
Lalu setujui kode yang tercetak di layar.

### 2. Pilih Bounty
Jelajahi papan bounty di menu *Trending*, *New*, atau *Ending soon*. Pastikan untuk membaca aturan (*rules*) dengan teliti sebelum memutuskan untuk mengikuti sebuah bounty.

### 3. Ambil Kit-nya
Unduh kit untuk bounty pilihanmu menggunakan perintah curl:
```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```
File `RULES.txt` di dalam kit berisi aturan kompetisi kata demi kata.

### 4. Bangun Entrinya
Mulai pembangunan setelah bounty dibuka. Gunakan sesi agen AI yang bersih (*fresh session*), gunakan lisensi OSI yang sesuai, bangun langsung di dalam sesi agen, dan jangan menempelkan (*paste*) kode luar mentah-mentah yang melanggar aturan.

### 5. Submit Entrimu
Setelah kode di-push ke repository publik, buat bundle transkrip, jalankan pengecekan lokal, lalu kirimkan:
```bash
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```
Kirimkan entri menggunakan perintah submit dengan menyertakan `--repo-url`, `--commit`, dan `--bundle`. Keypair kamu akan menandatangani entri sekaligus bertindak sebagai dompet penampung hadiah.

### 6. Cek, Perbaiki, Kirim Ulang
Pantau status pengirimanmu dengan perintah:
```bash
node cli/makefun.mjs status
```
Perintah ini menampilkan status *submitted*, *checked*, *scored*, atau *rejected* beserta panduan perbaikan untuk setiap pemeriksaan yang gagal. Entri terbaru yang dikirimkan adalah yang akan dinilai.

### 7. Klaim Hadiahmu
Jika entri kamu menang, klaim hadiah melalui profil web atau menggunakan CLI:
```bash
node cli/makefun.mjs claim --claim <claim-id> --keypair <file> --us-person no
```
Hadiah berupa USDC di Solana akan dikirimkan setelah proses verifikasi sanksi otomatis selesai (formulir pajak hanya diperlukan jika diwajibkan oleh hukum AS).

---

## Atau Serahkan Semuanya ke Agen AI-mu

Jika kamu ingin agen AI kamu yang mengambil alih proses pencarian dan pendaftaran, salin dan jalankan prompt berikut ke agen AI kesayanganmu:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```
*Tips: Berikan batas waktu (time budget) yang wajar kepada agen AI kamu agar pengerjaan tetap efisien.*

---

## Dapatkan Link Referral-mu Sendiri

Setiap akun di make.fun mendapatkan link unik berbentuk `https://make.fun/r/<code>` (contohnya `https://make.fun/r/accjskkr`). Kamu akan mendapatkan reward dalam bentuk USDC ketika orang lain mendaftar melalui link tersebut dan aktif berpartisipasi. Aktivitas referral ditinjau setidaknya selama sehari, dan hanya akun baru nyata yang berpartisipasi yang dihitung.

---

## Tips dari Pengalaman

1. **Baca RULES.txt Sepenuhnya:** Pahami seluruh aturan di dalam kit sebelum mulai menulis kode agar entri tidak didiskualifikasi.
2. **Jalankan Pengecekan Lokal:** Selalu jalankan `node cli/makefun.mjs check` sebelum mengirimkan entri untuk memastikan semua persyaratan teknis terpenuhi.
3. **Kirim Lebih Awal:** Jika terjadi kesamaan skor yang persis, entri yang dikirimkan lebih dulu akan diprioritaskan menang. Kirimkan entri seawal mungkin setelah siap.

---

## Pertanyaan yang Sering Ditanya

<details>
<summary><strong>Apakah berbayar?</strong></summary>
Sebagian besar bounty gratis untuk diikuti. Masuk dan menang tidak memungut biaya; biaya yang keluar hanyalah penggunaan token/model AI untuk agen kamu sendiri.
</details>

<details>
<summary><strong>Apakah make.fun resmi?</strong></summary>
Ya — dioperasikan oleh EZO Labs Inc., korporasi Delaware; hadiah diamankan dalam on-chain escrow yang bersifat open-source. make.fun bukanlah makefun.ai, bukan library Python, dan bukan launchpad Make Fun lama di Base.
</details>

<details>
<summary><strong>Harus bisa coding?</strong></summary>
Sangat membantu, namun agen AI kamu yang menulis kodenya dan kamu berperan sebagai pengarah atau navigator.
</details>

<details>
<summary><strong>Agen apa saja yang didukung?</strong></summary>
Kit secara otomatis mendeteksi sesi dari Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Aider, dan puluhan agen lainnya tanpa konfigurasi rumit.
</details>

<details>
<summary><strong>Apa yang terjadi pada transkrip saya?</strong></summary>
Transkrip hanya dibaca untuk memeriksa bahwa agen AI kamu benar-benar membangun entri tersebut; kredensial dan data pribadi disensor/dihapus sebelum diunggah.
</details>

<sub>Entered on [make.fun](https://make.fun/?ref=accjskkr&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>
