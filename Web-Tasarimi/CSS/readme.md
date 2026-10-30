
## 1. CSS Nedir ve Ne İş Yapar?

**CSS (Cascading Style Sheets)**, HTML elemanlarının ekranda, kağıtta veya diğer medyalarda nasıl görüneceğini tanımlayan bir stil dilidir.
---

## 2. CSS'in HTML'e Ekleme Yöntemleri

CSS, HTML belgelerine 3 farklı yoldan eklenebilir:

### A. Satır İçi Stil 
Doğrudan HTML etiketinin `style` özniteliği içine yazılır. Sadece o etiketi etkiler.
> **Not:** Okunabilirliği düşürdüğü ve kod tekrarına sebep olduğu için genellikle **önerilmez**.

```html
<h1 style="color: blue; font-size: 24px;">Satır İçi Başlık</h1>
```

### B. Dahili Stil
HTML belgesinin `<head>` bölümü içine `<style>` etiketleri açılarak yazılır. Tek sayfadan oluşan küçük projeler için uygundur.

```html
<head>
    <style>
        p {
            color: gray;
            line-height: 1.5;
        }
    </style>
</head>
```

### C. Harici Stil  - **En İyi Uygulama**
CSS kodları `.css` uzantılı ayrı bir dosyada tutulur ve HTML sayfasına `<link>` etiketi ile bağlanır. Büyük projelerde standart yöntem budur.

**HTML Tarafı (`index.html`):**
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

**CSS Tarafı (`style.css`) dosyası içeriği:**
```css
body {
    background-color: #f4f4f4;
    font-family: Arial, sans-serif;
}
```

---

## 3. CSS'in yazılış biçimi:

CSS kod yapısı bir **Seçici ** ve **Bildirim Bloğundan** oluşur.

```css
seçici {
    özellik: değer;
    özellik2: değer2;
}
```

### Temel Seçici Türleri

#### 1. Eleman (Element) Seçici
Tüm ilgili HTML etiketlerini hedefler.

```css
h2 {
    color: darkred; /* Sayfadaki TÜM <h2> etiketlerini kırmızı yapar */
}
```

#### 2. Sınıf (Class) 'lar
HTML'de `class="..."` tanımı yapılmış etiketleri hedefler. Başına **nokta (`.`)** konur. Birden fazla elemana aynı sınıf verilebilir.

**HTML:** `<button class="css-dersi">Gönder</button>`  
**CSS:**
```css
.css-dersi {
    background-color: #007bff;
    color: white;
    border-radius: 4px;
}
```

#### 3. Kimlik (ID) Verme
HTML'de `id="..."` tanımı yapılmış **tekil** elemanı hedefler. Başına **kare/diyez/hashtag (`#`)** işareti konur. Bir ID sayfada sadece bir elemana verilmelidir.

**HTML:** `<header id="main-header">...</header>`  
**CSS:**
```css
#main-header {
    height: 80px;
    background-color: #333;
}
```

---

## 4. Kutu Modeli

CSS'te her HTML elemanı dikdörtgen bir kutu olarak değerlendirilir. **Kutu Modeli**, bir elemanın boyutunu ve etrafındaki boşlukları yöneten temel kuraldır.

```
+-----------------------------------+
|            MARGIN (Dış Boşluk)    |
|  +-----------------------------+  |
|  |         BORDER (Kenarlık)   |  |
|  |  +-----------------------+  |  |
|  |  |   PADDING (İç Boşluk) |  |  |
|  |  |  +-----------------+  |  |  |
|  |  |  |    CONTENT      |  |  |  |
|  |  |  |    (İçerik)     |  |  |  |
|  |  |  +-----------------+  |  |  |
|  |  +-----------------------+  |  |
|  +-----------------------------+  |
+-----------------------------------+
```

