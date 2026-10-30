
## BÖLÜM 1: Değişkenler  Senaryosu

**Senaryo (Soru):** 
Bir e-ticaret sistemi geliştiriyorsunuz. Bir ürünün temel bilgilerini sistemde tutmanız gerekiyor. Ürünün adını, fiyatını, stok miktarını ve şu an kargoya verilip verilemeyeceği (stokta olup olmadığı) bilgisini değişkenlerde tutan ve ekrana yazdıran bir C# kodu yazınız.

**Çözüm (Kod):**
```csharp
string urunAdi = "Kablosuz Kulaklık";
double fiyat = 1499.99;
int stokMiktari = 45;
bool satistaMi = true;

Console.WriteLine("Ürün Adı: " + urunAdi);
Console.WriteLine("Fiyat: " + fiyat + " TL");
Console.WriteLine("Stokta Kalan: " + stokMiktari);
Console.WriteLine("Satışa Uygun mu?: " + satistaMi);
```

**Kod Açıklaması:**
* `string`: Metinsel bir veri olan ürün adını tutmak için kullanıldı.
* `double`: Fiyat bilgisi ondalıklı (kuruşlu) olabileceği için tercih edildi.
* `int`: Stok adedi küsuratlı olamayacağı için tam sayı tipi seçildi.
* `bool`: Ürünün satış durumu sadece "Evet/Hayır" veya "Doğru/Yanlış" olabileceği için (true/false) veri tipi kullanıldı.

---

## BÖLÜM 2: Döngüler Senaryosu

**Senaryo (Soru):** 
Bir spor salonu uygulamasında, kullanıcının hedefine ulaşması için 5 set şınav çekmesi gerekiyor. Ekrana 1'den 5'e kadar set numaralarını yazdıran ve 5. set bittiğinde "Tebrikler, antrenmanı tamamladınız!" mesajı veren bir kod yazınız.

**Çözüm (Kod):**
```csharp
for (int set = 1; set <= 5; set++)
{
    Console.WriteLine(set + ". Set tamamlandı.");
}
Console.WriteLine("Tebrikler, antrenmanı tamamladınız!");
```

**Kod Açıklaması:**
* Bu senaryoda döngünün kaç kere çalışacağı (5 kez) kesin olarak bilindiği için **for** döngüsü tercih edilmiştir.
* `int set = 1`: Seti sayısını belirten sayaç değişkenimiz 1'den başlatıldı.
* `set <= 5`: Döngünün çalışma şartı set sayısının 5'e eşit veya küçük olmasıdır.
* `set++`: Her adımda set numarası 1 artırılır.
* Döngü bittikten sonra (süslü parantezlerin dışına çıkıldığında) tebrik mesajı ekrana yazdırılır.

---

## BÖLÜM 3: Diziler Senaryosu

**Senaryo (Soru):** 
Bir öğretmensiniz ve 3 öğrencinizin ismini ve bu öğrencilerin matematik sınavından aldıkları notları tutmak istiyorsunuz. Öğrenci isimlerini ve notlarını iki ayrı dizide tanımlayıp, bir döngü yardımıyla "Öğrenci Adı - Notu" şeklinde eşleştirerek ekrana yazdıran kodu yazınız.

**Çözüm (Kod):**
```csharp
string[] ogrenciler = { "Ali", "Zeynep", "Can" };
int[] notlar = { 85, 95, 70 };

for (int i = 0; i < ogrenciler.Length; i++)
{
    Console.WriteLine("Öğrenci: " + ogrenciler[i] + " | Sınav Notu: " + notlar[i]);
}
```

**Kod Açıklaması:**
* İsimler metin olduğu için `string[]`, notlar tam sayı olduğu için `int[]` kullanılarak iki adet dizi oluşturuldu.
* Her iki dizinin de veri sayısı 3'tür. İndeksler 0, 1 ve 2'dir. (Örn: Ali'nin indeksi 0, Ali'nin notu olan 85'in indeksi de 0'dır.)
* Ekrana yazdırmak için `for` döngüsü kullanıldı. Döngü `i = 0`'dan başlayıp, dizinin içerisindeki veri sayısının uzunluğuna (`ogrenciler.Length` yani 3) kadar çalışır.
* `ogrenciler[i]` ve `notlar[i]` kullanılarak her adımda aynı indeks sırasına sahip isim ve not eşleştirilip ekrana basılır.


---
## Bölüm 4: Üniversite vize ve final ortalaması hesaplama

**Soru:**
Kullanıcıdan sırasıyla Vize ve Final notlarını girmesini isteyen bir program yazınız. Üniversite not sistemine göre Vize notunun %40'ı, Final notunun ise %60'ı alınarak dönem sonu ortalaması hesaplanmaktadır. Program, alınan notları ve hesaplanan yıl sonu ortalamasını ekrana düzgün bir formatta yazdırmalıdır.

**Çözüm (Kod):**

```csharp
// 1. Kullanıcıdan Vize notunu alma ve dönüştürme
Console.Write("Lütfen Vize notunuzu giriniz: ");
int vizeNotu = Convert.ToInt32(Console.ReadLine());

// 2. Kullanıcıdan Final notunu alma ve dönüştürme
Console.Write("Lütfen Final notunuzu giriniz: ");
int finalNotu = Convert.ToInt32(Console.ReadLine());

// 3. Ortalama Hesaplama (Vize %40, Final %60)
// Not: Çarpım sonucu ondalıklı çıkabileceği için ortalama değişkeni double olarak tanımlanmıştır.
double ortalama = (vizeNotu * 0.40) + (finalNotu * 0.60);

// 4. Sonuçları Ekrana Yazdırma ($ işareti ile String Interpolation kullanarak)
Console.WriteLine("-----------------------------------");
Console.WriteLine($"Girdiğiniz Notlar -> Vize: {vizeNotu} | Final: {finalNotu}");
Console.WriteLine($"Dönem Sonu Ortalamanız: {ortalama}");
```

