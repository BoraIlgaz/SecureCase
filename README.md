# 🔐 Secure Case - Akıllı Güvenlik ve IoT Kasa Sistemi
**Secure Case**, fiziksel güvenliği modern IoT teknolojileriyle birleştiren, gerçek zamanlı takip ve uzaktan kontrol imkanı sunan bir akıllı güvenlik projesidir. Kasa kapağının izinsiz açılmasını algılar ve kullanıcıyı anında mobil bildirimlerle uyarır.
---
## 🖼️ Proje Görselleri ve Tasarım
Sistemin donanım mimarisi ve fiziksel yapısı aşağıda detaylandırılmıştır:

| **1. Devre Şeması (P1)** | **2. İç Tasarım ve Sensör (P2)** | **3. Kasa Genel Görünüm (P3)** |
| :--- | :--- | :--- |
| ![Devre Şeması](Screenshots/p1.jpg) | ![İç Tasarım](Screenshots/p2.jpg) | ![Proje Fotoğrafı](Screenshots/p3.jpg) |
| *Sistemin elektronik bağlantı planı.* | *Mesafe sensörünün stratejik konumu.* | *Bitmiş projenin dış görünüşü.* |

---
## 🚀 Proje Genel Bakış
Sistem, kasanın içine yerleştirilen bir mesafe sensörü (p2) aracılığıyla kapağın konumunu sürekli takip eder. Güvenlik modu aktifken gerçekleşen herhangi bir hareket (kapak açılması), sistemi alarm durumuna geçirir.
* **Fiziksel Uyarı:** Kasa üzerinde bulunan **Buzzer** ve **LED** aracılığıyla sesli ve ışıklı alarm verilir.
* **IoT Takip:** **MQTT** protokolü kullanılarak kasanın durumu anlık olarak mobil uygulamaya iletilir.
* **Uzaktan Kontrol:** Mobil uygulama üzerinden güvenlik modu tek tuşla açılıp kapatılabilir.
---
## 🛠️ Teknik Bileşenler
### Donanım (Hardware)
* **Mesafe Sensörü (Ultrasonik):** Kasa kapağının açıklık durumunu hassas bir şekilde ölçer.
* **Buzzer & LED:** İzinsiz giriş denemelerinde yerinde sesli ve görsel uyarı sağlar.
* **Mikrodenetleyici:** Sensör verilerini işler ve Wi-Fi üzerinden buluta bağlanır.
### Yazılım (Software)
* **MQTT Protokolü:** Düşük gecikmeli, güvenilir veri iletimi sağlar.
* **Mobil Uygulama:** Güvenlik durumunu yönetmek ve bildirim almak için tasarlanmış arayüz.
* **Gömülü Yazılım:** Sensör verilerini analiz eden ve MQTT haberleşmesini yöneten C++ tabanlı yazılım.
---
## ⚙️ Çalışma Mantığı
1.  **Güvenlik Aktif:** Mobil uygulamadan güvenlik modu açılır. Mesafe sensörü kapağın kapalı olduğunu doğrular.
2.  **İzinsiz Giriş:** Kapak açıldığında mesafe artar. Sistem bu farkı algılar.
3.  **Alarm Durumu:** Aynı anda Buzzer öter, LED yanıp söner ve MQTT üzerinden telefona "Kasa Açıldı!" bildirimi gider.
4.  **Devre Dışı Bırakma:** Kullanıcı kapağı açmak istediğinde önce mobil uygulamadan güvenliği kapatır, böylece alarm tetiklenmeden kasaya erişebilir.
---
## 🔓 Lisans
Bu proje **MIT Lisansı** ile korunmaktadır.
