# CHEAT SHEET 01 — VERİ BİLİMİNE GİRİŞ

**Kaynak:** Bolum_2_Veri_Bilimine_Giris — 26 slayt  
**Kapsam:** Temel kavramlar, veri türleri, süreç, yöntemler ve uygulamalar.

## 1. Veri Nedir?

**Veri:** Bilgisayara girilen işlenmemiş (ham) bilgilerdir. Bilgisayarın alabildiği, işleyebildiği, sonuç üretebildiği ve saklayabildiği her şey veri olabilir. Programlar tarafından işlenebilmesi için derlenmiş ve formüle edilmiş bilgi biçimi olarak da tanımlanır. Tek başına anlam taşımayabilir.

**Örnek:** Ölçüm, gözlem, sensör kaydı, işlem kaydı, metin, görüntü, ses ve video.

## 2. Veri Türleri ve Değişkenler

| Veri türü | Açıklama | Örnek |
|---|---|---|
| Yapılandırılmış | Önceden belirlenmiş şema, satır ve sütunlar | SQL, Excel |
| Yarı yapılandırılmış | Sabit tablo yok; anahtar veya etiketlerle düzenli | JSON, XML, e-posta başlığı, log |
| Yapılandırılmamış | Önceden tanımlı model yok | Metin, görüntü, ses, video |

| Değişken türü | Alt tür | Özellik | Örnek |
|---|---|---|---|
| Kategorik | Nominal | Sıra yok | Renk, şehir |
| Kategorik | Ordinal | Anlamlı sıra var | Düşük, orta, yüksek |
| Sayısal | Kesikli | Sayılabilir değer | Öğrenci sayısı |
| Sayısal | Sürekli | Aralık içinde ölçüm | Boy, ağırlık |

## 3. DIKW Piramidi

**Veri → Enformasyon → Bilgi → Bilgelik**

| Düzey | Anlamı | Şemsiye örneği |
|---|---|---|
| Veri (Data) | Ham değerler | Haftalık satış: 120, 95, 60 |
| Enformasyon (Information) | Anlamlandırılmış veri | Satış üç haftada %50 düştü |
| Bilgi (Knowledge) | İlişkiyi anlama | Satışlar yağışlı günlerle ilişkili |
| Bilgelik (Wisdom) | Karara dönüştürme | Hava tahminine göre stok planlama |

## 4. Veri Bilimi

**Tanım:** İstatistik, matematik, bilgisayar bilimi ve alan bilgisini birleştirerek veriden anlamlı bilgi, öngörü ve değer üreten disiplinlerarası alan.

**Amaçlar:** Problemi belirleme; veriyi toplama, hazırlama, analiz etme ve modelleme; sonuçları yorumlama, sunma ve kararları destekleme.

**Temel bileşenler:** Bilgisayar bilimi/programlama; matematik/istatistik; alan bilgisi; makine öğrenmesi.

**İlgili alanlar:** Yapay zekâ, büyük veri, veritabanları, istatistiksel modelleme, görselleştirme, iş zekâsı ve karar destek.

## 5. Büyük Veri ve 5V

| 5V | Türkçe | Açıklama |
|---|---|---|
| Volume | Hacim | Veri miktarı |
| Velocity | Hız | Üretim ve işleme hızı |
| Variety | Çeşitlilik | Farklı veri türleri |
| Veracity | Doğruluk | Güvenilirlik ve kalite |
| Value | Değer | Veriden elde edilen fayda |

**Neden veri bilimi?** İnternet, mobil cihazlar ve sensörler çok veri üretir. Amaç, veriyi analiz ederek veriye dayalı karar vermektir.

## 6. Uygulama Alanları

| Alan | Uygulamalar |
|---|---|
| İş dünyası ve pazarlama | Segmentasyon, churn tahmini, öneri sistemleri, hedefli pazarlama |
| Finans ve bankacılık | Kredi riski, dolandırıcılık, yatırım ve portföy analizi |
| Sağlık | Tıbbi görüntü, hastalık riski, ilaç keşfi, hasta takibi |
| Bilim ve mühendislik | Astronomi, biyoinformatik, iklim, kestirimci bakım |
| Metin ve web | Duygu analizi, arama, sohbet botları, metin sınıflandırma |
| Kamu ve güvenlik | Akıllı şehir, trafik, siber saldırı, vergi kaçakçılığı |

## 7. Veri Bilimi Yaşam Döngüsü

1. **Problemi Tanımlama:** Hangi soruya yanıt aranıyor?
2. **Veri Toplama:** Veritabanı, API, sensör, anket, web.
3. **Veri Hazırlama:** Temizleme, bütünleştirme, dönüştürme.
4. **Keşifsel Analiz:** İstatistik, grafik, örüntü.
5. **Modelleme:** Algoritma seçimi ve eğitim.
6. **Değerlendirme:** Başarı ölçütleri ve doğrulama.
7. **Sunum ve Dağıtım:** Rapor, pano, canlı sistem.

