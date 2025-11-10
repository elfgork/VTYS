🎯 Amaç

Bu Access veritabanı, bir güzellik merkezinde yer alan uzmanlar, verilen hizmetler ve yapılan uygulamaları yönetmek amacıyla hazırlanmıştır.
Veritabanı, ilişkisel veri yapısını örneklemek ve temel Access bileşenlerinin (tablolar, ilişkiler, sorgular, raporlar) kullanımını göstermek için oluşturulmuştur.

🧩 Veritabanı Yapısı

1. BeautyExperts (Güzellik Uzmanı) Tablosu

Alan Adı	Açıklama
id	Otomatik artan birincil anahtar
name	Güzellik uzmanının adı ve soyadı

2. Services (Hizmetler) Tablosu

Alan Adı	Açıklama
id	Otomatik artan birincil anahtar
name	Hizmetin adı
expert_id	Hizmeti hazırlayan güzellik uzmanının kimliği (FK → BeautyExperts.id)

3. Applications (Uygulamalar) Tablosu

Alan Adı	Açıklama
id	Otomatik artan birincil anahtar
service_id	Uygulama yapılan hizmetin kimliği (FK → Services.id)
customer_name	Müşterinin adı
type	Hizmet türü (Saç, Tırnak, Ayak vb.)
duration	Hizmetin süresi (dakika)
applied_by	Uygulamayı yapan uzman (FK → BeautyExperts.id)
supervised_by	Uygulamayı denetleyen uzman (FK → BeautyExperts.id)
🔗 İlişkiler

Services.expert_id → BeautyExperts.id

Applications.service_id → Services.id

Applications.applied_by → BeautyExperts.id

Applications.supervised_by → BeautyExperts.id

Tüm ilişkiler referential integrity kurallarıyla oluşturulmuştur.

🧮 Örnek Veriler

4 güzellik uzmanı (Ayşe Korkmaz, Elif Demir, Merve Yıldız, Seda Özcan)

5 hizmet (Saç Kesimi, Manikür, Pedikür, Cilt Bakımı, Kaş Tasarımı)

5 uygulama (farklı müşterilerle ve farklı sürelerde)

🔍 Oluşturulan Sorgular

Q_BeautyExpertsApplications → Uzmanlar ve yaptıkları uygulamaların listesi

Q_ServiceWithExpert → Hizmetler ve onları hazırlayan uzmanlar

Q_ApplicationDetails → Uygulama, hizmet ve ilgili uzman bilgilerini birleştirir

📊 Rapor

R_BeautyExpertsApplications adlı rapor, her uzmanın yaptığı uygulamaları gruplandırılmış biçimde listeler.
(Veri kaynağı: Q_BeautyExpertsApplications sorgusu)

🧱 Kullanılan Access Özellikleri

Tablo oluşturma ve ilişkilendirme

SQL ile veri ekleme

Sorgu oluşturma (JOIN yapıları)

Rapor tasarımı

Veri bütünlüğü (foreign key ilişkileri)
