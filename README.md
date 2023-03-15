import os
os.system ('cls')

class Barang:
    def __init__(self, nama_barang, harga, stok):
        self.nama_barang = nama_barang
        self.harga = harga
        self.stok = stok
        self.next = None

class TokoATK:
    def __init__(self):
        self.head = None

    def tambah_barang(self):
        nama_barang = input("\nMasukkan nama barang: ")
        harga = int(input("Masukkan harga barang: "))
        stok = int(input("Masukkan stok barang: "))
        new_barang = Barang(nama_barang, harga, stok)

        if self.head is None:
            self.head = new_barang
        else:
            current = self.head
            while current.next is not None:
                current = current.next
            current.next = new_barang

        print("\n^^^Barang berhasil ditambahkan.^^^")

    def lihat_barang(self):
        if self.head is None:
            print("Tidak ada barang.")
        else:
            current = self.head
            while current is not None:
                print("Nama barang: ", current.nama_barang)
                print("Harga barang: ", current.harga)
                print("Stok barang: ", current.stok)
                current = current.next

    def hapus_barang(self):
        nama_barang = input("\nMasukkan nama barang yang ingin dihapus: ")
        if self.head is None:
            print("Tidak ada barang.")
        elif self.head.nama_barang == nama_barang:
            self.head = self.head.next
            print("\nBarang berhasil dihapus.")
        else:
            current = self.head
            while current.next is not None:
                if current.next.nama_barang == nama_barang:
                    current.next = current.next.next
                    print("Barang berhasil dihapus.")
                    return
                current = current.next
            print("Barang tidak ditemukan.")
            
if __name__ == '__main__':
    toko_atk = TokoATK()
    while True:
        print("\nMenu:")
        print("1. Tambah barang")
        print("2. Lihat barang")
        print("3. Hapus barang")
        print("4. Keluar")

        pilihan = int(input("\nMasukkan pilihan: "))
        if pilihan == 1:
            toko_atk.tambah_barang()
        elif pilihan == 2:
            toko_atk.lihat_barang()
        elif pilihan == 3:
            toko_atk.hapus_barang()
        elif pilihan == 4:
            break
        else:
            print("Pilihan tidak valid.")

Data pada linked list diatas berupa dictionary yang terdiri dari tiga key, yaitu 'nama', 'harga', dan 'jumlah'.
Fungsi tambah_data digunakan untuk menambahkan data baru ke linked list.
Fungsi hapus_data digunakan untuk menghapus data pada linked list berdasarkan nilai dari key 'nama', 'harga', dan 'jumlah'.
Fungsi lihat_data digunakan untuk menampilkan semua data pada linked list.
data digunakan untuk menyimpan data dalam simpul. 
next digunakan untuk menunjukkan simpul berikutnya dalam urutan linked list.
head yang digunakan untuk menunjukkan simpul pertama dalam linked list.
current yang digunakan untuk menunjukkan simpul yang sedang ditinjau.
penjelasan program:
di awal masuk, akan menampilkan menu yang harus dipilih yaitu menu tambah, menu hapus, menu lihat, dan juga menu untuk keluar dari program. Awalnya menu tambah digunakan untuk menambah baran yang ada di dalam toko atk, karena belum ada data yang masuk didalmnya, jadi sebelum itu harus menambahkan data terlebih dahulu. lalu jika menambahkan data maka akan diperintahkan untuk memasukkan nama barang nya dan memasukkan harga nya lalu memasukkan stok barang nya. setelah menu tambah, ada menu lihat untuk melihat data apa yang ada di dalamnya dan juga menampilkan data yang sudah dditambahkan. lalu menu ketiga yaitu menghapus datanya, akan diminta untuk memasukkan nama barang yang akan dihapus, lalu jika berhasil maka barang tersebut berhasil dihapus. setelah itu menu yang terakhiryaitukeluar.
