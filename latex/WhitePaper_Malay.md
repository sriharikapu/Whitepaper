PPIO: Rangkaian Penyimpanan dan Penghantaran P2P yang Boleh Diprogram

1. Abstrak
2. Pengenalan
3. Penyelesaian
3.1. Sorotan Teknologi
3.2. Rangkaian P2P
3.2.1. Penjadualan Data-Memacu
3.2.2. Pangkalan Data dan Routing yang diedarkan
3.2.3. Rangkaian Overlay Penganjur P2P
3.2.4. Mengoptimumkan Pengedaran Kandungan Populer
3.2.5. Penjadualan Mesra ISP
3.2.6. PCDN
3.3. Bukti
3.3.1. Bukti-Replikasi (PoRep)
3.3.2. Bukti-muat turun (PoD)
3.3.3. Proof-of-Spacetime (PoSt)
3.3.4. Cahaya-Bukti-Kapasiti (LPoC)
3.4. Konsensus
3.4.1. Kuasa Penambang
3.4.2. Fungsi Rawak Diverifikasi (VRF)
3.4.3. Byzantine Fault Tolerance (BFT)
3.4.4. Persetujuan PVFT
4. Senibina
4.1. Lapisan Fizikal
4.2. Lapisan Data
4.3. Lapisan Rangkaian
4.4. Lapisan Konsensus
4.5. Layer Insentif
4.6. Lapisan Antara Muka
4.7. Lapisan Aplikasi
5. Keselamatan
5.1. Serangan Sybil
5.2. Serangan Penyumberan Luar
5.3. Serangan Generasi
5.4. Penafian Penyerang Perkhidmatan yang Diedarkan
5.5. Serangan Gerhana
6. Ekosistem
6.1. Peranan
6.2. Perlombongan
6.3. Kontrak Pintar
6.4. Gas
6.5. Harga Gas
6.6. Coin-Pool
7. Masa Depan
8. RUJUKAN

1. Abstrak

PPIO adalah rangkaian penyimpanan dan penghantaran penghantaran yang dapat diprogramkan. Ia bukan sahaja menyediakan perkhidmatan yang lebih mantap dan cekap daripada platform simpanan berasaskan awan sedia ada seperti AWS S3 tetapi juga dengan ketara mengurangkan kos storan. Pada masa yang sama, PPIO menawarkan keselamatan data dan perlindungan privasi yang lebih baik. Rangkaian storan dan mekanisme insentif yang direka bentuk dengan baik PPIO membolehkan ia menggunakan sejumlah besar jalur lebar dan sumber penyimpanan yang tidak digunakan di Internet, dan menyediakan perkhidmatan storan yang boleh dipercayai dengan kos yang lebih rendah. Sistem fail decentralized PPIO menghalang akses yang tidak dibenarkan dan memastikan semua data boleh disimpan dengan selamat dan secara persendirian. PPIO direka bentuk dari bawah untuk melaksanakan secara cekap pada skala global, dengan memanfaatkan pengalaman pasukan pengasasnya daripada mereka bentuk dan menjalankan rangkaian yang terdesentralisasi dengan ratusan juta pengguna. PPIO memenuhi keperluan simpanan kedua-dua perniagaan dan perkhidmatan Internet hari ini, dan aplikasi terdesentralisasi yang muncul (DApps).

Dalam karya ini, matlamat reka bentuk PPIO dijelaskan, diikuti dengan butiran tentang bagaimana ia mencapai matlamat ini. Ia memberikan butiran mendalam mengenai sistem failnya yang diedarkan, seni bina rangkaian, dan aliran kerja penyimpanan. Ia menerangkan bagaimana PPIO boleh menghalang pelbagai serangan rangkaian, dan membincangkan bagaimana ia mewujudkan mekanisme insentif yang sihat dan mampan, model ekonomi dan ekosistem.

2. Pengenalan

Pasaran penyimpanan awan global telah berkembang pesat dalam beberapa tahun kebelakangan dan akan terus berkembang pada kadar yang lebih pantas. Walau bagaimanapun, penyelesaian berpusat sedia ada mempunyai banyak masalah. Pelanggaran data sering berlaku, dengan skala yang semakin berkembang dan kesan. Sebagai contoh, penggodam Dropbox pada 2016 sahaja membocorkan 68 juta akaun pengguna. Insiden ini menimbulkan ancaman serius bukan hanya privasi pengguna individu, tetapi juga keselamatan dan integriti seluruh Internet. Pada masa yang sama, kos jalur lebar dan penyimpanan yang tinggi adalah masalah lain yang wujud dalam sistem penyimpanan terpusat, menjadikannya amat sukar bagi banyak syarikat Internet untuk menguntungkan.

Terdapat banyak percubaan untuk membina sistem penyimpanan terdistribusi. Walau bagaimanapun, mereka tidak berjaya. Sebagai contoh, Siacoin dibina di atas kata sepakat seperti Bukti Kerja Kerja (PoW) Bitcoin. PoW memperkenalkan pengiraan yang sewajarnya dan penggunaan tenaga, dan ia tidak mengambil kira tahap penyimpanan dan sumbangan jalur lebar yang berbeza di kalangan pelombong, yang penting kepada sistem storan terdistribusi yang terdesentralisasi. Storj adalah satu lagi projek yang telah melalui tahun-tahun pembangunan, tetapi ia masih dalam tahap ujian. Beberapa isu Storj yang diketahui adalah kekurangan tindak balas yang cepat dari para penambang atas permintaan simpanan dan transaksinya diselesaikan sekali sebulan yang tidak ramah kepada penambang. BurstCoin menggunakan Bukti Kapasiti (PoC) yang mengambil kapasiti simpanan para penambang, tetapi malangnya, tidak cukup untuk berkhidmat dengan baik untuk keperluan penyimpanan.

Projek FileCoin yang sedang dibangunkan yang sedang dibangun oleh Protokol Labs menambah lapisan insentif di atas Sistem Fail Inter-planet (IPFS), dengan matlamat untuk membina infrastruktur penyimpanan dan protokol untuk menggantikan protokol HTTP. Untuk tujuan itu, indeks failnya dijadikan awam untuk memudahkan ciri seperti akses Web, tetapi ia menimbulkan cabaran untuk memelihara privasi pengguna dan keselamatan data dalam rangkaian storan. Selain itu, beberapa bukti storannya terlalu rumit dan kemungkinan untuk memegang sistem kembali dari berjalan dengan cekap pada skala yang besar. Ia meminjam reka bentuk sistem P2P yang matang dari aplikasi terbukti seperti BitTorrent, tetapi ia tidak menyediakan penyelesaian yang baik untuk menangani persekitaran rangkaian yang rumit dan tidak menawarkan pengoptimuman prestasi dalam rangkaian serantau. Kekurangan itu dalam reka bentuk boleh menyebabkan banyak masalah dunia nyata kepada penambang dan ISP. Oleh kerana Protokol Labs mendakwa bahawa fail yang disimpan di IPFS adalah kekal dan tidak boleh dipadamkan, ia berjalan ke
