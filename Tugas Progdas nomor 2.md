#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int jumlah;
    cout << "Berapa jenis barang yang ingin dimasukkan? ";
    cin >> jumlah;

    string namaBarang[jumlah];
    int hargaBarang[jumlah];
    int jumlahBeli[jumlah];
    int total = 0;

    // Input data barang
    for (int i = 0; i < jumlah; i++) {
        cout << "\nMasukkan nama barang ke-" << i + 1 << ": ";
        cin >> ws; 
        getline(cin, namaBarang[i]);

        cout << "Masukkan harga satuan " << namaBarang[i] << ": Rp ";
        cin >> hargaBarang[i];

        cout << "Masukkan jumlah " << namaBarang[i] << " yang dibeli: ";
        cin >> jumlahBeli[i];

        total += hargaBarang[i] * jumlahBeli[i];
    }

    // Struk pembayaran
    cout << "\n================ STRUK PEMBAYARAN ================\n";
    cout << left << setw(20) << "Barang" << setw(10) << "Harga" << setw(8) << "Qty" << setw(12) << "Subtotal" << "\n";
    cout << "---------------------------------------------------\n";

    for (int i = 0; i < jumlah; i++) {
        int subtotal = hargaBarang[i] * jumlahBeli[i];
        cout << left << setw(20) << namaBarang[i]
             << "Rp " << setw(7) << hargaBarang[i]
             << setw(8) << jumlahBeli[i]
             << "Rp " << subtotal << "\n";
    }

    cout << "---------------------------------------------------\n";
    cout << left << setw(30) << "Total Belanja" << "Rp " << total << "\n";

    int bayar;
    cout << "\nMasukkan uang pembayaran: Rp ";
    cin >> bayar;

    if (bayar > total) {
        cout << "Kembalian Anda: Rp " << bayar - total << "\n";
    } else if (bayar == total) {
        cout << "Uang pas. Tidak ada kembalian.\n";
    } else {
        cout << "Uang Anda kurang Rp " << total - bayar << "\n";
    }

    cout << "============== TERIMA KASIH SUDAH BERBELANJA ==============\n";
    return 0;
}
