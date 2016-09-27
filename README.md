# PKSJ - Tugas 1

## Pendahuluan

**Anggota Kelompok**

| NRP         | Nama                     |
|-------------|--------------------------|
| 5113100050  | Freddy Hermawan Y        |
| 5113100109  | Daniel Fablius           |
| 5113100113  | Muhamad Luthfie La Roeha |

#### Penjelasan Tugas
**Uji penetrasi 1 :**
* Instal sebuah virtual OS dengan Ubuntu server
* Instal SSH server dengan konfigurasi default
* Instal satu lagi virtual OS dengan OS bebas, misalnya Kali Linux atau Ubuntu Desktop
* Pastikan tools untuk SSH brute force attack sudah terinstal
* Lakukan uji penetrasi 1: dengan THC-Hydra atau Ncrack dan catat hasil uji penetrasi 

**Uji penetrasi 2:**
* Instal fail2ban pada Ubuntu server yang telah diinstal SSH servernya
* Konfigurasilah SSH server agar tidak default lagi
* Lakukan uji penetrasi 2 dengan tools yang sama dan catat hasilnya


## Dasar Teori

**1. OS yang digunakan**

* **Kali Linux** adalah 

* **Ubuntu Server** adalah 

**2. Tools yang digunakan**

*Cracking Tool*

* **Hydra**, adalah 
* **BELUM SELESAI**, adalah

*Defending Tool*

* **Fail2Ban** adalah 


## Persiapan

#### 1. Langkah Instalasi Ubuntu Server
  1.
  2.
  3.

#### 2. Langkah Instalasi Kali Linux

  1. Langkah 1
  2. Langkah 2

#### 3. Penambahan User

1. Tambahkan *user* baru dengan nama *user* `lutfi` dan password `dolphins` dengan cara :
```
sudo adduser lutfi
```
2. Setelah itu sistem akan meminta password untuk *user* `lutfi`. Masukkan password `dolphins`.

#### 4. Konfigurasi Server
> Server IP : 10.151.36.109
>
> username : server
> password : pksj123!
>
> username : lutfi
> password : dolphins

## Uji Penetrasi 1

#### 1. Uji Penetrasi dengan Hydra

Pada tahap ini, kami melakukan 2 skenario uji penetrasi, yaitu :
1. Brute Force User `lutfi` menggunakan list password [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2)
2. Brute Force User `server` menggunakan list password [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2)

**Skenario 1** : Brute Force user `lutfi` menggunakan list password [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2)
- Download file [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2) dengan cara :
```
wget http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2
```
- Extract file tersebut dengan cara :
```
bzip2 -d 500-worst-passwords.txt.bz2
```
- Lalu, gunakan *Hydra* untuk melakukan Brute Force Attack pada user `lutfi` dengan cara :
```
hydra -l lutfi -P 500-worst-passwords.txt 10.151.36.109 ssh
```
 Pastikan pada direktori yang aktif terdapat file **500-worst-passwords.txt**
- Tools `Hydra` akan melakukan Brute Force Attack dengan menggunakan username `lutfi` dan list password yang ada pada [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2) pada alamat IP `10.151.36.109`
- Tunggu hingga proses Brute Force selesai dilakukan. Seperti dibawah ini :

![Hasil Skenario 1](Hydra/Skenario1.png)

**Skenario 2** : Brute Force User `server` menggunakan list password [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2)
- Lalu, gunakan *Hydra* untuk melakukan Brute Force Attack pada user `lutfi` dengan cara :
```
hydra -l lutfi -P 500-worst-passwords.txt 10.151.36.109 ssh
```
 Pastikan pada direktori yang aktif terdapat file **500-worst-passwords.txt**
- Tools `Hydra` akan melakukan Brute Force Attack dengan menggunakan username `server` dan list password yang ada pada [500-worst-password.txt](http://downloads.skullsecurity.org/passwords/500-worst-passwords.txt.bz2) pada alamat IP `10.151.36.109`
- Tunggu hingga proses Brute Force selesai dilakukan.
- Karena password yang dipakai tidak ada pada list password, maka akan tampil seperti dibawah ini :
![Hasil Skenario 2](Hydra/Skenario2.png)
