# Tugas 1 – Komunikasi Data dan Jaringan Komputer
## Subnetting VLSM & CIDR  

| Nama                   | NRP        |
| ---------------------- | ---------- |
| S. Farhan Baig | 5027241097 |


---

## Deskripsi Tugas
Tugas ini bertujuan untuk merancang dan mengonfigurasi jaringan komputer pada Yayasan Pendidikan ARA yang terdiri dari Kantor Pusat dan Kantor Cabang.  
Perancangan jaringan dilakukan menggunakan Cisco Packet Tracer dengan penerapan Subnetting VLSM dan CIDR.

---

## Base Network
Base network ditentukan berdasarkan rumus:

10.(NRP mod 256).0.0

Perhitungan:
5027241097 mod 256 = 137

Base Network:
10.137.0.0

Supernet yang digunakan:
10.137.0.0/22

---

## Kebutuhan Host

| Unit Kerja | Jumlah Host |
|-----------|-------------|
| Sekretariat | 380 |
| Bidang Kurikulum | 220 |
| Bidang Guru & Tendik | 95 |
| Bidang Sarana Prasarana | 45 |
| Bidang Pengawas Sekolah (Cabang) | 18 |
| Server & Admin | 6 |
| Jaringan Gabungan | 6 |
| Link Antar Router | 2 |

---

## Subnetting VLSM

| Subnet | Network Address | Prefix | Subnet Mask | Host Range | Broadcast | Gateway |
|-------|----------------|--------|-------------|------------|-----------|---------|
| Sekretariat | 10.137.0.0 | /23 | 255.255.254.0 | 10.137.0.1 - 10.137.1.254 | 10.137.1.255 | 10.137.0.1 |
| Bidang Kurikulum | 10.137.2.0 | /24 | 255.255.255.0 | 10.137.2.1 - 10.137.2.254 | 10.137.2.255 | 10.137.2.1 |
| Bidang Guru & Tendik | 10.137.3.0 | /25 | 255.255.255.128 | 10.137.3.1 - 10.137.3.126 | 10.137.3.127 | 10.137.3.1 |
| Bidang Sarana Prasarana | 10.137.3.128 | /26 | 255.255.255.192 | 10.137.3.129 - 10.137.3.190 | 10.137.3.191 | 10.137.3.129 |
| Bidang Pengawas Sekolah | 10.137.3.192 | /27 | 255.255.255.224 | 10.137.3.193 - 10.137.3.222 | 10.137.3.223 | 10.137.3.193 |
| Server & Admin | 10.137.3.224 | /29 | 255.255.255.248 | 10.137.3.225 - 10.137.3.230 | 10.137.3.231 | 10.137.3.225 |
| Jaringan Gabungan | 10.137.3.232 | /29 | 255.255.255.248 | 10.137.3.233 - 10.137.3.238 | 10.137.3.239 | 10.137.3.233 |
| Tunnel WAN | 10.137.3.240 | /30 | 255.255.255.252 | 10.137.3.241 - 10.137.3.242 | 10.137.3.243 | 10.137.3.241 |

---
## Toplogi VLSM
<img width="1283" height="778" alt="image" src="https://github.com/user-attachments/assets/45186f0c-8b3e-42b3-b873-bcc3613488de" />

---
## VLSM Tree


---

## CIDR

### CIDR Level A
- 10.137.0.0/23
- 10.137.2.0/24
- 10.137.3.0/25
- 10.137.3.128/26
- 10.137.3.192/27
- 10.137.3.224/29
- 10.137.3.232/29
- 10.137.3.240/30

### CIDR Level B
- 10.137.0.0/22
- 10.137.3.192/26

### CIDR Root
10.137.0.0/21

---

## CIDR Tree


---

## Topologi Jaringan
<img width="1212" height="705" alt="image" src="https://github.com/user-attachments/assets/4b5d6bf4-9582-4c97-b74c-27e24e589eb4" />


---



## Kesimpulan
Subnetting menggunakan VLSM membuat penggunaan alamat IP lebih efisien, sedangkan CIDR digunakan untuk menggabungkan beberapa subnet menjadi supernet agar routing lebih sederhana.
