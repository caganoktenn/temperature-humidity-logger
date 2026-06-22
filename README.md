# Temperature & Humidity Data Logger

A DHT11-based temperature and humidity logger built on Arduino R4 Minima, featuring real-time OLED display and SD card data storage. Logged data is analyzed and visualized using a Python script.

## Hardware

- Arduino R4 Minima
- DHT11 temperature & humidity sensor
- SSD1306 OLED display (I2C)
- SD card module

## Features

- Real-time temperature and humidity readings from the DHT11 sensor
- Live display of readings on the OLED screen
- Continuous logging of sensor data to an SD card (`LOG.CSV`)
- Python-based post-processing script (`analyze.py`) using pandas and matplotlib to visualize trends over time

## Repository Structure

```
temperature-humidity-logger/
├── logger/
│   └── logger.ino        # Arduino sketch: sensor reading, OLED display, SD logging
├── analyze.py             # Python script for analyzing and plotting logged data
├── LOG.CSV                # Example logged data
├── circuit_photo_1.jpg    # Circuit setup photo
└── circuit_photo_2.jpg    # Circuit setup photo
```

## How It Works

1. The Arduino reads temperature and humidity from the DHT11 sensor at fixed intervals.
2. Readings are displayed live on the OLED screen.
3. Each reading is appended as a new row to `LOG.CSV` on the SD card.
4. After data collection, `analyze.py` reads `LOG.CSV` with pandas and generates a plot of temperature and humidity over time.

## Running the Analysis Script

```bash
pip install pandas matplotlib
python analyze.py
```

## Circuit

See `circuit_photo_1.jpg` and `circuit_photo_2.jpg` for the physical setup.

## Notes

This project was built as a hands-on introduction to embedded sensor integration, I2C communication, and SD card file I/O on Arduino, paired with basic data analysis in Python.

---

# Sıcaklık & Nem Veri Kaydedici

DHT11 sensörü ile çalışan, Arduino R4 Minima üzerinde gerçek zamanlı OLED ekran gösterimi ve SD karta veri kaydı yapan bir sıcaklık-nem logger projesi. Kaydedilen veriler Python scripti ile analiz edilip görselleştiriliyor.

## Donanım

- Arduino R4 Minima
- DHT11 sıcaklık & nem sensörü
- SSD1306 OLED ekran (I2C)
- SD kart modülü

## Özellikler

- DHT11 sensöründen gerçek zamanlı sıcaklık ve nem ölçümü
- Ölçümlerin OLED ekranda anlık gösterimi
- Sensör verilerinin SD karta sürekli olarak kaydedilmesi (`LOG.CSV`)
- Kaydedilen verinin zaman içindeki değişimini görselleştirmek için pandas ve matplotlib kullanan Python scripti (`analyze.py`)

## Repo Yapısı

```
temperature-humidity-logger/
├── logger/
│   └── logger.ino        # Arduino kodu: sensör okuma, OLED gösterim, SD kayıt
├── analyze.py             # Kaydedilen veriyi analiz eden ve grafikleyen Python scripti
├── LOG.CSV                # Örnek kayıt verisi
├── circuit_photo_1.jpg    # Devre kurulum fotoğrafı
└── circuit_photo_2.jpg    # Devre kurulum fotoğrafı
```

## Nasıl Çalışıyor

1. Arduino, belirli aralıklarla DHT11 sensöründen sıcaklık ve nem verisi okuyor.
2. Ölçümler OLED ekranda anlık olarak gösteriliyor.
3. Her ölçüm, SD karttaki `LOG.CSV` dosyasına yeni bir satır olarak ekleniyor.
4. Veri toplama tamamlandıktan sonra `analyze.py`, pandas ile `LOG.CSV`'yi okuyup zaman içindeki sıcaklık ve nem değişimini gösteren bir grafik üretiyor.

## Analiz Scriptini Çalıştırma

```bash
pip install pandas matplotlib
python analyze.py
```

## Devre

Fiziksel kurulum için `circuit_photo_1.jpg` ve `circuit_photo_2.jpg` dosyalarına bakabilirsin.

## Notlar

Bu proje; Arduino üzerinde sensör entegrasyonu, I2C haberleşmesi ve SD kart dosya işlemlerine pratik bir giriş, buna ek olarak Python'da temel veri analizi olarak geliştirildi.
