#Program nomor 1 deret bilangan prima

```cpp
#include <iostream>
using namespace std;

int main() {

    char ulangi; 

    do {
        int n;
        cout << "Masukkan jumlah bilangan prima yang ingin ditampilkan: ";
        cin >> n;

        int count = 0;       
        int angka = 2;       
        int jumlah = 0;      

        cout << "Deret bilangan prima: ";

        
        while (count < n) {
            bool prime = true;

            
            for (int i = 2; i * i <= angka; i++) {
                if (angka % i == 0) {
                    prime = false;
                    break;
                }
            }

            if (prime) {
                cout << angka << " ";
                jumlah += angka;
                count++;
            }
            angka++;
        }

        cout << "\nJumlah bilangan prima = " << jumlah << endl;
        cout << "Program selesai, terima kasih\n";

        
        cout << "Apakah ingin coba lagi? (y/n): ";
        cin >> ws >> ulangi;
        

    } while (ulangi == 'y' || ulangi == 'Y');

    cout << "Terima kasih telah menggunakan program ini\n";
    return 0;
}
