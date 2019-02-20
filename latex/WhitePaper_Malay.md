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

Projek FileCoin yang sedang dibangunkan yang sedang dibangun oleh Protokol Labs menambah lapisan insentif di atas Sistem Fail Inter-planet (IPFS), dengan matlamat untuk membina infrastruktur penyimpanan dan protokol untuk menggantikan protokol HTTP. Untuk tujuan itu, indeks failnya dijadikan awam untuk memudahkan ciri seperti akses Web, tetapi ia menimbulkan cabaran untuk memelihara privasi pengguna dan keselamatan data dalam rangkaian storan. Selain itu, beberapa bukti storannya terlalu rumit dan kemungkinan untuk memegang sistem kembali dari berjalan dengan cekap pada skala yang besar. Ia meminjam reka bentuk sistem P2P yang matang dari aplikasi terbukti seperti BitTorrent, tetapi ia tidak menyediakan penyelesaian yang baik untuk menangani persekitaran rangkaian yang rumit dan tidak menawarkan pengoptimuman prestasi dalam rangkaian serantau. Kekurangan itu dalam reka bentuk boleh menyebabkan banyak masalah dunia nyata kepada penambang dan ISP. Oleh kerana Protokol Labs mendakwa bahawa fail yang disimpan di IPFS adalah kekal dan tidak boleh dipadamkan, ia berjalan kee risiko menghadapi pertikaian undang-undang terhadap dasar dan peraturan dan membuat penempatan di seluruh dunia lebih sukar.

Dari perbincangan di atas, adalah jelas bahawa penyelesaian storan yang tidak lengkap akan dibina untuk menyokong kes penggunaan storan berskala besar dan dunia sebenar, yang merupakan usaha PPIO untuk mencapai matlamat. Pasukan pengasas PPIO berjaya merangka, membangun dan mengekalkan PPLive, sistem pengintipan kepada rakan sebaya yang melayani ratusan juta pengguna setiap hari. Pengalaman sedemikian membolehkan pasukan untuk membangunkan penyelesaian yang cekap dan praktikal dan mencapai matlamat reka bentuk berikut.

Kos Penyimpanan Rendah. Kos simpanan tinggi adalah cabaran kritikal untuk perniagaan Internet. Insentif yang direka dengan baik PPIO memberikan ganjaran kewangan yang menarik kepada pelombong dan menggalakkan mereka untuk menyumbang kepada rangkaian. Pada masa yang sama, ia menghukum peserta yang tidak senonoh. Hasilnya, komuniti pelombong yang berkualiti tinggi boleh ditubuhkan. Ini membolehkan PPIO menggunakan sejumlah besar sumber jalur lebar dan simpanan yang tidak digunakan di Internet, dan menyediakan perkhidmatan storan yang teguh pada kos yang lebih rendah. Untuk menjadikan sistem storan mudah digunakan, PPIO memperkenalkan satu skim yang dipanggil "Coin-Pool", yang membantu para pengguna untuk menguruskan penyimpanan dan muat turun mikrofon dengan mudah. Pada masa yang sama, PPIO juga memperkenalkan mekanisme untuk melindungi pengguna daripada kesan turun naik harga storan, yang memberikan pengalaman pengguna yang lebih baik daripada platform penyimpanan terpusat yang sedia ada.

Skalabiliti dan Kecekapan Tinggi. Mengambil manfaat daripada pengalaman pasukan pengasas mewujudkan dan mengendalikan rangkaian diedarkan dengan beratus-ratus juta pengguna, PPIO dirancang dari bawah untuk melaksanakan dengan cekap pada skala global. Selain daripada satu set teknologi penghantar P2P terbukti industri, pasukan itu juga membangun penjadualan data yang dikendalikan oleh data, rangkaian overlay penganjur diri dan mengoptimumkan pengedaran kandungan. Reka bentuk PPIO juga meningkatkan kecekapan dalam rangkaian serantau dan menjadikannya lebih mesra kepada ISP. Digabungkan dengan inovasinya dalam NAT Traversal, Kaldemlia diedarkan hash table (DHT), bukti konsensus penyimpanan ringan dan pengoptimuman transmisi untuk streaming media, rangkaian storan yang diagihkan PPIO dapat dilakukan dengan kecekapan yang sangat tinggi dan dapat dengan mudah diperingkatkan menjadi ratusan juta node jaringan.

Privasi, Keselamatan dan Kestabilan. Perlindungan privasi dan privasi data adalah keperluan utama dalam reka bentuk sistem fail PPIO yang diedarkan. Dengan menggunakan algoritma sharding dan penyulitan data, data pengguna hanya boleh diambil oleh orang yang memiliki kunci persendirian unik pengguna. Pada masa yang sama, ia membolehkan pengguna untuk berkongsi data dengan mudah kepada orang awam atau dalam kumpulan swasta. PPIO dilengkapi dengan bukti penyimpanan praktikal untuk mengekalkan integriti dan kebolehpercayaan kandungan simpanannya. Bukti Kapasiti Cahaya (LPoC) dibangunkan untuk menyediakan pengesahan keupayaan penyimpanan yang disediakan oleh penambang. Bukti Masa Angkasa yang dioptimumkan (PoSt) memastikan bahawa data yang ditentukan sememangnya disimpan oleh pelombong sepanjang tempoh yang ditentukan. Bukti Replikasi (PoRep) digunakan untuk menjamin bahawa para penambang meniru data pengguna. Bukti Muat turun (PoD) memastikan pengguna boleh memuat turun data yang disimpan dengan betul.

Sokongan Permohonan Yang Kukuh dan Ekosistem. PPIO menyediakan satu set API penyimpanan serupa dengan perkhidmatan awan seperti AWS S3 dan menjadikan penghijrahan data dari perkhidmatan tersebut lebih mudah. PPIO juga mempunyai satu set teknologi yang dibina untuk menyokong aplikasi terdesentralisasi yang lebih baik, termasuk penyimpanan berasaskan objek, mekanisme dApp Sandbox, dan pengurusan akses fail, dan lain-lain. PPIO mempunyai pelan komprehensif untuk membangunkan ekosistem yang teguh, sihat dan lestari, untuk memudahkan pembangunan aplikasi dan perkhidmatan, dan membolehkan pemaju menikmati manfaat sebenar daripada pertumbuhan PPIO.

3. Penyelesaian
3.1. Sorotan Teknologi
Dalam bab ini, penyelesaian PPIO akan diterangkan dalam tiga bidang teknikal berikut.

Rangkaian P2P: PPIO membina rangkaian P2P sendiri yang mengawal, berdaya tahan dan berskala yang membolehkan nod yang terlibat dengan mudah berkongsi sumber bandwidth, penyimpanan, dan pengiraan yang terbiar atau tidak digunakan. Dalam model Pelanggan-Server (CS) tradisional, pelayan dapat menjadi hambatan jaringan dengan cepat apabila populasi klien tumbuh. Walau bagaimanapun, rangkaian peer-to-peer yang terdesentralisasi tidak bergantung kepada mana-mana pelayan pusat untuk berfungsi dengan betul, dan dengan mudah boleh bertolak ansur dengan kesalahan dan kegagalan sesetengah nod. Dalam rangkaian sedemikian, banyak salinan data diedarkan dan disimpan pada banyak nod yang berbeza. Ia dengan ketara meningkatkan keteguhan sistem storan teragih dan membolehkan pelanggan memuat turun data dari jiran terdekat di rangkaian. Disebabkan sifat unik rangkaian P2P, lebih banyak salinan data membawa kepada kelajuan muat turun yang lebih pantas. Dalam bab 2 bab ini, Reka bentuk rangkaian P2P PPIO akan diterangkan secara terperinci, termasuk algoritma penjadualan data berasaskan data pintar, pelaksanaan Jadual Hash yang Didistribusikan(DHT), pengurusan lalu lintas berdasarkan Penyedia Penyedia Rangkaian Proaktif (P4P), dan teknologi pengedaran kandungan P2Pnya (PCDN).

Bukti: Nod rangkaian dalam rangkaian P2P tradisional boleh menyertai atau meninggalkan rangkaian sesuka hati, yang menjadikannya sukar untuk mengekalkan kestabilan rangkaian. PPIO memberi insentif kepada nod berdasarkan sumbangan mereka dalam penyimpanan dan jalur lebar, supaya mereka lebih cenderung untuk kekal dalam rangkaian dan terus membuat sumbangan. [1] Walau bagaimanapun, nod jahat dan jahat boleh cuba menipu melalui pelbagai jenis serangan, yang melemahkan sistem. Bahagian 3 bab ini menerangkan Bukti Replikasi PPIO (PoRep), Bukti Muat Turun (PoD), Bukti Masa Ruang (PoSt) [2] [3], dan Bukti Kapasiti Cahaya (LPoC) yang direka untuk mempertahankan rangkaian terhadap semua serangan ini dan mengekalkan integriti sistem. Pelaksanaan bukti yang dioptimumkan dan selamat membolehkan mereka berfungsi dengan cekap secara besar-besaran, yang membolehkan sistem insentif beroperasi dengan cara yang selamat dan membantu mewujudkan pasaran simpanan dan ekonomi yang sihat.

Konsensus: Algoritma konsensus blockchain yang popular seperti Bukti Kerja (PoW), Bukti Stake (PoS) dan Bukti Pelepasan Stake (DPoS) semua membuat pertukaran dalam desentralisasi, keselamatan dan prestasi. Algoritma konsensus PPIO direka bentuk oleh senario penggunaannya. Ia mengira kuasa pelombong berdasarkan sumbangan storan dan jalur lebar mereka, memilih pengeluar blok secara rawak melalui Fungsi Rawak yang Diverifikasi (VRF) [24] [25], menggunakan konsensus konsensus berasaskan Byzantine Fault Tolerance (BFT) untuk pengesahan. Ia meningkatkan kecekapan rangkaian, melindungi keutuhannya dan membolehkannya beroperasi dengan cara yang aman dan terpencil. Ia juga merupakan asas pasaran simpanan besar-besaran, besar-besaran PPIO.

3.2. Rangkaian P2P
Pasukan pengasas PPIO telah membangunkan rangkaian teknologi P2P dan teknologi penghantaran data PPLive yang inovatif [4] [5] [6] [7].

Fakta mengenai PPLive:

Hanya rangkaian P2P penyimpanan dan penghantaran data dunia yang beroperasi pada lebih daripada 500 juta nod;

1/10 kos operasi rangkaian data tradisional;

Penyimpanan 40PB menggabungkan kapasiti storan P2P.

Dengan memanfaatkan pengalaman sedemikian, rangkaian P2P PPIO dibina ke dalam sistem storan dan penghantaran data yang mantap, berskala dan berprestasi tinggi.

3.2.1. Penjadualan Data-Memacu
Dalam sistem PPIO, "Objek" simpanan dibahagikan kepada "Segmen", setiap "Segmen" dibahagikan kepada beberapa "Pieces". Sebagai contoh, satu segmen boleh dibahagikan kepada kepingan M, dan kepingan ini boleh diduplikasi dan disimpan oleh penambang simpanan N yang berlainan. Setiap penambang N ini juga dikenali sebagai "Peer". Penjadual memutuskan bagaimana potongan M boleh dimuat turun dari rakan sebaya N supaya segmen itu dapat diambil dengan cepat, cekap, dan mengelakkan kepingan pendua untuk dimuat turun. Proses ini dipanggil Penjadualan Unduh Multi-point.

Dua algoritma penjadualan data yang dibangunkan untuk kedua-dua kes penggunaan:

Muat turun fail
Media streaming pada permintaan [4]
Muat turun Fail

Ringkasan algoritma penjadualan PPIO:

Sambungan maya pelbagai (Tunnels) ditubuhkan antara pengguna dan setiap rakan sebaya dengan sumber, untuk meningkatkan kecekapan penghantaran. Protokol berasaskan UDP seperti KCP atau UDT [13] cuba terlebih dahulu untuk membuat sambungan. Sekiranya gagal, protokol yang berasaskan TCP akan digunakan untuk menyesuaikan diri dengan pelbagai jenis rangkaian heterogen.
Bagi setiap rakan sebaya, kelajuan muat turun yang dijangkakan $ V_ {conn} $ dikira berdasarkan sejarah penghantarannya. Jika tiada sejarah ditemui, nilai empirikal lalai digunakan.
Bilangan sambungan maya pada setiap peer berbeza-beza rakan sebaya yang lebih tinggi $ V_ {conn} $ boleh mempunyai sejumlah besar sambungan maya awal.
Berdasarkan pemisahan segmen, pengguna pertama menghantar permintaan muat turun ke rakan sebaya yang diberikan untuk sekeping sewenang-wenangnya, dan rakan sebaya membalas dengan sewajarnya dengan menghantar pengguna potongan setelah menerima permintaan tersebut.
Apabila sekeping diterima dari sambungan maya, anggaran kelajuan muat turun $ V_ {conn} $ dikemas kini, dan satu lagi bahagian yang sewenang-wenang akan diminta dari sambungan segera sehingga semua data dimuat turun.
Apabila masa muat turun permintaan, permintaan dibatalkan, dan semua sambungan ke rakan sebaya yang tidak bertindak balas akan ditutup. Permintaan muat turun dari baki yang masih lagi akan dialihkan kembali kepada rakan-rakan lain. Dalam kes ini, rakan sebaya yang tidak bertindak balas juga akan dihukum, dan bilangan sambungan yang boleh ditubuhkan dari rakan sebaya dalam muat turun masa depan dikurangkan.
Berdasarkan pengalaman membina rangkaian P2P berprestasi tinggi, reka bentuk PPIO membolehkan pelbagai sambungan ditubuhkan dari setiap rakan sebaya. Ia secara signifikan meningkatkan kecekapan penghantaran keseluruhan rangkaian, terutamanya untuk sambungan TCP, kerana ia berfungsi di sekitar masalah kecekapan rendah yang disebabkan oleh kawalan aliran TCP yang konservatif.

Penyiaran Data masa nyata

Selain menyokong muat turun fail yang cekap, PPIO juga menyokong streaming data P2P yang dioptimumkan. Data PPIO-driven scheduler direka untuk menyediakan prestasi aliran masa nyata yang stabil dalam rangkaian P2P ad hoc [12]. Teknologi ini telah melalui banyak pengoptimuman pengoptimuman percubaan dan kesilapan dan terbukti memberikan pengalaman pengguna berkualiti tinggi kepada aplikasi streaming seperti perkhidmatan video-on-demand (VOD).

Sistem penstriman P2P mempunyai ciri reka bentuk unik berikut:

Muat turun urutan. Segmen dan potongan berikutnya dari titik main semula semasa perlu diprioritaskan dalam penjadualan muat turun, untuk mengekalkan main balik aliran lancar.

Kepingan yang tidak popular. Kepingan yang tidak popular adalah yang mempunyai bilangan pendua yang terkecil dalam rangkaian. Dalam kes penggunaan streaming media, mereka perlu diprioritaskan semasa muat turun. Ini mungkin kelihatan sangat kontra, tetapi keutamaan kepingan ini akan membantu membuat muat turun keseluruhan segmen dengan lebih cepat dan mencapai pengalaman yang lebih baik.

Mata utama. Banyak aplikasi streaming media membolehkan main balik akses rawak seperti penghantaran pantas atau carian. Mata anchor diletakkan di dalam aliran video untuk membolehkan akses rawak. Potongan di titik anchor diprioritaskan semasa muat turun, untuk membolehkan main balik dimulakan dengan segera selepas akses rawak.

Untuk mencapai keperluan reka bentuk di atas, algoritma penjadualan diperlukan untuk membuat keputusan pintar yang mana sekeping rakan sebaya perlu dimuat turun dari, berapa banyak rakan sebaya harus digunakan untuk muat turun secara serentak, bagaimana menetapkan pemasa untuk setiap rakan sebaya, bagaimana menjadualkan semula baki kepingan dan menyesuaikan diri dengan perubahan rangkaian, dan lain-lain Penjadual juga direka untuk memaksimumkan kelajuan muat turun dan meminimumkan overhed permintaan dan penghantaran data yang diduplikasi. Ringkasan algoritma penjadualan adalah seperti berikut:

