

## 1. Algoritma Nedir?

**Algoritma**, belirli bir problemi çözmek, bir görevi yerine getirmek veya bir hedefe ulaşmak için izlenen, **kesinlikle sonu olan, açık ve net adımlardan oluşan** mantıksal işlem dizisidir.

Bilgisayarlar kendi başlarına düşünemezler. Onlara ne yapacaklarını son derece disiplinli, sıralı ve eksiksiz bir şekilde tarif etmemiz gerekir. İşte bu tarife **algoritma** denir.

> **Kısaca:** Algoritma, bilgisayara verilen adım adım işlem tarifidir.

---

## 2. Bir Algoritmanın Temel Özellikleri

Bir işlem dizisinin algoritma olarak kabul edilebilmesi için şu 5 temel kriteri karşılaması gerekir:

1. **Girdi (Input):** Algoritma dışarıdan sıfır veya daha fazla veri/bilgi alabilir.
2. **Çıktı (Output):** Algoritma en az bir sonuç veya çıktı üretmelidir.
3. **Kesinlik:** Algoritmanın her adımı net, anlaşılır ve tek bir anlama gelmelidir. Muğlak ifadelere yer yoktur.
4. **Sonluluk:** Algoritma sonsuz bir döngüde kalmamalı, belirli bir adım sayısından sonra mutlaka sonlanmalıdır.
5. **Etkinlik / Uygulanabilirlik :** Her adım, kağıt ve kalemle dahi mantıken yürütülebilecek kadar basit ve uygulanabilir olmalıdır.

---

## 3. Algoritma Geliştirme Adımları

Başarılı bir yazılım geliştirmek için algoritma tasarlarken şu süreç izlenir:

```
[ Problem Tanımı ] ──> [ Analiz & Girdiler ] ──> [ Algoritma Tasarımı ] ──> [ Test & İyileştirme ] ──> [ Kodlama ]
```

1. **Problemi Anlama:** Problemin ne olduğunu, sınırlarını ve bizden ne istendiğini tam olarak kavrama.
2. **Girdi ve Çıktıları Belirleme:** Hangi verilere sahibiz? Sonuçta ne elde etmek istiyoruz?
3. **Çözüm Yolu (Mantık) Kurgulama:** Problemi küçük parçalara bölerek adım adım çözümü tasarlama.
4. **Sözde Kod veya Akış Şeması Çizimi:** Çözümü kod yazmadan önce görselleştirme veya metne dökme.
5. **Test Etme (Tracing):** Farklı senaryolar ve uç değerler (edge cases) ile algoritmanın doğruluğunu kontrol etme.
6. **Kodlama:** Doğrulanan algoritmayı istenilen programlama diline (C#, Python, Java vb.) dönüştürme.

---

## 4. Algoritma Türleri

Problemin yapısına göre kullanılan temel algoritma türleri şunlardır:

### 1. Lineer / Doğrusal Algoritmalar
İşlemlerin baştan sona doğru, hiç dallanma (koşul) yapmadan sıra ile çalıştırıldığı en basit yapılardır.

### 2. Koşullu (Dallanan) Algoritmalar
Gelen verilere göre mantıksal bir karar verip farklı yollara sapan yapılardır (`if-else` / `switch-case`).

### 3. Döngüsel (Iterative) Algoritmalar
Belirli bir koşul sağlandığı sürece aynı adımları tekrar eden yapılardır (`for`, `while`).

### 4. Özyinelemeli (Recursive) Algoritmalar
Bir problemin çözümü için fonksiyonun kendi kendini daha küçük parametrelerle tekrar çağırdığı algoritmalar. (Örn: Faktöriyel hesaplama, Fibonacci dizisi).

### 5. Arama ve Sıralama Algoritmaları
Veri yığınları içinde aranan elemanı bulma (Linear Search, Binary Search) veya verileri belirli bir düzene sokma (Bubble Sort, Quick Sort) algoritmalarıdır.

---

## 5. Algoritma Karmaşıklığı 

Bir problemin birden fazla algoritma ile çözümü olabilir. Hangisinin **daha hızlı** veya **daha az bellek** kullandığını ölçmek için **Big O Gösterimi ($O$)** kullanılır.

* **$O(1)$ - Sabit Zaman:** Veri boyutu ne kadar büyürse büyüsün işlem süresi değişmez. (Örn: Bir dizinin ilk elemanına erişim)
* **$O(\log n)$ - Logaritmik Zaman:** Veri boyutu her adımda yarıya iner. Çok hızlıdır. (Örn: İkili Arama / Binary Search)
* **$O(n)$ - Doğrusal Zaman:** Veri boyutu arttıkça işlem süresi de aynı oranda artar. (Örn: Dizide baştan sona eleman aramak)
* **$O(n^2)$ - Karesel Zaman:** İç içe döngülerin olduğu, veri arttıkça sürenin karesi oranında yavaşlayan yapılardır. (Örn: Kabarcık Sıralaması / Bubble Sort)

---

## 6. Uygulamalı Örnek: En Büyük Sayıyı Bulma Algoritması

**Problem:** Kullanıcıdan alınan 3 sayı arasından en büyük olanını bulan algoritma.

### A. Metinsel Algoritma Adımları

1. Başla.
2. `Sayı1`, `Sayı2` ve `Sayı3` değerlerini kullanıcıdan oku.
3. `EnBüyük = Sayı1` kabul et.
4. Eğer `Sayı2 > EnBüyük` ise `EnBüyük = Sayı2` yap.
5. Eğer `Sayı3 > EnBüyük` ise `EnBüyük = Sayı3` yap.
6. `EnBüyük` değerini ekrana yazdır.
7. Bitir.

### B. C# Kodu Karşılığı

```csharp

        Console.Write("1. Sayıyı girin: ");
        int s1 = Convert.ToInt32(Console.ReadLine());

        Console.Write("2. Sayıyı girin: ");
        int s2 = Convert.ToInt32(Console.ReadLine());

        Console.Write("3. Sayıyı girin: ");
        int s3 = Convert.ToInt32(Console.ReadLine());

        int enBuyuk = s1;

        if (s2 > enBuyuk)
        {
            enBuyuk = s2;
        }

        if (s3 > enBuyuk)
        {
            enBuyuk = s3;
        }

        Console.WriteLine($"Girilmiş olan en büyük sayı: {enBuyuk}");
```


---
