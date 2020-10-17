# Lapres Praktikum Modul 1
**A. Display Filter**
1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

   Display filter: http.host == testing.mekanis.me
   
   Klik kanan -> pilih follow -> http stream -> terdapat
   
   webserver:nginx/1.14.0 (Ubuntu)
2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

   http contains Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg
   
   file -> export object -> http -> Cari nama file -> Save
   
3. Cari username dan password ketika login di "ppid.dpr.go.id"!

   http.request.method == POST && http.host == ppid.dpr.go.id
   
4. Temukan paket dari web-web yang menggunakan basic authentication method!

   http.authbasic
5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

   http.host contains "aku.pengen.pw"
   
   Buka length 574 -> hypertext -> authorization -> credential
   
   Di temukan USER : kakakgamtenk PASS : hartatahtabermuda
   
6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

   ftp-data.command contains "Answer.zip"
   
   ftp-data.command contains "zipkey.txt"
   
   masing masing di follow stream -> ubah ascii menjadi raw -> save as dan bernama sesuai format file nya
   
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

   frame contains "Yes.pdf"
   
   follow stream -> ubah ascii menjadi raw -> save as sesui dengan format file
   
8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

   ftp.request.command == RETR
   
9. Cari username dan password ketika login FTP pada localhost!

   ftp.request.command==USER
   
   ftp.request.command==PASS
   
10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"

   CTRL - Find -> 35 50 44 46 -> Follow stream -> save as sesuai format file

**B. Capture Filter**

11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

    tcp port 21
    
12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

    tcp src port 80
    
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

    tcp dst port 443
    
14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

    src host 192.168.1.9
    
15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

    dst monta.if.its.ac.id
    
