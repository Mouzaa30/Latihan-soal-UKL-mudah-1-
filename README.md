Scanner → digunakan untuk membaca input dari pengguna (keyboard).
NumberFormat → digunakan untuk memformat angka ke dalam bentuk mata uang.
Locale → digunakan untuk menentukan format negara (dalam hal ini Indonesia, agar tampil “Rp”).
BiayaPengiriman adalah nama kelas utama.
main() adalah method yang akan dijalankan pertama kali saat program dijalankan.
Scanner input = new Scanner(System.in); Digunakan untuk menerima input dari pengguna melalui terminal/console.
try digunakan agar jika ada error, scanner tetap ditutup.
finally memastikan bahwa input.close() tetap dijalankan untuk menutup scanner setelah digunakan (mencegah kebocoran memori).
System.out.print("Masukkan berat paket (kg): ");
double berat = input.nextDouble();

System.out.print("Masukkan jarak pengiriman (km): ");
double jarak = input.nextDouble();

System.out.print("Masukkan panjang paket (cm): ");
double panjang = input.nextDouble();

System.out.print("Masukkan lebar paket (cm): ");
double lebar = input.nextDouble();

System.out.print("Masukkan tinggi paket (cm): ");
double tinggi = input.nextDouble();
Setiap baris meminta pengguna untuk memasukkan data numerik.

Semua data disimpan dalam variabel bertipe double agar bisa menampung angka desimal.
Jika salah satu nilai yang dimasukkan negatif, program akan menampilkan pesan error dan berhenti (return).
double volume = panjang * lebar * tinggi; Volume dihitung dengan rumus panjang × lebar × tinggi (satuan cm³).
double biayaPerKg = (jarak <= 10) ? 4250 : 6000;
Menggunakan operator ternary
Jika jarak ≤ 10 km, biaya per kg = Rp 4.250
Jika jarak > 10 km, biaya per kg = Rp 6.000
double totalBiaya = berat * biayaPerKg;
Biaya awal dihitung dari berat × biaya per kg.
Jika volume paket lebih besar dari 100 cm³, maka ditambahkan biaya tambahan Rp50.000.
final berarti nilai VOLUME_THRESHOLD tidak bisa diubah lagi (konstanta).
Membuat formatter agar angka tampil seperti Rp6.000.
setMaximumFractionDigits(0) menghapus angka desimal di belakang koma.
String.format("%.0f", volume) → menampilkan volume tanpa desimal.
nf.format(...) → mengubah angka menjadi format rupiah.
volume > VOLUME_THRESHOLD ? nf.format(50000) : nf.format(0) → menampilkan biaya volume hanya jika melebihi ambang batas.
input.close();
Scanner ditutup untuk membebaskan resource yang digunakan.


