# 📘 Belajar ESP32 dengan Arduino IDE — **Modul 0: Panduan Lengkap**

> **Tujuan dokumen ini:** memberi gambaran lengkap tentang cakupan kursus, alur belajar, daftar modul & unit, proyek praktik, serta sumber daya pendukung. Tetap ramah untuk pembaca awam, namun **tidak disederhanakan berlebihan**.

## 🧭 Cara Mengikuti Kursus
- **Modul bersifat independen**, boleh loncat topik sesuai minat.  
- **Wajib mulai dari Modul 1** untuk menyiapkan _boards core_ ESP32 di Arduino IDE. Tanpa ini, banyak contoh tidak akan berjalan.  
- Setiap _Unit_ menyediakan **kode sumber, skema rangkaian, dan bahan pendukung**. Anda bisa mengunduh per unit atau **clone seluruh repositori GitHub kursus** untuk akses cepat.  
- Simpan catatan pribadi: versi Arduino IDE, versi core ESP32, tipe board (mis. `DOIT ESP32 DEVKIT V1`), port, dan trik _troubleshooting_.

## 📦 Sumber Daya & Unduhan
- **Kode & Skema:** tersedia per unit dan dalam satu repositori GitHub kursus.  
- **Referensi pinout & panduan tambahan:** lihat bagian **Extra Units** di bawah.  
- **Komunitas/dukungan:** forum & grup diskusi (opsional) untuk berbagi masalah dan solusi.

---

# 🗺️ Struktur Kursus (8 Modul + 4 Proyek + Extra Units)

Di bawah ini adalah daftar lengkap **Modul** dan **Unit** yang dicakup kursus.

## Modul #1 — Getting Started with ESP32
Pengantar papan ESP32: fitur utama, cara menggunakan board di kursus ini, dan **menyiapkan Arduino IDE** agar siap _upload sketch_. **Ikuti modul ini terlebih dahulu.**  
**Unit:**  
1. **Introducing ESP32** — karakteristik, fitur inti, varian.  
2. **Installing the ESP32 Board in Arduino IDE (Windows, macOS, Linux)** — pemasangan core/boards.  
3. **How To Use Your ESP32 Board with this Course** — kebiasaan kerja & alur praktik.  
4. **Make the ESP32 Breadboard Friendly** — tips fisik agar mudah digunakan di breadboard.

## Modul #2 — Exploring the ESP32 GPIO Pins
Dasar antarmuka hardware: input/output digital, sensor sentuh, PWM, ADC, sensor hall, interupsi, hingga memori flash untuk menyimpan data permanen.  
**Unit:**  
1. **ESP32 Digital Inputs and Outputs**  
2. **ESP32 Touch Sensor**  
3. **ESP32 Pulse‑Width Modulation (PWM)**  
4. **ESP32 Reading Analog Inputs**  
5. **ESP32 Hall Effect Sensor**  
6. **ESP32 with PIR Motion Sensor — Interrupts and Timers**  
7. **ESP32 Flash Memory — Store Permanent Data (Write and Read)**  
8. **Other ESP32 Sketch Examples**

## Modul #3 — ESP32 Deep Sleep Mode
Teknik **hemat daya** untuk aplikasi berbasis baterai + variasi cara membangunkan ESP32.  
**Unit:**  
1. **ESP32 Deep Sleep Mode**  
2. **Deep Sleep — Timer Wake Up**  
3. **Deep Sleep — Touch Wake Up**  
4. **Deep Sleep — External Wake Up**

## Modul #4 — Building Web Servers with the ESP32
Membangun **web server** untuk kontrol & pemantauan, menyisipkan HTML/CSS, membuat autentikasi, akses dari luar jaringan lokal, _async update_, hingga kontrol servo/RGB LED.  
**Unit:**  
1. **ESP32 Web Server — Introduction**  
2. **ESP32 Web Server — Control Outputs**  
3. **ESP32 Web Server — HTML and CSS Basics (Part 1/2)**  
4. **ESP32 Web Server — HTML in Arduino IDE (Part 2/2)**  
5. **ESP32 Web Server — Control Outputs (Relay)**  
6. **Making Your ESP32 Web Server Password Protected**  
7. **Accessing the ESP32 Web Server From Anywhere**  
8. **ESP32 Web Server — Display Sensor Readings**  
9. **ESP32 Control Servo Motor Remotely (Web Server)**  
10. **ESP32 Color Picker Web Server for RGB LED Strip**  
11. **Asynchronous Temperature and Humidity Web Server with Auto Update**  
12. **Asynchronous Web Server — Control Outputs**