1. **Content (İçerik):** Metin, görsel vb. asıl içeriğin durduğu alan (`width` ve `height`).
2. **Padding (İç Boşluk):** İçerik ile kenarlık (border) arasında kalan boşluktur.
3. **Border (Kenarlık):** İçeriği ve padding'i çevreleyen çizgidir.
4. **Margin (Dış Boşluk):** Kutunun diğer dış elemanlarla arasındaki uzaklıktır.

**Örnek Kullanım:**
```css
.kart {
    width: 300px;
    padding: 20px;            /* Kutunun içinden 20px boşluk verir */
    border: 2px solid #ccc;  /* 2px kalınlığında gri düz çizgi */
    margin: 15px auto;        /* Üst/alt 15px, sağ/sol otomatik ortala */
}
```

---

## 5. Modern Düzen Yapısı: Flexbox

Esnek ve hizalaması kolay sayfa düzenleri (layouts) oluşturmak için kullanılan en popüler CSS modülüdür.

Parent (kapsayıcı) elemana `display: flex;` verilerek aktifleştirilir.

```css
.kapsayici {
    display: flex;
    justify-content: space-between; /* Yatayda elemanların arasını eşit açar */
    align-items: center;            /* Dikeyde elemanları ortalar */
}
```

---

## 6. Kapsamlı Örnek: Ürün Kartı Tasarımı

Aşağıda hem HTML hem de CSS'in birlikte nasıl kullanıldığını gösteren pratik bir örnek yer almaktadır.

### HTML Yapısı (`index.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Ürün Kartı Örneği</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="card">
        <h3 class="card-title">Keçiborlu MYO</h3>
        <p class="card-text">HTML, CSS ve javaScript dersleri konu anlatımı.</p>
        <div class="card-footer">
            <span class="price">299 TL</span>
            <button class="btn">Satın Al</button>
        </div>
    </div>

</body>
</html>
```

### CSS Yapısı (`style.css`)

```css
/* Genel Sıfırlama ve Gövde Ayarları */
body {
    background-color: #eef2f5;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

/* Kart Kapsayıcısı */
.card {
    background-color: #ffffff;
    width: 320px;
    padding: 24px;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

/* Kart İç Başlığı */
.card-title {
    margin-top: 0;
    color: #1a202c;
    font-size: 1.25rem;
}

/* Kart Açıklama Metni */
.card-text {
    color: #4a5568;
    font-size: 0.95rem;
    line-height: 1.5;
}

/* Alt Bilgi Hizalaması (Flexbox) */
.card-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 20px;
}

/* Fiyat Etiketi */
.price {
    font-size: 1.2rem;
    font-weight: bold;
    color: #2b6cb0;
}

/* Satın Al Butonu */
.btn {
    background-color: #319795;
    color: white;
    border: none;
    padding: 10px 18px;
    border-radius: 6px;
    cursor: pointer;
    font-weight: 600;
    transition: background-color 0.2s ease;
}

/* Buton Üzerine Gelindiğinde (Hover Efekti) */
.btn:hover {
    background-color: #2c7a7b;
}
```

### Kod Açıklaması:
1. **`box-shadow`**: Karta hafif bir gölge vererek sayfada 3 boyutlu bir derinlik algısı yaratır.
2. **`border-radius`**: Keskin köşeleri yumuşatarak ovalleştirir.
3. **`transition` & `:hover`**: Butonun üzerine fare ile gelindiğinde renk geçişini yumuşak bir animasyonla sağlar.
4. **`display: flex` (`.card-footer`)**: Fiyat bilgisi ve butonu dikeyde ortalar, yatayda zıt iki uca yaslar (`space-between`).

---

## Özet

* CSS, web sayfalarının **görsel sunumunu** kontrol eder.
* HTML elemanlarını hedeflemek için **Class (`.`)**, **ID (`#`)** veya **Etiket Adı** seçicileri kullanılır.
* **Box Model** (Content, Padding, Border, Margin) alan hesabının temelidir.
* Modern sayfa düzenleri için **Flexbox** en etkili araçtır.
