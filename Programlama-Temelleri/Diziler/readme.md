## Dizi (Array) Nedir?

Dizi, aynı veri tipine sahip (örneğin sadece sayılar veya sadece metinler) birden fazla değeri tek bir isim altında saklamamıza olanak tanıyan bir veri yapısıdır. 

Eğer 5 farklı öğrencinin yaşını değişkende tutmak isterseniz 5 ayrı değişken (`yas1`, `yas2`, ...) oluşturmak yerine, 5 verili tek bir `int[]` (tam sayı dizisi) oluşturmak çok daha pratik ve yönetilebilirdir.

> **Önemli Kural:** C#'ta dizilerin indeks numaraları (sıra numaraları) her zaman **0'dan başlar**. Yani ilk veri indeksi 0'dır, 1 değil.

---

## 1. Tam Sayı Dizileri: `int[]` Kullanımı

Sadece tam sayıları (integer) tutmak için kullanılır. Matematiksel işlemler, yaşlar, id numaraları gibi verileri gruplamak için idealdir.

### Tanımlama ve Değer Atama Yöntemleri

**Yöntem 1: Önce boyut belirleyip sonra değer atama**
Bu yöntemde dizinin kaç Verili olacağını (örneğin 3) baştan belirtiriz.

```csharp
// 3 Verili boş bir tam sayı dizisi oluşturduk.
int[] yaslar = new int[3];

// İndeks numaralarını kullanarak değerleri atıyoruz:
yaslar[0] = 25; // 1. Veri
yaslar[1] = 30; // 2. Veri
yaslar[2] = 22; // 3. Veri
```

**Yöntem 2: Tanımlama sırasında değerleri verme**
Dizinin boyutunu yazmaya gerek kalmadan, süslü parantezler `{}` içinde değerleri doğrudan verebiliriz.

```csharp
int[] notlar = new int[] { 85, 90, 78, 100, 60 };

// Daha kısa bir kullanım:
int[] puanlar = { 50, 60, 70, 80 };
```

### Verileri Okuma ve Değiştirme
```csharp
int ilkPuan = puanlar[0]; // 50 değerini okur ve ilkPuan yazan yere artık 50 yazar.
// Örneğin Console.WriteLine(ilkPuan); yazdığımızda ekranda 50 yazar.


puanlar[1] = 65;          // 60 olan 2. veriyi 65 olarak günceller
//Bu güncelleme öncesinde Console.WriteLine(puanlar[1]); yazdığımız yerde 60 yazacaktı güncellediğimiz için 65 yazacak.
```

---

## 2. Metin Dizileri: `string[]` Kullanımı

Sadece metin (karakter dizisi) verilerini tutmak için kullanılır. İsim listeleri, günler, aylar, ürün adları gibi veriler için kullanılır. Metinler mutlaka çift tırnak `""` içinde yazılmalıdır.

### Tanımlama ve Değer Atama Yöntemleri

**Yöntem 1: Boyut belirleyerek tanımlama**
```csharp
string[] haftaninGunleri = new string[];
haftaninGunleri[0] = "Pazartesi";
haftaninGunleri[1] = "Salı";
// ... diğer günler
```

**Yöntem 2: Tanımlama sırasında değer verme**
```csharp
string[] meyveler = { "Elma", "Armut", "Muz", "Çilek" };
```

### Veri Okuma ve Değiştirme
```csharp
string sevdigimMeyve = meyveler[2]; // "Muz" değerini okur çünkü 0'dan başlar ve Muz 2'inci sıraya düşer Elma 0'dır. Armut ise 1.

meyveler[0] = "Yeşil Elma";         // "Elma" değerini "Yeşil Elma" olarak günceller
```

---

## Dizilerle Çalışırken 

### Dizinin Uzunluğunu Bulma: `Length`
Bir dizide toplam kaç Veri olduğunu öğrenmek için `.Length` özelliği kullanılır. 

```csharp
string[] sehirler = { "İstanbul", "Ankara", "İzmir" };
int sehirSayisi = sehirler.Length; 
// sehirSayisi değişkeninin değeri 3 olur.
```

### Dizileri Döngülerle Kullanmak
Dizilerin en yakın arkadaşı `for` ve `foreach` döngüleridir.

**`for` döngüsü ile:**
```csharp
int[] sayilar = { 10, 20, 30, 40 };

for (int i = 0; i < sayilar.Length; i++)
{
    Console.WriteLine($"{i} - Değer: {sayilar[i]}");
}
```
i 0'dan başlattık ve sayilar.Length diyerek 4 değer olduğu için i 4'den küçük olduğu sürece dedik.
0'dan başladığı için 4'den küçük dememiz gerekiyor. 4'e eşit deseydik 5 tane dizin olması gerekirdi.
0-1-2-3-4 şeklinde 5 tane olacaktı ve 5'inci dizinimiz olmadığı için hata vericekti.
4'den küçük olduğu sürece dediğimiz için 0-1-2-3 ile 4 tane dizin okuyacak.

i 0'dan başladığı için 0'ıncı dizinimiz yani 10'u okuyacak ve i'yi 1 arttıracak.
1'inci dizinimiz 20 olduğu için ekrana 20 yazıcak ve böyle 4'e kadar artıcak.


**`foreach` döngüsü ile :**
```csharp
string[] arabalar = { "Volvo", "BMW", "Ford", "Mazda" };

foreach (string araba in arabalar)
{
    Console.WriteLine(araba);
}
```

Arabalar ismindeki dizindeki bütün değerleri tek tek okuyacak ve ekrana yazdıracak.



## Özet
*   `int[]` sayıları, `string[]` metinleri listelemek için kullanılır.
*   Dizi verilerine erişmek için `[]` (köşeli parantez) kullanılır.
*   **İndeksler 0'dan başlar!** Uzunluğu 5 olan bir dizinin son verisine ulaşmak için 4 yazılır.
