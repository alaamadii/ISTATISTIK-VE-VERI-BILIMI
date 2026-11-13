# CHEAT SHEET 03 — KARAR AĞAÇLARI İLE SINIFLANDIRMA

**Kaynak:** KARAR AĞAÇLARI SINIFLANDIRMA(1).pptx — 83 slayt.

## 1. Sınıflandırma ve Karar Ağaçları

**Sınıflandırma:** Bir kaydın ortak özelliklerine göre hangi sınıfa ait olduğunun belirlenmesidir. Eğitim verilerinden model öğrenilir; test verileriyle model sınanır; yeni kayıtların sınıfı tahmin edilir.

**Karar ağacı:** Akış şemasına benzeyen, nitelik testleriyle dallanan sınıflandırma yapısı.

| Kavram | Açıklama |
|---|---|
| Kök Düğüm | En üstteki başlangıç düğümü |
| İç Düğüm | Nitelik testi yapılan düğüm |
| Dal | Test sonucuna karşılık gelen yol |
| Yaprak | Sınıf kararının verildiği son düğüm |
| Hedef Nitelik | Tahmin edilen sınıf |
| Eğitim Kümesi | Model oluşturmak için kullanılan kayıtlar |

Dallanma algoritması grupları: **Entropiye Dayalı Algoritmalar**, **Sınıflandırma ve Regresyon Ağaçları**, **Bellek Tabanlı Sınıflandırma Algoritmaları**. **ID3 ve C4.5**, Quinlan'ın entropi tabanlı algoritmalarıdır.

## 2. Entropi

Bir sistemdeki belirsizlik ölçüsü:

$$H(T)=-\sum_{i=1}^{k}p_i\log_2(p_i)$$

Burada $p_i$, i. sınıfın toplam kayıtlar içindeki oranıdır. İkili sınıflandırmada tüm kayıtlar aynı sınıftaysa $H=0$; iki sınıf eşit dağılıyorsa $H=1$.

**Ders örneği:** 14 kayıt, 9 Evet ve 5 Hayır:

$$H(T)=-\frac9{14}\log_2\frac9{14}-\frac5{14}\log_2\frac5{14}\approx0.9403$$

## 3. Kazanç Ölçütü (Information Gain)

Bir niteliğe göre bölünme sonrası ağırlıklı entropi:

$$H(X,T)=\sum_{i=1}^{m}\frac{|T_i|}{|T|}H(T_i)$$

Bilgi kazancı:

$$\boxed{Kazanç(X,T)=H(T)-H(X,T)}$$

**ID3:** En yüksek kazanç sağlayan nitelik seçilir.

**Hesaplama sırası:** (1) Hedef sınıfları say. (2) Başlangıç entropisini hesapla. (3) Nitelik değerlerine göre kayıtları böl. (4) Her dalın entropisini hesapla. (5) Dal büyüklükleriyle ağırlıklandır. (6) Başlangıç entropisinden çıkar. (7) Aday nitelikleri karşılaştır. (8) En yüksek kazancı seç.

## 4. Karar Ağacı Oluşturma — OYUN Örneği

**Tablo 3.2:** Hedef nitelik OYUN (9 Evet, 5 Hayır). Aday nitelikler HAVA, ISI, NEM, RÜZGAR.

| Nitelik | Kazanç |
|---|---:|
| HAVA | 0.246 |
| ISI | 0.029 |
| NEM | 0.151 |
| RÜZGAR | 0.048 |

**Kök = HAVA** (en büyük kazanç).

**HAVA=Güneşli:** 5 kayıt, 2 Evet ve 3 Hayır. $H\approx0.971$.

| Nitelik | Kazanç |
|---|---:|
| ISI | 0.570 |
| NEM | 0.970 |
| RÜZGAR | 0.019 |

**NEM seçilir:** Yüksek → Hayır; Normal → Evet.

**HAVA=Bulutlu:** 4 kayıt, hepsi Evet → Yaprak Evet; entropi 0.

**HAVA=Yağmurlu:** 5 kayıt, 3 Evet ve 2 Hayır. **RÜZGAR** ile tam ayrım: Hafif → Evet; Kuvvetli → Hayır.

```text
HAVA
├── Güneşli → NEM
│   ├── Yüksek → Hayır
│   └── Normal → Evet
├── Bulutlu → Evet
└── Yağmurlu → RÜZGAR
    ├── Hafif → Evet
    └── Kuvvetli → Hayır
```

**Dallanma durdurma:** İlgili alt kümede bütün hedef değerler aynı sınıftaysa yeni bölünme yapılmaz. Bir alt düğümde yalnızca o dala ait kayıtlar kullanılır.

## 5. Kazanç Oranı (Gain Ratio)

Bilgi kazancı, çok fazla farklı değer içeren nitelikleri tercih edebilir. Bölünme büyüklüklerinin entropisi **Bilgi Bölünmesi (Split Information)** olarak hesaplanır:

$$H(P_{X,T})=-\sum_{i=1}^{m}\frac{|T_i|}{|T|}\log_2\left(\frac{|T_i|}{|T|}\right)$$

$$\boxed{Kazanç\ Oranı(X,T)=\frac{Kazanç(X,T)}{H(P_{X,T})}}$$

**Önemli:** Bilgi Bölünmesi'nde hedef sınıfların Evet/Hayır dağılımı değil, dallardaki kayıt sayıları kullanılır. Payda sıfırsa oran tanımsızdır.

