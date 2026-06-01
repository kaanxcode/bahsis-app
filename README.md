# 🐷 Bahşiş Kumbaram (Tip Tracker)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap_5-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)

**Bahşiş Kumbaram**, otel çalışanları ve hizmet sektörü profesyonelleri için geliştirilmiş, çoklu para birimi (TL, USD, EUR, GBP) destekli modern bir bahşiş takip uygulamasıdır. 

Kullanıcıların günlük gelir ve giderlerini kayıt altına almasını, haftalık/aylık istatistiklerini takip etmesini ve verilerini bulut üzerinde güvenle saklamasını sağlar. Tamamen mobil uyumlu (Responsive) ve PWA mantığına yakın bir SPA (Single Page Application) olarak tasarlanmıştır.

---

## ✨ Özellikler

* **Çoklu Para Birimi Desteği:** TL (₺), Dolar ($), Euro (€) ve Pound (£) cinsinden işlem yapabilme.
* **Bulut Tabanlı Senkronizasyon:** Firebase entegrasyonu sayesinde veriler bulutta tutulur; herhangi bir cihazdan giriş yapıldığında geçmiş verilere anında erişim sağlanır.
* **Kalıcı Oturum Yönetimi:** Firebase Auth ile güvenli kullanıcı girişi ve kalıcı oturum. Cihazdan "Çıkış Yap" denilmediği sürece oturum açık kalır.
* **Gelişmiş İstatistikler:** Tüm para birimlerinde ayrı ayrı haftalık ve aylık toplam bakiye görüntüleme.
* **Modern & Responsive UI:** Bootstrap 5 kullanılarak hazırlanan, yuvarlak hatlı, yumuşak renk tonlarına sahip "sevimli" ve modern tasarım. Mobil cihazlarda kusursuz görünüm.

---

## 🛠 Kurulum ve Çalıştırma

Uygulama statik dosyalar (HTML, CSS, JS) barındırdığı için herhangi bir sunucu kurulumu gerektirmez. Doğrudan GitHub Pages, Vercel veya Netlify gibi servislerde yayınlanabilir.

1.  Projeyi bilgisayarınıza klonlayın:
    ```bash
    git clone [https://github.com/KULLANICI_ADINIZ/bahsis-app.git](https://github.com/KULLANICI_ADINIZ/bahsis-app.git)
    ```
2.  Firebase Console üzerinden yeni bir proje oluşturun ve **Authentication** (Email/Password) ile **Firestore Database** özelliklerini aktif edin.
3.  `index.html` dosyasının en altındaki script etiketleri arasına kendi Firebase konfigürasyon bilgilerinizi ekleyin.
4.  Güvenlik için Firestore Rules kısmına aşağıdaki kuralı uygulayın:
    ```javascript
    rules_version = '2';
    service cloud.firestore {
      match /databases/{database}/documents {
        match /users/{userId}/transactions/{document=**} {
          allow read, write: if request.auth != null && request.auth.uid == userId;
        }
      }
    }
    ```
5. Kodlarınızı GitHub'a push'layın ve **Settings > Pages** sekmesinden yayınlayın.

---

## 🤖 Yapay Zeka Destekli Geliştirme

Bu projenin temel mimarisi, tasarımı ve kodlaması tamamen yapay zeka (Google Gemini) kullanılarak, özel prompt mühendisliği (Prompt Engineering) teknikleriyle oluşturulmuştur. 

Projeyi hayata geçiren temel "Prompt" aşağıda yer almaktadır:

> *"Benim için bahyşilerimi birkritirebileceğim bir web app tasarla otelde çalışıyorum türk lirası pound dolar ve euro olarak bahşiş alıyorum günlük bahşilerimi girebileceğim para çıkışı yapabileceğim her işlem kayıt altına alınsın ve gözüksün total paramı göerebileğim aylık ve haftalık bahşiişimi göreyeim ortala günlüğk ne akdar kazandım göçrebileğim uygulama çok kullanıcılı olsun ve hesap oluşturulsun öğle gfi,rlisin javascrşipt html bootstrap kulllajnh github pagesta yayınlaycağpım host edeceğim nereden oturum açrsam açayım eski datam gelsin bunun için firebase kullan buna uygun bir sisitem tasraala giriş yaptıktan sonra o cihazda çıkış yap demeden çıkış yapmasın tüm uygulama mobil uyumlu responsive olsun senden modern göze hoş gelen biraz sevimli, bir tasarım ve yazılım bekliyorum bqana kodu yaz ve tüm yayınlama adımlarını anlatabir yazı ver"*

---

<div align="center">
  <sub>Modern web teknolojileri ile 🤍 tarafından geliştirilmiştir.</sub>
</div>
