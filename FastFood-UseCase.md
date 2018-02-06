## Use Case Diagram

Berdasarkan *features* yang telah di-design, dibuatkan diagram *use case*.

1. Login

   **Description**

   User masuk ke sistem untuk tujuan meng-establish identitas user di dalam sistem (untuk keperluan pencatatan dan akuntibilitas).

   Seluruh fungsi sistem hanya dapat digunakan apabila user sudah login ke dalam sistem.

   **Normal Flow**

   1. User menyalakan aplikasi Order
   2. Aplikasi Order menampilkan halaman login
   3. User memasukkan user dan password untuk login ke sistem
   4. Sistem memeriksa user dan password, apabila valid dan masih aktif, user akan di-login-kan ke sistem
   5. User sudah dapat menggunakan aplikasi Order

   **Alternative Flow**

   User salah memasukkan user/password

   1. User memasukkan user/password yang salah
   2. Sistem menampilkan pesan kesalahan dan menunggu user untuk memasukkan user dan password lagi
   3. Ulangi proses normal flow langkah ke 2.

   User lupa usernama/password
   1. Sistem menampilkan pilihan Forgot Password
   2. Password baru akan dikirim melalui email atau no telepon yg terdaftar oleh user

2. Logout

   **Description**

   User keluar dari sistem. Setiap user berkewajiban untuk logout dari sistem apabila sudah selesai menggunakan sistem.

   **Preconditions**

   User dalam keadaan login di sistem.

   **Normal Flow**

   User mengakses menu logout atau menekan tombol close pada aplikasi Order
   Sistem meng-logout user

3. Add User (Developer)

   **Description**
   
   Menambahkan user baru ke dalam sistem.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.

   **Normal Flow**
   
   1. User membuka menu user management dan menekan tombol add untuk menambahkan user baru.
   2. Sistem menampilkan form pendaftaran user baru
   3. User menginput data user baru:
      
      - nama lengkap
      - nama user
      - password & password verification
      - jenis user (kasir/manajemen)
      - optional mengupload foto
      
      dan menekan tombol save untuk menyimpan data user
      
   4. Sistem memeriksa validitas data user baru, menyimpan informasi user ke databse dan menampilkan pesan notifikasi
      ke user bahwa user sudah tersimpan.
      
4. Remove User (Developer)

   **Description**
   
   Meng-nonaktifkan user. User yang sudah di-nonaktifkan tidak dapat login ke dalam sistem.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.
   
   **Normal Flow**
   
   1. User membuka menu user management dan memilih account user yang akan dinonaktifkan.
   2. Sistem menampilkan form tampilan informasi account user.
   3. User menekan tombol non-aktif untuk meng-nonaktifkan user.
   4. Sistem mengupdate status keaktifan user ke database.
   
   Untuk mengaktifkan kembali user, lakukan flow yang sama.

5. Update user account (Developer)

   **Description**
   
   Mengubah informasi mengenai user, misalnya nama lengkap atau password.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.
   
   **Normal Flow**
   
   1. User membuka menu user management dan memilih account user yang akan di-update.
   2. Sistem menampilkan form tampilan informasi account user.
   3. User mengupdate informasi user dan menekan tombol save.
   4. Sistem menyimpan perubahan account user ke database.
   
6. Add Product (Developer)

   **Description**
   
   Menambahkan product baru ke dalam sistem.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.

   **Normal Flow**
   
   1. User membuka menu product management dan menekan tombol add untuk menambahkan product baru.
   2. Sistem menampilkan form pendaftaran product baru
   3. User menginput data product baru:
      
      - kode product
      - nama product
      - harga product
      - jenis product
      - optional mengupload foto
      
      dan menekan tombol save untuk menyimpan data product
      
   4. Sistem memeriksa validitas data product baru, menyimpan informasi product ke databse dan menampilkan pesan
      notifikasi ke user bahwa data sudah tersimpan.
      
