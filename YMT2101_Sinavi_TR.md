# YMT2101 — İSTATİSTİK VE VERİ BİLİMİ
## Zor Karma Deneme Sınavı: Test + Klasik + Uygulama

**Fırat Üniversitesi · Yazılım Mühendisliği**  
**Kapsam:** Veri bilimine giriş, veri madenciliği, ön işleme, birliktelik kuralları, karar ağaçları (ID3/C4.5), sınıflandırıcı değerlendirme, KNN ve ağırlıklı oylama.  
**Düzey:** Zor / ayırt edici · **Önerilen süre:** 180–210 dakika · **Toplam:** 100 puan

> **Uyarı:** Bu sınav ve sondaki cevap anahtarı yapay zekâ tarafından hazırlanmıştır. **Cevap anahtarı hata içerebilir.** Özellikle sayısal sonuçları bağımsız olarak kontrol ediniz. Bu belge resmî üniversite sınavı değildir.

### Sınav kuralları
- **Bölüm A:** 40 test sorusu × 1 puan = 40 puan. Her sorunun **tek en iyi cevabı** vardır.
- **Bölüm B:** 10 klasik/uygulamalı soru × 6 puan = 60 puan. **İşlem basamakları, tablolar ve gerekçeler zorunludur.**
- İstenmedikçe sonuçları **4 ondalık basamağa** yuvarlayınız. Logaritma tabanı 2'dir.
- KNN'de uzaklık Öklid, ağırlık gerekiyorsa `w=1/d²` kabul edilir.
- **Cevap anahtarı yalnızca belgenin en sonundadır.** Klasik sorular için tam çözüm verilmez; kontrol amaçlı kısa sonuçlar bulunur.

---

# BÖLÜM A — TEST (40 × 1 PUAN)

### Temeller, veri ön işleme ve veri madenciliği

**1.** Bir şirketin geçmiş satışlarından gelecek ayın satış miktarını tahmin etmek istemesi, aşağıdakilerden hangisine en uygun örnektir?

A) Kümeleme  
B) Regresyon  
C) Birliktelik kuralı çıkarımı  
D) Anomali tespiti  
E) Sınıf etiketleme olmadan örüntü keşfi

**2.** Aşağıdaki işlemlerden hangisi *veri ön işleme* aşamasına **doğrudan** örnek değildir?

A) Yinelenen kayıtları temizlemek  
B) Farklı kaynakları birleştirmek  
C) Sayısal değerleri normalize etmek  
D) Eğitilmiş sınıflandırıcının F1 değerini raporlamak  
E) Eksik değerleri ele almak

**3.** `X={10, 20, 30, 40, 50}` için `X=35` değerinin min–max dönüşümü kaçtır?

A) 0.375  
B) 0.500  
C) 0.625  
D) 0.700  
E) 0.875

**4.** Ortalaması 40, standart sapması 8 olan bir nitelikte `X=28` için z-skoru nedir?

A) −1.50  
B) −0.67  
C) 0.67  
D) 1.50  
E) −12.00

**5.** `{2, 4, 6}` veri kümesinin **örneklem** standart sapması kaçtır?

A) √(8/3)  
B) 2  
C) 4  
D) √2  
E) 8

**6.** KNN'de yaş (18–70) ve yıllık gelir (10.000–1.000.000) birlikte kullanılıyor. En doğru yaklaşım hangisidir?

A) Yüksek sayısal değerli niteliği otomatik silmek  
B) Hedef sınıfı da normalleştirerek uzaklığa katmak  
C) Ölçek farkının uzaklığı baskılamasını önlemek için özellikleri uygun biçimde ölçeklemek  
D) `k` değerini özellik sayısına eşitlemek  
E) Sadece geliri kullanmak

**7.** Aşağıdaki yöntem–öğrenme türü eşleştirmelerinden hangisi genel olarak doğrudur?

A) KNN–denetimsiz; kümeleme–denetimli  
B) Karar ağacı sınıflandırması–denetimli; kümeleme–denetimsiz  
C) Birliktelik kuralları–zorunlu denetimli; regresyon–denetimsiz  
D) Regresyon–yalnızca denetimsiz; KNN–denetimsiz  
E) Anomali tespiti–her zaman denetimli

**8.** Hiyerarşik kümelemede *dendrogram* neyi gösterir?

