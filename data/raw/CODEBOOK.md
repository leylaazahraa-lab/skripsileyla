# Codebook — Synthetic IBS & IMK panel (2018–2022)

> **DATA SINTETIS / FAKE DATA.** Seluruh angka dibangkitkan secara acak namun
> konsisten secara akuntansi. **Bukan data BPS sebenarnya** — hanya untuk
> prototipe kode, ilustrasi proposal, dan pengujian pipeline. Jangan dikutip
> sebagai fakta empiris.

Dibangkitkan oleh `scripts/make_dummy_ibs.py` dan `scripts/make_dummy_imk.py`
(seed tetap `20260613`, reproducible). Nama variabel = nama layout asli dengan
akhiran tahun dihilangkan (mis. `OUTPUT22`→`OUTPUT`); identifier panel `TAHUN`
dan `PROV` ditambahkan. Nilai uang IBS dalam **ribu Rupiah (Rp .000)**; nilai
uang IMK dalam **Rupiah** (skala mikro/kecil).

**Identitas yang dijamin:** IBS `VTLVCU = OUTPUT − IINPUT`, subtotal tenaga
kerja, roll-forward modal tetap, blok persentase = 100. IMK `R803 = R801 − R802`,
blok komposisi aset / sumber bahan / saluran penjualan / pemasaran = 100,
rincian pekerja (gender × bayar/tak-bayar, umur, pendidikan) menjumlah ke total.

**Field tambahan (kedua survei):**

| Variabel | Keterangan |
|---|---|
| `TAHUN` | Tahun panel survei 2018-2022 (ditambahkan untuk data dummy) |
| `PROV` | Kode provinsi BPS 2-digit (ditambahkan untuk data dummy) |

## IBS — Industri Besar Sedang (231 var + TAHUN/PROV)