7. Remove Product (Developer)

   **Description**
   
   Meng-nonaktifkan product. Product yang sudah di-nonaktifkan tidak akan dimunculkan pada saat pelanggan melakukan
   order.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.
   
   **Normal Flow**
   
   1. User membuka menu product management dan memilih product yang akan dinonaktifkan.
   2. Sistem menampilkan form tampilan informasi product.
   3. User menekan tombol non-aktif untuk meng-nonaktifkan product.
   4. Sistem mengupdate status keaktifan product ke database.
   
   Untuk mengaktifkan kembali product, lakukan flow yang sama.

8. Update Product (Developer)

   **Description**
   
   Mengubah informasi mengenai product, misalnya harga atau foto product.
   
   **Precondition**
   
   User sudah login sebagai user manajemen.
   
   **Normal Flow**
   
   1. User membuka menu product management dan memilih product yang akan di-update.
   2. Sistem menampilkan form tampilan informasi product.
   3. User mengupdate informasi product dan menekan tombol save.
   4. Sistem menyimpan perubahan account product ke database.
   
9. Order Food

   **Description**
   
   User akan melakukan orderan dengan menu/pilihan yang tersedia

   **Preconditions**
   
   User sudah dalam keadaan log in di dalam sistem

   **Normal Flow**
   1. User mengakses Menu / pilihan yang tersedia dalam home page
   2. User memilih Menu makanan yg tersedia di Menu
   3. Setelah memilih menu makanan yang akan dipesan, user memasukaan metode pengantaran apakah Takeaway / Delivery
   4. Apabila user memilih metode takeaway makan user akan memilih restoran tempat pengambilan makanan 
5. Apabila user memilih metode Delivery, maka user akan memasukkan alamat yang diinginkan
6. Kemudian user akan memilih metode pembayaran yang tersedia
7. Orderan akan diproses dan dikonfirmasi oleh sistem

   **Alternative Flow**
   
   Apabila orderan tidak dapat diproses atau menu yg dipesan tidak tersedia maka user akan dihubungi oleh sistem untuk dilakukan konfirmasi orderan
   
10. Payment

    **Description**
    
    Pelanggan membayar pesanan.
    
    **Precodition**
    
    User sudah masuk ke dalam sistem sebagai pelanggan.
    Orderan pelanggan sudah disimpan oleh sistem (order valid).
    
    **Normal Flow**
    
    1. Sistem meminta pembayaran kepada pelanggan sesuai dengan total tagihan dari e-money/ kartu kredit/ kartu debit.
	   Kemudian memberikan informasi pembayaran.
    2. Sistem merekam informasi pembayaran dan kemudian mencetak faktur order dan pembayaran.
    3. Sistem menginformasikan ke staff di Fast Food Restaurant untuk membuat pesanan sesuai dengan faktur order dan pembayaran.
	4. Sistem menginformasikan ke staff bahwa orderan merupakan delivery atau take away.
	   
11. Report POS

    **Description**
    
    Menampilkan summary transaksi POS berdasarkan kriteria tertentu.
    
    **Precondition**
    
    User sudah login sebagai user manajemen.
   
    **Normal Flow**
   
    1. User mengakses menu laporan dan memilih laporan POS.
    2. Sistem menampilkan form untuk menerima input kriteria laporan.
    3. User menginput kriteria laporan dan mengklik tombol report.
    4. Sistem mengolah data report dan kemudian menampilkan laporan kepada user.
   
12. Report History

    **Description**
    
    Menampilkan summary transaksi pelanggan berdasarkan kriteria tertentu.
    
    **Precondition**
    
    User sudah login sebagai user.
   
    **Normal Flow**
   
    1. User mengakses menu history dan memilih history pemesanan
    2. Sistem menampilkan form untuk menerima input kriteria laporan.
    3. User menginput kriteria laporan dan mengklik tombol report.
    4. Sistem mengolah data report dan kemudian menampilkan laporan kepada user.
	


   