A) Her kaydın gerçek sınıfını  
B) Yalnızca sınıflandırıcının hata oranını  
C) Kümelerin hangi sırayla ve hangi uzaklık düzeylerinde birleştiğini  
D) En iyi `k` komşu sayısını  
E) Normalizasyon için min–max değerlerini

**9.** Beş işlemden üçü `{A,B}` içeriyor, dördü `A` içeriyor. `A→B` kuralının support ve confidence değerleri sırasıyla nedir?

A) 0.75 ve 0.60  
B) 0.60 ve 0.75  
C) 0.60 ve 0.60  
D) 0.75 ve 0.75  
E) 0.80 ve 0.60

**10.** `{Ketçap, Meyve suyu}→{Yağ}` kuralında confidence paydası hangisidir?

A) Tüm işlemlerin sayısı  
B) Yalnız yağ içeren işlem sayısı  
C) Ketçap **ve** meyve suyu içeren işlem sayısı  
D) Üç üründen en az birini içeren işlem sayısı  
E) Üç ürünü birlikte içeren işlem sayısı

**11.** Aynı ürün kümesi için `Support(A→B)` ile `Support(B→A)` karşılaştırması nedir?

A) Birincisi daima büyüktür  
B) İkincisi daima büyüktür  
C) Eşittir; confidence değerleri farklı olabilir  
D) Yalnız confidence eşittir  
E) Her ikisi de yönle zorunlu değişir

**12.** Minimum support %40, minimum confidence %70. Bir kuralın support'u %50, confidence'ı %65 ise sonuç nedir?

A) Güçlüdür; support yeterlidir  
B) Güçlüdür; iki değerin ortalaması yeterlidir  
C) Güçlü değildir; confidence eşiğini geçememiştir  
D) Güçlü değildir; support çok yüksektir  
E) Yalnız lift biliniyorsa karar verilebilir

### Karar ağaçları — kavramlar, entropi, ID3 ve C4.5

**13.** Bir karar ağacında `Hava?` testinin yapıldığı başlangıç noktası nedir?

A) Yaprak  
B) Dal  
C) Kök düğüm  
D) Hedef nitelik  
E) Eğitim kümesi

**14.** İkili sınıflandırmada 12 örneğin 6'sı EVET, 6'sı HAYIR. Entropi kaçtır?

A) 0  
B) 0.5  
C) 1  
D) 1.5  
E) 2

**15.** 8 EVET ve 0 HAYIR içeren bir düğüm için entropi nedir?

A) 0  
B) 0.25  
C) 0.5  
D) 1  
E) Tanımsız

**16.** 8 kaydın 6'sı EVET, 2'si HAYIR. Başlangıç entropisine en yakın değer hangisidir?

A) 0.5436  
B) 0.6500  
C) 0.8113  
D) 0.9183  
E) 1.0000

**17.** Bir niteliğe göre iki dal oluşuyor: 6 kayıtlık dalın entropisi 0; 4 kayıtlık dalın entropisi 1. Ağırlıklı entropi kaçtır?

A) 0.20  
B) 0.40  
C) 0.50  
D) 0.60  
E) 1.00

**18.** Başlangıç entropisi 0.9710, bölünme sonrası ağırlıklı entropi 0.6000. Kazanç kaçtır?

A) 0.3710  
B) 0.6000  
C) 0.9710  
D) 1.5710  
E) 0.6180

**19.** ID3'te kök nitelik seçiminin temel ölçütü hangisidir?

A) En küçük bilgi kazancı  
B) En yüksek bilgi kazancı  
C) En çok dal oluşturan nitelik  
D) En küçük veri tipi boyutu  
E) En yüksek hata sayısı

**20.** Aşağıdaki adaylar için `Kazanç(A)=0.32`, `Kazanç(B)=0.27`, `Kazanç(C)=0.31`. ID3 hangi niteliği seçer?

A) A  
B) B  
C) C  
D) B ve C  
E) SplitInfo olmadan karar verilemez

**21.** Bir niteliğin bölünme büyüklükleri 4 ve 4 (toplam 8). `SplitInfo` kaçtır?

A) 0  
B) 0.5  
C) 0.75  
D) 1  
E) 2

**22.** `Gain(X)=0.24`, `SplitInfo(X)=1.50`. Gain Ratio kaçtır?

A) 0.06  
B) 0.16  
C) 0.24  
D) 0.36  
E) 1.74

