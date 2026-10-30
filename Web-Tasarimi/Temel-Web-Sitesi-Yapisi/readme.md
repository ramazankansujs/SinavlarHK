
## 1. HTML Nedir?

**HTML**, bir programlama dili değil, bir **işaretleme dilidir (markup language)**. Web sayfalarının yapısını, metinlerini, görsellerini ve bağlantılarını düzenlemek için etiketler (`<tag>`) kullanır.

Bir web sitesini insan vücuduna benzetirsek:
* **HTML:** Sitemizde görünen her şey HTML ile yapılır ancak CSS olmadan dümdüz durur.
* **CSS:** HTML etiketlerine yani kodlarına görünüm kazandırır konumlandırmamızı sağlar renk verir görsel düzenleme olan her şeyi CSS ile yaparız.
* **JavaScript:** Etkileşime girmemiz gerektiğinde javaScript kullanırız, bi butona bastığında çalışması gibi.

---

## 2. Temel HTML5 Sayfa İskeleti

Standart ve modern bir HTML5 belgesi aşağıdaki temel yapıya sahiptir:

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <title>Web Sitemin Başlığı</title>
</head>
<body>

    <!-- Kullanıcının ekranda gördüğü tüm içerik buraya yazılır -->
    <h1>Web Sitemize Hoş Geldiniz</h1>
    <p>Bu benim ilk web sayfamın paragrafıdır.</p>

</body>
</html>
```

---

## 3. Etiketlerin Detaylı Açıklamaları ve Görevleri

### 1. `<!DOCTYPE html>`
* **İşlevi:** Belgenin **HTML5** standartlarında yazıldığını tarayıcıya (Chrome, Safari, Firefox vb.) bildiren etikettir.

* **Neden Önemli?:** Tarayıcının sayfayı modern kurallara göre hatasız ve hızlı bir şekilde işlemesini  sağlar.

### 2. `<html lang="tr">` ... `</html>`
* **İşlevi:** Web sayfasının **kök (ana) elemanıdır**. Sayfadaki tüm diğer etiketler bu iki etiketin arasında yer alır.

---

### 3. `<head>` ... `</head>`
* **İşlevi:** Kullanıcının ekranda **doğrudan görmediği**, ancak sayfanın arka planındaki ayarlarını, kimlik bilgilerini ve dış kaynak bağlantılarını barındıran bölümdür.

* **`<title>` ... `</title>`:**
  * Tarayıcının üst sekmesinde (tab) görünen başlık yazısını ve Google arama sonuçlarındaki ana başlığı belirler.

---

### 4. `<body>` ... `</body>` (Sayfa Gövdesi)
* **İşlevi:** Bir web sitesini ziyaret ettiğinizde ekranda gördüğünüz **her şey** (metinler, resimler, videolar, butonlar, formlar) `<body>` etiketleri içinde yer alır.