## Modul #5 — ESP32 Bluetooth Low Energy (BLE) & Bluetooth Classic
Mengenal BLE dan Bluetooth Classic di ESP32: **scan perangkat**, **server–client BLE**, pertukaran data, serta integrasi dengan **Android**.  
**Unit:**  
1. **ESP32 Bluetooth Low Energy (BLE) — Introduction**  
2. **Bluetooth Low Energy — Notify and Scan**  
3. **ESP32 BLE Server and Client (Part 1/2)**  
4. **ESP32 BLE Server and Client (Part 2/2)**  
5. **ESP32 with Bluetooth Classic and Android Smartphone**

## Modul #6 — LoRa Technology with the ESP32
Mengenal **LoRa** untuk komunikasi jarak jauh antar-perangkat IoT dan opsi perluasan jaringan.  
**Unit:**  
1. **ESP32 with LoRa — Introduction**  
2. **ESP32 LoRa Sender and Receiver**  
3. **Further Reading about LoRa Gateways**  
4. **LoRa — Where to Go Next?**

## Modul #7 — ESP32 with MQTT
Membangun komunikasi **publish/subscribe** (IoT) antara ESP32, integrasi **Mosquitto** (broker MQTT) dan **Node‑RED** (dashboard).  
**Unit:**  
1. **ESP32 with MQTT — Introduction**  
2. **Installing Mosquitto MQTT Broker on a Raspberry Pi**  
3. **MQTT Project — MQTT Client ESP32 #1**  
4. **MQTT Project — MQTT Client ESP32 #2**  
5. **Installing Node‑RED and Node‑RED Dashboard on a Raspberry Pi**  
6. **Connect ESP32 to Node‑RED using MQTT**

## Modul #8 — ESP‑NOW Communication Protocol
Protokol koneksi‑less dari Espressif untuk pengiriman paket singkat, mendukung **topologi satu‑ke‑banyak** dan **banyak‑ke‑satu**, serta integrasi dengan Wi‑Fi.  
**Unit:**  
1. **ESP‑NOW: Getting Started**  
2. **ESP‑NOW Two‑Way Communication Between ESP32**  
3. **ESP‑NOW Send Data to Multiple Boards (one‑to‑many)**  
4. **ESP‑NOW Receive Data from Multiple Boards (many‑to‑one)**  
5. **ESP‑NOW Web Server Sensor Dashboard (ESP‑NOW + Wi‑Fi)**

---

# 🔧 Proyek Praktik (End‑to‑End)

## Proyek #1 — ESP32 Wi‑Fi Multisensor
Membangun perangkat multisensor Wi‑Fi: **PIR**, **LDR**, **DHT22**, **relay**, **RGB LED**, lengkap dengan web server untuk mode kontrol berbeda.  
**Unit:**  
1. **ESP32 Wi‑Fi Multisensor — Temperature, Humidity, Motion, Luminosity, and Relay Control**  
2. **ESP32 Wi‑Fi Multisensor — How the Code Works?**

## Proyek #2 — Remote Controlled Wi‑Fi Car Robot
Membuat **robot mobil** yang dikendalikan melalui Wi‑Fi, termasuk perakitan rangka/chassis dan opsi **Access Point (AP)**.  
**Unit:**  
1. **Remote Controlled Wi‑Fi Car Robot — Part 1/2**  
2. **Remote Controlled Wi‑Fi Car Robot — Part 2/2**  
3. **Assembling the Smart Robot Car Chassis Kit**  
4. **Extra — Access Point (AP) For Wi‑Fi Car Robot**

## Proyek #3 — BLE Android App (MIT App Inventor)
Membangun **aplikasi Android** yang terhubung ke ESP32 via BLE untuk kontrol output dan pembacaan sensor.  
**Unit:**  
1. **ESP32 BLE Android Application — Control Outputs and Display Sensor Readings**  
2. **Bluetooth Low Energy (BLE) Android Application with MIT App Inventor 2 — How the App Works?**

