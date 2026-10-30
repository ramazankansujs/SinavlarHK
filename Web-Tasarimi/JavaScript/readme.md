

## 1. JavaScript'i HTML'e Bağlamak (`<script>` ve `onclick`)

JavaScript kodlarının HTML sayfasında çalışabilmesi o sayfa ile etkileşime girebileceğimiz anlamına gelir.

*   **`<script>` Etiketi:** HTML dosyası içinde (genellikle `<body>` etiketinin en sonuna) JavaScript kodlarımızı yazmak için açtığımız alandır.
*   **`onclick` Olayı (Event):** Bir butona tıklandığında hangi JavaScript fonksiyonunun çalıştırılacağını belirler. 
    *Örnek:* `<button type="button" onclick="yazdir()">yazdır</button>` (Butona basıldığında `yazdir` isimli fonksiyon çalışır. Type="Button" demezsek butona tıkladığımızda sayfa yenilenir.)

## 2. HTML Elemanlarını Seçmek: `document.getElementById()`

HTML sayfasındaki belirli bir elemanı, ona verdiğimiz **ID** (`id=""`) değeri ile bulup yakalamamızı sağlar.

```javascript
document.getElementById("isim") // HTML'deki id'si "isim" olan elemanı bulur.
document.getElementById("sonuc") // HTML'deki id'si "sonuc" olan elemanı bulur.
```

## 3. İçerik Okuma ve Değiştirme (`.value` ve `.innerHTML`)

HTML elemanlarını `getElementById` ile yakaladıktan sonra içlerindeki yazıları okuyabilir veya değiştirebiliriz.

### A. `<input>` İçindeki Veriyi Almak: `.value`
Kullanıcının metin kutularına (`<input type="text">` veya `<input type="password">`) girdiği verileri (yazıları) okumak için kullanılır.

```javascript
// Kullanıcının "isim" id'li kutuya yazdığı yazıyı alır ve "metin" değişkenine kaydeder.
var metin = document.getElementById("isim").value; 
```

### B. Ekrana Yazı Yazdırmak: `.innerHTML`
Bir `<p>`, `<h2>` veya `<div>` gibi etiketlerin açılış ve kapanışları arasındaki metni değiştirmek için kullanılır.

```javascript
// id'si "yazi" olan paragrafın içeriğini, az önce kutudan aldığımız "metin" ile değiştirir.
var metin = document.getElementById("isim").value; 
document.getElementById("yazi").innerHTML = metin;
```

## 4. CSS Stillerini JavaScript ile Değiştirmek (`.style`)

JavaScript sadece metinleri değil, sayfadaki elemanların tasarımlarını (CSS) da anlık olarak değiştirebilir.

**Kural:** CSS'te tire (`-`) ile yazılan özellikler, JavaScript'te bitişik ve ikinci kelimenin baş harfi büyük olacak şekilde yazılır. (Örn: `background-color` yerine `backgroundColor`).

```javascript
// 1. Yazı Rengini Değiştirme
document.getElementById("metinkutusu").style.color = "red";

// 2. Arka Plan Rengini Değiştirme (Tüm sayfanın - body)
document.body.style.backgroundColor = "#e0f7fa";

// 3. Yazı Tipi (Font) Ayarlarını Değiştirme
let metin = document.getElementById("font");
metin.style.fontSize = "24px";     // Yazı boyutunu büyütür
metin.style.fontWeight = "bold";   // Yazıyı kalın (bold) yapar
```

## 5. Değişkenler ve Mantıksal Kontroller (`var`, `let`, `if-else`)


### Değişken Tanımlama (`var` ve `let`)
Kutulardan okuduğumuz verileri bilgisayarın hafızasında geçici olarak tutmak için kullanılırlar.
```javascript
var kullanici = document.getElementById("kullanici").value; // Kullanıcı adını hafızaya al
var sifre = document.getElementById("sifre").value;         // Şifreyi hafızaya al
```

### Koşul Yapısı (`if - else`)
Gelen verilerin doğruluğunu kontrol edip, sonuca göre farklı işlemler yapmak için kullanılır.

*   `==` : Eşit mi? diye kontrol eder.
*   `&&` : **VE (AND)** operatörüdür. Her iki şartın da aynı anda doğru olması gerektiğini belirtir.

*   `&&` yazılmışsa iki koşulda kesin olarak gerçekleştiğinde çalışır. Anlamı "ve" demektir.
*   `||` yazılmışsa iki koşuldan biri bile doğruysa çalışır. Anlamı "veya" demektir.


```javascript
// EĞER kullanıcı adı "admin" ise VE şifre "1234" ise:
if (kullanici == "admin" && sifre == "1234") {
    document.getElementById("sonuc").innerHTML = "Sifre Doğru";
} 
// DEĞİLSE (şartlardan biri bile yanlışsa):
else {
    document.getElementById("sonuc").innerHTML = "Sifre Yanlis";
    alert("Kullanı adınız veya şifreniz yanlış.");
    // alert sayfanın üstünden alarm vermeyi sağlar
}
```

## ÖZET
1. **Olayı Bekle:** Kullanıcı butona basar (`onclick="kontrol()"`).
2. **Veriyi Yakala:** Kutulardaki bilgiler `getElementById().value` ile alınır ve değişkenlere atanır.
3. **Müdahale Et:** Alınan veriler ya `if-else` ile kontrol edilir ya da `.innerHTML` ve `.style` kullanılarak anında ekrana yansıtılıp tasarımları değiştirilir.
3. **Buton ve Input tipi:** Type="Button" demek zorundayız. Bunu yazmazsak butona bastığımızda sayfamızı yeniler ve yaptığımız işlem gözükmez. <input> içerisinde type="text" yazarsak içerisine yazdığımız yazılar gözükür. Gözükmesin istiyorsak örneğin şifre girişi vs. gibi durumlarda type="password" yazmak gerekir.
