# 🛠️ Modul 1 — Unit 2: **Instalasi ESP32 di Arduino IDE (Windows, macOS, Linux)**

> Unit ini memandu Anda menginstal **Arduino IDE**, menambahkan **ESP32 Boards Core** melalui *Boards Manager*, serta **menguji instalasi** dengan contoh **WiFi Scan**. Disertai **troubleshooting** umum (gagal upload, COM port tidak muncul, kabel USB hanya-charging). Materi bersumber dari eBook yang Anda unggah. fileciteturn2file0

---

## 🎯 Tujuan Pembelajaran
Setelah menyelesaikan unit ini, Anda mampu:
- Memasang **Arduino IDE** yang sesuai (legacy 1.8.x atau versi 2.x) dan memahami catatan kompatibilitas untuk ESP32. fileciteturn2file0
- Menambahkan **URL Boards Manager** ESP32 dan **menginstal “ESP32 by Espressif Systems”**. fileciteturn2file0
- Melakukan **uji cepat** menggunakan contoh **WiFi Scan** (memilih board, port, upload, dan memantau hasil). fileciteturn2file0
- Menangani masalah umum: **“Failed to connect… Connecting…”**, **COM port tidak muncul**, dan **kabel USB tanpa data**. fileciteturn2file0

---

## 🔎 Ringkasan Satu Halaman (Quick Start)
1. **Unduh & jalankan Arduino IDE** (disarankan *Windows ZIP* untuk Windows). *Catatan sumber: saat penulisan, disarankan **legacy 1.8.19** untuk ESP32 bila Anda menemui bug di v2.x.* fileciteturn2file0  
2. **File → Preferences** → isi **Additional Boards Manager URLs** dengan:  
   `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`  fileciteturn2file0  
   *(Jika juga pakai ESP8266, pisahkan dengan koma dan tambahkan: `http://arduino.esp8266.com/stable/package_esp8266com_index.json`)* fileciteturn2file0  
3. **Tools → Board → Boards Manager…** → cari **ESP32** → **Install “ESP32 by Espressif Systems”**. *Contoh di eBook diuji pada **v2.0.1** — downgrade jika versi lebih baru bermasalah.* fileciteturn2file0  
4. **Colokkan board ESP32** → **Tools → Board** pilih **DOIT ESP32 DEVKIT V1** (atau model Anda) → **Tools → Port** pilih port yang muncul. *Jika tidak muncul, instal driver USB (mis. **CP210x**) atau ganti kabel data.* fileciteturn2file0  
5. **File → Examples → WiFi (ESP32) → WiFi Scan** → **Upload** → buka **Serial Monitor @115200** → tekan tombol **EN/RESET** → lihat daftar jaringan Wi‑Fi. fileciteturn2file0

---

## 🧰 Prasyarat
- **Arduino IDE** terpasang. (Jika Anda masih di Java 8/Runtime untuk **IDE 1.8.x**, pastikan Java tersedia. **IDE 2.x** menyertakan runtime sendiri.) fileciteturn2file0  
- **Board ESP32** (contoh: **DOIT ESP32 DEVKIT V1**) dan **kabel USB data** (bukan kabel charge-only). fileciteturn2file0

---

## A. Unduh & Jalankan Arduino IDE
1. Kunjungi halaman unduhan **Arduino IDE** dan pilih OS Anda (**Windows/macOS/Linux**). Untuk Windows, **disarankan “Windows ZIP file”** agar mudah dijalankan tanpa instalasi penuh. fileciteturn2file0  
2. Jika Anda sudah punya versi lama, **upgrade** ke versi terbaru. *Catatan sumber:* **IDE 1.8.19** kerap direkomendasikan untuk ESP32 jika Anda mengalami bug pada v2.x. fileciteturn2file0  
3. **Ekstrak ZIP** (Windows) atau jalankan sesuai OS. Buka aplikasi **Arduino IDE** dan pastikan jendela IDE tampil. fileciteturn2file0

> **Catatan kompatibilitas:** Meskipun **IDE 2.x** bekerja baik untuk Arduino secara umum, sebagian fitur/dukungan ESP32 bisa memiliki bug pada waktu tertentu. Jika bermasalah, uji dengan **IDE 1.8.19**. fileciteturn2file0

---

## B. Pasang ESP32 Boards Core lewat *Boards Manager*
1. Buka **File → Preferences**. Pada kolom **Additional Boards Manager URLs**, tempel:  
   `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`  fileciteturn2file0  
   - Jika sudah memiliki URL **ESP8266**, gabungkan dengan tanda koma, misalnya:  
     `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json, http://arduino.esp8266.com/stable/package_esp8266com_index.json`  fileciteturn2file0  
