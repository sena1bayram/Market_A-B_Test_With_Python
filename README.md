# Pazarlama Veri Seti ile A/B Testi Analizi 🎡

Bu depo, bir pazarlama veri setini kullanarak A/B testi analizi yapmak için bir Python betiği içermektedir. Bu analizdeki amaç, farklı test gruplarının (örneğin, reklamlar ve kamu hizmeti duyuruları) dönüşüm oranlarında istatistiksel olarak anlamlı bir fark olup olmadığını belirlemektir.

## Veri Seti Genel Bakış

Veri seti, kullanıcıların pazarlama kampanyalarıyla etkileşimlerine ilişkin bilgiler içermektedir. Öne çıkan özellikler:
- **test group**: Kullanıcının bir reklam (`ad`) veya bir kamu hizmeti duyurusu (`psa`) görüp görmediğini belirtir.
- **converted**: Kullanıcının dönüşüm sağlayıp sağlamadığını belirtir (1: Dönüştü, 0: Dönüşmedi).
- **most ads day**: Kullanıcının en fazla reklam gördüğü gün.
- **most ads hour**: Kullanıcının en fazla reklam gördüğü saat.

## Hipotez ve Amaç 🌐

### Null Hipotez (H₀):
`ad` grubu ile `psa` grubu arasında dönüşüm oranları açısından anlamlı bir fark yoktur.

### Alternatif Hipotez (H₁):
`ad` grubu ile `psa` grubu arasında dönüşüm oranları açısından anlamlı bir fark vardır.

Birincil hedef, istatistiksel analiz (t-testi) kullanarak hipotezleri değerlendirmektir.

## Keşifsel Veri Analizi 🔍

1. Eksik değerler ve temel veri seti bilgileri kontrol edildi.
2. `test group` sütunundaki gereksiz boşluklar temizlendi.
3. `converted` sütunu analiz için sayısal formata dönüştürüldü.
4. Genel ve gruplandırılmış dönüşüm oranları hesaplandı.
5. Reklamların en etkili olduğu günler ve saatler belirlendi.

## Analiz Adımları 🔢

1. **Veri Temizleme**:
   - Eksik değerler kontrol edildi.
   - Kategorik değişkenlerden boşluklar kaldırıldı.
   - Mantıksal `converted` değerleri tamsayıya dönüştürüldü.

2. **Gruplama ve Toplama**:
   - Her test grubu için ortalama dönüşüm oranları hesaplandı.
   - Reklam dönüşümleri açısından en iyi performans gösteren günler ve saatler belirlendi.

3. **İstatistiksel Test**:
   - `ad` ve `psa` grupları arasındaki dönüşüm oranlarını karşılaştırmak için bağımsız t-testi uygulandı.

## Temel Bulgular 🔍

### 1. Dönüşüm Oranları:
- **ad grubunun dönüşüm oranı**: %2.55
- **psa grubunun dönüşüm oranı**: %1.79
  - **Yorum**: Reklam grubunun dönüşüm oranı, kamu spotu grubuna göre daha yüksektir.

### 2. En Verimli Günler:
- **En yüksek dönüşüm oranı**: Pazartesi günü (%3.28).
- **En düşük dönüşüm oranı**: Cumartesi günü (%2.10).
  - **Yorum**: Reklamlar, hafta başında daha etkili olabilir; bu durum stratejik planlamada dikkate alınabilir.

### 3. En Verimli Saatler:
- **En yüksek dönüşüm oranı**: 16:00 (%3.07) ve 15:00 (%2.97) saatlerindedir.
- **En düşük dönüşüm oranı**: 02:00 (%0.73) saatindedir.
  - **Yorum**: Reklamların gündüz saatlerinde daha etkili olduğu gözlemlenmiştir.

### 4. T-Testi Sonuçları:
- **T-istatistiği**: 7.37
- **P-değeri**: < 0.0001
  - **Yorum**: Gruplar arasında istatistiksel olarak anlamlı bir fark bulunmaktadır. `ad` grubunun dönüşüm oranı, `psa` grubuna göre belirgin derecede daha yüksektir.

### 5. Genel Değerlendirme:
- Reklam grubunun (`ad`) performansı, kamu spotu grubuna (`psa`) göre daha başarılıdır.
- Reklamların daha etkili olduğu günler (Pazartesi ve Salı) ve saatler (öğleden sonra) stratejik olarak değerlendirilebilir.
- Bu bulgular, bütçe ve zamanlama optimizasyonu için önemli içgörüler sunmaktadır.

## Görselleştirmeler 🎨

1. **Test Grubuna Göre Dönüşüm Oranı**:
   `ad` ve `psa` gruplarının dönüşüm oranlarını karşılaştıran bir sütun grafiği.

2. **En Etkili Günler**:
   Haftanın her günü için dönüşüm oranlarını gösteren bir sütun grafiği.


3. **En Etkili Saatler**:
   Saatlik dönüşüm oranlarını vurgulayan bir sütun grafiği.

![image](https://github.com/user-attachments/assets/ce6da466-891f-4230-9c4d-e7a552aa2d26)
![image](https://github.com/user-attachments/assets/135b64e9-fa74-4d7a-99d1-ec05b85f53e9)


## Kullanım 🚀

1. Depoyu klonlayın:
   ```bash
   git clone https://github.com/your_username/marketing-ab-testing.git
   ```
2. Gerekli Python kütüphanelerini yükleyin:
   ```bash
   pip install -r requirements.txt
   ```
3. Betiği çalıştırın:
   ```bash
   python ab_testing_analysis.py
   ```

## Gereksinimler 📊

- Python 3.8+
- Pandas
- Matplotlib
- SciPy


## Katkıda Bulunun 📚

Geliştirmeler için lütfen konular açın veya pull request gönderin. Bu analizi daha da geliştirmek için iş birliği yapalım!

---


