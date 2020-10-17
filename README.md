# Lapres Praktikum Modul 1
**A. Display Filter**
1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

   `http.host == testing.mekanis.me`
   
   Klik kanan -> pilih follow -> http stream -> terdapat
   
   webserver:nginx/1.14.0 (Ubuntu)
   ![1](https://user-images.githubusercontent.com/61223768/96330285-4f762a80-107e-11eb-9f25-c3985175564b.jpg)

2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

   `http contains Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg`
   
   file -> export object -> http -> Cari nama file -> Save
   
   ![2](https://user-images.githubusercontent.com/61223768/96330137-112c3b80-107d-11eb-9591-1c1c7603e8f5.jpg)
![Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436](https://user-images.githubusercontent.com/61223768/96330113-df1ad980-107c-11eb-965c-21e773fd4956.jpg)
   
3. Cari username dan password ketika login di "ppid.dpr.go.id"!

   `http.request.method == POST && http.host == ppid.dpr.go.id`
   
   ![3](https://user-images.githubusercontent.com/61223768/96330312-792f5180-107e-11eb-9fdc-7217c0d0cf5b.jpg)

4. Temukan paket dari web-web yang menggunakan basic authentication method!

   `http.authbasic`
   
   ![4](https://user-images.githubusercontent.com/61223768/96330134-0ec9e180-107d-11eb-8da0-d374e975ff68.jpg)

5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

   `http.host == aku.pengen.pw`
   
   Buka length 574 -> hypertext -> authorization -> credential
   
   Di temukan USER : kakakgamtenk PASS : hartatahtabermuda
   
   ![5](https://user-images.githubusercontent.com/61223768/96330283-4c7b3a00-107e-11eb-9f3b-d4bfc1afe79b.jpg)
![55](https://user-images.githubusercontent.com/61223768/96330224-de367780-107d-11eb-882b-6d7371f44d72.jpg)
   
6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

   ``ftp-data.command contains "Answer.zip"``
   
   ``ftp-data.command contains "zipkey.txt"``
   
   masing masing di follow stream -> ubah ascii menjadi raw -> save as dan bernama sesuai format file nya
   
   ![6](https://user-images.githubusercontent.com/61223768/96330219-db3b8700-107d-11eb-9676-09d463bdc40e.jpg)
   
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

   `frame contains "Yes.pdf"`
   
   follow stream -> ubah ascii menjadi raw -> save as sesui dengan format file
   
   ![7](https://user-images.githubusercontent.com/61223768/96330220-dc6cb400-107d-11eb-86d3-bc3ab3ee25ce.jpg)
![77](https://user-images.githubusercontent.com/61223768/96330225-df67a480-107d-11eb-964c-a666d7ed94c4.jpg)
   
8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

   `ftp.request.command == RETR`
   
   ![8](https://user-images.githubusercontent.com/61223768/96330223-dd9de100-107d-11eb-949d-ab7ae45f6931.jpg)
![88](https://user-images.githubusercontent.com/61223768/96330226-e0003b00-107d-11eb-9aa4-985ee88e371e.jpg)
   
9. Cari username dan password ketika login FTP pada localhost!

   `ftp.request.command==USER`
   
   `ftp.request.command==PASS`
   
   ![9PASS](https://user-images.githubusercontent.com/61223768/96330465-a0d2e980-107f-11eb-84a3-9c1a57a7ff33.jpg)
![9user](https://user-images.githubusercontent.com/61223768/96330467-a4667080-107f-11eb-9a5c-2284163a4023.jpg)
   
10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"

     CTRL - Find -> 35 50 44 46 -> Follow stream -> save as sesuai format file
   
   ![10](https://user-images.githubusercontent.com/61223768/96330469-a8928e00-107f-11eb-9c5a-3354dc006df4.jpg)
   ![1010](https://user-images.githubusercontent.com/61223768/96330493-cd870100-107f-11eb-9585-d4cbe788ac8b.jpg)
![101010](https://user-images.githubusercontent.com/61223768/96330462-957fbe00-107f-11eb-8a66-e72d82af79bb.jpg)

**B. Capture Filter**

11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

    `tcp port 21`
    
    ![11](https://user-images.githubusercontent.com/61223768/96330473-adefd880-107f-11eb-9e79-e211172c4ad6.jpg)
    
12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

    `tcp src port 80`
    
    ![12](https://user-images.githubusercontent.com/61223768/96330475-b5af7d00-107f-11eb-9884-48306ea4f72f.jpg)
    
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

    `tcp dst port 443`
    
    ![13](https://user-images.githubusercontent.com/61223768/96330479-bba55e00-107f-11eb-8793-8ae9b323eacf.jpg)
    
14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

    `src host 192.168.1.9`
    
    ![14](https://user-images.githubusercontent.com/61223768/96330488-c829b680-107f-11eb-88c7-967b2a25f4e2.jpg)

15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!

    `dst monta.if.its.ac.id`
    
    ![15](https://user-images.githubusercontent.com/61223768/96330489-c95ae380-107f-11eb-9e16-44996bccb5e7.jpg)
    
    
