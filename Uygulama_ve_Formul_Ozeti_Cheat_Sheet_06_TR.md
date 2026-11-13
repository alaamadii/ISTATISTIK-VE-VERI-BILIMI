# CHEAT SHEET 06 — UYGULAMA VE FORMÜL ÖZETİ

**Kapsam:** Veri Ön İşleme · Karar Ağaçları · Model Değerlendirme · KNN · Birliktelik Kuralları

> Bu özet önceki ders materyallerindeki formülleri ve örnekleri birleştirir. Bazı sayısal örnekler ek alıştırmadır.

## 1. Hangi Soruda Hangi Formül?

| Soru | Yöntem |
|---|---|
| 0–1 aralığına dönüştürme | Min-Max |
| Ortalamaya göre uzaklık | Z-Score |
| Belirsizlik | Entropi |
| Kök düğüm seçimi | Kazanç / Kazanç Oranı |
| Sayısal niteliği bölme | Eşik Değeri |
| Eksik nitelik değeri | Düzeltme Faktörü |
| Tahmin başarısı | Confusion Matrix |
| Precision ve Recall'ı birleştirme | F₁-Score |
| Yeni gözlemin sınıfı | KNN |
| Yakın komşuya daha fazla önem | Ağırlıklı Oylama |
| Birlikte alınan ürünler | Support / Confidence |

## 2. Min-Max Normalleştirme

$$X'=\frac{X-X_{\min}}{X_{\max}-X_{\min}}$$

**Adımlar:** Minimumu bul → maksimumu bul → değeri yerine koy → sonucu hesapla.

**Örnek:** $X=\{10,20,30,40,50\}$ ve $X=30$ için:

$$X'=\frac{30-10}{50-10}=0.5$$

**Hatırla:** Minimum 0, maksimum 1 olur. Payda sıfırsa formül doğrudan uygulanamaz.

## 3. Z-Score Standartlaştırma

$$Z=\frac{X-\bar X}{s}$$

**Örnek:** $\bar X=40$, $s=8$, $X=28$:

$$Z=\frac{28-40}{8}=-1.5$$

**Yorum:** Gözlem, ortalamanın 1.5 standart sapma altındadır. Z pozitifse ortalamanın üstünde, negatifse altındadır.

## 4. Entropi

$$H(T)=-\sum_{i=1}^{k}p_i\log_2(p_i)$$

**Adımlar:** Her sınıfın sayısını bul → olasılıkları hesapla → formüle yerleştir → topla.

**Örnek:** 6 Evet, 2 Hayır:

$$H(T)=-\frac68\log_2\frac68-\frac28\log_2\frac28\approx0.8113$$

**Hatırla:** İkili sınıflandırmada H=0 saf grup; H=1 eşit dağılım.

## 5. Kazanç Ölçütü (Information Gain)

$$H(X,T)=\sum_{i=1}^{m}\frac{|T_i|}{|T|}H(T_i)$$

$$Kazanç(X,T)=H(T)-H(X,T)$$

**Adımlar:** Ana entropi → niteliğe göre gruplar → her grubun entropisi → ağırlıklı entropi → çıkarma → adayları karşılaştırma.

**ID3:** En yüksek Kazanç seçilir.

**Ders örneği (OYUN):**

| Nitelik | Kazanç (yaklaşık) |
|---|---:|
| HAVA | 0.2467 |
| ISI | 0.0292 |
| NEM | 0.1518 |
| RÜZGAR | 0.0481 |

**Kök düğüm:** HAVA.

## 6. Kazanç Oranı (Gain Ratio)

$$SplitInfo(X)=-\sum_{i=1}^{m}\frac{|T_i|}{|T|}\log_2\frac{|T_i|}{|T|}$$

$$GainRatio(X)=\frac{Gain(X)}{SplitInfo(X)}$$

**Örnek (HAVA):** $Gain=0.2467$, $SplitInfo\approx1.5774$:

$$GainRatio\approx\frac{0.2467}{1.5774}=0.1564$$

**Fark:** Kazanç hesabında hedef sınıflarının dağılımı; SplitInfo hesabında dal büyüklükleri kullanılır. Payda sıfırsa oran tanımsızdır.

## 7. Sayısal Nitelikler — Eşik Değeri

$$t_i=\frac{v_i+v_{i+1}}2$$

**Adımlar:** Değerleri sırala → aday eşikleri belirle → her eşikte $\leq t$ ve $>t$ olarak ayır → iki grubun entropilerini hesapla → Kazanç hesapla → en yüksek Kazanç değerini seç.

**Ders örneği:** 80 ve 85 arasındaki eşik:

$$t=\frac{80+85}{2}=82.5\approx83$$

- NİTELİK2 ≤ 83
- NİTELİK2 > 83

**Önemli:** Eşiğin en uygun olduğunu doğrulamak için hedef sınıf değerleriyle Kazanç karşılaştırması gerekir.

## 8. Kayıp Nitelik Değerleri

