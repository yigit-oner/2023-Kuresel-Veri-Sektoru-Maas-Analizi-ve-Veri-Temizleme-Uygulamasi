# 2023-Kuresel-Veri-Sektoru-Maas-Analizi-ve-Veri-Temizleme-Uygulamasi
Veri sektörü çalışanlarının maaş ve iş özelliklerini incelediğim, eksik veri simülasyonu, istatistiksel veri doldurma teknikleri ve özellik mühendisliği (Feature Engineering) adımlarını içeren kapsamlı veri analizi projesi.

Bu projede 2023 yılına ait küresel veri bilimi, veri mühendisliği ve analitik rollerindeki çalışanların maaşlarını, deneyim seviyelerini ve çalışma koşullarını inceledim. Amacım sadece mevcut veriyi görselleştirmek değil, aynı zamanda ham bir veriyi analize hazır hale getirmek için gereken veri temizleme ve öznitelik türetme süreçlerini uygulamalı olarak göstermekti.

Projeyi geliştirirken izlediğim adımlar ve uyguladığım yöntemler şunlardır:

1. Eksik Veri Simülasyonu Gerçek hayat senaryolarına hazırlıklı olmak adına, elimdeki temiz veri setinin belirli bir oranına (%3) rastgele eksik değerler (NaN) atayan özel bir fonksiyon yazdım. Böylece veri temizleme yeteneklerimi test edebileceğim bir ortam oluşturdum.

2. Veri Dağılımı ve Doldurma Stratejisi Eksik verileri rastgele doldurmak yerine istatistiksel yöntemlere başvurdum. Sayısal değişkenlerin KDE grafiklerini çizdirdim ve çarpıklık (skewness) değerlerini hesapladım.

Simetrik dağılan değişkenleri ortalama (mean) ile doldurdum.

Çarpık dağılan değişkenleri, aykırı değerlerden etkilenmemesi için medyan (median) ile doldurdum.

3. Gelişmiş Veri Doldurma Maaş gibi kritik değişkenlerde genel ortalamayı kullanmak yanıltıcı olabilirdi. Bu yüzden "job_title" (iş unvanı) bazında gruplama yaparak, eksik maaş verilerini o pozisyonun kendi ortalamasıyla doldurdum. Bu sayede verinin tutarlılığını korudum.

4. Aykırı Değer Tespiti (Outlier Detection) Maaş verilerindeki uç değerleri tespit etmek için IQR (Interquartile Range) yöntemini kullandım. Alt ve üst sınırları belirleyerek verinin genel dağılımını bozan noktaları istatistiksel olarak saptadım.

5. Özellik Mühendisliği (Feature Engineering) Analizi derinleştirmek için mevcut verilerden yeni değişkenler türettim:

salary_range: Maaşları belirli aralıklara göre Low, Medium ve High olarak kategorize ettim.

is_international: Çalışanın yaşadığı ülke ile şirketin bulunduğu ülkeyi karşılaştırarak, kişinin sınır ötesi (uluslararası) çalışıp çalışmadığını tespit eden bir etiket oluşturdum.

6. Görselleştirme Korelasyon haritaları (Heatmap) ile değişkenler arasındaki ilişkileri, Boxplot ile şirket büyüklüğü ve çalışma ortamının maaş üzerindeki etkilerini görselleştirdim. Ayrıca belirli lokasyonlardaki (örneğin Avustralya) iş dağılımlarını filtreleyen fonksiyonlar geliştirdim.

Kullanılan Teknolojiler: Python, Pandas, NumPy, Seaborn, Matplotlib, Missingno.
