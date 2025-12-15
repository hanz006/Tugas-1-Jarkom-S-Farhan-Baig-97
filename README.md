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

### Subnetting
Supernet yang digunakan:
10.137.0.0/22

Total Host: 778 host


| **Nama Subnet**                    | **Host** | **Host + Gateway** | **Netmask** |
|-----------------------------------|---------:|--------------------:|:-----------:|
| Sekretariat                       |     380 |                381  | /23         |
| Bidang Kurikulum                  |     220 |                221  | /24         |
| Bidang Guru & Tendik              |      95 |                 96  | /25         |
| Bidang Sarana Prasarana           |      45 |                 46  | /26         |
| Bidang Pengawas Sekolah           |      18 |                 19  | /27         |
| Server & Admin                    |       6 |                  7  | /28         |
| Jaringan Gabungan                 |       6 |                  6  | /29         |
| Tunnel (Link Pusat dan Cabang)    |       2 |                  2  | /30         |
| TOTAL                             |         |              **778**| **/22**     |

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
<img width="744" height="816" alt="image" src="https://github.com/user-attachments/assets/edeb41be-5fe8-4713-b9d7-82e4f1c9b4c5" />

---

## Topologi CIDR
<img width="1212" height="705" alt="image" src="https://github.com/user-attachments/assets/4b5d6bf4-9582-4c97-b74c-27e24e589eb4" />

---

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
<img width="1196" height="696" alt="image" src="https://github.com/user-attachments/assets/18a415de-bc21-49c0-bb35-2f3327e9ddf9" />



---
## Subnetting CIDR

| Subnet | Prefix | Deskripsi Jaringan | Network Address | Subnet Mask | Range Host Aktif | Broadcast Address | Gateway |
|------|--------|--------------------|-----------------|-------------|------------------|-------------------|---------|
| A1 | /23 | Sekretariat | 10.137.0.0 | 255.255.254.0 | 10.137.0.1 – 10.137.1.254 | 10.137.1.255 | 10.137.0.1 |
| A2 | /24 | Bidang Kurikulum | 10.137.2.0 | 255.255.255.0 | 10.137.2.1 – 10.137.2.254 | 10.137.2.255 | 10.137.2.1 |
| A3 | /25 | Bidang Guru & Tendik | 10.137.3.0 | 255.255.255.128 | 10.137.3.1 – 10.137.3.126 | 10.137.3.127 | 10.137.3.1 |
| A4 | /26 | Bidang Sarana Prasarana | 10.137.3.128 | 255.255.255.192 | 10.137.3.129 – 10.137.3.190 | 10.137.3.191 | 10.137.3.129 |
| A5 | /27 | Bidang Pengawas Sekolah | 10.137.3.192 | 255.255.255.224 | 10.137.3.193 – 10.137.3.222 | 10.137.3.223 | 10.137.3.193 |
| A6 | /29 | Server & Admin | 10.137.3.224 | 255.255.255.248 | 10.137.3.225 – 10.137.3.230 | 10.137.3.231 | 10.137.3.225 |
| A7 | /29 | Jaringan Gabungan / Backbone | 10.137.3.232 | 255.255.255.248 | 10.137.3.233 – 10.137.3.238 | 10.137.3.239 | 10.137.3.233 |
| A8 | /30 | Link Antar Router (WAN) | 10.137.3.240 | 255.255.255.252 | 10.137.3.241 – 10.137.3.242 | 10.137.3.243 | 10.137.3.241 |

---


## Kesimpulan
Subnetting menggunakan VLSM membuat penggunaan alamat IP lebih efisien, sedangkan CIDR digunakan untuk menggabungkan beberapa subnet menjadi supernet agar routing lebih sederhana.
