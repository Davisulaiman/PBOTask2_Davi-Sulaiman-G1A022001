# PBOTask2
1.Implementasikan kelas Mahasiswa, Jurusan dan Universitas sesuai dengan spesifikasi yang diberikan.
class Mahasiswa: #kelas mahasiswa
    def __init__(self, nama, nim, jurusan): #fungsi parameter nama dan jurusan
        self.nama = nama #string nama
        self.nim = nim #string nim
        self.jurusan = jurusan #string jurusan

    def tampilkan_info(self):  #method untuk menampilkan informasi
        print("Nama:", self.nama) # untuk mencetak nama
        print("NIM:", self.nim) #untuk mencetak nim
        print("Jurusan:", self.jurusan.NamaJurusan) #untuk mencetak jurusan

class Jurusan: #kelas jurusan
    def __init__(self, nama_jurusan): #fungsi parameter nama dan jurusan
        self.NamaJurusan = nama_jurusan #insisalisasi atribut NamaJurusan untuk kode program
        self.DaftarMahasiswa = [] # daftar kosong unutk menyimpan nama mahasiswa

    def tambah_mahasiswa(self, mahasiswa): # fungsi menambahkan objek Mahasiswa ke dalam daftar mahasiswa di objek Jurusan.
        self.DaftarMahasiswa.append(mahasiswa) #insialisasi daftar mahasiswa

    def tampilkan_daftar_mahasiswa(self): #mencetak judul "Daftar Mahasiswa di <nama_jurusan>" menggunakan self.NamaJurusan
        print("Daftar Mahasiswa di", self.NamaJurusan) #Mencetak daftar mahasiswa
        for mahasiswa in self.DaftarMahasiswa: #iterasi melalui objek mahasiswa yang di daftar mahasiswa
            mahasiswa.tampilkan_info() #mencetak informasi tampilkan info mahasiswa

class Universitas: #kelas universitas
    def __init__(self, nama_universitas):#konstruktor kelas Universitas yang digunakan untuk menginisialisasi objek Universitas.
        self.NamaUniversitas = nama_universitas #insialisasi atribut nama universitas
        self.DaftarJurusan = [] #daftar kosong untuk nama jurusan 

    def tambah_jurusan(self, jurusan): #fungsi ini sebagai parameter menambah jurusan
        self.DaftarJurusan.append(jurusan) #berfungsi sebagai menambah objek jurusa

    def tampilkan_daftar_jurusan(self): #digunakan untuk menampilkan daftar jurusan
        print("Daftar Jurusan di", self.NamaUniversitas) #print daftar jurusan
        for jurusan in self.DaftarJurusan: #iterasi objek dalam jurusan
            print(jurusan.NamaJurusan) #mencetak nama jurusan

    @staticmethod #sebagai mendeklarasikan metode sebagai metode statis dalam sebuah kelas
    def cari_jurusan(nama_jurusan, universitas): #digunakan untuk menampilkan nama jurusan dan universitas
        for jurusan in universitas.DaftarJurusan: #melakukan iterasi melalui setiap objek jurusan dalam daftar jurusan (universitas.DaftarJurusan) yang ada dalam objek universitas.
            if jurusan.NamaJurusan.lower() == nama_jurusan.lower(): #berfungsi sebagai emeriksaan ini dilakukan dengan membandingkan kedua string dalam format yang sama yaitu dengan mengubahnya menjadi lowercase menggunakan metode lower()
                return jurusan #bila fungsi ini akan mengulang program jika ada kecocokan, program akan langsung mengembalikan objek
        return None #ini tidak ditemukan jurusan dengan nama yang sesuai, maka program akan mengembalikan fungsi program tersebut

    @staticmethod #sebagai mendeklarasikan metode sebagai metode statis dalam sebuah kelas
    def cari_mahasiswa(nama_mahasiswa, jurusan):#digunakan untuk menampilkan nama mahasiswa dan jurusan
        for mahasiswa in jurusan.DaftarMahasiswa: #melakukan iterasi melalui setiap objek jurusan dalam daftar jurusan (jurusan.DaftarMahasiswa) yang ada dalam objek universitas.
            if mahasiswa.nama.lower() == nama_mahasiswa.lower():##berfungsi sebagai pemeriksaan ini dilakukan dengan membandingkan kedua string dalam format yang sama yaitu dengan mengubahnya menjadi lowercase menggunakan metode lower()
                return mahasiswa #bila fungsi ini akan mengulang program jika ada kecocokan, program akan langsung mengembalikan objek
        return None#ini tidak ditemukan nama mahasiswa dengan nama yang sesuai, maka program akan mengembalikan fungsi program tersebut

# Membuat objek Universitas dengan nama "XYZ University"
universitas_xyz = Universitas("XYZ University")

