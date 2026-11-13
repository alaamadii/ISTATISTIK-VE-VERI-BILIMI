# CHEAT SHEET 05 — EN YAKIN K-KOMŞU ALGORİTMASI (KNN)

**Kaynak:** EN YAKIN KOMŞU ALGORİTMASI(2).pdf — 29 sayfa

## 1. Bellek Tabanlı Sınıflandırma

**KNN (K-Nearest Neighbors):** Sınıfları bilinen eğitim gözlemlerinden yararlanarak yeni bir gözlemin sınıfını belirleyen, denetimli ve bellek tabanlı sınıflandırma yöntemidir. Yeni gözlem ile eğitim gözlemleri arasındaki uzaklıklar hesaplanır; en yakın k komşunun sınıfları kullanılır.

## 2. Algoritmanın Aşamaları

1. **K'nın belirlenmesi:** Kaç komşu kullanılacağını seç.
2. **Uzaklıkların hesaplanması:** Yeni gözlem ile bütün eğitim gözlemleri arasındaki uzaklığı hesapla.
3. **Sıralama:** Uzaklıkları küçükten büyüğe sırala.
4. **Komşu seçimi:** En küçük k uzaklığa sahip gözlemi seç.
5. **Sınıf belirleme:** Seçilen komşuların sınıflarını say.
6. **Tahmin:** En çok tekrar eden sınıfı seç.

## 3. Öklid Uzaklığı

Genel formül:

$$D(i,j)=\sqrt{\sum_{r=1}^{p}(x_{ir}-x_{jr})^2}$$

İki boyutlu formül:

$$d=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2}$$

Üç boyutlu formül:

$$d=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2+(z_1-z_2)^2}$$

**Örnek:** A=(2,4), B=(8,4):

$$d=\sqrt{(2-8)^2+(4-4)^2}=6$$

**Kural:** Küçük uzaklık, daha yakın gözlem demektir.

## 4. Uygulama 1 — İki Değişkenli KNN

**Yeni gözlem:** (8,4); **k=4**.

| X1 | X2 | Y | Uzaklık | Sıra |
|---:|---:|---|---:|---:|
| 2 | 4 | KÖTÜ | 6.00 | 9 |
| 3 | 6 | İYİ | 5.39 | 8 |
| 3 | 4 | İYİ | 5.00 | 5–6 |
| 4 | 10 | KÖTÜ | 7.21 | 10 |
| 5 | 8 | KÖTÜ | 5.00 | 5–6 |
| 6 | 3 | İYİ | **2.24** | **1** |
| 7 | 9 | İYİ | 5.10 | 7 |
| 9 | 7 | KÖTÜ | **3.16** | **3** |
| 11 | 7 | KÖTÜ | **4.24** | **4** |
| 10 | 2 | KÖTÜ | **2.83** | **2** |

**Seçilen dört komşu:** (6,3) İYİ; (10,2) KÖTÜ; (9,7) KÖTÜ; (11,7) KÖTÜ.

- İYİ = 1
- KÖTÜ = 3

**Sonuç: Y(8,4) = KÖTÜ.**

## 5. KNN'de Normalleştirme

Niteliklerin ölçekleri farklı olduğunda uzaklıklar yanıltıcı olabilir. Dersin ikinci uygulamasında **Min-Max Normalleştirme** kullanılır:

$$X^*=\frac{X-X_{\min}}{X_{\max}-X_{\min}}$$

- Her nitelik ayrı ayrı normalleştirilir.
- Yeni gözlem de eğitim kümesinden elde edilen **aynı minimum ve maksimum** değerlerle dönüştürülür.
- Daha sonra Öklid uzaklıkları hesaplanır.

## 6. Uygulama 2 — Normalleştirilmiş KNN

**Yeni gözlem:** (7,8,5); **k=3**.

### Orijinal eğitim kümesi

| X1 | X2 | X3 | Y |
|---:|---:|---:|---|
| 10 | 5 | 19 | EVET |
| 8 | 2 | 4 | HAYIR |
| 18 | 16 | 6 | HAYIR |
| 12 | 15 | 8 | EVET |
| 3 | 15 | 15 | EVET |

| | X1 | X2 | X3 |
|---|---:|---:|---:|
| Minimum | 3 | 2 | 4 |
| Maksimum | 18 | 16 | 19 |

İlk satırın dönüşümü:

$$X_1^*=\frac{10-3}{18-3}=0.47$$
$$X_2^*=\frac{5-2}{16-2}=0.21$$
$$X_3^*=\frac{19-4}{19-4}=1$$

### Normalleştirilmiş eğitim kümesi

| X1* | X2* | X3* | Y |
|---:|---:|---:|---|
| 0.47 | 0.21 | 1.00 | EVET |
| 0.33 | 0.00 | 0.00 | HAYIR |
| 1.00 | 1.00 | 0.13 | HAYIR |
| 0.60 | 0.93 | 0.27 | EVET |
| 0.00 | 0.93 | 0.73 | EVET |

Yeni gözlem aynı kuralla dönüştürülür: **(7,8,5) → (0.26,0.43,0.07)**.

| Gözlem | Uzaklık | Sıra | Sınıf |
|---:|---:|---:|---|
| 1 | 0.98 | 5 | EVET |
| 2 | **0.44** | **1** | HAYIR |
| 3 | 0.93 | 4 | HAYIR |
| 4 | **0.63** | **2** | EVET |
| 5 | **0.87** | **3** | EVET |

En yakın üç komşu: HAYIR=1, EVET=2.

