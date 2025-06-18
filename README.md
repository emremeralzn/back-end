# 🚀 Açık Artırma Web Sitesi

[![GitHub](https://img.shields.io/badge/GitHub-Backend-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/emremeralzn/back-end)
[![GitHub](https://img.shields.io/badge/GitHub-Frontend-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/emremeralzn/front-end)

Bu proje, modern web teknolojileri kullanılarak geliştirilmiş, gerçek zamanlı açık artırma işlemlerini destekleyen tam kapsamlı bir web uygulamasıdır. SignalR ile anlık güncellemeler, JWT ile güvenli kullanıcı yönetimi, Stripe ile ödeme altyapısı ve MSSQL veritabanı üzerinde Code-First mimarisi kullanılmıştır. 

> Frontend kurulumu için: [Frontend Repo](https://github.com/emremeralzn/front-end)

---

## 👥 Proje Ekibi

Bu kapsamlı proje, 8 kişilik bir ekip tarafından geliştirilmiştir:

### Backend Ekibi (3 Kişi)
- Katmanlı mimari tasarımı
- API geliştirme
- Veritabanı yönetimi
- SignalR entegrasyonu
- Stripe ödeme sistemi entegrasyonu

### Frontend Ekibi (3 Kişi)
- React.js ile modern UI geliştirme
- Gerçek zamanlı teklif sistemi
- Kullanıcı deneyimi optimizasyonu
- Responsive tasarım

### Test Ekibi (2 Kişi)
- API testleri
- Kullanıcı arayüzü testleri
- Performans testleri
- Güvenlik testleri

> **Not:** Projede hem backend hem de frontend geliştirme süreçlerinde aktif rol aldım. Backend tarafında API geliştirme ve veritabanı yönetimi, frontend tarafında ise kullanıcı arayüzü geliştirme , gerçek zamanlı teklif sistemi entegrasyonu , stripe ödeme sistemi entegresi ve dashboard sayfa tasarımları ve endpoint tanımlamaları görevlerinde çalıştım.


## 🔍 Proje Hakkında

Kullanıcılar, araç, elektronik, müzik aletleri, emlak ve giyim kategorilerinde ürünler ekleyebilir ve bu ürünlere açık artırma usulüyle teklif verebilir. SignalR sayesinde teklifler anlık olarak tüm kullanıcılarla senkronize edilir. Ödeme işlemleri Stripe üzerinden güvenli bir şekilde gerçekleştirilir.

| Özellik                                | Açıklama                                                              |
| -------------------------------------- | --------------------------------------------------------------------- |
| 🧑‍💼 Kullanıcı Kayıt / Giriş Sistemi  | JWT ile kimlik doğrulama ve güvenli oturum yönetimi                   |
| ⚡ Gerçek Zamanlı Teklif Güncellemeleri | SignalR ile canlı teklif artışları ve anlık bildirimler               |
| 💳 Stripe ile Ödeme Entegrasyonu       | Kullanıcıların güvenli ödeme yapabilmesi için Stripe API entegrasyonu |
| 🧾 Ürün Listeleme ve Filtreleme        | Kategori bazlı arama ve ürün listeleme özellikleri                    |
| 📦 Code-First Entity Framework (MSSQL) | MSSQL ve EF Core ile modern veri modellemesi                          |
| 🧑‍💻 Yönetici Paneli (Admin Panel)    | Ürün ve kullanıcı yönetimi için özel yönetim ekranları                |

## 📦 Kategoriler

Uygulama aşağıdaki ana ürün kategorilerini desteklemektedir:

- 🚗 Vehicles (Araçlar)
- 💻 Electronic (Elektronik)
- 🎸 Musical Instruments (Müzik Aletleri)
- 🏠 Estates (Gayrimenkul)
- 👗 Dresses (Kıyafetler)

## 🚀 Projeyi Çalıştırmak İçin

### Backend Kurulumu

1. **Veritabanı Hazırlığı**
   - Visual Studio'da `MyGalaxy_Auction.sln` projesini açın
   - Çözüm Gezgini'nde (`Solution Explorer`) `MyGalaxy_Auction` katmanına sağ tıklayın ve **Başlangıç projesi olarak ayarla** seçeneğini tıklayın.
   - `appsettings.example.json` dosyasını `appsettings.json` olarak kopyalayın ve aşağıdaki bilgileri kendi bilgilerinizle güncelleyin:

   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER_NAME;Database=MyGalaxyAuctionDB;Trusted_Connection=True;TrustServerCertificate=True;"
     },
     "SecretKey": {
       "jwtKey": "YOUR_JWT_SECRET_KEY_HERE"
     },
     "Stripe": {
       "SecretKey": "YOUR_STRIPE_SECRET_KEY",
       "PublishableKey": "YOUR_STRIPE_PUBLISHABLE_KEY"
   }
   ```

   > **Önemli Not:** 
   > - Connection string'deki `YOUR_SERVER_NAME` kısmını kendi SQL Server adınızla değiştirin
   > - JWT secret key için güvenli ve uzun bir string kullanın
   > - Stripe anahtarlarını [Stripe Dashboard](https://dashboard.stripe.com/apikeys)'dan alabilirsiniz

   > **Güvenlik Uyarısı:** Güvenlik nedeniyle projenin orijinal veritabanı ve API anahtarları paylaşılmamıştır. Bunun yerine, `updated seed data.txt` dosyası projeye dahil edilmiştir. Bu dosyadaki örnek verileri kullanarak kendi veritabanınızı oluşturabilirsiniz.

2. **Migration ve Veritabanı Oluşturma**
   - Package Manager Console'u açın (Visual Studio'da `Ctrl+Q` tuşlarına basıp "Package Manager Console" yazın)
   - **Dikkat:** Package Manager Console'un üst kısmındaki 'Varsayılan Proje'yi `MyGalaxy_Auction_Data_Access` olarak seçin.
   - İlk olarak tabloları oluşturmak için:

  > **Önemli Not:** Seed data migration'ı, veritabanına örnek veriler ekler:
   > - 20 adet araç (Toyota, Ferrari, Lamborghini vb.)
   > - 20 adet elektronik ürün (iPhone, Samsung, Sony vb.)
   > - 20 adet müzik aleti (Yamaha, Roland, Fender vb.)
   > - 20 adet gayrimenkul (Daire, Villa, Arsa vb.)
   > - 20 adet kıyafet (Zara, H&M, Mango vb.)
   >
   > Tüm ürünler için detaylı bilgiler ve görseller `updated seed data.txt` dosyasında bulunmaktadır.

   > **ApplicationDbContext Yapılandırması:**
   > `ApplicationDbContext.cs` dosyasında, veritabanı tabloları ve ilişkileri tanımlanmıştır. update seed data.txt de ki veri ve tablo oluşumu bu dosyada yapılır. Her kategori için örnek veriler (elektronik ürünler, gayrimenkul, kıyafetler ve müzik aletleri) bu şekilde veritabanına eklenir. Tüm ürünler için:
   > - Başlangıç fiyatı
   > - Açık artırma başlangıç ve bitiş tarihleri
   > - Ürün detayları (marka, model, açıklama vb.)
   > - Görsel URL'leri
   > - Satıcı bilgileri
   > gibi bilgiler otomatik olarak eklenir.

   -  updated seed data.txt de ki tabloları oluşturmak için:
   ```powershell
   # İlk migration'ı oluşturun (tablolar için)
   Add-Migration mig1
   
   # Veritabanını güncelleyin
   Update-Database
   ```

   - Ardından updated seed data.txt de ki verileri eklemek için:
   ```powershell
   # Seed data için migration oluşturun
   Add-Migration mig2
   
   # Veritabanını güncelleyin
   Update-Database
   ```

> **Önemli Not:** İlgili tablolar oluşturulduktan sonra MSSQL de bu komutun çalıştırılması gerekir:
> ```sql
> DROP INDEX IX_PaymentHistories_VehicleId ON PaymentHistories;
> ```

3. **Swagger Arayüzü**
   - Backend projesini başlattığınızda otomatik olarak Swagger arayüzü açılacaktır
   - Varsayılan URL: `https://localhost:7074/swagger`
   - Swagger üzerinden tüm API endpointlerini test edebilirsiniz

### Frontend Kurulumu

Frontend projesi React ile geliştirilmiştir. Kurulum için:

```bash
# Repoyu klonlayın
git clone [frontend-repo-url]

# Proje dizinine gidin
cd [frontend-dir]

# Gerekli paketleri yükleyin
npm install

# Projeyi başlatın
npm run dev
```

## 📁 Proje Yapısı

```
📦 MyGalaxy_Auction
├── 📁 Controllers              # API controller'ları
├── 📁 Extensions               # Extension methodlar
├── 📁 Hubs                     # SignalR hub sınıfları
├── 📁 Images                   # Görseller
├── 📄 appsettings.json         # Uygulama yapılandırmaları
├── 📄 Program.cs               # Giriş noktası

📦 MyGalaxy_Auction_Business
├── 📁 Abstraction              # Interface tanımlamaları
├── 📁 Concrete                 # Servis implementasyonları
├── 📁 Dtos                     # Veri transfer objeleri
├── 📁 Mapper                   # Mapleme işlemleri

📦 MyGalaxy_Auction_Core
├── 📁 Common                   # Genel yardımcı sınıflar
├── 📁 MailHelper               # Mail gönderimi için yardımcı sınıflar
├── 📁 Models                   # Temel modeller

📦 MyGalaxy_Auction_Data_Access
├── 📁 Context                  # DbContext sınıfı
├── 📁 Domain                   # Varlık (Entity) tanımlamaları
├── 📁 Enums                    # Enum tipleri
├── 📁 Migrations               # Code-First migration dosyaları
├── 📁 Models                   # ViewModel veya veri taşıyıcı yapılar
```

## 🛠️ Kullanılan Teknolojiler

| Bileşen                 | Teknoloji / Araç                       | Açıklama                                   |
| ----------------------- | --------------------------------------- | ------------------------------------------ |
| Backend                 | ASP.NET Core 8                          | API ve iş mantığı katmanı                  |
| Gerçek Zamanlı İletişim | SignalR                                 | Anlık teklif güncellemeleri                |
| Kimlik Doğrulama        | JWT (JSON Web Token)                    | Kullanıcı oturumları ve yetkilendirme      |
| Veritabanı              | MSSQL + Entity Framework Core (Code-First) | Veritabanı yönetimi ve veri modeli oluşturma |
| Frontend                | React.js + Vite                         | Kullanıcı arayüzü                          |
| Durum Yönetimi          | React Context API                       | Kullanıcı, sepet ve teklif durumlarını yönetme |
| Ödeme Sistemi           | Stripe API                              | Güvenli ödeme alma işlemleri               |
| API Testi               | Swagger                                 | Endpoint testleri ve dokümantasyonu        |

## 🏗️ Mimarî Yapı

Bu projede, sürdürülebilir ve genişletilebilir bir yazılım altyapısı oluşturmak amacıyla Katmanlı Mimari (Layered Architecture) yaklaşımı benimsenmiştir.

| Katman                 | Açıklama                                                                                                                                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Presentation (API)* | MyGalaxy_Auction projesinde yer alır. Kullanıcı isteklerini alır ve ilgili servis katmanına yönlendirir. ASP.NET Core API Controller'ları burada bulunur.                                                             |
| *Business*           | MyGalaxy_Auction_Business projesinde yer alır. İş kuralları ve uygulama mantığı bu katmanda tanımlanır. Servisler ve iş akışı bu bölümde şekillendirilir.                                                             |
| *Core*               | MyGalaxy_Auction_Core projesinde yer alır. Ortak yapı, model sınıfları, yardımcı fonksiyonlar ve sabitler gibi bağımsız kodlar burada tutulur. Katmanlar arası geçişte sözleşmelerin (interface) yer aldığı bölümdür. |
| *Data Access*        | MyGalaxy_Auction_Data_Access projesinde bulunur. Veritabanı işlemleri (CRUD) Entity Framework Core kullanılarak bu katmanda gerçekleştirilir. Ayrıca Migrations klasörü burada yer alır.                            |

### 🎯 Amaçlar ve Avantajlar

Katmanlı mimari tercih edilerek uygulama daha modüler, test edilebilir ve sürdürülebilir hale getirilmiştir. Bu mimarinin sağladığı başlıca avantajlar aşağıdaki gibidir:

- *🧩 Kodun Ayrışması*  
  Her katman belirli bir sorumluluğa sahiptir. Kullanıcı arayüzü (UI), iş mantığı (Business) ve veri erişimi (Data Access) gibi görevler net bir şekilde ayrılmıştır.

- *🧪 Yüksek Test Edilebilirlik*  
  Katmanlar arası bağımsızlık sayesinde her bir katman izole bir şekilde test edilebilir. Özellikle iş katmanı için birim test yazımı kolaylaşır.

- *♻️ Yeniden Kullanılabilirlik*  
  Özellikle servis ve veri erişim katmanları, farklı projelerde veya senaryolarda yeniden kullanılabilir yapıdadır.

- *🔧 Bakım Kolaylığı*  
  Hataların giderilmesi veya yeni özelliklerin eklenmesi sadece ilgili katman üzerinde yapılır. Bu da kod karmaşasını azaltır ve geliştirme sürecini hızlandırır.

- *🚀 Genişletilebilirlik*  
  Yeni bir özellik eklenmek istendiğinde mevcut katmanlar bozulmadan sisteme entegre edilebilir.

## 🧪 Test Bilgileri

Uygulamayı test etmek için aşağıdaki senaryoları kullanabilirsiniz:

- *🔁 SignalR Gerçek Zamanlı Güncelleme Testi*  
  Aynı ürün detay sayfasını iki farklı tarayıcı sekmesinde açarak bir sekmeden teklif verin. Diğer sekmede teklifin anlık olarak güncellendiğini gözlemleyebilirsiniz.

- *💳 Stripe Test Ödeme Bilgileri*  


- *🧪 API Testleri (Swagger / Postman ile)*  
  > ![Swagger](https://i.imgur.com/H9Ypvk6.png)
  Veritabanı yapılandırıldıktan sonra API uç noktalarını test etmek için [Swagger UI](https://swagger.io/tools/swagger-ui/) ya da [Postman](https://www.postman.com/) kullanabilirsiniz.  
  - Kullanıcı kayıt ve giriş işlemleri  
  - Ürün ekleme / listeleme  
  - Teklif gönderme  
  - Ödeme işlemleri gibi tüm API'leri detaylı şekilde test edebilirsiniz.

> Swagger arayüzü genellikle /swagger endpoint'inde yayınlanır. Örneğin: https://localhost:5001/swagger

## 📬 İletişim

Benimle her zaman iletişime geçebilirsiniz:

[![Web Sitem](https://img.shields.io/badge/Web%20Site-1976d2?style=for-the-badge&logo=google-chrome&logoColor=white)](https://emremeralzn.github.io/myblog/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/emre-meralsm/)

---

> Proje, modern web standartlarına uygun olarak geliştirilmiştir.  
> Hem güvenli hem de kullanıcı dostu bir açık artırma deneyimi sunar.
