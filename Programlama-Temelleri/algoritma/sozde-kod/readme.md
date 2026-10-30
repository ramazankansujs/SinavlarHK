

## 1. Sözde Kod (Pseudocode) Nedir?

**Sözde Kod (Pseudocode)**, bir algoritmanın herhangi bir programlama dilinin (C#, Python, Java vb.) katı sözdizimi (syntax) kurallarına bağlı kalmaksızın, insan konuşma diline yakın bir yapıda ve kod mantığına uygun olarak kaleme alınmış halidir.

Sözde kod gerçek bir programlama dili değildir ve bir bilgisayar tarafından doğrudan çalıştırılamaz. Ancak kod yazmaya başlamadan önce algoritmanın mantıksal kurgusunu planlamak için kullanılır.

## 2. Neden Sözde Kod Kullanılır?

* **Sözdizimi (Syntax) Hatalarından Bağımsızlık:** Süslü parantezler `{ }`, noktalı virgüller `;` veya değişken tipi tanımlamalarıyla vakit kaybetmeden doğrudan **mantiğa ve çözüme** odaklanmayı sağlar.
* **Kolay Anlaşılabilirlik:** Yazılımcı olmayan bir proje yöneticisi veya iş analisti dahi yazılan sözde kodu okuyup algoritmanın doğru çalışıp çalışmadığını kavrayabilir.
* **Dil Bağımsızlığı:** Yazılan bir sözde kod, istenilen herhangi bir programlama diline (C#, C++, Python vb.) kolaylıkla dönüştürülebilir.
* **Hızlı Tasarım:** Karmaşık projelerde kod yazmaya geçmeden önce algoritmayı test etmenin en hızlı ve maliyetsiz yoludur.

## 3. Temel Sözde Kod Yapıları ve Terimleri

Sözde kod yazarken standart bir kural olmamakla birlikte, evrensel kabul görmüş bazı temel ifadeler ve yapılar kullanılır:

| İşlem Türü | Kullanılan Anahtar Kelimeler (Türkçe / İngilizce) | Açıklama |
| :--- | :--- | :--- |
| **Başlangıç / Bitiş** | `BAŞLA ... BİTİR` / `BEGIN ... END` | Algoritmanın sınırlarını belirler. |
| **Girdi Alma** | `OKU`, `GİR` / `READ`, `INPUT` | Kullanıcıdan veya dış kaynaktan veri okur. |
| **Çıktı Verme** | `YAZ`, `GÖSTER` / `WRITE`, `PRINT` | Ekrana bilgi veya sonuç yazdırır. |
| **Atama / Hesaplama** | `ATANIR`, `=` / `SET`, `=` | Bir değişkene değer verir veya hesaplama yapar. |
| **Koşul (Karar)** | `EĞER ... İSE ... DEĞİLSE` / `IF ... THEN ... ELSE` | Şarta bağlı dallanma oluşturur. |
| **Döngü (Dönüş)** | `OLDUĞU SÜRECE ... YAP` / `WHILE ... DO` <br> `... İÇİN ... YAP` / `FOR ... DO` | Tekrarlayan işlemleri ifade eder. |

---

## 4. Algoritma İfade Yöntemlerinin Karşılaştırılması

Bir problemin çözümünü ifade etmenin 4 temel yolu vardır:

```text
[ Düz Metin / Doğal Dil ] ──► [ Akış Şeması (Flowchart) ] ──► [ Sözde Kod (Pseudocode) ] ──► [ C# Kodu ]
```


---

## 5. Örnek Senaryolar ve Sözde Kod Karşılıkları

### Senaryo 1: Koşullu Yapı (Vize-Final Not Ortalaması)

**Problem:** Vize (%40) ve Final (%60) notu girilen bir öğrencinin ortalamasını hesaplayıp, ortalama 50 veya üzerindeyse "Geçti", değilse "Kaldı" mesajı veren sistem.

#### Sözde Kod:

```text
BAŞLA
    OKU vizeNotu
    OKU finalNotu

    ortalama = (vizeNotu * 0.40) + (finalNotu * 0.60)

    EĞER ortalama >= 50 İSE
        YAZ "Tebrikler, Geçtiniz! Ortalamanız: ", ortalama
    DEĞİLSE
        YAZ "Maalesef Kaldınız! Ortalamanız: ", ortalama
    EĞER BİTTİ
BİTİR
```

#### C# Kodu Karşılığı:

```csharp
Console.Write("Vize notu: ");
double vizeNotu = Convert.ToDouble(Console.ReadLine());

Console.Write("Final notu: ");
double finalNotu = Convert.ToDouble(Console.ReadLine());

double ortalama = (vizeNotu * 0.40) + (finalNotu * 0.60);

if (ortalama >= 50)
{
    Console.WriteLine($"Tebrikler, Geçtiniz! Ortalamanız: {ortalama}");
}
else
{
    Console.WriteLine($"Maalesef Kaldınız! Ortalamanız: {ortalama}");
}
```

---

### Senaryo 2: Döngü Yapısı (1'den N'e Kadar Olan Sayıların Toplamı)

**Problem:** Kullanıcının girdiği bir $N$ sayısına kadar olan pozitif tam sayıların toplamını hesaplayan algoritma.

#### Sözde Kod:

```text
BAŞLA
    OKU N
    toplam = 0
    sayac = 1

    SAYAC <= N OLDUĞU SÜRECE YAP
        toplam = toplam + sayac
        sayac = sayac + 1
    DÖNGÜ BİTTİ

    YAZ "1'den ", N, "'e kadar sayıların toplamı: ", toplam
BİTİR
```

#### C# Kodu Karşılığı:

```csharp
Console.Write("N sayısını giriniz: ");
int N = Convert.ToInt32(Console.ReadLine());

int toplam = 0;
int sayac = 1;

while (sayac <= N)
{
    toplam += sayac;
    sayac++;
}

Console.WriteLine($"1'den {N}'e kadar sayıların toplamı: {toplam}");
```

---

### Senaryo 3: Dizi Üzerinde En Büyük Elemanı Bulma

**Problem:** 5 elemanlı bir sayı dizisi içindeki en büyük sayıyı bulan algoritma.

#### Sözde Kod:

```text
BAŞLA
    sayilar = [12, 45, 7, 89, 23]
    enBuyuk = sayilar[0]

    i = 1 'den 4 'e KADAR YAP
        EĞER sayilar[i] > enBuyuk İSE
            enBuyuk = sayilar[i]
        EĞER BİTTİ
    DÖNGÜ BİTTİ

    YAZ "Dizideki en büyük sayı: ", enBuyuk
BİTİR
```

#### C# Kodu Karşılığı:

```csharp
int[] sayilar = { 12, 45, 7, 89, 23 };
int enBuyuk = sayilar[0];

for (int i = 1; i < sayilar.Length; i++)
{
    if (sayilar[i] > enBuyuk)
    {
        enBuyuk = sayilar[i];
    }
}

Console.WriteLine($"Dizideki en büyük sayı: {enBuyuk}");
```

---

## 6. Sözde Kod Yazarken Dikkat Edilmesi Gereken Öneriler

1. **Girintileme (Indentation) Kullanın:** `EĞER` bloklarının veya `DÖNGÜ`lerin içindeki adımları sağa girintili yazmak okunabilirliği artırır.
2. **Kısa ve Net Olun:** Bir satıra birden fazla iş sığdırmak yerine adımları tane tane yazın.
3. **Büyük/Küçük Harf Standardı:** Anahtar kelimeleri (`BAŞLA`, `EĞER`, `OKU`) büyük harfle, değişken isimlerini ise küçük harfle yazmak okunabilirliği artırır.
4. **Dile Bağlanmayın:** Sözde kod yazarken `Convert.ToInt32()` veya `Console.WriteLine()` gibi dile özel metot isimleri yazmaktan kaçının; bunun yerine `OKU` ve `YAZ` kullanın.