2. **Tools → Board → Boards Manager…** → ketik **ESP32** → pilih **ESP32 by Espressif Systems** → **Install**. fileciteturn2file0  
   - *Versi contoh eBook*: **2.0.1**. Jika versi terkini bermasalah, lakukan **downgrade** ke **2.0.1** dari daftar versi. fileciteturn2file0

---

## C. Uji Instalasi dengan **WiFi Scan**
1. **Sambungkan** papan **ESP32 DEVKIT V1 DOIT** ke komputer via USB. fileciteturn2file0  
2. **Tools → Board**: pilih **DOIT ESP32 DEVKIT V1** (atau papan Anda). **Tools → Port**: pilih **COM/tty** yang muncul.  
   - Jika **COM/tty** tidak muncul, instal **driver USB** sesuai chip pada papan (misal **CP2102**) dari situs **Silicon Labs**, lalu **restart IDE**. Juga pastikan **kabel USB** mendukung **data** (bukan kabel charge-only). fileciteturn2file0  
3. **File → Examples → WiFi (ESP32) → WiFi Scan** → jendela sketch akan terbuka. **Upload** sketch. fileciteturn2file0  
   - Jika pada *debug console* muncul banyak titik (`.....`) lalu error upload, **klik Upload lagi** dan saat tulisan **“Connecting…”** muncul, **tahan tombol BOOT** beberapa detik, lalu lepaskan. fileciteturn2file0  
4. Jika berhasil, Anda akan melihat pesan **“Done uploading.”**. Buka **Serial Monitor** (115200 bps), **tekan tombol EN/RESET**, lalu Anda akan melihat daftar **jaringan Wi‑Fi** di sekitar. fileciteturn2file0

---

## D. Troubleshooting Umum
### 1) “Failed to connect to ESP32: Timed out… Connecting…”
- Penyebab: board **tidak masuk mode flashing** otomatis.  
- Solusi: **Klik Upload** → saat muncul **“Connecting…”**, **tahan BOOT** selama beberapa detik → lepaskan → tunggu **“Done uploading.”**. fileciteturn2file0

### 2) COM Port tidak ditemukan/tersedia
- Penyebab paling umum: **driver USB belum terpasang** atau **kabel USB hanya-charging**.  
- Solusi:
  - Lihat chip di dekat regulator pada papan (contoh: **CP2102** untuk DOIT V1). **Pasang driver** yang sesuai OS Anda, lalu **restart Arduino IDE**. fileciteturn2file0  
  - Pastikan Anda menggunakan **kabel USB data** (kabel *powerbank* sering **tanpa jalur data**). Ganti kabel bila perlu. fileciteturn2file0

---

## ✅ Checklist Selesai Instalasi
- [ ] Arduino IDE berjalan normal (1.8.19 atau 2.x). fileciteturn2file0  
- [ ] URL Boards Manager ESP32 ditambahkan di **Preferences**. fileciteturn2file0  
- [ ] **ESP32 by Espressif Systems** terpasang (versi stabil yang bekerja di komputer Anda). fileciteturn2file0  
- [ ] Board **DOIT ESP32 DEVKIT V1** (atau model lain) dipilih, **Port** terbaca. fileciteturn2file0  
- [ ] **WiFi Scan** berhasil di-*upload* dan menampilkan daftar jaringan pada **Serial Monitor**. fileciteturn2file0

---

## 🧠 FAQ Mini
**Q:** Bolehkah saya menginstal dukungan **ESP8266** bersamaan?  
**A:** Boleh. Tambahkan URL ESP8266 di **Additional Boards Manager URLs** dipisahkan koma seperti contoh di atas. fileciteturn2file0

**Q:** Mengapa **COM Port** saya tetap tidak muncul?  
**A:** Umumnya karena **driver USB** belum terpasang atau **kabel tanpa data**. Cek jenis chip USB‑UART (mis. **CP2102**) dan gunakan **kabel data** yang baik. fileciteturn2file0

**Q:** Kapan saya perlu **menekan BOOT** saat upload?  
**A:** Jika board tidak masuk mode flashing otomatis: ketika *console* menampilkan **“Connecting…”**, tahan **BOOT** ±2–3 detik, lalu lepaskan. fileciteturn2file0

---

> **Langkah Berikutnya — Unit 3:** Memahami **alur & kebiasaan kerja** dengan board Anda pada kursus ini serta penyiapan fisik agar **ramah breadboard**. fileciteturn2file0