**23.** `Kazanç Ölçütü` ile `Kazanç Oranı` arasındaki ilişkiyi en iyi açıklayan ifade hangisidir?

A) İki yöntem matematiksel olarak tamamen bağımsızdır  
B) Kazanç oranı, kazancı bölünme bilgisine oranlar  
C) Kazanç, kazanç oranının karesidir  
D) ID3 her zaman kazanç oranını kullanır  
E) Kazanç oranı hedef sınıfları hiç kullanmaz

**24.** Sayısal nitelikte sıralı komşu farklı değerler 80 ve 85 ise aday eşik hangisidir?

A) 80  
B) 81  
C) 82.5  
D) 85  
E) 165

**25.** Bir sayısal nitelik için en iyi eşik nasıl seçilir?

A) Her zaman medyan alınır  
B) Yalnız en büyük ve en küçük değerlerin ortalaması alınır  
C) Aday eşiklerin oluşturduğu bölünmelerin kazançları karşılaştırılır  
D) Rastgele seçilir; KNN sonradan düzeltir  
E) Sınıf etiketleri hiç incelenmez

**26.** 20 kayıttan 15'inde `X` niteliği biliniyor. Dersin kayıp değer düzeltme faktörü `F` kaçtır?

A) 0.20  
B) 0.25  
C) 0.50  
D) 0.75  
E) 1.33

**27.** `F=0.75` ve bilinen veriler üzerinden hesaplanan kazanç `0.40` ise ders formülüne göre düzeltilmiş kazanç kaçtır?

A) 0.10  
B) 0.25  
C) 0.30  
D) 0.40  
E) 0.5333

**28.** Aşağıdaki ifadelerden hangisi karar ağacından elde edilen bir *karar kuralına* uygundur?

A) `IF Hava=Bulutlu THEN Oyun=Evet`  
B) `Oyun = (Hava + Nem) / 2`  
C) `k = 3, en yakın komşu seç`  
D) `Support = n(X∩Y)/N`  
E) `Normalize(X)=log₂(X)`

### Sınıflandırıcı değerlendirme

**29.** Gerçekte pozitif olan bir örneğin negatif tahmin edilmesi hangisidir?

A) TP  
B) TN  
C) FP  
D) FN  
E) Precision

**30.** `TP=18`, `TN=72`, `FP=8`, `FN=2`. Accuracy kaçtır?

A) 0.80  
B) 0.82  
C) 0.90  
D) 0.92  
E) 0.98

**31.** `TP=30`, `FP=10`, `FN=20`. Precision kaçtır?

A) 0.50  
B) 0.60  
C) 0.67  
D) 0.75  
E) 0.80

**32.** `TP=30`, `FP=10`, `FN=20`. Recall kaçtır?

A) 0.50  
B) 0.60  
C) 0.67  
D) 0.75  
E) 0.80

**33.** Precision=0.75, Recall=0.50 ise F1 kaçtır?

A) 0.50  
B) 0.55  
C) 0.60  
D) 0.625  
E) 0.75

**34.** Dengesiz veri kümesinde 990 negatif, 10 pozitif var. Model herkesi negatif tahmin ediyor. En doğru yorum hangisidir?

A) Accuracy %99 olduğu için pozitif sınıfı çok iyi yakalar  
B) Accuracy %99 olabilir ama pozitif sınıfın Recall değeri 0'dır  
C) Precision ve Recall kesinlikle %99'dur  
D) FP=10 ve FN=0'dır  
E) TN=0'dır

### KNN ve ağırlıklı oylama

**35.** KNN için aşağıdakilerden hangisi doğrudur?

A) `k` kullanılan özellik sayısıdır  
B) Yeni gözlemin sınıfı uzaklık hesabına özellik olarak katılır  
C) `k`, oylamaya alınan komşu sayısıdır  
D) KNN yalnız iki boyutlu veriyle çalışır  
E) KNN denetimsiz bir kümeleme yöntemidir

**36.** `A=(1,2,2)` ve `B=(4,6,2)` için Öklid uzaklığı kaçtır?

A) 3  
B) 4  
C) 5  
D) √41  
E) 7

**37.** Yeni gözleme en yakın 5 komşunun sınıfları `EVET, HAYIR, EVET, HAYIR, EVET`. Normal oylama sonucu nedir?

A) HAYIR  
B) EVET  
C) Eşitlik  
D) Hesaplanamaz; normalize edilmemiştir  
E) Yalnız ağırlıklı oylamayla bulunur