# Membuat objek Jurusan dengan nama "Teknik Informatika" dan tambahkan ke dalam Universitas XYZ
jurusan_ti = Jurusan("Teknik Informatika") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ti) #membuat objek jurusan pada universitas

# Membuat objek Mahasiswa dengan nama "Davi Sulaiman", NIM "G1A022001", dan masukkan ke dalam Jurusan Teknik Informatika di Universitas XYZ
mahasiswa_davi = Mahasiswa("Davi Sulaiman", "G1A022001", jurusan_ti) #membuat objek untuk nama dan nim
jurusan_ti.tambah_mahasiswa(mahasiswa_davi) #menambahkan objek ke dalam jurusan di universitas

# Menambahkan Jurusan Teknik Sipil
jurusan_ts = Jurusan("Teknik Sipil")#menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ts) #membuat objek jurusan pada universitas

# Menambahkan Mahasiswa Fadli ke Jurusan Teknik Sipil di Universitas XYZ
mahasiswa_fadli = Mahasiswa("Fadli", "G1B022002", jurusan_ts) #membuat objek untuk nama dan nim
jurusan_ts.tambah_mahasiswa(mahasiswa_fadli)#menambahkan objek ke dalam jurusan di universitas

# Menambahkan Jurusan Teknik Mesin
jurusan_tm = Jurusan("Teknik Mesin")#menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_tm) #membuat objek jurusan pada universitas

# Menambahkan Mahasiswa Ranes ke Jurusan Teknik Mesin di Universitas XYZ
mahasiswa_ranes = Mahasiswa("Ranes", "G1C022003", jurusan_tm) #membuat objek untuk nama dan nim
jurusan_tm.tambah_mahasiswa(mahasiswa_ranes)#menambahkan objek ke dalam jurusan di universitas

# Menambahkan Jurusan Teknik Elektro
jurusan_te = Jurusan("Teknik Elektro") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_te) #membuat objek jurusan pada universitas

# Menambahkan Mahasiswa Rama ke Jurusan Teknik Elektro di Universitas XYZ
mahasiswa_rama = Mahasiswa("Rama", "G1D022004", jurusan_te) #membuat objek untuk nama dan nim
jurusan_te.tambah_mahasiswa(mahasiswa_rama)#menambahkan objek ke dalam jurusan di universitas

# Menambahkan Jurusan Arsitektur
jurusan_ar = Jurusan("Arsitektur") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ar) #membuat objek jurusan pada universitas

# Menambahkan Mahasiswa Risma ke Jurusan Arsitektur di Universitas XYZ
mahasiswa_risma = Mahasiswa("Risma", "G1E022005", jurusan_ar) #membuat objek untuk nama dan nim
jurusan_ar.tambah_mahasiswa(mahasiswa_risma)#menambahkan objek ke dalam jurusan di universitas

# Menambahkan Jurusan Sistem Informasi
jurusan_si = Jurusan("Sistem Informasi") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_si) #membuat objek jurusan pada universitas

# Menambahkan Mahasiswa Ajeng ke Jurusan Sistem Informasi di Universitas XYZ
mahasiswa_ajeng = Mahasiswa("Ajeng", "G1F022006", jurusan_si) #membuat objek untuk nama dan nim
jurusan_si.tambah_mahasiswa(mahasiswa_ajeng)#menambahkan objek ke dalam jurusan di universitas

while True: #program ini mengginakan loop untuk berjalan terus menerus hingga pengguna memilih untuk keluar
    print("\nPilih opsi:") #Mencetak untuk menampilkan pilih opsi 
    print("1. Tampilkan Daftar Jurusan")# untuk opsi 1 mencetak daftar jurusan
    print("2. Cari Mahasiswa")#untuk mencetak opsi 2 cari mahasiswa
    print("0. Keluar") #untuk mencetak opsi keluar

    opsi = input("Masukkan opsi: ") #untuk menginput opsi 

    #Jika opsi yang dipilih adalah "1", maka program akan memanggil metode tampilkan_daftar_jurusan() pada objek universitas_xyz untuk menampilkan daftar jurusan yang ada di universitas.
    if opsi == "1":
        # Menampilkan daftar jurusan yang ada di Universitas XYZ
        universitas_xyz.tampilkan_daftar_jurusan()

    #Jika opsi yang dipilih adalah "2", maka program akan meminta pengguna untuk memasukkan nama jurusan yang ingin dicari.
    elif opsi == "2":
        nama_jurusan_dicari = input("Masukkan nama jurusan yang ingin Anda cari: ")
        jurusan_dicari = Universitas.cari_jurusan(nama_jurusan_dicari, universitas_xyz)

        #Jika jurusan ditemukan, program akan memanggil metode tampilkan_daftar_mahasiswa() pada objek jurusan yang ditemukan untuk menampilkan daftar mahasiswa dalam jurusan tersebut.
        if jurusan_dicari:
            jurusan_dicari.tampilkan_daftar_mahasiswa()
        
        #Jika jurusan tidak ditemukan, program akan mencetak pesan "Jurusan tidak ditemukan." 
        else:
            print("Jurusan tidak ditemukan.")

    #Jika opsi yang dipilih adalah "0", program akan keluar dari loop while dan program akan selesai.
    elif opsi == "0":
        break #ia akan berhenti jika opsi ditemukan maka akan ke program selesai

    #Jika opsi yang dipilih tidak valid, program akan mencetak pesan "Opsi tidak valid. Silakan pilih opsi yang tersedia."
    else:
        print("Opsi tidak valid. Silakan pilih opsi yang tersedia.")

