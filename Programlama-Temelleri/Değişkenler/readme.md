
## Değişken Nedir?
Değişkenler, verileri depolamak için kullanılan hafıza alanlarıdır. Bir bilgisayar programı çalışırken sayılara, metinlere veya mantıksal değerlere ihtiyaç duyar. Bu değerleri tutmak ve daha sonra kullanmak veya değiştirmek için değişkenleri kullanırız.

**Temel Tanımlama Kuralı:**
Bir değişken oluştururken onun hangi tür veri (sayı, metin vb.) tutacağını baştan belirtmeniz gerekir.

```csharp
veri_tipi degiskenAdi = deger;
int sayi1 = 10;
```

---

## Temel Veri Tipleri ve Kullanımları

### 1. Tam Sayılar (`int`, `long`, `short`, `byte`)
Küsuratı olmayan tam sayıları tutmak için kullanılırlar. En yaygın kullanılanı `int`'tir.

*   **`int`**: Standart tam sayı (-2,147,483,648 ile 2,147,483,647 arası). Matematiksel işlemler ve sayma işlemleri için idealdir.
*   **`long`**: Çok daha büyük sayılar için kullanılır (sonuna `L` konulması tavsiye edilir).

```csharp
int yas = 25;
int ogrenciSayisi = 1500;
long dunyaNufusu = 8000000000L;
```

### 2. Ondalıklı Sayılar (`double`, `float`, `decimal`)
Kesirli/ondalıklı sayıları tutmak için kullanılırlar. 

*   **`double`**: Varsayılan ondalıklı sayı tipidir. Bilimsel hesaplamalarda sıkça kullanılır.
*   **`float`**: Daha az hassasiyet gerektiren durumlarda kullanılır, bellekte daha az yer kaplar. Değerin sonuna `f` veya `F` konulmalıdır.
*   **`decimal`**: Finansal ve parasal işlemler için kullanılır çünkü yuvarlama hataları yapmaz. Değerin sonuna `m` veya `M` konulmalıdır.

```csharp
double piDegeri = 3.1415926535;
float sicaklik = 36.5f;
decimal urunFiyati = 199.99m;
```

### 3. Metin ve Karakterler (`string`, `char`)
Yazıları ve tekil karakterleri tutmak için kullanılırlar.

*   **`string`**: Metin (kelime, cümle) tutar. Değerler çift tırnak `""` içine yazılır.
*   **`char`**: Sadece tek bir karakter tutar. Değerler tek tırnak `''` içine yazılır.

```csharp
string kullaniciAdi = "Ramazan Kansu";
string okulIsmi = "Keçiborlu MYO";
char Sinif = 'A';
char secim = 'E'; // Evet'in E'si
```

### 4. Mantıksal Değerler (`bool`)
Sadece iki farklı değer alabilen veri tipidir: `true` (doğru) veya `false` (yanlış).

*   Genellikle koşul ifadelerinde (if-else) ve döngülerde kontrol mekanizması olarak kullanılır.

```csharp
bool oyunBittiMi = false;
bool yetiskinMi = true;
bool kayitBasariliMi = true;
```

---


## Değişken İsimlendirme Kuralları

C#'ta değişkenlere isim verirken uymanız gereken bazı kurallar vardır:

**Zorunlu Kurallar:**
1.  Değişken isimleri sayıyla başlayamaz. (`1sayi` olmaz, `sayi1` olur)
2.  Boşluk içeremez. (`kullanici adi` olmaz, `kullaniciAdi` olur)
3.  C#'a özel anahtar kelimeler (`int`, `class`, `void` vb.) isim olarak kullanılamaz.
4.  Özel karakterler içeremez (Sadece `_` (alt çizgi) kullanılabilir).

**Tavsiye Edilen Standartlar:**
*   **camelCase:** Değişken isimleri küçük harfle başlar, sonraki her kelimenin ilk harfi büyük yazılır. (Örn: `musteriBakiyesi`, `dogumTarihi`)
*   Değişken isimleri açıklayıcı olmalıdır. (`a` ve `b` gibi isimler yerine `genislik` ve `yukseklik` kullanın).

---

## Özet Tablosu

| Veri Tipi | Ne İşe Yarar? | Örnek Atama |
| :--- | :--- | :--- |
| `int` | Tam Sayı | `int x = 5;` |
| `double` | Ondalıklı Sayı | `double y = 5.99;` |
| `decimal` | Finansal Sayı | `decimal para = 10.50m;` |
| `char` | Tek Karakter | `char harf = 'A';` |
| `string` | Metin | `string isim = "Ali";` |
| `bool` | Doğru/Yanlış | `bool aktifMi = true;` |
