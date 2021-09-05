Nama  : Muhammad Takdim  
NIM   : H071191042  

# Clustering  
*Clustering* adalah sebuah proses untuk mengelompokan data ke dalam beberapa *cluster* atau kelompok sehingga data dalam satu *cluster* memiliki tingkat kemiripan yang maksimum dan data antar *cluster* memiliki kemiripan yang minimum.*Clustering* banyak digunakan dalam berbagai aplikasi seperti misalnya pada *business intelligence*, pengenalan pola citra, *web search*, bidang ilmu biologi, dan untuk keamanan (*security*). Di dalam *business intelligence*, clustering bisa mengatur banyak customer ke dalam banyaknya kelompok.  
Adapun syarat sekaligus tantangan yang harus dipenuhi oleh suatu algoritma *clustering* yaitu Skalabilitas, yaitu suatu metode *clustering* harus mampu menangani data dalam jumlah yang besar. Saat ini data dalam jumlah besar sudah sangat umum digunakan dalam berbagai bidang misalnya saja suatu database. Tidak hanya berisi ratusan objek, suatu database dengan ukuran besar bahkan berisi lebih dari jutaan objek.  

## K-Means  
K-means merupakan algoritma *clustering*. K-means *Clustering* adalah salah satu “*unsupervised machine learning algorithms*” yang paling sederhana dan populer. K-Means *Clustering* adalah suatu metode penganalisaan data atau metode *Data Mining* yang melakukan proses pemodelan tanpa *supervisi* (*unsupervised*) dan merupakan salah satu metode yang melakukan pengelompokan data dengan sistem partisi.  
Data *clustering* menggunakan metode K-Means *Clustering* ini secara umum dilakukan dengan algoritma dasar sebagai berikut:  
1. Tentukan jumlah *cluster*  
2. Alokasikan data ke dalam *cluster* secara random  
3. Hitung *centroid*/rata-rata dari data yang ada di masing-masing *cluster*  
4. Alokasikan masing-masing data ke *centroid*/rata-rata terdekat  
5. Kembali ke Step 3, apabila masih ada data yang berpindah *cluster* atau apabila perubahan nilai *centroid*, ada yang di atas nilai *threshold* yang ditentukan atau apabila perubahan nilai pada *objective function* yang digunakan di atas nilai *threshold* yang ditentukan  
Beberapa permasalahan yang sering muncul pada saat menggunakan metode K-Means untuk melakukan pengelompokan data adalah:  
1. Ditemukannya beberapa model *clustering* yang berbeda  
2. Pemilihan jumlah *cluster* yang paling tepat  
3. Kegagalan untuk *converge*  
4. *Outliers*  

## K-Medoids
K-Medoids atau *Partitioning Around Method* (*PAM*) adalah metode *cluster* non hirarki yang merupakan varian dari metode K-Means. K-Medoids hadir untuk mengatasi kelemahan K-Means yang sensitif terhadap *outlier* karena suatu objek dengan suatu nilai yang besar mungkin secara substansial menyimpang dari distribusi data (Jiawei & Kamber, 2006). K-Medoids menggunakan metode pengelompokan partisi untuk mengelompokan sekumpulan n objek menjadi sejumlah *k cluster*. Algoritma ini menggunakan objek pada kumpulan objek yang mewakili sebuah *cluster*. Objek yang mewakili sebuah *cluster* disebut dengan *medoids*.  
Tahapan-tahapan K-Medoids:  
1. Tentukan k (jumlah *cluster*) yang diinginkan.  
2. Pilih secara acak medoid awal sebanyak *k* dari *n* data.  
3. Hitung jarak masing-masing obyek ke *medoid* sementara, kemudian tandai jarak terdekat obyek ke *medoid* dan hitung totalnya.  
4. Lakukan iterasi *medoid*.  
5. Hitung total simpangan (S).  
Jika *a* adalah jumlah jarak terdekat antara obyek ke medoid awal, dan *b* adalah jumlah jarak terdekat antara obyek ke medoid baru, maka total simpangan adalah *S = b — a*  
Jika *S < 0*, maka tukar obyek dengan data untuk membentuk sekumpulan *k* baru sebagai medoid.  
6. Ulangi langkah 3 sampai 5 dan hentikan jika sudah tidak terjadi perubahan anggota *medoid*.

## Hierarchical Clustering  
*Hierarchical methods* adalah teknik *clustering* membentuk hirarki atau berdasarkan tingkatan tertentu sehingga menyerupai struktur pohon. Dengan demikian proses pengelompokannya dilakukan secara bertingkat atau bertahap. Biasanya, metode ini digunakan pada data yang jumlahnya tidak terlalu banyak dan jumlah *cluster* yang akan dibentuk belum diketahui.  
Dalam *agglomerative method*, teknik pengelompokan yang paling dikenal adalah:  
1. *Single linkage* (jarak terdekat atau tautan tunggal)  
Teknik yang menggabungkan *cluster-cluster* menurut jarak antara anggota-anggota terdekat di antara dua *cluster*.  
2. *Average linkage* (jarak rata-rata atau tautan rata-rata)  
Teknik yang menggabungkan *cluster-cluster* menurut jarak rata-rata pasangan anggota masing-masing pada himpunan antara dua *cluster*.  
3. *Complete linkage* (jarak terjauh atau tautan lengkap)  
Teknik yang menggabungkan *cluster-cluster* menurut jarak antara anggota-anggota terjauh di antara dua *cluster*.  
Berikut adalah algoritma cluster hirarki agglomerative:  
1. Hitung matriks jarak.  
2. Gabungkan dua *cluster* terdekat.  
3. Perbarui matriks jarak sesuai dengan teknik pengelompokan *agglomerative method*.
4. Ulangi langkah 2 dan 3 sampai hanya tersisa satu cluster.  
5. 5. Buat *Dendogram*.  


## DB SCAN  
*Algoritma Density-based Spatial Clustering of Application with Noise (DBSCAN)* merupakan metode *clustering* yang berbasis kepadatan (*density-based*) dari posisi amatan data dengan prinsip mengelompokkan data yang relatif berdekatan. DBSCAN sering diterapkan pada data yang banyak mengandung *noise*, hal ini dikarenakan DBSCAN tidak akan memasukkan data yang dianggap *noise* kedalam *cluster* manapun.  
Dalam proses pembuatan *cluster* menggunakan DBSCAN sebuah data akan dikelompokkan dengan tetangganya. Sepasang amatan dikatakan bertetangga apabila jarak antara dua amatan tersebut kurang dari sama dengan nilai *epsilon*. Secara sederhana cara kerja DBSCAN adalah sebagai berikut :
1. Tentukan nilai minPts dan epsilon (eps) yang akan digunakan.
2. Pilih data awal “p” secara acak.
3. Hitung jarak antara data “p” terhadap semua data menggunakan *Euclidian distance*.
4. Ambil semua amatan yang *density-reachable* dengan amatan “*p*”.
5. Jika amatan yang memenuhi nilai *epsilon* lebih dari jumlah minimal amatan dalam satu gerombol maka amatan “*p*” dikategorikan sebagai *core points* dan gerombol terbentuk.
6. Jika amatan “p” adalah border points dan tidak ada amatan yang density-reachable dengan amatan “*p*”, maka lanjutkan pada amatan lainnya.
7. Ulangi langkah 3 sampai 6 hingga semua amatan diproses.