print("Program selesai.") #berfungsi sebagai Setelah loop selesai, program akan mencetak pesan "Program selesai."

2.Buatlah sebuah objek Universitas dengan nama "XYZ University".
# Membuat objek Universitas dengan nama "XYZ University"
universitas_xyz = Universitas("XYZ University")

3.Buatlah objek Jurusan dengan nama "Teknik Informatika" dan tambahkan objek tersebut ke dalam Universitas XYZ.
# Membuat objek Jurusan dengan nama "Teknik Informatika" dan tambahkan ke dalam Universitas XYZ
jurusan_ti = Jurusan("Teknik Informatika") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ti) #membuat objek jurusan pada universitas

namun disini saya membuat fungsi menambahkan jurusan yang ada 

# Menambahkan Jurusan Teknik Sipil
jurusan_ts = Jurusan("Teknik Sipil")#menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ts) #membuat objek jurusan pada universitas

# Menambahkan Jurusan Teknik Mesin
jurusan_tm = Jurusan("Teknik Mesin")#menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_tm) #membuat objek jurusan pada universitas

# Menambahkan Jurusan Teknik Elektro
jurusan_te = Jurusan("Teknik Elektro") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_te) #membuat objek jurusan pada universitas

# Menambahkan Jurusan Arsitektur
jurusan_ar = Jurusan("Arsitektur") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_ar) #membuat objek jurusan pada universitas

# Menambahkan Jurusan Sistem Informasi
jurusan_si = Jurusan("Sistem Informasi") #menambah jurusan
universitas_xyz.tambah_jurusan(jurusan_si) #membuat objek jurusan pada universitas

4.Buatlah objek Mahasiswa dengan nama "Kalian masing", NIM "Kalian masing", dan masukkan ke dalam Jurusan Teknik Informatika di Universitas XYZ.
# Membuat objek Mahasiswa dengan nama "Davi Sulaiman", NIM "G1A022001", dan masukkan ke dalam Jurusan Teknik Informatika di Universitas XYZ
mahasiswa_davi = Mahasiswa("Davi Sulaiman", "G1A022001", jurusan_ti) #membuat objek untuk nama dan nim
jurusan_ti.tambah_mahasiswa(mahasiswa_davi) #menambahkan objek ke dalam jurusan di universitas

5.Tampilkan daftar jurusan yang ada di Universitas XYZ.
Daftar Jurusan di XYZ University
Teknik Informatika
Teknik Sipil
Teknik Mesin
Teknik Elektro
Arsitektur
Sistem Informasi

6.Tampilkan daftar mahasiswa yang terdaftar dalam Jurusan Teknik Informatika di Universitas XYZ.
Masukkan nama jurusan yang ingin Anda cari: Teknik Informatika
Daftar Mahasiswa di Teknik Informatika
Nama: Davi Sulaiman
NIM: G1A022001
Jurusan: Teknik Informatika


untuk program tersebut ia akan mengeluarkan output seperti berikut 
Pilih opsi:
1. Tampilkan Daftar Jurusan
2. Cari Mahasiswa
0. Keluar
Masukkan opsi: 1
Daftar Jurusan di XYZ University
Teknik Informatika
Teknik Sipil
Teknik Mesin
Teknik Elektro
Arsitektur
Sistem Informasi

Pilih opsi:
1. Tampilkan Daftar Jurusan
2. Cari Mahasiswa
0. Keluar
Masukkan opsi: 2
Masukkan nama jurusan yang ingin Anda cari: Teknik Informatika
Daftar Mahasiswa di Teknik Informatika
Nama: Davi Sulaiman
NIM: G1A022001
Jurusan: Teknik Informatika

Pilih opsi:
1. Tampilkan Daftar Jurusan
2. Cari Mahasiswa
0. Keluar
Masukkan opsi: 0
Program selesai.


(Untuk melihat jalannya sebuah kode program ini bisa dijalankan kode program yang sudah saya upload filenya
