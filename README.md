# Polyglot Learner - Yapay Zeka Destekli Tek Dosya Dil Öğrenme Platformu

Bu proje, modern web teknolojilerini (React, Zustand, Framer Motion) kullanarak geliştirilmiş, **kurulum gerektirmeyen ve tamamen tek bir HTML dosyası içinde çalışan** devrim niteliğinde bir dil öğrenme uygulamasıdır.

## 🌟 Proje Vizyonu ve Mimarisi

Geleneksel web uygulamalarının aksine, bu proje "Serverless" ve "Buildless" (Sunucusuz ve Derlemesiz) bir yaklaşımla tasarlanmıştır. 
Uygulamanın tüm HTML yapısı, CSS stilleri (Bootstrap & Custom) ve JavaScript mantığı (React Components) tek bir `POLYGLOT_LEARNER_FULL_APP.html` dosyası içinde birleştirilmiştir.

Bu mimari sayesinde:
- **Sıfır Kurulum:** Node.js, npm veya herhangi bir sunucu kurulumuna gerek yoktur.
- **Taşınabilirlik:** Sadece HTML dosyasını bir USB belleğe atıp veya e-posta ile gönderip herhangi bir cihazda (PC, Tablet, Mobil) tarayıcı üzerinden anında çalıştırabilirsiniz.
- **Çevrimdışı Çalışma (Kısmi):** AI özellikleri hariç, temel öğrenme mekanikleri internet olmadan da çalışabilir.

## 🚀 Temel Özellikler

- **Tek Dosya Mimarisi (Single File App):** Tüm proje tek bir `.html` dosyasından ibarettir.
- **JIT (Just-In-Time) Kelime Üretimi:** 10.000+ kelimelik devasa bir kelime havuzu (A1'den C2'ye kadar) arka planda hafif metin dizileri olarak tutulur. Sistem sadece o gün öğrenilecek kelimeleri anlık olarak işler, böylece tarayıcı belleği şişmez.
- **Gemini AI Entegrasyonu:** Seçilen kelimeler Google Gemini AI kullanılarak anında zenginleştirilir (Çeviri, 3 farklı zamanda örnek cümleler, boşluk doldurma soruları, telaffuz).
- **Yerel Veri Kalıcılığı (localStorage):** Kullanıcı ilerlemesi, ayarları ve öğrenilen kelimeler tarayıcının yerel depolamasında güvenle saklanır. Uygulamayı kapatsanız bile verileriniz kaybolmaz.
- **Dışa Aktarma (Export):** Ayarlar menüsündeki "Projeyi Dışa Aktar" butonu ile, o anki tüm verilerinizle birlikte uygulamanın güncel halini yeni bir HTML dosyası olarak indirebilirsiniz.
- **Akıllı Flashcard Sistemi:** Dinamik yazı boyutu, renk kodlaması ve 3D çevirme animasyonlarıyla görsel hafızayı destekleyen öğrenme kartları.
- **Aralıklı Tekrar (Spaced Repetition) Mantığı:** Kelimeler hedef tekrar sayısına ulaşana kadar oturumlarda karşınıza çıkar. Zorlanılan kelimeler özel bir havuza ayrılıp tekrar edilebilir.
- **Oyunlaştırılmış Test Modu:** Öğrenilen kelimeleri pekiştirmek için çoktan seçmeli ve interaktif test ekranı.

## 🛠 Teknik Altyapı (CDN Üzerinden)

Uygulama, modern kütüphaneleri UMD (Universal Module Definition) formatında CDN'ler üzerinden anlık olarak çeker:

- **Core:** React 18, ReactDOM 18, Babel (Tarayıcı içi JSX derleme)
- **Routing:** React Router DOM v6
- **State Management:** Zustand (Persist middleware ile)
- **UI & Styling:** Bootstrap 5.3, Özel CSS Utility sınıfları
- **Icons & Animations:** Lucide React, Framer Motion
- **AI:** @google/genai (Browser Bundle)

## 🧠 Performans ve Algoritma Detayları

### 1. Hafif Bellek (Lightweight Memory) Havuzu
10.000 kelimenin tamamını detaylarıyla bellekte tutmak tarayıcıyı dondurur. Bu yüzden `SYSTEM_DICTIONARY` objesi içinde sadece kelime kökleri (örn: 'apple', 'run') tutulur. Bu yapı, devasa bir sözlüğün sadece birkaç KB yer kaplamasını sağlar.

### 2. Tembel Zenginleştirme (Lazy Enrichment)
Kullanıcı yeni bir oturum başlattığında:
1. Sistem kullanıcının seviyesine (örn: B1) bakar.
2. Havuzdan daha önce öğrenilmemiş 5 (veya ayarlanan günlük hedef kadar) kelime seçer.
3. Bu kelimeleri Gemini AI'a göndererek cümleler ve çevirilerle zenginleştirir. (API key yoksa sistem otomatik Mock/Sahte veri üretir).
4. Sadece bu 5 kelimeyi `localStorage`'a kaydeder.
Bu sayede uygulama her zaman maksimum performansta çalışır.

## 📥 Kurulum ve Kullanım

1. Proje dizinindeki `POLYGLOT_LEARNER_FULL_APP.html` dosyasını bulun.
2. Dosyaya çift tıklayarak modern bir web tarayıcısında (Chrome, Firefox, Edge, Safari) açın.
3. Adınızı girin, seviyenizi ve öğrenmek istediğiniz dili seçin.
4. (Opsiyonel) Ayarlar menüsünden Google Gemini API anahtarınızı girerek yapay zeka özelliklerini aktif edin.
5. Öğrenmeye başlayın!

---
*Not: Bu proje, modern web geliştirme yeteneklerinin sınırlarını zorlayan bir "Proof of Concept" (Kavram Kanıtı) ve tam teşekküllü bir eğitim aracıdır.*
