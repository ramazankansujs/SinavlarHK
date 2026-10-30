
## Döngü Nedir ve Neden Kullanılır?

Döngüler, belirli bir koşul sağlandığı sürece veya bir veri grubunun içindeki elemanlar bitene kadar, içine yazılan kod bloklarını **tekrar tekrar çalıştırmamızı** sağlayan programlama yapılarıdır. 

---

## 1. `for` Döngüsü

Döngünün kaç kez tekrar edeceği **önceden tam olarak biliniyorsa** kullanılır.

**Yazılışı (Syntax):**
```csharp
for (başlangıç_değeri; çalışma_koşulu; artırım_veya_azaltım)
{
    // Tekrar edilecek kodlar
}
```

**Örnek:** 1'den 5'e kadar olan sayıları ekrana yazdırma.
```csharp
for (int i = 1; i <= 5; i++)
{
    Console.WriteLine($"Sayı: {i}");
}
// Çıktı: 1, 2, 3, 4, 5
```
* **Başlangıç:** `int i = 1` (Döngü 1'den başlar)
* **Koşul:** `i <= 5` (i ismini verdiğimiz değişken, 5'e eşit veya küçük olduğu sürece çalışır)
* **Artırım:** `i++` (Her dönüşte i'nin değerini 1 artırır)
* **Bitiş** i her bir döngüde 1'er 1'er artıp 5'i geçtiği anda döngü biter. Çünkü i değikeni 5'e eşit ve 5'den küçük olduğu sürece çalışmasını istedik.

---

## 2. `while` Döngüsü

Döngünün kaç kez döneceği belli değilse ve tamamen dışarıdan gelen bir şarta (örneğin kullanıcının bir eylemine veya bir dosyanın sonuna gelmeye) bağlıysa kullanılır. Döngüye girmeden önce koşul kontrol edilir; koşul `true` ise döngü çalışır.

**Sözdizimi (Syntax):**
```csharp
while (koşul)
{
    // Koşul doğru (true) olduğu sürece çalışacak kodlar
}
```

**Örnek:** Kullanıcı şifreyi doğru girene kadar tekrar tekrar sorma.
```csharp
string sifre = Console.readLine();;

while (sifre != "1234")
{
    Console.Write("Lütfen şifrenizi girin: ");
    sifre = Console.ReadLine();
}
Console.WriteLine("Giriş başarılı!");
```


* **Kontrol** `sifre !="1234"` demek, sifre isminde belirttiğimiz değişken klavyeden 1234 girilmediği sürece tekrar tekrar bize denetmeye devam edicek.
---

## 3. `do-while` Döngüsü

`while` döngüsüne çok benzer. Aralarındaki **tek ve en önemli fark**, `do-while` döngüsünde koşulun döngü bloğu bir kez çalıştıktan *sonra* kontrol edilmesidir. Bu durum, koşul baştan yanlış (`false`) olsa bile içerideki kodların **kesinlikle en az 1 kez çalışmasını** garanti eder.

**Örnek:**
```csharp
int sayi = 10;

do
{
    Console.WriteLine("Bu yazı koşul sağlanmasa bile en az 1 kez yazdırılır.");
    sayi++;

} while (sayi < 5); // 11 < 5 koşulu false olmasına rağmen döngü bir kere çalıştı.
```

---

## 4. `foreach` Döngüsü

Diziler ve koleksiyonlar  üzerinde işlem yapmak için özel olarak tasarlanmıştır. Koleksiyon içindeki elemanları ilk sıradan başlayıp son sıraya kadar tek tek getirir.


**Örnek:** Bir isim listesini ekrana yazdırma.
```csharp
string[] ogrenciler = { "Ahmet", "Ayşe", "Mehmet", "Fatma" };

foreach (string ogrenci in ogrenciler)
{
    Console.WriteLine($"Öğrenci Adı: {ogrenci}");
}
```

* ** `string[]` demek  string değişkenimizin bir dizin olduğunu belirtir.
* ** Dizinler sürekli yeni değişken belirtip değişkene isim vermek yerine tek seferde 1 den fazla değişken ile işlem yapabilmemizi sağlar. Örneğin `String[] ogrenciler = new String[3] {"Ramazan", "Ali Can", "Zehra"};` şeklinde kullandığımız zaman 3 ayrı değişken eklemek yerine tek satırda bellekte 3 ayrı değişken ayırırız. Ancak 1'inci değişkene ulaşabilmek için `Console.WriteLine(ogrenciler[0]);` yazmak gerekir. Çünkü programlama 1'inci değeri aslında 0'ıncı değer olarak sayıp 0'dan başlar.
---

## Döngü Kontrol İfadeleri (`break` ve `continue`)

Bazen bir döngünün normal akışına müdahale etmemiz gerekir.

### Döngüyü Kırma `break` 
Döngünün koşulunun bitmesini beklemeden, döngüyü **anında sonlandırıp** döngü bloğunun dışına çıkılmasını sağlar.

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i == 5)
    {
        break; // Döngü 5'e geldiğinde tamamen durur.
    }
    Console.WriteLine(i); 
}
// Çıktı: 1, 2, 3, 4
```

### `continue` Anahtar Kelimesi
Döngünün o anki adımını pas geçerek, döngü bloğunun sonuna atlar ve **bir sonraki adımdan devam eder**. 

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3)
    {
        continue; // 3'e geldiğinde bu adımı atlar, alttaki koda geçmeden 4'ten devam eder.
    }
    Console.WriteLine(i);
}
// Çıktı: 1, 2, 4, 5 (3 yazdırılmadı çünkü 3'e eşitse continue diyerek o bölümü atladık.)
```

---

## Hangi Döngüyü Ne Zaman Kullanmalıyım? (Özet)

| Senaryo | En Uygun Döngü |
| :--- | :--- |
| **Kaç kere döneceğini tam olarak biliyorsanız** (Örn: 1'den 100'e saymak) | `for` |
| **Bir dizinin veya listenin tüm elemanlarını okuyacaksanız** | `foreach` |
| **Bitiş zamanı belli değilse ve bir koşula bağlıysa**  | `while` |
| **Koşula bağlıysa ama kodun ne olursa olsun en az 1 kez çalışması şartsa** | `do-while` |
