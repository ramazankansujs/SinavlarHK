# HTML'de Kutu Modeli: `<div>` ve `class` Kullanım Rehberi

Bir web sitesi tasarlarken ekrandaki elemanları (yazılar, resimler, butonlar) yan yana, alt alta veya belirli gruplar halinde dizmemiz gerekir. İşte bu gruplama ve düzenleme işleminin kahramanları **`<div>`** etiketi ve **`class`** niteliğidir.

## 1. `<div>` (Division) Nedir?

`<div>` kelimesi İngilizce "Division" (Bölüm/Kısım) kelimesinin kısaltmasıdır. 

Kendi başına **hiçbir görsel özelliği yoktur**. Renksiz, şeffaf ve boş bir **kutu (konteyner)** gibidir. İçerisine yazılar, resimler, tablolar veya başka div'ler koyarak bunları tek bir paket haline getirmenizi sağlar.

**Neden `<div>` Kullanırız?**
* **Gruplama:** Örneğin bir haber sitesindeki "Haber Başlığı", "Haber Resmi" ve "Devamını Oku" butonunu tek bir `<div>` içine alırsak, bu üç elemanı ekranda bir bütün olarak hareket ettirebiliriz.
* **Düzen (Layout):** Sayfayı sağ, sol, orta, üst ve alt gibi parçalara bölmek için kullanılır. Biz CSS ile müdahale edene kadar yanına başka bir eleman kabul etmez, tüm satırı kaplar.

## 2. `class` (Sınıf) Nedir?

Bir web sayfasında onlarca, hatta yüzlerce `<div>` olabilir. Tarayıcıya "Sadece soldaki div'in rengini kırmızı yap" diyebilmek için o div'e bir isim/etiket vermemiz gerekir. İşte **`class`** bu etiketlendirme işini yapar.

Bir `class` ismini sayfa içinde **birden fazla** elemana verebilirsiniz. (Örneğin sayfadaki tüm butonlara `class="kirmizi-buton"` verebilirsiniz).

* CSS'te class'ları oluşturmak için isminin başına **nokta (`.`)** konur.

### `class` vs `id` Farkı Nedir?
* **`class`:** Sınıf gibidir. İçinde birçok öğrenci (eleman) olabilir. (Örn: `.ogrenci`)
* **`id`:** TC Kimlik Numarası gibidir. Bir sayfada aynı `id` sadece **bir tane** elemana verilebilir. (Örn: `#okul-muduru`)

## 3. `<div>` ve `class` Birlikte Nasıl Kullanılır?

İkisinin uyumu web tasarımının temelidir. HTML'de kutuları (`<div>`) oluşturur ve isimlendiririz (`class`), CSS'te ise bu kutuları boyar ve yerleştiririz.

### Adım 1: HTML Tarafı (İskelet ve Gruplama)

Aşağıda sayfayı 3 parçaya böldüğümüz bir yapı var:

```html
<!-- Tüm sayfayı kaplayan ana taşıyıcı (kapsayıcı) div -->
<div class="sayfa-kapsayici">

    <!-- Sol Menü -->
    <div class="sol-menu">
        <p>Burası sol menüdür.</p>
    </div>

    <!-- Ana İçerik (Orta Kısım) -->
    <div class="ana-icerik">
        <h2>Hoş Geldiniz</h2>
        <p>Burası web sitemizin ana gövdesidir.</p>
    </div>

</div>
```

### Adım 2: CSS Tarafı (Şekillendirme ve Yerleştirme)

Yukarıda verdiğimiz `class` isimlerini CSS'te çağırarak (nokta ile) şekil verelim:

```css
/* Ana Kapsayıcıyı esnek yapı (Flexbox) yapıyoruz ki içindekiler yan yana gelsin */
.sayfa-kapsayici {
    display: flex; /* aşağıdaki özelliklerin çalışması için div'i flex yapıya dönüştürür.*/
    gap: 20px; /* Kutular arasına 20 piksel boşluk koy */
    padding: 10px;
}

/* Sol menü kutusunun ayarları */
.sol-menu {
    width: 25%; /* Ekranın %25'ini kapla */
    background-color: lightblue;
    padding: 15px;
    border-radius: 8px; /* Köşeleri yuvarlat */
}

/* Ana içerik kutusunun ayarları */
.ana-icerik {
    width: 75%; /* Ekranın %75'ini kapla */
    background-color: lightgreen;
    padding: 15px;
    border: 2px solid black; /* Etrafına siyah çizgi çek */
    
}


```

## 4. Birden Fazla Class Kullanımı

Bir HTML elemanına aynı anda birden fazla `class` verebilirsiniz. Aralarında sadece **boşluk** bırakmanız yeterlidir.

```html
<div class="kutu uyari golgeli">Bu bir uyarı kutusudur.</div>
```
Bu sayede eleman hem `.kutu` class'ının, hem `.uyari` class'ının, hem de `.golgeli` class'ının CSS özelliklerini aynı anda alır. Kod tekrarını önler ve işleri çok hızlandırır.

## Özet

1. **`<div>`** görünmez bir poşettir. İçine başka eşyalar (metinler, resimler) koyup taşımamızı sağlar.
2. **`class`** o poşetin üzerine yapıştırdığımız isim etiketidir ("Mutfak Eşyaları", "Kırtasiye" gibi).
3. Sayfayı tasarlarken HTML'de bolca `<div>` kullanır, onlara `class` ile isim verir, ardından CSS dosyasına geçip bu `class` isimlerini çağırarak renk, boyut ve konum ayarlarını yaparız.