**38.** `d=0.20` olan bir komşunun `w=1/d²` ağırlığı kaçtır?

A) 0.04  
B) 0.20  
C) 5  
D) 20  
E) 25

**39.** Üç komşu: `(EVET, 0.10)`, `(HAYIR, 0.40)`, `(HAYIR, 0.50)`. Normal ve ağırlıklı oylama sonuçları sırasıyla hangisidir?

A) EVET / EVET  
B) EVET / HAYIR  
C) HAYIR / EVET  
D) HAYIR / HAYIR  
E) Eşitlik / EVET

**40.** KNN'de `k` büyüdükçe hangisi genel olarak beklenebilir?

A) Gürültüye duyarlılık kesinlikle artar  
B) Yerel ayrıntılar kaybolabilir ve karar sınırı daha düzgün olabilir  
C) `k` özellik sayısına dönüşür  
D) Eğitim verisi artık gerekli değildir  
E) Tüm durumlarda doğruluk kesinlikle artar

---

# BÖLÜM B — KLASİK VE UYGULAMALI (10 × 6 PUAN)

> **Tam işlem gösteriniz.** Sadece sonuca puan verilmesi beklenmemelidir.

## K1 — İstatistik + ölçekleme (6 puan)

Bir sensörün altı ölçümü `4, 6, 8, 10, 12, 14` olarak kaydedilmiştir.

1. Aritmetik ortalamayı hesaplayınız.
2. **Örneklem varyansı** ve **örneklem standart sapmasını** bulunuz.
3. `X=12` için z-skorunu hesaplayınız.
4. Aynı değerin min–max normalizasyonunu bulunuz.
5. Z-skoru ile min–max dönüşümünün amaçlarını birer cümleyle karşılaştırınız.

## K2 — Apriori: üç ürünlü kural (6 puan)

Bir mağazanın işlem verileri:

| İşlem | Ürünler |
|---|---|
| T1 | Makarna, Ketçap, Yağ, Meyve suyu |
| T2 | Makarna, Ketçap |
| T3 | Ketçap, Yağ, Meyve suyu |
| T4 | Makarna, Ketçap, Yağ, Meyve suyu |
| T5 | Makarna, Ketçap, Yağ |
| T6 | Yağ, Meyve suyu |
| T7 | Ketçap, Meyve suyu |
| T8 | Makarna, Yağ, Meyve suyu |

`minSupport=0.25`, `minConfidence=0.70`.

1. `{Ketçap, Meyve suyu} → {Yağ}` kuralının support ve confidence değerlerini bulunuz.
2. `{Yağ} → {Ketçap, Meyve suyu}` kuralının support ve confidence değerlerini bulunuz.
3. Her iki kuralın güçlü olup olmadığını ayrı ayrı belirleyiniz.
4. Yön değişince support neden aynı, confidence neden farklı olabilir? Açıklayınız.

## K3 — Karar ağacı: sıfırdan ID3 (6 puan)

Bir eğitim kümesinde hedef `Y ∈ {E,H}`:

| No | A | B | Y |
|---:|---|---|---|
| 1 | K | U | E |
| 2 | K | U | E |
| 3 | K | V | E |
| 4 | K | V | H |
| 5 | L | U | E |
| 6 | L | U | H |
| 7 | L | V | H |
| 8 | L | V | H |

1. `H(T)` hesaplayınız.
2. `A` için her dalın entropisini, ağırlıklı entropiyi ve kazancı hesaplayınız.
3. Aynı işlemleri `B` için yapınız.
4. ID3'e göre kök niteliği seçiniz ve sayısal gerekçe veriniz.
5. Kök bölünmesinden sonra **saf olmayan** dalları belirtiniz; bir sonraki adımda ne yapılacağını açıklayınız.

## K4 — Karar ağacı: Gain Ratio ve yüksek dallanma (6 puan)

12 kayıt içeren bir veri kümesinin başlangıç entropisi `H(T)=1`'dir. İki aday nitelik için:

- **Nitelik P:** 3 dal, büyüklükler `4,4,4`; bölünme sonrası ağırlıklı entropi `0.45`.
- **Nitelik Q:** 2 dal, büyüklükler `6,6`; bölünme sonrası ağırlıklı entropi `0.55`.

