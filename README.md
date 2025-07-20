# 🧠 Face Recognition AI – Kendi Yüzünü Tanıyan Yapay Zeka Modeli

Bu proje, staj kapsamında kendi yüzünü tanıyabilen bir yapay zeka modeli geliştirmek amacıyla oluşturulmuştur. Amaç, kişisel yüz görüntülerinden özel bir veri seti oluşturarak YOLOv8 tabanlı bir nesne algılama modeli eğitmek ve bu modeli hem test verileriyle hem de canlı kamera görüntüsüyle test etmektir.

> 🔐 **Gizlilik Notu:** Veri seti kişisel yüz fotoğraflarını içerdiğinden paylaşılmamıştır. Ancak model eğitimi, tahmin süreci ve canlı kamera testi için kullanılan tüm kod ve yapılandırmalar bu projede yer almaktadır.

---

## 🌟 Projenin Amacı

- Kendi yüz fotoğraflarından oluşan özgün bir veri seti oluşturmak  
- YOLOv8 modeli ile yüz tespiti yapabilen bir yapay zeka modeli eğitmek  
- Eğitilen modeli test görüntüleri ve webcam ile canlı olarak test etmek

---

## ⚙️ Kullanılan Teknolojiler

| Teknoloji | Kullanım Amacı |
|----------|----------------|
| **Python** | Model eğitimi ve tahmin süreci |
| **Google Colab** | GPU destekli bulut ortamında model eğitimi |
| **Roboflow** | Görsel veri etiketleme ve YOLOv8 formatında dışa aktarma |
| **Ultralytics YOLOv8** | Nesne algılama modeli |
| **OpenCV** | Görüntü işleme ve çizim işlemleri |
| **Colab Webcam API** | Canlı kamera ile model testi |

---

## 🖼️ Veri Seti Özeti

- **Toplam Görsel:** 130 adet
- **Fotoğraf Özellikleri:**  
  - Farklı açılar (ön, sağ, sol, yukarı, aşağı)  
  - Farklı ışık koşulları  
  - Farklı yüz ifadeleri
- **Etiketleme:** Roboflow üzerinde bounding box ile yalnızca kendi yüzüm etiketlendi
- **Veri Formatı:** YOLOv8 (COCO uyumlu)

---

## 🧠 Model Eğitimi

| Parametre | Değer |
|-----------|-------|
| Model tipi | YOLOv8n (lightweight) |
| Eğitim süreci | 30 epoch |
| Görüntü boyutu | 640x640 px |
| Batch boyutu | 8 |
| Ortam | Google Colab (T4 GPU) |

### Eğitim Sürecinde Gözlemler:
- Box ve Class Loss değerleri eğitim boyunca düzenli olarak azaldı  
- Overfitting görülmedi  
- mAP ve Recall değerleri 25. epoch sonrası stabilize oldu

---

## 📊 Eğitim Sonuçları

| Metrik | Değer |
|--------|-------|
| **Precision** | ~0.99 |
| **Recall** | ~1.00 |
| **mAP@0.5** | 1.00 |
| **mAP@0.5:0.95** | ~0.75 |
| **Box Loss (Val)** | ~1.0 |
| **Class Loss (Val)** | ~0.8 |
| **DFL Loss (Val)** | ~1.3 |

📈 Eğitim grafikeri ve metrik tablosu `results.png` ve `results.csv` dosyaları ile birlikte `yolov8_training_report.pdf` raporunda sunulmuştur.

---

##  Model Testi ve Gerçek Zamanlı Uygulama

Model, test görselleri üzerinde başarılı sonuçlar vermiştir. Ayrıca, Google Colab üzerinde çalışan bir canlı kamera arayüzü ile çekilen fotoğraflar modele verilmiş ve yüz doğru şekilde tespit edilerek kutu (bounding box) çizilmiştir.

### 🔍 Canlı Kamera Testi:
- Fotoğraf tarayıcıdan çekildi
- YOLOv8 tahmini yapıldı
- Tespit edilen yüz üzerine kutu başarıyla çizildi

---

## 📁 Proje İçeriği

```
├── yolov8_training_report.pdf   # Eğitim grafikeri ve metrik özeti
├── face-recog-miniproject.ipynb                  # Tüm eğitim ve test sürecini içeren Colab notebook
└── README.md                    # Bu dosya
```

---

## 👤 Geliştirici

**AI Trainee:** [ademvnc](https://github.com/ademvnc)  
📍 Yazılım.xyz 2025 Yaz Stajı – Yapay Zeka Bölümü

---

## 📌 Notlar

- Model yalnızca eğitilen yüzü tanımak üzere özelleştirilmiştir
- Çok kişi için kullanılacaksa daha geniş veri seti gereklidir
- Canlı testler Colab içinde çalıştırılabilir ve tarayıcıya erişim gerekir

---

## 🔗 Proje Bağlantısı

🔗 GitHub Repository:  
https://github.com/ademvnc/face-recognition-project

