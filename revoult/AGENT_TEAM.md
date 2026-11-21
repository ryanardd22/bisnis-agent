# Tim agen Revoult

Konfigurasi proyek ada di [`.codex/agents/`](../.codex/agents/) dan aturan kerja bersama ada di [`AGENTS.md`](../AGENTS.md). Agen memakai model, MCP, dan izin sesi induk. Gunakan mode baca saja di sesi induk untuk penugasan riset yang perlu membatasi perubahan file. [Dokumentasi Codex](https://learn.chatgpt.com/docs/agent-configuration/subagents#custom-agents)

| Agen | Nama di Codex | Hasil utama |
| --- | --- | --- |
| Market Research Agent | [`market_research`](../.codex/agents/market_research.toml) | Peluang, bukti permintaan, harga pesaing, tren, tanggal dan sumber |
| Business Analyst Agent | [`business_analyst`](../.codex/agents/business_analyst.toml) | Peringkat, tiga skenario profit dan modal, titik impas, risiko dan cadangan |
| Lead Generation Agent | [`lead_generation`](../.codex/agents/lead_generation.toml) | Prospek dengan kebutuhan teramati, jalur pembelian, dan kanal yang sesuai |
| Sales & Marketing Agent | [`sales_marketing`](../.codex/agents/sales_marketing.toml) | Draf penawaran, harga, pesan, proposal dan kriteria penerimaan |
| Development Agent | [`development`](../.codex/agents/development.toml) | Prototipe atau perubahan terkecil yang memenuhi lingkup, dengan hasil tes aktual |
| QA & Security Agent | [`qa_security`](../.codex/agents/qa_security.toml) | Temuan fungsional, regresi, dan keamanan defensif beserta keputusan kesiapan |
| Critic & Evaluation Agent | [`critic_evaluation`](../.codex/agents/critic_evaluation.toml) | Verifikasi sumber dan hitungan, keberatan terkuat, keputusan lanjut, revisi, atau berhenti |
| Orchestrator Agent | [`orchestrator`](../.codex/agents/orchestrator.toml) | Prioritas, tugas tiap agen, keputusan berdasarkan hasil aktual, dan pembaruan catatan yang diperlukan |

## Cara pakai

1. Buka checkout `bisnis-agent` di Codex CLI, desktop, atau IDE. Tinjau `AGENTS.md` dan `.codex/agents/`, lalu tandai proyek sebagai tepercaya jika diminta. Di CLI, jalankan `codex` dari root checkout. [Konfigurasi proyek Codex](https://learn.chatgpt.com/docs/config-file/config-basic#configuration-precedence)
2. Sebutkan nama peran serta tugas, batas biaya, dan hasil yang diminta dalam satu prompt. Gunakan pencarian web sesi induk jika tugas memerlukan bukti pasar aktual. Di CLI, `/subagents` menampilkan sesi agen yang dipanggil. [Penggunaan subagen](https://learn.chatgpt.com/docs/agent-configuration/subagents)
3. Untuk misi lintas fungsi, minta `orchestrator` menyusun rencana. Sesi utama kemudian memanggil spesialis yang diperlukan dan meneruskan hasilnya ke tahap berikutnya. Untuk tugas tunggal, sebut spesialisnya langsung.

**Contoh untuk menyiapkan pilot yang sudah dipilih**

> Panggil `orchestrator` untuk meninjau `revoult/NEXT_ACTIONS.md` dan menyiapkan uji pilot laporan Rp850.000. Minta sesi utama menjalankan `market_research` dan `lead_generation` secara paralel bila masih ada celah bukti. Gunakan `business_analyst` untuk memeriksa ekonomi berdasarkan temuan dan `critic_evaluation` untuk memeriksa klaim utama. Minta `sales_marketing` menyesuaikan draf hanya bila ada calon pembeli yang cocok. Batasi tahap ini pada persiapan tanpa pengeluaran atau pengiriman pesan.

**Contoh untuk pengujian teknis**

> Panggil `qa_security` untuk menguji perubahan pada branch ini terhadap kriteria penerimaan. Gunakan data sintetis. Laporkan hasil yang benar-benar dijalankan, temuan per tingkat dampak, dan keputusan kesiapan.

Secara umum, alurnya adalah bukti pasar dan prospek, analisis ekonomi, tinjauan independen, draf penawaran, uji komersial yang disetujui, pengembangan bila diperlukan, lalu QA defensif sebelum serah terima. Perbarui catatan berdasarkan hasil aktual. Untuk aturan persetujuan komunikasi, pengeluaran, dan akses, lihat [`AGENTS.md`](../AGENTS.md).

## Repository untuk ditinjau

Rekomendasi untuk kondisi sekarang adalah menggunakan konfigurasi Codex dalam repository ini. Lihat **CrewAI** terlebih dahulu untuk membandingkan pola pembagian tim bisnis. Alternatif berikut memiliki rilis dan contoh publik yang bisa diperiksa. Penggunaan untuk menghasilkan penjualan Revoult belum teruji. Snapshot rilis diperiksa 22 November 2026 WIB.

| Opsi | Kapan berguna | Bukti dan kebutuhan |
| --- | --- | --- |
| [CrewAI](https://github.com/crewAIInc/crewAI) | Tim berbasis peran untuk riset, penilaian lead dan penulisan laporan. | MIT, rilis 1.15.44 pada 20 Nov. Butuh runtime Python dan kredensial penyedia model. Repository contoh lead scoring sudah diarsipkan dan layak ditinjau sebagai pola. [Rilis](https://github.com/crewAIInc/crewAI/releases/tag/1.15.44) · [Contoh lead scoring](https://github.com/crewAIInc/crewAI-examples/tree/main/flows/lead-score-flow) |
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | Menjalankan tim melalui aplikasi Python dengan routing manajer, handoff, dan riwayat proses. | MIT, rilis v0.25.0 pada 18 Nov. Quickstart menggunakan API key. [Rilis](https://github.com/openai/openai-agents-python/releases/tag/v0.25.0) · [Contoh koordinasi](https://github.com/openai/openai-agents-python/blob/main/examples/agent_patterns/README.md) |
| [LangGraph](https://github.com/langchain-ai/langgraph) | Alur panjang yang perlu dijeda saat menunggu persetujuan dan dilanjutkan dengan status tersimpan. | MIT, rilis 1.2.24 pada 20 Nov. Alur persetujuan memerlukan checkpoint dan ID sesi. Produksi memerlukan penyimpanan checkpoint yang tahan lama. [Rilis](https://github.com/langchain-ai/langgraph/releases/tag/1.2.24) · [Contoh persetujuan](https://docs.langchain.com/oss/python/langgraph/interrupts) |
