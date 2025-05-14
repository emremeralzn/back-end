🚀 Modern Web Geliştirme ile Açık Artırma Uygulaması
Bu proje, modern web teknolojileri kullanılarak geliştirilmiş, gerçek zamanlı açık artırma işlemlerini destekleyen tam kapsamlı bir web uygulamasıdır. SignalR ile anlık güncellemeler, JWT ile güvenli kullanıcı yönetimi, Stripe ile ödeme altyapısı ve MSSQL veritabanı üzerinde Code-First mimarisi kullanılmıştır.

🔍 Proje Hakkında
Kullanıcılar, araç, elektronik, müzik aletleri, emlak ve giyim kategorilerinde ürünler ekleyebilir ve bu ürünlere açık artırma usulüyle teklif verebilir. SignalR sayesinde teklifler anlık olarak tüm kullanıcılarla senkronize edilir. Ödeme işlemleri Stripe üzerinden güvenli bir şekilde gerçekleştirilir.

| Özellik                                | Açıklama                                                              |
| -------------------------------------- | --------------------------------------------------------------------- |
| 🧑‍💼 Kullanıcı Kayıt / Giriş Sistemi  | JWT ile kimlik doğrulama ve güvenli oturum yönetimi                   |
| ⚡ Gerçek Zamanlı Teklif Güncellemeleri | SignalR ile canlı teklif artışları ve anlık bildirimler               |
| 💳 Stripe ile Ödeme Entegrasyonu       | Kullanıcıların güvenli ödeme yapabilmesi için Stripe API entegrasyonu |
| 🧾 Ürün Listeleme ve Filtreleme        | Kategori bazlı arama ve ürün listeleme özellikleri                    |
| 📦 Code-First Entity Framework (MSSQL) | MSSQL ve EF Core ile modern veri modellemesi                          |
| 🧑‍💻 Yönetici Paneli (Admin Panel)    | Ürün ve kullanıcı yönetimi için özel yönetim ekranları                |



📦 Kategoriler
Uygulama aşağıdaki ana ürün kategorilerini desteklemektedir:

🚗 Vehicles (Araçlar)

💻 Electronic (Elektronik)

🎸 Musical Instruments (Müzik Aletleri)

🏠 Estates (Gayrimenkul)

👗 Dresses (Kıyafetler)


| *Bileşen*                 | *Teknoloji / Araç*                       | *Açıklama*                                   |
| --------------------------- | ------------------------------------------ | ---------------------------------------------- |
| *Backend*                 | ASP.NET Core 8                             | API ve iş mantığı katmanı                      |
| *Gerçek Zamanlı İletişim* | SignalR                                    | Anlık teklif güncellemeleri                    |
| *Kimlik Doğrulama*        | JWT (JSON Web Token)                       | Kullanıcı oturumları ve yetkilendirme          |
| *Veritabanı*              | MSSQL + Entity Framework Core (Code-First) | Veritabanı yönetimi ve veri modeli oluşturma   |
| *Frontend*                | React.js + Vite                            | Kullanıcı arayüzü                              |
| *Durum Yönetimi*          | React Context API                          | Kullanıcı, sepet ve teklif durumlarını yönetme |
| *Ödeme Sistemi*           | Stripe API                                 | Güvenli ödeme alma işlemleri                   |
| *API Testi*               | Postman / Swagger                          | Endpoint testleri ve dokümantasyonu            |
| *Paket Yöneticisi*        | NuGet (Backend), NPM (Frontend)            | Bağımlılık yönetimi                            |
| *Geliştirme Ortamı*       | Visual Studio, VS Code                     | Kodlama ve hata ayıklama                       |
| *Versiyon Kontrolü*       | Git + GitHub                               | Sürüm takibi ve ekip içi işbirliği             |

<pre><code>
  ## 📁 Klasör Yapısı 
  
   📦 MyGalaxy_Auction
├── 📁 Connected Services
├── 📁 Controllers                # API controller'ları
├── 📁 Extensions                # Extension methodlar
├── 📁 Hubs                      # SignalR hub sınıfları
├── 📁 Images                    # Görseller (örn: ürün resimleri)
├── 📄 appsettings.json         # Uygulama yapılandırmaları
├── 📄 Program.cs               # Giriş noktası
├── 📄 MyGalaxy_Auction.http     # API test dosyası

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

   </code></pre>

   🏗️ Mimarî Yapı
Bu projede, sürdürülebilir ve genişletilebilir bir yazılım altyapısı oluşturmak amacıyla Katmanlı Mimari (Layered Architecture) yaklaşımı benimsenmiştir.

| Katman                 | Açıklama                                                                                                                                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *Presentation (API)* | MyGalaxy_Auction projesinde yer alır. Kullanıcı isteklerini alır ve ilgili servis katmanına yönlendirir. ASP.NET Core API Controller’ları burada bulunur.                                                             |
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

---


   
### 🧪 Test Bilgileri

Uygulamayı test etmek için aşağıdaki senaryoları kullanabilirsiniz:

- *🔁 SignalR Gerçek Zamanlı Güncelleme Testi*  
  Aynı ürün detay sayfasını iki farklı tarayıcı sekmesinde açarak bir sekmeden teklif verin. Diğer sekmede teklifin anlık olarak güncellendiğini gözlemleyebilirsiniz.

- *💳 Stripe Test Ödeme Bilgileri*  
  Stripe ödeme testini gerçekleştirmek için aşağıdaki test kartı bilgilerini kullanabilirsiniz:
  
    Kart Numarası : 4242 4242 4242 4242
    Son Kullanım : 12/25
    CVC : 123

ilgili tablolar oluşturulduktan sonra bu komutun çalıştırılması gerekir: 
DROP INDEX IX_PaymentHistories_VehicleId ON PaymentHistories;

- *🧪 API Testleri (Swagger / Postman ile)*  
Veritabanı yapılandırıldıktan sonra API uç noktalarını test etmek için [Swagger UI](https://swagger.io/tools/swagger-ui/) ya da [Postman](https://www.postman.com/) kullanabilirsiniz.  
- Kullanıcı kayıt ve giriş işlemleri  
- Ürün ekleme / listeleme  
- Teklif gönderme  
- Ödeme işlemleri gibi tüm API'leri detaylı şekilde test edebilirsiniz.

> Swagger arayüzü genellikle /swagger endpoint'inde yayınlanır. Örneğin: https://localhost:5001/swagger

---




📜 Lisans
Bu proje MIT Lisansı ile lisanslanmıştır.
