# Jarkom-Modul-4-T09-2021

Nama Anggota | NRP
------------------- | --------------		
Natasya Abygail N | 05111940000020
Muhammad Hilmi Ramadhan | 05311940000044
Sri Puspita Dewi | 05111940000045

## List of Contents :
- [VLSM](#vlsm)
	- [Jawaban](#jawaban-soal-vlsm)
- [CIDR](#cidr)
	- [Jawaban](#jawaban-soal-cidr)

Berikut merupakan soal topologi yang diberikan dimana kami diminta untuk menyelesaikannya dalam `Subnetting` dengan dua metode yaitu `VLSM` dan `CIDR`.

![Foto](./img/soalTopologi.png)
<br>

## Catatan
---
1. VLSM dikerjakan di Cisco Packet Tracer
2. CIDR dikerjakan di GNS3
3. Prefix IP menggunakan `10.46.0.0`

Detil soal dapat dilihat pada [tautan ini](https://docs.google.com/document/d/1hf5Vi5nbEq6YY-nqmK7XUTHGNL_KVEFVc14mW9k0FAg/edit)

## VLSM
---
Buatlah penyelesaian subnetting dengan metode VLSM dari topologi yang diberikan!

## Jawaban Soal VLSM 
---
Pertama-tama kami membuat pembagian subnet terhadap topologi soal.

![Foto](./img/VLSMsoalShiftmodul4/topologiVLSMsoalShiftModul4.jpg)
<br>

Dari hasil pembagian subnet diketahui terdapat sejumlah **15 Subnet**

### Perhitungan VLSM
1. Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dari 15 subnet yang ada 	

   | Subnet | Jumlah IP | Netmask |
   | :---:  | :---:     | :---:   |
   | A1     | 721       | /22     |
   | A2     | 252       | /24     | 
   | A3     | 2         | /30     | 
   | A4     | 521       | /22     |  
   | A5     | 13        | /28     |  
   | A6     | 502       | /23     |  
   | A7     | 2         | /30     |  
   | A8     | 2         | /30     |  
   | A9     | 1001      | /22     |  
   | A10    | 701       | /22     |  
   | A11    | 2         | /30     |  
   | A12    | 2021      | /21     |  
   | A13    | 101       | /25     |   
   | A14    | 2         | /30     |   
   | A15    | 2         | /30     |   
   | **Total**   | **5845**    | **/19**     | 

2. Subnet besar yang kami bentuk memiliki NID 10.46.0.0 dengan netmask /19. Lalu, kita mulai dengan perhitungan pembagian IP dengan bantuan pohon IP seperti gambar berikut:
![Foto](./img/VLSMsoalShiftmodul4/treeVLSMsoalShiftModul4.jpg)
Sehingga pembagian IP yang memungkinkan dalam topologi seperti gambar berikut:
![Foto](./img/VLSMsoalShiftmodul4/tabelPohonIPsoalShiftModul4.jpg)
<br>

3. Setting IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM. Interface dapat diatur pada menu Config > INTERFACE > “nama interface” pada `Cisco Packet Tracerr`
- FOOSHA (Sebagai Router)
	- IP pada interface FOOSHA yang mengarah ke CLOUD `(Fa0/0)`
	![Foto](./img/VLSMsoalShiftmodul4/.jpg)
	- IP pada interface FOOSHA yang mengarah ke BLUENO (1000 Host) `(Fa0/1)`
	![Foto](./img/VLSMsoalShiftmodul4/.jpg)
	- IP pada interface FOOSHA yang mengarah ke WATER7 `(Eth1/0)`
	![Foto](./img/VLSMsoalShiftmodul4/.jpg)
	- IP pada interface FOOSHA yang mengarah ke GUANHAO `(Eth1/2)`
	![Foto](./img/VLSMsoalShiftmodul4/.jpg)
	- IP pada interface FOOSHA yang mengarah ke DORIKI Server `(Eth1/1)`
	![Foto](./img/VLSMsoalShiftmodul4/.jpg)
	<br>

	
## CIDR
---
Buatlah topologi jaringan dengan kriteria sebagai berikut: `EniesLobby` sebagai `DNS Server`, `Jipangu` sebagai `DHCP Server`, `Water7` sebagai `Proxy Server`.

## Jawaban Soal CIDR 
---
Pertama-tama kami membuat sebuah node yang terhubung dengan internet dengan nama NAT1. Node tersebut kemudian disambungkan dengan router foosha melalui interface `nat0` menuju interface `eth0`. Selanjutnya persiapkan peletakan node-node sesuai dengan yang ada pada [Soal Shift](https://docs.google.com/document/d/1hwuI5YpxiP-aboS7wGWPbaQeSOQl0HHVHLT3ws2BPUk/edit)

![Foto](./img/no1/topologi.jpg)
<br>