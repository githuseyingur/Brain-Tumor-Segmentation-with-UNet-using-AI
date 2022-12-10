# Brain Tumor Segmentation with U-Net using AI
<br />
<p>Beyin tümörünün MRI görüntüleri üzerinden manuel segmente edilmesi çok zaman alan bir yöntemdir ve performans büyük ölçüde hekimin deneyimine bağlıdır. Bu yüzden derin öğrenme yöntemleri kullanılarak MRI görüntülerinden beyin tümör segmentasyonunun otomatik olarak yapılması tümörün verimli bir şekilde belirlenmesini sağlamaktadır. Bu çalışmada beyin tümör segmentasyonu için CNN tabanlı bir U-Net modeli kullanılmıştır. </p>

#### Projenin ilk aşamasında tam tümör segmentasyonu yapan bir model, ikinci aşamasında ise tümörün farklı alanları için segmentasyon yapan başka bir model başarılı bir şekilde oluşturulmuştur. Son olarak tahmin görselleri birleştirilerek elde edilen sonuçlar karşılaştırılmıştır.


<br /><br />
### VERİ SETİ (BraTS 2019)

Veri seti, 335 adet eğitim ve 127 adet doğrulama olmak üzere toplam 462 veri içermektedir. Her bir veri aynı görüntü için Flair, T1, T1c ve T2 olmak üzere dört farklı tür görüntüden oluşmaktadır. Ek olarak bir adet de orijinal segmentasyon görüntüsü yer almaktadır.

Tam tümör, genişleyen tümör alanı ve ödemsiz tümör alanı olmak üzere her biri için segmentasyon yapan toplam üç model kullanılmıştır. Her bir model eğitimi, görüntülerin belirli kesit aralığı alınarak 7770 adet veri ile gerçekleştirilmiştir. Bu modellerin tahminleri birleştirilerek sonuç görseli elde edilmiştir.

 Veri seti içerisinde her bir veri içerisinde bulunan dosyalara ait kesitler: 
 <br />

![data_set](https://user-images.githubusercontent.com/120099096/206864407-ca65e05b-06b2-48e1-8076-78ad18dec599.png)
![data_set2](https://user-images.githubusercontent.com/120099096/206864409-8c3fd7f3-406f-4be5-8fa0-7266b00c31d4.png)

<br /><br />

### U-NET

U-Net modelinden bahsetmek gerekirse; oluşturulan U-Net modeli, Sıkışma ve Genişleme olmak üzere iki kısımdan oluşmaktadır. Sıkışma yolunda boyut azaltma işlemi yapılırken, Genişleme yolunda boyut arttırma işlemi gerçekleştirilmektedir. Belirtilen bu iki yoldaki her katman birden fazla Evrişim(Convolutional) katmanı ve bir adet Ortaklama(Pooling) katmanından oluşmaktadır. Pooling katmanında Maksimum Pooling yöntemi uygulanmaktadır. Modelin ikinci yarısında yani Genişleme yolunda boyut arttırma işlemi gerçekleştirileceği için Ters Evrişim katmanları bulunmaktadır. Modelde yer alan Evrişim katmanlarını ReLU adında bir aktivasyon fonksiyonu aktive etmektedir. Bu fonksiyon modelin negatif değerleri öğrenmesini engellemektedir.

U-Net modelinin, diğer CNN (Convolutional Neural Network) mimarilerinden farkı ve avantajı ise özellik haritalarının(Feature Maps) sıkışma yolundaki her katmandan genişleme yolundaki her katmana yatay bir şekilde bağlantı kurularak aktarılmasıdır. Bu işleme Copy and Corp denilmektedir. Bu işlemle, boyut azaltma işlemi ile kaybedilen özellikler Genişleme yolunda tekrar kazanılmaktadır. U-Net mimarisinde özellikler, özellik haritalarının bağlantılı bir şekilde kopyalanması sayesinde kaybedilmemektedir.
 <br />
 
![U_net](https://user-images.githubusercontent.com/120099096/206864660-8602de60-5f69-4ea8-8673-3921dd82a544.png)

<br /><br />

### SONUÇLAR

#### 1. Aşama - Tam Tümör Segmentasyonu Prediction <br /><br />

![1](https://user-images.githubusercontent.com/120099096/206865925-4fb76413-acd4-427d-8486-f27df6375cbe.png) <br /><br />

![2](https://user-images.githubusercontent.com/120099096/206866032-d2c7a156-84e2-45af-a7f5-1ec63ddbfbee.png) <br /><br />

![4](https://user-images.githubusercontent.com/120099096/206866037-e02e3b05-db26-40e8-b687-7b318f914143.png) <br /><br />

![1000_Inferno](https://user-images.githubusercontent.com/120099096/206866041-91e8af00-e833-444a-b428-06e33d3500d4.png) <br /><br /><br /><br />

#### 2. Aşama - Farklı Alanlar İle Tümör Segmentasyonu Prediction <br /><br />

Sonuçlar incelendiğinde Orijinal Segmentasyon görüntülerine çok yakın sonuçlar elde edilmiştir. Bir radyolog tarafından segmentasyonu yapılan görüntülerin, saniyeler içerisinde segmentasyonu otomatik olarak gerçekleştirilebilmektedir. Eğitim verileri için %96 ve doğrulama verileri için %82 başarı oranı elde edilmiştir. <br /><br />
<br /><br />
 
![Results](https://user-images.githubusercontent.com/120099096/206864960-0b4503ad-65f4-46f3-a70f-852eaf9a87bd.png)  <br /><br />


![Results2](https://user-images.githubusercontent.com/120099096/206865220-81f9e9a0-e616-40aa-9438-0375a4e18679.png) <br /><br />


![1772_test](https://user-images.githubusercontent.com/120099096/206865363-c1be903c-c719-48cd-a5f7-46402b8c71c4.png) <br /><br /> <br /><br /><br /><br />

![AccuracyTable](https://user-images.githubusercontent.com/120099096/206866196-4b5068d1-47e8-4309-85de-ff124c34f446.png)