Sama seperti muat turun fail, banyak sambungan maya (terowong) ditubuhkan dengan setiap rakan sebaya, dan anggaran kelajuan penghantaran $ V_ {conn} $ dikira setiap sambungan maya.
Pieces yang akan dimuat turun disusun mengikut keutamaan mereka dan diperuntukkan terlebih dahulu kepada sambungan maya yang tersedia dengan meletakkan mereka dalam beratur muat turun yang sepadan. Anggaran masa ketibaan untuk setiap helaian boleh dikira berdasarkan kelajuan setiap sambungan maya dan kepingan yang tinggal untuk dimuat turun dalam setiap giliran. Secara umum, kepingan dengan keutamaan yang lebih tinggi harus berakhir dengan masa ketibaan yang lebih awal. Satu ilustrasi algoritma pra-peruntukan ditunjukkan dalam Rajah 3.1.
Langkah 2 diulang secara berkala, dan semua bahagian yang tinggal akan diperuntukkan semula untuk menampung perubahan dalam kelajuan penghantaran dan ketersediaan sambungan maya.
Selepas sekeping berjaya dimuat turun, kelajuan penghantaran sambungan maya dikemas kini, dan permintaan dihantar segera untuk memuat turun sekeping seterusnya dalam barisan.
Potongan segera boleh diminta dari pelbagai sambungan untuk memastikan main balik yang lancar.
Bahagian lain dari algoritma ini berfungsi dengan cara yang sama seperti muat turun fail biasa.
Pembolehubah persekitaran algoritma pra-peruntukan
// Pengertian setiap sambungan maya
struct PeerConn {
    kelajuan: = anggaran kelajuan sambungan maya ini, dalam KB / s
    barisan: = maya muat turun maya sambungan ini
    isReq: = ada menunggu permintaan
    lastReqTime: = perkiraan waktu ketibaan potongan terakhir di baris gilir, di kutu
}

pieceSize: = saiz sekeping, dalam KB
sekarangTick: = masa semasa, dalam kutu
Peer [] conns: = sambungan yang tersedia
keping: = keping disusun mengikut keutamaan
Pseudocode
pra-jadual

Rajah 3.1 Ilustrasi pra-peruntukan

Rangkaian penghantaran P2P PPIO dinamik sepenuhnya. Setiap rekan merespon beberapa permintaan muat turun, dan berpotensi untuk beberapa nod muat turun. Setiap nada memuat turun menghantar permintaan muat turun ke rakan sebaya yang banyak, menguruskan potongan yang dimuat turun dan berurusan dengan masa yang berpotensi dan kegagalan dari rakan-rakan. Pada masa yang sama, nada memuat turun itu sendiri boleh menyampaikan permintaan muat turun, berfungsi sebagai peer ke nod lain. Dengan menggunakan dua algoritma penjadualan data berasaskan data, rangkaian P2P dinamik PPIO boleh mengendalikan jumlah penghantaran data serentak yang sangat tinggi dengan cekap.

3.2.2. Pangkalan Data dan Routing yang diedarkan
PPIO adalah sistem storan dan pengedaran yang sepenuhnya yang memerlukan pangkalan datanya juga dikendalikan dengan cara yang terdesentralisasi. PPIO menggunakan Jadual Hash yang Diagihkan (DHT) untuk menyimpan data dan menyediakan perkhidmatan penghalaan dan pencarian.

Dalam DHT, setiap bahagian data dibundarkan dengan kunci yang unik ke dalam pasangan kunci-nilai. Pasangan nilai utama ini diedarkan dan disimpan di antara nod yang terlibat. Ia mengelakkan masalah dengan sistem pangkalan data berpusat, di mana kegagalan pelayan pusat menyebabkan pecahan keseluruhan rangkaian. Tiada satu nod peserta dalam DHT ditugaskan untuk mengekalkan keseluruhan rangkaian. Setiap nod hanya menyimpan sebahagian kecil daripada pangkalan data dan hanya perlu mengekalkan maklumat nod bersebelahannya, reka bentuk tersebut dengan ketara mengurangkan setiap jalur lebar nod dan penggunaan sumber. Redundancy juga ditambah kepada data dan disimpan pada beberapa nod untuk mengekalkan kebolehpercayaan system supaya satu kegagalan nod tunggal tidak menyebabkan kehilangan data.

Terdapat banyak pelaksanaan DHT, beberapa yang biasa digunakan adalah Chord [14], Pastry [15], Tapestry [18], Dynamo [19], dan Kademlia [16]. PPIO menggunakan kademlia, begitu juga banyak projek P2P yang terkenal seperti PPLive, BitTorrent, eMule, dll.

Algoritma Kademlia memberikan ID unik kepada setiap nod yang mengambil bahagian. ID nod juga digunakan untuk mengira jarak antara nod dan mencari pasangan nilai utama. Langkah-langkah algoritma melalui laluan rangkaian dan mencari nod lebih hampir dengan kunci pada setiap langkah untuk mencari pasangan kunci nilai khusus dalam rangkaian sehingga ia mencapai nod yang menyimpan pasangan kunci. Setiap nod perlu menyimpan maklumat dari kumpulan nod lain berdasarkan jarak mereka untuk menyokong pencarian. Jarak tersebut dikira dengan mengambil operasi XOR pada dua ID Nod. ID nod mempunyai panjang yang sama seperti kekunci yang digunakan dalam pasangan nilai utama. Oleh itu, jarak antara ID dan kekunci nod boleh dikira dengan cara yang sama. Memandangkan jarak XOR tidak mengambil kira jarak geografi yang sebenar, adalah mungkin bagi dua nod untuk tinggal bersebelahan di antara satu sama lain dalam rangkaian walaupun salah satu daripada mereka mungkin berada di United Kingdom, sementara yang lain berada di Amerika Syarikat.

kad_find_example

Rajah 3.2 Mencari Kademlia DHT

PPIO juga menggunakan pelanjutan Kademlia - S / Kademlia [23] untuk meningkatkan keselamatan rangkaian. Perubahan ini disebabkan terutamanya oleh nod melalui selari melihat ke arah jalan yang tidak disertasi. Rangkaian ini boleh mengekalkan serangan walaupun sejumlah besar nod dikompromi.

Dengan pelaksanaan DHT di atas, data berstruktur seperti indeks fail, statistik pada nod rangkaian, dan metadata lain boleh diselamatkan dengan selamat dan cepat didapatkan dalam rangkaian yang diedarkan PPIO. Walau bagaimanapun, pemindahan data dalam rangkaian simpanannya ditangani secara berbeza, yang akan dibincangkan dalam bahagian seterusnya.

3.2.3. Rangkaian Overlay Penganjur P2P
Perkhidmatan storan yang mantap hari ini, seperti Amazon S3, Dropbox, Google Drive, iCloud, dan lain-lain, menyimpan data pelanggan di pusat data berskala besar. Di bawah kekangan kos, setiap perkhidmatan hanya boleh menggunakan beberapa pusat data terhad di seluruh dunia. Penyebaran pusat data Amazon AWS ditunjukkan dalam Rajah 3.3. Disebabkan sifat ad hoc Internet, ia mencabar untuk menjamin pemindahan data pantas di mana-mana di dunia dengan bergantung pada beberapa pusat data. Pengguna di rantau yang sama perlu bersaing untuk jalur lebar yang tersedia dari pusat data. Apabila bilangan pengguna bertambah, kelajuan pemindahan dan pengalaman pengguna mungkin akan merosot.

AWS

Rajah 3.3 AWS infrastruktur global

Storan yang diedarkan PPIO adalah rangkaian overlay penganjur, yang tidak terstruktur, yang menggalakkan sambungan antara rakan-rakan tempatan. Penambang simpanan berdekatan lebih cenderung untuk dipilih untuk menyimpan data. Begitu juga, pengedaran dan pengambilan data kebanyakannya dikendalikan oleh rakan-rakan berdekatan. Akibatnya, pemindahan data boleh dikekalkan pada kelajuan yang lebih tinggi dengan sepenuhnya menggunakan jalur lebar rangkaian tempatan.

Dengan lebih banyak nod yang menyertai rangkaian storan PPIO, menjadi lebih mudah bagi setiap nod untuk mencari rakan-rakan berdekatan dengan sambungan yang lebih cepat, untuk penyimpanan dan pengambilan semula. Jalur lebar pelayan tidak lagi hambatan, dan pertumbuhan pengguna membawa kepada kelajuan dan pengalaman yang lebih baik.

Mewujudkan Rangkaian P2P Menyusun Sendiri

Setiap nod dalam rangkaian PPIO mengekalkan senarai rakan jiran untuk terus berhubung. Senarai itu terus dikemas kini dengan menjatuhkan nod yang hilang dan menambah jiran yang baru bergabung. Akibatnya, senarai itu kebanyakannya mengandungi jiran yang aktif dan cepat. Dengan semua nod yang mengikuti proses yang sama seperti yang dihuraikan di bawah, rangkaian overlay penganjuran P2P sendiri boleh ditubuhkan dan dikekalkan.

Mulakan dengan memilih set permulaan jiran calon di kalangan rakan sebaya yang mempunyai sambungan di masa lalu. Nod baru yang baru bermula dengan senarai kosong.
Dapatkan jiran calon baru dari Kademlia DHT. Seperti yang dibincangkan di bahagian sebelumnya, tidak ada jaminan bahawa rakan sebaya ini adalah jiran geografi atau mempunyai sambungan cepat ke nod.
Cuba untuk membuat sambungan ke dua set nod kandidat di atas, bilangan sambungan tidak boleh melebihi batas yang diberikan. Setiap nod yang disambung kini dianggap sebagai jiran.
Dapatkan calon baru berulang kali, dengan mencari jiran tetangga.
Siasat dan menilai kelajuan penghantaran setiap calon baru berulang kali, dalam fesyen robin bulat, pangkat calon berdasarkan penilaian.
Hilangkan jiran yang mempunyai sambungan berkelajuan rendah ke nod atau tidak lagi dapat dicapai.
Pilih calon yang disenaraikan di bahagian atas untuk menggantikan jiran yang dihapuskan.
Ulangi keseluruhan proses.
Setiap nod perlu mengekalkan dua senarai masa sebenar untuk menyokong proses di atas, senarai jiran semasa, dan senarai calon jiran. Selain itu, setiap nod juga mengekalkan senarai jiran terdahulu. Ini adalah penting untuk pemilihan nod dalam rangkaian tindanan.

Penambang simpanan pilihan dengan rangkaian yang lebih dekatjarak

Apabila pengguna memuat naik data ke rangkaian storan PPIO, jirannya dengan jarak rangkaian yang lebih dekat diprioritaskan apabila memilih penambang simpanan menyimpan data. Peratusan besar salinan data disimpan di pelombong jiran dengan sambungan yang lebih cepat kepada pengguna, untuk mencapai kelajuan pemindahan yang lebih tinggi semasa penyimpanan dan pengambilan semula. Apabila nodus penambang yang cukup menyertai jaringan di pelbagai kawasan di dunia, kelajuan pemindahan data yang tinggi dapat dikekalkan di seluruh dunia.

Mengenai pengguna yang sering menukar wilayah

Apabila nod pengguna berulang kali bergerak di antara dua kawasan yang berbeza, reka bentuk PPIO dapat memberikan pengalaman pengguna yang hebat di kedua-dua tempat. Apabila nod pengguna berada di lokasi $ A $, ia mendapati jiran di lokasi $ A $. Apabila nod pengguna berada di lokasi kedua $ B $, ia mendapati jiran di lokasi $ B $. Hasilnya, senarai jiran atau sejarahnya mengandungi rakan dari kedua-dua lokasi. Jika nod pengguna kekal di lokasi $ A $ untuk tempoh lanjutan, senarai jirannya akan mengandungi lebih banyak rakan dari lokasi $ A $, dan sebaliknya. Jika nod pengguna berulang kali bergerak ke belakang dan sebagainya, senarai itu akan mengandungi bilangan rakan sebaya yang sama dari lokasi $ A $ dan $ B $. Dengan cara ini, apabila pengguna nod memuat data, pelombongan jiran dari kedua-dua nod akan menyimpan salinan data, supaya pengambilan data pantas dapat dicapai di kedua-dua tempat.

Jika pengguna secara kekal berpindah ke rantau yang berbeza

Apabila nod pengguna kekal berpindah ke rantau yang berbeza, PPIO menyediakan ciri set semula untuk membantu penjadualan semula. Apabila tetapan semula dimulakan, senarai jirannya dibina semula dari awal. Salinan baru dicipta untuk data pengguna sedia ada dalam rangkaian, dan salinan-salinan ini disimpan dengan mengutamakan jiran-jiran baru. Dengan cara ini, pengambilan data pantas dapat dicapai untuk data yang disimpan sebelum ini, serta data baru yang akan disimpan ke rangkaian.

3.2.4. Mengoptimumkan Pengedaran Kandungan Populer
Dalam rangkaian pengedaran data, sebilangan kecil kandungan popular boleh menggunakan sebahagian besar sumber jalur lebar dan penyimpanan. Pada masa yang sama, kelajuan muat turun kandungan popular boleh memberi impak besar kepada pengalaman pengguna keseluruhan. Oleh itu, pengoptimuman pengedaran kandungan popular adalah penting untuk rangkaian. PPIO menyediakan dua kaedah penjadualan yang optimum untuk kandungan yang popular, satu adalah penambang simpanan pemilihan aktif, dan yang lain dikuatkuasakan oleh penjadual (nod pengindeks). Kedua-dua kaedah ini direka bentuk untuk bekerjasama dan memastikan pengagihan kandungan yang popular dan mengekalkan ekosistem yang sihat bagi rangkaian storan.

Peniaga simpanan pemilihan aktif

Seperti yang dijelaskan dalam bahagian 3.2.3, rangkaian overlay penganjur diri ditubuhkan oleh nod yang mengambil bahagian. Apabila nod pengguna meminta sekeping data, ia melihat sumber dari nod indeks, dan nod indeks mengembalikan maklumat mengenai nod miner yang menyimpan kandungan. Pada masa yang sama, nod pengguna juga menyiarkan permintaan kepada jirannya untuk mencari sumber. Rakan-rakannya akan mengemukakan permintaan kepada jiran-jiran mereka setelah menerima. Untuk mengelakkan beban yang tidak perlu di rangkaian, panjang laluan penghantaran terhad. Tetapi ia juga menyesuaikan diri berdasarkan jumlah nod yang telah dicapai oleh permintaan. Apabila nod tidak mencukupi, laluan yang lebih panjang dibenarkan.

Apabila nod penambang menerima permintaan yang dikemukakan, dan jika ia berlaku untuk memiliki sumber yang diminta, ia memberitahu pengguna dan ada keutamaan yang lebih baik bahawa pengguna akan, sebenarnya, muat turun data daripadanya, kerana nod penambang berada di jalur pemajuan daripada jiran pengguna, dan dengan itu dekat dengan pengguna. Di PPIO, pelombong itu diberi insentif untuk menyediakan perkhidmatan muat turun kerana mendapat ganjaran untuk melakukannya.

Dari proses di atas, pelombong dapat menjejaki permintaan pengguna berdekatan dan mengenal pasti kandungan yang popular. Sebagai menyimpan kandungan popular meningkatkan peluang untuk menyediakan perkhidmatan muat turun dan mendapat ganjaran, pelombong secara proaktif akan menghantar permintaan kepada penjadual untuk menyimpan sumber kandungan yang popular. Seperti banyak pelombong mengikuti strategi yang sama, data popular mendapat penduduk yang cepat, dan ia meningkatkan kelajuan muat turun dengan ketara bagi pengguna. Apabila penambang mendapati bahawa kandungannya yang tersimpan tidak lagi bergaya, ia boleh meminta untuk mengeluarkan kandungan dari storannya. Sebaik sahaja diluluskan, storan boleh dikeluarkan dan disediakan untuk menyimpan sumber-sumber lain.