1. P ve Q için `Gain` hesaplayınız.
2. P ve Q için `SplitInfo` hesaplayınız.
3. Her ikisinin `Gain Ratio` değerini hesaplayınız.
4. **Yalnız Gain** ölçütüne göre hangisi seçilir?
5. **Yalnız Gain Ratio** ölçütüne göre hangisi seçilir?
6. Sonuçlar farklıysa nedenini açıklayınız. (C4.5'in gerçek seçim uygulamasında kazanç filtresi olabileceğini de not ediniz.)

## K5 — Sayısal eşik: tüm adayları sınayın (6 puan)

Bir nitelik ve hedef sınıf:

| X | Y |
|---:|---|
| 2 | H |
| 4 | H |
| 6 | E |
| 8 | E |
| 10 | H |
| 12 | E |

1. `H(T)` hesaplayınız.
2. **Tüm farklı komşu değerlerin orta noktalarından** aday eşikleri oluşturunuz.
3. Her eşik için `X≤t` ve `X>t` alt kümelerinin sınıf dağılımlarını yazınız.
4. Her adayın ağırlıklı entropisini ve kazancını hesaplayınız.
5. En iyi eşiği seçiniz. Eşitlik varsa bütün en iyi eşikleri belirtiniz.
6. Seçilen eşik için IF–THEN biçiminde bir **kısmi** karar kuralı yazınız; saf olmayan dalı otomatik saf kabul etmeyiniz.

## K6 — Eksik değerler ve değerlendirme (6 puan)

Bir veri kümesinde 24 kaydın 18'inde `Nem` değeri biliniyor. Bilinen değerler üzerinden bulunan `Gain(Nem)=0.36`.

Ayrı bir test kümesinde gerçek/tahmin sonuçları:

| Gerçek \ Tahmin | Pozitif | Negatif |
|---|---:|---:|
| Pozitif | 24 | 6 |
| Negatif | 9 | 61 |

1. Dersin kayıp değer düzeltme faktörü `F` ve düzeltilmiş kazancı hesaplayınız.
2. TP, TN, FP, FN ve toplam örnek sayısını belirtiniz.
3. Accuracy, Error, Precision, Recall, Specificity ve F1'i hesaplayınız.
4. Pozitif vakaları kaçırmanın maliyeti yüksekse hangi ölçüte özellikle dikkat edilmesi gerektiğini gerekçelendiriniz.

## K7 — Büyük KNN: üç boyutlu min–max ve normal oylama (6 puan)

**Yeni gözlem:** `Q=(7,8,5)`; `k=3`.

| No | X1 | X2 | X3 | Y |
|---:|---:|---:|---:|---|
| 1 | 10 | 5 | 19 | EVET |
| 2 | 8 | 2 | 4 | HAYIR |
| 3 | 18 | 16 | 6 | HAYIR |
| 4 | 12 | 15 | 8 | EVET |
| 5 | 3 | 15 | 15 | EVET |

1. Her özellik için min ve max değerleri bulunuz.
2. **Beş eğitim gözleminin tamamını** min–max ile normalize ediniz.
3. Yeni gözlem Q'yu **eğitim verisinin min–max değerleriyle** normalize ediniz.
4. Normalize edilmiş Q'nun her eğitim gözlemine Öklid uzaklığını hesaplayınız.
5. Uzaklıkları sıralayıp en yakın 3 komşuyu belirleyiniz.
6. Normal oylamayla sınıfı bulunuz. `Y` sütununun neden uzaklık hesabına girmediğini açıklayınız.

## K8 — Büyük KNN: normal ve ağırlıklı oylama ters düşüyor (6 puan)

**Yeni gözlem:** `Q=(0.10, 0.50)`, `k=3`. Veriler zaten normalize edilmiştir.

| No | X1 | X2 | Y |
|---:|---:|---:|---|
| 1 | 0.15 | 0.55 | KADIN |
| 2 | 0.20 | 0.25 | ERKEK |
| 3 | 0.08 | 0.20 | ERKEK |
| 4 | 0.90 | 0.90 | KADIN |
| 5 | 0.60 | 0.10 | ERKEK |
| 6 | 0.40 | 0.80 | KADIN |

1. **Altı** gözlemin tüm Öklid uzaklıklarını hesaplayınız.
2. İlk üç komşuyu belirleyiniz.
3. Normal oylama sonucunu bulunuz.
4. Her seçili komşunun ağırlığını `w=1/d²` ile hesaplayınız (**yuvarlanmamış uzaklık karelerini kullanınız**).
5. Sınıf ağırlıklarını toplayıp ağırlıklı oylama sonucunu bulunuz.
6. Aynı `k` ve aynı verilerle sonuçların neden farklılaştığını açıklayınız.

## K9 — KNN: ölçekleme sıralamayı değiştirir mi? (6 puan)

Aşağıdaki **eğitim** verileri ve yeni gözlem veriliyor:

| No | X1 (Yaş) | X2 (Gelir) | Y |
|---:|---:|---:|---|
| A | 20 | 1000 | EVET |
| B | 40 | 1010 | HAYIR |
| C | 50 | 1002 | EVET |
| D | 30 | 1040 | HAYIR |

`Q=(35,1003)`, `k=1`.

1. Normalizasyon yapmadan Q'nun A, B, C, D'ye uzaklıklarını hesaplayınız.
2. `k=1` ile ilk tahmini bulunuz.
3. Eğitim verisinden X1 ve X2 için min–max değerlerini bulunuz.
4. Tüm gözlemleri ve Q'yu min–max ile dönüştürünüz.
5. Normalize edilmiş uzaklıkları yeniden hesaplayınız; en yakın komşu değişti mi?
6. Değişimin nedenini ve yeni gözlemin dönüşümünde neden eğitim min–max'ının kullanıldığını açıklayınız.

## K10 — Bütünleşik vaka: karar ağacı + KNN + metrik yorumu (6 puan)

Bir bankanın 200 işlemlik test kümesinde iki modelin sonuçları:

| Model | TP | FN | FP | TN |
|---|---:|---:|---:|---:|
| Karar Ağacı | 32 | 8 | 20 | 140 |
| KNN | 36 | 4 | 32 | 128 |

1. Her model için Accuracy, Precision, Recall ve F1 hesaplayınız.
2. Dolandırıcılığı kaçırmanın (FN) maliyeti çok yüksekse **hangi modelin tercih edilebileceğini**, sayılarla savununuz.
3. Yanlış alarmın (FP) operasyonel maliyeti çok yüksekse kararın neden değişebileceğini açıklayınız.
4. KNN modelinde özellik ölçekleme, `k` seçimi ve ağırlıklı oylamanın hangi açılardan etkili olabileceğini yazınız.
5. Karar ağacında ID3 ve C4.5'in nitelik seçim mantığını iki cümleyle karşılaştırınız.
6. Yalnız Accuracy değerine bakmanın bu vakada neden yetersiz olabileceğini açıklayınız.

---

# CEVAP ANAHTARI — YALNIZCA SINAV BİTTİKTEN SONRA BAKINIZ

> **ÖNEMLİ UYARI:** Aşağıdaki anahtar **yapay zekâ tarafından çözülmüştür ve hata içerebilir**. Resmî cevap anahtarı değildir. Sayısal sonuçlar bağımsız hesap makinesiyle veya ders materyaliyle kontrol edilmelidir.

## A. Test cevapları

| Soru | Cevap | Soru | Cevap | Soru | Cevap | Soru | Cevap |
|---:|:---:|---:|:---:|---:|:---:|---:|:---:|
| 1 | B | 11 | C | 21 | D | 31 | D |
| 2 | D | 12 | C | 22 | B | 32 | B |
| 3 | C | 13 | C | 23 | B | 33 | C |
| 4 | A | 14 | C | 24 | C | 34 | B |
| 5 | B | 15 | A | 25 | C | 35 | C |
| 6 | C | 16 | C | 26 | D | 36 | C |
| 7 | B | 17 | B | 27 | C | 37 | B |
| 8 | C | 18 | A | 28 | A | 38 | E |
| 9 | B | 19 | B | 29 | D | 39 | C |
| 10 | C | 20 | A | 30 | C | 40 | B |

## B. Klasik sorular — kısa kontrol anahtarı (çözüm adımları verilmemiştir)

**K1.** Ortalama `9`; örneklem varyansı `14`; örneklem standart sapması `√14 ≈ 3.7417`; `z(12)=3/√14 ≈ 0.8018`; min–max `(12−4)/(14−4)=0.8`.

**K2.** `{Ketçap,Meyve suyu,Yağ}` birlikte `T1,T3,T4` → `3/8=0.375` support. `{Ketçap,Meyve suyu}` `T1,T3,T4,T7` → confidence `3/4=0.75` (güçlü). `{Yağ}` `T1,T3,T4,T5,T6,T8` → ters yön confidence `3/6=0.50` (güçlü değil). Support aynı.

**K3.** `H(T)=1`. A dalları `(3E,1H)` ve `(1E,3H)` → ağırlıklı H `0.8113`, Gain(A) `0.1887`. B dalları `(3E,1H)` ve `(1E,3H)` → aynı: Gain(B) `0.1887`. **Kök için eşitlik vardır**; tek bir zorunlu seçim yoktur. Her iki olası kök altında saf olmayan dallar yeniden bölünmelidir. *(Eşit kazanç kasıtlıdır.)*

**K4.** `Gain(P)=0.55`, `Gain(Q)=0.45`; `SplitInfo(P)=log₂3≈1.5850`, `SplitInfo(Q)=1`; `Ratio(P)≈0.3470`, `Ratio(Q)=0.45`. Yalnız Gain → **P**; yalnız Gain Ratio → **Q**.

**K5.** `H(T)=1`. Adaylar `t=3,5,7,9,11`. Kazançlar yaklaşık `0.1909, 0.4591, 0.0817, 0, 0.1909`. En iyi `t=5`; sol dal `(0E,2H)` saf H; sağ dal `(3E,1H)` saf değildir. *Not: 9 eşiği için iki dalda da oranlar 2E/2H ve 1E/1H olduğundan kazanç 0'dır.*

**K6.** `F=18/24=0.75`, düzeltilmiş Gain `0.27`. `TP=24`, `FN=6`, `FP=9`, `TN=61`, `N=100`. Accuracy `0.85`, Error `0.15`, Precision `24/33≈0.7273`, Recall `24/30=0.8`, Specificity `61/70≈0.8714`, F1 `48/63≈0.7619`. FN önemli ise Recall.

**K7.** Min `(3,2,4)`, max `(18,16,19)`; Q' `(0.2667,0.4286,0.0667)`. Normalize eğitim satırları yaklaşık `(0.4667,0.2143,1)`, `(0.3333,0,0)`, `(1,1,0.1333)`, `(0.6,0.9286,0.2667)`, `(0,0.9286,0.7333)`. Uzaklıklar yaklaşık `0.9783, 0.4388, 0.9321, 0.6333, 0.8750`; en yakın `2,4,5`; **EVET**.

**K8.** Uzaklıklar yaklaşık `0.0707, 0.2693, 0.3007, 0.8944, 0.6403, 0.4243`. En yakın `1,2,3`. Normal oylama **ERKEK**. Ağırlıklar `200`, `1/0.0725≈13.7931`, `1/0.0904≈11.0619`; `W(KADIN)=200`, `W(ERKEK)≈24.8550`; ağırlıklı sonuç **KADIN**.

**K9.** Ham uzaklıklar: A `√234≈15.2971`, B `√74≈8.6023`, C `√226≈15.0333`, D `√1394≈37.3363` → **B/HAYIR**. Min `(20,1000)`, max `(50,1040)`; Q' `(0.5,0.075)`; A `(0,0)`, B `(2/3,0.25)`, C `(1,0.05)`, D `(1/3,1)`; normalize uzaklıklar yaklaşık `0.5056,0.2417,0.5006,0.9399` → **B/HAYIR**. *Bu veri kümesinde en yakın komşu değişmez; “mutlaka değişir” varsayımı yanlıştır.* Ölçeklemenin uzaklıkları ve göreli farkları değiştirdiği yine de gösterilmelidir.

**K10.** Karar Ağacı: Accuracy `0.86`, Precision `32/52≈0.6154`, Recall `0.80`, F1 `64/92≈0.6957`. KNN: Accuracy `0.82`, Precision `36/68≈0.5294`, Recall `0.90`, F1 `72/108≈0.6667`. FN maliyeti yüksekse **KNN lehine**; FP maliyeti yüksekse **karar ağacı lehine** gerekçe kurulabilir. Tek metrikle kesin seçim yapılamaz.

---

**Hazırlanma amacı:** YMT2101 dersine yönelik zorlayıcı, özgün çalışma sınavı. Sorular, önceki ders notlarının konu çerçevesine dayalıdır; uygulama tablolarının bir kısmı sınav alıştırması için özgün oluşturulmuştur.
