📌 Proje Hakkında
Bu proje, bir güzellik salonunun günlük operasyonlarını yönetmek için tasarlanmış bir veritabanı sistemidir. Microsoft Access kullanılarak geliştirilmiştir.
🎯 Projenin Amacı

Güzellik uzmanlarının bilgilerini saklamak
Sunulan hizmetleri kayıt altına almak
Müşteri uygulamalarını takip etmek
Uzmanlık alanlarına göre hizmet dağılımını yönetmek
Denetim ve gözetim süreçlerini kaydetmek

🗂️ Veritabanı Yapısı
Tablolar:
1. GuzellikUzmanlari
Salonda çalışan uzmanların bilgilerini tutar.

id (Otomatik Sayı, Birincil Anahtar)
uzmanAdi (Kısa Metin, 100 karakter)

2. Hizmetler
Salonda sunulan hizmetlerin listesini içerir.

id (Otomatik Sayı, Birincil Anahtar)
hizmetAdi (Kısa Metin, 100 karakter)
uzmanID (Sayı, Yabancı Anahtar → GuzellikUzmanlari)

3. Uygulamalar
Müşterilere yapılan uygulamaların detaylarını saklar.

id (Otomatik Sayı, Birincil Anahtar)
hizmetID (Sayı, Yabancı Anahtar → Hizmetler)
musteriAdi (Kısa Metin, 100 karakter)
uygulamaTuru (Kısa Metin, 50 karakter)
sure (Sayı, dakika cinsinden)
uygulayan (Sayı, Yabancı Anahtar → GuzellikUzmanlari)
denetleyen (Sayı, Yabancı Anahtar → GuzellikUzmanlari)

🔗 İlişkiler

Hizmetler → GuzellikUzmanlari (Bir uzman birden fazla hizmet verebilir)
Uygulamalar → Hizmetler (Her uygulama bir hizmete bağlıdır)
Uygulamalar → GuzellikUzmanlari (Uygulayan uzman)
Uygulamalar → GuzellikUzmanlari (Denetleyen uzman)
