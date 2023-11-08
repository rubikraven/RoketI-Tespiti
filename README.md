# Hızlı Nesne Tespit Sistemi

## Açıklama

Filistin için güvenlik ihtiyaçlarını göz önünde bulundurarak tasarladığım bu sistem, Python ve OpenCV teknolojilerini kullanmaktadır. Sistem, uzaktan gelen hızlı hareket eden nesneleri (örneğin bir füze ışığı gibi) basit bir yöntemle tespit ederek uyarı sinyali verebilmektedir. En iyi sonuçlar için yüksek çözünürlüklü bir kamera kullanımı önerilmektedir.

## Özellikler

- Lazer pointer gibi hızlı hareket eden nesnelerin algılanması.
- Hız sınırı aşıldığında sesli uyarı verme.
- Kullanıcı dostu arayüz ve kolay kurulum.

## Kurulum

Projeyi kullanmadan önce gerekli olan Python paketlerini yüklemeniz gerekmektedir. Aşağıdaki adımları takip ederek sistemi kurabilirsiniz:

1. Gerekli Python paketlerini yükleyin:
```bash
pip install opencv-python
pip install numpy