Kaedah ini didorong oleh permintaan, dan ia memberi insentif kepada pelombong untuk menyimpan kandungan popular secara proaktif. Ia juga menyesuaikan diri dengan populariti data di rantau yang berbeza. Sebagai rangkaian overlay PPIO dibina dengan mengelompokkan rakan-rakan berdekatan, jika sekeping kandungan hanya popular di rantau tertentu, hanya pelombong di kawasan yang sama memilikinya secara meluas. Penambang di bahagian lain rangkaian tidak terjejas. Oleh itu, kecekapan keseluruhan rangkaian storan dikekalkan.

Algoritma untuk mengenal pasti kandungan popular boleh disesuaikan oleh setiap penambang. Pelombong yang berlainan di kawasan yang berlainan boleh menyesuaikan algoritma secara berbeza, untuk mengoptimumkan untuk r yang lebih tinggipemberi pinjaman.

Dipaksa oleh pengindeks

Node penambang yang menyimpan sejumlah besar kandungan popular mungkin menerima lebih banyak permintaan muat turun, dan memenuhi permintaan tersebut menjadikannya lebih tinggi. Walau bagaimanapun, terlalu banyak muat turun serentak akan membuang sumber jalur lebar penambang ini dan mengurangkan kelajuan muat turun setiap pengguna. Pada masa yang sama, tidak adil kepada pelombong yang menyimpan kandungan yang kurang popular, yang mendapat pahala yang lebih rendah daripada yang lain.

Untuk mengelakkan masalah ini, penjadual (pengindeks) dalam rangkaian menggunakan perkhidmatan penjadualan yang disesuaikan berdasarkan populariti kandungan. Pelombong yang meminta untuk menyimpan kandungan yang paling popular perlu membayar penjadual (pengindeks) sebelum menerima sumber. Nod miner dengan lebar jalur yang lebih tinggi dan penyimpanan yang lebih besar masih mempunyai insentif yang mencukupi untuk melakukannya, tetapi mereka tidak akan memuat terlalu banyak kandungan sedemikian. Jika tidak, mereka tidak lagi boleh mencapai lebihan dengan menyediakan perkhidmatan muat turun yang membolehkan jalur lebar mereka.

hot_download

Rajah 3.3 Pengiriman Kandungan Popular

Seperti yang ditunjukkan dalam Rajah 3.3, beberapa pelombong menyimpan salinan data yang sama, mereka perlu bersaing untuk menyediakan perkhidmatan muat turun kepada pengguna. Pengguna sentiasa lebih suka yang memberikan kelajuan muat turun yang lebih tinggi. Jika penambang tidak mempunyai lebar jalur yang cukup, pengguna akan bertukar kepada orang lain. Jumlah data yang dimuat naik ke pengguna akan berkurangan, yang seterusnya mengurangkan ganjaran yang diterima. Oleh itu, pelombong dengan lebar jalur yang lebih rendah tidak akan diberi insentif untuk menyimpan kandungan yang popular. Akibatnya, kandungan popular kebanyakannya disimpan pada pelombong dengan lebar jalur yang lebih tinggi, yang seterusnya meningkatkan kelajuan dan pengalaman apabila pengguna memuat turun kandungan tersebut.

3.2.5. Penjadualan Mesra ISP
Dalam kebanyakan rangkaian P2P, nod boleh memindahkan data dengan rakan sebaya lain, tanpa mengira lokasi mereka. Akibatnya, pemindahan data tunggal berpotensi untuk mewujudkan lalu lintas di mana sahaja di dunia dan menggunakan jalur lebar antara Pembekal Perkhidmatan Internet (ISP) yang berlainan, atau bahkan di antara negara yang berbeza. Pada tahun 2007, sebuah institut penyelidikan iPoque menjalankan analisis mengenai hampir 3TB data tanpa nama yang dicontohkan daripada lebih daripada satu juta pengguna internet di Eropah Timur, Eropah Selatan, Australia, dan Timur Tengah. [26] Kajian mereka menunjukkan bahawa perkongsian fail P2P mengambil sebahagian besar daripada penggunaan jalur lebar rangkaian, yang menyumbang kira-kira 49% di Timur Tengah, dan 84% di Eropah Timur. Dari perspektif global, 95% jalur lebar pada masa utama terlibat dalam beberapa bentuk penghantaran data P2P. Dalam tahun-tahun kebelakangan ini, peratusan trafik P2P telah menurun disebabkan oleh perubahan dalam corak penggunaan aplikasi Internet. Bagaimanapun, dengan perkembangan terbaru teknologi blockchain dan aplikasi yang terdesentralisasi, lalu lintas rangkaian P2P dijangka mula meningkat lagi. Lalu lintas P2P menggunakan jumlah bandwidth yang luar biasa, termasuk jalur lebar antarabangsa. Ia meletakkan banyak beban pada infrastruktur internet kami, dan dengan ketara meningkatkan kos bagi ISP untuk beroperasi.

Seperti yang diterangkan dalam seksyen 3.2.3, rangkaian overlay penganjur sendiri PPIO menggalakkan pemindahan data di antara nod jiran, peratusan besar lalu lintasnya terkandung dalam rangkaian tempatan, dan kos operasi yang dilakukan ke atas ISP berkurangan dengan ketara. Walau bagaimanapun, topologi rangkaian overlay PPIO mungkin tidak sepadan dengan topologi ISP dengan tepat. Pengoptimuman lebih lanjut untuk mengurangkan lalu lintas yang tidak perlu antara ISP diperlukan untuk meningkatkan keupayaan PPIO yang semakin meningkat secara global.

Sekiranya nodus yang berpartisipasi dalam penghantaran data berlaku di sekitar satu sama lain, kemungkinan lalu lintas akan terkandung dalam rangkaian kawasan mereka. Akibatnya, kos bandwidth akan dikurangkan dengan ketara. Inilah prinsip di sebalik P4P, untuk menggunakan jalur lebar rangkaian tempatan sepenuhnya dalam rangkaian P2P.

P4P, atau Penyedia Penyedia rangkaian Proaktif untuk P2P [17], merupakan kaedah untuk perisian ISP dan P2P untuk mengoptimumkan sambungan []. Ia membolehkan pemilihan rakan sebaya berdasarkan topologi rangkaian fizikal, untuk mengurangkan trafik ke rangkaian tulang belakang, mengurangkan kos operasi pembekal rangkaian, dan meningkatkan kecekapan pemindahan data.

Pelaksanaan P4P dalam rangkaian P2P tradisional bergantung pada pelayan pusat. Oleh kerana PPIO adalah rangkaian yang sepenuhnya terdesentralisasi, penyelesaian P4P yang terdesentralisasi diperlukan.

PPIO menyediakan antara muka iP4P yang membolehkan ISP menyediakan dan mengkonfigurasi P4P dalam rangkaian mereka dan membenarkan aplikasi menanyakan maklumat tersebut. iP4P direka untuk menjadi sama dengan antara muka iTracker [17] dalam rangkaian P2P berpusat, untuk menjadikannya lebih mudah untuk menyesuaikan diri.

ip-list: membolehkan ISP untuk menyediakan senarai IP dalam rangkaian mereka, membolehkan nod dalam rangkaian PPIO dikaitkan dengan ISP mereka.
dasar membolehkan ISP untuk mengkonfigurasi dasar bagi aplikasi untuk mengakses maklumat P4P.
jarak p4p membolehkan aplikasi menanyakan kos dan jarak P4P antara nod rangkaian.
keupayaan membolehkan aplikasi menanyakan sumber rangkaian dan kapasiti rangkaian ISP.
friendly-isp-list
membolehkan aplikasi menanyakan maklumat ISP yang mesra, termasuk jarak p4p merentasi ISP yang berbeza.
Pada masa yang sama, PPIO memperkenalkan pangkalan data IP global yang dikekalkan oleh masyarakat. Maklumat dalam pangkalan data boleh digunakan untuk mengira jarak p4p antara dua nod dalam rangkaian apabila sekurang-kurangnya satu daripada mereka tidak berada dalam rangkaian ISP yang diketahui dari Antara Muka iP4P. Pangkalan data diselaraskan untuk nod penjadual (Indexer) dan nod Verifier dalam rangkaian P2P. Setiap nod dalam rangkaian boleh menanyakan maklumatnya dari pangkalan data. Berikut ini menunjukkan sebahagian daripada maklumat yang disimpan untuk setiap nod.

mesej P4PPeerInfo {
    uint32 countryId = 1; // Negara ID
    uint32 ispId = 2; // ID ISP
    uint32 stateId = 3; // Negeri atau ID Negeri
    uint32 cityId = 4; // Bandar ID
}
Apabila memilih sambungan data dari nod yang diberikan, nod pengindeksan dan penjadualan (Indexer) dalam rangkaian PPIO memeriksa sama ada nod boleh ditanyakan dari antara muka iP4P:

Sekiranya demikian, carian rakan sebaya dalam rangkaian ISP nod akan dijalankan terlebih dahulu, diikuti oleh carian di ISP yang mesra, dan akhirnya di kalangan semua rakan sebaya lain. Keputusan rakan sebaya akhir masih akan diputuskan berdasarkan kelajuan sambungan seperti yang dijelaskan dalam 3.2.3. Dengan cara ini, rakan dengan jarak p4p yang lebih pendek ke nod lebih cenderung untuk dipilih untuk memuat naik atau memuat turun datanya. Pada masa yang sama, nod dalam ISP yang lebih perlahan masih boleh menyambung kepada rakan sebaya yang lebih cepat. Akibatnya, lalu lintas yang tidak diperlukan antara pembekal rangkaian yang berbeza berkurang dengan ketara, dan pengalaman pengguna di seluruh rangkaian dikekalkan pada peringkat tinggi.

Jika tidak, jarak p4p yang dikira dari pangkalan data IP global digunakan dalam pra-pemilihan rakan sebaya. Begitu juga, pemilihan akhir masih akan menjadi kelajuan sambungan berasaskan.

3.2.6. PCDN
PCDN bermaksud percepatan CDN dengan P2P, dan ia menggunakan sumber jalur lebar dan penyimpanan yang banyak pelombong dalam rangkaian P2P untuk mencapai pengedaran data yang lebih cepat. PPIO direka untuk menyokong PCDN dan menyediakan antara muka yang mudah digunakan untuk DApps untuk mempercepatkan penghantaran kandungan mereka.

Ia diterbitkan pada node sumber pertama untuk mula mengedarkan sekeping kandungan. Selagi nod sumber online, pengguna boleh memuat turunnya. Bagaimanapun, memandangkan bilangan pengguna yang memuat turun dari nod sumber yang sama meningkat, jalur lebar yang tersedia akan menjadi sangat lelah, dan muat turun akan melambatkan. Dengan PCDN, apabila nod miner lain mula menyimpan dan menyediakan perkhidmatan muat turun untuk sekeping kandungan yang sama, pengguna akan dapat memuat turun daripada rakan sebaya dalam rangkaian dan menikmati pengalaman pengguna yang lebih baik.

pcdn

Rajah 3.5 Aliran Data PCDN

Terdapat dua cara untuk melaksanakan aplikasi PCDN di PPIO.

Manfaatkan penjadualan kandungan yang diterangkan dalam 3.2.4. Memandangkan PPIO membenamkan penjadualan kandungan popular dalam rangkaian overlaynya, pelombong akan memuat turun dan menyimpan data-data ini secara proaktif dan menyediakan perkhidmatan muat turun. Akibatnya, data akan disalin dan diedarkan di seluruh rangkaian di mana data tersebut dianggap popular. Ia meningkatkan pengalaman muat turun kerana bilangan salinan meningkat.

Membolehkan dan mengkonfigurasi PCDN secara langsung. PPIO menyediakan satu set API untuk membolehkan DApps menyediakan PCDN untuk kandungan mereka. Permohonan boleh menentukan jumlah salinan yang dikekalkan di bahagian tertentu rangkaian, atau lokasi geografi tertentu mengenai negara, ISP, negeri dan bandar, seperti yang ditakrifkan dalam pangkalan data P4P. PPIO akan menemui nod miner di kawasan yang ditentukan untuk menyimpan salinan dan menyediakan perkhidmatan muat turun. Oleh kerana penjadualan ditentukan oleh aplikasi, ia perlu mengimbangi kos pelombong dalam ruang penyimpanan, menjadualkan dan menjalankan bukti storan. Rajah 3.5 menunjukkan aliran data yang didorong oleh PCDN dalam rangkaian dalam kes ini.

3.3. Bukti
PPIO mempekerjakan 4 bukti penyimpanan yang berbeza, iaitu Bukti Replikasi (PoRep), Bukti Muat Turun (PoD), Bukti Ruang Masa (PoSt) dan Bukti Kapasiti Cahaya (LPoC). Bukti-bukti ini menjamin bahawa penyedia storan (penambang) betul mereplikasi data dan secara konsisten menyimpan data dalam tempoh yang disepakati. Mereka juga memastikan bahawa pengguna boleh berjaya memuat turun data pada bila-bila masa semasa tempoh yang dipersetujui. Bukti-bukti ini mengekalkan integriti dan kebolehpercayaan sistem storan PPIO. Mereka akan dibincangkan secara terperinci di bahagian ini.

Takrif istilah dalam bahagian:

CRH: Hashing-Tenggelisan Tenggelam, fungsi hash h yang sangat sukar untuk mencari dua input yang berbeza x, x ', dan menghasilkan output yang sama h (x) == h (x').

MerkleCRH: Hash akar pokok Merkle yang terbina dari hashing tahan perlanggaran. Pokok Merkle boleh digunakan sebagai cara yang berkesan untuk mengesahkan jika kandungan blok data sepadan dengan data asal.

Meterai: Kaedah penyulitan untuk memastikan setiap salinan data mempunyai perwakilan yang unik dan bebas. Proses penyulitan perlu mengambil masa yang lebih lama daripada dekripsi, untuk mengelakkan Serangan Generasi. AES-256 adalah pilihan untuk pelaksanaannya.

Cipher: Cahaya ringankaedah yption dengan kekunci simetri, yang digunakan dalam Proof-of-Download. XOR Cipher adalah pilihan untuk pelaksanaannya.

3.3.1. Bukti-Replikasi (PoRep)
Bukti Replikasi (PoRep) menyediakan cara untuk mengesahkan bahawa Miner $ L $ betul mereplikasi Data $ D $ dari Pengguna $ U $ dan menyimpannya dalam storannya. Proses ini juga memberikan bukti tidak langsung jalur lebar yang tersedia kepada $ L $. Prosedur PoRep diterangkan di bawah.

PoRep

Rajah 3.6 Proof-of-Replication

Pengguna $ U $ menghasilkan kunci Seal $ PK_ {Seal} $, menggunakannya untuk menyulitkan Data $ D $, dan menghasilkan salinan unik $ R = Seal (D, PK_ {Seal}) $. Ia juga membina sebuah pokok Merkle di atas $ R $, mengira hash akar pokok $ RT = MerkleCRH (R) $, dan menghantar $ RT $ kepada Verifier $ V $.
$ U $ memindahkan $ R $ dan $ PK_ {Seal} $ kepada penambang $ L $.
Permintaan $ L $ PoRep dari $ V $, $ V $ menerima permintaan dan menghantar cabaran rawak $ c $ ke $ L $, iaitu ia mencabar penyimpanan blok data $ c $ ke $ R $.
$ L $ mengambil $ R_ {c} $ yang merupakan blok $ c $ th $ R $, dan mengira $ Path_ {RC-RT} $ yang mengandungi nilai hash dari semua jalan nodus pohon Merkle dari $ R_ { c} $ ke nod akar. $ L $ mengembalikan perkara berikut kepada $ V $:
$ R_ {c} $
$ Path_ {RC-RT} $
Daripada menerima $ R_ {c} $ dan $ Path_ {RC-RT} $, $ V $ menjana akar pohon Merk hash $ RT '$, jika $ RT $ $ sepadan dengan hash root asal diterima dari $ U $, RT '== RT $, bukti telah berjaya, jika tidak bukti telah gagal.
3.3.2. Bukti-muat turun (PoD)
Bukti-muat turun (PoD) menyediakan cara untuk mengesahkan bahawa Data $ D $ telah dimuat turun dengan betul dari Miner $ L $ kepada Pengguna $ U $. Prosedur PoD diterangkan di bawah.

