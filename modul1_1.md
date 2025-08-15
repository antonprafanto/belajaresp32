# 🔰 Modul 1 — Unit 1: **Mengenal ESP32 (Introducing ESP32)**

> Unit ini memperkenalkan **apa itu ESP32**, fitur kunci yang membuatnya populer, spesifikasi teknis penting, perbedaan ESP32 vs ESP8266, jenis **development board**, kriteria pemilihan papan yang tepat, serta gambaran **cara pemrograman** yang didukung. Materi dirancang **lengkap & komprehensif** namun tetap ramah untuk pembaca awam.

---

## 🎯 Tujuan Pembelajaran
Setelah menyelesaikan unit ini, Anda mampu:
- Menjelaskan **konsep ESP32** sebagai SoC (System-on-a-Chip) dengan Wi‑Fi dan Bluetooth terintegrasi.
- Menguraikan **fitur utama** ESP32 (biaya, konsumsi daya, konektivitas, prosesor, dan periferal I/O).
- Mengidentifikasi **spesifikasi teknis** (CPU, memori, _wireless_, periferal, keamanan perangkat keras).
- Membedakan ESP32 dan **ESP8266** pada aspek inti (kinerja, GPIO, ADC, Bluetooth, biaya).
- Memilih **ESP32 development board** yang sesuai kebutuhan proyek awal.
- Memahami opsi **bahasa & _framework_ pemrograman** untuk ESP32 serta fokus kursus ini.

> Sumber utama unit ini diambil dari eBook kursus yang Anda unggah. fileciteturn1file0

---

## 1) Gambaran Umum ESP32
**ESP32** adalah seri **mikrokontroler SoC** berbiaya rendah dan hemat daya dari **Espressif** yang mengintegrasikan **Wi‑Fi** dan **Bluetooth** (BLE & Classic), umumnya dengan **prosesor dual‑core**. Jika Anda pernah memakai **ESP8266**, ESP32 adalah penerusnya dengan fitur lebih kaya dan performa lebih tinggi. fileciteturn1file0

### Mengapa ESP32 populer?
- **Biaya rendah**: tersedia mulai kisaran **$6** sehingga terjangkau untuk edukasi dan prototipe.  
- **Hemat daya**: mendukung mode **deep sleep** untuk aplikasi baterai.  
- **Wi‑Fi**: dapat **terhubung ke jaringan** (station mode) atau **membuat jaringan sendiri** (access point) — ideal untuk **IoT** & **Home Automation**.  
- **Bluetooth**: mendukung **BLE** dan **Classic**, membuka beragam skenario integrasi ponsel/alat lain.  
- **Dual‑core**: mayoritas varian menyertakan **2 inti Xtensa 32‑bit LX6** (core 0 & core 1).  
- **Periferal I/O kaya**: **capacitive touch, ADC, DAC, UART, SPI, I²C, I²S, PWM, RMII**, dsb.  
- **Mendukung Arduino‑style**: dapat diprogram dengan **Arduino C/C++**.  
- **Dukungan MicroPython**: tersedia _firmware_ **MicroPython** untuk alternatif pemrograman (di luar cakupan kursus ini). fileciteturn1file0

> **Catatan:** Meskipun mudah diprogram ala Arduino, ESP32 adalah SoC “serius” dengan fitur industri seperti akselerator AES dan SSL/TLS di perangkat keras. fileciteturn1file0

---

## 2) Spesifikasi Teknis Ringkas (Chip ESP32)
> Rangkuman berikut menyorot parameter penting; untuk detail penuh rujuk _datasheet_ resmi. fileciteturn1file0

| Kategori | Rincian Utama |
|---|---|
| **Prosesor** | **Tensilica Xtensa LX6 Dual‑Core 32‑bit**, hingga **160–240 MHz** |
| **Wi‑Fi** | 2.4 GHz, hingga **150 Mbps** (HT40) |
| **Bluetooth** | **BLE** dan **Classic** (4.2) |
| **Memori internal** | **ROM 448 KB**, **SRAM ~520 KB**, **RTC fast/slow SRAM masing‑masing 8 KB** |
| **eFuse** | **1 Kbit** (256 bit untuk sistem/MAC; 768 bit untuk aplikasi, mis. **Flash‑Encryption**, **Chip‑ID**) |
| **Flash terintegrasi (varian)** | 0 MiB / 2 MiB / 4 MiB tergantung tipe chip (mis. **D0WD**, **D2WD**, **PICO‑D4**) |
| **Daya rendah** | Dukungan konversi **ADC** saat **deep sleep** |
| **Periferal** | **Touch**, **ADC**, **DAC**, **UART**, **SPI**, **I²C**, **I²S**, **RMII**, **PWM** |
| **Keamanan HW** | Akselerator **AES**, **SSL/TLS** |