**Önemli:** Süreç doğrusal değil, döngüseldir. Değerlendirmeden sonra önceki adımlara dönülebilir.

## 8. Veri Ön İşleme

| İşlem | Açıklama |
|---|---|
| Veri temizleme | Eksik, hatalı ve tutarsız değerleri düzeltme |
| Veri bütünleştirme | Farklı kaynakları birleştirme |
| Veri indirgeme | Örnek veya özellik sayısını azaltma |
| Veri dönüştürme | Normalizasyon, ölçekleme, kodlama |

**İlke:** Kaliteli model, kaliteli veriyle başlar; veri hazırlama önemli zaman alır.

## 9. Veri Bilimcinin Araç Kutusu

| Kategori | Araçlar |
|---|---|
| Programlama | Python, R, SQL |
| Veri işleme | NumPy, pandas |
| Makine öğrenmesi | scikit-learn, TensorFlow, PyTorch |
| Görselleştirme | Matplotlib, Seaborn, Power BI, Tableau |
| Geliştirme | Jupyter Notebook, Google Colab, VS Code |
| Büyük veri | Apache Hadoop, Apache Spark |

## 10. Yöntemlerin Sınıflandırılması

**Tahmin edici (Predictive):** Bilinmeyen hedef veya gelecek değer tahmini. Sınıflandırma, regresyon, zaman serisi analizi.

**Tanımlayıcı (Descriptive):** Gizli ilişki ve örüntüleri keşfetme. Kümeleme, birliktelik kuralları, sıralı örüntü, özetleme/tanımsal istatistik, aykırı değer analizi.

| Öğrenme türü | Özellik | Örnek |
|---|---|---|
| Denetimli | Hedef etiketi bilinir | Sınıflandırma, regresyon |
| Denetimsiz | Hedef etiketi yoktur | Kümeleme, birliktelik |
| Yarı denetimli | Etiketli ve etiketsiz veriler | Az etiketli veri |
| Pekiştirmeli | Ödül/ceza geri bildirimi | Karar verme |

## 11. Sınıflandırma (Classification)

**Tanım:** Önceden belirlenmiş kategorik sınıfı tahmin eden, denetimli ve tahmin edici yöntem.

**Örnek:** Spam/normal, riskli/risksiz, iyi/kötü, başarılı/başarısız.

**İki aşama:**
1. **Model oluşturma:** Sınıfı bilinen eğitim verilerinden kurallar/model öğrenilir.
2. **Model kullanımı:** Model yeni örneğe uygulanır; test verisinin gerçek sınıfıyla tahmin karşılaştırılır.

**Algoritmalar:** Karar ağaçları, Bayes, k-en yakın komşu (k-NN), yapay sinir ağları, destek vektör makineleri (SVM).

**Değerlendirme:** Doğruluk (Accuracy), kesinlik (Precision), duyarlılık (Recall), F1-skoru; hız (eğitim ve tahmin), kararlılık (gürültüye dayanıklılık), ölçeklenebilirlik, yorumlanabilirlik, kuralların sadeliği.

## 12. Kümeleme (Clustering)

**Tanım:** Önceden bilinen sınıf etiketi olmadan benzer örnekleri gruplara ayırma. Denetimsiz ve tanımlayıcıdır; gruplama/demetleme de denir. Tek başına veya ön işleme amacıyla kullanılabilir.

**Örnek:** Müşteri segmentasyonu.

**Algoritmalar:** k-ortalamalar (k-means), hiyerarşik kümeleme, DBSCAN.

| Sınıflandırma | Kümeleme |
|---|---|
| Denetimli | Denetimsiz |
| Sınıflar bilinir | Sınıflar önceden bilinmez |
| Tahmin edici | Tanımlayıcı |
| Karar ağacı, k-NN | k-means, hiyerarşik kümeleme |

## 13. Birliktelik Kuralları (Association Rule Discovery)

**Tanım:** Öğelerin/olayların birlikte gerçekleşme ilişkilerini inceler. Market sepet analizi, raf düzeni ve kampanya tasarımında kullanılır.

**Ders örneği:** Gömlek alan müşterilerin %55'i aynı alışverişte kravat da alır.

**Kural:** `X → Y`

**Destek (Support):**

`Support(X → Y) = n(X ∩ Y) / N`

**Güven (Confidence):**

`Confidence(X → Y) = n(X ∩ Y) / n(X)`

- `n(X ∩ Y)`: X ve Y'yi birlikte içeren işlem sayısı.
- `N`: Toplam işlem sayısı.
- `n(X)`: X'i içeren işlem sayısı.