**Kodun Açıklaması:**

1. `Console.Write`: Kullanıcıya ne girmesi gerektiğini soran bir mesaj ekrana basar (İmleci alt satıra atmaz, yanında bekler).
2. `Convert.ToInt32(Console.ReadLine())`: Kullanıcının girdiği notları önce `ReadLine` ile metin olarak okur, ardından `Convert.ToInt32` ile tam sayıya (`int`) çevirip `vizeNotu` ve `finalNotu` değişkenlerine kaydeder.
3. `double ortalama`: Vize notu $0.40$ ile, final notu ise $0.60$ ile çarpılır. Çıkan sonuç ondalıklı (küsuratlı) olabileceği için sonucu tutacak olan `ortalama` değişkeni `double` veri tipinde tanımlanmıştır.
4. `Console.WriteLine($"... {ortalama} ...")`: Kullanıcının girdiği notlar ve sistemin hesapladığı sonuç, `$` sembolü yardımıyla tek bir metin cümlesi içine yerleştirilerek kullanıcıya sunulur.
---

## BÖLÜM 5: Sınavda Çıkabilecek Senaryolar

**Soru:** 
Bilgisayarın arka planda 0 ile 9 arasında rastgele bir sayı tuttuğu bir tahmin oyunu yazınız. 
* Kullanıcıya bu sayıyı bilmesi için toplam **5 hak (can)** verilecektir.
* Kullanıcı her sayı girdiğinde sistem bu sayıyı kontrol etmeli; eğer girilen sayı tutulan sayıdan küçükse **"Daha büyük bir sayı giriniz"**, büyükse **"Daha küçük bir sayı giriniz"** şeklinde ipucu vermelidir.
* Kullanıcı doğru sayıyı tahmin ederse sistem "Tebrikler, bildiniz!" diyerek **döngüyü anında sonlandırmalıdır.**
* Kullanıcının 5 hakkı da tükenirse, oyun bitmeli ve ekrana bilgisayarın tuttuğu o gizli sayı yazdırılmalıdır.


## Çözüm Kodu

```csharp
Console.WriteLine("--- Sayı Tahmin Oyununa Hoş Geldiniz! ---");

int tutulanSayi = Random.Shared.Next(0, 10);
int can = 5;
//Ramazan Kansu
while (can > 0)
{
    Console.Write($"--------------------------------------\nKalan can sayısı {can}: Bir sayı girin: ");

    int tahmin = Convert.ToInt32(Console.ReadLine());

    if (tahmin == tutulanSayi){
        Console.WriteLine("Tebrikler, bildiniz!");
        break;
        }
    
    else if (tahmin < tutulanSayi){
        Console.WriteLine("Daha büyük bir sayı giriniz.");
        }
    else{
    Console.WriteLine("Daha küçük bir sayı giriniz.");
    }
    can--;    
}
     if (can == 0){
        Console.WriteLine($"\nTahmin hakkınız tükenmiştir. Tutulan sayı: {tutulanSayi}");
    }
```

---

## Kodun Detaylı Açıklaması

Bu program, kullanıcıdan veri alma, rastgele sayı üretme, döngü kontrolü ve koşullu dallanma (if-else) gibi C#'ın en temel taşlarını kullanır.

1. **Rastgele Sayı Üretimi:**
   `int tutulanSayi = Random.Shared.Next(0, 10);` 
   Sistem, 0 ile 10 arasında (10 dahil değil, yani 0-9 arası) rastgele bir tam sayı üretir ve bunu `tutulanSayi` değişkenine atar.

2. **Can Değişkeni:**
   `int can = 5;` 
   Kullanıcının kaç hakkı kaldığını takip etmek için bir değişken tanımlanır.

3. **Oyun Döngüsü (`while`):**
   `while (can > 0)` 
   Kullanıcının canı 0'dan büyük olduğu sürece döngü çalışmaya devam eder. Yani hak bitene kadar sorular tekrar sorulur.

4. **Kullanıcıdan Veri Alma ve Dönüştürme:**
   `int tahmin = Convert.ToInt32(Console.ReadLine());`
   Kullanıcının klavyeden girdiği değer (metin olarak gelir), `Convert.ToInt32` ile matematiksel bir tam sayıya (`int`) çevrilip `tahmin` değişkenine aktarılır.

5. **Koşul Kontrolleri (Oyunun Mantığı):**
   * **Doğru Tahmin:** `if (tahmin == tutulanSayi)` koşulu sağlanırsa, ekrana tebrik mesajı yazılır ve `break;` komutu ile döngü zorla sonlandırılarak oyun bitirilir.
   * **Küçük Tahmin:** `else if (tahmin < tutulanSayi)` ile girilen sayının küçük olup olmadığına bakılır ve kullanıcıyı yukarı yönlendirir.
   * **Büyük Tahmin:** `else` bloğu, yukarıdaki iki durum da gerçekleşmediyse (sayı doğru değilse ve küçük de değilse mecburen büyüktür) çalışır ve kullanıcıyı aşağı yönlendirir.

6. **Canın Azalması:**
   `can--;`
   Kullanıcı her tahminde bulunduğunda (döngünün her turunda) can değişkeni 1 azaltılır. (Bu ifade `can = can - 1;` ile aynı işi yapar).

7. **Oyunun Kaybedilmesi:**
   `if (can == 0)`
   Eğer can değişkeni 0'a ulaşırsa kullanıcının hakkı bitmiş demektir. Döngü bitmeden hemen önce bu blok çalışır ve tutulan sayı ekrana yazdırılarak oyun sonlandırılır.