**Sonuç: Y(7,8,5) = EVET.**

## 7. Ağırlıklı Oylama (Weighted Voting)

Normal oylamada bütün seçilmiş komşuların oyları eşittir. Ağırlıklı oylamada yakın komşular daha fazla etkilidir.

**Ders formülü:**

$$w_i=\frac{1}{d_i^2}$$

Sınıf toplamı:

$$W(C)=\sum_{i:Y_i=C}\frac1{d_i^2}$$

**En büyük toplam ağırlığa sahip sınıf seçilir.**

| Normal Oylama | Ağırlıklı Oylama |
|---|---|
| Komşu sayısı önemlidir. | Uzaklıklar da önemlidir. |
| Her komşunun oyu eşittir. | Yakın komşunun oyu daha güçlüdür. |
| En çok tekrar eden sınıf seçilir. | En büyük ağırlık toplamı seçilir. |

## 8. Uygulama 3 — Normal ve Ağırlıklı Oylama

**Yeni gözlem:** (0.10,0.50); **k=3**.

### Eğitim kümesi

| X1 | X2 | CINS |
|---:|---:|---|
| 0.08 | 0.20 | ERKEK |
| 0.07 | 0.07 | ERKEK |
| 0.20 | 0.09 | ERKEK |
| 1.00 | 0.20 | KADIN |
| 0.05 | 0.06 | ERKEK |
| 0.20 | 0.25 | ERKEK |
| 0.17 | 0.07 | ERKEK |
| 0.15 | 0.55 | KADIN |
| 0.50 | 0.08 | ERKEK |
| 0.10 | 0.06 | KADIN |

### En yakın üç komşu

| Nokta | Uzaklık | Sınıf | Dersin Ağırlığı |
|---|---:|---|---:|
| (0.15,0.55) | 0.07 | KADIN | 200.000 |
| (0.20,0.25) | 0.27 | ERKEK | 13.793 |
| (0.08,0.20) | 0.30 | ERKEK | 11.046 |

**Normal oylama:** ERKEK=2, KADIN=1 → **ERKEK**.

**Ağırlıklı oylama:**

$$W(ERKEK)=11.046+13.793=24.839$$
$$W(KADIN)=200$$

**Sonuç: Ağırlıklı KNN = KADIN.**

**Önemli:** Aynı veri üzerinde normal oylama ve ağırlıklı oylama farklı sonuçlar verebilir. Ağırlıklı oylama bütün gözlemlere uygulanabilir, ancak büyük veri kümelerinde işlem süresi artabilir.

## 9. K Parametresinin Önemi — Ek Açıklama

- Küçük k: Yerel kararlara duyarlıdır; gürültüden daha çok etkilenebilir.
- Büyük k: Daha fazla komşuyu dikkate alır; yerel ayrıntıları kaybedebilir.
- İkili sınıflandırmada tek sayılı k, oy eşitliği ihtimalini azaltabilir.
- Uygun k, doğrulama verileriyle seçilebilir.

*Bu yorumlar ders örneklerini destekleyen genel açıklamalardır.*

## 10. Avantajlar ve Dezavantajlar — Ek Açıklama

| Avantajlar | Dezavantajlar |
|---|---|
| Basit ve anlaşılırdır. | Büyük veri kümelerinde tahmin yavaş olabilir. |
| Karmaşık eğitim aşaması gerektirmez. | Çok sayıda uzaklık hesabı gerektirir. |
| Yeni gözlemlere kolay uygulanır. | Ölçek farklılıklarından etkilenir. |
| Farklı sınıf yapılarına uygulanabilir. | Gürültü ve ilgisiz niteliklerden etkilenebilir. |

## 11. Sınav İçin Formül Özeti

| Konu | Formül |
|---|---|
| Öklid Uzaklığı | $\sqrt{\sum_{r=1}^{p}(x_{ir}-x_{jr})^2}$ |
| İki Boyutlu Uzaklık | $\sqrt{(x_1-x_2)^2+(y_1-y_2)^2}$ |
| Min-Max | $\frac{X-X_{\min}}{X_{\max}-X_{\min}}$ |
| Ağırlıklı Oylama | $w_i=\frac1{d_i^2}$ |
| Sınıf Ağırlığı | $W(C)=\sum_{i:Y_i=C}w_i$ |

## 12. Sınavda Dikkat Edilecek Noktalar

- **KNN:** Yeni gözlemin sınıfını belirler.
- **k:** Seçilen en yakın komşu sayısıdır.
- **Uzaklık:** Küçükse gözlem daha yakındır.
- **Normal oylama:** En sık görülen sınıf kazanır.
- **Ağırlıklı oylama:** En büyük ağırlık toplamı kazanır.
- **Normalleştirme:** Her nitelik ayrı dönüştürülür; yeni gözlem aynı ölçeği kullanır.
- **Uygulama 1:** (8,4), k=4 → KÖTÜ.
- **Uygulama 2:** (7,8,5), k=3 → EVET.
- **Uygulama 3:** Normal → ERKEK; ağırlıklı → KADIN.

**Kaynak notu:** İlk sekiz bölümün verileri, hesaplama örnekleri ve sonuçları 29 sayfalık ders PDF'inden alınmıştır. Dokuzuncu ve onuncu bölümlerdeki genel yorumlar açıkça ek açıklama olarak işaretlenmiştir. Uygulama 1 ve 2'deki slayt metinlerinde komşu sayısı ile sınıf sayıları arasında yazım tutarsızlıkları bulunmaktadır; tablolar ve nihai sonuçlar esas alınmıştır.
