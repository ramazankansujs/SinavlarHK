

## 1. Temel Tablo Yapısı ve Etiketler

Bir HTML tablosu en basit haliyle 4 temel etiket ile oluşturulur:

| Etiket | Anlamı | Görevi / İşlevi |
| :--- | :--- | :--- |
| `<table>` | **Table** | Tablonun başladığını ve bittiğini belirten ana kapsayıcıdır. |
| `<tr>` | **Table Row** | Tabloda **yeni bir satır** oluşturur. |
| `<th>` | **Table Header** | **Başlık hücresi** oluşturur. İçindeki metin varsayılan olarak **koyu (bold)** ve **ortalanmış** görünür. |
| `<td>` | **Table Data** | **Veri hücresi** oluşturur. Normal standart verileri barındırır. |

### Basit Tablo Örneği

```html
<table>
  <!-- 1. Satır: Başlıklar -->
  <tr>
    <th>Ad</th>
    <th>Soyad</th>
    <th>Yaş</th>
  </tr>
  <!-- 2. Satır: 1. Veri Seti -->
  <tr>
    <td>Ramazan</td>
    <td>Kansu</td>
    <td>23</td>
  </tr>
  <!-- 3. Satır: 2. Veri Seti -->
  <tr>
    <td>Ali Can</td>
    <td>Elçi</td>
    <td>17</td>
  </tr>
</table>
```

---

## 2. Hücre Birleştirme Nitelikleri

Bazen birden fazla hücreyi yatayda veya dikeyde birleştirerek tek bir hücre haline getirmemiz gerekir.

### A. `colspan` (Sütun Birleştirme - Yatay)

Yan yana duran sütun hücrelerini **yatayda** birleştirmek için kullanılır. 

* `colspan="2"` ifadesi, o hücrenin 2 sütun genişliğinde kaplayacağını belirtir.

```html
<tr>
  <!-- 2 sütunluk alanı tek bir hücre kaplar -->
  <td colspan="2">Toplam Tutar:</td>
  <td>500 TL</td>
</tr>
```

### B. `rowspan` (Satır Birleştirme - Dikey)

Alt alta duran satır hücrelerini **dikeyde** birleştirmek için kullanılır.

* `rowspan="2"` ifadesi, o hücrenin 2 satır yüksekliğinde kaplayacağını belirtir.

```html
<tr>
  <!-- Dikeyde 2 satırı birleştirir -->
  <td rowspan="2">Pazartesi</td>
  <td>Matematik</td>
</tr>
<tr>
  <td>İngilizce 101</td>
</tr>
```

---

## 3. Detaylı Örnek Senaryo: Öğrenci Not Çizelgesi

Pekiştirme adına hem `colspan`, hem `rowspan`, hem de anlamsal etiketleri bir arada kullanan kapsamlı bir tablo kurgulayalım:

```html
<table>
  <caption>Öğrenci Sınav Değerlendirme Tablosu</caption>
  <thead>
    <tr>
      <th rowspan="2">Öğrenci Adı</th>
      <th colspan="2">Sınavlar</th>
      <th rowspan="2">Ortalama</th>
    </tr>
    <tr>
      <th>Vize</th>
      <th>Final</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ramazan Kansu</td>
      <td>70</td>
      <td>80</td>
      <td>76</td>
    </tr>
    <tr>
      <td>Ali Can Elçi</td>
      <td>90</td>
      <td>100</td>
      <td>96</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="3">Sınıf Ortalaması:</td>
      <td>86</td>
    </tr>
  </tfoot>
</table>
```

### Kod Açıklaması:

1. `<th rowspan="2">Öğrenci Adı</th>`: "Öğrenci Adı" başlığı altındaki 2 satırı dikeyde kaplar.
2. `<th colspan="2">Sınavlar</th>`: "Sınavlar" başlığı yanındaki Vize ve Final sütunlarını yatayda kaplar.
3. `<td colspan="3">Sınıf Ortalaması:</th>`: Alt bilgideki metin 3 sütunluk alanı kaplayarak sonucu en sağa hizalar.

---

## 4. CSS ile Tablo Şekillendirme Temelleri

Varsayılan HTML tabloları kenarlıksız ve oldukça sade görünür. Tabloyu çizgili ve şık hale getirmek için temel CSS kuralları eklenir:

```css
table {
  width: 100%;
  border-collapse: collapse; /* Çift kenarlıkları engeller, tek çizgi yapar */
}

th, td {
  border: 1px solid #ddd; /* Hücrelere gri kenarlık ekler */
  padding: 8px;           /* Hücre içi boşluk bırakır */
  text-align: left;       /* Metinleri sola hizalar */
}

th {
  background-color: #f4f4f4; /* Başlık alanına arka plan rengi verir */
}
```

---

## Özet

* Tablolar **`<table>`** ile başlar, **`<tr>`** ile satır, **`<td>`** veya **`<th>`** ile hücre oluşturulur.
* Daha düzenli yapılar için **`<thead>`**, **`<tbody>`** ve **`<tfoot>`** bölümleri kullanılır.
* **Yatayda** hücre birleştirmek için **`colspan`**, **dikeyde** hücre birleştirmek için **`rowspan`** kullanılır.