## Proyek #4 — LoRa Long‑Range Sensor Monitoring
Sistem **off‑grid** pemantauan kelembapan tanah & suhu, **pengirim bertenaga surya**, dan penerima di dalam ruangan; analisis data akhir.  
**Unit:**  
1. **LoRa Long Range Sensor Monitoring and Data Logging**  
2. **ESP32 LoRa Sender**  
3. **ESP32 LoRa Receiver**  
4. **ESP32 LoRa Sender Solar Powered**  
5. **Final Tests, Demonstration, and Data Analysis**

---

# ➕ Extra Units (Modul Tambahan)
- **ESP32 Static/Fixed IP Address**  
- **ESP32 Dual Core — Create Tasks**  
- **ESP32 SPIFFS (SPI Flash File System)**  
- **Build an ESP32 Web Server using Files from Filesystem (SPIFFS)**  
- **ESP32 Client‑Server Wi‑Fi Communication Between Two Boards**  
- **ESP32 HTTP GET (OpenWeatherMap and ThingSpeak)**  
- **ESP32 HTTP POST (ThingSpeak and IFTTT.com)**  
- **ESP32 Pinout Reference: Which GPIO pins should you use?**

---

# 🧰 Kebutuhan Perangkat & Perangkat Lunak

## Perangkat Keras (umum untuk sebagian besar unit)
- **Papan ESP32** (mis. DevKit/NodeMCU ESP32, pilih varian yang didukung _boards core_).  
- **Kabel USB** (Micro‑USB/USB‑C sesuai papan).  
- **Breadboard & jumper**; **LED + resistor**; **tombol push**; **sensor** (PIR, LDR/photocell, DHT22, dsb. — sesuai unit).  
- **Komponen tambahan**: relay 5V, **servo**, modul **LoRa** (untuk Modul #6 & Proyek #4), RGB LED strip (untuk unit Web Server RGB), **catu daya** & **baterai** (untuk proyek _portable_).  

> **Catatan:** Daftar komponen bervariasi per modul/proyek. Untuk daftar terlengkap, rujuk **appendix/daftar parts** dari kursus sumber (atau _sheet_ inventaris Anda sendiri).

## Perangkat Lunak
- **Arduino IDE (versi stabil terbaru)**.  
- **ESP32 Boards Core** dipasang via **Boards Manager** (Windows/macOS/Linux).  
- **Driver USB** (mis. CP2102/CH340) bila diperlukan.  
- **Raspberry Pi (opsional)** untuk Modul #7 (Mosquitto & Node‑RED).  
- **MIT App Inventor** (opsional) untuk Proyek #3 (BLE Android App).  

---

# 🧪 Uji Lingkungan Kilat (Disarankan)
Sebelum lanjut, pastikan upload _sketch_ bekerja dengan baik (contoh **Blink** di LED bawaan).  
Jika gagal, cek: _Board_ & _Port_ di menu **Tools**; tekan **BOOT/EN** saat _flashing_ (pada beberapa board); pastikan driver terpasang.

---

# 📚 Konvensi Penulisan di E‑Book Ini (untuk konsistensi)
- **Setiap modul**: tujuan belajar → prasyarat → peta materi → praktik langkah‑demi‑langkah → troubleshooting → latihan → rangkuman.  
- **Kode**: disertai komentar singkat, nama pin & parameter dibuat mudah diganti.  
- **Istilah teknis**: tetap dicantumkan **lengkap** dan diberi penjelasan ringkas saat pertama kali muncul.  
- **Tautan sumber**: sediakan rujukan kode/skema agar pembaca bisa langsung mencoba.  

---

# ✅ Ringkasan
- Kursus mencakup **8 modul**, **4 proyek**, dan **extra units** yang memperkaya praktik (BLE, MQTT, ESP‑NOW, Web Server, LoRa).  
- **Mulai dari Modul #1** untuk setup Arduino IDE & boards core ESP32.  
- Unduh **kode & skema** per unit atau sekaligus dari repositori kursus.  
- Susun catatan dan checklist personal agar percobaan berikutnya lebih cepat dan rapi.
