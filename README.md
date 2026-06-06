# Hacker News Teknoloji Depremleri Analizi

 Hazırlayan: Tülin Eren

 ## Proje Amacım

Bu projede Hacker News veri setini sadece bir haber arşivi olarak değil, zaman içinde teknoloji dünyasının hafızası olarak ele aldım.

Yaklaşık 120.000+ haber üzerinden şu sorulara cevap aradım:

- Teknoloji dünyasında yaşanan büyük olaylar Hacker News’te nasıl yankı buluyor?
- 2008 finansal krizi, COVID-19, Bitcoin gibi olaylar tartışmaları nasıl etkiledi?
- Kullanıcı davranışları zaman içinde nasıl değişiyor?
- Hangi olaylar daha fazla etkileşim alıyor?

Veriyi adeta bir zaman makinesi gibi kullanarak incelemek istedim.


## Veri Seti
- Kaynak: Hacker News (Parquet formatı)
- Veri boyutu: ~120.000+ story
- Yıllar: 2007 – 2020
- İçerik: Başlık (title), Puan (score), Yorum sayısı (descendants), Zaman (time), Yazar bilgisi
## Kullandığım Teknolojiler
- Python 
- DuckDB (büyük veri sorgulama)
- Pandas
- Plotly (interaktif görselleştirme)
- Scikit-learn
## Veri Hazırlama Süreci
### Veriyi Çektim
S3 üzerinde bulunan Parquet veri setini DuckDB ile okudum
Sadece “story” türündeki verileri kullandım
### Temizleme Yaptım
- Silinmiş ve ölü postları çıkardım
- Boş başlıkları temizledim
- 2007–2020 yılları arasını filtreledim
  
## Olay Etiketleme Sistemi

Veri içinde önemli dünya olaylarını keyword bazlı olarak etiketledim:

- Finansal Kriz (2008)
- Bitcoin / Kripto
- iPhone / Mobil Devrim
- Heartbleed / Güvenlik açıkları
- Facebook / Gizlilik
- COVID-19
- GPT-3 / Yapay Zeka

Her haber başlığını ve içeriğini bu anahtar kelimelerle eşleştirdim.

## Yaptığım Analizler
### Yıllara Göre Olay Dağılımı

Hangi yılda hangi olayın daha çok konuşulduğunu inceledim.

### Isı Haritası (Heatmap)

Olayların zaman içindeki yoğunluğunu görselleştirdim.

### En Popüler Haberler

Her olay için en çok upvote alan haberleri çıkardım.

### Zaman Serisi Analizi

Olayların yıllık ve aylık değişimini analiz ettim.

### Etki Profili Analizi

Şu metrikleri normalize ederek karşılaştırdım:

- Toplam story sayısı
- Ortalama puan
- Ortalama yorum sayısı
- Maksimum etkileşim

## Elde Ettiğim Sonuçlar
- iPhone ve mobil devrim en uzun süreli etkiyi yaratan alanlardan biri oldu
- Bitcoin belirli dönemlerde ani yükselişler gösterdi
- COVID-19 kısa ama çok yoğun bir etki oluşturdu
- Güvenlik olayları teknoloji topluluğunda ciddi yankı buldu
  
## Sonuç

Bu projede Hacker News verisini kullanarak şunu göstermeye çalıştım:

Teknoloji dünyasında yaşanan büyük olaylar, dijital platformlarda iz bırakıyor ve bu izler veriyle okunabiliyor.