PoD

Gambar3.7 Bukti Pengunduhan

Untuk Data $ D $ akan dimuat turun, Pengguna $ U $ akan menghantar hash root pokok Merkle $ DT_ {U} = MerkleCRH (D) $ hingga Verifier $ V $.
Penambang $ L $ menyalin salinan tersimpan $ R $ dan memperoleh data $ D $. Ia kemudian mengira hash akar pokok Merkle $ DT_ {L} = MerkleCRH (D) $.
$ L $ mencipta Cip Cip $ PK_ {Cipher} $, menerapkannya kepada Data $ D $, dan menghasilkan salin tersusun $ R '= Cipher (D, PK_ {Cipher}) $. Ia kemudian mengira hash akar $ R'T = MerkleCRH (R ') $, dan menghantar yang berikut kepada $ V $:
$ DT_ {L} $
$ PK_ {Cipher} $
$ R'T $
$ V $ mengecek apakah $ DT_ {U} $ sama dengan $ DT_ {L} $. Jika tidak, bukti telah gagal.
$ V $ menghantar satu cabaran rawak $ c $ ke $ L $, iaitu cabaran simpanan blok $ c $ th $ D $ dan $ R '$.
$ L $ mengambil $ D_ {c} $ yang merupakan blok $ c $ th $ D $ dan mengira $ Path_ {DC-DT} $ yang mengandungi nilai hash dari semua jalan nodus pohon Merkle dari $ D_ {c } $ ke nod akar. $ L $ juga mengambil $ R '{c} $ yang merupakan blok $ c $ th $ R $ dan mengira $ Path {R'C-R'T} $ yang mengandungi nilai hash dari semua nodus pokok Merkle  path dari $ R '_ {c} $ ke nod akar. Ia kemudian mengembalikan yang berikut kepada $ V $:
$ D_ {c} $
$ Path_ {DC-DT} $
$ Path_ {R'C-R'T} $
Daripada menerima $ D_ {c} $ dan $ Path_ {DC-DT} $, $ V $ menjana akar root Merkle $ DT '{L} $, dan mengesahkan bahawa $ DT' {L} $ sepadan dengan hash root $ DT_ {L} $ sebelum ini diterima dari $ L $, iaitu $ DT '{L} == DT {L} $. Jika tidak, bukti telah gagal.
Daripada menerima $ D_ {c} $ dan $ PK_ {Cipher} $, $ V $ menghasilkan blok data yang dikitarkan $ R '{c} = Cipher (D {c}, PK_ {Cipher}) $, R'T '$ menggunakan $ R' {c} $ dan menerima $ Path {R'C-R'T} $, dan mengesahkan bahawa $ R'T '$ sepadan dengan hash root sebelum ini menerima $ R'T $ daripada $ L $, iaitu $ R'T '== R'T $. Jika tidak, bukti telah gagal.
$ U $ data muat turun $ R '$ dari $ L $.
$ U $ meminta bukti muat turun dari $ V $
$ V $ menghantar satu cabaran rawak $ c $ hingga $ U $, iaitu cabaran penyimpanan blok $ c $ th $ R '$.
$ U $ mengambil $ R '{c} $ yang merupakan blok kandungan $ {c} $ pada $ R' $, dan mengira $ Path {R'C-R'T} $, yang mengandungi nilai hash semua jalan nod pokok Merkle dari $ R '_ {c} $ ke nod akar, dan hantar berikut ke $ V $:
$ R '_ {c} $
$ Path_ {R'C-R'T} $
Daripada $ R '{c} $ dan $ Path {R'C-R'T} $, $ V $ menjana akar root Merkle $ R'T "$, jika $ R'T" $ sepadan dengan hash root $ R'T $ sebelum ini diterima daripada $ L $, iaitu $ R'T "== R'T $, bukti telah berjaya, dan $ V $ menghantar kunci Cipher $ PK_ {Cipher} $ hingga $ U $, jadi bahawa $ U $ dapat menghuraikan $ R '$ untuk mendapatkan data $ D $ berjaya.
3.3.3. Proof-of-Spacetime (PoSt)
Bukti Masa Ruang (PoSt) menyediakan cara untuk mengesahkan bahawa Miner $ L $ telah menyimpan Data $ D $ untuk tempoh tertentu. Proses ini juga menyediakan bukti tidak langsung mengenai kapasiti simpanan $ L $. Prosedur PoSt diterangkan di bawah.

PoSt

Gambarajah 3.8 Bukti Masa Ruang

Seperti yang dijelaskan dalam prosedur PoRep, data $ D $ disulitkan untuk memperoleh salinan unik $ R $, $ R $ disimpan pada $ L $, hash root pohon Merkle ialah $ RT = MerkleCRH (R) $.
$ V $ juga menyimpan $ RT $.
Pada masa tertentu $ T $, $ L $ meminta bukti cabaran storan dari $ V $.
$ V $ menghantar cabaran rawak $ c $ ke $ L $, iaitu cabaran storan pada blok $ c $ th $ R $.
$ L $ mengambil $ R_ {c} $ yang merupakan blok $ c $ th $ R $, dan mengira $ Path_ {RC-RT} $ yang mengandungi nilai hash dari semua jalan nodus pohon Merkle dari $ R_ { c} $ dan nod akar, dan hantar yang berikut ke $ V $:
$ R_ {c} $
$ Path_ {RC-RT} $
Dari yang diterima $ R_ {c} $ dan $ Path_ {RC-RT} $, $ V $ menjana
Root pokok Merkle hash $ RT '$, dan mengesahkan bahawa $ RT $ $ sepadan dengan hash root asal yang disimpan $ RT $, iaitu $ RT' == RT $. Jika tidak, bukti telah gagal.
Ulangi langkah 3 hingga 6 pada selang masa yang diberikan.
Siri cabaran dan bukti yang berulang diulang antara $ L $ dan $ V $ menghasilkan bukti yang berjaya dalam tempoh masa.
3.3.4. Cahaya-Bukti-Kapasiti (LPoC)
Bukti Kapasiti Cahaya (LPoC) menyediakan cara untuk mengesahkan keupayaan penyimpanan yang ada pada penambang $ L $. Kapasiti yang tersedia tidak termasuk ruang storan yang telah digunakan untuk data sedia ada. Bukti ringan PPIO mengurangkan jumlah sumber yang terbuang apabila menjalankan bukti rumit. Prosedur LPoC dipecahkan kepada dua fasa, yang diterangkan di bawah.

Fasa Inisialisasi
LPoC-Init

Rajah 3.9 Inisialisasi Tahap Cahaya-Bukti-Kapasiti

$ V $ menghasilkan Grafik Aciclic Directed (DAG) yang unik $ G = (N, E) $ untuk pelombong tertentu $ L $, di mana N adalah kumpulan nod dalam G, dan E adalah kumpulan tepi yang menghubungkan nod dalam G.
Mari $ \ pi (n) = {n ':( n', n) \ in E | n '\ in N, n \ in N} $ menjadi set pendahulu nod $ n $ dalam $ G $.
Biarkan $ L_ {ID} $ menjadi pengecam $ L $, biarkan $ | n | $ menjadi pengenal nod $ n $.
Let $ w (n) = CRH (L_ {ID}, | n |, w (\ pi (n)) $ menjadi nilai hash nod $ n $, di mana $ w (\ pi (n)) = w (n_ {1}), ..., w (n_ {M})) $ dan $ n_ {1}, ... n_ {M} \ in \ pi (n) $;
$ L $ mengira nilai hash $ w (n) $ untuk semua nod dalam $ G $, dan menyimpan nilai dalam storan yang tersedia, untuk menyediakan cabaran dari $ V $.
Fasa Pengesahan
LPoC-Verify

Gambarajah 3.10 Fasa Pengesahan Cahaya-Bukti-Kapasiti

Pada masa yang diberikan $ T $, $ L $ meminta cabaran LPoC dari $ V $.
$ V $ memilih nod rawak $ n \ dalam N $, dan menghantar $ | n | $ hingga $ L $.
Berdasarkan yang diterima $ | n | $, $ L $ menghantar nilai hashnya yang tersimpan $ w (\ pi (n)) $ dari semua nod dalam $ \ pi (n) $ dan disimpan $ w (n) $ hingga $ V $
Dari yang diterima $ w (\ pi (n)), $ V $ mengira $ w '(n) $ dengan formula $ w (n) = CHR (L_ {ID}, dan | n | n)) $, dan mengesahkan bahawa $ w '(n) $ adalah serupa dengan yang sebelumnya diterima $ w (n) $ dari $ L $. Jika tidak, bukti itu telah gagal.
$ V $ secara rawak memilih salah satu daripada pendahulunya $ n $, mengulangi langkah 2 hingga 4, sehingga tidak ada lagi pendahulunya untuk mencuba mana-mana set pendahulunya.
Ulangi prosedur dari langkah 1 pada selang masa yang diberikan.
Serangkaian cabaran dan bukti yang berjaya diulang antara $ L $ dan $ V $ menghasilkan bukti kebolehan yang berjaya untuk $ L $.
3.4. Konsensus
Untuk rangkaian blockchain terdesentralisasi untuk beroperasi, nod yang berbeza perlu mencapai persetujuan untuk mengesahkan dan merekodkan transaksi dalam rangkaian. Ia juga merupakan proses yang diperlukan apabila menambah blok baru ke lejar blockchain. Pasaran simpanan PPIO adalah berdasarkan teknologi blockchain. Ia juga memerlukan mekanisme konsensus yang direka dengan jelas untuk rangkaian simpanannya, untuk mengekalkan pasaran simpanan yang selamat dan sihat. Algoritma konsensus yang biasa digunakan mempunyai kebaikan dan keburukan mereka. Kesepakatan Bukti Kerja (PoW) memaksa setiap simpul untuk menyelesaikan masalah matematik rumit, untuk bersaing untuk membina blok baru. PoW boleh dipercayai, tetapi ia memperkenalkan pengiraan yang tidak bermakna dan pembaziran tenaga. Bukti konsekuensi Stakes (PoS) menimbang nod berdasarkan berapa banyak cryptocurrencies yang mereka simpan, dalam menentukan nod yang mempunyai hak untuk membina blok baru. Ia membolehkan bangunan blok yang lebih cepat dan mengurangkan masalah pembaziran di PoW, tetapi masih berisiko menjadi terpusat, kerana pihak berkepentingan yang paling menonjol mungkin mendominasi dan menjadi monopoli. FileCoin memperkenalkan Bukti Masa Ruang dan menggunakannya sebagai ukuran untuk mengira kuasa setiap nod dalam algoritma konsensusnya. Ia adalah gabungan idea-idea di sebalik PoW dan PoS. Bagaimanapun, dengan menggunakan bukti jarak masa sahaja tidak mencerminkan sumbangan setiap nod. Sebagai contoh, nod tertentu mungkin tidak mempunyai kapasiti storan yang besar, tetapi masih boleh memberikan perkhidmatan muat turun berharga dengan sambungan jalur lebar yang tinggi, yang juga perlu dikira sebagai sumbangan kepada rangkaian.

Algoritma konsensus PPIO mengambil kedua-dua storan penyimpanan dan jalur lebar setiap nod miner ke akaun ketika mengira kuasanya. Proses ini bermula dengan menjana kumpulan nod penambang calon berdasarkan kekuatan setiap nod, dan dari kolam, pelombong rawak dipilih melalui Fungsi Rawak Terperinci (VRF) untuk membina blok baru. Akhirnya, blok itu disahkan melalui kesepakatan Byzantine Fault Tolerance (BFT). Kaedah ini dapat meningkatkan kelajuan dan mengurangkan kos bangunan blok, mencegah nod dari menjadi monopoli, dan mengekalkan ketekalan dan keselamatan lejar.

3.4.1. Kuasa Penambang
Kuasa mengundi setiap nod dalam rangkaian PPIO dikira berdasarkan dua faktor:

Kuasa Penyimpanan: Kekuatan penyimpanan untuk penambang $ L_ {i} $ pada masa yang diberikan $ t $ dikira sebagai: $ L ^ {i, t} {s} = \ alpha * L ^ {i, t} { st} / N_ {st} + \ beta * L ^ {i, t} {c} / N {c} $, di mana $ L ^ {i, t} {st} $ adalah ruang simpanan yang terbukti penambang $ L {i} $ pada masa $ t $, $ L ^ {i, t} {c} $ adalah kapasiti terbukti pada masa $ t $, $ N {st} $ adalah jumlah masa yang terbukti dari seluruh rangkaian, dan $ N_ {c} $ ialah jumlah kapasiti terbukti of rangkaian keseluruhan. Pengiraan ini mengambil kira kedua-dua ruang penyimpanan semasa dan keupayaan baki pelombong supaya ia menilai bukan sahaja sumbangan semasa pelombong tetapi juga potensi sumbangannya pada masa akan datang. Parameter $ \ alpha $ dan $ \ beta $ boleh digunakan untuk menyesuaikan keseimbangan antara dua faktor di peringkat pembangunan yang berbeza, untuk menyediakan insentif yang mencukupi untuk pelombong baru untuk menyertai dan menyumbang sumber. Sebagai contoh, semasa peringkat awal rangkaian apabila tidak ada data yang mencukupi untuk disimpan, lebih besar $ \ beta $ dan nilai $ \ alpha $ yang lebih kecil boleh digunakan. Apabila penggunaan storan meningkat, nilai $ \ beta $ akan secara beransur-ansur menurun sementara nilai $ \ alpha $ akan meningkat secara beransur-ansur.

Kuasa jalur lebar: Kekuatan jalur lebar untuk penambang $ L_ {i} $ pada masa yang diberikan $ t $ dikira sebagai: $ L ^ {i, t} {b} = \ gamma * L ^ {i, t} { bw} / N_ {bw} $, di mana $ L ^ {i, t} {bw} $ adalah lebar jalur terbukti pelombong $ L {i} $ pada masa yang diberikan $ t $, dan $ N_ {bw} lebar lebar terbukti rangkaian.

Dengan menggabungkan kuasa penyimpanan dan kuasa lebar jalur, kuasa keseluruhan pelombong $ L_ {i} $ pada masa $ t $ boleh dikira sebagai: $ L ^ {i, t} {pow} = L ^ {i, t} {s} + L ^ {i, t} _ {b} $.

Langkah seterusnya adalah untuk menggunakan kuasa keseluruhan setiap nod dalam memilih calon untuk membina blok seterusnya. Pada masa $ t $, biarkan $ B_ {prev} $ menjadi blok sebelumnya dalam lejar, biarkan $ M $ menjadi nilai maksimal fungsi $ Hash $, biarkan $ D $ menjadi parameter kesulitan, pelombong yang memenuhi syarat berikut akan dipilih sebagai calon: $ Hash (Hash (B_ {prev}), L_ {i}) \ leq L ^ {i, t} _ {pow} * M / D $

Dari persamaan, jelas bahawa peluang penambang yang dipilih dipilih bergantung pada kuasa keseluruhannya pada masa itu $ L ^ {i, t} _ {pow} $, yang mewakili keseluruhan sumbangannya kepada rangkaian. Kuasa yang lebih tinggi membawa kepada peluang yang lebih tinggi dipilih.

3.4.2. Fungsi Rawak Diverifikasi (VRF)
Selepas pemilihan di 3.4.1 selesai, semua pelombong calon diletakkan di dalam kolam, bersedia untuk peringkat pemilihan seterusnya. PPIO menyuntik rawak pada langkah ini untuk mengelakkan monopoli oleh sebilangan kecil pelombong. Bagaimanapun, dalam rangkaian yang terdesentralisasi, kekangan itu sendiri perlu disahkan. Oleh itu, PPIO mengamalkan fungsi rawak yang dapat diverifikasi (VRF) [20] dalam pengiraan untuk menentukan pelombong calon mana yang mempunyai hak akhir untuk menulis satu blok.

VRF adalah fungsi pseudo-rawak yang membuktikan bukti ketepatan outputnya [24], definisi matematiknya [25] adalah:

$ Fungsi $ $ F $

$ GEN \ left (1 ^ k \ right) = menjana \ left (PK, SK \ kanan) $

$ PROVE_ {SK} (x) = (F_ {SK} (x), \ Pi_ {SK} (x)) $

$ VER_ {PK} (x, y, \ Pi) = true \ mathbin {/} false $

Fungsi $ GEN $ menghasilkan kunci awam $ PK $ dan kunci peribadi $ SK $. Terapkan VRF $ F $ dengan $ PK $ pada input $ x $ untuk mendapatkan $ y = F_ {SK} (x) $ dan bukti $ \ Pi_ {SK} (x) $. $ y $ adalah nombor rawak yang dihasilkan, dan ia boleh disahkan menggunakan kunci awam $ PK $ oleh $ VER_ {PK} (x, y, \ Pi) = true \ mathbin {/} false $.

VRF mempunyai ciri-ciri berikut:

Keunikan

$ \ nexists ((x, y_ {1}, \ Pi_ {1}), (x, y_ {2}, \ Pi_ {2})) $ s.t. $ VER_ {PK} (x, y_ {1}, \ Pi_ {1}) = VER_ {PK} (x, y_ {2}, \ Pi_ {2}) $
Kesediaan

jika $ (y, \ Pi) = PROVE_ {SK} (x) $ maka $ VER_ {PK} (x, y, \ Pi) = true $
3.4.3. Byzantine Fault Tolerance (BFT)
Toleransi Kesalahan Byzantine (BFT) berasal dari Masalah Jenderal Byzantine, yang merupakan contoh terkenal mengenai persetujuan yang diagihkan. [21] Dalam rangkaian yang diedarkan, nod yang berbeza mencapai konsensus dengan bertukar maklumat. Walau bagaimanapun, sesetengah mesej mungkin mengandungi maklumat yang salah atau mengelirukan kerana kegagalan nod, atau rasuah mesej semasa penghantaran. Ia juga mungkin bahawa nod tertentu berniat jahat atau dikompromikan dan menyerang rangkaian dengan sengaja. Akibatnya, konsensus yang konsisten tidak dapat dicapai dengan mudah. Matlamat BFT adalah untuk menyelesaikan masalah ini.

3.4.4. Persetujuan PVFT
PPIO menggabungkan pemilihan nod berdasarkan kuasa, bangunan blok rawak berdasarkan VRF dan toleransi kesalahan berdasarkan BFT ke dalam algoritma konsensus yang unik yang dipanggil PVFT, dan bentuk matematiknya ditakrifkan sebagai berikut:

$ G_ {bp} = {bp_ {1}, bp_ {2}, ... bp_ {n} | saham (bp_ {i}) \ geqslant C} $ Kuasa setiap nod kandidat di kolam calon $ G_ { bp} $ perlu lebih tinggi atau sama dengan nilai minimum C.

$ (F_ {SK} (Block_ {prev}), \ Pi_ {SK} (x)), BP = F_ {SK} (Block_ {prev}) \ mod | G_ {bp} | $. Cari nombor rawak dengan menggunakan VRF ke hash blok sebelumnya, kemudian hitung modulusnya dengan saiz kumpulan calon $ G_ {bp} $, dan gunakan hasilnya untuk memilih nod untuk membina blok seterusnya.

$ BFT (G_ {bp}) $ Nod kandidat mengesahkan blok baru yang ditambah dan mencapai pengesahan akhir.

4. Senibina
PPIO mengikuti reka bentuk sistem berlapis, untuk memudahkan perkembangan masa depan, dan menjadikannya lebih mesra kepada pemaju. Seperti yang ditunjukkan dalam Rajah 4.1, PPIO terdiri daripada tujuh lapisan, iaitu:

lapisan

Rajah 4.1 7 lapisan seni bina PPIO

Lapisan Fizikal: lapisan perkakasan, yang menyediakan sumber penyimpanan dan jalur lebar yang dibincangkan dalam 4.1.

Lapisan Data: unit dan struktur data asas, dibincangkan dalam 4.2.

Network Layer: Protokol rangkaian dan algoritma rangkaian P2P untuk sambungan, pemindahan data, mengimbangi beban dan penyulitan, dibincangkan dalam 4.3.

Lapisan Konsensus: Skim konsensus PPIO dan pelaksanaannya, dibincangkan dalam 4.4

Layer Insentif: menguruskan insentif dan ganjaran berdasarkan peranan setiap nod dalam rangkaian, dibincangkan dalam 4.5

Lapisan Antara Muka: SDK dan API untuk pemaju dan untuk menyokong lapisan permohonan, dibincangkan dalam 4.6

Lapisan Aplikasi: Aplikasi atau DApps yang dibangunkan oleh pemaju pihak ketiga, dibincangkan dalam 4.7

4.1. Lapisan Fizikal
Penyimpanan cakera dan jalur lebar rangkaian adalah komponen teras lapisan fizikal PPIO. Mereka adalah sumber penting dalam rangkaian penyimpanan PPIO dan oleh itu juga merupakan asas dalam menilai setiap sumbangan penambang simpanan ke rangkaian. Pelombong dengan kapasiti storan yang besar tetapi lebar jalur yang terhad dapat menyumbang lebih banyak dalam menyediakan perkhidmatan storan, sementara dengan storan kurang tetapi lebar jalur yang lebih tinggi dapat menyumbang lebih banyak dalam menyediakan perkhidmatan jalur lebar. Para penambang dengan simpanan yang banyak dan jalur lebar yang tinggi menyumbang kepada rangkaian yang paling dan seterusnya, mendapat ganjaran yang paling banyak.

Penyimpanan: Storan fizikal mungkin terdiri daripada pemacu denyar, Pemacu Negeri Solid (SSD), Pemacu Cakera Keras (HDD), Pita dan Cakera Optik (OD). Dalam rangkaian storan PPIO, pelbagai storan boleh memainkan peranan berbeza berdasarkan ciri-ciri mereka. Sebagai contoh, SSD boleh digunakan untuk menyimpan dan menyediakan perkhidmatan pengambilan cepat untuk kandungan yang popular. Jangka hayat media storan juga perlu menampung panjang kontrak penyimpanan, sebagai contoh, pita dan cakera optik boleh digunakan untuk penyimpanan lama sementara SSD dan Flash boleh meliputi penggunaan storan jangka pendek.

Jalur lebar rangkaian: Dalam bit / saat, lebar jalur rangkaian mengukur kadar pemindahan data maksimum di seluruh rangkaian rangkaian yang diberikan. Media penghantaran rangkaian boleh termasuk kabel sepaksi, kabel pasangan berpintal, kabel serat optik, dan sambungan tanpa wayar. Bandwidth mereka berbeza-beza banyak, dari Kilobits dan Megabits sesaat untuk Gigabits sesaat. Perkhidmatan rangkaian boleh dikategorikan ke dalam rangkaian perniagaan dan kediaman, dan mereka mempunyai ciri-ciri yang sangat berbeza dalam penggunaan bandwidth. Sebagai contoh, penggunaan jalur lebar perniagaan biasanya tinggi pada siang hari, sementara penggunaan jalur lebar kediaman tetap rendah. Sebaliknya berlaku pada waktu malam dan hujung minggu. Rangkaian storan yang diedarkan PPIO menyesuaikan diri dengan dinamik ini untuk menggunakan penggunaan jalur lebar yang ada dalam rangkaian.

4.2. Lapisan Data
dia seterusnya di atas lapisan fizikal adalah lapisan data. Seperti yang ditunjukkan dalam Rajah 4.2, terdapat tiga jenis struktur data yang digunakan dalam rangkaian storan PPIO:

datalayer

Rajah 4.2 Struktur data dalam lapisan data

Plot / Tile: unit kapasiti storan

Plot ini boleh dianggap sebagai pemacu maya dalam rangkaian storan PPIO, dan ia dimulakan apabila penambang menyertai rangkaian. Tanpa apa-apa data yang disimpan, ia adalah unit asas yang digunakan dalam bukti kapasiti - LPoC (seperti yang diterangkan dalam bahagian 3.3.4). Dengan data yang disimpan, ia adalah unit asas bukti masa - PoSt (seperti yang diterangkan dalam bahagian 3.3.3).

Tile adalah unit terkecil penyimpanan yang dapat disahkan dalam plot. Saiznya ialah 128KB. Dalam PoRep, PoD, dan PoSt, Tile digunakan sebagai unit asas dalam pengesahan.

Segmen: unit data storan

Segmen ini adalah unit asas penyimpanan berorientasikan objek PPIO. Objek penyimpanan sentiasa dibahagikan kepada beberapa segmen. Untuk meningkatkan perlindungan privasi, PPIO menghalang mana-mana nod miner dari menyimpan semua segmen salinan objek, walaupun salinan objek disulitkan. Segmen juga merupakan unit terkecil dalam penjadualan storan, dan saiznya berkisar dari 128KB hingga 16MB.
Piece: unit penghantaran data

Sekeping adalah unit data terkecil dalam penghantaran rangkaian PPIO, dengan saiz 128KB.
Penyebaran data diperlukan untuk mengekalkan penyimpanan data yang boleh dipercayai. PPIO mengamalkan dua kaedah untuk menambah kelebihan kepada data yang disimpannya.

Salinan Data: Data asal direplikasi ke dalam lebih banyak salinan. Walaupun kaedah memperkenalkan overhed penyimpanan yang besar, kerumitan perhitungannya adalah rendah, dan data asal dapat dipulihkan dengan cepat. Ia sering digunakan dalam menyimpan kandungan popular.

Pengekodan Berlebihan: Bahagikan data asal ke blok dan kodkan kod tersebut dengan Kod Erasure untuk menghasilkan sekumpulan blok data baru yang mempunyai kelebihan tertanam. Data asal boleh dipulihkan jika tidak lebih daripada sebilangan blok data yang hilang atau rosak. Kaedah ini mempunyai lebih banyak storan penyimpanan yang lebih rendah, tetapi lebih intensif dengan komputasi. Ia sering digunakan untuk menyimpan kandungan yang tidak berubah atau kurang popular. Reed Solomon [22] adalah salah satu Kod Erase yang biasa digunakan, dan boleh dijelaskan seperti berikut:

Biarkan $ n $ menjadi bilangan blok data dalam data asal, dan $ m $ menjadi bilangan blok data yang berlebihan, blok data asal boleh dilambangkan sebagai $ D_ {n \ times 1} $.
Tentukan Matriks Pengedaran sebagai $ B _ {(n + m) \ kali n} $, di mana n baris pertama dan n lajur membentuk matriks identiti, dan baris b dan m yang tinggal dipanggil Vandermonde Matrix atau Cauchy Matrix.
Pengekodan: Encode $ D_ {n \ times 1} $ dan menghasilkan blok data baru $ DC _ {(n + m) \ times 1} $, $ B _ {(n + m) \ times n} \ times D_ { n \ kali 1} = DC _ {(n + m) \ times 1} $;
Pengesahan: Membongkar blok data $ B ^ {- 1} {n \ times (n + m)} \ times DC {(n + m) \ times 1} = D '{n \ times 1} $. Jika $ D '{n \ times 1} == data DC' _ {n \ times 1} $ telah diod dengan betul, jika tidak, kehilangan data atau rasuah telah berlaku, dan data asal perlu dipulihkan;
Pembetulan: Anggapkan terdapat blok data $ m $ yang hilang atau rusak dalam $ DC _ {(n + m) \ kali 1} $
Dapatkan $ DC '{n \ times 1} $ dengan mengeluarkan baris m data korup dalam $ DC {(n + m) \ kali 1} $
Dapatkan $ B '{n \ times n} $ dengan membuang matriks penghantaran bersekutu dan mengira $ B' ^ {- 1} {n \ times n} $
Dapatkan data pulih $ D_ {n \ times 1} = B '^ {- 1} _ {n \ times n} \ times DC' _ {n \ times 1} $
4.3. Lapisan Rangkaian
Komunikasi di antara nod yang berbeza dalam rangkaian PPIO adalah berdasarkan satu set protokol P2P yang merangkumi yang berikut:

Transmisi: Menyokong penghantaran berasaskan TCP dan UDP. Protokol KCP [8], QUIC [9] dan SCTP [10] juga boleh digunakan, untuk meningkatkan kecekapan dan kebolehpercayaan.

Kesambungan: Teknologi NAT traversal adalah penting untuk menjamin kesambungan. PPIO menggunakan STUN (Session Traversal Utilities untuk NAT) dan relay rangkaian untuk membantu menubuhkan hubungan antara nod di belakang gerbang.

Imbangan Beban: Dengan menggunakan hash yang tetap [11], lalu lintas boleh diedarkan sama rata ke nod yang berbeza. Ia membantu mengurangkan kesan nodus kiri atau nod baru yang menyertai rangkaian.

Penyulitan: Dengan menggunakan tanda tangan utama awam-swasta asimetrik, dan penyulitan data simetrik, identiti pengirim mesej boleh disahkan, dan kandungan mesej boleh disahkan.

4.4. Lapisan Konsensus
Seperti yang dijelaskan dalam seksyen 3.4, algoritma konsensus PPIO direka khusus untuk rangkaian penyimpanannya yang diedarkan. Ia menggabungkan bukti storan, pemilihan rawak VRF, dan konsensus BFT. Untuk meningkatkan prestasi dan skalabiliti, PPIO juga mengamalkan pendekatan berlapis dalam pelaksanaan lapisan konsensus. Nod dalam rangkaian dikelompokkan kepada banyak rantaian sisi dan satu rantai induk. Rantai tuan dibentuk oleh nod terpilih yang bertanggungjawab untuk mengekalkan kesepakatan seluruh rangkaian. Di setiap rantaian sampingan, urus niaga ditangani secara tempatan tetapi diagregatkan dan dilaporkan kepada rantaian induk secara berkala. Rajah 4.3 menunjukkan contoh konsensus berlapis. Nod dalam P2P dikelompokkan kepada 3 kumpulan, kumpulan tuan, kumpulan rantaian hitam dan kumpulan rantaian putih. Butiran reka bentuk dibentangkan di bawah.

konsensus

Rajah 4.3 Kumpulan nod P2P

Master Chain, nod dalam rantai induk memohon skim konsensus PPIO untuk mengekalkan keseluruhan rangkaian.

Nod dipilih untuk menyertai rantaian induk berdasarkan sumbangan storan dan bandwidth mereka, apabila sumbangan simpul menyeberangi ambang, ia dibenarkan menyertai rantai induk.

Setiap nod dalam rantai induk juga merupakan anggota rantaian sampingan, dan ia bertanggungjawab untuk merakam urus niaga dan mengekalkan lejar rantaian sampingan.

Nod dalam rantai induk juga bertanggungjawab untuk:

Mewujudkan dan menguruskan rantaian sampingan.

Mengesahkan dan melaksanakan kontrak dan urus niaga simpanan.

Mengekalkan lejar induk.

-  Side Chain

Nod yang baru disambung ditugaskan kepada rantaian sampingan berdasarkan jarak rangkaian dan pengimbangan beban, untuk mengekalkan sambungan berkelajuan tinggi di antara nod dalam rantaian sampingan yang sama. Sekurang-kurangnya satu nod dalam rantai induk perlu diperuntukkan kepada setiap rantaian sampingan.

Nod boleh menukar rantai untuk menyesuaikan diri dengan perubahan dalam rangkaian. Rantaian sisi dengan beberapa nod di dalamnya boleh digabungkan dengan rantai lain.

Nod dalam rantai sampingan bertanggungjawab untuk:

Mengendali operasi storan.

Menjalankan bukti penyimpanan termasuk PoRep, PoD, PoSt, dan LPoC.

Memadai kontrak penyimpanan antara pelombong dan pengguna.

Mengekalkan lejar rantaian sampingan.

Melaporkan bukti dan kontrak yang sepadan dengan rantai induk.

Kelebihan konsensus berlapis:

Dalam rangkaian penyimpanan yang terdesentralisasi, nod mengambil banyak peranan yang berlainan, dan setiap operasi perlu disahkan. Konsensus berlapis membantu memudahkan pengurusan nod rangkaian dan mengelakkan ketidakcekapan untuk menyegerakkan melalui keseluruhan rangkaian.

Mengekalkan latensi rangkaian rendah adalah kunci untuk memenuhi jangkaan tinggi pengguna mengenai penyimpanan dan prestasi muat turun. Konsensus berlapis membolehkan rangkaian dibahagikan berdasarkan jarak rangkaian dan kelajuan sambungan. Oleh kerana operasi penyimpanan dapat dikendalikan dalam setiap rantai sampingan, latensi rendah dapat dicapai.

Penyimpanan atau muat turun setiap objek memerlukan kontrak. Kontrak perlu disahkan, dipadankan, dilaksanakan, dan kemudian direkodkan dalam lejar. Melakukan semua ini pada rantai tunggal boleh membebankan rangkaian. Dengan pendekatan berlapis, rantaian sampingan boleh mengambil alih sebahagian daripada beban kerja, dan ia membolehkan rangkaian menjadi lebih baik dan boleh mengendalikan sejumlah besar urus niaga serentak.

4.5. Layer Insentif
Asas mekanisme insentif PPIO is dibentuk oleh pelbagai bukti yang diterangkan dalam 3.3, termasuk PoRep, PoD, PoSt, dan LPoC. Bukti-bukti ini diperolehi dengan ketat dan diuji dengan ketat, untuk membolehkan pengesahan yang boleh dipercayai dari pelbagai jenis kerja yang dilakukan oleh nod dalam rangkaian, supaya jumlah ganjaran yang tepat dapat diberikan kepada pihak yang berlainan, untuk mengekalkan ekonomi yang sihat dan terus berkembang.

Kontrak pintar adalah asas mekanisme ganjaran PPIO:

Kontrak Penyimpanan:

Kontrak penyimpanan pengguna:  membuat kontrak penyimpanan untuk menyimpan fail ke rangkaian, yang termasuk maklumat mengenai objek penyimpanan, tempoh penyimpanan, bilangan salinan dan jumlah pembayaran yang ditawarkan.

Kontrak simpanan miner: pelombong menyerahkan kontrak penyimpanan untuk menawarkan perkhidmatan storan, yang merangkumi maklumat mengenai kapasiti storan, tempoh yang tersedia, jumlah pembayaran yang boleh diterima. Kontrak penyimpanan miner juga boleh dikemas kini di kemudian hari.

Pengindeks ini sepadan dengan kontrak pengguna dan penambang. Apabila berjaya, Pengguna mula memuat naik salinan objek ke pelombong. Semua pemindahan data dijadualkan oleh pengindeks.

Muat turun Kontrak

Kontrak muat turun pengguna: pengguna membuat kontrak muat turun untuk memuat turun fail, yang merangkumi maklumat mengenai objek yang hendak dimuat turun dan jumlah bayaran yang ditawarkan.

Kontrak memuat miner: pelombong menyerahkan kontrak muat turun untuk menawarkan perkhidmatan muat turun, yang merangkumi maklumat mengenai lebar jalur yang disediakan, tempoh dan amaun pembayaran yang boleh diterima.

Pengindeks cuba untuk memadankan kontrak pengguna dan penambang. Apabila berjaya, Pengguna mula memuat turun objek dari penambang. Semua pemindahan data dijadualkan oleh pengindeks.

Dalam rangkaian PPIO, nod yang berbeza mendapat ganjaran berdasarkan peranan mereka:

Indeks: Apabila pengguna memuat turun atau menyimpan data, ia perlu mendapatkan info pengindeksan dari Indeks. Oleh itu, Indexers menerima ganjaran pengindeksan. Apabila Indeks menghantar tugas kepada pelombong, mereka juga menerima ganjaran penjadualan.

Pengesahkan: Pengesah mengendalikan semua bukti storan PoRep, PoD, PoSt, dan PoC, dan mereka menerima ganjaran pengesahan.

Miner: Pelombong tidak hanya menyediakan ruang penyimpanan untuk menyimpan data pengguna tetapi juga menyediakan jalur lebar rangkaian untuk membolehkan pemindahan data. Penggunaan storan dan jalur lebar rangkaian akan diberi pampasan sewajarnya. Pada masa yang sama, berdasarkan jumlah penyimpanan dan jalur lebar para pelombong menyumbang kepada rangkaian, mereka akan menerima ganjaran secara berkala.

Block Builder: Nod yang merakam transaksi dan mengekalkan lejar mendapat ganjaran dengan menerima sebahagian daripada yuran transaksi. Mereka juga menerima ganjaran untuk menambah blok baru kepada lejar.

4.6. Lapisan Antara Muka
Salah satu matlamat utama reka bentuk PPiO adalah untuk menyediakan penyimpanan teragih yang boleh diprogramkan, yang juga boleh dipanggil Storage Desentralized sebagai Perkhidmatan (DSaaS), Untuk menjadi lebih mesra kepada pemaju, ia menyediakan:

SDK

Ia menyediakan API peringkat tinggi pada pelbagai platform, seperti iOS, Android, Mac dan Windows.

API Web

Memudahkan pemaju membangunkan aplikasi berasaskan web.

Antara muka JSON-RPC

Membenarkan DApps untuk membuat panggilan ke fungsi pada nod yang diedarkan, membolehkan penyepaduan mudah sistem penyimpanan PPIO.

Kotak pasir App
PPIO boleh menyokong sejumlah besar aplikasi yang berjalan serentak dalam rangkaian storannya. Pemaju boleh mengkonfigurasi keselamatan fail dalam aplikasi mereka.

Setiap Apl mempunyai kunci penyulitan.

Pemaju aplikasi boleh menentukan bagaimana untuk menyulitkan objek data dalam aplikasi mereka:

Penyulitan menggunakan kunci penyulitan Apl sahaja.

Enkripsi menggunakan kekunci penyulitan kedua-dua App dan pengguna.

Pemilik objek boleh mengkonfigurasi akses objek dalam tiga cara:

Persendirian: hanya pemilik boleh mengakses.

Sharable: pemilik boleh berkongsi akses ke objek tersebut kepada beberapa pengguna lain.

Awam: semua pengguna boleh mengakses objek tersebut.

Pemaju apl bertanggungjawab untuk kandungan fail dalam aplikasi mereka.

object_encrypt.png

Rajah 4.4 Diagram kotak pasir App

PPIO menyediakan dua peringkat API. API peringkat rendah memberi pemaju lebih banyak fleksibiliti dan kawalan yang lebih baik terhadap pelbagai fungsi PPIO. Antara muka peringkat tinggi lebih mudah, dan mereka berfungsi sebagai sistem fail tradisional dengan reka bentuk untuk membolehkan penggunaan yang cepat dan mudah.

API peringkat rendah

ppio init - memulakan nod pengguna

Pengguna baldi PPIO ... - operasi berkaitan baldi seperti penciptaan, pemadaman, dll.

Objek pengguna PPIO ... - operasi berkaitan objek seperti penciptaan, pemadaman, dll.

Metodata pengguna PPIO ... - operasi berkaitan metadata

Penyimpanan pengguna PPIO gc - padam data yang tiada penyendiri mempunyai kontrak penyimpanan

Penggunaan storan pengguna PPIO - senaraikan maklumat penggunaan storan

Daemon pengguna PPIO memulakan perkhidmatan RPC dan P2P

Berhenti daemon PPIO-perkhidmatan - perkhidmatan penutupan

Pengguna pengguna PPIO l - tunjukkan maklumat pengguna semasa, seperti id, alamat ip dll.

PPIO-user net ping <peer-id> - keseragaman ujian dari rakan sebaya, pengguna atau pelombong.

Rakan bersih PPIO pengguna - menunjukkan semua rakan semasa yang disambungkan.

API Penyimpanan peringkat tinggi

PPIO-ndisk initlialize disk rangkaian

Penggunaan PPIO-ndisk - periksa
penggunaan cakera rangkaian

PPIO-ndisk - muat naik fail setempat ke cakera rangkaian

PPIO-ndisk mendapatkan - muat turun fail dari cakera rangkaian

Copy PPIO-nd - salin fail dari cakera rangkaian lain

PPIO-ndisk mkdir - buat direktori

PPIO-ndisk ls - senarai kandungan cakera rangkaian

PPIO-ndisk cp - salin fail dari cakera rangkaian

PPIO-ndisk rm - padam fail dari cakera rangkaian

PPIO-ndisk mv - memindahkan fail pada cakera rangkaian

Tuntutan PPIO - memberikan hak akses ke pengguna lain

Antara muka Pembangunan Aplikasi Multimedia peringkat tinggi

Info media PPIO - dapatkan info asas media aliran
Main PPIO-media - mula mainkan media aliran
Berhenti PPIO-media - berhenti untuk memainkan media aliran
Jeda media PPIO - media aliran jeda
Mencari media PPIO - mencari titik dalam media aliran dan menyambung semula bermain
4.7. Lapisan Aplikasi
API PPIO direka untuk membolehkan pemaju pihak ketiga untuk membina semua jenis aplikasi, termasuk tetapi tidak terhad kepada yang berikut:

Aplikasi Penyimpanan

Penyimpanan data peribadi. Disebabkan sifatnya yang terdesentralisasi, rangkaian storan PPIO sangat sesuai untuk aplikasi storan rangkaian peribadi. Data peribadi dibahagikan, disulitkan dan disimpan pada nod yang berbeza untuk memastikan tahap perlindungan privasi yang tinggi. Pada masa yang sama, akses kepada data dibatasi oleh kunci peribadi pengguna, menjadikan aset data peribadi lebih selamat.

Penyimpanan data perusahaan: PPIO dapat memberikan penjimatan kos yang signifikan untuk storan data perusahaan sambil menyediakan perkhidmatan berprestasi tinggi. Pada masa yang sama, antarmukanya serasi dengan perkhidmatan storan data yang sedia ada seperti AWS S3 dan membuat penghijrahan ke PPIO lebih mudah.

DApps:

Menyimpan data aplikasi pada blockchain sangat mahal untuk aplikasi terdesentralisasi. Kontrak pintar atau data aplikasi lain boleh disimpan pada storan luaran dengan menggunakan API PPIO, untuk mencapai penjimatan kos yang ketara. Sebagai contoh:

DApps Sosial: PPIO dapat membantu mengesahkan identiti pengguna dan mesej mereka, ia juga boleh membantu mengekalkan perbualan secara peribadi.

Sistem iklan: Selain menyimpan kandungan iklan, PPIO juga boleh membantu dengan tepat mengira dan melaporkan statistik akses Iklan, seperti kadar klik-tayang. Oleh kerana data semacam itu biasanya menjadi asas pembayaran iklan, ketepatan dan ketelusannya selalu menjadi masalah untuk platform iklan tradisional. Perniagaan mungkin tidak dapat mengesahkan statistik yang dilaporkan, untuk memastikan mereka membayar pendedahan sebenar iklan, dan memahami keutamaan pengguna sebenar. PPIO dapat menyelesaikan masalah ini dengan cekap.

Kebolehpercayaan Apps: Rantaian bekalan atau DApps lain yang memerlukan penyimpanan data yang boleh dipercayai dan dapat diverifikasi.

Aplikasi Media

PPIO menyediakan sumber jalur lebar yang berkesan yang boleh membantu mengurangkan kos pengedaran kandungan dengan ketara. PPIO juga dilengkapi dengan penjadualan dan algoritma penghantaran yang dioptimumkan khusus untuk mencapai main balik streaming yang lancar. Bersama dengan caching PCDN untuk pengedaran kandungan atas permintaan, dan pecutan silang rangkaian untuk penyiaran masa nyata, pengalaman pengguna berkualiti tinggi dapat dicapai dan dikekalkan untuk aplikasi media. Pada masa yang sama, PPIO dapat menyediakan statistik yang boleh dipercayai mengenai penggunaan kandungan yang merupakan data pemasaran berharga untuk aplikasi ini.

Pertukaran data

Aset fail boleh didagangkan dalam rangkaian PPIO. PPIO boleh menyediakan cara untuk memadankan penjual dan pembeli dan menangani transaksi dengan selamat dan boleh dipercayai, tanpa memerlukan pihak perantaraan. Aplikasi biasa seperti pasaran apl dan platform kandungan boleh mendapat manfaat daripada penggunaan PPIO.

Gudang Data

PPIO boleh digunakan sebagai gudang data perusahaan, menyimpan sejumlah besar data sejarah, dan menggantikan storan data tempatan yang tidak boleh dipercayai tradisional atau penyimpanan awan mahal. Selain data perusahaan, PPIO juga boleh digunakan untuk menyimpan pangkalan data awam seperti kolam gen.

Untuk keperluan penyimpanan jenis lain, PPIO juga akan memberikan sokongan yang diperlukan. Selain itu, PPIO akan dibuka sumber tidak lama lagi. Pada masa itu, peminat dan pemaju App akan dapat mengambil bahagian dalam pembangunan PPIO dan menambah sokongan untuk banyak lagi aplikasi.

5. Keselamatan
Mengekalkan keselamatan adalah tugas paling penting dalam rangkaian storan yang diedarkan. Reka bentuk PPIO mengikuti langkah-langkah keselamatan yang ketat untuk memastikan integriti dan kebolehpercayaan sistem storannya. Bab ini membincangkan bagaimana PPIO mempertahankan terhadap serangan rangkaian biasa, termasuk serangan Serangan, serangan Outsourcing, Generasi serangan Sybil yang menyasarkan sistem storan terdesentralisasi sendiri, dan Serangan Penyebaran Dedarkan Perkhidmatan (DDoS), Serangan Eclipse yang menyasarkan blockchain.

5.1. Serangan Sybil
Seperti yang ditunjukkan dalam Rajah 5.1, serangan Sybil berlaku apabila nod penambang tamak mewujudkan beberapa akaun dalam rangkaian dan mendakwa telah menyimpan salinan data dalam setiap akaun, tetapi sebenarnya, ia hanya menyimpan salinan tunggal. Sekiranya berjaya, serangan itu membolehkan penambang menerima ganjaran daripada pelbagai akaun secara tidak adil. Sebaliknya, ia dapat mengurangkan keterlaluan data sebenar dalam rangkaian, ad sangat kompromi kebolehpercayaan sistem storan.

serangan sybil

Rajah 5.1 Serangan Sybil

Bukti Replikasi PPIO (PoRep) dan Bukti Masa Ruang (PoSt) menghalang serangan Sybil dengan menghendaki setiap salinan data menjadi unik. Akibatnya, setiap akaun pelombong sepatutnya menyimpan salinan yang berbeza. Pengesahan Dalam kedua-dua bukti ini mengesahkan salinan berdasarkan pokok Merkle yang dibina secara unik. Oleh kerana diperlukan sejumlah besar masa untuk mencipta salinan untuk mengira pokok Merkle yang betul, kedua-dua bukti akan gagal atau tamat masa jika penambang tidak menyimpan salinan uniknya dengan betul.

5.2. Serangan Penyumberan Luar
Seperti yang ditunjukkan dalam Rajah 5.2, serangan penyumberan luar berlaku apabila penambang mendakwa telah menyimpan salinan data dalam storan fizikal mereka, tetapi sebenarnya mereka telah menyimpan data pada sistem storan pihak ketiga. Penambang ini memenuhi permintaan muat turun dengan menghantar data dari storan pihak ketiga kepada pengguna. Apabila berbilang pelombong mengikuti, sistem storan pihak ketiga hanya boleh menyimpan satu salinan data untuk menjimatkan kos, dan menyampaikannya kepada beberapa penambang. Akibatnya, serangan itu mengurangkan kelebihan data sebenar dalam sistem. Selain itu, apabila storan pihak ketiga adalah sistem storan terpusat, ia meningkatkan risiko data yang tidak dapat pulih apabila terdapat kegagalan dengan pelayan terpusat.

serangan penyumberan luar

Serangan Penyumberan Luar

PoSt PPIO secara efektif dapat mempertahankan terhadap serangan generasi, kerana para penambang perlu secara berkala membuktikan penyimpanan aset data pada penyimpanan fizikal mereka. Salinan data setiap kedai penanam perlu unik, oleh itu ia meningkatkan kesukaran bagi mana-mana nod penambang untuk melakukan penyumberan luar serangan, dan ia mengurangkan risiko kehilangan redundansi data dalam rangkaian.

Pada masa yang sama, Pengesah di PoSt menghendaki cabaran untuk dijawab dalam tempoh tertentu. Apabila penambang menyimpan data pada storan pihak ketiga, ia mengambil masa tambahan untuk mengambil data sebelum mereka dapat menghasilkan bukti yang betul. Hasilnya, cabaran itu mungkin akan tamat tempoh, dan pelombong akan dihukum kerana gagal memberikan bukti dalam masa.

5.3. Serangan Generasi
Seperti yang ditunjukkan dalam Rajah 5.3, serangan generasi berlaku apabila pelombong berpura-pura menyimpan salinan data, tetapi sebenarnya, ia hanya menyimpan maklumat yang cukup yang boleh digunakan untuk menghasilkan bukti dan bertindak balas terhadap cabaran penyimpanan dari Verifier dalam masa nyata. Sekiranya berjaya, pelombong boleh mendakwa telah menyimpan sejumlah besar data dan mendapat ganjaran yang tidak adil. Sebaliknya, kerana pengguna tidak boleh memuat turun data yang betul dari penambang, kebolehpercayaan sistem storan terdegradasi dengan ketara.

serangan generasi

Rajah 5.3 Generasi Serangan

PPIO berkesan dapat mencegah serangan generasi dengan reka bentuk berikut:

PoSt dan LPoC memerlukan pelombong untuk menjana pra-pohon Merkle atau DAG dari data, untuk memenuhi cabaran berkala. Ia sangat memakan masa untuk menghasilkan bukti-bukti, dan cabaran-cabaran yang mungkin akan berlaku ketika pelombong cuba untuk menjana mereka apabila diminta. Sekalipun pelombong itu melabur dalam perkakasan yang membolehkan generasi bukti masa nyata, kosnya akan mengatasi ganjaran. Oleh itu, pelombong tidak diberi insentif untuk melakukan serangan generasi.

Selain itu, penambang yang menyimpan data pengguna juga perlu menyediakan perkhidmatan muat turun. Dalam PoD, Pengesah mengesahkan muat turun pengguna data dari penambang. Oleh kerana pelombong yang menjalankan serangan generasi tidak menyimpan salinan data sebenar, PoD akan sentiasa gagal, dan penambang akhirnya akan dihukum kerana tidak dapat memenuhi permintaan muat turun. Ini juga mengambil insentif untuk pelombong melakukan serangan generasi.

5.4. Penafian Penyerang Perkhidmatan yang Diedarkan
Seperti yang ditunjukkan dalam Rajah 5.1, Serangan DDoS berlaku apabila sebilangan besar nod rangkaian menyerang nod sasaran pada masa yang sama. Sebagai contoh, serangan itu boleh menyebabkan sejumlah besar trafik rangkaian yang melebih-lebihkan nod itu, dan menyebabkan ia tidak dapat bertindak balas kepada permintaan perkhidmatan tetap.

Serangan DDOS

Rajah 5.4 Serangan DDoS

PPIO berkesan boleh menghalang serangan DDoS dengan reka bentuk berikut:

Untuk nod untuk menggunakan sebarang perkhidmatan di PPIO, ia perlu menawarkan bayaran (atau membelanjakan Gas). Ia akan menyebabkan penyerang banyak wang untuk menyebarkan nod. Oleh itu, ia menjadi mahal untuk mengendalikan serangan DDoS dengan berkesan dalam rangkaian PPIO.

Dalam mekanisme konsensus PPIO, nod dipilih secara rawak untuk membina blok seterusnya dalam lejar. Sekiranya penyerang menyerang semua nod yang tersedia di seluruh rangkaian, operasi PPIO tidak akan terjejas. Akibatnya, tidak realistik bagi penyerang untuk melakukan serangan DDoS yang berkesan terhadap PPIO.

5.5. Serangan Gerhana
Seperti yang ditunjukkan dalam Rajah 5.5, serangan gerhana berlaku apabila penyerang mengasingkan nod mangsa dengan mengawal semua sambungan ke dan dari nod. Hasilnya, nod mangsa tidak lagi menerima maklumat yang betul dari seluruh rangkaian dan oleh itu boleh dimanipulasi oleh penyerang, satud mungkin berakhir dengan kerugian ekonomi.

serangan gerhana

Rajah 5.5 Serangan Gerhana

PPIO berkesan dapat menghalang Serangan Eclipse dengan reka bentuk berikut:

Dalam rangkaian blok PPIO, cara sambungan yang ditubuhkan di antara nod yang berbeza tidak semata-mata berdasarkan ID rakan sebaya mereka. Kekangan pada alamat IP juga digunakan. Hasilnya, penyerang perlu mempunyai banyak alamat IP untuk mengasingkan nod sasaran dengan berkesan. Oleh itu ia secara substansial meningkatkan kos menjalankan serangan gerhana.

Fungsian teras dalam rangkaian PPIO diedarkan di antara nod yang berbeza, yang menjadikannya lebih susah untuk diserang. Sebagai contoh, terdapat beberapa nod Indekser dan nod Verifier dalam rangkaian. Walaupun penyerang berjaya mengasingkan nod Indekser, nod Verifier masih berfungsi dan boleh membantu menemui serangan, dan sebaliknya. Oleh itu, penyerang perlu mengawal majoriti nod Indexer dan nod Verifier dalam rangkaian, menjadikan ia tidak dapat dilaksanakan secara ekonomi untuk melakukan serangan gerhana yang berkesan.

6. Ekosistem
Ahli-ahli yang mengambil bahagian dalam ekosistem PPIO mengambil peranan yang berbeza, seperti Pengguna, Penambang, Penilai atau Penunjuk. Sistem ini memberi insentif kepada setiap ahli untuk mengambil tanggungjawab mereka. Mereka diberi ganjaran kerana melaksanakan fungsi mereka dan membuat sumbangan kepada rangkaian. Mereka dihukum kerana gagal menunaikan tanggungjawab mereka atau menjalankan operasi haram. Oleh kerana rangkaian beroperasi dalam persekitaran yang terbuka dan adil, ia menggalakkan ahli untuk menyumbang lebih banyak sumber kepada rangkaian, menarik ahli baru untuk mengambil bahagian dan membantu mengekalkan ekosistem yang sihat dan mengekalkan.

Reka bentuk PPIO juga menggunakan beberapa mekanisme yang membantu menstabilkan ekonominya. Cryptocurrency yang digunakan dalam sistem PPIO untuk mengutip ganjaran atau perkhidmatan pembelian dipanggil PPIO Coin. PPIO menawarkan program kunci harga yang membolehkan pengguna memanfaatkan harga yang lebih rendah apabila kos penyimpanan dan jalur lebar jatuh. Pada masa yang sama, ia melindungi pengguna dari kenaikan harga apabila kos sumber meningkat disebabkan oleh turun naik pasaran yang tidak dapat dielakkan. PPIO menggunakan sistem Oracle untuk membimbing penentuan harga penyimpanan dan perkhidmatan muat turun, yang membantu mengurangkan turun naik PPIO Coin supaya pengguna dan pemaju dapat menikmati ekonomi yang lebih stabil. PPIO juga menggunakan mekanisme pembayaran yang disebut Coin-Pool, yang membolehkan pengguna membeli perkhidmatan storan secara pukal. Ia membantu menjadikan sistem pembayaran lebih fleksibel dan mudah digunakan.

6.1. Peranan
Peranan berikut wujud dalam sistem storan PPIO:

Node Pengguna
Pengguna adalah pengguna sistem storan PPIO, dan mereka memperoleh perkhidmatan penyimpanan dan muat turun dengan mengambil sejumlah duit syiling PPIO.

Node Sumber
Dalam senario penggunaan PCDN, node sumber adalah nod pengguna khusus yang menerbitkan kandungan, biasanya ia tetap dalam talian dan menyediakan perkhidmatan muat turun kepada pengguna lain.

Nod Miner
Node yang menyediakan sumber penyimpanan dan jalur lebar dalam rangkaian PPIO, dan menerima Koin PPIO untuk sumbangannya.

Indexer Node
Nod yang menyediakan kedua-dua perkhidmatan pengindeksan dan penjadualan ke rangkaian, dan menerima hadiah PPIO Coin sesuai. Perkhidmatan pengindeksan mereka membantu pengguna dengan cepat mencari data yang disimpan. Perkhidmatan penjadualan mereka menguruskan storan dan muat turun data, dan juga memudahkan penghantaran kandungan dengan menyesuaikan bagaimana salinan data diedarkan dalam rangkaian.

Node Verifier
Nod yang menjalankan dan mengesahkan bukti penyimpanan dalam rangkaian, dan menerima ganjaran dengan sewajarnya. Mereka bertanggungjawab untuk mengesahkan keupayaan penyimpanan yang ada bagi penambang, mengesahkan storan dan muat turun data, mengesahkan masa penyimpanan dan lebar jalur yang berkesan.

Node Coin-Pool
Node yang menyediakan perkhidmatan pembayaran kepada pengguna, dengan lebih banyak pilihan pembayaran yang mesra untuk penyimpanan.

Mana-mana nod di atas juga boleh menyertai mekanisme konsensus PPIO dengan pilihan dan menjadi layak untuk membina blok baru pada lejar. Dengan algoritma konseptual PVFT PPIO, nodus peserta bersaing untuk menjadi pembina blok seterusnya dalam cara yang adil. Apabila nod dipilih dan berjaya membina blok seterusnya, ia juga mendapat ganjaran sewajarnya.

6.2. Perlombongan
Dalam rangkaian storan PPIO, pelombong mendapat ganjaran dengan menyediakan perkhidmatan penyimpanan atau muat turun. Selain itu, mereka juga mendapat peluang untuk menerima ganjaran perlombongan dari platform, apabila blok baru dijana pada lejar yang diedarkan.

Ganjaran perlombongan PPIO diedarkan berdasarkan sumbangan setiap pelombong, diukur dengan bukti penyimpanan. Tujuan ganjaran adalah untuk menggalakkan pelombong mengambil bahagian, menyumbang lebih banyak sumber dan menyediakan perkhidmatan yang lebih baik kepada rangkaian. PPIO membenarkan pelombong mengumpul ganjaran perlombongan dalam dua cara, koleksi tidak dijamin, dan koleksi cagaran.

Perlombongan yang tidak bercagar: Para pelombong dibenarkan mengumpul ganjaran perlombongan tanpa cukup duit syiling PPIO sebagai cagaran. Walau bagaimanapun, ganjaran yang diagihkan kepada pelombong akan didepositkan sebagai cagaran dan tidak boleh ditarik balik oleh pelombong, sehingga sejumlah deposit minimum dicapai. Kaedah ini adalah utama y direka untuk pelombong yang baru menyertai. Ia membolehkan mereka mula membina deposit dan kredit yang diperlukan semasa menyediakan perkhidmatan kepada rangkaian. Selepas jumlah minimum deposit untuk cagaran perkhidmatan dicapai dan dikekalkan, pelombong akan memulakan kutipan ganjaran perlombongan collateralized.

Perlombongan terjamin: Deposit Minit PPIO Coins sebagai cagaran dan komitmen terhadap perkhidmatan yang mereka berikan. Apabila pelombong tidak memenuhi perkhidmatan yang mereka janjikan, bukan sahaja mereka akan menjadi tidak layak untuk menerima lebih banyak hadiah perlombongan, mereka juga akan kehilangan sebahagian daripada deposit sebagai hukuman. Jumlah deposit yang dikehendaki adalah berpadanan dengan panjang perkhidmatan yang mereka mendaftar untuk menyediakan, semakin lama tempoh perkhidmatan adalah, semakin tinggi deposit akan.

Hadiah pertambangan PPIO diagihkan dengan menimbang sumbangan para pelombong. Setiap berat pelombong $ W $ diputuskan oleh bukti storan terkumpulnya, dikira dengan formula berikut:

$$ W = (\ alpha f (PoRep) + \ beta f (PoSt) + \ gamma f (PoD) + \ sigma f (LPoC)) \ cdot \ delta $$

di mana $ \ delta $ ialah parameter cagaran. Dengan mengandaikan dua pelombong mempunyai sumbangan yang sama, pelombong dengan komitmen perkhidmatan masa depan yang lebih lama akan diberikan parameter cagaran yang lebih tinggi, dan dengan itu menerima ganjaran perlombongan yang lebih tinggi.

Nilai piawai faktor skala setiap bukti adalah seperti berikut:

Parameter Penerangan Nilai Lalai
$ \ alpha $ PoRep Scaling Factor 20%
$ \ beta $ PoSt Scaling Factor 40%
$ \ gamma $ PoD Scaling Factor 30%
$ \ sigma $ LPoC Scaling Factor 10%
Semasa penggunaan awal PPIO, diharapkan jumlah transaksi yang disimpan dan transaksi akan mulai rendah. Untuk menggalakkan pelombong baru untuk menyertai rangkaian dan membuat kapasiti simpanan mereka tersedia, faktor pendorong LPoC akan dinaikkan dalam tempoh ini. Apabila volum simpanan bertambah, faktor pendorong LPoC akan dikurangkan secara beransur-ansur, sementara faktor penimbunan dari bukti penyimpanan lain akan ditingkatkan.

Apabila blok baru ditambah kepada lejar PPO yang didistribusikan, sejumlah koin PPIO dibuat sebagai hadiah. Walau bagaimanapun, nod yang membina blok tidak menerima semua ganjaran. Sebaliknya, kebanyakan ganjaran diedarkan kepada pelombong, berdasarkan berat yang dikira setiap pelombong dari sumbangan storan dan bandwidth mereka dalam tempoh masa.

Koin PPIO yang dibuat untuk blok baru diedarkan seperti berikut:

Peranan Peranan Pengedaran
Blok Pengeluar 5%
Penambang 90%
Pengesahan 4%
Indeks 1%
6.3. Kontrak Pintar
Kontrak pintar melaksanakan sendiri digunakan dalam rangkaian penyimpanan PPIO untuk mengendalikan storan atau muat turun data.

Kontrak Penyimpanan: Kontrak dicipta apabila pengguna menyimpan objek ke dalam rangkaian storan PPIO. Ia menentukan tempoh penyimpanan dan bilangan syiling PPIO yang perlu dibayar untuk perkhidmatan storan. Sebaik sahaja kontrak dilaksanakan, objek akan disimpan dalam tempoh tertentu dengan harga yang dipersetujui, tanpa mengira turun naik harga Coin PPIO pada tempoh tersebut.

Muat turun Kontrak: Kontrak dibuat apabila pengguna mahu memuat turun objek data dari rangkaian storan PPIO. Ia menentukan jumlah syiling PPIO yang akan dibayar untuk perkhidmatan tersebut. Sebaik sahaja kontrak dijalankan, para pelombong mesti menyediakan perkhidmatan dengan serta-merta untuk pengguna memuat turun data.

Kontrak penyimpanan yang dilaksanakan boleh dikemaskini oleh:

Pembaharuan Simpanan: Kontrak Penyimpanan boleh diperbaharui untuk melanjutkan tempoh penyimpanan. Sebagai contoh, tempoh penyimpanan maksimum mana-mana kontrak baru di PPIO adalah 365 hari. Tetapi lanjutan boleh dilakukan dengan memperbaharui kontrak sebelum tarikh tamat tempoh.

Penamatan Penyimpanan: PPIO membolehkan pengguna menamatkan kontrak penyimpanan sebelum tarikh tamat tempoh. Pengguna akan mendapat pulangan jumlah Kadaran PPIO yang masih belum dibelanjakan dalam kontrak.

Kemas kini Penyimpanan: PPIO membenarkan pengguna mengemaskini objek yang disimpan. Kontrak baru untuk objek yang dikemaskini akan dibuat dan dilaksanakan, dengan bayaran baru yang dibayar dalam Duit Mata Wang PPIO. Kontrak lama ditamatkan, dan Sisa PPIO yang masih dalam kontrak dikembalikan kepada pengguna.

6.4. Gas
Seperti yang ditunjukkan dalam Rajah 6.1 dan 6.2, sambil melaksanakan sama ada jenis kontrak pintar, PPIO menghantar pelombong dan nod lain untuk menyediakan perkhidmatan dan memberi ganjaran kepada mereka dengan sewajarnya. PPIO mengadaptasi Gas sebagai unit untuk mengukur sumbangan setiap nod dalam memenuhi kontrak tertentu. Akhirnya, setiap nod akan menerima Koin PPIO pada jumlah yang berdasarkan bilangan unit Gas. Jumlah Sumbangan PPIO yang pengguna membayar setiap unit Gas dalam kontrak ini dipanggil Harga Gas.

Urus niaga gas di antara nod yang berbeza semasa melaksanakan kontrak penyimpanan dan muat turun diterangkan di bawah.

Kontrak Penyimpanan
Pengguna membayar Gas untuk menyimpan setiap objek, dalam jumlah $ G_ {u} $.
Verifier menerima Gas untuk menjalankan Bukti Masa Angkasa (PoSt), dalam jumlah $ G_ {post} $.
Penambang menerima Gas untuk menyediakan masa ruang penyimpanan semasa tempoh penyimpanan, dalam jumlah $ G_ {st} $.
Urus niaga boleh dirumuskan sebagai:

$ G_ {u} = \ sum G_ {st} + \ sum G_ {post} $

$ \ sum G_ {st} = N_ {Salinan}
\ cdot G_ {st} $

$ \ sum G_ {post} = N_ {Verifier} \ cdot G_ {post} $

Di mana $ N_ {Salin} $ ialah bilangan salinan yang disimpan, dan $ N_ {Verifier} $ adalah bilangan pengesah yang terlibat.

Apabila operasi storan berlaku, penambang perlu membuat pembayaran Gas $ G_ {l} $ untuk mendapatkan satu salinan data. Penambang berbuat begitu kerana ia dapat menerima lebih banyak pembayaran di masa depan untuk menyimpan data dan menyediakan perkhidmatan muat turun semasa tempoh penyimpanan. $ G_ {rep} $ adalah jumlah Gas penambang yang membayar kepada penambang lain untuk mendapatkan satu salinan objek data. $ G_ {porep} = N_ {Verifier} \ cdot G_ {porep} $, yang merupakan jumlah penambang Gas yang dibayar kepada Verifier untuk menjalankan Bukti Replikasi (PoRep). $ G_ {jadual} $ adalah jumlah Gas pelombong yang membayar kepada Indeks untuk penjadualan salinan data. Jumlah penambang yang dibayar adalah $ G_ {l} = G_ {rep} + G_ {porep} + G_ {jadual} $

fail dimuatnaik

Rajah 6.1 Pelaksanaan Kontrak Penyimpanan

Muat turun Kontrak:
Pengguna membayar Gas untuk memuat turun objek data, dalam jumlah $ G_ {u} $.
Miner menerima Gas untuk data yang dimuat turun dari storannya, semakin banyak data yang dimuat turun, lebih besar jumlah Gas $ G_ {d} $ akan diterima.
Indekser menerima Gas untuk menyediakan perkhidmatan penjadualan, dalam jumlah $ G_ {index} $.
Verifier menerima Gas untuk menjalankan Bukti Muat turun (PoD), dalam jumlah $ G_ {pod} $.
Urus niaga boleh dirumuskan sebagai:

$ G_ {u} = \ sum G_ {d} + \ sum G_ {pod} + G_ {index} $
object_download

Rajah 6.2 Pelaksanaan Kontrak Muat Turun

Pengguna membayar Koin PPIO di hadapan penuh dalam urus niaga ini, tetapi pelombong menerima Duit PPIO secara beransur-ansur kerana mereka menyediakan perkhidmatan tersebut. Semasa tempoh penyimpanan, sekiranya penambang berjalan di luar talian atau berhenti menyediakan perkhidmatan, Indekser akan mencari penambang lain yang tersedia untuk menyimpan salinan data, untuk mengekalkan tahap redundansi data dalam rangkaian. Pada ketika ini, pelombong baru akan mula menerima Duit Syiling PPIO untuk menyimpan salinan itu, manakala pelombong sebelumnya akan berhenti menerima pembayaran selanjutnya.

6.5. Harga Gas
Nisbah untuk menukar Gas ke dalam PPIO Coin diputuskan oleh Harga Gas dalam setiap kontrak. Bilangan syiling PPIO yang akan dibayar untuk kontrak dikira seperti berikut:

$ PPIO Coin = GasPrice \ cdot Gas $

$ PPIO Coin $ adalah jumlah duit syiling PPIO yang pengguna bersedia membayar ketika membuat kontrak. Gas adalah jumlah unit gas yang diperlukan untuk melaksanakan kontrak.

Seperti yang dibincangkan dalam seksyen 6.3, kontrak pintar boleh dikemas kini selepas pelaksanaan, dan kontrak baru boleh diwujudkan. Setiap kali kontrak dibuat atau dikemaskini, Harga Gasnya perlu diputuskan. Jumlah Gas yang akan dibelanjakan ditentukan oleh jenis kontrak. Contohnya, jumlah gas untuk kontrak simpanan ditentukan oleh saiz data yang akan disimpan, bilangan salinan yang akan dibuat dan tempoh penyimpanan. Dengan jumlah duit syiling PPIO pengguna bersedia untuk membayar kontrak, Harga Gasnya boleh dikira menggunakan formula di atas. Selepas kontrak diterima dan dilaksanakan, jumlah Gas diagihkan kepada nod yang terlibat dalam pelaksanaan kontrak berdasarkan sumbangan mereka. Setiap nod akan menerima jumlah Duit Pusingan PPIO yang dikira dengan menggunakan nilai Harga Gas yang diputuskan sebelum ini untuk kontrak.

Harga Gas adalah kunci untuk kontrak diterima di pasaran. Sebagai contoh, proses memadankan kontrak simpanan adalah untuk mencari pelombong yang cukup yang sanggup menerima Harga Gas dalam kontrak, supaya ia dapat dilaksanakan. Semakin tinggi Harga Gas, semakin mudah dan cepat untuk mencari penambang cukup untuk menyimpan data. Jika tidak, jika Harga Gas terlalu rendah, kontrak itu tidak boleh dilaksanakan.

Selain daripada kebanyakan aplikasi lain, masa pelaksanaan kontrak penyimpanan biasanya lebih lama. Sebagai contoh, pengguna boleh menyimpan sekeping data selama setahun. Pada masa itu, harga PPIO Coin dapat berubah dengan ketara, dan ketidakpastian seperti itu meningkatkan risiko bagi pengguna dan pelombong. PPIO menggunakan Oracle Harga Gas untuk membantu mengurangkan ketidakpastian, dan mengekalkan ekonomi yang lebih stabil dan adil.

Oracle mengira dan menyediakan Harga Gas Platform. Diharapkan bahawa pada Harga Gas Platform, majoriti kontrak mestilah dapat mencari perlawanan. Harga dikira dengan mengambil kira sejarah transaksi keseluruhan rangkaian, turun naik harga PPIOCoin, dan trend penyimpanan dan kos jalur lebar di pasaran luar. Sebagai contoh, kos penyimpanan dan sumber jalur lebar dijangka akan turun secara beransur-ansur melalui masa, di bawah keadaan biasa. Oleh itu untuk kontrak penyimpanan dengan tempoh penyimpanan yang berpanjangan, Oracle cenderung untuk menyediakan Harga Gas Platform yang lebih rendah.

Harga Gas Platform adalah harga rujukan. Setiap pengguna dan pelombong boleh memutuskan sama ada ia adalah harga yang boleh diterima untuk kontrak berdasarkan keadaan mereka, dan mereka boleh mencadangkan harga yang berbeza apabila diperlukan. Memandangkan Oracle mengambil kira transaksi dalam platform, ia berfungsi sebagai panduan yang baik dan membantu menstabilkan harga dalam sistem.

Oleh kerana PPIO adalah satu penipuan
sistem ntralized, pelaksanaan Oracle juga didesentralisasi. Nod berganda dalam rangkaian boleh memenuhi fungsi Oracle, dan mekanisme konsensus juga digunakan untuk memastikan kebolehpercayaannya.

6.6. Coin-Pool
Setiap transaksi perlu mengambil sejumlah Gas untuk menggalakkan nod yang berbeza dalam rangkaian untuk menyertai. Walau bagaimanapun, jika setiap urus niaga memerlukan pengguna untuk membuat mikrofon individu, pengalaman pengguna akan dihina, kerana mereka perlu mengendalikan terlalu banyak pembayaran. Selain itu, memikirkan Harga Gas yang betul untuk setiap transaksi juga menjadi beban kepada kebanyakan pengguna. Oleh itu, aplikasi mungkin memberikan lebih banyak pilihan pembayaran yang mesra kepada pengguna. Sebagai contoh, aplikasi pemacu rangkaian mungkin ingin menyediakan pakej storan yang membolehkan pengguna membuat bayaran pendahuluan untuk kuota storan tertentu untuk tempoh (sebagai contoh, simpanan 6 bulan 200 GB). Pengguna tidak perlu membuat mikrofon tambahan untuk menyimpan atau memuat turun data di bawah kekangan ini.

PPIO menyelesaikan masalah ini dengan memperkenalkan nod unik yang dikenali sebagai Coin-Pool. Setiap Coin-Pool adalah entiti perniagaan individu yang bertanggungjawab ke atas keuntungan dan kerugiannya. Pengguna atau pemaju mendaftar dan membeli perkhidmatan yang disediakan oleh Coin-Pool, seperti pakej penyimpanan. Sebaik sahaja perjanjian dicapai, Coin-Pool akan mengendalikan semua bayaran bagi pihak pengguna, apabila mereka menggunakan mana-mana perkhidmatan PPIO yang termasuk dalam pakej yang mereka beli.



Rajah 6.3 Coin-Pool

Coin-Pool mempunyai ciri-ciri berikut:

Pengguna membayar sejumlah duit syiling PPIO yang dipersetujui ke Coin-Pool apabila mereka membeli pakej perkhidmatan.
Coin-Pool membuat pembayaran bagi setiap transaksi pengguna dalam rangkaian PPIO, berdasarkan syarat perkhidmatan yang dipersetujui. Operasi penyimpanan dan muat turun masih sepenuhnya dicetuskan dan dikendalikan oleh pengguna.
Untuk mengekalkan kebolehpercayaan sistem sedemikian, Coin-Pool perlu menyimpan sejumlah duit syiling PPIO sebagai cagaran, sebelum dapat melayani pengguna. Sekiranya Coin-Pool gagal untuk memenuhi liabiliti ejennya, depositnya boleh dirampas. Coin-Pool mungkin tidak lagi layak untuk menyediakan perkhidmatan, dan kontrak pengguna dan perkhidmatan sedia ada boleh diambil alih oleh Coin-Pool yang layak.
Maklumat yang diperlukan untuk semua Coin-Pools dalam rangkaian dijadikan umum supaya pengguna boleh dimaklumkan apabila memilih Coin-Pool untuk diri mereka sendiri. Maklumat yang diterbitkan termasuk jumlah Koin PPIO yang didepositkan oleh Coin-Pool, jumlah Koin PPIO yang dipegang Coin-Pool untuk pengguna, dan jumlah pengguna mendaftar untuk perkhidmatannya.
PPIO menyediakan satu set API untuk membangun Coin-Pool, untuk membolehkan pengendalian pembayaran untuk transaksi pengguna.
Pemaju syiling-Pool boleh membangunkan gerbang pembayaran yang membolehkan pengguna membuat pembayaran dalam mata wang fiat, serta mata wang kriptografi yang lain. Ia membantu membuat perkhidmatan sedemikian dapat diakses oleh lebih banyak pengguna.
Coin-Pool adalah entiti perniagaan yang bertanggungjawab ke atas keuntungan dan kerugiannya. Persaingan di antara Coin-Pools yang berbeza boleh membuat harga lebih terjangkau oleh pengguna, dan membantu mengekalkan ekonomi keseluruhan yang lebih sihat dalam rangkaian storan PPIO.
7. Masa Depan
Penyimpanan panas dan penarafan penyimpanan sejuk
Kandungan penyimpanan biasanya dikategorikan dalam Storan Panas dan Penyimpanan Sejuk. Penyimpanan panas adalah data yang anda perlu akses segera, di mana prestasi berada di premium (seperti laman berita); Penyimpanan sejuk adalah maklumat yang anda tidak perlu akses sangat kerap. Data tidak aktif tidak perlu diakses untuk tempoh yang lama adalah jenis kandungan yang penyimpanan sejuk sesuai untuk (seperti penyimpanan data). Kedua-dua keadaan ini berbeza mengenai penyimpanan dan kecekapan jalur lebar rangkaian. Kami mungkin akan melaksanakan dua reka bentuk yang berbeza pada masa hadapan untuk penyelesaian penyimpanan dalam ekosistem kami untuk menggunakan lebih banyak ruang storan dan jalur lebar;

Pecutan VCDN
Untuk kes penggunaan seperti streaming video langsung yang memerlukan pecutan penghantaran kandungan secara besar-besaran, nod dengan lebar jalur berkualiti tinggi lebih disukai berbanding kapasiti penyimpanan. Kami akan memperkenalkan satu set reka bentuk pecutan PCDN untuk menggunakan sumber jalur lebar untuk keperluan tersebut. Penyelesaian itu akan membawa hasil yang lebih tinggi untuk nod yang telah habis semua sumber simpanan mereka semasa memenuhi permintaan untuk peningkatan jalur lebar;

Lebih banyak idea
Apabila ekosistem terbentuk daripada urus niaga antara bekalan dan permintaan storan, kami percaya rangkaian nilai berasaskan simpanan dicipta. Penilaian harga dibuat terbuka dan telus pada rangkaian untuk setiap fail yang dimuat turun atau diakses, dengan cara ekosistem membantu menilai setiap nilai kandungan yang berkaitan. Ini menandakan era rangkaian nilai yang akan datang. PPIO akhirnya menyediakan satu sistem data besar untuk penyelesaian penyimpanan yang paling selamat dan dilindungi untuk semua aplikasi dan inovasi atas, membawa AI lebih dekat, dan membina masa depan yang lebih bijak dan lebih baik untuk kita semua.