$$F=\frac{\text{Bilinen örnek sayısı}}{\text{Toplam örnek sayısı}}$$

$$Düzeltilmiş\ Kazanç=F[H(T)-H(X,T)]$$

**Örnek:** 14 kaydın 13'ü biliniyor:

$$F=\frac{13}{14}\approx0.9286$$

Kazanç 0.20 ise düzeltilmiş değer:

$$0.9286\times0.20\approx0.1857$$

## 9. Confusion Matrix

| GERÇEK / TAHMİN | Pozitif | Negatif |
|---|---|---|
| Pozitif | TP | FN |
| Negatif | FP | TN |

- **TP:** Gerçek pozitif, tahmin pozitif.
- **TN:** Gerçek negatif, tahmin negatif.
- **FP:** Gerçek negatif, tahmin pozitif.
- **FN:** Gerçek pozitif, tahmin negatif.

$$N=TP+TN+FP+FN$$

| Ölçüt | Formül |
|---|---|
| Accuracy | $(TP+TN)/N$ |
| Error | $(FP+FN)/N$ |
| Precision | $TP/(TP+FP)$ |
| Recall (Sensitivity) | $TP/(TP+FN)$ |
| Specificity | $TN/(TN+FP)$ |
| F₁-Score | $2PR/(P+R)$ |
| Fβ-Score | $(1+\beta^2)PR/(\beta^2P+R)$ |

**Ek uygulama:** $TP=40$, $TN=30$, $FP=10$, $FN=20$, $N=100$.

| Ölçüt | Hesap | Sonuç |
|---|---|---:|
| Accuracy | $(40+30)/100$ | 0.70 |
| Error | $(10+20)/100$ | 0.30 |
| Precision | $40/(40+10)$ | 0.80 |
| Recall | $40/(40+20)$ | 0.6667 |
| Specificity | $30/(30+10)$ | 0.75 |
| F₁ | $2(0.8)(0.6667)/(0.8+0.6667)$ | 0.7273 |

**Hatırla:** Accuracy yüksek olsa bile dengesiz veri kümesinde Recall çok düşük olabilir. Sıfır paydalı ölçüt matematiksel olarak tanımsızdır.

## 10. KNN — En Yakın K-Komşu

$$d(i,j)=\sqrt{\sum_{r=1}^{p}(x_{ir}-x_{jr})^2}$$

**İki boyutlu örnek:** $A=(3,4)$, $B=(7,7)$:

$$d=\sqrt{(7-3)^2+(7-4)^2}=5$$

**Çözüm sırası:** k belirle → uzaklıkları hesapla → küçükten büyüğe sırala → ilk k komşuyu seç → sınıfları say → çoğunluk sınıfını seç.

**Ders örnekleri:**

- $(8,4)$, $k=4$ → **KÖTÜ**.
- $(7,8,5)$, $k=3$ ve Min-Max → **EVET**.
- $(0.10,0.50)$, $k=3$ → Normal Oylama: **ERKEK**; Ağırlıklı Oylama: **KADIN**.

### Ağırlıklı Oylama

$$w_i=\frac1{d_i^2}$$

$$W(C)=\sum_{i:Y_i=C}w_i$$

**Ders örneği:** ERKEK ağırlığı $11.046+13.793=24.839$, KADIN ağırlığı $200$ → **KADIN**.

**Not:** $d=0$ olduğunda $1/d^2$ formülü doğrudan uygulanamaz; aynı konumdaki gözlemler özel olarak ele alınır.

## 11. Birliktelik Kuralları

$$Support(X\rightarrow Y)=\frac{n(X\cap Y)}{N}$$

$$Confidence(X\rightarrow Y)=\frac{n(X\cap Y)}{n(X)}$$

**Ek örnek:** 10 işlem, 4 işlemde ekmek, 3 işlemde hem ekmek hem süt:

$$Support=\frac3{10}=0.30$$

$$Confidence=\frac34=0.75$$

**Fark:** Support tüm işlemleri, Confidence öncülün gerçekleştiği işlemleri esas alır.

## 12. Sınav İçin Hızlı Ezber Tablosu

| Konu | Kural |
|---|---|
| Min-Max | Minimum 0, maksimum 1 |
| Z-Score | Negatif = ortalamanın altında |
| Entropi | 0 = belirsizlik yok |
| ID3 | En büyük Kazanç |
| Gain Ratio | Kazanç / Bilgi Bölünmesi |
| Eşik | Adaylar arasında en büyük Kazanç |
| Kayıp Değer | Düzeltme Faktörü |
| TP / TN | Doğru tahmin |
| FP / FN | Yanlış tahmin |
| Precision | TP / (TP + FP) |
| Recall | TP / (TP + FN) |
| F₁ | Precision ve Recall harmonik ortalaması |
| KNN | En yakın k komşu |
| Ağırlıklı KNN | Yakın komşunun etkisi daha büyük |
| Support | Birlikte görülme / Toplam |
| Confidence | Birlikte görülme / Öncül |
