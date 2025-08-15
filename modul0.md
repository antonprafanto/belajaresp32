# 📘 Belajar ESP32 dengan Arduino IDE — **Modul 0: Pengantar Kursus**

> Ebook ringkas dan ramah pemula. Dibaca berurutan atau loncat topik, tapi **wajib** menyiapkan lingkungan di Modul 1 sebelum praktik lanjutan.

## 🎯 Tujuan Pembelajaran
- Memahami gambaran umum kursus ESP32 untuk pemula.
- Mengetahui alur belajar, struktur modul, dan cara mengikuti materi.
- Menyiapkan alat & perangkat lunak yang diperlukan.
- Mengetahui cara mendapatkan kode sumber, skema rangkaian, dan bahan pendukung.

## 🧭 Cara Mengikuti Kursus Ini
1. **Mulai dari Modul 1** untuk menyiapkan Arduino IDE agar bisa mengunggah program ke ESP32.
2. **Unduh resource** (kode, skema, bahan bacaan) dari repositori yang disediakan penulis kursus.
3. Setiap modul bersifat **mandiri** — pilih topik sesuai kebutuhan, namun beberapa proyek menggabungkan konsep dari modul sebelumnya.
4. Kerjakan **latihan kecil** di akhir subbab agar konsep langsung nempel.
5. Simpan catatan singkat Anda (troubleshooting, port, versi core) agar mudah mengulang.

> **Tip:** Setiap kali ganti komputer/IDE, ulangi langkah pemasangan core/boards agar contoh program berjalan mulus.

## 🧩 Peta Besar Kursus
Kursus terdiri dari 8 modul utama, 4 proyek, dan unit tambahan. Ringkasan berikut membantu Anda memilih topik dengan cepat:

| Modul | Fokus Praktik | Hasil Cepat yang Dipelajari |
|---|---|---|
| 1. Getting Started | Kenalan ESP32, menyiapkan Arduino IDE | IDE siap, upload sketch pertama |
| 2. GPIO | Input/output digital, PWM, analog, touch, hall sensor | Membaca tombol/sensor, mengendalikan LED/servo |
| 3. Deep Sleep | Hemat daya & cara membangunkan ESP32 | Mode tidur dengan timer/touch/external wake-up |
| 4. Web Server | Web server untuk kontrol & monitoring | Antarmuka HTML/CSS untuk mengendalikan perangkat |
| 5. Bluetooth | BLE & Classic | Pindai perangkat, client–server, kirim data |
| 6. LoRa | Komunikasi jarak jauh | Kirim/terima data antarmodule di area luas |
| 7. MQTT | Publish/subscribe, integrasi Node‑RED | Hubungkan ESP32 ke dashboard/otomasi |
| 8. ESP‑NOW | Komunikasi langsung tanpa Wi‑Fi | Jaringan one-to-many & many-to-one |

**Proyek contoh:** Multisensor Wi‑Fi, mobil Wi‑Fi, aplikasi Android BLE, dan pemantauan sensor berbasis LoRa.

## 🧰 Yang Perlu Disiapkan
**Perangkat Keras**
- Papan pengembangan ESP32 (mis. DevKit/NodeMCU ESP32).
- Kabel USB sesuai papan (Micro‑USB/USB‑C).
- Breadboard, jumper, LED, resistor; sensor sederhana (mis. DHT22, LDR), opsional relay/servo.

**Perangkat Lunak**
- Arduino IDE (versi terbaru stabil).
- **Core ESP32** melalui *Boards Manager* di Arduino IDE.
- Driver USB sesuai chip (CP2102/CH340) jika diperlukan.

> **Checklist cepat:** IDE terpasang ✅ | Core ESP32 terpasang ✅ | Port serial terbaca ✅ | Upload contoh **Blink** berhasil ✅

## 🧪 Latihan Kilat — Blink LED
Cobalah mengunggah kode berikut untuk memastikan lingkungan siap:

```cpp
// Blink LED bawaan (seringnya terhubung ke GPIO2 atau LED_BUILTIN)
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(500);
  digitalWrite(LED_BUILTIN, LOW);
  delay(500);
}
```

> **Troubleshooting cepat:** Jika gagal upload, periksa pemilihan **Board** & **Port** di menu *Tools*, lalu tekan tombol **BOOT/EN** saat proses flashing jika papan membutuhkannya.

## 📝 Struktur Belajar yang Disarankan
- **Baca ringkasan modul** →
- **Praktik unit pendek** →
- **Catat temuan/troubleshoot** →
- **Ulangi dengan variasi** (mis. ubah pin, timing, sensor) →
- **Gabungkan ke proyek mini** (mis. LED + tombol + server web sederhana).

## 🧠 Glosarium Mini (Ringkas)
- **GPIO:** Pin input/output umum untuk membaca tombol/ sensor & menyalakan aktuator.
- **PWM:** Sinyal *pulse‑width modulation* untuk mengatur tingkat terang LED atau sudut servo.
- **Analog Input (ADC):** Membaca nilai sensor kontinu (0–4095 pada banyak varian ESP32).
- **Deep Sleep:** Mode hemat daya; bangunkan via timer, sentuhan, atau sumber eksternal.
- **Web Server:** Halaman web dari ESP32 untuk pantau/kontrol.
- **BLE/MQTT/LoRa/ESP‑NOW:** Ragam protokol komunikasi untuk berbagai kasus penggunaan IoT.

## 🔚 Ringkasan
- Mulai dari **Modul 1** agar lingkungan siap.
- Pilih modul sesuai kebutuhan, lakukan latihan kecil di tiap unit.
- Simpan *checklist* & catatan troubleshooting untuk mempercepat progres berikutnya.

---

> **Catatan penyusun:** Materi modul ini diringkas & disederhanakan untuk pembaca awam berdasarkan kursus ESP32 yang memuat 8 modul, 4 proyek, dan unit tambahan. Gunakan modul ini sebagai pijakan sebelum menyelam ke topik GPIO, Web Server, Bluetooth, LoRa, MQTT, dan ESP‑NOW.