fileciteturn1file0

> **Tip praktis:** untuk proyek pemula, fokus pada **GPIO, ADC, PWM, I²C/SPI**. Fitur lain seperti **RMII** (Ethernet PHY) dan **I²S** (audio) berguna pada proyek menengah/lanjutan. fileciteturn1file0

---

## 3) ESP32 vs ESP8266 — Perbedaan Utama
- **Kinerja**: ESP32 **lebih cepat** dan umumnya **dual‑core**; ESP8266 **single‑core**.  
- **GPIO**: ESP32 menyediakan **lebih banyak GPIO** dengan **fungsi multipurpose**.  
- **ADC**: ESP32 memiliki **hingga 18 channel analog**; ESP8266 hanya **1 pin ADC 10‑bit**.  
- **Bluetooth**: ESP32 mendukung **BLE + Classic**; ESP8266 **tidak**.  
- **Biaya**: ESP32 sedikit lebih mahal (± **$6–$12**) dibanding ESP8266 (± **$4–$6**), tergantung varian & vendor. fileciteturn1file0

> **Kapan pilih ESP8266?** Jika proyek **sangat sederhana** dan biaya **sangat ketat**. Namun untuk fleksibilitas jangka panjang, **ESP32** biasanya pilihan yang lebih baik. fileciteturn1file0

---

## 4) Development Board ESP32
Istilah “**ESP32**” sering dipakai untuk menyebut **chip** maupun **development board**. Untuk belajar dan prototipe, gunakan **development board** karena sudah memiliki:
- **Regulator tegangan** & **USB‑to‑UART** (agar mudah diberi daya dan _upload_ kode).  
- **Pin header** untuk akses GPIO.  
- **LED indikator** (power & status), **antena Wi‑Fi**, dan kadang **fitur ekstra** (sensor, OLED, kamera/ESP32‑CAM, dsb.). fileciteturn1file0

### Cara Memilih Development Board (Kriteria Utama)
1. **USB‑to‑UART & Regulator** — memastikan **kemudahan sambung ke PC** & stabilitas daya.  
2. **Tombol BOOT & RESET/EN** — memudahkan masuk **flashing mode** & **restart** (beberapa papan _auto‑boot_).  
3. **Dokumentasi pinout** — **wajib** untuk menghindari salah sambung GPIO.  
4. **Antena/antarmuka antena** — **eksternal antenna** meningkatkan jangkauan Wi‑Fi.  
5. **Konektor baterai** — berguna untuk proyek **portable**.  
6. **Fitur ekstra** — pilih sesuai kebutuhan (OLED, **LoRa**, **SIM800**, kamera, _battery holder_). fileciteturn1file0

### Rekomendasi untuk Pemula
- **ESP32 DEVKIT DOIT** (seri **V1**, varian **30/36/38 pin**). Dipakai luas di contoh‑contoh praktikum, **stabil**, dan dokumentasi melimpah.  
- Alternatif populer: **Adafruit Feather ESP32**, **SparkFun ESP32 Thing**, **NodeMCU‑32S**, **Wemos LoLin32**, dll. fileciteturn1file0

> **Catatan kompatibilitas:** Materi kursus kompatibel bagi sebagian besar development board ESP32. Jika memakai papan berbeda, sesuaikan **pinout** dan perhatikan **chip USB‑UART** yang digunakan. fileciteturn1file0

---

## 5) Studi Papan Referensi — **ESP32 DEVKIT V1 DOIT**
Papan referensi yang digunakan di kursus ini adalah **ESP32 DEVKIT V1 DOIT** (contoh varian **36 GPIO**). Fitur umum:  
- **Antarmuka micro‑USB** untuk **daya** dan **unggah kode**.  
- **Chip USB‑UART**: **CP2102** (alternatif populer: **CH340**). **Instal driver** yang sesuai OS Anda.  
- **Tombol**: **RESET/EN** dan **BOOT**.  
- **LED bawaan** (biru) biasanya ke **GPIO 2**; **LED power** (merah) menyala saat papan diberi daya. fileciteturn1file0

