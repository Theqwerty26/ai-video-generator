# AI Video Generator - Yapay Zeka Destekli Video Üretim Platformu

Kullanıcıların metin veya sesli komut vererek, maksimum 2 dakikalık, yüksek kaliteli, yapay zekâ destekli videolar oluşturabileceği modern bir web uygulaması.

## 🎬 Özellikler

### Video Üretimi
- **Metin ile Video Oluşturma**: Detaylı prompt'larla profesyonel videolar
- **Sesli Komut Desteği**: Speech-to-text teknolojisi ile sesli giriş
- **Tema Seçenekleri**: Bilimkurgu, doğa, hikaye, şiir, soyut, belgesel
- **Özelleştirme**: Ses tonu, arka plan müziği, karakter tipi seçimi
- **Kalite Seçenekleri**: Standart (720p), HD (1080p), 4K

### AI Entegrasyonları
- **RunwayML Gen-2**: Video sahne üretimi
- **Google TTS**: AI seslendirme
- **Soundraw**: Arka plan müziği üretimi
- **Firebase**: Bulut depolama ve veri yönetimi

### Kullanıcı Deneyimi
- **Modern UI/UX**: Tailwind CSS ile responsive tasarım
- **Gerçek Zamanlı İlerleme**: Video oluşturma sürecini takip
- **Video Galerisi**: Oluşturulan videoları yönetme
- **Sosyal Paylaşım**: Videoları indirme ve paylaşma
- **Tema Desteği**: Açık/koyu mod

### Gelir Modeli
- **Freemium**: Günlük 1 video (30 saniye, filigran ile)
- **Premium**: Sınırsız video (2 dakika, filigransız)
- **Gelişmiş Özellikler**: HD/4K kalite, öncelikli işleme

## 🚀 Kurulum

### Gereksinimler
- Node.js 18+
- npm veya yarn

### Adımlar

1. **Projeyi klonlayın**
```bash
git clone <repository-url>
cd ai-video-generator
```

2. **Bağımlılıkları yükleyin**
```bash
npm install --legacy-peer-deps
```

3. **Ortam değişkenlerini ayarlayın**
`.env.local` dosyasını oluşturun:
```env
# AI Video Generation APIs
RUNWAY_API_KEY=your_runway_gen2_api_key_here
GOOGLE_TTS_API_KEY=your_google_tts_api_key_here
SOUNDRAW_API_KEY=your_soundraw_api_key_here

# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key_here
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id

# App Configuration
NEXT_PUBLIC_APP_URL=http://localhost:8000
NEXT_PUBLIC_MAX_FREE_VIDEO_DURATION=30
NEXT_PUBLIC_MAX_PREMIUM_VIDEO_DURATION=120
```

4. **Geliştirme sunucusunu başlatın**
```bash
npm run dev
```

5. **Uygulamayı açın**
[http://localhost:8000](http://localhost:8000) adresine gidin.

## 📁 Proje Yapısı

```
src/
├── app/                    # Next.js App Router
│   ├── api/               # API endpoints
│   │   └── generate-video/ # Video üretim API'si
│   ├── create/            # Video oluşturma sayfası
│   ├── gallery/           # Video galerisi
│   ├── settings/          # Kullanıcı ayarları
│   ├── layout.tsx         # Ana layout
│   └── page.tsx           # Ana sayfa
├── components/            # React bileşenleri
│   ├── ui/               # Shadcn/UI bileşenleri
│   ├── video-creation-form.tsx
│   ├── video-preview.tsx
│   ├── loading-indicator.tsx
│   └── navigation.tsx
├── hooks/                # Custom React hooks
│   └── use-speech-to-text.ts
├── lib/                  # Yardımcı kütüphaneler
│   ├── video-service.ts  # AI video servisleri
│   ├── firebase.ts       # Firebase yapılandırması
│   ├── store.ts          # Zustand state management
│   └── utils.ts          # Yardımcı fonksiyonlar
└── styles/
    └── globals.css       # Global stiller
```

## 🛠️ Teknolojiler

### Frontend
- **Next.js 15**: React framework
- **TypeScript**: Tip güvenliği
- **Tailwind CSS**: Utility-first CSS
- **Shadcn/UI**: Modern UI bileşenleri
- **Zustand**: State management

### Backend & APIs
- **Next.js API Routes**: Sunucu tarafı API'ler
- **RunwayML Gen-2**: Video üretimi
- **Google TTS**: Metin-ses dönüşümü
- **Soundraw**: Müzik üretimi
- **Firebase**: Veritabanı ve depolama

### Özellikler
- **Speech-to-Text**: Web Speech API
- **Form Validation**: React Hook Form + Zod
- **Notifications**: Sonner
- **Theme Support**: next-themes

## 🎯 Kullanım

### Video Oluşturma
1. **Ana sayfadan** "Video Oluştur" butonuna tıklayın
2. **Prompt girin** veya sesli komut kullanın
3. **Tema ve ayarları** seçin
4. **Video oluştur** butonuna tıklayın
5. **İşlem tamamlandığında** videonuzu izleyin

### Galeri Yönetimi
- Oluşturulan videolar otomatik olarak galeriye kaydedilir
- Videoları filtreleyebilir ve arayabilirsiniz
- İndirme ve paylaşım seçenekleri mevcuttur

### Ayarlar
- Kullanıcı tercihleri
- Bildirim ayarları
- Abonelik yönetimi
- Gizlilik kontrolü

## 🔧 Geliştirme

### Yeni Özellik Ekleme
1. İlgili bileşeni `src/components/` altında oluşturun
2. Gerekirse API endpoint'i `src/app/api/` altında ekleyin
3. State management için `src/lib/store.ts` dosyasını güncelleyin

### API Entegrasyonu
- Video servisleri `src/lib/video-service.ts` dosyasında tanımlı
- Yeni AI servisi eklemek için bu dosyayı güncelleyin
- API anahtarlarını `.env.local` dosyasına ekleyin

## 📱 Mobil Uygulama

Bu proje web uygulaması olarak geliştirilmiştir. Mobil uygulama için Flutter kullanılması önerilir:

- **Flutter**: Cross-platform mobil geliştirme
- **Firebase**: Backend servisleri
- **Aynı API'ler**: Web uygulaması ile aynı AI servisleri

## 🚀 Deployment

### Vercel (Önerilen)
```bash
npm run build
vercel --prod
```

### Diğer Platformlar
- **Netlify**: Static export ile
- **AWS**: Amplify veya EC2
- **Google Cloud**: App Engine

## 🤝 Katkıda Bulunma

1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit edin (`git commit -m 'Add amazing feature'`)
4. Push edin (`git push origin feature/amazing-feature`)
5. Pull Request oluşturun

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır.

## 🆘 Destek

Sorularınız için:
- GitHub Issues
- Email: support@example.com
- Discord: [Community Server]

## 🎉 Teşekkürler

- **RunwayML**: Video üretim teknolojisi
- **Google**: TTS servisleri
- **Soundraw**: Müzik üretimi
- **Vercel**: Hosting ve deployment
- **Shadcn**: UI bileşenleri
