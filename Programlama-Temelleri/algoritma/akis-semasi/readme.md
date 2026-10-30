
## Akış Şeması Oluşturma

Çözmek istediğimiz bir problemin adımlarını yazıyla belirledikten sonra, bu adımları şekiller kullanarak çizmeye **akış şeması** denir. Kod yazmaya başlamadan önce programın haritasını çıkarmak gibidir.

Bu harita sayesinde, programın baştan sona nasıl çalışacağını ve nerede karar vereceğini tek bir bakışta kolayca görebiliriz.

### 1. Çizim Yaparken Dikkat Edilmesi Gereken Kurallar

Bir akış şeması çizerken herkesin aynı şeyi anlaması için şu basit kurallara uyarız:

<img width="670" height="715" alt="image" src="https://github.com/user-attachments/assets/75e0db20-8bd9-4067-b9a0-a8cdce00a479" />


### 2. Bir Örnek: Ehliyet Yaşı Kontrolü

Kullanıcının yaşını soran ve 18'den büyük/eşitse "Ehliyet Alabilir", küçükse "Alamaz" diyen bir akış şeması tasarlayalım.

**Adım Adım Çizim Mantığı:**

* **Adım 1:** [Elips] BAŞLA
* **Adım 2:** [Paralelkenar] Kullanıcıdan `Yas` bilgisini al.
* **Adım 3:** [Eşkenar Dörtgen] Soru sor: `Yas` değeri 18'den büyük veya eşit mi? ($Yas \geq 18$)
  * **Cevap Evet ise:** Ekrana "Ehliyet Alabilir" yazdır ve bitişe git.
  * **Cevap Hayır ise:** Ekrana "Ehliyet Alamaz" yazdır ve bitişe git.
* **Adım 4:** [Elips] BİTİR

---

### 3. Kod Olarak Nasıl Görünür? (Sözde Kod)

Akış şemasını çizdiğimiz bu basit mantığın koda dökülmüş hali de şu şekildedir:

```text
BAŞLA
  YAZ "Lütfen yaşınızı girin:"
  OKU Yas

  EĞER Yas >= 18 İSE
    YAZ "Ehliyet Alabilir"
  DEĞİLSE
    YAZ "Ehliyet Alamaz"
  BİTİR_EĞER
BİTİR
```

### 4. Neden Akış Şeması Çizeriz?

* **Hataları Erken Görmek İçin:** Yanlış düşündüğümüz bir yeri, kod yazmadan çok önce çizim üzerinde fark ederiz.
* **Herkes Anlasın Diye:** Kodu sadece yazılımcılar anlar ama çizimi herkes anlar.
* **Resmin Tamamını Görmek İçin:** Programın nasıl çalıştığını kolayca kavramamızı sağlar.
