

## 1. Düzen ve Esnek Kutu (Layout & Flexbox) Özellikleri

Sayfadaki elemanları yan yana, alt alta veya ekranda istenilen yere hizalamak için kullanılır.

### `display`
* **Anlamı:** Div'in ekrandaki görünüm ve düzenleme modunu belirler.
* **Kullanılan Değerler:**
  * `flex`: Div'i ve içindeki divleri esnek kutu düzenine çevirir.
  * `block`: Div'i tam satır kaplayan bir blok yapar (`<div>`, `<p>` gibi).
  * `none`: Div'i tamamen gizler.
* **Örnek:** `display: flex;`

### `justify-content`
* **Anlamı:** Flexbox yapısındaki iç elemanları **yatay eksende**  hizalar veya aralarını açar.
* **Kullanılan Değerler:**
  * `center`: İçerikleri yatayda tam ortalar.
  * `space-between`: İlk Div'i en sola, son Div'i en sağa yaslar; diğerlerinin arasını eşit açar.
* **Örnek:** `justify-content: center;`

### `align-items`
* **Anlamı:** Flexbox yapısındaki iç elemanları **dikey eksende**  hizalar.
* **Kullanılan Değerler:**
  * `center`: İçerikleri dikeyde tam ortalar.
* **Örnek:** `align-items: center;`

### `gap`
* **Anlamı:** Flexbox yapısındaki yan yana veya alt alta duran kutuların **arasındaki boşluk mesafesini** ayarlar.
* **Örnek:** `gap: 10px;`

---

## 2. Boyutlandırma  Özellikleri

Kutuların ve elemanların genişlik ve yükseklik ölçülerini belirler.

### `width`
* **Anlamı:** Div'in **genişliğini** belirler. Piksel (`px`) veya yüzde (`%`) cinsinden verilebilir.
* **Örnek:** `width: 100%;` veya `width: 320px;`

### `height`
* **Anlamı:** Div'in **yüksekliğini** belirler.
* **Örnek:** `height: 500px;`

---

## 3. Kutu Modeli ve Boşluk Özellikleri

Kutuların içindeki ve dışındaki mesafeleri yönetir.

### `padding`
* **Anlamı:** **İç boşluk.** Div'in kendi kenarlıkları ile içindeki yazı/içerik arasındaki mesafeyi ayarlar.
* **Örnek:** `padding: 20px;`

### `margin`
* **Anlamı:** **Dış boşluk.** Div'in etrafındaki diğer komşu elemanlarla arasındaki uzaklığı ayarlar.
* **Örnek:** `margin: 0;` veya `margin: 15px auto;` *(Üst/alt 15px, sağ/sol otomatik ortala)*

### `margin-bottom`
* **Anlamı:** Div'in **sadece alt tarafına** dış boşluk ekler. Kutuların alt alta yapışmasını engeller.
* **Örnek:** `margin-bottom: 10px;`

### `margin-top`
* **Anlamı:** Div'in **sadece üst tarafına** dış boşluk ekler.
* **Örnek:** `margin-top: 20px;`

---

## 4. Kenarlık ve Şekillendirme (Border) Özellikleri

Kutuların etrafına çizgi çekme ve köşelerini ovalleştirme işlemlerini yapar.

### `border`
* **Anlamı:** Div'in etrafına kenarlık çeker. Sırasıyla **Kalınlık**, **Stil** (solid, dashed vb.) ve **Renk** değerlerini alır.
* **Örnek:** `border: 2px solid black;`

### `border-collapse`
* **Anlamı:** Tablolarda (`<table>`) hücrelerin çift kat görünen çizgilerini birleştirerek **tek net çizgi** haline getirir.
* **Örnek:** `border-collapse: collapse;`

### `border-radius`
* **Anlamı:** Kutuların veya butonların keskin köşelerini yumuşatarak **ovalleştirir**.
* **Örnek:** `border-radius: 8px;`

---

## 5. Arka Plan ve Görsel Efekt Özellikleri

### `background-color`
* **Anlamı:** Div'in veya sayfanın **arka plan rengini** belirler. Renk adı (`red`), HEX kodu (`#e0f7fa`) veya RGB/HSL cinsinden verilebilir.
* **Örnek:** `background-color: lightblue;`

### `box-shadow`
* **Anlamı:** Kutunun veya kartın arkasına **gölge ve derinlik efekti** ekler.
* **Örnek:** `box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);`

### `transition`
* **Anlamı:** CSS özelliklerinde bir değişim olduğunda (örneğin butonun üzerine gelindiğinde rengin değişmesi), bu değişimin aniden değil **yumuşak bir animasyonla** geçiş yapmasını sağlar.
* **Örnek:** `transition: background-color 0.2s ease;`

---

## 6. Metin ve Tipografi (Typography) Özellikleri

Yazıların görünümünü, boyutunu ve hizalamasını düzenler.

### `color`
* **Anlamı:** **Metin (yazı) rengini** veya buton içindeki ikon/yazı rengini belirler.
* **Örnek:** `color: red;` veya `color: #1a202c;`

### `font-size`
* **Anlamı:** Yazı boyutunu (büyüklüğünü/küçüklüğünü) ayarlar.
* **Örnek:** `font-size: 24px;` veya `font-size: 1.25rem;`

### `font-weight`
* **Anlamı:** Yazının **kalınlık/incelik** derecesini ayarlar.
* **Kullanılan Değerler:** `bold` (kalın), `normal`, `600`, `bold` vb.
* **Örnek:** `font-weight: bold;`

### `font-family`
* **Anlamı:** Yazının **font ailesini (yazı tipini)** belirler.
* **Örnek:** `font-family: Arial, sans-serif;`

### `line-height`
* **Anlamı:** **Satır yüksekliği** (satırlar arasındaki dikey mesafe). Okunabilirliği artırır.
* **Örnek:** `line-height: 1.5;`

### `text-align`
* **Anlamı:** Metnin kutu içindeki **yatay hizalamasını** ayarlar.
* **Kullanılan Değerler:** `left` (sola), `center` (ortala), `right` (sağa).
* **Örnek:** `text-align: center;`

---

## 7. Etkileşim ve Durum (Interactivity & Pseudo-Classes) Özellikleri

Kullanıcının fare veya klavye eylemlerine yanıt veren özelliklerdir.

### `cursor`
* **Anlamı:** Fare imleci Div'in üzerine geldiğinde imlecin alacağı şekli belirler.
* **Kullanılan Değerler:** `pointer` (tıklanabilir el işareti), `default` (normal ok), `text` (yazı seçici).
* **Örnek:** `cursor: pointer;`

### `:hover` (Sözde Sınıf / Pseudo-class)
* **Anlamı:** Fare ile bir Div'in (buton, resim, kutu) **üzerine gelindiğinde** hangi stillerin geçerli olacağını tanımlar.
* **Örnek:**
```css
button:hover {
    background-color: coral;
}
```

---

## Özet Tablo: En Çok Karıştırılan İkililer

| CSS Özelliği | Ne İşe Yarar? | Neyi Etkiler? |
| :--- | :--- | :--- |
| **`padding`** | İç Boşluk | Kutunun içi ile içeriği (yazı/resim) arasındaki mesafe |
| **`margin`** | Dış Boşluk | Kutunun dışındaki diğer elemanlarla arasındaki mesafe |
| **`justify-content`** | Yatay Hizalama | Flexbox ana ekseninde (soldan sağa) hizalama |
| **`align-items`** | Dikey Hizalama | Flexbox çapraz ekseninde (yukarıdan aşağıya) hizalama |
