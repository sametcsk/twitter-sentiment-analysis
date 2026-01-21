# Twitter Duygu Analizi (Sentiment Analysis)

Bu projede, İngilizce tweetlerin **pozitif** mi yoksa **negatif** mi olduğunu tahmin eden bir makine öğrenmesi modeli geliştirdim. Veri seti olarak Kaggle'daki meşhur **Sentiment140** veri setini kullandım.

##  Ne Yaptım?

Twitter verileri çok kirli olduğu için (linkler, @mentions, garip işaretler) önce ciddi bir **veri temizliği** yaptım. 

Projede izlediğim adımlar şunlar:

1.  **Veri Temizliği:** Regex kullanarak linkleri ve kullanıcı adlarını sildim.
2.  **Akıllı Stopwords:** "the", "is", "at" gibi gereksiz kelimeleri attım ama cümlenin anlamını değiştiren **"not", "never", "no"** gibi kelimeleri özellikle tuttum.
3.  **Vektörleştirme:** Metinleri sayısal verilere çevirmek için **TF-IDF** yöntemini kullandım.
4.  **Modelleme:** 3 farklı algoritmayı yarıştırdım:
    * Logistic Regression
    * Naive Bayes
    * Random Forest

##  Sonuçlar

Modelleri test ettiğimde en iyi sonucu **Logistic Regression** verdi.

* **Logistic Regression: %79 Başarı** 
* Naive Bayes: %77.5
* Random Forest: %76.2

## 💻 Nasıl Çalıştırılır?

Projeyi kendi bilgisayarınızda denemek isterseniz:

1.  Gerekli kütüphaneleri yükleyin:
    ```bash
    pip install pandas numpy scikit-learn nltk matplotlib seaborn wordcloud
    ```

2.  Kodu çalıştırın. En sonda `tahmin_et` fonksiyonu ile kendi cümlelerinizi test edebilirsiniz.

```python
# Örnek kullanım:
tahmin_et("I love this project, simple and effective!")
# Çıktı: POZİTİF