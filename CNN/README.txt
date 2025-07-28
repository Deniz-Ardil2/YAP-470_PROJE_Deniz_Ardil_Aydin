Burada dosyaların neler olduğunu ve ne işe yaradıklarını kısaca açıklayacağım.Kodların içinde de detaylı açıklamalar bulunmakta.*.ipynb dosyalarında belirttiğim gibi sürekli bir warning alıyorum kodu bozmuyor orada duruyor sadece.

Yöntem2_Test.ipynb
Sırayla en iyi CNN versiyonlarını yüklüyor ve sırayla test ediyor bunların confusion matrixlerini veriyor. Ayrıca Classification Reportlarını da veriyor buradaki sonuçlara baktığımda ne bşaarılı modelin 64x64 olan model olduğunu söyleyebilirim.

Önemli Not:kullanılan modellerin ismini ben sonradan değiştirdim ki daha anlaşılır olsun bu sebeple eğer önce alttaki dosyaları test ederseniz ordan çıkan yeni isimli dosyalar Yöntem2_test dosyamın çalışmasını engelleyebilir.

Vakitim yetişmediği için böyle bir sıkıntı yaşadım biraz daha vaktim olsaydı bu hatayı düzeltebilirdim ancak modelleri tekrar eğitmem gerekirdi kodu kontrol etmek için ve buna yeterli vaktim yoktu günlerdir aralıksız model eğitiliyor.Puanım kırılabileceğinin farkındayım Ama detaylı bir açıklama yapmak istedim.

Saygılarımla
Deniz





64x64_CNN.ipynb

Bu dosyada 64x64 boyutuna yeniden boyutlandırılmış görüntülerle bir CNN modeli eğitilmiştir.
Model, 2 adet konvolüsyon + max pooling katmanı ve ardından bir fully connected (dense) katman içerir.
Dropout uygulanarak overfitting riski azaltılmıştır.
Modelin doğruluğu (accuracy) eğitim ve doğrulama setleri üzerinde takip edilmiştir.
En iyi model, best_model_64x64.keras adıyla kaydedilmiştir.
Eğitim süresi görece kısa(2.5 saat civarı sürdü), başarı oranı ise en yüksek çıkan dosyamdır.

Önemli Not:Dosyayı tekrar çalıştırırsanız bu ilk yazdığım dosya olduğu için tüm grid searchte eğitilen modelleri kaydediyor o yüzden bir anda 16 dosya beliricektir.Ben githuba boyut yetersizliğinden bunları silerek attım.


64x64_Dataset_2_CNN.ipynb
Yukardakilerin aynısını sadece grayscale imagelar olan dataset 2 ile yapar.Bu dosya tüm modelleri kaydetmez daha doğrusu kaydetse de en iyi hariç bu modelleri siler.

best_model_64x64_Dataset_2.keras en iyi modelidir

128x128_CNN.ipynb

Görseller 128x128 çözünürlüğe çıkarılmış, daha fazla detay korunmuştur.
Daha büyük filtre boyutları ve daha derin bir mimari kullanılmıştır.
Eğitim süresi gözle görülür şekilde artmıştır(yaklaşık 7 saat sürmüştü sanırsam).
Modelin çıktısı: best_model_128x128.keras

128x128_Dataset_2_CNN.ipynb
128x128 çözünürlükteki model, Dataset_2 ile yeniden eğittiğim versiyonu.
Karşılaştırma amacıyla yapılmıştır.

Model çıktısı: best_model_128x128_Dataset_2.keras

Ekstra:
128x128_model_1.keras – Model çıktısı
128x128_model_2.keras – Model çıktısı
Farklı hiperparametre kombinasyonları ile eğitilmiş modellerin çıktılarıdır.Modellerin kalmasını istediğiniz için silmedim
Karşılaştırma ve en iyi sonucu veren modelin seçilmesi amacıyla kaydedilmişti.

212x212_CNN.ipynb
Görsel boyutu 212x212’ye çıkarılmış, bu da modeli daha derin hale getirmiştir.
Çok daha fazla parametre içerdiğinden eğitim süresi uzundur.
Grid Search'i bu sebeple daha kısa tuttum çünkü 8 model eğitmesi bile 10 saatten fazla aldı.
Bu deney, yüksek çözünürlüğün model başarısına etkisini test etmek için yapılmıştır.
Ironik olarak en başarısız cnn modelimdir test dosyama göre.

En iyi model: best_model_212x212.keras

Ekstralar: 
 212x212_model_5.keras – Eğitim sonucu model dosyası
 best_model_212x212_overall.keras – Grid search sonrası en iyi model


