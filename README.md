# pishingEmailDetection-ml
Makine Öğrenimi ile Oltalama E-Posta Tespiti

## Giriş
Bu projede https://www.kaggle.com/datasets/subhajournal/phishingemails veri setini kullanarak kandırma,oltama amaçlı gönderilen e-postaların tespitini hedefledim.Günümüzde kullanıcıların tek tıkla kaybedebileceği bir çok kişisel veri,para,hesap vb. durumlardan onları korumak adına sahte e-postaları **otomatik ve etkili bir şekilde tespit edebilen bir model** oluşturarak dijital güvenliğe katkı sağlayan bir proje gerçekleştirdim.

Öncelikle veri setimdeki 'Label' sütununu makine öğrenmesi algoritmalarının anlayabilmesi için '0'(gerçek) ve '1' (phishing) olarak kodladım.
Daha sonra veri setimi daha temiz bir hale getirebilmek amacıyla ön işledim.Bunun için:
-Harfleri küçültme('lower()'),
-Noktalama silme(regex),
-Boşlukları temizleme('strip') gibi methodlar kullandım.
 Metin verilerini sayısal hale getirmek için **TF-IDF (Term Frequency - Inverse Document Frequency)** yöntemini kullandım.Bu yöntemle her kelimenin e-posta içindeki önemi sayısal skorlarla ifade edilerek modelin öğrenmesine uygun hale getirdim.TF-IDF skoru yüksek olan kelimeler, modelin sahte e-postaları daha etkili şekilde ayırt etmesinde önemli rol oynadı.
## Kullanılan Algoritmalar
Bu projede 
  - Logistic Regression  
  - Naive Bayes  
  - Decision Tree  
  - Random Forest  
  - K-Nearest Neighbors (KNN)  
  - Support Vector Machine (SVM)  
  - SGDClassifier  
  - LDA algoritmalarını denedim ve **cross_val_score** yöntemi ile bu algoritmaların verimliliğini kıyasladım.En yüksek doğruluk oranını elde ettiğim **Support Vector Machine(SVM)** modelini final model olarak kullandım.

# Metrikler
En yüksek doğruluk oranını veren **Support Vector Machine(SVM) modeli ile detaylı bir değerlendirme yaptım.Modelimin başarısını değerlendirmek için kullandığım **metrikler:**

-Confusion Matrix

-Accuracy

-Precision

-Recall

-F1-Score

**Confusion matrix** sonucum:

[[2140 69]
[ 30 1488]]
çıktı.
Bu matris, modelimin sınıfları ne kadar doğru tahmin ettiğini gösterdi:
- 2140 adet gerçek e-posta doğru şekilde tanındı.
- 1488 adet phishing e-posta doğru olarak yakalandı.
- 69 gerçek e-posta yanlışlıkla phishing zannedildi (false positive).
- 30 phishing e-posta gözden kaçtı, yani gerçek sanıldı (false negative).
-**Accuracy (Genel Doğruluk):** %97  
- **Precision:** Modelin "phishing" dediği e-postaların %96’sı gerçekten phishing.  
- **Recall:** Gerçek phishing e-postalarının %98’ini başarıyla yakaladı.  
- **F1-Score:** Precision ve Recall'un dengeli ortalaması → %97

Bu metrikler modelimin sahte e-posta için güçlü ve güvenilir olduğunu kanıtladı.Kullanıcıların güvenliğini sağlayacak bir sistemde yanlış alarm oranının düşük olması kritik öneme sahiptir.Yüksek başarı oranı, bu tür bir modelin siber güvenlik sistemlerinde gerçek hayatta da kullanılabileceğini gösteriyor.
# Sonuç ve Gelecek Çalışmalar

Bu proje ile, metin madenciliği ve makine öğrenmesi tekniklerini birleştirerek sahte (phishing) e-postaları tespit edebilen bir sistem geliştirdim.  
Gerçek hayatta insanların sadece bir tıkla önemli bilgilerini kaybettiği senaryoları düşündüğümde, bu çalışmanın dijital güvenlik adına **anlamlı ve uygulanabilir bir çözüm sunduğunu** düşünüyorum.

Support Vector Machine(SVM) modeli, %97 doğruluk oranıyla en yüksek başarıyı gösterdi.  
Model, hem sahte e-postaları doğru şekilde tespit edebildi hem de yanlış alarm oranını oldukça düşük tuttu.  
Bu sonuçlar, sistemin **güvenilir ve dengeli** olduğunu gösteriyor.

## Gelecek Çalışmalar
Ben yapay zeka ve siber güvenlik alanlarına ilgi duyan bir öğrenciyim.
Bu projeyi, yapay zeka ve siber güvenlik alanlarına olan ilgimi birleştirebileceğim bir başlangıç olarak gördüm.  
Aslında bu proje benim için nihai bir çözümden çok, **deneysel bir temel** ve ilerde yapmayı hayal ettiğim **daha özgün çalışmaların ilk adımıydı**.

Gerçek zamanlı sahte e-posta tespiti gibi konular günümüzde çokça ele alınıyor. Ben ise bu tarz klasik yaklaşımların ötesine geçerek, siber güvenlik problemlerini daha yaratıcı yöntemlerle çözmeyi hedefliyorum.  
Örneğin:
- E-posta içeriğinin sadece metinsel değil, **duygusal veya dilsel ton analizine dayalı olarak değerlendirilmesi**  
- Sosyal mühendislik saldırılarını anlamaya yönelik, kullanıcı davranışlarına göre **kişiselleştirilmiş güvenlik uyarı sistemleri**  
- AI destekli güvenlik uygulamalarının etik, adil ve şeffaf tasarlanması

Yani bu projeden elde ettiğim teknik kazanımları, ilerde daha özgün ve derinlikli fikirlerde kullanmak istiyorum.  
Benim amacım sadece modelleri denemek değil, yapay zekayı **daha anlamlı, yaratıcı ve sorumlu** bir şekilde kullanabilmek.

Bu projeyi ise, asıl hedefime ulaşmada bir basamak olarak görüyorum.

Bu proje, hem teknik anlamda bana çok şey kattı hem de ilgi duyduğum alanları nasıl bir araya getirebileceğimi görmemi sağladı.  
Gelecekte yapay zeka ve güvenliği birleştiren projeler geliştirerek bu alanda ilerlemeyi çok istiyorum.

# Linkler
Projeme ait tüm kodlar,teknik detaylar ve veri seti aşağıdaki linkte bulunmaktadır.
https://www.kaggle.com/code/beyzaceyhan/phishingemaildetection


