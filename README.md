## **Tugas-4-Network-Programming-Kelompok**

### **Anggota:**
        
        Fadillah Rizky R                1301164493
        Mazaya Z D                      1301154508
        Renaning Karutami Susilo        1301154466

### **JSON Marshal:**

**Soal** 

![soal 1](https://user-images.githubusercontent.com/33456025/53415137-fe29ab00-3a02-11e9-94ae-7364f7780c0b.png)

**Jawaban**

![jawaban 1](https://user-images.githubusercontent.com/33456025/53416140-67aab900-3a05-11e9-9d36-fd1623c4782a.png)

**Penjelasan**
        
        Fungsi json.Marshal digunakan untuk decoding data ke json. 
        Data tersebut bisa berupa variable objek cetakan struct map[string]interface{}, bisa juga bertipe array. 

        Program pada nomor 1 adalah contoh cara encode data ke bentuk json. 
        * Pertama import package yang dibutuhkan dan siapkan struct Person.
        * Hasil encode nantinya akan disimpan ke variable objek cetakan struct Person.
        * Buat contoh struct Person.
        * Buat json dari contoh data  
        * Buat pesan ketika error
        * Hasil encode adalah bertipe [ ]byte. Casting ke string bisa digunakan untuk menampilkan data.

        
### **JSON Unmarshal:**

**Soal**

![soal 2](https://user-images.githubusercontent.com/33456025/53415471-eacb0f80-3a03-11e9-9c1d-175f8376dedf.png)

**Jawaban**

![jawaban 2](https://user-images.githubusercontent.com/33456025/53416349-e99ae200-3a05-11e9-891f-f43dc6e4699f.png)

**Penjelasan**

        Data json tipenya adalah [ ]byte, bisa didapat dari file ataupun string (dengan hasil casting).
        Dengan menggunakan json.Unmarshal, data tersebut bisa dikonversi menjadi bentuk objek, 
        seperti bentuk map[string]interface{} ataupun variable objek hasil struct. 

        Program pada nomor 2 adalah contoh cara decoding json ke bentuk objek. 
        * Pertama import package yang dibutuhkan dan siapkan struct Person.
        * Hasil decode nantinya akan disimpan ke variable objek cetakan struct Person.
        * Selanjutnya siapkan data json string sederhana, gunakan casting ke [ ]byte agar dideteksi 
          sebagai data json.
        * Dalam penggunaan fungsi json.Unmarshal, variable yang akan menampung hasil decode harus di-passing 
          sebagai pointer (&p).
        * Pada kode di soal nomor 2 bisa dilihat bahwa terdapat property struct Person yang memiliki tag, 
          yaitu FirstName dan LastName. Tag tersebut digunakan untuk mapping data json ke property yang 
          bersangkutan.
        * Data json yang akan diparsing memiliki 2 property yaitu FirstName dan LastName.
        * Property FirstName struct tersebut kemudian ditugaskan untuk menampung data json property firstname, 
          ditandai dengan tag ‘json:”firstname”’ pada saat deklarasi structnya.
          
### **Flatbuffer dan Protocol Buffer:**

**Soal**

Jalankan program pada repository github berikut: https://github.com/jonog/grpc-flatbuffers-example 
Berikan analisis berupa:
1. Apakah outputnya (berikan printscreen)!
2. Jelaskan cara kerjanya dan buatlah diagram FSMnya! 
3. Analisis perbedaan dari protocol buffer dan flatbuffer!

**Jawaban**

1. Output

   **Server**

   ![whatsapp image 2019-02-26 at 19 50 40](https://user-images.githubusercontent.com/33456025/53416927-0c79c600-3a07-11e9-9fae-3c5626c69ac8.jpeg)

   **CLient**

   ![whatsapp image 2019-02-26 at 19 52 02](https://user-images.githubusercontent.com/33456025/53417063-595d9c80-3a07-11e9-9045-506926ec41cb.jpeg)

2. Diagram FSM dan Cara Kerja

   **Diagram FSM**
   
   ![fsm](https://user-images.githubusercontent.com/33456025/53417361-01736580-3a08-11e9-8dab-69de9004ad7a.jpeg)
   
   **Cara Kerja**
   
   Server yang telah siap akan menerima request 'add' dari client, jumlah tiap request 'add' akan disimpan oleh server 
   begitu juga dengan url dan judul yang direquest oleh client. Saat  client merequest 'last added' maka akan ditampilkan
   request 'add' terakhir yang dilakukan oleh client.

3. Analisis perbedaan dari protocol buffer dan flatbuffer

   Protokol Buffer memang relatif mirip dengan FlatBuffers, dengan perbedaan utama adalah bahwa FlatBuffers tidak 
   memerlukan langkah parsing / membongkar untuk representasi sekunder sebelum dapat mengakses data, sering ditambah
   dengan alokasi memori per-objek. Kode urutan ukurannya jauh lebih besar. Protokol Buffer tidak memiliki impor / ekspor 
   teks opsional atau fitur bahasa skema seperti penyatuan.

