# Hotspot QR Code Scanner - TemplateMikrotik.id

Scanner QR Code modern, cepat, dan responsif untuk autentikasi login voucher MikroTik Hotspot. Dilengkapi dengan UI dark neon elegan khas TemplateMikrotik, kontrol lampu senter (flashlight), ganti kamera, upload dari galeri, dan dukungan fallback captive portal.

---

### Cara Penggunaan di MikroTik Hotspot

#### 1. Tambahkan Tombol Scan di `login.html`
Sisipkan tombol pemindai QR Code di file `login.html` template hotspot Anda:

```html
<a href="/qr/" class="btn btn-qr">
  <svg width="18" height="18" fill="none" stroke="currentColor" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v1m6 11h2m-6 0h-2v4m0-11v3m0 0h.01M12 12h4.01M16 20h4M4 12h4m12 0h.01M5 8h2a1 1 0 001-1V5a1 1 0 00-1-1H5a1 1 0 00-1 1v2a1 1 0 001 1zm12 0h2a1 1 0 001-1V5a1 1 0 00-1-1h-2a1 1 0 00-1 1v2a1 1 0 001 1zM5 20h2a1 1 0 001-1v-2a1 1 0 00-1-1H5a1 1 0 00-1 1v2a1 1 0 001 1z"></path>
  </svg>
  <span>Scan QR Voucher</span>
</a>
```

#### 2. Konfigurasi Walled Garden (Jika scanner di-host di luar server lokal)
Jika QR Scanner dihosting di server eksternal / CDN (misal `qr.templatemikrotik.id`), jalankan perintah berikut di Terminal MikroTik agar dapat diakses oleh user sebelum login:

```routeros
/ip hotspot walled-garden
add dst-host=qr.templatemikrotik.id action=allow comment="Hotspot QR Code Scanner"
```

---

### Fitur Utama:
- **Tema Desain Elegan**: Selaras dengan identitas visual TemplateMikrotik.id (Dark Mode #000000 + Aksen Neon Lime #a9f501).
- **Viewfinder HUD Futuristik**: 4 corner bracket neon dan animasi laser scanning line.
- **Auto Switch & Flip Kamera**: Mendeteksi kamera belakang (environment) secara otomatis serta tombol ganti kamera.
- **Kontrol Flashlight (Senter)**: Tombol on/off senter kamera untuk scanning di tempat gelap.
- **Upload Foto Voucher**: Scan QR langsung dari tangkapan layar / file galeri foto.
- **Dukungan Captive Portal Android**: Tombol cepat "Buka di Google Chrome" via Intent jika browser bawaan sistem membatasi izin kamera.
- **Feedback Audio & Getar**: Bunyi konfirmasi beep instan via Web Audio API dan getar haptic saat scan berhasil.

&copy; 2026 [TemplateMikrotik.id](https://templatemikrotik.id)