**ISI örneği:** Soğuk=4, Ilık=6, Sıcak=4; toplam=14.

$$H(P_{ISI,OYUN})=-\left(\frac4{14}\log_2\frac4{14}+\frac6{14}\log_2\frac6{14}+\frac4{14}\log_2\frac4{14}\right)\approx1.5567$$

$$Kazanç(ISI)\approx0.0292;\qquad Kazanç\ Oranı(ISI)\approx\frac{0.0292}{1.5567}=0.0188$$

| Kazanç Ölçütü | Kazanç Oranı |
|---|---|
| Bölünmenin belirsizliği ne kadar azalttığını ölçer | Kazancı bölünme bilgisine oranlar |
| ID3 için temel ölçüt | C4.5 için kullanılan ölçüt |
| Hedef sınıf dağılımını temel alır | Ek olarak dal büyüklüklerini kullanır |

## 6. Sayısal Nitelikler ve Eşik Değeri

Sürekli/sayısal nitelikler için ikili test:

$$X\le t\quad\text{veya}\quad X>t$$

**Aday eşik:** Sıralanmış komşu iki farklı değer arasındaki orta nokta:

$$\boxed{t_i=\frac{v_i+v_{i+1}}2}$$

**Yöntem:** Sayısal değerleri sırala → aday eşikleri bul → her eşikte iki grup oluştur → her grubun hedef sınıf entropisini hesapla → ağırlıklı entropi ve kazancı hesapla → en yüksek kazanç sağlayan eşiği seç.

**Ders örneği:** NİTELİK2 değerleri $\{65,70,75,80,85,90,95,96\}$. Sunumda 80 ile 85 arasındaki eşik seçilir:

$$t=\frac{80+85}{2}=82.5\approx83$$

**NİTELİK2 ≤ 83** → Eşit veya küçük; **NİTELİK2 > 83** → Büyük.

**Dikkat:** 80'in en uygun ayırma noktası olduğu sonucunu yalnızca sayıları sıralayarak genelde bulamayız; hedef SINIF değerleri ve kazanç hesabı gereklidir. Tablo 3.17'de 78 de vardır; gerçek aday eşikler farklı kayıt değerlerinin sıralanmasıyla oluşturulur.

## 7. Bilinmeyen Nitelik Değerleri

Eksik değer sunumda **?** ile gösterilir. C4.5, eksik nitelik değerlerini dikkate almak için düzeltme faktörü kullanır.

$$\boxed{F=\frac{\text{Niteliği bilinen örnek sayısı}}{\text{Toplam örnek sayısı}}}$$

$$\boxed{Kazanç(X)=F\,[H(T)-H(X,T)]}$$

**Tablo 3.21:** NİTELİK1'de 14 kaydın birinde `?` bulunduğu için $F=13/14\approx0.9286$. Bu, kazancı düzeltmek için kullanılan faktördür; kendi başına kazanç değildir.

## 8. Karar Kuralları Oluşturmak

Karar ağacının kökten yaprağa her yolu bir **IF–THEN–ELSE** kuralına dönüştürülebilir.

```text
KURAL 1: EĞER HAVA=Güneşli VE NEM=Yüksek İSE OYUN=Hayır
KURAL 2: EĞER HAVA=Güneşli VE NEM=Normal İSE OYUN=Evet
KURAL 3: EĞER HAVA=Bulutlu İSE OYUN=Evet
KURAL 4: EĞER HAVA=Yağmurlu VE RÜZGAR=Kuvvetli İSE OYUN=Hayır
KURAL 5: EĞER HAVA=Yağmurlu VE RÜZGAR=Hafif İSE OYUN=Evet
```

## 9. Formül Özeti

| Konu | Formül |
|---|---|
| Entropi | $H(T)=-\sum p_i\log_2p_i$ |
| Ağırlıklı Entropi | $H(X,T)=\sum(|T_i|/|T|)H(T_i)$ |
| Kazanç | $H(T)-H(X,T)$ |
| Bilgi Bölünmesi | $-\sum(|T_i|/|T|)\log_2(|T_i|/|T|)$ |
| Kazanç Oranı | $Kazanç/Bilgi\ Bölünmesi$ |
| Eşik | $(v_i+v_{i+1})/2$ |
| Düzeltme Faktörü | $Bilinen/Toplam$ |
| Düzeltilmiş Kazanç | $F[H(T)-H(X,T)]$ |

## 10. Sınav İpuçları

- Entropi 0 → bütün kayıtlar aynı sınıfta; yaprak oluştur.
- Kazanç büyük → daha fazla belirsizlik azalması.
- ID3 → Kazanç Ölçütü.
- C4.5 → Kazanç Oranı, sayısal nitelikler ve eksik değer işlemleri.
- Kök → seçilen ölçüte göre en iyi nitelik.
- Alt dal hesabı → yalnızca o dala ait kayıtlarla.
- Sayısal nitelik → eşik ile ikili test.
- Kayıp değer → `?`.
- Karar kuralı → kökten yaprağa bir yol.

**Kaynak notu:** Bu özet, 83 slaytlık dersin başlıklarını ve tablolarını izler. Görsel/formül olarak saklanan bazı slayt içerikleri düz metin çıkarımında görünmediğinden, standart formüller dersin bağlamına uygun matematiksel gösterimle yazılmıştır.