**Örnek:** 5 işlemden 4'ünde ekmek, 3'ünde ekmek ve peynir varsa:
- Support(Ekmek → Peynir) = 3/5 = **%60**.
- Confidence(Ekmek → Peynir) = 3/4 = **%75**.

**Başka örnek:** 5 işlemin 4'ünde peynir ve makarna birlikteyse ve peynir 4 işlemde varsa Support = 4/5 = %80; Confidence = 4/4 = %100.

**Önemli:** Minimum destek ve minimum güven eşikleri güçlü kural seçiminde kullanılır. Support paydasında tüm işlemler; Confidence paydasında X içeren işlemler vardır.

## 14. Sıralı Örüntü Keşfi (Sequential Pattern Discovery)

**Tanım:** Zamana bağlı olarak birbirini izleyen olayları bulma. Birliktelik kurallarından farklı olarak sıra ve zaman önemlidir.

**Ders örneği:** 1. alışveriş ayakkabı → 2. alışveriş raket ve tenis topu → 3. alışveriş spor kıyafeti.

**Diğer örnekler:** Web tıklama dizileri, ağ saldırısı adımları.

| Birliktelik | Sıralı örüntü |
|---|---|
| Birlikte görülme | Birbirini izleme |
| Sıra temel şart değil | Sıra/zaman önemli |

## 15. Regresyon (Regression)

**Tanım:** Diğer değişkenlerden yararlanarak sürekli sayısal hedefi tahmin eden, denetimli ve tahmin edici yöntem. İlişki doğrusal veya doğrusal olmayan biçimde olabilir.

**Örnek:** Ev fiyatı, yeni ürün satış fiyatı, talep tahmini; bankacılık ve sigortacılık.

**Temel fark:** Sınıflandırma → kategorik hedef; regresyon → sayısal hedef.

## 16. Anomali / Sapma Tespiti

**Tanım:** Genel örüntüden belirgin biçimde sapan sıra dışı gözlemleri (aykırı değerleri) belirleme.

**Örnek:** Kredi kartı dolandırıcılığı, ağ saldırısı, üretimde arızalı ürün.

## 17. Sınavda Karıştırılmaması Gerekenler

| Soru ipucu | Doğru kavram |
|---|---|
| Ham değer | Veri |
| İşlenmiş anlamlı veri | Enformasyon |
| Karara dönüştürülmüş bilgi | Bilgelik |
| Sınıf etiketi var | Denetimli öğrenme |
| Sınıf etiketi yok | Denetimsiz öğrenme |
| Spam mı değil mi? | Sınıflandırma |
| Benzer müşterileri grupla | Kümeleme |
| Ev fiyatı kaç TL? | Regresyon |
| Ekmek ve peynir birlikte alınıyor mu? | Birliktelik kuralları |
| Önce ayakkabı, sonra raket | Sıralı örüntü |
| Sıra dışı kredi kartı işlemi | Anomali tespiti |
| Birlikte görülme / tüm işlemler | Support |
| X alanların Y alma oranı | Confidence |
| Eksik/hatalı verileri düzelt | Veri temizleme |
| Farklı kaynakları birleştir | Veri bütünleştirme |
| Örnek/özellik sayısını azalt | Veri indirgeme |
| Ölçekleme/kodlama | Veri dönüştürme |

## 18. Formül Özeti

**Support:** `n(X ∩ Y) / N`  
**Confidence:** `n(X ∩ Y) / n(X)`

## 19. Sınav Öncesi Kontrol Listesi

- [ ] Veri, enformasyon, bilgi ve bilgelik farklarını biliyorum.
- [ ] Yapılandırılmış, yarı yapılandırılmış ve yapılandırılmamış verileri ayırt ediyorum.
- [ ] Kategorik ve sayısal değişken türlerini biliyorum.
- [ ] Büyük Verinin 5V özelliğini biliyorum.
- [ ] Veri Bilimi Yaşam Döngüsünü sırasıyla biliyorum.
- [ ] Ön işleme yöntemlerini ayırt ediyorum.
- [ ] Tahmin edici ve tanımlayıcı yöntemleri ayırt ediyorum.
- [ ] Denetimli ve denetimsiz öğrenme farkını biliyorum.
- [ ] Sınıflandırmanın iki aşamasını açıklıyorum.
- [ ] Sınıflandırma ve kümeleme farkını biliyorum.
- [ ] Support ve Confidence hesaplıyorum.
- [ ] Birliktelik ve sıralı örüntü farkını biliyorum.
- [ ] Regresyon ve sınıflandırma farkını biliyorum.
- [ ] Anomali tespitinin amacını biliyorum.

---

**Kapsam notu:** Bu çalışma, ilk 26 slaytlık Veri Bilimine Giriş sunumunun sınav odaklı özetidir. Veri Madenciliği Bölüm 2, KNN, karar ağaçları ve değerlendirme sonraki cheat sheet konularıdır.
