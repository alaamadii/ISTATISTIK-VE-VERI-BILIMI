# CHEAT SHEET 02 — VERİ MADENCİLİĞİNE GİRİŞ

**Kaynak:** Bölüm 3(3).pptx — Bölüm 2, 63 slayt

## 1. Veriyi Bilgiye Dönüştürmenin Yolu
- Bilişim teknolojileri sayesinde kurumlar büyük miktarda veriyi sayısal ortamda saklar.
- Veriyi saklamak yeterli değildir; değerli bilgiye dönüştürmek gerekir.
- Veri miktarı arttıkça klasik çözümleme yöntemleri zorlaşır.
- **Veri ambarı:** Verilerin yönetilmesi ve bütünleşik biçimde saklanması.
- **Veri madenciliği:** Verilerden yararlı bilgi ve ilişkilerin ortaya çıkarılması.

## 2. Veri Madenciliği
Büyük ölçekli verilerden değerli, gizli bilgi ve örüntülerin elde edilmesidir. Veriler arasındaki ilişkileri ortaya koyar, ileriye yönelik kestirimlerde bulunabilir ve karar destek sistemlerine katkı sağlar.

**Klasik istatistik:** Genellikle düzenlenmiş ve özet verilerle çalışır. **Veri madenciliği:** Milyonlarca/milyarlarca veri ve çok sayıda değişkeni inceleyebilir.

## 3. Uygulama Alanları
| Alan | Örnekler |
|---|---|
| Pazarlama | Satın alma alışkanlıkları, demografik ilişkiler, pazar sepet analizi, müşteri ilişkileri yönetimi, müşteri değerlendirme, satış tahmini |
| Bankacılık | Finansal ilişkiler, kredi kartı dolandırıcılığı, harcamalara göre gruplama, kredi taleplerinin değerlendirilmesi |
| Sigortacılık | Yeni poliçe talebi tahmini, sigorta dolandırıcılığı, riskli müşteri grupları |
| Elektronik Ticaret | Saldırı analizi, e-CRM, web ziyaretlerinin analizi |

## 4. Veri Madenciliği Süreci
1. **Veri Temizleme:** Eksik, hatalı, tutarsız verileri düzeltme. Tutarsız/hatalı veriler *gürültü (noise)* sayılır.
2. **Veri Bütünleştirme:** Farklı kaynaklardan verileri birlikte değerlendirmek üzere birleştirme.
3. **Veri İndirgeme:** Sonucu önemli ölçüde değiştirmeden veri veya değişken sayısını azaltma.
4. **Veri Dönüştürme:** Farklı ölçekli değişkenleri normalleştirme veya standartlaştırma.
5. **Veri Madenciliği Algoritmasını Uygulama:** Hazırlanan veriye uygun algoritmayı uygulama.
6. **Sonuçları Sunum ve Değerlendirme:** Sonuçları rapor ve grafiklerle sunma; hiyerarşik kümeleme için dendrogram kullanma.

### Eksik Veriyle Baş Etme — Beş Yöntem
A. Eksik değer içeren kayıtları silme.
B. Genel bir sabit kullanma (ör. `bilinmiyor`); tüm değişkenlerde aynı sabit sorun yaratabilir.
C. Değişkenin genel ortalamasını kullanma.
D. Aynı sınıftaki örneklerin ortalamasını kullanma.
E. Regresyon veya karar ağacıyla eksik değeri tahmin etme.

## 5. Min-Max Normalleştirilmesi
Verileri **0–1** aralığına dönüştürür.

$$X'=\frac{X-X_{\min}}{X_{\max}-X_{\min}}$$

- $X$: gözlem; $X_{\min}$: minimum; $X_{\max}$: maksimum; $X'$: yeni değer.
- Minimum → 0; maksimum → 1.
- Maksimum ve minimum eşitse formülün paydası sıfırdır.

**Ders örneği:** $X=\{30,36,45,50,62\}$; minimum 30, maksimum 62.

| X | X' |
|---:|---:|
| 30 | 0.0000 |
| 36 | 0.1875 |
| 45 | 0.4688 |
| 50 | 0.6250 |
| 62 | 1.0000 |

$X'(45)=(45-30)/(62-30)=15/32=0.46875$.

## 6. Z-Score Standartlaştırması
Verileri **ortalama** ve **standart sapma** üzerinden dönüştürür.

$$Z=\frac{X-\bar X}{s},\qquad \bar X=\frac{\sum_{i=1}^n X_i}{n}$$

Örneklem standart sapması: $s=\sqrt{\sum(X_i-\bar X)^2/(n-1)}$; anakütle standart sapması için payda $n$ olur. Soruda verilen standart sapmayı kullanın.

**Uygulama:** Ortalama 40, standart sapma 8, $X=28$ ise $Z=(28-40)/8=-1.5$.

- $Z=0$: ortalamaya eşit.
- $Z>0$: ortalamanın üzerinde.
- $Z<0$: ortalamanın altında.
- $Z=-1.5$: ortalamanın 1.5 standart sapma altında.

**Min-Max / Z-Score:** Min-Max minimum ve maksimuma dayanır ve [0,1] üretir; Z-Score ortalama ve standart sapmaya dayanır, negatif veya pozitif olabilir.

## 7. Veri Madenciliği Yöntemleri
**A) Sınıflandırma — B) Kümeleme — C) Birliktelik Kuralları**

