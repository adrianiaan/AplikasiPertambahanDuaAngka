# Aplikasi Pertambahan Dua Angka
Latihan 1 - Adrian Akhmad Firdaus (2210010491)
---
# Deskripsi

Aplikasi ini memungkinkan pengguna untuk melakukan operasi penjumlahan dua angka dengan antarmuka grafis yang sederhana.
## Fitur Aplikasi

1. **Penjumlahan Dua Angka**: 
   - Pengguna memasukkan dua angka di `JTextField` dan menekan tombol **Tambah** untuk menampilkan hasil.
   - **Kode Implementasi**:
     ```java
     private void btnTambahActionPerformed(java.awt.event.ActionEvent evt) {                                          
         try {
             int angka1 = Integer.parseInt(txtAngka1.getText());
             int angka2 = Integer.parseInt(txtAngka2.getText());
             int hasil = angka1 + angka2;
             txtHasil.setText(String.valueOf(hasil));
         } catch (NumberFormatException e) {
             JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
         }
     }
     ```

2. **Menghapus Input**:
   - Tombol **Hapus** akan membersihkan input pada kedua `JTextField` dan mengarahkan fokus ke input pertama.
   - **Kode Implementasi**:
     ```java
     private void btnHapusActionPerformed(java.awt.event.ActionEvent evt) {                                         
         txtAngka1.setText("");
         txtAngka2.setText("");
         txtHasil.setText("");
         txtAngka1.requestFocus();
     }
     ```

3. **Keluar dari Aplikasi**:
   - Tombol **Keluar** akan menutup aplikasi.
   - **Kode Implementasi**:
     ```java
     private void btnKeluarActionPerformed(java.awt.event.ActionEvent evt) {                                          
         System.exit(0);
     }
     ```

4. **Validasi Input Angka**:
   - Membatasi input hanya untuk angka pada kedua `JTextField` menggunakan `KeyAdapter`.
   - **Kode Implementasi**:
     ```java
     private void txtAngka1KeyTyped(java.awt.event.KeyEvent evt) {                                   
         char c = evt.getKeyChar();
         if (!Character.isDigit(c) && c != KeyEvent.VK_BACK_SPACE) {
             evt.consume();
         }
     }
     ```

5. **Pesan Kesalahan**:
   - Jika input tidak valid (misalnya, kosong atau bukan angka), akan muncul pesan kesalahan menggunakan `JOptionPane`.
   - **Kode Implementasi**:
     ```java
     JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
     ```

6. **Pembersihan Input saat Fokus**:
   - Input akan otomatis dibersihkan ketika pengguna mengklik atau memfokuskan pada `JTextField`.
   - **Kode Implementasi**:
     ```java
     private void txtAngka1FocusGained(java.awt.event.FocusEvent evt) {                                      
         txtAngka1.setText("");
     }
     ```

7. **Hasil Tidak Bisa Diedit**:
   - Hasil penjumlahan ditampilkan di `txtHasil` yang telah disetel tidak dapat diedit.
   - **Kode Implementasi**:
     ```java
     txtHasil.setEditable(false);
     ```

## Komponen GUI

Aplikasi ini menggunakan komponen berikut:
- **JFrame**: Jendela utama aplikasi.
- **JPanel**: Panel untuk menata komponen.
- **JLabel**: Label untuk keterangan input.
- **JTextField**: Input angka pertama, angka kedua, dan output hasil.
- **JButton**: Tombol **Tambah**, **Hapus**, dan **Keluar**.

## Struktur Program

1. **Desain GUI**: 
   - Komponen ditata menggunakan `GridBagLayout` untuk fleksibilitas tata letak.
   
2. **Logika Program**:
   - Validasi input dan operasi penjumlahan diterapkan pada event listener.

3. **Events**:
   - `ActionListener` untuk tombol.
   - `KeyAdapter` untuk validasi input angka.
   - `FocusListener` untuk pembersihan input otomatis.

## Cara Menjalankan Aplikasi

1. Buka proyek di NetBeans IDE 8.2.
2. Jalankan file utama `AplikasiPertambahanDuaAngka.java`.
3. Masukkan dua angka pada `JTextField` yang disediakan.
4. Gunakan tombol:
   - **Tambah** untuk menghitung penjumlahan.
   - **Hapus** untuk membersihkan input.
   - **Keluar** untuk menutup aplikasi.

## Gambar pada saat Aplikasi Dijalankan

![image](https://github.com/user-attachments/assets/e5de38b7-a0e7-42e6-8f91-35da115ede45)


---

## Indikator Penilaian

| No  | Komponen           | Persentase |
|-----|---------------------|------------|
| 1   | Komponen GUI       | 20%        |
| 2   | Logika Program     | 20%        |
| 3   | Events             | 15%        |
| 4   | Kesesuaian UI      | 15%        |
| 5   | Memenuhi Variasi   | 30%        |
| **TOTAL** |               | **100%**   |

---
## Pembuat

Nama: Adrian Akhmad Firdaus

NPM: 2210010491

Kelas: 5A Reguler Pagi

Tugas : Latihan 1 - Aplikasi Pertambahan Dua Angka

Fakultas : Fakultas Teknologi Informasi (FTI)

Unversitas : Universitas Islam Kalimantan Muhammad Arsyad Al Banjari Banjarmasin
