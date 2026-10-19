# Dijital Sinyal İşleme ile Sinyal Sınıflandırma

## Özet

Bu notebook (`DSP_Sinyal_Siniflandirma.ipynb`), motor titreşimlerini taklit eden yapay sinyallerden yola çıkarak motorun hızını (Düşük / Orta / Yüksek) tahmin eder. Akış şöyledir:

1. **Sinyal üretme:** Gürültü, DC ofset, trend ve 50 Hz parazit içeren sinyaller oluşturulur.
2. **Ön işleme:** DC ofset ve trend kaldırılır (detrend).
3. **Filtreleme:** Butterworth alçak geçiren filtre `filtfilt` ile uygulanır.
4. **Öznitelik çıkarma:** Her sinyalden RMS, sıfır geçiş sayısı, baskın frekans gibi değerler hesaplanır.
5. **Eğitim/test ayırma:** Veri %70 eğitim, %30 test olarak bölünür.
6. **Sınıflandırma:** k-NN modeli eğitilir.
7. **Yorumlama:** Doğruluk, karışıklık matrisi ve hatalı örnekler incelenir.

Her kod hücresinin üstünde açıklama bulunur.

## Kurulum

Proje klasöründe bir sanal ortam (venv) oluşturun ve etkinleştirin:

```bash
python -m venv venv

# macOS / Linux
source venv/bin/activate

# Windows
venv\Scripts\activate
```

Gerekli kütüphaneleri yükleyin:

```bash
pip install -r requirements.txt
```

## Çalıştırma

```bash
jupyter notebook DSP_Sinyal_Siniflandirma.ipynb
```

Hücreleri yukarıdan aşağıya sırayla çalıştırın (`Shift + Enter`). İşiniz bitince ortamdan `deactivate` komutuyla çıkabilirsiniz.