### Sınıflandırma
Eğitim verisinden sınıflandırma kuralları öğrenilir; yeni örnekler bu kurallarla değerlendirilir.

**Bankanın kredi riski örneği:**

| Müşteri | BORÇ | GELİR | STATÜ | RİSK |
|---:|---|---|---|---|
| 1 | Yüksek | Yüksek | İşveren | Kötü |
| 2 | Yüksek | Yüksek | Ücretli | Kötü |
| 3 | Yüksek | Düşük | Ücretli | Kötü |
| 4 | Düşük | Düşük | Ücretli | İyi |
| 5 | Düşük | Düşük | İşveren | Kötü |
| 6 | Düşük | Yüksek | İşveren | İyi |
| 7 | Düşük | Yüksek | Ücretli | İyi |

**Karar ağacından kurallar:**
1. BORÇ=Yüksek → RİSK=Kötü.
2. BORÇ=Düşük VE GELİR=Yüksek → RİSK=İyi.
3. BORÇ=Düşük VE GELİR=Düşük VE STATÜ=İşveren → RİSK=Kötü.
4. BORÇ=Düşük VE GELİR=Düşük VE STATÜ=Ücretli → RİSK=İyi.

### Kümeleme
Verileri benzerliklerine göre gruplandırır. Pazarlama, desen tanımlama, resim işleme ve uzaysal harita analizinde kullanılır.

| Gözlem | X1 | X2 |
|---:|---:|---:|
| 1 | 1 | 1 |
| 2 | 2 | 1 |
| 3 | 4 | 5 |
| 4 | 7 | 7 |
| 5 | 5 | 7 |

**Dersin hiyerarşik kümeleme örneği:** Küme 1=(1,2); Küme 2=(4,5); Küme 3=(3,4,5); Küme 4=(1,2,3,4,5). Kümeleme grafiğine **dendrogram** denir. Buradaki hiyerarşik en yakın komşu yaklaşımı sınıflandırmadaki k-NN ile karıştırılmamalıdır.

### Birliktelik Kuralları
Birlikte gerçekleşen olayları ve birlikte satın alınan ürünleri bulur. Pazar sepet analizi, müşteri alışkanlıkları ve raf düzenlemede kullanılır.

**Dersin sepet verileri:**

| Müşteri | Ürünler |
|---:|---|
| 1 | Makarna, yağ, meyve suyu, peynir |
| 2 | Makarna, ketçap |
| 3 | Ketçap, yağ, meyve suyu, bira |
| 4 | Makarna, ketçap, yağ, meyve suyu |
| 5 | Makarna, ketçap, yağ, bira |

**Support (Destek):**
$$Support(X\to Y)=\frac{n(X\cap Y)}{N}$$

**Confidence (Güven):**
$$Confidence(X\to Y)=\frac{n(X\cap Y)}{n(X)}$$

**Apriori sonuçları (slayt 63):**

| Kural | s | c |
|---|---:|---:|
| {Ketçap, Meyve suyu} → {Yağ} | 0.4 | 1.0 |
| {Ketçap, Yağ} → {Meyve suyu} | 0.4 | 0.67 |
| {Yağ, Meyve suyu} → {Ketçap} | 0.4 | 0.67 |
| {Meyve suyu} → {Ketçap, Yağ} | 0.4 | 0.67 |
| {Yağ} → {Ketçap, Meyve suyu} | 0.4 | 0.5 |
| {Ketçap} → {Yağ, Meyve suyu} | 0.4 | 0.5 |

**Örnek:** {Ketçap, Meyve suyu} → {Yağ}: birlikte görülme sayısı 2; toplam 5 işlem; öncülün görülme sayısı 2. Support=2/5=0.4, Confidence=2/2=1.0.

## 8. Sınav İçin Hızlı Karşılaştırma
| İpucu | Kavram |
|---|---|
| Eksik/hatalı/tutarsız veri | Veri Temizleme |
| Farklı kaynakları birleştirme | Veri Bütünleştirme |
| Veri/değişken sayısını azaltma | Veri İndirgeme |
| Veriyi ölçekleme | Veri Dönüştürme |
| 0–1 aralığı | Min-Max |
| Ortalama ve standart sapma | Z-Score |
| Bilinen sınıf etiketleri | Sınıflandırma |
| Benzer örnekleri gruplama | Kümeleme |
| Hiyerarşik kümeleme grafiği | Dendrogram |
| Birlikte alınan ürünler | Birliktelik Kuralları |
| Birliktelik keşif algoritması | Apriori |
| Birlikte görülme / tüm işlemler | Support |
| Birlikte görülme / öncülün işlemleri | Confidence |

## 9. Formül Özeti
- Min-Max: $(X-X_{\min})/(X_{\max}-X_{\min})$
- Ortalama: $\sum X_i/n$
- Z-Score: $(X-\bar X)/s$
- Support: $n(X\cap Y)/N$
- Confidence: $n(X\cap Y)/n(X)$

---
**Kaynak notu:** Bu çalışma 63 slaytlık `Bölüm 3(3).pptx` sunumuna dayanmaktadır. Bazı matematiksel ifadeler dosyanın metin çıkarımında görünmediği için Min-Max ve Z-Score formülleri standart gösterimle verilmiştir. Dersin örnek tabloları ve Apriori sonuçları korunmuştur.
