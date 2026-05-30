# 🎧 WhisperIO

> **Ultra-hafif P2P oyuncu sesli chat. Discord'un 10'da 1'i RAM, %0.3 CPU. Açık kaynak.**

---

## 🎯 Vizyon

Discord 500MB RAM, %8 CPU yerken WhisperIO **50MB RAM, %0.3 CPU** ile aynı işi yapar.
Sunucu bağımlılığı minimum, iletişim WebRTC P2P mantığı ile ilerler.

**Slogan:** "Sesin özgür. Bilgisayarın rahat."

---

## ✨ Öne Çıkan Özellikler

- Oda kodu ile hızlı oda oluşturma ve katılma
- Düşük kaynak kullanımı odaklı performans
- Host yönetimi:
  - Katılımcıyı odadan atma
  - Odayı kalıcı olarak silme
- Gürültü bastırma seçeneği
- Katılımcı bazlı ses seviyesi kontrolü
- WebRTC tabanlı düşük gecikmeli ses iletişimi
- İngilizce dil desteği

---

## 🛠 Teknoloji Stack'i

| Katman | Teknoloji | Açıklama |
|--------|-----------|----------|
| **UI Shell** | Tauri 2 + React 19 | Hafif masaüstü binary + OS webview |
| **Ses Yakalama** | cpal + WASAPI/CoreAudio | Cross-platform ses yakalama |
| **Codec** | Opus 16-32kbps | Discord ile benzer codec yaklaşımı |
| **Gürültü** | RNNoise | Gürültü bastırma yaklaşımı |
| **Ağ + Şifreleme** | WebRTC P2P + DTLS-SRTP | E2EE odaklı gerçek zamanlı iletişim |
| **Signaling** | Go + WebSocket | Hafif signaling altyapısı |

---

## 📂 Proje Yapısı

```text
whisper-io/
├── src/                    # React UI (TypeScript)
│   ├── components/         # UI bileşenleri
│   ├── hooks/              # Zustand store + custom hooks
│   └── styles/             # Tailwind CSS
├── src-tauri/              # Tauri + Rust backend
│   └── src/
│       ├── audio/          # Ses motoru
│       └── commands.rs     # Tauri IPC komutları
├── signaling-server/       # Go WebSocket signaling
└── overlay-dll/            # Overlay (gelecek sürümler)
```

---

## 🗺 Yol Haritası

- [x] Proje scaffold (Tauri + React + Rust)
- [x] Ses cihazı listeleme
- [x] Temel UI (oda ekranı, kullanıcı listesi)
- [x] Signaling sunucu
- [ ] Opus encode/decode entegrasyonu
- [ ] RNNoise gürültü bastırma
- [ ] WebRTC P2P mesh bağlantı
- [ ] DirectX in-game overlay
- [ ] macOS + Linux desteği
- [ ] Pozisyonel ses
- [ ] v1.0.0 release

---

## 🌍 English

WhisperIO is a lightweight desktop voice chat app designed for low CPU and memory usage.
It focuses on fast room-based communication with modern real-time voice technologies.

### Highlights

- Quick room flow with room codes
- Low resource usage focused architecture
- Host controls (kick participant, delete room)
- Optional noise suppression
- Per-participant volume control
- WebRTC-based low-latency voice communication
- English language support

---

## 📝 Lisans

MIT © WhisperIO Contributors

---

*"Oyun oynarken sesin CPU'nu yemesin."*