**Ringkasan Spesifikasi (DOIT V1)**
| Parameter | Nilai |
|---|---|
| **Inti CPU** | **2 (dual‑core)** |
| **Wi‑Fi** | **2.4 GHz** hingga **150 Mbit/s** |
| **Bluetooth** | **BLE** & **Legacy (Classic)** |
| **Arsitektur** | **32‑bit** |
| **Frekuensi** | hingga **240 MHz** |
| **RAM** | **512 KB** |
| **Jumlah pin** | **30/36/38** (bergantung model) |
| **Periferal** | **Touch, ADC, DAC, I²C, UART, CAN 2.0, SPI, I²S, RMII, PWM** |

> Jumlah **GPIO tersedia** bervariasi menurut model. Rujuk **diagram pinout** papan Anda sebelum merangkai. fileciteturn1file0

---

## 6) Panduan Singkat **GPIO & Pinout**
- **ESP32** memiliki hingga **48 pin** (chip), namun **tidak semua** diekspos pada tiap papan.  
- Banyak pin bersifat **multipurpose**; pemetaan **UART/I²C/SPI** dapat diatur dari **kode** (fitur _pin multiplexing_).  
- Jika **tidak diatur** khusus, pin mengikuti **fungsi default** pabrikan.  
- Beberapa pin memiliki **karakteristik khusus** (mis. _strapping pins_, _input-only_, _pulldown_ internal) sehingga **tidak cocok** untuk fungsi tertentu.  
- **Rekomendasi**: **cetak pinout** papan (versi **30** atau **36** pin) dan **tempel** di meja kerja Anda. fileciteturn1file0

> **Praktik baik:** Buat **lembar referensi pin** proyek Anda (kolom: GPIO, fungsi, arah, tegangan, catatan). Ini mengurangi kesalahan kabel & mempercepat _debugging_. fileciteturn1file0

---

## 7) Bagaimana Memrogram ESP32?
ESP32 mendukung berbagai **bahasa/kerangka kerja**:
- **Arduino C/C++** dengan **Arduino core for ESP32** (fokus eBook ini).  
- **Espressif IDF** (_IoT Development Framework_).  
- **MicroPython**.  
- **JavaScript**, **LUA**, dll.  

> Dalam kursus ini, kita fokus pada **Arduino‑style C/C++** karena komunitas besar dan _learning curve_ yang bersahabat bagi pemula. Untuk **MicroPython**, tersedia eBook terpisah. fileciteturn1file0

---

## 📌 Ringkasan Unit
- **ESP32** = SoC Wi‑Fi + Bluetooth yang **murah**, **hemat daya**, dan **kaya periferal**.  
- **Lebih unggul** dari ESP8266 pada kinerja, jumlah GPIO, ADC, dan Bluetooth.  
- Pilih **development board** dengan USB‑UART & dokumentasi **pinout** yang baik; **ESP32 DEVKIT DOIT** sangat direkomendasikan untuk pemula.  
- Pahami **pinout & multiplexing** sebelum merangkai.  
- Kursus ini memakai **Arduino C/C++** untuk mempercepat praktik.

---

## 🧪 Latihan Singkat (Opsional)
1) Sebutkan **tiga alasan** mengapa ESP32 cocok untuk proyek IoT pemula.  
2) Cari **chip USB‑UART** pada papan Anda (CP2102/CH340) dan **unduh driver** yang sesuai OS.  
3) Cetak **pinout** papan Anda (30/36 pin) dan tandai **GPIO** yang akan dipakai pada proyek pertama Anda.

---

## ❓ FAQ Mini
**Q:** Apakah semua ESP32 pasti dual‑core?  
**A:** **Mayoritas ya**, namun ada varian khusus. Cek **_datasheet_** papan Anda. fileciteturn1file0

**Q:** Apakah saya bisa langsung pakai MicroPython?  
**A:** Bisa. Namun materi kursus ini fokus **Arduino core**. Jika tertarik MicroPython, gunakan eBook khususnya. fileciteturn1file0

**Q:** LED bawaan terhubung ke pin berapa?  
**A:** Umumnya **GPIO 2** pada papan **DOIT V1**, cocok untuk uji **Blink**. Cek kembali dokumentasi papan Anda. fileciteturn1file0

---

> **Lanjut ke Unit 2:** Instalasi **ESP32 Board** di **Arduino IDE** (Windows/macOS/Linux) dan uji **upload** pertama Anda. fileciteturn1file0
