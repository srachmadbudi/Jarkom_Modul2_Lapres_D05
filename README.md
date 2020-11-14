# Jarkom_Modul2_Lapres_D05
Perjuangan modul 2 dalam menjalani kehidupan jarkom.

### Nomor 1 
Membuat sebuah website utama dengan alamat http://semeruyyy.pw (yyy diganti dengan d05)

_**Langkah**_
- membuat domain 

![image](https://user-images.githubusercontent.com/57980671/99139103-90a32f80-2668-11eb-90f8-f3db80cc2712.png)
- membuat file semerud05.pw

![image](https://user-images.githubusercontent.com/57980671/99139497-d0b7e180-266b-11eb-8546-d60456071fe1.png)
- setting nameserver pada client

![image](https://user-images.githubusercontent.com/57980671/99139533-170d4080-266c-11eb-9f93-51abfe589ed1.png)

### Nomor 2
Membuat alias domain http://semerud05.pw = www.semerud05.pw

_**Langkah**_
- tambahkan konfigurasi pada file semerud05.pw

![image](https://user-images.githubusercontent.com/57980671/99139622-090bef80-266d-11eb-8f5a-e3f2fb965100.png)
- lakukan cek dengan ping www.semerud05.pw atau host -t CNAME www.semerud05.pw

![image](https://user-images.githubusercontent.com/57980671/99139728-e0d0c080-266d-11eb-9c60-049067a9693e.png)

### Nomor 3
Membuat subdomain penanjakan.semerud05.pw

_**Langkah**_
- tambahkan konfigurasi pada file semerud05.pw

![image](https://user-images.githubusercontent.com/57980671/99139815-a0257700-266e-11eb-99af-5f5fffc3adba.png)

### Nomor 4 
Membuat Reverse domain utama

_**Langkah**_
- tambahkan konfigurasi pada file named.conf.local

![image](https://user-images.githubusercontent.com/57980671/99139907-846ea080-266f-11eb-922a-975006c7244d.png)

- cp file db.local yg berada di /etc/bind ke 79.151.10.in-addr.arpa dalam folder jarkom
- edit file tersebut

![image](https://user-images.githubusercontent.com/57980671/99139960-fe9f2500-266f-11eb-8ac7-6f72305a6346.png)
- kemudian restart bind9
- lalu jalankan perintah host -t PTR 10.151.79.50 //IP MALANG pada client GRESIK

![image](https://user-images.githubusercontent.com/57980671/99139997-52aa0980-2670-11eb-9638-7fa80c3fbfb3.png)
( disini terdapat error yang saya tidak tahu ) 
1. pertama saya mendapatkan error "not found"
2. kedua saya mendapatkan error seperti pada gambar diatas

### Nomor 5
Membuat DNS Server Slave pada MOJOKERTO

_**Langkah**_
- ubah konfigurasi pada file named.conf.local di server MALANG

![image](https://user-images.githubusercontent.com/57980671/99140065-c77d4380-2670-11eb-9519-d767eee3a568.png)
- kemudian lakukan restart bind9
- tambahkan konfigurasi pada file named.conf.local di server MOJOKERTO

![image](https://user-images.githubusercontent.com/57980671/99140127-702ba300-2671-11eb-9a67-ae013aa1f1d7.png)
- kemudian restart bind9
- lalu test dengan cara stop bind9 dan ping semerud05.pw di client GRESIK

![image](https://user-images.githubusercontent.com/57980671/99140207-2a230f00-2672-11eb-9942-7c632d4eaed4.png)

### Nomor 6
Membuat Subdomain gunung.semerud05.pw

_**Langkah**_
- ubah file semerud05.pw pada server MALANG seperti gambar dibawah

![image](https://user-images.githubusercontent.com/57980671/99140279-03190d00-2673-11eb-815e-3f6480162ce3.png)
- kemudian ubah file named.conf.options seperti gambar dibawah

![image](https://user-images.githubusercontent.com/57980671/99140304-41aec780-2673-11eb-907c-664ad1e79805.png)

![image](https://user-images.githubusercontent.com/57980671/99140346-bda90f80-2673-11eb-8d95-e852484d0c96.png)
- setelah itu restart bind9
- lakukan sepert mengubah file named conf.options pada server MALANG pada server MOJOKERTO

![image](https://user-images.githubusercontent.com/57980671/99140427-9737a400-2674-11eb-986b-473587e6d037.png)
- edit file named.conf.local pada server MOJOKERTO

![image](https://user-images.githubusercontent.com/57980671/99141195-6eff7380-267b-11eb-9c44-d31435907748.png)
- lalu buat direktori baru dengan nama delegasi, kemudian cp db.local ke gunung.semerud05.pw di direktori tersebut
- kemudian edit file tersebut seperti gambar dibawah

![image](https://user-images.githubusercontent.com/57980671/99141220-bede3a80-267b-11eb-94db-f189555d3e98.png)
- kemudian restart bind9
- lalu lakukan test ping gunung.semerud05.pw pada client GRESIK

![image](https://user-images.githubusercontent.com/57980671/99141248-12e91f00-267c-11eb-9182-78a092058af5.png)

### Nomor 7
Membuat Subdomain dengan nama naik.gunung.semerud05.pw

_**Langkah**_
- Langkah nomor 7 sama seperti nomor 6, tetapi tambahkan konfigurasi pada file named.conf.local di server MOJOKERTO

![image](https://user-images.githubusercontent.com/57980671/99141274-678c9a00-267c-11eb-9bb8-f7268ede62de.png)
- kemudian restart bind9
- lalu lakukan test ping naik.gunung.semerud05.pw pada client GRESIK

![image](https://user-images.githubusercontent.com/57980671/99141291-96a30b80-267c-11eb-87ad-8fc399105d2a.png)
