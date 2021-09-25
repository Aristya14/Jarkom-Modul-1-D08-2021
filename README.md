# Jarkom-Modul-1-D08-2021

## Soal No 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 

Untuk mengetahui server yang digunakan dalam web ichimarumaru.txt ialah dengan melakukann filter  ``host ichimarumaru.tech`` kemudia menggunakan display filter ``http.host==ichimarumaru.tech``. Setelah itu memmbuka analyze kemudia ke follow dan dibagian http stream akan tertera server dari ichimarumaru.tech yaitu `nginx/1.18.0 (Ubuntu)`

![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/no%201/no%201.png)

## Soal No 2
Temukan paket dari web-web yang menggunakan basic authentication method!

Untuk mengetahui paket dari web menggunakan basic authentication method adalah melakukan filter ``http.authbasic``

![2](./Gambar/2.png)

## Soal No 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Untuk mendapatkan paket yang mengandung website ``basic.ichimarumaru.tech`` dapat digunakan filter ``http.host==basic.ichimarumaru.tech``  
Dibagian hypertext transfer terdapat authorization. Dibagian ini terdapat credentials yang berisi username dan password.  
Username: kuncimenujulautan  
Pass: tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN  
![image](https://user-images.githubusercontent.com/73290753/134759237-9561c242-febf-4e4a-b3fd-97ce359eb826.png)

Setelah username dan password sudah didapatkan, Login di website ``basic.ichimarumaru.tech`` dan melakukan perintah yang ditampilkan yaitu sebutkan urutan konfigurasi pengkabelan T568A  
![image](https://user-images.githubusercontent.com/73290753/134759374-5c054117-18b0-4d44-8a71-032c3cb05c43.png)



## Soal No 4
Temukan paket mysql yang mengandung perintah query select!

## Soal No 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

## Soal No 6
Cari username dan password ketika melakukan login ke FTP Server!

Untuk mengetahui username dan password ketika login di ftp server ialah menggunkan filter ``ftp contains USER or ftp contains PASS``

![6](./Gambar/6.png)

## Soal No 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

## Soal No 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!

## Soal No 9
Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
Dari file 8-10.pcap selanjutnya mneggunakan ``ftp-data`` untuk mencari `secret.zip`. Lalu memilih salah satu dari `STOR ZIP`, setelah itu kita bisa menyimpannya melalui analyze, kemudian follow lalu pilih TCP Stream,kemudian memilih mengubah dari ASCII ke raw, dan menyimpannya engan nama secret.zip. Jika kita buka maka didalamnya ada file pdf bernama `Wanted`. untuk membukanya, kita membutuhkan password yang di temukan pada soal no 10.
![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/Gambar/9%20mencari%20secert%20zip.png)
![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/Gambar/9%20isi%20secret%20zip.png)
![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/Gambar/9%20wanted.png)

## Soal No 10
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Berdasarkan file 8-10.pcap yang ada pada soal, maka dapat dicari history.txt dengan menggunakan display filter ``ftp-data contains "history"``.
Setelah itu pada bagian line-based text data terdapat file bernama bukanapaapa.txt.

![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/no%2010/10%20history%20txt.png)

Dengan mencari di display filter ``ftp-data contains "bukanapaapa"`` maka didapatkan password yang terletak pada line-based text data yaitu `d1b1langbukanapaapajugagapercaya`
![alt text](https://github.com/Aristya14/Jarkom-Modul-1-D08-2021/blob/main/no%2010/10%20bukanapaapa%20txt.png)

## Soal No 11
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 

Untuk mengambil paket yang berasal dari port 80 dengan cara memfilter  menggunakan ``src port 80``

![11](./Gambar/11.png)

## Soal No12
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Untuk mengambil paket yang mengandung port 21 dengan cara memfilter menggunakan ``port 21``

![12](./Gambar/12.png)

## Soal No 13
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

Untuk menampilkan paket yang menuju pada port 443 dengan cara memfilter menggunakan ``dst port 443``

![13](./Gambar/13.png)

## Soal No 14
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!

Untuk mengambil paket yang tujuannya ke kemenag.go.id dengan mencari ip dari link tersebut dengan menggunakan terminal ``ping kemenag.go.id``. Setelah mendapatkan ip dari link tersebut, dapat memfilter di dalam wireshark ``ip.dst == 103.7.13.247``

![14](./Gambar/14.png)

## Soal No 15
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Untuk mengambil paket yang berasal dari ip kita adalah dengan mengetahui terlebih dahulu ip kita, kemudian melakukan filter di wireshark dengan cara ``ip.src == 192.168.100.226``

![15](./Gambar/15.png)