| # | Variabel (dummy) | Variabel asli BPS | Tipe | Keterangan |
|--:|---|---|---|---|
| 1 | `DISIC2` | `DISIC222` | C2 | KBLI 2 digit |
| 2 | `JAN` | `JAN` | N1 | Januari (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 3 | `FEB` | `FEB` | N1 | Februari (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 4 | `MAR` | `MAR` | N1 | Maret (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 5 | `APR` | `APR` | N1 | April (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 6 | `MEI` | `MEI` | N1 | Mei (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 7 | `JUN` | `JUN` | N1 | Juni (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 8 | `JUL` | `JUL` | N1 | Juli (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 9 | `AGS` | `AGS` | N1 | Agustus (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 10 | `SEP` | `SEP` | N1 | September (Bulan kegiatan produksi perusahaan selama tahun 2022 |
| 11 | `OKT` | `OKT` | N1 | Oktober (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 12 | `NOP` | `NOP` | N1 | November (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 13 | `DES` | `DES` | N1 | Desember (Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 14 | `YEAR` | `YEAR` | N2 | Tahun (berapa Bulan kegiatan produksi perusahaan selama tahun 2022) |
| 15 | `SHIFTM` | `SHIFTM22` | N2 | Rata-rata hari kerja per bulan (hari) |
| 16 | `SHIFTD` | `SHIFTD22` | N2 | Rata-rata jam kerja per hari (jam) |
| 17 | `DPUSDA` | `DPUSDA22` | N5.2 | Persentase Investasi/Permodalan Dalam Negeri, Pemerintah per 31 Desember 2022 |
| 18 | `DNFINS` | `DNFINS22` | N5.2 | Persentase Investasi/Permodalan Dalam Negeri, Perusahaan/Lembaga Non Keuangan  per 31 Desember 2022 |
| 19 | `DFINSI` | `DFINSI22` | N5.2 | Persentase Investasi/Permodalan Dalam Negeri, Perusahaan/Lembaga Keuangan per 31 Desember 2022 |
| 20 | `DNOPRO` | `DNOPRO22` | N5.2 | Persentase Investasi/Permodalan Dalam Negeri, Lembaga Nirlaba per 31 Desember 2022 |
| 21 | `DINDIV` | `DINDIV22` | N5.2 | Persentase Investasi/Permodalan Dalam Negeri, Perorangan per 31 Desember 2022 |
| 22 | `DASING` | `DASING22` | N5.2 | Persentase Investasi/Permodalan Luar Negeri (Asing) per 31 Desember 2022 |
| 23 | `CONTROW1` | `CONTROW1` | N3 | Negara asal Pemegang saham asing ke 1 |
| 24 | `BUSINES1` | `BUSINES1` | C68 | Bidang usaha Pemegang saham asing ke 1 |
| 25 | `STOCKOW1` | `STOCKOW1` | N5.2 | Persentase Kepemilikan saham pemegang saham asing ke 1 |
| 26 | `CONTROW2` | `CONTROW2` | N3 | Negara asal Pemegang saham asing ke 2 |
| 27 | `BUSINES2` | `BUSINES2` | C66 | Bidang usaha Pemegang saham asing ke 2 |
| 28 | `STOCKOW2` | `STOCKOW2` | N5.2 | Persentase Kepemilikan saham pemegang saham asing ke 3 |
| 29 | `STOCKOWO` | `STOCKOWO` | N5.2 | Persentase Kepemilikan saham pemegang saham asing Lainnya |
| 30 | `NAMRTL` | `NAMRTL` | C139 | Nama bahan baku utama berasal dari dalam negeri |
| 31 | `PPR1RTL` | `PPR1RTL` | N5.2 | Asal Pembelian bahan baku dalam satu provinsi |
| 32 | `PROV1RTL` | `PROV1RTL` | N2 | Asal Pembelian bahan baku di provinsi lain ke 1 |
| 33 | `PPRV1RTL` | `PPRV1RTL` | N5.2 | Prosentase asal Pembelian bahan baku di provinsi lain ke 1 |
| 34 | `PROV2RTL` | `PROV2RTL` | N2 | Asal Pembelian bahan baku di provinsi lain ke 2 |
| 35 | `PPRV2RTL` | `PPRV2RTL` | N5.2 | Prosentase asal Pembelian bahan baku di provinsi lain ke 2 |
| 36 | `PROV3RTL` | `PROV3RTL` | N2 | Asal Pembelian bahan baku di provinsi lain ke 3 |
| 37 | `PPRV3RTL` | `PPRV3RTL` | N5.2 | Prosentase asal Pembelian bahan baku di provinsi lain ke 3 |
| 38 | `PPRVORTL` | `PPRVORTL` | N5.2 | Prosentase asal Pembelian bahan baku di provinsi lainnya |
| 39 | `NAMYPR` | `NAMYPR` | C143 | Nama produk utama yang dijual ke dalam negeri |
| 40 | `PPR1YPR` | `PPR1YPR` | N5.2 | Prosentase  penjualan dalam satu provinsi |
| 41 | `PROV1YPR` | `PROV1YPR` | N2 | Tujuan penjualan produk utama pada provinsi lain ke 1 |
| 42 | `PPRV1YPR` | `PPRV1YPR` | N5.2 | Prosentase penjualan produk utama pada provinsi lain ke 1 |
| 43 | `PROV2YPR` | `PROV2YPR` | N2 | Tujuan penjualan produk utama pada provinsi lain ke 2 |
| 44 | `PPRV2YPR` | `PPRV2YPR` | N5.2 | Prosentase penjualan produk utama pada provinsi lain ke 2 |
| 45 | `PROV3YPR` | `PROV3YPR` | N2 | Tujuan penjualan produk utama pada provinsi lain ke 3 |
| 46 | `PPRV3YPR` | `PPRV3YPR` | N5.2 | Prosentase penjualan produk utama pada provinsi lain ke 3 |
| 47 | `PPRVOYPR` | `PPRVOYPR` | N5.2 | Prosentase penjualan produk utama pada provinsi lain Lainnya |
| 48 | `RND` | `RND22` | N1 | Kegiatan R&D sendiri? Kode BPS 0=Ya, 2=Tidak |
| 49 | `COSTRD` | `COSTRD22` | N1 | Membiayai kegiatan Penelitian dan Pengembangan (R&D) yang dilakukan oleh pihak lain |
| 50 | `INOV` | `INOV22` | N1 | Melakukan inovasi? Kode BPS 0=Ya, 2=Tidak |
| 51 | `AMDAL` | `AMDAL22` | N1 | Pengelolaan limbah ,Analisa mengenai dampak lingkungan hidup |
| 52 | `PPLIHI` | `PPLIHI22` | N1 | Pengelolaan limbah, Upaya pengelolaan lingkungan hidup dan upaya pemantauan lingkungan hidup |
| 53 | `SPPLHI` | `SPPLHI22` | N1 | Pengelolaan limbah, Surat pernyataan pengelolaan lingkungan hidup |
| 54 | `INSPLI` | `INSPLI22` | N1 | Pengelolaan limbah, Pengolahan limbah |
| 55 | `SOWSTE` | `SOWSTE22` | N1 | Pengelolaan limbah yang dilakukan, Limbah padat |
| 56 | `LIWSTE` | `LIWSTE22` | N1 | Pengelolaan limbah yang dilakukan, Limbah cair |
| 57 | `B3WSTE` | `B3WSTE22` | N1 | Pengelolaan limbah yang dilakukan, limbah B3 |
| 58 | `LPMNOP` | `LPMNOP22` | N5 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tetap laki-laki |
| 59 | `LPMNON` | `LPMNON22` | N5 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tidak tetap laki-laki |
| 60 | `LNMNOP` | `LNMNOP22` | N4 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tetap laki-laki |
| 61 | `LNMNON` | `LNMNON22` | N5 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tidak tetap laki-laki |
| 62 | `LPWNOP` | `LPWNOP22` | N5 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tetap Perempuan |
| 63 | `LPWNON` | `LPWNON22` | N5 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tidak tetap Perempuan |
| 64 | `LNWNOP` | `LNWNOP22` | N4 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tetap Perempuan |
| 65 | `LNWNON` | `LNWNON22` | N4 | Banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tidak tetap Perempuan |
| 66 | `LPRNOP` | `LPRNOP22` | N5 | Total banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tetap |
| 67 | `LPRNON` | `LPRNON22` | N5 | Total banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Produksi tidak tetap |
| 68 | `LNPNOP` | `LNPNOP22` | N4 | Total banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tetap |
| 69 | `LNPNON` | `LNPNON22` | N5 | Total banyaknya rata-rata per hari kerja selama tahun 2022 Pekerja Lainnya tidak tetap |
| 70 | `LTLNOF` | `LTLNOF22` | N5 | Banyak pekerja asing rata-rata per hari kerja selama tahun 2022 |
| 71 | `LTLRND` | `LTLRND22` | N4 | Banyak pekerja yang khusus melakukan Penelitian dan Pengembangan (R & D) |
| 72 | `ZPTVCU` | `ZPTVCU22` | N16.8 | Upah/gaji, upah lembur, tunjangan pekerja produksi |
| 73 | `ZNTVCU` | `ZNTVCU22` | N9.1 | Upah/gaji, upah lembur, tunjangan pekerja Lainnya |
| 74 | `ZPRVCU` | `ZPRVCU22` | N16.9 | Pengeluaran lainnya pekerja produksi (Rp) |
| 75 | `ZNRVCU` | `ZNRVCU22` | N9.1 | Pengeluaran lainnya pekerja lainnya (Rp) |
| 76 | `ZPDVCU` | `ZPDVCU22` | N10.1 | Jumlah pengeluaran pekerja produksi (Rp) |
| 77 | `ZNDVCU` | `ZNDVCU22` | N9.1 | Jumlah pengeluaran pekerja Lainnya (Rp) |
| 78 | `EPELIU` | `EPELIU22` | N8 | Banyaknya  Bensin,Pertalite,Pertamax yang digunakan selama tahun 2022 |
| 79 | `EPEVCU` | `EPEVCU22` | N9 | Nilai (Rp) seluruh Bensin,Pertalite,Pertamax yang digunakan selama tahun 2022 |
| 80 | `EPELIE` | `EPELIE22` | N7 | Banyaknya Bensin,Pertalite,Pertamax untuk pembangkit tenaga listrik selama tahun 2022 |
| 81 | `EPEVCE` | `EPEVCE22` | N8 | Nilai (Rp) Bensin,Pertalite,Pertamax untuk pembangkit tenaga listrik |
| 82 | `ESOLIU` | `ESOLIU22` | N8 | Banyaknya  Minyak Solar, Dexlite, Pertamina dex yang digunakan selama tahun 2022 |
| 83 | `ESOVCU` | `ESOVCU22` | N9 | Nilai (Rp) seluruh Minyak Solar, Dexlite, Pertamina dex  yang digunakan selama tahun 2022 |
| 84 | `ESOLIE` | `ESOLIE22` | N8 | Banyaknya Minyak Solar, Dexlite, Pertamina dex untuk pembangkit tenaga listrik selama tahun 2022 |
| 85 | `ESOVCE` | `ESOVCE22` | N9 | Nilai (Rp) Minyak Solar, Dexlite, Pertamina dex untuk pembangkit tenaga listrik selama tahun 2022 |
| 86 | `ESDLIU` | `ESDLIU22` | N9 | Banyaknya Minyak Diesel  yang digunakan selama tahun 2022 |
| 87 | `ESDVCU` | `ESDVCU22` | N10 | Nilai (Rp) seluruh Minyak Diesel yang digunakan selama tahun 2022 |
| 88 | `ESDLIE` | `ESDLIE22` | N8 | Banyaknya Minyak Diesel untuk pembangkit tenaga listrik selama tahun 2022 |
| 89 | `ESDVCE` | `ESDVCE22` | N9 | Nilai (Rp) Minyak Diesel untuk pembangkit tenaga listrik selama tahun 2022 |
| 90 | `EDILIU` | `EDILIU22` | N8 | Banyaknya Bio Solar/Bio Diesel yang digunakan selama tahun 2022 |
| 91 | `EDIVCU` | `EDIVCU22` | N9 | Nilai (Rp)  Bio Solar/Bio Diesel seluruh  yang digunakan selama tahun 2022 |
| 92 | `EDILIE` | `EDILIE22` | N8 | Banyaknya Bio Solar/Bio Diesel untuk pembangkit tenaga listrik selama tahun 2022 |
| 93 | `EDIVCE` | `EDIVCE22` | N9 | Nilai (Rp)  Bio Solar/Bio Diesel untuk pembangkit tenaga listrik selama tahun 2022 |
| 94 | `ECLKGU` | `ECLKGU22` | N8 | Banyaknya Batubara yang digunakan selama tahun 2022 |
| 95 | `ECLVCU` | `ECLVCU22` | N10 | Nilai (Rp) seluruh Batubara yang digunakan selama tahun 2022 |
| 96 | `ECLKGE` | `ECLKGE22` | N8 | Banyaknya Batubara untuk pembangkit tenaga listrik selama tahun 2022 |
| 97 | `ECLVCE` | `ECLVCE22` | N10 | Nilai (Rp) seluruh Batubara untuk pembangkit tenaga listrik selama tahun 2022 |
| 98 | `ECKKGU` | `ECKKGU22` | N6 | Banyaknya  Kokas yang digunakan selama tahun 2022 |
| 99 | `ECKVCU` | `ECKVCU22` | N10 | Nilai (Rp) seluruh Kokas yang digunakan selama tahun 2022 |
| 100 | `ECKKGE` | `ECKKGE22` | N5 | Banyaknya  Kokas untuk pembangkit tenaga listrik selama tahun 2022 |
| 101 | `ECKVCE` | `ECKVCE22` | N9 | Nilai (Rp) seluruh Kokas untuk pembangkit tenaga listrik selama tahun 2022 |
| 102 | `ECBKGU` | `ECBKGU22` | N8 | Banyaknya Briket Batubara yang digunakan selama tahun 2022 |
| 103 | `ECBVCU` | `ECBVCU22` | N9 | Nilai (Rp) seluruh Briket Batubara yang digunakan selama tahun 2022 |
| 104 | `ECBKGE` | `ECBKGE` | N1 | Banyaknya Briket Batubara untuk pembangkit Tenaga Listrik selama tahun 2022 |
| 105 | `ECBVCE` | `ECBVCE` | N1 | Nilai (Rp) seluruh Briket Batubara untuk pembangkit Tenaga Listrik selama tahun 2022 |
| 106 | `ENGKGU` | `ENGKGU22` | N7 | Banyaknya  Gas Alam yang digunakan selama tahun 2022 |
| 107 | `ENGVCU` | `ENGVCU22` | N9 | Nilai (Rp) seluruhnya Gas Alam seluruh  yang digunakan selama tahun 2022 |
| 108 | `ENGKGE` | `ENGKGE22` | N7 | Banyaknya Gas Alam seluruh  yang digunakan selama tahun 2022 |
| 109 | `ENGVCE` | `ENGVCE22` | N9 | Nilai (Rp) seluruh Gas Alam untuk pembangkit tenaga listrik selama tahun 2022 |
| 110 | `EFOLIU` | `EFOLIU22` | N7 | Banyaknya  Minyak Bakar yang digunakan selama tahun 2022 |
| 111 | `EFOVCU` | `EFOVCU22` | N8 | Nilai (Rp) seluruh Minyak Bakar yang digunakan selama tahun 2022 |
| 112 | `EFOLIE` | `EFOLIE22` | N7 | Banyaknya  Minyak Bakar untuk pembangkit tenaga listrik selama tahun 2022 |
| 113 | `EFOVCE` | `EFOVCE22` | N8 | Nilai (Rp) seluruh Minyak Bakar untuk tenaga listrik selama tahun 2022 |
| 114 | `ELPKGU` | `ELPKGU22` | N8 | Banyaknya LPG yang digunakan selama tahun 2022 |
| 115 | `ELPVCU` | `ELPVCU22` | N9 | Nilai (Rp) seluruh LPG yang digunakan selama tahun 2022 |
| 116 | `ELPKGE` | `ELPKGE22` | N6 | Banyaknya LPG untuk pembangkit tenaga listrik selama tahun 2022 |
| 117 | `ELPVCE` | `ELPVCE22` | N7 | Nilai (Rp) seluruh LPG untuk pembangkit tenaga listrik selama tahun 2022 |
| 118 | `ECAKGU` | `ECAKGU22` | N8 | Banyaknya Biomassa yang digunakan selama tahun 2022 |
| 119 | `ECAVCU` | `ECAVCU22` | N9 | Nilai (Rp) seluruh  Biomassa yang digunakan selama tahun 2022 |
| 120 | `ECAKGE` | `ECAKGE22` | N8 | Banyaknya Biomassa untuk pembangkit tenaga listrik selama tahun 2022 |
| 121 | `ECAVCE` | `ECAVCE22` | N9 | Nilai (Rp) seluruh  Biomassa untuk pembangkit tenaga listrik selama tahun 2022 |
| 122 | `ECADES` | `ECADES22` | C72 | Jenis Biomassa lainnya (tuliskan) |
| 123 | `ENCVCU` | `ENCVCU22` | N9 | Nilai (Rp) seluruh Bahan bakar lainnya, tuliskan yang digunakan selama tahun 2022 |
| 124 | `ENCVCE` | `ENCVCE22` | N10 | Nilai (Rp) seluruh Bahan bakar lainnya, tuliskan untuk pembangkit tenaga listrik selama tahun 2022 |
| 125 | `ENCDES` | `ENCDES22` | C56 | Jenis bahan bakar lainnya (tuliskan) |
| 126 | `ELULIU` | `ELULIU22` | N8 | Banyaknya Pelumas yang digunakan selama tahun 2022 |
| 127 | `ELUVCU` | `ELUVCU22` | N9 | Nilai (Rp) seluruh Pelumas yang digunakan selama tahun 2022 |
| 128 | `ELULIE` | `ELULIE22` | N9 | Banyaknya Pelumas untuk pembangkit tenaga listrik selama tahun 2022 |
| 129 | `ELUVCE` | `ELUVCE22` | N8 | Nilai (Rp) seluruh Pelumas pembangkit tenaga listrik selama tahun 2022 |
| 130 | `EFUVCU` | `EFUVCU22` | N10 | Jumlah Nilai (Rp) seluruhnya bahan bakar dan pelumas yang digunakan selama tahun 2022 |
| 131 | `EFUVCE` | `EFUVCE22` | N1 | Jumlah Nilai (Rp) seluruhnya bahan bakar dan pelumas untuk tenaga listrik selama tahun 2022 |
| 132 | `EPCKVA` | `EPCKVA22` | N10 | Daya tersambung PLN yang dipakai |
| 133 | `EPLKHU` | `EPLKHU22` | N10 | Banyaknya Penggunaan listrik PLN yang dipakai   (kwh) |
| 134 | `EPLVCU` | `EPLVCU22` | N10 | Nilai (Rp) Penggunaan listrik PLN yang dipakai  (.000) |
| 135 | `ENPKHU` | `ENPKHU22` | N10 | Banyaknya Penggunaan listrik Non PLN yang dipakai (kwh) |
| 136 | `ENPVCU` | `ENPVCU22` | N10 | Nilai (Rp) Penggunaan listrik Non PLN yang dipakai (.000) |
| 137 | `MGEKIN` | `MGEKIN22` | C49 | Jenis pembangkit listrik yang digunakan |
| 138 | `MGENOU` | `MGENOU22` | N10 | Banyaknya pembangkit listrik yang digunakan |
| 139 | `MGEKWU` | `MGEKWU22` | N11 | Kapasitas terpasang pembangkit listrik yang digunakan |
| 140 | `ESGKHU` | `ESGKHU22` | N10 | Tenaga listrik yang dibangkitkan oleh perusahaan (kwh) |
| 141 | `OEUKHU` | `OEUKHU22` | N10 | Tenaga listrik digunakan sendiri oleh perusahaan |
| 142 | `OELKHU` | `OELKHU22` | N9 | Tenaga listrik yang dijual |
| 143 | `IBRVCU` | `IBRVCU22` | N10 | Pengeluaran untuk sewa atau kontrak Gedung, mesin, serta alat-alat |
| 144 | `ILRVCU` | `ILRVCU22` | N10 | Pengeluaran untuk sewa atau kontrak Tanah |
| 145 | `ITXVCU` | `ITXVCU22` | N10 | Pajak/ Tax |
| 146 | `IISLOV` | `IISLOV22` | N10 | Jasa industri (maklun) yang dibayarkan ke pihak lain Dalam negeri |
| 147 | `IISFOV` | `IISFOV22` | N10 | Jasa industri (maklun) yang dibayarkan ke pihak lain Luar negeri |
| 148 | `IINVCU` | `IINVCU22` | N10 | Pengeluaran Bunga atas pinjaman |
| 149 | `ICOVCU` | `ICOVCU22` | N9 | Pengeluaran Hadiah, sumbangan, derma dan sejenisnya |
| 150 | `IPKVCU` | `IPKVCU22` | N9 | Pengeluaran Kemasan |
| 151 | `IDEVCU` | `IDEVCU22` | N11 | Pengeluaran Dividen/laba yang dibagikan |
| 152 | `IPRVCU` | `IPRVCU22` | N10 | Pengeluaran Premi asuransi kerugian yang dibayarkan |
| 153 | `IRDVCU` | `IRDVCU22` | N9 | Pengeluaran Biaya penelitian dan pengembangan (R&D). Tidak termasuk pengeluaran untuk pekerja/karyawan yang khusus melakukan R&D |
| 154 | `IKLVCU` | `IKLVCU22` | N9 | Pengeluaran Kekayaan intelektual (Paten, Merk, Hak Cipta, Desain Industri, Royalti) yang dibayarkan ke pihak lain dalam negeri |
| 155 | `IKOVCU` | `IKOVCU22` | N9 | Kekayaan intelektual (Paten, Merk, Hak Cipta, Desain Industri, Royalti) yang dibayarkan ke pihak lain luar negeri |
| 156 | `IUWVCU` | `IUWVCU22` | N9 | Pengeluaran Air (Nilai pengeluaran air selain untuk bahan baku dan penolong) |
| 157 | `IOTVCU` | `IOTVCU22` | N11.3 | Pengeluaran Lainnya |
| 158 | `IT1VCU` | `IT1VCU22` | N11.3 | Jumlah pengeluaran lain selama tahun 2022 |
| 159 | `IMPOR` | `IMPOR22` | N1 | Impor bahan baku langsung? Kode BPS 0=Ya, 2=Tidak (import flag) |
| 160 | `RDNVCU` | `RDNVCU22` | N11 | Nilai (Rp) bahan baku dan bahan penolong produksi dalam negeri yang digunakan selama tahun 2022 |
| 161 | `RIMVCU` | `RIMVCU22` | N11 | Nilai (Rp) bahan baku dan bahan penolong Impor yang digunakan selama tahun 2022 |
| 162 | `PRPRCA` | `PRPRCA22` | N11.8 | Persentase realisasi produksi terhadap kapasitas (%) |
| 163 | `EKSPOR` | `EKSPOR22` | N1 | Ekspor langsung? Kode BPS 0=Ya, 2=Tidak (export flag) |
| 164 | `YPRVCU` | `YPRVCU22` | N16.7 | Nilai produksi / production value (Rp .000) |
| 165 | `YISVDO` | `YISVDO22` | N11 | Pendapatan dari jasa industri (maklun) Dalam negeri |
| 166 | `YISVFO` | `YISVFO22` | N10 | Pendapatan dari jasa industri (maklun) Luar negeri |
| 167 | `YISVCU` | `YISVCU22` | N11 | Jumlah Pendapatan dari jasa industri (maklun) |
| 168 | `YRSVCU` | `YRSVCU22` | N10 | Nilai (Rp) Keuntungan/kerugian penjualan barang dalam bentuk yang sama |
| 169 | `YKDVCU` | `YKDVCU22` | N10 | Nilai (Rp) Penjualan kekayaan intelektual (Paten, Merk, Hak Cipta, Desain Industri) dalam negeri |
| 170 | `YKFVCU` | `YKFVCU22` | N5 | Nilai (Rp) Penjualan kekayaan intelektual (Paten, Merk, Hak Cipta, Desain Industri) luar negeri |
| 171 | `YSNVCU` | `YSNVCU22` | N10 | Nilai (Rp) Jasa yang tidak berkaitan dengan proses produksi |
| 172 | `YELVCU` | `YELVCU22` | N9 | Nilai (Rp) Tenaga listrik yang dijual |
| 173 | `NOPVCU` | `NOPVCU22` | N10 | Nilai (Rp) Pendapatan non operasional (Laba/Dividen yang diterima, bunga atas simpanan dan piutang, pendapatan dari sewa lahan, klaim asuransi kerugian yang diterima) |
| 174 | `YRNVCU` | `YRNVCU22` | N11 | Nilai (Rp) Lainnya |
| 175 | `YTOVCU` | `YTOVCU22` | N11 | Jumlah Nilai (Rp) Pendapatan Lainnya |
| 176 | `SRJVCU` | `SRJVCU22` | N11 | Nilai (Rp) persediaan awal stok bahan baku, bahan penolong, bahan bakar, bahan pembungkus, dan lain-lain |
| 177 | `SRDVCU` | `SRDVCU22` | N10 | Nilai (Rp) persediaan akhir tahun 2022 stok bahan baku, bahan penolong, bahan bakar, bahan pembungkus, dan lain-lain |
| 178 | `SHJVCU` | `SHJVCU22` | N10 | Nilai (Rp) Persediaan awal tahun 2022 stok barang produksi setengah jadi (dinilai sesuai dengan nilai bahan baku ditambah nilai pekerjaan yang dilakukan) |
| 179 | `SHDVCU` | `SHDVCU22` | N10 | Nilai (Rp) akhir tahun 2022 stok barang produksi setengah jadi (dinilai sesuai dengan nilai bahan baku ditambah nilai pekerjaan yang dilakukan) |
| 180 | `SFJVCU` | `SFJVCU22` | N10 | Nilai (Rp) persediaan awal tahun 2022 Nilai stok barang jadi yang dihasilkan |
| 181 | `SFDVCU` | `SFDVCU22` | N10 | Nilai (Rp) persediaan akhir  tahun 2022 Nilai stok barang jadi yang dihasilkan |
| 182 | `STJVCU` | `STJVCU22` | N11 | Jumlah Nilai (Rp) persediaan awal tahun 2022 |
| 183 | `STDVCU` | `STDVCU22` | N11 | Jumlah Nilai (Rp) persediaan akhir tahun 2022 |
| 184 | `CLFPCU` | `CLFPCU22` | N11 | Nilai (Rp) taksiran Tanah , posisi awal tahun Tanah |
| 185 | `CLTTCU` | `CLTTCU22` | N11 | Nilai (Rp) taksiran Tanah Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 186 | `CLSACU` | `CLSACU22` | N11 | Nilai taksiran Tanah Penjualan/ pengurangan barang modal |
| 187 | `V1101` | `V1101` | N11 | Nilai (Rp) taksiran Tanah menurut harga berlaku per 31 desember 2022 |
| 188 | `CBFPCU` | `CBFPCU22` | N11 | Nilai (Rp) taksiran Gedung , posisi awal tahun 2022 |
| 189 | `CBTTCU` | `CBTTCU22` | N11 | Nilai (Rp) taksiran Gedung Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 190 | `CBSACU` | `CBSACU22` | N11 | Nilai taksiran Gedung Penjualan/ pengurangan barang modal |
| 191 | `V1103` | `V1103` | N11 | Nilai (Rp) taksiran Gedung menurut harga berlaku per 31 desember 2022 |
| 192 | `CMFPCU` | `CMFPCU22` | N12.3 | Nilai (Rp) taksiran Mesin dan perlengkapan , posisi awal tahun 2022 |
| 193 | `CMTTCU` | `CMTTCU22` | N11.3 | Nilai (Rp) taksiran Mesin dan perlengkapan Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 194 | `CMSACU` | `CMSACU22` | N11 | Nilai taksiran Mesin dan perlengkapan Penjualan/ pengurangan barang modal |
| 195 | `V1106` | `V1106` | N12.3 | Nilai (Rp) taksiran Mesin dan perlengkapan menurut harga berlaku per 31 desember 2022 |
| 196 | `CVFPCU` | `CVFPCU22` | N11 | Nilai (Rp) taksiran Kendaraan, posisi awal tahun 2022 |
| 197 | `CVTTCU` | `CVTTCU22` | N11.1 | Nilai (Rp) taksiran  Kendaraan Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 198 | `CVSACU` | `CVSACU22` | N11 | Nilai taksiran  Kendaraan Penjualan/ pengurangan barang modal |
| 199 | `V1109` | `V1109` | N11.1 | Nilai (Rp) taksiran  Kendaraan menurut harga berlaku per 31 desember 2022 |
| 200 | `CSFPCU` | `CSFPCU22` | N11 | Nilai (Rp) taksiran Software/Data base , posisi awal tahun 2022 |
| 201 | `CSTTCU` | `CSTTCU22` | N11 | Nilai (Rp) taksiran Software/Data base Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 202 | `R601E_K4` | `R601E_K4` | N11 | Nilai taksiran Software/Data base Penjualan/ pengurangan barang modal |
| 203 | `V1110` | `V1110` | N11 | Nilai (Rp) taksiran Software/Data base menurut harga berlaku per 31 desember 2022 |
| 204 | `COFPCU` | `COFPCU22` | N11 | Nilai (Rp) taksiran Lainnya , posisi awal tahun 2022 |
| 205 | `COTTCU` | `COTTCU22` | N11 | Nilai (Rp) taksiran Lainnya Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 206 | `COSACU` | `COSACU22` | N11 | Nilai taksiran Lainnya Penjualan/ pengurangan barang modal |
| 207 | `V1112` | `V1112` | N11 | Nilai (Rp) taksiran Lainnya menurut harga berlaku per 31 desember 2022 |
| 208 | `CTFPCU` | `CTFPCU22` | N12.3 | Jumlah Nilai (Rp) posisi awal tahun modal tetap tahun 2022 |
| 209 | `CTTTCU` | `CTTTCU22` | N12.3 | Jumlah Nilai (Rp) taksiran Pembelian/ penambahan dan pembuatan/ perbaikan besar |
| 210 | `CTSACU` | `CTSACU22` | N12 | Jumlah Nilai (Rp) taksiran  Penjualan/ pengurangan barang modal |
| 211 | `V1125` | `V1125` | N12.3 | Jumlah Nilai (Rp) taksiran  menurut harga berlaku per 31 desember 2022 |
| 212 | `R1001A` | `R1001A` | N10.1 | Nilai (Rp) Pekerja (R.301 jumlah) kolom (2) + kolom (3) |
| 213 | `R1001B` | `R1001B` | N10 | Nilai Bahan bakar (R.302 jumlah) kolom (4) |
| 214 | `R1001C` | `R1001C` | N10 | Nilai Nilai tenaga listrik (R.303.a + R.303.b) kolom (3) |
| 215 | `R1001D` | `R1001D` | N11.3 | Nilai Pengeluaran lainnya (R.306 jumlah) kolom (2) |
| 216 | `R1001E` | `R1001E` | N11 | Nilai Bahan baku dan penolong (R.307.b.Jumlah kolom (5) + kolom (7)) |
| 217 | `R1001SUM` | `R1001SUM` | N14.3 | Jumlah Nilai (Rp) 1001 |
| 218 | `R1002A` | `R1002A` | N16.7 | Nilai (Rp) Barang-barang yang dihasilkan (R.402.b jumlah) kolom (6) |
| 219 | `RTLVCU` | `RTLVCU22` | N11 | Nilai (Rp) Jasa industri (R.501 jumlah) kolom (2) |
| 220 | `SRMVCU` | `SRMVCU22` | N11 | Nilai (Rp) Pendapatan lainnya (R.502 jumlah - R.502.e) kolom (2) |
| 221 | `SHFVCU` | `SHFVCU22` | N11 | Nilai (Rp) Selisih nilai stok barang (R.503.b) kolom (3)-(2) |
| 222 | `SFNVCU` | `SFNVCU22` | N11 | Jumlah Nilai (Rp)  1002 |
| 223 | `STLVCU` | `STLVCU22` | N12 | Rekap R.306.a.2 sewa tanah (Rp .000) |
| 224 | `LPRNOU` | `LPRNOU22` | N5 | Rekap R.306.b pajak tak langsung (Rp .000) |
| 225 | `LNPNOU` | `LNPNOU22` | N5 | Rekap R.306.d bunga atas pinjaman (Rp .000) |
| 226 | `LTLNOU` | `LTLNOU22` | N5 | Rekap R.306.e hadiah/sumbangan/derma (Rp .000) |
| 227 | `PENGTK` | `PENGTK22` | N10.1 | Jumlah pengeluaran tenaga kerja / total labour cost (Rp .000) |
| 228 | `OUTPUT` | `OUTPUT22` | N16.7 | Nilai output / total output (Rp .000) |
| 229 | `IINPUT` | `IINPUT22` | N13.3 | Biaya antara / total intermediate input (Rp .000) |
| 230 | `VTLVCU` | `VTLVCU22` | N16.8 | Nilai tambah / value added = OUTPUT - IINPUT (Rp .000) |
| 231 | `RENUM` | `RENUM` | N5 | Identitas Hasil Renumbering |

## IMK Tabel 1 — Industri Mikro Kecil (166 var + PROV)

| # | Variabel (dummy) | Variabel asli BPS | Tipe | Keterangan |
|--:|---|---|---|---|
| 1 | `TAHUN` | `TAHUN` | C4 | Tahun survei |
| 2 | `KBLI` | `KBLI` | C2 | Kode Baku Klasifikasi Indonesia 2 digit |
| 3 | `KLAS` | `KLAS` | C1 | Klasifikasi Usaha |
| 4 | `WEIGHT` | `WEIGHT` | N16.14 | Penimbang |
| 5 | `R205` | `R205` | C2 | Kode KBLI 2-digit |
| 6 | `R206B` | `R206B` | C1 | Jenis kelamin pengusaha |
| 7 | `R206C` | `R206C` | N2 | Umur pengusaha |
| 8 | `R206D` | `R206D` | C1 | Jenjang pendidikan tertinggi yang ditamatkan pengusaha |
| 9 | `R207A1` | `R207A1` | C1 | Kepemilikan Nomor Induk Berusaha (NIB) |
| 10 | `R207A2` | `R207A2` | C1 | Kepemilikan Surat Izin Usaha Perdagangan (SIUP) |
| 11 | `R207B` | `R207B` | C1 | Status badan hukum/usaha |
| 12 | `R207C1` | `R207C1` | C1 | Dapat memisahkan pendapatan di pencatatan keuangan usaha dari catatan keuangan rumah tangga |
| 13 | `R207C2` | `R207C2` | C1 | Dapat memisahkan pengeluaran di pencatatan keuangan usaha dari catatan keuangan rumah tangga |
| 14 | `R207C3` | `R207C3` | C1 | Dapat memisahkan aset di pencatatan keuangan usaha dari catatan keuangan rumah tangga |
| 15 | `R207C4` | `R207C4` | C1 | Dapat memisahkan tabungan/hutang di pencatatan keuangan usaha dari catatan keuangan rumah tangga |
| 16 | `R208` | `R208` | N4 | Tahun mulai berdiri |
| 17 | `R209` | `R209` | N4 | Tahun mulai berproduksi secara komersial |
| 18 | `R210` | `R210` | C1 | Apakah usaha/perusahaan menjadi anggota koperasi? |
| 19 | `R301A1` | `R301A1` | C1 | Pemanfaatan internet untuk pemasaran produk |
| 20 | `R301A2` | `R301A2` | C1 | Pemanfaatan internet untuk pemesanan bahan baku |
| 21 | `R301A3` | `R301A3` | C1 | Pemanfaatan internet untuk pembayaran transaksi |
| 22 | `R301A4` | `R301A4` | C1 | Pemanfaatan internet untuk pinjaman fintech |
| 23 | `R301A5` | `R301A5` | C1 | Pemanfaatan internet untuk pencarian informasi pengembangan usaha/perusahaan |
| 24 | `R301B1` | `R301B1` | C1 | Jenis Platform Pemasaran: Instant messaging (whatsapp, telegram, dll) |
| 25 | `R301B2` | `R301B2` | C1 | Jenis Platform Pemasaran: Market place (Tokopedia, Lazada, Shopee, dll) |
| 26 | `R301B3` | `R301B3` | C1 | Jenis Platform Pemasaran: Media sosial (facebook, twitter/X, instagram, tiktok, dll) |
| 27 | `R301B4` | `R301B4` | C1 | Jenis Platform Pemasaran: E-mail (gmail, yahoo, outlook, dll) |
| 28 | `R301B5` | `R301B5` | C1 | Jenis Platform Pemasaran: Website |
| 29 | `R301B6` | `R301B6` | C1 | Jenis Platform Pemasaran: e-Katalog LKPP |
| 30 | `R301C` | `R301C` | C2 | Alasan tidak memanfaatkan internet |
| 31 | `R3021` | `R3021` | C1 | Sertifikasi standar nasional/internasional pada produk yang dihasilkan: Sertifikasi Standar Nasional Indonesia (SNI) |
| 32 | `R3022` | `R3022` | C1 | Sertifikasi standar nasional/internasional pada produk yang dihasilkan: Sertifikat Halal |
| 33 | `R3023` | `R3023` | C1 | Sertifikasi standar nasional/internasional pada produk yang dihasilkan: SPP-IRT |
| 34 | `R303` | `R303` | C1 | Apakah produk yang dihasilkan memiliki sertifikat hak paten/hak cipta/Hak atas Kekayaan Intelektual (HaKI)? |
| 35 | `R304A1` | `R304A1` | C1 | Inovasi: produk |
| 36 | `R304A2` | `R304A2` | C1 | Inovasi: pemasaran dan distribusi |
| 37 | `R304A3` | `R304A3` | C1 | Inovasi: teknologi/proses produksi |
| 38 | `R304A4` | `R304A4` | C1 | Inovasi: lainnya |
| 39 | `R304B` | `R304B` | C1 | Siapakah yang Mengembangkan Inovasi Tersebut? |
| 40 | `R305A1` | `R305A1` | C1 | Kendala/Kesulitan: Bahan Baku |
| 41 | `R305A2` | `R305A2` | C1 | Kendala/Kesulitan: Permodalan |
| 42 | `R305A3` | `R305A3` | C1 | Kendala/Kesulitan: Pemasaran/Penjualan Produk |
| 43 | `R305A4` | `R305A4` | C1 | Kendala/Kesulitan: BBM, Listrik dan Gas |
| 44 | `R305A5` | `R305A5` | C1 | Kendala/Kesulitan: Infrastruktur (Jalan, Air, Komunikasi, dan Lainnya) |
| 45 | `R305A6` | `R305A6` | C1 | Kendala/Kesulitan: Tenaga Kerja |
| 46 | `R305B` | `R305B` | C1 | Alasan utama kendala bahan baku |
| 47 | `R306A1` | `R306A1` | C1 | Jenis Kemitraan yang Pernah Dilakukan oleh Usaha/Perusahaan selama Setahun yang lalu: Permodalan |
| 48 | `R306A2` | `R306A2` | C1 | Jenis Kemitraan yang Pernah Dilakukan oleh Usaha/Perusahaan selama Setahun yang lalu: Bahan Baku |
| 49 | `R306A3` | `R306A3` | C1 | Jenis Kemitraan yang Pernah Dilakukan oleh Usaha/Perusahaan selama Setahun yang lalu: Pemasaran |
| 50 | `R306A4` | `R306A4` | C1 | Jenis Kemitraan yang Pernah Dilakukan oleh Usaha/Perusahaan selama Setahun yang lalu: Barang modal (Mesin/sarana/prasarana/peralatan) |
| 51 | `R306A5` | `R306A5` | C1 | Jenis Kemitraan yang Pernah Dilakukan oleh Usaha/Perusahaan selama Setahun yang lalu: Lainnya |
| 52 | `R306B1` | `R306B1` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Inti Plasma |
| 53 | `R306B2` | `R306B2` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Sub Kontrak |
| 54 | `R306B3` | `R306B3` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Perdagangan Umum/Konsinyasi |
| 55 | `R306B4` | `R306B4` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Bagi Hasil |
| 56 | `R306B5` | `R306B5` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Kerja Sama Operasional |
| 57 | `R306B6` | `R306B6` | C1 | Bentuk/pola kemitraan yang dilaksanakan: Usaha Patungan (joint venture) |
| 58 | `R3071` | `R3071` | C1 | Badan/lembaga yang pernah memberi pelayanan/bantuan: instansi pemerintah |
| 59 | `R3072` | `R3072` | C1 | Badan/lembaga yang pernah memberi pelayanan/bantuan: perusahaan swasta |
| 60 | `R3073` | `R3073` | C1 | Badan/lembaga yang pernah memberi pelayanan/bantuan: perbankan |
| 61 | `R3074` | `R3074` | C1 | Badan/lembaga yang pernah memberi pelayanan/bantuan: yayasan/LSM |
| 62 | `R3075` | `R3075` | C1 | Badan/lembaga yang pernah memberi pelayanan/bantuan: koperasi |
| 63 | `R3081` | `R3081` | C1 | Jenis bimbingan/pelatihan/penyuluhan: Manajerial |
| 64 | `R3082` | `R3082` | C1 | Jenis bimbingan/pelatihan/penyuluhan: Keterampilan/Teknik Produksi |
| 65 | `R3083` | `R3083` | C1 | Jenis bimbingan/pelatihan/penyuluhan: Pemasaran |
| 66 | `R3084` | `R3084` | C1 | Jenis bimbingan/pelatihan/penyuluhan: AMDAL |
| 67 | `R3091` | `R3091` | C1 | Teknologi proses kegiatan: manual |
| 68 | `R3092` | `R3092` | C1 | Teknologi proses kegiatan: mekanik |
| 69 | `R3093` | `R3093` | C1 | Teknologi proses kegiatan: elektronik |
| 70 | `R3094` | `R3094` | C1 | Teknologi proses kegiatan: digital |
| 71 | `R401AK3` | `R401AK3` | N2 | Banyaknya pekerja: Juli 2023 |
| 72 | `R401AK4` | `R401AK4` | N2 | Banyaknya pekerja: Agustus 2023 |
| 73 | `R401AK5` | `R401AK5` | N2 | Banyaknya pekerja: September 2023 |
| 74 | `R401AK6` | `R401AK6` | N2 | Banyaknya pekerja: Oktober 2023 |
| 75 | `R401AK7` | `R401AK7` | N2 | Banyaknya pekerja: November 2023 |
| 76 | `R401AK8` | `R401AK8` | N2 | Banyaknya pekerja: Desember 2023 |
| 77 | `R401AK9` | `R401AK9` | N2 | Banyaknya pekerja: Januari 2024 |
| 78 | `R401AK10` | `R401AK10` | N2 | Banyaknya pekerja: Februari 2024 |
| 79 | `R401AK11` | `R401AK11` | N2 | Banyaknya pekerja: Maret 2024 |
| 80 | `R401AK12` | `R401AK12` | N2 | Banyaknya pekerja: April 2024 |
| 81 | `R401AK13` | `R401AK13` | N2 | Banyaknya pekerja: Mei 2024 |
| 82 | `R401AK14` | `R401AK14` | N2 | Banyaknya pekerja: Juni 2024 |
| 83 | `R401BK3` | `R401BK3` | N2 | Hari kerja per bulan: Juli 2023 |
| 84 | `R401BK4` | `R401BK4` | N2 | Hari kerja per bulan: Agustus 2023 |
| 85 | `R401BK5` | `R401BK5` | N2 | Hari kerja per bulan: September 2023 |
| 86 | `R401BK6` | `R401BK6` | N2 | Hari kerja per bulan: Oktober 2023 |
| 87 | `R401BK7` | `R401BK7` | N2 | Hari kerja per bulan: November 2023 |
| 88 | `R401BK8` | `R401BK8` | N2 | Hari kerja per bulan: Desember 2023 |
| 89 | `R401BK9` | `R401BK9` | N2 | Hari kerja per bulan: Januari 2024 |
| 90 | `R401BK10` | `R401BK10` | N2 | Hari kerja per bulan: Februari 2024 |
| 91 | `R401BK11` | `R401BK11` | N2 | Hari kerja per bulan: Maret 2024 |
| 92 | `R401BK12` | `R401BK12` | N2 | Hari kerja per bulan: April 2024 |
| 93 | `R401BK13` | `R401BK13` | N2 | Hari kerja per bulan: Mei 2024 |
| 94 | `R401BK14` | `R401BK14` | N2 | Hari kerja per bulan: Juni 2024 |
| 95 | `R401CK3` | `R401CK3` | N2 | Rata-rata jam kerja per hari: Juli 2023 |
| 96 | `R401CK4` | `R401CK4` | N2 | Rata-rata jam kerja per hari: Agustus 2023 |
| 97 | `R401CK5` | `R401CK5` | N2 | Rata-rata jam kerja per hari: September 2023 |
| 98 | `R401CK6` | `R401CK6` | N2 | Rata-rata jam kerja per hari: Oktober 2023 |
| 99 | `R401CK7` | `R401CK7` | N2 | Rata-rata jam kerja per hari: November 2023 |
| 100 | `R401CK8` | `R401CK8` | N2 | Rata-rata jam kerja per hari: Desember 2023 |
| 101 | `R401CK9` | `R401CK9` | N2 | Rata-rata jam kerja per hari: Januari 2024 |
| 102 | `R401CK10` | `R401CK10` | N2 | Rata-rata jam kerja per hari: Februari 2024 |
| 103 | `R401CK11` | `R401CK11` | N2 | Rata-rata jam kerja per hari: Maret 2024 |
| 104 | `R401CK12` | `R401CK12` | N2 | Rata-rata jam kerja per hari: April 2024 |
| 105 | `R401CK13` | `R401CK13` | N2 | Rata-rata jam kerja per hari: Mei 2024 |
| 106 | `R401CK14` | `R401CK14` | N2 | Rata-rata jam kerja per hari: Juni 2024 |
| 107 | `R402AK2` | `R402AK2` | N2 | Jenis pekerja: laki-laki |
| 108 | `R402AK3` | `R402AK3` | N2 | Jenis pekerja: perempuan |
| 109 | `R402AK4` | `R402AK4` | N2 | Jumlah jenis pekerja |
| 110 | `R402A1K2` | `R402A1K2` | N2 | Banyaknya Pekerja dibayar: laki-laki |
| 111 | `R402A1K3` | `R402A1K3` | N2 | Banyaknya Pekerja dibayar: perempuan |
| 112 | `R402A1K4` | `R402A1K4` | N2 | Jumlah pekerja dibayar |
| 113 | `R402A2K2` | `R402A2K2` | N2 | Banyaknya pekerja tidak dibayar: laki-laki |
| 114 | `R402A2K3` | `R402A2K3` | N2 | Banyaknya tidak dibayar: perempuan |
| 115 | `R402A2K4` | `R402A2K4` | N2 | Jumlah pekerja tidak dibayar |
| 116 | `R402BK2` | `R402BK2` | N2 | Kelompok umur: laki-laki |
| 117 | `R402BK3` | `R402BK3` | N2 | Kelompok umur: perempuan |
| 118 | `R402BK4` | `R402BK4` | N2 | Jumlah kelompok umur |
| 119 | `R402B1K2` | `R402B1K2` | N1 | Banyaknya pekerja umur kurang dari 15 tahun: laki-laki |
| 120 | `R402B1K3` | `R402B1K3` | N1 | Banyaknya pekerja umur kurang dari 15 tahun: perempuan |
| 121 | `R402B1K4` | `R402B1K4` | N1 | Jumlah pekerja umur kurang dari 15 tahun |
| 122 | `R402B2K2` | `R402B2K2` | N2 | Banyaknya pekerja umur 15-24 tahun: laki-laki |
| 123 | `R402B2K3` | `R402B2K3` | N2 | Banyaknya pekerja umur 15-24 tahun: perempuan |
| 124 | `R402B2K4` | `R402B2K4` | N2 | Jumlah pekerja umur 15-24 tahun |
| 125 | `R402B3K2` | `R402B3K2` | N2 | Banyaknya pekerja umur 25-64 tahun: laki-laki |
| 126 | `R402B3K3` | `R402B3K3` | N2 | Banyaknya pekerja umur 25-64 tahun: perempuan |
| 127 | `R402B3K4` | `R402B3K4` | N2 | Jumlah pekerja umur 25-64 tahun |
| 128 | `R402B4K2` | `R402B4K2` | N2 | Banyaknya pekerja umur 65 tahun ke atas: laki-laki |
| 129 | `R402B4K3` | `R402B4K3` | N1 | Banyaknya pekerja umur 65 tahun ke atas: perempuan |
| 130 | `R402B4K4` | `R402B4K4` | N2 | Jumlah pekerja umur 65 tahun ke atas |
| 131 | `R402CK2` | `R402CK2` | N2 | Pendidikan tertinggi yang ditamatkan: pekerja laki-laki |
| 132 | `R402CK3` | `R402CK3` | N2 | Pendidikan tertinggi yang ditamatkan: pekerja perempuan |
| 133 | `R402CK4` | `R402CK4` | N2 | Jumlah pekerja pendidikan tertinggi yang ditamatkan |
| 134 | `R402C1K2` | `R402C1K2` | N2 | Banyaknya pekerja berpendidikan tidak tamat SD: laki-laki |
| 135 | `R402C1K3` | `R402C1K3` | N2 | Banyaknya pekerja berpendidikan tidak tamat SD: perempuan |
| 136 | `R402C1K4` | `R402C1K4` | N2 | Jumlah pekerja berpendidikan tidak tamat SD |
| 137 | `R402C2K2` | `R402C2K2` | N2 | Banyaknya pekerja berpendidikan SD dan sederajat: laki-laki |
| 138 | `R402C2K3` | `R402C2K3` | N2 | Banyaknya pekerja berpendidikan SD dan sederajat: perempuan |
| 139 | `R402C2K4` | `R402C2K4` | N2 | Jumlah pekerja berpendidikan SD dan sederajat |
| 140 | `R402C3K2` | `R402C3K2` | N2 | Banyaknya pekerja berpendidikan SMP dan sederajat: laki-laki |
| 141 | `R402C3K3` | `R402C3K3` | N2 | Banyaknya pekerja berpendidikan SMP dan sederajat: perempuan |
| 142 | `R402C3K4` | `R402C3K4` | N2 | Jumlah pekerja berpendidikan SMP dan sederajat |
| 143 | `R402C4K2` | `R402C4K2` | N2 | Banyaknya pekerja berpendidikan SMA/MA/Paket C: laki-laki |
| 144 | `R402C4K3` | `R402C4K3` | N2 | Banyaknya pekerja berpendidikanSMA/MA/Paket C: perempuan |
| 145 | `R402C4K4` | `R402C4K4` | N2 | Jumlah pekerja berpendidikan SMA/MA/Paket C |
| 146 | `R402C5K2` | `R402C5K2` | N2 | Banyaknya pekerja berpendidikan SMK: laki-laki |
| 147 | `R402C5K3` | `R402C5K3` | N2 | Banyaknya pekerja berpendidikan SMK: perempuan |
| 148 | `R402C5K4` | `R402C5K4` | N2 | Jumlah pekerja berpendidikan SMK |
| 149 | `R402C6K2` | `R402C6K2` | N1 | Banyaknya pekerja berpendidikan Diploma I/II/III: laki-laki |
| 150 | `R402C6K3` | `R402C6K3` | N2 | Banyaknya pekerja berpendidikan Diploma I/II/III: perempuan |
| 151 | `R402C6K4` | `R402C6K4` | N2 | Jumlah pekerja berpendidikan Diploma I/II/III |
| 152 | `R402C7K2` | `R402C7K2` | N2 | Banyaknya pekerja berpendidikan Diploma IV/S1: laki-laki |
| 153 | `R402C7K3` | `R402C7K3` | N1 | Banyaknya pekerja berpendidikan Diploma IV/S1: perempuan |
| 154 | `R402C7K4` | `R402C7K4` | N2 | Jumlah pekerja berpendidikan Diploma IV/S1 |
| 155 | `R402C8K2` | `R402C8K2` | N1 | Banyaknya pekerja berpendidikan S2/S3: laki-laki |
| 156 | `R402C8K3` | `R402C8K3` | N1 | Banyaknya pekerja berpendidikan S2/S3: perempuan |
| 157 | `R402C8K4` | `R402C8K4` | N1 | Jumlah pekerja berpendidikan S2/S3 |
| 158 | `R403DK2` | `R403DK2` | N9 | Jumlah nilai seluruh balas jasa dalam rupiah untuk pekerja (tanpa pengusaha) pada bulan terakhir produksi |
| 159 | `R503K5` | `R503K5` | N10 | Jumlah nilai (Rp) Pendapatan pada bulan terakhir produksi |
| 160 | `R603` | `R603` | N9 | Pengeluaran non-operasional (pengeluaran bagi hasil kepada pemilik modal, bunga pinjaman yang dibayarkan, premi asuransi kerugian, pengeluaran lainnya seperti: sumbangan, CSR, dan denda |
| 161 | `R602PK5` | `R602PK5` | N9 | Jumlah nilai (Rp) Pengeluaran Umum |
| 162 | `R601NK5` | `R601NK5` | N10 | Jumlah nilai (Rp) Pengeluaran Khusus |
| 163 | `R401BKLAST` | `R401BKLAST` | N2 | Hari kerja di bulan terakhir berproduksi |
| 164 | `R401BKTOTA` | `R401BKTOTA` | N3 | (lihat layout BPS) |
| 165 | `R401CKLAST` | `R401CKLAST` | N2 | Rata-rata jam kerja di bulan terakhir berproduksi |
| 166 | `RENUM` | `RENUM` | N5 | Identitas Unik Hasil Renumbering |

## IMK Tabel 2 — Industri Mikro Kecil (36 var + PROV)

| # | Variabel (dummy) | Variabel asli BPS | Tipe | Keterangan |
|--:|---|---|---|---|
| 1 | `TAHUN` | `TAHUN` | C4 | Tahun survei |
| 2 | `KBLI` | `KBLI` | C2 | Kode Baku Klasifikasi Indonesia 2 digit |
| 3 | `KLAS` | `KLAS` | C1 | Klasifikasi Usaha |
| 4 | `WEIGHT` | `WEIGHT` | N16.14 | Penimbang |
| 5 | `R703AK2` | `R703AK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan milik sendiri per 30 Juni 2024 |
| 6 | `R703BK2` | `R703BK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan pinjaman bank nonsubsidi per 30 Juni 2024 |
| 7 | `R703CK2` | `R703CK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan Pinjaman bank subsidi per 30 Juni 2024 |
| 8 | `R703DK2` | `R703DK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan pinjaman koperasi per 30 Juni 2024 |
| 9 | `R703EK2` | `R703EK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan Pinjaman lembaga keuangan bukan bank per 30 Juni 2024 |
| 10 | `R703FK2` | `R703FK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan Pinjaman dari perorangan per 30 Juni 2024 |
| 11 | `R703GK2` | `R703GK2` | N5.2 | Komposisi asal perolehan aset/harta usaha perusahaan Pinjaman dari lembaga nonkeuangan per 30 Juni 2024 |
| 12 | `R704` | `R704` | C1 | Jika rincian 703.b dan 703.c kolom (2) tidak terisi, alasan utama tidak meminjam dari bank: |
| 13 | `R7051` | `R7051` | N10 | Jika rincian 703.c kolom (2) terisi, berapa nilai pinjaman Kredit Usaha Rakyat |
| 14 | `R7052` | `R7052` | N10 | Jika rincian 703.c kolom (2) terisi, berapa nilai pinjaman Kredit subsidi lainnya |
| 15 | `R801` | `R801` | N10 | Ringkasan: Pendapatan |
| 16 | `R802` | `R802` | N10 | Ringkasan: Biaya/Pengeluaran |
| 17 | `R803` | `R803` | N10 | Ringkasan: Selisih |
| 18 | `R901A` | `R901A` | N3 | Bahan baku utama dibeli/diperoleh dari Dalam satu kabupaten/kota |
| 19 | `R901B` | `R901B` | N3 | Bahan baku utama dibeli/diperoleh dari Luar kabupaten/kota satu provins |
| 20 | `R901C` | `R901C` | N3 | Bahan baku utama dibeli/diperoleh dari Luar provinsi |
| 21 | `R901D` | `R901D` | N3 | Bahan baku utama dibeli/diperoleh dari Langsung luar negeri/importir |
| 22 | `R902A` | `R902A` | N5.2 | Persentase penjualan produk yang dihasilkan: Konsumen akhir (rumah tangga) |
| 23 | `R902B` | `R902B` | N5.2 | Persentase penjualan produk yang dihasilkan: Pedagang eceran |
| 24 | `R902C` | `R902C` | N5.2 | Persentase penjualan produk yang dihasilkan: Pedangan besar |
| 25 | `R902D` | `R902D` | N3.1 | Persentase penjualan produk yang dihasilkan: Industri dan pelaku komersial lainnya |
| 26 | `R902E` | `R902E` | N5.2 | Persentase penjualan produk yang dihasilkan: Pemerintah/institusi |
| 27 | `R903A` | `R903A` | N5.2 | Alokasi pemasaran dalam satu kabupaten/kota |
| 28 | `R903B` | `R903B` | N5.2 | Alokasi pemasaran luar kabupaten/kota satu provinsi |
| 29 | `R903C` | `R903C` | N5.2 | Alokasi pemasaran luar provinsi |
| 30 | `R903D` | `R903D` | N3.1 | Alokasi pemasaran luar negeri |
| 31 | `R904A` | `R904A` | N5.2 | Persentase penjualan dengan metode online |
| 32 | `R904B` | `R904B` | N4.2 | Persentase pembelian bahan baku dengan metode online |
| 33 | `R703MK2` | `R703MK2` | C1 | Yang memiliki komposisi aset terbesar dari list isian di 703 |
| 34 | `R902M` | `R902M` | C1 | Yang memiliki persentase nilai terbesar dari list isian di 902 |
| 35 | `R903M` | `R903M` | C1 | Yang memiliki persentase nilai terbesar dari list isian di 903 |
| 36 | `RENUM` | `RENUM` | N5 | Identitas Unik Hasil Renumbering |
