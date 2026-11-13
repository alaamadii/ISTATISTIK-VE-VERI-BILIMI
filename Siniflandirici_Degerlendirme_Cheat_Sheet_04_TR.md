# CHEAT SHEET 04 — SINIFLANDIRICI DEĞERLENDİRME

**Kaynak:** DEĞERLENDİRME(2).pdf — 11 slayt. **Konular:** Hata Matrisi, Accuracy, Error, Precision, Recall, Specificity, F-Score.

## 1. Hata Matrisi (Confusion Matrix)

Gerçek sınıflar ile tahmin edilen sınıfları karşılaştırır.

| GERÇEK / TAHMİN | Pozitif C⁺ | Negatif C⁻ | Toplam |
|---|---:|---:|---:|
| Pozitif C⁺ | TP | FN | TP + FN |
| Negatif C⁻ | FP | TN | FP + TN |
| Toplam | TP + FP | FN + TN | N |

- **TP (True Positive):** Gerçekte pozitif, tahminde pozitif — doğru.
- **TN (True Negative):** Gerçekte negatif, tahminde negatif — doğru.
- **FP (False Positive):** Gerçekte negatif, tahminde pozitif — hata.
- **FN (False Negative):** Gerçekte pozitif, tahminde negatif — hata.
- **N = TP + TN + FP + FN.**
- Gerçek pozitif sayısı **N⁺ = TP + FN**; gerçek negatif sayısı **N⁻ = TN + FP**.
- Tahmin pozitif sayısı **N̂⁺ = TP + FP**; tahmin negatif sayısı **N̂⁻ = TN + FN**.

## 2. Accuracy (Doğruluk) ve Hata Oranı

**Accuracy = (TP + TN) / N**

**Error = (FP + FN) / N = 1 − Accuracy**

Dersin ilk örneği:

| GERÇEK / TAHMİN | Pozitif | Negatif | Toplam |
|---|---:|---:|---:|
| Pozitif | 10 | 2 | 12 |
| Negatif | 2 | 8 | 10 |
| Toplam | 12 | 10 | 22 |

- Accuracy = (10 + 8) / 22 = **0.8182 ≈ 0.82**.
- Error = (2 + 2) / 22 = **0.1818 ≈ 0.18**.

## 3. Precision (Kesinlik)

**Precision = TP / (TP + FP)**

Pozitif tahmin edilen örneklerin gerçekten pozitif olanlarının oranı. Soru: **Pozitif dediklerimin kaçı gerçekten pozitif?**

Yüksek Precision, yanlış pozitif tahminlerin az olduğunu gösterir.

## 4. Recall (Duyarlılık)

**Recall = TP / (TP + FN)**

Gerçek pozitif örneklerin doğru pozitif tahmin edilenlerinin oranı. Soru: **Gerçek pozitiflerin kaçını yakaladım?**

Diğer adı: **Sensitivity / True Positive Rate (TPR)**.

## 5. Specificity (Özgüllük)

**Specificity = TN / (TN + FP)**

Gerçek negatif örneklerin doğru negatif tahmin edilenlerinin oranı. Soru: **Gerçek negatiflerin kaçını doğru buldum?**

Diğer adı: **True Negative Rate (TNR)**.

## 6. F-Score ve Harmonik Ortalama

**F₁ = 2 × Precision × Recall / (Precision + Recall)**

**Fβ = (1 + β²) × Precision × Recall / (β² × Precision + Recall)**

- β = 1: Precision ve Recall eşit ağırlıklı.
- β > 1: Recall daha önemli.
- 0 < β < 1: Precision daha önemli.

**Harmonik Ortalama = n / Σ(1/xᵢ)**.

İki değer için: **2 / (1/Precision + 1/Recall) = F₁** (pozitif paydalar için).

## 7. Dersin İkinci Örneği: Dengesiz Veri

| GERÇEK / TAHMİN | Pozitif | Negatif | Toplam |
|---|---:|---:|---:|
| Pozitif | 0 | 5 | 5 |
| Negatif | 7 | 993 | 1000 |
| Toplam | 7 | 998 | 1005 |

TP = 0, FN = 5, FP = 7, TN = 993.

| Ölçüt | İşlem | Sonuç |
|---|---|---:|
| Accuracy | (0 + 993) / 1005 | **0.9881 ≈ 0.99** |
| Error | (7 + 5) / 1005 | **0.0119 ≈ 0.01** |
| Precision | 0 / (0 + 7) | **0** |
| Recall | 0 / (0 + 5) | **0** |
| Specificity | 993 / (993 + 7) | **0.993 ≈ 0.99** |
| F₁ | 2 × 0 × 0 / (0 + 0) | **0 (slaytta böyle gösterilir)** |

**Önemli:** F₁ ifadesinde Precision = Recall = 0 iken doğrudan yazılan kesrin paydası sıfır olur; pratikte F₁ = 0 kabul edilir. Slaytta sonuç 0 verilmiştir.

**Sınav tuzağı:** Accuracy ≈ %99 olsa da gerçek pozitiflerin **hiçbiri** bulunamamıştır. Dengesiz veri kümelerinde Accuracy tek başına yeterli değildir.

## 8. Ölçütlerin Yorumu

| Ölçüt | Yüksek değer | Düşük değer |
|---|---|---|
| Accuracy | Genel doğruluk yüksek | Genel doğruluk düşük |
| Precision | Yanlış pozitif az | Yanlış pozitif fazla |
| Recall | Kaçırılan pozitif az | Kaçırılan pozitif fazla |
| Specificity | Gerçek negatifler iyi tanınır | Gerçek negatifler sıkça yanlış pozitif olur |
| F₁ | Precision ve Recall birlikte güçlü | İkisinden biri veya her ikisi zayıf |
| Error | Daha çok hata (kötü) | Daha az hata (iyi) |

Her problem için sabit bir iyi/kötü eşiği yoktur. Hangi hatanın daha önemli olduğuna göre değerlendirme yapılır.

## 9. Soru İpuçları

| Soruda geçen ifade | Ölçüt |
|---|---|
| Tüm doğru tahminlerin oranı | Accuracy |
| Tüm yanlış tahminlerin oranı | Error |
| Pozitif tahmin edilenlerin doğruluğu | Precision |
| Gerçek pozitiflerin yakalanması | Recall |
| Gerçek negatiflerin doğru sınıflandırılması | Specificity |
| Precision ve Recall birlikte | F₁-Score |
| Precision/Recall ağırlığı β ile ayarlanır | Fβ-Score |

## 10. Tek Sayfalık Formül Özeti

| Ölçüt | Formül |
|---|---|
| Accuracy | (TP + TN) / N |
| Error | (FP + FN) / N |
| Precision | TP / (TP + FP) |
| Recall | TP / (TP + FN) |
| Specificity | TN / (TN + FP) |
| F₁ | 2PR / (P + R) |
| Fβ | (1 + β²)PR / (β²P + R) |

**Not:** Paydanın sıfır olduğu durumlarda matematiksel ifade tanımsızdır; uygulama için ayrıca sıfır bölme kuralı belirlenir.
