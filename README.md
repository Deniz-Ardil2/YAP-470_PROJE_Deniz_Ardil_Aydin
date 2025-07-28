# YAP-470_PROJE_Deniz_Ardil_Aydin
# Farklı Öznitelik Çıkarım Yöntemleriyle Görüntü Sınıflandırma ve Karşılaştırmalı Makine Öğrenmesi Modelleri HOCAM YÖNTEM 2 AÇIKLAMA README DOSYASI CNN KLASÖRÜ İÇİNDE

Bu projede 2 farklı veri seti ile görselden duygu tanıma gerçekleştirilmiştir. HOG, LBP ve Gabor gibi öznitelikler çıkarılarak SVM, MLP, Random Forest ve XGBoost algoritmaları ile sınıflandırma yapılmıştır.


## Önemli Not: 
    - Sayın Hocam projedeki en başarlı modelleri test etmek için test_dosyası kullanılıyor ilgili açıklama aşağıda ve dosyanın en üstünde bulunmakta.
    - Sayın Hocam projeyi test ederken (test_dosyası) önceden hazırlanmış bir pca kullanılıyor ilgili açıklama test_dosyasının altında bulunmakta



## Kullanılan Veri Setleri
1. Dataset 1 (RGB):
   - Veri Seti indirme linki : https://www.kaggle.com/datasets/sujaykapadnis/emotion-recognition-dataset
   - Progress Report 2 dosyamda ya da önceki progress report dosyamda detaylı açıklama bulunmakta
   - 5 sınıf, toplam 14.248 görsel bulunuyor

2. Dataset 2 (grayscale):
   - https://www.kaggle.com/datasets/chiragsoni/ferdata
   - Üstteki veri seti gibi detaylı açıklama raporumda bulunuyor
   - 5 sınıf, toplam 17.460 görsel bulunuyor


Not: 2 veri setinde bulunan sınıflar ortaktır.     
     
## 📚 Jupyter Notebook Dosyaları

### train_hog.ipynb
- HOG öznitelik çıkarımı yapılır.Yukarda belirttiğim 4 farklı Model (SVM, MLP, Random Forest ve XGBoost) ile eğitim yapılır
- Her modelde ayrı ayrı birçok hiperparemetre denedim.
- Eğitimler sonucunda sonuçları inceledikten sonra en iyi modele karar verdim.
- En iyi modeli `model_hog_svm.pkl` olarak kaydettim.
- Şuan dosyada commentlenmiş bir şekilde bu kaydetme aşaması duruyor.

### train_lbp.ipynb
- LBP öznitelik çıkarmı yapılır. Yukarda belirttiğim 4 farklı Model (SVM, MLP, Random Forest ve XGBoost) ile eğitim yapılır
- Her modelde ayrı ayrı birçok hiperparemetre denedim.
- Eğitimler sonucunda sonuçları inceledikten sonra en iyi modele karar verdim.
- En iyi modeli `model_lbp_mlp.pkl` olarak kaydettim.
-  Şuan dosyada commentlenmiş bir şekilde bu kaydetme aşaması duruyor

### train_gabor.ipynb
- Gabor öznitelik çıkarımı yapıldıktan sonra ve ardından belirtilen 4 model ile eğitim yapılır. 
- Her modelde ayrı ayrı birçok hiperparemetre denemesi yaptım.
- En iyi doğruluk oranı veren modeli  `model_gabor_mlp.pkl` olarak kaydettim.

### train_combined_features.ipynb
- HOG, LBP ve Gabor öznitelikleri bu dosyada birleştirildi.
- PCA uygulanır (varyansın %95’ini korur)
- 4 farklı model(SVM, MLP, Random Forest ve XGBoost) ile eğitim yapılır
- En iyi model `model_combined_features_svm.pkl` olarak kaydedilir

### test_dosyası.ipynb


- Bu dosyada,öncelikle test amaçlı olarak HOG, LBP ve Gabor öznitelikleri ayrı ayrı çıkarılır.
- Her bir öznitelik grubu için en yüksek başarıya sahip ilgili önceden eğitilmiş model (model_hog_svm.pkl, model_lbp_mlp.pkl, model_gabor_mlp.pkl) yüklenir.
- Test sonuçları böylece karşımıza gelir.
- Ardından üç öznitelik grubu birleştirilerek PCA uygulanır (varyansın %95’ini koruyacak şekilde).
- PCA sonrası elde edilen veriler, model_combined_features_svm.pkl modeliyle test edilir.
- Modelin beklediği giriş formatı, PCA sayesinde sağlanarak eğitim-test tutarlılığı korunur.

## Not:
-En iyi model olarak kaydedilen modeller üstte verilen isimlerle bulunmakta.

### *_dataset_2.ipynb
- Yukarıdaki adımların aynıları ikinci veri setiyle yapıldı
- Tüm dosya isimlerinin sonunda `_dataset_2` vardır.
- 2.veri seti için ayrı model oluşturulmamıştır çünkü tüm kod aynıdır.
- 2.veri seti jupider dosyaları ile 1.veri seti jupiter dosyaları arasındaki tek fark veri yoludur.
- 1.veri setini kullanan modeller Data klasöründen veri alırken 2.veri setini kullanan modeller Data_2 klasöründen veri alırlar

## ⚙️ Teknik Detaylar
- Her dosyada eğitim ve test çıktıları vardır görünmektedir.
- Her dosya için en iyi model  `.pkl` formatında kayıtlıdır
- Jupyter dosyaları açıldığında çeşitli ara sonuçlar vardır.
- Tekrar çalıştırılabilmektedir
- Değerlendirme metrikleri: `accuracy`, `precision`, `recall`, `f1`

## 📌 Önemli Not
- Eğitim ve test verileri ayrı tutulmuştur.
- İlgili jupyter dosyasında eğitim ve test verilerinin boyutunu gösteren açıklamalar vardır 

